# crowmail

Dockerized mailman

I installed docker on my droplet via [this method](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04)
OK, well I didn't need to do that because I just wanted docker-compose which I set up using [this](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04) but commands repeated here to update versioning...

```sh
# https://github.com/docker/compose/releases/download/v2.39.4/docker-compose-linux-x86_64
sudo curl -L "https://github.com/docker/compose/releases/download/v2.39.4/docker-compose-$(uname -s | tr '[:upper:]' '[:lower:]')-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

## Create List

```sh
docker exec -it $(docker ps -qf "name=mailman-core") \
    mailman create list mylist@example.com
```
