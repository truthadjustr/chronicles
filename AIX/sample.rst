Introduction
============

To get the operating system's version::

    root@aixbox::/> oslevel -s
    7100-03-05-1524
    root@aixbox::/> 
    root@aixbox::/>

To identify to what **HMC** is an **LPAR** attached to. From the LPAR's console, type this::

    root@aixbox::/> lsrsrc IBM.MCP
    Resource Persistent Attributes for IBM.MCP
    resource 1:
            MNName            = "192.168.100.1"
            NodeID            = 83908901111000123122
            KeyToken          = "svrhmc2"
            IPAddresses       = {"10.172.111.33"}
            ConnectivityNames = {"192.168.100.1"}
            HMCName           = "9042DR7*16BB22D"
            HMCIPAddr         = "10.172.111.33"
            HMCAddIPs         = "172.96.0.5"
            HMCAddIPv6s       = ""
            ActivePeerDomain  = ""
            NodeNameList      = {"aixbox"}
    resource 2:
            MNName            = "192.168.100.1"
            NodeID            = 1232138940938450059
            KeyToken          = "svrhmc1"
            IPAddresses       = {"10.172.111.32"}
            ConnectivityNames = {"192.168.100.1"}
            HMCName           = "9042DR7*16BB0FA"
            HMCIPAddr         = "10.172.111.32"
            HMCAddIPs         = "192.28.128.1"
            HMCAddIPv6s       = ""
            ActivePeerDomain  = ""
            NodeNameList      = {"aixbox"}
    root@aixbox::/>
