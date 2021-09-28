# tf-customer-plugin-2
Testing adding customer plugin

## pre-requirements

- Install **Vagrant**
    - Download and install accordingly to your OS as described here : https://www.vagrantup.com/downloads.html
	
# Requirements
- Oracle Virtualbox recent version installed
[VirtualBox installation manual](https://www.virtualbox.org/manual/ch01.html#intro-installing)

- Hashicorp vagrant recent version installed
[Vagrant installation manual](https://learn.hashicorp.com/tutorials/vagrant/getting-started-install)


## Preparation 
- Clone git repository. 

```bash
git clone https://github.com/ayahmuhamed/tf-customer-plugin-2
```


- Change folder to tf-ob-custom-plugin

```bash
cd tf-customer-plugin-2
```

## Provisioning

- In the same folder you were before run 

```bash
vagrant up
```



## Implementation

- Connect to VM. In the same folder you were before run 

```bash
vagrant ssh
```


- Clone plugin repository. Run:

```
git clone https://github.com/petems/terraform-provider-extip
```



- Change directory to terraform-provider-extip. Run:

```bash
cd terraform-provider-extip
```

- Build provider. Run:

```bash
sudo make build
```

Simple result:

```bash
$ sudo make build
==> Checking that code complies with gofmt requirements...
go install
```

- Create plugin directory. In the same terminal run:

```bash
mkdir -p /vagrant/.terraform.d/plugins/localproviders/petems/extip/0.1.2/linux_amd64
```

Sample result

```bash
$ mkdir -p /vagrant/.terraform.d/plugins/localproviders/petems/extip/0.1.2/linux_amd64
$
```

- Copy plugin to the required path. Run:

```bash
cp $GOPATH/bin/terraform-provider-extip /vagrant/.terraform.d/plugins/localproviders/petems/extip/0.1.2/linux_amd64
```

- Change current directory to /vagrant. Run:

```bash
cd /vagrant
```

-  In the same folder run 

```bash
terraform init
```


