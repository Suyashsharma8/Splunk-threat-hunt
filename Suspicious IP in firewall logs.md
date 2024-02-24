This is used to search list of suspicious IP's in the firewall logs. his command is looking at incoming or outgoing traffic, it depends on how the dest field is defined in your data. If dest represents the destination of the traffic from the perspective of the host that’s generating the data, then this command would be looking at outgoing traffic. That’s because it’s counting events where the host sent traffic to the specified IP addresses. However, if dest represents the source of the traffic from the perspective of the host, then this command would be looking at incoming traffic. You would need to check the definition of the dest field in your data to be sure.
```spl
index=ciso-fw_raw sourcetype="asa:traffic" dest IN ("154.221.31.191","45.12.253.56","45.12.253.72","45.12.253.98","45.130.151.133","47.90.167.104") 
| stats count by dest
```
