# vagrant-test-ms-edge

> Browser testing environment with Windows virtual machine on Vagrant.

## Installation

1. Install Vagrant and "Microsoft Remote Desktop" app

2. Download and unzip the image

   ```
   $ curl -O https://az792536.vo.msecnd.net/vms/VMBuild_20190311/Vagrant/MSEdge/MSEdge.Win10.Vagrant.zip
   $ unzip ./MSEdge.Win10.Vagrant.zip
   ```

3. Register the image as a box to Vagrant

   ```
   $ vagrant box add MSEdge.Win10 ./MSEdge\ -\ Win10.box
   ```

## Setup

First, need to enable "Remote Desktop" with GUI.

1. Boot virtual machine

    ```
    $ vagrant up
    ```

2. Login with VirtualBox GUI

3. Change `Remote Desktop settings`

    1. Move to `Settings` > `Remote Desktop settings`

    2. Change `Enable Remote Desktop` to `On`.

4. Save snapshot as "initilized"

    ```
    $ vagrant snapshot save initialized
    ```

## Usage

Booting virtual machine.

```
$ vagrant up
```

Access to virtual machine with "Microsoft Remote Desktop" app.       
Login with `IEUser:Passw0rd!`.

```
$ vagrant rdp
```

Stopping virtual machine.

```
$ vagrant halt
```
