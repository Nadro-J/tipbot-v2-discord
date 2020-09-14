# BitGreen Tipbot


### TODO

- [X] Airdrop -> Tipbot merge - _(prefix=$)_
    - [ ] Airdrop commands tested
      - [ ] **user** commands tested
        - [ ] getinfo
        - [ ] join
        - [ ] cmd
      - [ ] **admin** commands tested
        - [ ] stats
        - [ ] end
        - [ ] airdrop
        - [ ] send
        - [ ] set_retweet
        - [ ] lasttx
  - [ ] Twitter commands tested
    - [ ] Twitter **user** commands tested
      - [ ] register_airdrop
      - [ ] verify
    - [ ] Twitter **admin** commands tested
      - [ ] dfa_stats
  - [ ] CronJob commands tested
    - [ ] CronJob **admin** commands tested
      - [ ] setup_batch_cron
      - [ ] enable_batch_airdrop
      - [ ] disable_batch_airdrop
  
- [x] Upgrade to Discord v1.0
  - [x] TipBot **user** commands tested
    - [x] tip
    - [x] deposit
      - [X] dlist
    - [x] withdraw
      - [x] wlist
    - [x] rain
    - [x] soak
    - [x] bet
    - [x] coingecko
    - [ ] invite
  - [x] TipBot **admin** commands tested
    - [x] wallet
    - [x] uptime
    - [ ] checksoak
    - [ ] allowsoak
    - [ ] log
    - [ ] pull
    
    

# Requirements
* discord.py installed
* Python 3.6+
* A MySQL database
* The BitGreen wallet w/ RPC enabled.

# Functions
* Display general wallet information
* Display individual user balances
* Store user balance information in database
* Generate new deposit addresses for users
* Automatically add users to database
* Allow users to withdraw coins from the wallet with respect to how many coins they have in the DB

# Instructions
These instructions were used to create a working bot in March 2018.
Once a VPS is obtained, follow these instructions.
## mySQL
These instructions will help you install and setup a mySQL database
### Install mySQL
```
sudo apt-get install mysql-server
```
When prompted, set up a password for root.
### Configure mySQL Security
```
mysql_secure_installation
```
Press "Y" and ENTER to accept all the questions, with the exception of the one that asks if you'd like to change the root password.
### Verify mySQL is Running
```
systemctl status mysql.service
```
You should see a status message that says "active (running)".
## Update Python
Python should be updated to version 3.6 because version 3.5 is not compatible with some libraries
```
sudo add-apt-repository ppa:jonathonf/python-3.6
sudo apt update
sudo apt-get install python3.6
sudo apt-get install python3.6-dev
sudo apt-get install python3.6-venv
```
## Install Python's pip
Python's pip is a useful tool used to install python libraries
```
wget https://bootstrap.pypa.io/get-pip.py
sudo python3.6 get-pip.py
```
## Link python3 to python3.6
```
sudo ln -s /usr/bin/python3.6 /usr/local/bin/python3
```
## Install Discord Library
Install the discord library used for the bot
```
python3 -m pip install -U discord.py
```
## Install PyMySQL Library
```
pip install PyMySQL
```
## Clone tipbot repository
```
git clone https://github.com/denuoweb/tipbot-v2
```

## Configuration

Configure config.json

## Run bot
```
cd tipbot-v2

python3 bot.py
```
