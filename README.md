# NEXUS-GUIDE
Complete Installation and Configuration Process 
System Update and Initial Setup
(run the code in green one by one)


sudo apt update && sudo apt upgrade -y
sudo apt install -y build-essential curl wget git

Install Rust and Update Toolchain


apt install rustup
rustup update stable

sudo add-apt-repository universe
sudo apt update
sudo apt install -y protobuf-compiler

Install Nexus CLI


curl https://cli.nexus.xyz/ | sh

There will be an Error, don’t worry, keep going

source $HOME/.cargo/env
echo 'source $HOME/.cargo/env' >> ~/.rc

Install Additional Dependencies


sudo apt install -y pkg-config
sudo apt install -y libssl-dev
sudo apt install -y protobuf-compiler

Re-Install Nexus CLI (if needed)
Run the CLI installation again after dependencies are in place:


curl https://cli.nexus.xyz/ | sh

Disconnect and Reconnect to the Server
After reconnecting, start a screen session to keep the node running:


screen -S nexus

Reset Existing Nexus Configurations (If Needed)
If there were previous configurations that caused issues, move them:


mv ~/.nexus ~/.nexus_backup
Then re-run the installation:


curl https://cli.nexus.xyz/ | sh

During the setup, enter your desired Prover ID when prompted.
If the default Prover ID is used and you want to specify your own:
Check Nexus Configuration Files:
Locate ~/.nexus/prover-id (or a similar file) and edit it with a text editor:


nano ~/.nexus/prover-id
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
