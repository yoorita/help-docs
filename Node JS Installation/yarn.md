# Installation

To install Yarn, you can follow these steps depending on your operating system.

## Installing Yarn via npm (Global Installation)

If you already have npm installed, the easiest way to install Yarn globally is by running the following command in your terminal:

```bash
npm install -g yarn
```

After installation, you can verify that Yarn is installed by checking its version:

```bash
yarn --version
```

## Installing Yarn via Homebrew (macOS or Linux)

If you're on macOS or Linux and have Homebrew installed, you can install Yarn using the following command:

```bash
brew install yarn
```

If you don't want to install Node.js via Homebrew (since Homebrew installs Node.js as a dependency by default), you can use the --without-node flag:

```bash
brew install yarn --without-node
```

## Installing Yarn on Windows
For Windows, you can install Yarn through the Chocolatey package manager, or by downloading the installer directly from the Yarn website.

Using Chocolatey (if installed):

```bash
choco install yarn
```

Manual Installation:

Go to the Yarn website.
Download and run the Windows installer.
Once installed, you can check the version by running:

```bash
yarn --version
```

## Installing Yarn via the Official Yarn Installation Script (Linux and macOS)
You can also use Yarn's official installation script if you're on Linux or macOS. Run the following command in your terminal:

```bash
curl -sL https://yarnpkg.com/install.sh | bash
```

This will install Yarn globally, and it will set up the proper environment variables.
