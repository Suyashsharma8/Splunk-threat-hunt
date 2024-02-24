This is used to get statistics of firewall rule based on selected host
```spl
index=cisco-fw_raw sourcetype="asa:traffic" host="<enter ip here>" 
|stats count by rule
```
