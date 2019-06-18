useful commands:
```shell
docker build -t allofthecoins:zebra ./
docker run --name zebra -v zcash_copy:/root/.zcash -itd allofthecoins:zebra import /root/.zcash
docker run --name zebra -itd allofthecoins:zebra
docker logs -f zebra
```

