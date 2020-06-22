
## Fibonacci Caluculator:

This project was made as a part learning exercise for docker and kubernetes. It uses a redis cache and postgres DB for 
storing computed result for the current value entred via client and storing previously computed values respectively.

Desing:

Client - Calls the API to calculate fibonacci value for a number
Server - Pushes the number to redis and publishes `insert` event. Stores
Redis - Subscribes to `insert` event. Upon receiving the `insert` event, caluclates the fibonacci value and pushes the result 
to redis cache.

Upon refreshing the page, client issues a call to `/values/current` API, which fetches the result from redis cache and displays i
it.

# To run via docker : 

- Clone project
- Run `docker-compose up --build`

# To run via kubernetes:

- Clone project
- Run `kubectl apply -f k8s`
- Run `minikube ip` 
- Navigate to the `ip` from browser
