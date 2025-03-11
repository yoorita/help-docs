# Installation

- using `apt` with an alternate PPA software repository to install specific versions of the nodejs package
- installing `nvm`, the Node Version Manager, and using it to install and manage multiple versions of Node.js 
  **(Recommended)**
- using `apt` to install the nodejs package from Ubuntu’s default software repository
  **(Not recommended because it installs older versions)**

# Method 1

The NodeSource repository provides the latest Node.js packages for Ubuntu.

```bash
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash - &&\
sudo apt-get install -y nodejs
```

# Method 2

NVM(Node Version Manager) allows one to install a specific version of Node.js.

```bash
wget https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh &&\
bash install.sh &&\
source ~/.bashrc
```

Verify the NVM installation.

```bash
nvm -v
```

Once installed, use NVM to install the desired Node.js version. Populate a list of available versions with the command:

```bash
nvm list-remote
```

Now go ahead and install the latest available version of Node.js

```bash
nvm install v[VERSION NO.]
```

Once complete, verify the version.

```bash
node -v
```
