
Initially take a VM or Ubuntu Machine. 

Look into the given website https://rancher.com/docs/k3s/latest/en/installation/airgap/#manually-deploy-images-method.

In that look into “Manually Deploy Images Method “and further scroll down to “Prepare the images directory and K3 binary”.

Open the terminal in that create a directory as given below

sudo mkdir -p /var/lib/rancher/k3s/agent/images/

After creating a directory, obtain the images tar file for your architecture from the releases page for the version of K3s you will be running.

In releases page find the given version “k3s-airgap-images-amd64.tar”

Now run the wget linking with above version in the terminal

Unzip the above version by using sudo tar –xvf k3s-airgap-images-amd64.tar”

Copy the tar file in the images directory as given below

sudo cp ./k3s-airgap-images-amd64.tar/var/lib/rancher/k3s/agent/images

Now move to home user and place the binary at /usr/local/bin and ensure it is executable.

For the above the K3s binary from the releases page, in that pick “K3S” version. Place the binary in /usr/local/bin.

Download the K3s install script at https://get.k3s.io. Place the install script anywhere on each air-gapped node, and name it install.sh.

Run ./install.sh in the terminal.

Give permissions by running chmod 744 install.sh

Run command sudo INSTALL_K3s_SKIP_DOWNLOAD=true ./install.sh

Now K3 will be installed and run kubectl cli command to check the status.
