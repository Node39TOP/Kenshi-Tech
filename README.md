# Kenshi-Tech
Guide install 

**Install Nodejs**
```curl -fsSL https://deb.nodesource.com/setup_21.x | sudo -E bash - &&\sudo apt-get install -y nodejs```

**Install Package**
```npm i -g @kenshi.io/unchained```

**Install Postgres**
```sudo apt-get -y install postgresql```

**Login Postgres & Change Pass**
```sudo -u postgres psql```
```\password postgres```
Set Pass
```\quit```
Quit

**Create file**
```touch conf.yaml```

**Edit Conf.yaml**
```
log: info
name: <name>
lite: false
rpc:
  ethereum:
    - https://ethereum.publicnode.com
    - https://eth.llamarpc.com
    - wss://ethereum.publicnode.com
    - https://eth.rpc.blxrbdn.com
database:
  url: postgres://postgres:<pass>@localhost:5432/<database>
peers:
  max: 64
  parallel: 8
 jail:
  duration: 5
  strikes: 5
gossip:
  infect: 24
  die: 8
```

**Migrate**
```unchained postgres migrate conf.yaml```

**Run**
```unchained start conf.yaml --generate```

Note: Save the information inside the conf.yaml file

**Update**
```sudo npm i -g @kenshi.io/unchained@latest```
```unchained start conf.yaml```
