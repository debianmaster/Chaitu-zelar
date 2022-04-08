**<h1>Setting Up K3 Manually from Local Machine through Airgap</h1>**

1. Initially take a VM or local Ubuntu Machine. 

2. Look into the website **https://rancher.com/docs/k3s/latest/en/installation/airgap/#manually-deploy-images-method**.

3. In the website look into “**Manually Deploy Images Method** “and further scroll down to **Prepare the images directory and K3 binary**.

4. Open the terminal in that create a directory **sudo mkdir -p /var/lib/rancher/k3s/agent/images/**

5. After creating a directory, obtain the images tar file for your architecture from the releases page for the version of K3s you will be running.

6. In **releases** page find the given version **k3s-airgap-images-amd64.tar**

7. Now run the **wget** linking with above version in the terminal

8. Unzip the above version by using `sudo tar –xvf k3s-airgap-images-amd64.tar`

9. Copy the tar file in the images directory `sudo cp ./k3s-airgap-images-amd64.tar/var/lib/rancher/k3s/agent/images`

10. Now move to home user and place the binary at **/usr/local/bin** and ensure it is executable.

11. For the above the K3s binary from the releases page, in that pick **K3S** version. Place the binary in **/usr/local/bin**.

12. Download the K3s install script at **https://get.k3s.io.** Place the install script anywhere on each air-gapped node, and name it **install.sh**.

13. Run **./install.sh** in the terminal.

14. Give permissions by running **chmod 744 install.sh**

15. Run command **sudo INSTALL_K3s_SKIP_DOWNLOAD=true ./install.sh**

16. Now K3 will be installed and run kubectl cli command to check the status.
