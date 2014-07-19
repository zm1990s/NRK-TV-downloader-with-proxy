NRK-TV-downloader
=================

This is a set of scripts help you to download subtitles and videos from tv.nrk.no

scripts orginally written by [Ingvar Hagelund](http://users.linpro.no/ingvar/nrk/)

The author has written a blog about the scripts in [here](http://ingvar.blog.redpill-linpro.com/2012/05/31/downloading-hd-content-from-tv-nrk-no/comment-page-1/)

you can find the original scripts in [here](http://users.linpro.no/ingvar/nrk/)

The scipts rely on AdobeHDS, you can find the newest version of it in [here](https://raw.githubusercontent.com/K-S-V/Scripts/master/AdobeHDS.php)

And I made some modification so it can support http proxy 

and written a scripts for NRK Radios

**Usage:** ` ./nrk-download "URL-to-tv.nrk" [-p [proxy-address:port] ]`

**syntax description:**

      -p : means use http proxy, it's optional.
      
      proxy-address:port : 
      
      manually assign the proxy address instead of using the default '127.0.0.1:8087', 
      
      you can leave this blank that'll means use the default 127.0.0.1:8087.

**Example:** `./nrk-download http://tv.nrk.no/serie/store-leker/koid24008909/sesong-1/episode-5`

or 	`./nrk-download http://tv.nrk.no/serie/store-leker/koid24008909/sesong-1/episode-5 -p 127.0.0.1:2089`

or	`./nrk-download http://tv.nrk.no/serie/store-leker/koid24008909/sesong-1/episode-5 -p`

**nrk-radio-download is for NRK radio only**

**the usage is the same as nrk-download**


**Dependences**

_Fedora:_
*  php
*  php-bcmath
*  perl-DateTime-Precise
*  perl-Text-Iconv
*  perl-HTML-TokeParser-Simple
*  perl-libwww-perl

_Debian/Ubuntu:_
*  php5-cli
*  php5-curl
*  libwww-perl
*  libtext-iconv-perl
*  libhtml-tokeparser-simple-perl
*  libdatetime-precise-perl (cpan module - no .deb available, try running 'dh-make-perl --build --cpan DateTime::Precise' )
