# NEXUS-GUIDE
Complete Installation and Configuration Process 
System Update and Initial Setup
(run the code in green one by one)



1.  sudo apt update && sudo apt upgrade -y
2.  sudo apt install -y build-essential curl wget git
3.  Install Rust and Update Toolchain
3.  apt install rustup
4.  rustup update stable

5.  sudo add-apt-repository universe
6.  sudo apt update
7.  sudo apt install -y protobuf-compiler





Install Nexus CLI


8.  curl https://cli.nexus.xyz/ | sh

There will be an Error, don’t worry, keep going

9.  source $HOME/.cargo/env
10.  echo 'source $HOME/.cargo/env' >> ~/.rc
11.  Install Additional Dependencies


12.  sudo apt install -y pkg-config
13.  sudo apt install -y libssl-dev
14.  sudo apt install -y protobuf-compiler

15.  Re-Install Nexus CLI (if needed)

    
Run the CLI installation again after dependencies are in place:


16.  curl https://cli.nexus.xyz/ | sh

Disconnect and Reconnect to the Server
After reconnecting, start a screen session to keep the node running:


17.  screen -S nexus

Reset Existing Nexus Configurations (If Needed)
If there were previous configurations that caused issues, move them:


18.  mv ~/.nexus ~/.nexus_backup
19.  re-run the installation:

20.  curl https://cli.nexus.xyz/ | sh

    

During the setup, enter your desired Prover ID when prompted.
If the default Prover ID is used and you want to specify your own:
Check Nexus Configuration Files:


21.  Locate ~/.nexus/prover-id (or a similar file) and edit it with a text editor:


22.  nano ~/.nexus/prover-id
Replace the existing ID with your custom Prover ID, save the file, and then restart the node.
Use Command-Line Arguments:
If the Nexus CLI supports specifying the Prover ID via a parameter (check nexus network --help or official documentation), try something like:


nexus network setup --prover-id "my-custom-id"
or


nexus network configure --prover-id "my-custom-id"


Re-initialize the Node:
If direct editing or CLI arguments do not work, consider backing up and removing ~/.nexus, then re-running the setup process to define a Prover ID from scratch.
Refer to Documentation or Community Support:
Consult official Nexus documentation or community forums for more guidance on setting or changing the Prover ID.
