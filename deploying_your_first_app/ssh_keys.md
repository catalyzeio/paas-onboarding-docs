# SSH Keys

> No one can drive us crazy unless we give them the keys.

> — Douglas Horton

Once your environment is provisioned, you will be given a git url to push your code to. A public SSH key is required for you to push code to the Catalyze PaaS. Although the provisioning step happens after you enter your SSH key, we need the information in advance so we can authorize you (and only you to push code to the PaaS).

```
Note that you will need to add a unique ssh key per user that you wish to authorize to push code to the Catalyze PaaS.
```

If you don’t already use SSH, you’ll need to create a public/private key pair to deploy code to Catalyze. This keypair is used for the strong cryptography and that uniquely identifies you as a developer when pushing code changes.

Just like Heroku, we support RSA and DSA key formats. ECDSA keys are currently not supported.

##Getting your public SSH key
Note that the following instructions apply to Mac or Linux operating systems. Instructions for Windows will be added shortly. A full of instructions is available [here](https://help.github.com/articles/generating-ssh-keys) but is presented here in summary for quick reference. All credit to [Github](http://www.github.com).

### Step 1: check if you already have an SSH key

Navigate to your ssh directory (usually at ~/.ssh) and see if you already have a file called `id_rsa.pub` or `id_dsa.pub`

If you don't see it, then move to Step 2 otherwise go to Step 3

###Step 2: generate a new SSH key
Copy and paste the commands below but substituting **your email address** for "your_email@example.com"

```
ssh-keygen -t rsa -C "your_email@example.com"
```

You will see some output in the terminal which looks like this.Press enter to keep the default name.

```
# Creates a new ssh key, using the provided email as a label
# Generating public/private rsa key pair.
# Enter file in which to save the key (/Users/you/.ssh/id_rsa): [Press enter]
```

Next, you'll have to come up with a strong passphrase. Make it something [strong and memorable](http://xkcd.com/936/).

```
Enter passphrase (empty for no passphrase): [Type a passphrase]
# Enter same passphrase again: [Type passphrase again]
```
This will generate a key which you will then need to add to the ssh agent like so.

```
eval "$(ssh-agent -s)"
# wait until it starts and gives you a process ID
ssh-add ~/.ssh/id_rsa
```

###Step 3: Copy the key
Type in the following code which will copy the key to your clipboard so that you can directy (Command+v) paste it into the appropriate field in the dashboard.

```
pbcopy < ~/.ssh/id_rsa.pub
```

###Step 4: Paste it into the dashboard

Paste the key that you just copied into the dashboard as shown below.
![Paste the SSH key here](../pics/ssh.key.jpg)

