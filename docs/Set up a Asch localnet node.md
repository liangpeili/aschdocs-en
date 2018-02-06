## Recommand Configuration

OS ： Ubuntu 16.06 x64

Node.js version： 8.x.x

## Install dependencies

### 1. Update software
```
apt update 
apt upgrade
```
### 2. Install dependencies
```
apt install curl sqlite3 ntp wget git libssl-dev openssl make gcc g++ autoconf automake python build-essential -y
apt install libtool libtool-bin -y
```
### 3. Install node.js
```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh | bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" 
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

nvm install 8
```

## Intall Asch
### 1. Clone the source code from github
```
git clone https://github.com/AschPlatform/asch && cd asch && chmod u+x aschd
```
### 2. Install dependencies
```
npm install
```
If installation fails, delete the folder `node_modules` and  try again.
### 3. Start aschd
```
./aschd start 
```
Use 'netstat -nltp' to check if the port 4096 is open.
### 4. Access frontend
Type http://your-ip:4096 in your browser，it should response blow infomation：
```
{
  success: false,
  error: "Error: Failed to lookup view "wallet.html" in views directory "/root/asch/public/dist""
}
```

## Build wallet frontend

### 1. Install dependencies
```
npm install -g bower
npm install -g gulp
npm install browserify -g
```
### 2. Build wallet frontend
The frontend source code is in the asch/public folder.
```
cd you-path-to-asch/public
npm install
npm run build
gulp build-test
```
### 3. Login from the frontend
Login from http://your-ip:4096， it should be the same wallet frontend as the mainnet.

## Accounts and delegates

The genesis account of localnet is "someone manual strong movie roof episode eight spatial brown soldier soup motor", which contains 100 millions XAS. All the 101 delegates are listed in 'config.json', whose balance will increase as they are forging the block.