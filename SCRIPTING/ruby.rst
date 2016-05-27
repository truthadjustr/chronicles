Ruby
====

I highlight below an aspect of a programming language that just assumes too much and is hard to make sense of.

..  code-block:: ruby
    :emphasize-lines: 14

    require 'open-uri'
    require 'redis'

    URLS = %w[
        http://www.gutenberg.org/ebooks/98.txt.utf-8    
        http://www.gutenberg.org/ebooks/1400.txt.utf-8  
        http://www.gutenberg.org/ebooks/730.txt.utf-8   
        http://www.gutenberg.org/ebooks/766.txt.utf-8   
        http://www.gutenberg.org/ebooks/19337.txt.utf-8 
        http://www.gutenberg.org/ebooks/700.txt.utf-8   
    ]

    BOOKS = URLS.map(&File.method(:basename))
    REDIS = Redis.current

    URLS.each do |url|
        text = open(url)
        name = File.basename(url)

        text.each_line do |line|
            REDIS.pfadd(name,line.split(/\s+/).map(&:downcase))
        end
    end

    BOOKS.each do |name|
        puts "#{name}: #{REDIS.pfcount(name)}"
    end

    puts "All: #{REDIS.pfcount(*BOOKS)}"


