This is used to get statistics of firewall rule based on selected host
```spl
index=cisco-fw_raw sourcetype="asa:traffic" host="<enter ip here>" 
|stats count by rule
```

This can be used for suspicious URL's seen in the firewalls
```spl
index=cisco-fw_raw sourcetype="asa:threat" url IN
("*URL 1*", "*URL2*", "*URL3",.....)
| stats count by url
```
