# Donwloading: cURL, Wget


Basic usage


### wget
```bash
# Download tuto.pdf file
$ wget www.website.org/tutorials/tuto.pdf
```


### cURL

```bash
# Get index page
$ curl http://www.website.org > website.html
$ curl -o website.html http://www.website.org/index.html

# Get multiples files. "-O" flag keep origin file name 
$ curl -O http://www.zem.fr/index.html -O http://www.zem.fr/about.html

# FTP download
$ curl -u ftpuser:ftppass -O ftp://ftp_server/fichier.html

# Follow redirect
$ curl -L http://www.website.org > website.html

# Limit rate
$ curl --limit-rate 10MB -O http://www.website.fr/my-v1.0.2-file.iso
```

