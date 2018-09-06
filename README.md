# ProximaX Platform NIS1 Docker Compose

Launches ProximaX Platform and IPFS node using a bridged network

## Configuration
In the `docker-compose.yml` config file, specify the Docker image tag you wish to run.
```
image: proximax/proximax-platform-nis1:0.1.0-beta
```

The different Docker image versions can be found in [ProximaX Platform NIS1 Docker Hub](https://hub.docker.com/r/proximax/proximax-platform-nis1/) 

## How to run locally
Published Ports:

#### IPFS 
- 8080:8080
- 4001:4001
- 5001:5001

#### ProximaX Platform NIS1
- 8881:8881

Install Docker engine to your OS and run these commands

#### Launch ProximaX and IPFS containers
```bash
docker-compose up -d
```

#### Display the running processes 
```bash
docker-compose top
```

#### Test if the server is running  
```bash
curl http://localhost:8881/node/info 
``` 

An example response would be:

```
{
  "contextUri": "",
  "nemAddress": "TBNQIHIUC22BTRDVAS7D575SJLAJGKTNN57R6RWN",
  "nemNetworkProtocol": "http",
  "network": "testnet",
  "networkAddress": "23.228.67.85",
  "networkPort": "7890",
  "namespace": "prx",
  "mosaic": "xpx",
  "syncGateways": [
    "https://ipfs.io/ipfs",
    "https://gateway.ipfs.io/ipfs"
  ],
  "peerId": "{PeerID=QmXCjB97e2mDt7d7frCfSjWAigjsYkZhRyxvJxUusBtTsn}"
}
```
Where the `peerId` is the IPFS instance id.

#### Stop the running containers
```bash
docker-compose down
``` 
