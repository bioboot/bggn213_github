Test AWS connection

##  Generate an SSH key pair

The easiest way to set up GitHub access on your AWS instance:

### Generate a new SSH key
ssh-keygen -t ed25519 -C "your_email@example.com"

### Start the SSH agent
eval "$(ssh-agent -s)"

### Add your private key to the SSH agent
ssh-add ~/.ssh/id_ed25519

### Display your public key to copy
cat ~/.ssh/id_ed25519.pub

## 2. Add the SSH key to GitHub
Copy the output from the cat command
Go to GitHub → Settings → SSH and GPG keys → New SSH key
Paste your key and save

3. Test the connection

4. # Set your username and email
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"

clone, pull, do work commit and push...
