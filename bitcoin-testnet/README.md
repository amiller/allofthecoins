useful commands:
```shell
docker build -t allofthecoins:bitcoin-testnet ./
docker run --name bitcoin-testnet -itd allofthecoins:bitcoin-testnet
docker exec -it ./src/bitcoin-cli getinfo
docker exec -it tail -F /root/.bitcoin/debug.log
```


Runs the bitcoin node, listens of port 18333 on the host, listens for local RPC connections on 18332

```shell
docker run --name bitcoin -itd -p 18333:18333 -p 127.0.0.1:18332:18332 -v bitcoind-data:/root/.bitcoin allofthecoins:bitcoin
```
