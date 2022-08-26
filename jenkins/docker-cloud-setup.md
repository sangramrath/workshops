
## Pre-requisites
1. Install Docker
```
sudo chmod a+rwx /var/run/docker.sock
sudo chmod a+rwx /var/run/docker.pid
```

## Install plugins
1. Visit [publicip]:8080/pluginManager/
2. Click Available
3. Search for Docker
4. Check both Docker & Docker Pipeline
5. Click Install without restart

## Add docker as cloud
1. Go back to Dashboard
2. Click Nodes and Clouds
3. Click Configure Clouds
4. Click Add a new cloud and select Docker from the list
5. Click Docker Cloud details
6. Enter **unix:///var/run/docker.sock** for Docker Host URI
7. Click Test Connection
8. Check Enabled
9. Click Apply and then Save
