A command-line tool library that supports [[HTTP]], very used for scripts and automations

```shell-session
curl site.com

<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
...
```
## Verbs
### -k
For web applications that have not implemented a valid SSL certificate on the [[HTTPS]], it will skip the certificate check
### -I
only display the headers
### -A 'User-Agent'
 Sets the request as a specific Agent such as Mozilla/5.0
### -u user:passwd
to access pages that needs credentials ( the user and passwd can be placed directly on the link without -u )
### -X Request
specify which request such as GET or POST
### -b 'SOMEID=ID'
Set the cookies headers

