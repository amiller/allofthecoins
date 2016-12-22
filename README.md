# Allofthecoins
Create docker images that run nodes for different cryptocurrencies.

Installing
----------
To run the nodes, you need to first install `docker`. Installation instructions are on [their website](https://docs.docker.com/engine/installation/).

Running
-------
For any of the currencies in the repo, run the following command in the appropriate directory: 
```shell
docker build -t <image-name> .
```

For example, to create an image for Bitcoin the command will look like this:
```shell
docker build -t allofthecoins:bitcoin .
```

After the image is built run with:
```shell
docker run -d -p 8333 -p 8332 --name bitcoin allofthecoins:bitcoin
```
You have to look up the ports that each client needs.

Bitcoin uses `8333`, `8332`. Bitcoin testnet uses `18333`, `18332`.

