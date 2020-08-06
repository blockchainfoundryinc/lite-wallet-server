# Syscoin wallet dev kit

This bundle contains:

- Syscoind: Syscoin core.
- Blockbook: Block explorer
- Syscoin-websocket: receive realtime notifications around an address.

### Dependencies and installation

You need `docker-compose` in order to run this package. `docker-compose up -d` should spin up an instance of every service and will keep running on the background. Restart policies set in `docker-compose.yml` makes docker start the containers every time the docker service is started.

Blockbook runs on port `9130`
Websocket runs on port `9999`
Syscoin core is not accessible from outside the container.

### Troubleshooting

Ocassionally, Syscoin service will replace `syscoin.conf` inside of `/syscoin` folder on the first run (Syscoin writes a bunch of stuff to that folder). In case that happens, just stop the containers (`docker-compose down`) restore the original `syscoin.conf` file inside this repo and rerun `docker-compose up`.