# k3s-desktop

## run packer to build the initial VM
1. setup packer
```
cd packer
packer init
```
2. build cloud-config.yml
Set up a cloud-config so that you can use your own ssh keys. @TODO

3. build the VM
```
packer build k3s.json
```

## Add this box file to vagrant
```
cd ../vagrant
vagrant add {BOX FILE FROM ABOVE}
```
modify Vagrantfile to use the same name.

## Start/Provision the VM
```
vagrant up
```
The provisioner should start up k3s, and spit out the kubeconfig.

## Kubeconfig and using k3s
Save the kubeconfig and export $KUBECONFIG={That file}
now you can use k3s locally.
