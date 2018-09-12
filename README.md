# Kubernetes on local VM with kubeadm (OSX-Optimized)  #

### Why not Minikube or Docker for Mac? ###

Minikube and Kubernetes under Docker for Mac are both great and easy to use, but neither Minikube nor Docker for Mac use standard installation tools like kubeadm or kops that you might use for a production cluster. Projects that require a deeper Kubernetes integration will benefit
from production kube tools and a full kubernetes installation.

This projects encapsulates the scripts and configuration files required to automatically provision a local VM, via Vagrant, and bootstrap the VM
with a full Kubernetes installation and production cluster management tools.

### Technology Stack ###

It is highly recommended that engineers become acquainted with various supporting technologies. You can find more information here:

- Read more about [Vagrant](https://www.vagrantup.com/docs/getting-started/) *(https://www.vagrantup.com/docs/getting-started/)*
- Read more about [VirtualBox](https://www.virtualbox.org/manual/UserManual.html) *(https://www.virtualbox.org/manual/UserManual.html)*
- Read more about [Kubernetes](https://kubernetes.io/) *(https://kubernetes.io/)*

### Spin up your VM ###

Execute the following command locally to provision / configure your VM and generate the 'admin.conf' file, used to interact with
Kubernetes running in the VM:

    $ ./vm up

You can then interact with Kubernetes using kubectl (assumed to be installed on your development host) as follows:

    $ kubectl --kubeconfig ./admin.conf get nodes

### Additional Commands ###

Below is a list of commands to manage your local VM:

- ./vm ssh: SSH into the VM:

    `$ ./vm ssh`

- ./vm destroy: Completely delete the local VM and all associated files

    `$ ./vm destroy`

- ./vm reup: Completely delete the local VM and all associated files and spin up a new VM

    `$ ./vm reup`

- ./vm run: Pass ad-hoc commands to be executed in the VM (tunneled via SSH)

    `$ ./vm run ls -l /etc`

### Special Thanks ###

Special thanks to Liz Rice who put together much of the Vagrant automation in her blog post: https://medium.com/@lizrice/kubernetes-in-vagrant-with-kubeadm-21979ded6c63
