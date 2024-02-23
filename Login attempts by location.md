This SPL command is to get user attemps by location and separate the results based on date and then dedup IP.
```spl
index=cloud_azure_raw sourcetype="azure:aad:signin" <insert user's email address here> |eval time=strftime(_time, "%Y-%m-%d") |eval timeComp=strftime(_time, "%Y-%m-%d %H:%M")|eval location= 'location.countryOrRegion'. " - " .'location.city'|dedup consecutive=true location time ipAddress | table timeComp,location,action,appDisplayName,ipAddress,deviceDetail.browser, deviceDetail.operatingSystem,deviceDetail.displayName
```
