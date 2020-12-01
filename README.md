# Google Maps API Cache

Google Maps API caching server to reduce the amount of queries which are hammered against the google maps api. The proxy just caches duplicate requests. The project is fully complient to the google maps api guidelines and it adds a privacy layer for client side api calls.

## Install with docker-compose

1. copy the .env.local file to .env and change the params to your desire
2. run `docker-compose up -d` to start the server on port 8080.
3. run the queries you would run against the google maps api on http://localhost:8080/

## Options in the .env file

- GOOGLE_MAPS_API_KEY: your google maps api key. If you set this in the env, you dont need to pass it on your requests
- CACHE_LIFETIME: the lifetime of the cache entries. 720h is 30 days, which is the maximum allowed by google. You can put in any value that parse duration can parse (https://golang.org/pkg/time/#ParseDuration)
- CACHE_CAPACITY: the max number of entries in the cache

## You need a feature?

If you need a feature, add it! The state of the project fits my needs, so i dont have any desire adding features myself. If you find any bugs, put them in the issue tracker and i will fix them if i find time. 

Whatever, you can fork this repo at any given time and add features by yourself or make a pull request.

## Caution!

Google allows you to cache results for a period of 30 days, so using this proxy should be legal by there own terms (https://developers.google.com/maps/premium/optimize-web-services). Whatever, you are responsible for what you are doing!

You can save money using this proxy, but if and how much depends on what your doing, so dont nail me down on that.

## Problems

### The server says "open .env: no such file or directory

This means you didnt read the installation instructions or the docker container has to be rebuild to include your .env file. To rebuild the container run `docker-compose build --no-cache`. After that you should be able to start the server.

### I want to change the port

You can change the port for the server by changing the port value inside the docker-compose file.

### What is docker-compose and what do i need to install to get this running?

Please read https://docs.docker.com/compose/ for more informations on this.

## I want to give you money, because you saved me lot of money on google api billing!

Feel free to buy me a coffee or and say something nice at https://www.buymeacoffee.com/maxman, so i can build more helpfull stuff in the future!