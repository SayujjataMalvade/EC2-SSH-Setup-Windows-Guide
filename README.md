# ec2-to-ec2-ssh-guide
This repository provides step-by-step instructions on how to establish an SSH connection between two AWS EC2 instances. It covers generating and managing SSH keys, configuring authorized keys, and securely connecting from one instance to another.

# Prerequisites

One running EC2 instances (e.g., Server)

Access to both instances (e.g., via MobaXterm for Server)

Basic knowledge of SSH and Linux commands

# Steps

# 1.Launch EC2 Instances

Start Server in your AWS account.

Connect to Server using MobaXterm or gitbash or CMD


# 2.Navigate to .ssh Directory on Server

**'cd .ssh/'** 

You will see the existing authorized_keys file.

# 3. Generate SSH Keys on Server1

**'ssh-keygen'**

This will create a new pair of public and private keys.

# 4. Add Public Key to Authorized Keys

Copy the generated public key to the authorized_keys file so that connections can be established securely.

# 5. Download Keys to Local Machine

From your local PowerShell terminal, navigate to the downloads directory:

**'[cd ~/Downloads]'**

'**ls -la | grep key**'

# 6. Create a Directory for Server Keys

**'mkdir Linux-Server'**

'**cd Linux-Server'**

# 7. Securely Copy the Key from Server

Use scp to copy the key from Server to your local machine:

**'scp -i ./<KeyName> ubuntu@<Server-Public-IP>:/home/ubuntu/.ssh/id_rsa .'**

Replace <KeyName> with your actual private key file and <Server-Public-IP> with your instance’s public IP.

# Outcome

You will now have the Server2 SSH key securely stored on your local machine. This setup allows you to establish SSH connections between EC2 instances and manage secure file transfers.


