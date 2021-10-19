# Wireshark

- `http.request` display only HTTP requests
- `tcp.port == 80` Port 80 TCP 
- `tcp.window_size_value >= 8000` TCP packets with window size of 8000 bytes and above
- `and` `&&` and `or` `||`, `not` `!`
- `ip.dst_host == 10.10.10.1 && tcp` TCP with 10.10.10.1 distination
- `ntp or udp.port == 20000`

### statistics windows
1. Protocol Hierarchy
- Percentages of the number of packets/bytes in a protocol
2. Conversations
-  
3. Endpoints
