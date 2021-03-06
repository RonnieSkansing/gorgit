![Gopher robbing git](https://raw.githubusercontent.com/RonnieSkansing/gorgit/master/assets/0.5x/gorgit-logo%400.5x.png)

git file lister and source scraper

Not for use on git servers but for deploys accidentally including the `.git` folder

Zero dependencies and does not require the target to have open directory listing.

# Usage

```
Usage of go-rip-git:
  -c int
    	concurrent scrape requests (default 100)
  -p string
    	the absolute path to the git folder (default "/.git/")
  -s	scrape source files
  -t int
    	request connection idle timeout in seconds (default 5)
  -u string
    	URL to scan
  -vv
    	very verbose output
  -w duration
    	time in seconds to wait between each request, example 5s
```

### Show files
`go-rip-git -u http://target.tld`

Results in something like
```
c1f3161c27b7fb86615a4916f595473a0a76c774 .env
29c16c3f37ea57569fbf9cc1ce183938a9710aed config/config.json
...
```

## Proxy
HTTP_PROXY="socks5://127.0.0.1:9150/" go-rip-git -u http://target.tld

HTTPS_PROXY="socks5://127.0.0.1:9150/" go-rip-git -u https://target.tld

## Scrape files
`go-rip-git -u http://target.tld -s`

Scraped source is found in `target.tld/...``

# Developer notes / TODO
Pull requests with features, fixes and refactoring are appreciated

Things that come into mind
- Extract contents of .PACK files
- Choose output directory
- Tests
- Accepting a list of targets (from arg and file)

Found a **bug**? Create an issue

# Credits
### Logo
Thanks to [Paula Sobczak](https://paulajs.dk) for logo based on [Renee French's gophers](http://reneefrench.blogspot.com/)
licensed licensedhttps://creativecommons.org/licenses/by/3.0/

# Disclaimer
*Author accepts no liability and no responsibility for the use of this tool. It is intended only for use with consent.*
