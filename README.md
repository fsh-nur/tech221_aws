# *CREATING AND ADDING YOUR SSH KEY TO GITHUB* 

## How to push changes using github using SSH

### Well firstly, you need to create an SSH key pair, which has many types however, RSA is the most common which is made up of public key and private key. These are created in the local machine, however the public key is used on Github in order to produce a secure connection for **data transfer** between your machine and github!

## Generating an SSH Key into your local machine 

- Open GitBash (type in `cd` in order to be directed to "home" if you are not directed there already)
- Create a folder where you will store all of your SSH Keys (`mkdir .ssh`)
- Move to the newly created directory (`cd .ssh`)
- Creating an SSH Key (    `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"` ) This will create a new SSH key with your email attached. It will ask you to enter a file in which to save the key and name the file respectively. It will then ask you for a passphrase, just press enter each time.
- Woohoo! Public and Private Key saved: Randomart should have been generated and fingerprint. (Inset padlock and key images)

## Adding the SSH Key to the SSH Agent

- In git bash type:
`$ eval `ssh-agent -s` `
- Then:
`$ ssh-add fatima-github-key`
### (^^ Here you are adding your private key to your local machine)

## Adding the SSH key to your GitHub account

- In git bash type:
`$ cat <your public key> `
### Copy your SSH public key that is generated to add into your github

## Now we add our SSH Key to Github

1. Go to Settings on Github:
2. Locate the tab on the left-hand side which says "SSH and GPG Keys"
3.Click on "Add new key"
4.Name the key  (usually identical to what you named it on your local machine) and enter the SSH number you copied earlier.


## Now we test! 

- In git bash type:
`ssh -T git@github.com`
- What should appear:
```
> The authenticity of host 'github.com (IP ADDRESS)' can't be established.
> RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
> Are you sure you want to continue connecting (yes/no)?
```
- Verify that the fingerprint in the message you see matches GitHub's public key fingerprint. If it does, then type yes
- You should see:
```
> Hi username! You've successfully authenticated, but GitHub does not
> provide shell access.
```
### (^^Where username is your github username)

## Now we can initialise a repository and push changes from our local computer:

### Follow the instructions on github when creating a new repository and make sure you select SSH at the top!

