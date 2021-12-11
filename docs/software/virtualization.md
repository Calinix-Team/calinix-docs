# Virtual Machines

A virtual machine, commonly shortened to just VM, is no different than any other physical computer like a laptop, smart phone, or server. It has a CPU, memory, disks to store your files, and can connect to the internet if needed. While the parts that make up your computer (called hardware) are physical and tangible, VMs are often thought of as virtual computers or software-defined computers within physical servers, existing only as code.

Put simply virtual machines---known as VMs---are applications that create a software environment that mimics computer hardware. An operating system can then be installed into this environment. We call this a "guest OS", while the operating system you have installed on your physical computer is the "host OS". Additionally, virtualization can be enhanced with the help of dedicated system hardware!

## Virtual Machines vs. Dual Booting Linux

There are two ways to run multiple operating systems on a computer:

- Dual booting
- Virtual machine

Dual booting is good but has its downsides. For example, you can run two or more Linux distributions installed on your computer. However, it doesn't work well for everyone. Various issues can frustrate the experience, such as rebooting.

The time taken to restart, select a different OS at the GRUB bootloader screen, and then boot, can be problematic. This is especially true on systems where Linux is installed alongside Windows.

On slower systems, you could be waiting 5-10 minutes before you can start being productive. With anti-virus software scanning at boot, you're soon on a massive go-slow.

However, running your secondary OS in a virtual machine can overcome this problem.

### Check if your PC supports Virtualization

To check if your PC supports virtualization, fire up the terminal and enter

```bash
lscpu | grep "Virtualization"
```

You should see something like AMD-V, VT-x or VT-d to confirm your PC supports virtualization.


Let's see the different ways of Virtualization

## QEMU/KVM

KVM is one of the most used Virtualization software in Linux World. In fact, most cloud providers use KVM as their Hypervisor of choice. Big projects including Openstack use KVM as default Virtualization tool.

#### Install required packages

```
sudo pacman -Sy qemu virt-manager virt-viewer dnsmasq vde2 bridge-utils openbsd-netcat ebtables iptables libguestfs
```

#### Enable libvirtd.service

Once the installation is done, start and enable `libvirtd` service to start at boot:

```bash
sudo systemctl enable libvirtd.service
sudo systemctl start libvirtd.service
```

#### Enable Normal User to Manage KVM

Since we want to use our standard Linux user account to manage KVM, let’s configure KVM to allow this.

Open the `file /etc/libvirt/libvirtd.conf` for editing.

Set the UNIX domain socket group ownership to libvirt, (around line 85)

```bash
unix_sock_group = "libvirt"
```
Set the UNIX socket permissions for the R/W socket (around line 102)

```bash
unix_sock_rw_perms = "0770"
```

Add your user account to libvirt group.

```bash
sudo usermod -a -G libvirt $(whoami)
newgrp libvirt
sudo systemctl restart libvirtd.service
```

You have successfully installed KVM, QEMU and Virt Manager on Arch Linux. You are now good to go. You can install a Linux or Windows OS Virtual Machine and build your study labs.

