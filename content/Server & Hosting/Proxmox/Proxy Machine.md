---
publish: "true"
---
# Install CloudPanel
CloudPanel has a very easy [install process](https://www.cloudpanel.io/docs/v2/getting-started/other/). There is basically only "one command" to paste.

Choose an OS, in my case it's Ubuntu 22.04 LTS, and select the desired Database Engine.

Run the Command and login to the Admin Panel via ``http://publicip:8443``

Fill in your name and password, _enable Darkmode :wink:_ and navigate to the Admin Area on the upper right corner.

Under Settings > General > Domain Name, enter your desired CloudPanel domain and hit save.

Read more about CloudPanel [here](https://www.cloudpanel.io/docs).
# Install Dependencies

``` sh
curl -sSL https://get.docker.com/ | CHANNEL=stable bash
```

# Install Portainer
Create a volume that Portainer will use to store its database:
```sh
docker volume create portainer_data
```

Create and run the Portainer Container:
```sh
docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
```

Optionally you can change the ports used by Portainer for the admin Panel. See Docker-Env

Portainer has been installed and can be accessed via https://localhost:9443
_Note: Portainer will create a self signed Certificate.

Read more about Portainer [here](https://docs.portainer.io/start/install-ce/server/docker/linux).