# Installing Azure CLI

## Installation steps

```sh
AZ_REPO=$(lsb_release -cs)
if [ -f /etc/upstream-release/lsb-release ]
then
  . /etc/upstream-release/lsb-release
  AZ_REPO=$DISTRIB_CODENAME
fi

echo "deb [arch=amd64] https://packages.microsoft.com/repos/azure-cli/ $AZ_REPO main" | \
     sudo tee /etc/apt/sources.list.d/azure-cli.list
sudo apt-key adv --keyserver packages.microsoft.com --recv-keys 52E16F86FEE04B979B07E28DB02C46DF417A0893
sudo apt-get install apt-transport-https
sudo apt-get update && sudo apt-get install azure-cli
```

## Configure Azure CLI

```sh
az login
```

## Other useful notes
