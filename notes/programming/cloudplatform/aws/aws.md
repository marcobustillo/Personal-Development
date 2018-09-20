# AWS

### Installing Node and NPM
```bash
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
```

then install pm2 for production deployment
```bash
sudo npm install -g pm2
```
try pm2. If you encountered this error `/usr/bin/env: ‘node’: No such file or directory`. Below is the fix
```bash
sudo ln -s /usr/bin/nodejs /usr/bin/node
```

Re-route 80 to 8080
```bash
sudo iptables -t nat -I PREROUTING -p tcp --dport 80 -j REDIRECT --to-port 8080
```
