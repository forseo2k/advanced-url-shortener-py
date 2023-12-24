# advurl_shorten

Python Library to help you short urls with advanced options. Multiple domains, visit statistics etc.

## Features
- Multiple domains
- Link TTL (Time-To-Live) in seconds
- Redirect to second URL after expire main URL (TTL)
- Randomized and weighted randomnized redirect to different URLs
- Password protected visit statistics of shortned URL
- Password protected shortned url parameters (TTL, second URL etc.)

## Installation

In order install this package, simply run:

```bash
pip install advurl_shorten
```

## Usage

To use shorten_url, you first need to import the package:

```python
import advurl_shortener
```


### Shorten URL:
```python
advurl_shorten.short("https://google.com/")    # Returns the shortened URLs
advurl_shorten.short("https://google.com/", pass="1234x")    # Returns the shortened URLs, set password to get statistics and parameters of shortened url

advurl_shorten.short("https://google.com/", ttl=86400)    # Returns the shortened URLs., after 24 hours (86400 seconds) will return "The Link You Followed Has Expired"
advurl_shorten.short("https://google.com/",second_url="https://bing.com/")    # Returns shortened URLs. The shortened link is randomly redirected to one of the provided URLs.
advurl_shorten.short("https://google.com/",second_url="https://bing.com/", "weights"=[0.3, 0.4])    # Returns shortened URLs. The shortened link is randomly (weighted by weight parameter) redirected to one of the provided URLs.
advurl_shorten.short("https://google.com/", ttl=86400, second_url="https://bing.com/")    # Returns the shortened URLs., after 24 hours (86400 seconds)  shortned link will redirect to second_url


```
### Getting shortned URL parameters and visit statistics:
```python
advurl_shorten.stat("https://liil.bid/kdRz",pass="1234x")    # Returns the parameters and visit statistics of the shortened URL
```

### TODO:
- More than 2 URLs
- Weighted randomize

