NRK-TV-downloader
=================

This is a set of scripts help you to download subtitles and videos from tv.nrk.no

scripts orginally written by Ingvar Hagelund (http://users.linpro.no/ingvar/nrk/)

you can find the original scripts in here (http://users.linpro.no/ingvar/nrk/)

And I made some modification so it can support http proxy

Usage: ./nrk-download "URL-to-tv.nrk" [-p [proxy-address:port] ]

syntax description: 

      -p : means use http proxy, it's optional.
      
      proxy-address:port : manually assign the proxy address instead of using the default '127.0.0.1:8087', 
      
			      you can leave this blank that'll means use the default 127.0.0.1:8087.

Example: ./nrk-download http://tv.nrk.no/serie/store-leker/koid24008909/sesong-1/episode-5

or 	./nrk-download http://tv.nrk.no/serie/store-leker/koid24008909/sesong-1/episode-5 -p 127.0.0.1:2089

or	./nrk-download http://tv.nrk.no/serie/store-leker/koid24008909/sesong-1/episode-5 -p



