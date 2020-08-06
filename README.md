# IP-Static-route
For an article purposes but is free for open source.
This topology has contains:-
2 routers (R1 and R2)
2 Switches
6 hosts

It is a a two network topology, with each topology having 3 hosts and one switc.
the configurations are working fine, 
Although there is a Gigabitethernet link that is faulty and needs to fix. So if you notice that just know it was there for  a reason.

This topo it to test IP route static and everything different layer devices work.

R1]display ip routing-table
Route Flags: R - relay, D - download to fib
------------------------------------------------------------------------------
Routing Tables: Public
         Destinations : 7        Routes : 7        

Destination/Mask    Proto   Pre  Cost      Flags NextHop         Interface

       10.0.1.0/24  Direct  0    0           D   10.0.1.4        GigabitEthernet
0/0/0
       10.0.1.4/32  Direct  0    0           D   127.0.0.1       GigabitEthernet
0/0/0
       10.0.2.0/24  Direct  0    0           D   10.0.2.4        GigabitEthernet
0/0/1
       10.0.2.4/32  Direct  0    0           D   127.0.0.1       GigabitEthernet
0/0/1
      127.0.0.0/8   Direct  0    0           D   127.0.0.1       InLoopBack0
      127.0.0.1/32  Direct  0    0           D   127.0.0.1       InLoopBack0
    192.168.1.0/24  Static  60   0          RD   10.0.2.3        GigabitEthernet
0/0/1
 This is for R1 
 
 [R2]display ip routing-table
Route Flags: R - relay, D - download to fib
------------------------------------------------------------------------------
Routing Tables: Public
         Destinations : 7        Routes : 7        

Destination/Mask    Proto   Pre  Cost      Flags NextHop         Interface

       10.0.1.0/24  Static  60   0          RD   10.0.2.4        GigabitEthernet
0/0/0
       10.0.2.0/24  Direct  0    0           D   10.0.2.3        GigabitEthernet
0/0/0
       10.0.2.3/32  Direct  0    0           D   127.0.0.1       GigabitEthernet
0/0/0
      127.0.0.0/8   Direct  0    0           D   127.0.0.1       InLoopBack0
      127.0.0.1/32  Direct  0    0           D   127.0.0.1       InLoopBack0
    192.168.1.0/24  Direct  0    0           D   192.168.1.1     GigabitEthernet
0/0/3
    192.168.1.1/32  Direct  0    0           D   127.0.0.1       GigabitEthernet
0/0/3
FOR R2 .

Take time and go through it.
