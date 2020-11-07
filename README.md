# 1m-block    

after typing    
    
sudo iptables -F    
sudo iptables -A OUTPUT -j NFQUEUE --queue-num 0    
sudo iptables -A INPUT -j NFQUEUE --queue-num 0    
    
sudo make    
sudo ./1m-block blockingsites.txt    
    
# example of execution    
    
opening library handle    
unbinding existing nf_queue handler for AF_INET (if any)    
binding nfnetlink_queue as nf_queue handler for AF_INET    
binding this socket to queue '0'    
setting copy_packet mode    
    
....
        
Analysing HTTP header!    
This packet's method is : GET    
Host:jd.com    
This packet is dropped!    
Analysing HTTP header!    
This packet's method is : GET    
Host:test.gilgil.net    
This packet is accepted!    
Analysing HTTP header!    
This packet's method is : GET    
Host:jd.com    
This packet is dropped!    
Analysing HTTP header!    
This packet's method is : GET    
Host:jd.com    
This packet is dropped!    
Analysing HTTP header!    
This packet's method is : GET    
Host:jd.com    
This packet is dropped!    
Analysing HTTP header!    
This packet's method is : GET    
Host:jd.com    
This packet is dropped!    
Analysing HTTP header!    
This packet's method is : GET    
Host:google.com    
This packet is dropped!    
Analysing HTTP header!    
This packet's method is : GET    
Host:jd.com    
This packet is dropped!    
Analysing HTTP header!    
This packet's method is : GET    
Host:jd.com    
This packet is dropped!    
Analysing HTTP header!    
This packet's method is : GET    
Host:portal.korea.ac.kr    
This packet is accepted!    
Analysing HTTP header!    
This packet doesn't uses get or post method!    
Analysing HTTP header!    
This packet's method is : POST    
Host:portal.korea.ac.kr    
This packet is accepted!     
    
....
        
^C
