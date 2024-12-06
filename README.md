# Host a Free Onion Site Using Linux Terminal

Follow these steps to host an Onion site for free from the Linux terminal:

### Step 1: Install Tor
Run the following command to install Tor:
```bash
sudo apt-get install tor
```
### Step 2: Start the Tor Service
Start the Tor service with the default settings:
```bash
sudo systemctl start tor@default.service
```
### Step 3: Stop the Tor Service (if necessary)
If you need to stop the Tor service at any point, use:
```bash
sudo systemctl stop tor@default.service
```
### Step 4: Change Permissions
Change permissions of the Tor library directory to allow access:
```bash
sudo chmod -R 777 /var/lib/tor
```
### Step 5: Configure Tor
Open the Tor configuration file to modify the necessary settings:
```bash
sudo nano /etc/tor/torrc
```
In the file, remove the # from the following lines to uncomment them:
  * HiddenServiceDir: /var/lib/tor/hidden_service/
  * HiddenServicePort 80: 127.0.0.1:80
  * HiddenServicePort 443: 127.0.0.1:443
After making these changes, exit the file by pressing Ctrl + x, then confirm saving with y, and press Enter.
### Step 6: View Your Onion Site URL
To find the URL of your Onion site, run:
```bash
sudo nano /var/lib/tor/hidden_service/hostname
```
### Step 7: Adjust Permissions Again
Set stricter permissions for the Tor directory:
```bash
sudo chmod -R 700 /var/lib/tor
```
### Step 8: Start the Tor Service Again
Finally, start the Tor service again to apply your settings:
```bash
sudo systemctl start tor@default.service
```
### Note
Tor Browser is recommended for use on Linux platforms, as Windows may have bugs that could compromise your information.
