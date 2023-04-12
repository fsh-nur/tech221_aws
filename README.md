# CREATING AND ADDING YOUR SSH KEY TO GITHUB

## How to push changes using github using SSH

### Well firstly, you need to create an SSH key pair, which has many types however, RSA is the most common which is made up of public key and private key. These are created in the local machine, however the public key is used on Github in order to produce a secure connection for **data transfer** between your machine and github!
![public](https://user-images.githubusercontent.com/129324316/231217681-160aa26a-5cc9-459f-90d3-9c8f3c427b23.png)


## Generating an SSH Key into your local machine 

- Open GitBash (type in `cd` in order to be directed to "home" if you are not directed there already)
- Create a folder where you will store all of your SSH Keys (`mkdir .ssh`)
- Move to the newly created directory (`cd .ssh`)
- Creating an SSH Key (    `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"` ) This will create a new SSH key with your email attached. It will ask you to enter a file in which to save the key and name the file respectively. It will then ask you for a passphrase, just press enter each time.
- Woohoo! Public and Private Key saved: Randomart should have been generated and fingerprint. (Inset padlock and key images)

## Adding the SSH Key to the SSH Agent

- In git bash type:
`$ eval ssh-agent -s `
- Then:
`$ ssh-add <your-key-name`
### (^^ Here you are adding your private key to your local machine)

## Adding the SSH key to your GitHub account

- In git bash type:
`$ cat <your public key> `
### Copy your SSH public key that is generated to add into your github

## Now we add our SSH Key to Github

1. Go to Settings on Github:
![settings_githb](https://user-images.githubusercontent.com/129324316/231215183-b8bdab38-26a7-4c07-8b7d-f9e1e751016c.png)

2. Locate the tab on the left-hand side which says "SSH and GPG Keys"
![ssh_github](https://user-images.githubusercontent.com/129324316/231215230-4f7a4cfe-79af-4b14-b0aa-9479e9a56673.png)

3. Click on "New SSH Key"
![newssh_github](https://user-images.githubusercontent.com/129324316/231215300-e79f6151-490f-4c9f-8c9a-c2ab2deb81d2.png)

4. Name the key  (usually identical to what you named it on your local machine) and enter the SSH number you copied earlier.
![newkey_github](https://user-images.githubusercontent.com/129324316/231215333-56c25716-79be-48a8-b201-8dcefa4543ad.png)



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
![pushing_github](https://user-images.githubusercontent.com/129324316/231215382-431dea83-a55f-46d2-910e-240aeb16f363.png)

### Follow the instructions on github when creating a new repository and make sure you select SSH at the top!

