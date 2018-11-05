# How to install a Windows 10 Guest OS on Linux KVM Hypervisor using CLI (Virt-install) in Ubuntu 18.04

A guide on how to install a Windows 10 Guest OS on Linux KVM Hypervisor using CLI (Virt-install) in Ubuntu 18.04

This guide was written and tested in Ubuntu 18.04, 18.04.1


### Paste on Ubuntu cli

``
sudo virt-install \
    --name=Windows10 \
    --ram=8192 \
    --cpu host --hvm \
    --vcpus=2 \
    --os-type=windows \
    --os-variant=win8.1 \
    --disk /var/lib/libvirt/images/vms-win10,size=60,bus=virtio \
    --disk /var/lib/libvirt/boot/win-10-64bit-english.iso,device=cdrom,bus=ide \
    --disk /var/lib/libvirt/boot/virtio-win-drivers-20120712-1.iso,device=cdrom,bus=ide \
    --network bridge=br0 \
    --graphics vnc,listen=0.0.0.0
``

### Output

