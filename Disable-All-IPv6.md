**1.**  In AdGuard homepage go to DNS settings, under DNS server configuration section 

* Check `Disable IPv6` option
 
#

**2.**  Open to unbound config file :
       
    sudo nano /etc/unbound/unbound.conf.d/unbound.conf
       
* Go to line 18 and set `do-ip6: yes` to  `do-ip6: no`
 
#

**3.**  Open to stubby config file :

    cd /etc/stubby/ && sudo rm stubby.yml && sudo nano stubby.yml
    
* comment the lines `246` to `249`

#

**4.**  Open cloudflared config file:

    sudo nano /etc/default/cloudflared
        
* Delete `--upstream https://2606:4700:4700::1111/dns-query --upstream https://2606:4700:4700::1001/dns-query`

#

**5.**  Open AcrylicConfiguration.ini file (Windows):

    C:\Program Files (x86)\Acrylic DNS Proxy
        
* Set `SinkholeIPv6Lookups=No`
#

**6.**  Go to https://www.dynu.com/en-US/ControlPanel/DDNS and select _Manage your hostname_(pencil under actions) and *turn off* `Wildcard IPv6 Alias` & `Enable IPv6 Address`
#

### *** _Reboot pi_ ***
