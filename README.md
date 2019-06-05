## [fastlane match](https://docs.fastlane.tools/actions/match/)

This repository contains all your certificates and provisioning profiles needed to build and sign your applications. They are encrypted using OpenSSL via a passphrase.

**Important:** Make sure this repository is set to private and only your team members have access to this repo.

Do not modify this file, as it gets overwritten every time you run _match_.

### Installation

Make sure you have the latest version of the Xcode command line tools installed:

```
xcode-select --install
```

Install _fastlane_ using

```
[sudo] gem install fastlane -NV
```

or alternatively using `brew cask install fastlane`

### Usage

Navigate to your project folder and run

```
fastlane match development --readonly
```
```
fastlane match adhoc --readonly
```
```
fastlane match appstore --readonly
```

For more information open [fastlane match git repo](https://docs.fastlane.tools/actions/match/)

### Content

#### certs

This directory contains all your certificates with their private keys

#### profiles

This directory contains all provisioning profiles

------------------------------------

For more information open [fastlane match git repo](https://docs.fastlane.tools/actions/match/)

### Trouble shooting

1. Clone certificates repo taking like...forever

Try to add `--verbose` when run `match` command to see exact the proplem

2. Error when clone certificates repo

First, follow this [Link](https://github.com/settings/keys) to check if you did add your ssh key to your github account.
Second, check if you add github to your `known_host`. If not, you can use following script to add it to list known host
```
ssh-keyscan github.com >> ~/.ssh/known_hosts
```

3. Can not build project on a device

Please check if you select the right profile for your target.

4. I did select right profile but i can't build it either

Check if profile contain that device uuid

5. I built it successfully, but app crash right after app launch

Clean project and build it again. Maybe your cached framework still signed with old certificate (which had been revoke)