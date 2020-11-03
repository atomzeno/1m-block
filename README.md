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
hw_protocol=0x0800 hook=1 id=1 hw_src_addr=b8:55:10:e0:10:50 indev=2 payload_len=83    
hw_protocol=0x0800 hook=3 id=2 outdev=2 payload_len=52     
hw_protocol=0x0800 hook=1 id=3 hw_src_addr=b8:55:10:e0:10:50 indev=2 payload_len=76     
    
....
    
hw_protocol=0x0800 hook=1 id=783 hw_src_addr=b8:55:10:e0:10:50 indev=2 payload_len=53    
hw_protocol=0x0800 hook=3 id=784 outdev=2 payload_len=518    
Analysing HTTP header!    
Host:livescreensaver.com    
 This is dropped!    
    
....
    
hw_protocol=0x0800 hook=3 id=938 outdev=2 payload_len=518    
Analysing HTTP header!    
Host:livescreensaver.com    
 This is dropped!    
    
....
    
hw_protocol=0x0800 hook=3 id=942 outdev=2 payload_len=494    
Analysing HTTP header!    
Host:a0baa7ec381fb3b04a7eaba248d417dbf.profile.dxb50-c1.cloudfront.net    
 This is accepted!    
    
....
    
hw_protocol=0x0800 hook=3 id=1371 outdev=2 payload_len=503    
Analysing HTTP header!    
Host:greatfulpots.com    
 This is dropped!    
    
....
    
^C
