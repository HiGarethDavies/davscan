# DAVScan 

DAVScan is a quick and lightweight webdav scanner designed to discover hidden files and folders on DAV enabled webservers.
The scanner works by taking advantage of overly privileged/misconfigured WebDAV servers or servers vulnerable to various 
disclosure or authentication bypass vulnerabilities.

The scanner attempts to fingerprint the target server and then spider the server based on the results of a root PROPFIND request.

## What works:

**Server header fingerprinting** - If the webserver returns a server header, davscan can search for public exploits based on the response.

**Basic DAV scanning with PROPFIND** - Quick scan to find anything that might be visible from DAV.

**Unicode Auth Bypass** - Works using GET haven't added PROPFIND yet.  Not fully tested so double check the work.

**Exclusion of DoS exploit results** - You can exclude denial of service exploits from the searchsploit results.

**Exclusion of MSF modules from exploit results** - Custom searchsploit is included in the repo for this.  Either overwrite existing searchsploit or backup and replace. This feature may or may not end up in the real searchsploit script.

## What doesn't work:

**Authentication** - I've started this, but it's not finished yet.  I'll get to it when I actually need it.

**X header fingerprinting** - It's in there, but isn't working right.  Need to debug this.



**Probably a lot more that I haven't tested yet.**

## What I want to do:

**Build a sqlite database instead of flat file** - Currently output goes to file with a couple blurbs to the screen just to show it's working.  

**Become a fighter pilot!** - I saw Top Gun once and now I'm really stoked about going into the Air Force and living the dream.  "I feel the need for speed!"

## Usage:

`usage: davscan.py [-h] -H HOST [-p PORT] [-a AUTH] [-u USER] [-P PASSWORD]`
`                  [-o OUTFILE] [-d ] [-m ]`

`  -H HOST, --host HOST  hostname or IP address of web server; -h foo.com`  

`optional arguments:`

`  -h, --help            show this help message and exit`  
`  -p PORT, --port PORT  port to connect to the host on (defaults to port 80); -p 80`  
`  -a AUTH, --auth AUTH  Basic authentication required; -a basic`  
`  -u USER, --user USER  user; -u derp`  
`  -P PASSWORD, --password PASSWORD  password for user; -P 'hunter2'`  
`  -o OUTFILE, --out OUTFILE  output file. defaults to /tmp/davout; -o /foo/bar`  
`  -d, --no-dos  exclude DoS results from searchploit.`  
`  -m, --no-msf  exclude MSF modules from results.`  


