# Установка сервера FreeIPA

* doc - https://www.altlinux.org/FreeIPA/%D0%A3%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0_%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D0%B0_FreeIPA



```bash

apt-get install freeipa-server

ipa-server-install
```

```
Do you want to configure integrated DNS (BIND)? [no]: yes
```

```bash
ipa-server-install
```



https://www.altlinux.org/Update/Sisyphus

https://www.altlinux.org/Debuginfo

https://www.altlinux.org/FreeIPA/%D0%98%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F_%D1%81_AD


admin:///var/lib/bind/etc

Примечание: Если при добавлении зоны перенаправления появляется предупреждение об ошибке проверки DNSSEC, это означает что удалённый DNS-сервер не использует DNSSEC. Рекомендуется включить DNSSEC на удаленном DNS-сервере.
Если включить проверку DNSSEC на удаленном DNS-сервере нельзя, можно отключить DNSSEC на сервере FreeIPA. Для этого в файле /etc/bind/ipa-options-ext.conf следует привести параметр dnssec-validation к виду:

```
dnssec-validation no;
```

И перезапустить службу DNS:

```
# systemctl restart bind.service
```



# install

```bash



apt-get install freeipa-server
apt-get install freeipa-server-dns
ipa-server-install
```

```
This program will set up the IPA Server.
Version 4.12.5

This includes:
  * Configure a stand-alone CA (dogtag) for certificate management
  * Configure the NTP client (CHRONY)
  * Create and configure an instance of Directory Server
  * Create and configure a Kerberos Key Distribution Center (KDC)
  * Configure Apache (httpd)
  * Configure SID generation
  * Configure the KDC to enable PKINIT

To accept the default shown in brackets, press the Enter key.

Do you want to configure integrated DNS (BIND)? [no]: yes
```

```
Server host name [FreeIPA]: dc1.freeipa.alt

Warning: skipping DNS resolution of host dc1.freeipa.alt
The domain name has been determined based on the host name.

Please confirm the domain name [freeipa.alt]: 

The kerberos protocol requires a Realm name to be defined.
This is typically the domain name converted to uppercase.

Please provide a realm name [FREEIPA.ALT]: 
```

```
Directory Manager password: 12345678
Password (confirm): 12345678

The IPA server requires an administrative user, named 'admin'.
This user is a regular system account used for IPA server administration.

IPA admin password: 12345678
Password (confirm): 12345678

```

```

Checking DNS domain freeipa.alt., please wait ...
Please provide the IP address to be used for this host name: 192.168.1.10

```

Нужно указать статический IP-адрес этого сервера (например, 192.168.1.10), который будет привязан к имени dc1.freeipa.alt в DNS-зоне FreeIPA.

10.0.1.1

```

Enter an additional IP address, or press Enter to skip: 

```

```

Checking DNS domain freeipa.alt., please wait ...
Please provide the IP address to be used for this host name: 192.168.1.10
Enter an additional IP address, or press Enter to skip: 
No network interface matches the IP address 192.168.1.10
WARNING: No network interface matches the IP address 192.168.1.10
Do you want to configure DNS forwarders? [yes]: 
Following DNS servers are configured in /etc/resolv.conf: 10.0.2.3
Do you want to configure these servers as DNS forwarders? [yes]: 
All detected DNS servers were added. You can enter additional addresses now:
Enter an IP address for a DNS forwarder, or press Enter to skip: 
DNS forwarders: 10.0.2.3
Checking DNS forwarders, please wait ...
Do you want to search for missing reverse zones? [yes]: 
Checking DNS domain 1.168.192.in-addr.arpa., please wait ...
Do you want to create reverse zone for IP 192.168.1.10 [yes]: 
Please specify the reverse zone name [1.168.192.in-addr.arpa.]: 
Checking DNS domain 1.168.192.in-addr.arpa., please wait ...
Using reverse zone(s) 1.168.192.in-addr.arpa.
Trust is configured but no NetBIOS domain name found, setting it now.
Enter the NetBIOS name for the IPA domain.
Only up to 15 uppercase ASCII letters, digits and dashes are allowed.
Example: EXAMPLE.

```


```
NetBIOS domain name [FREEIPA]: 

Do you want to configure CHRONY with NTP server or pool address? [no]: 
 
The IPA Master Server will be configured with:
Hostname:       dc1.freeipa.alt
IP address(es): 192.168.1.10
Domain name:    freeipa.alt
Realm name:     FREEIPA.ALT

The CA will be configured with:
Subject DN:   CN=Certificate Authority,O=FREEIPA.ALT
Subject base: O=FREEIPA.ALT
Chaining:     self-signed

BIND DNS server will be configured to serve IPA domain with:
Forwarders:       10.0.2.3
Forward policy:   only
Reverse zone(s):  1.168.192.in-addr.arpa.

Continue to configure the system with these values? [no]: yes
```


```
See the installation logs and the following files/directories for more information:
  /var/log/pki/pki-tomcat
  [error] RuntimeError: CA configuration failed.
CA configuration failed.
The ipa-server-install command failed. See /var/log/ipaserver-install.log for more information
```


```bash
ipa-server-install --uninstall
```

```bash
systemctl enable --now certmonger.service
```

```
Created symlink '/etc/systemd/system/multi-user.target.wants/certmonger.service' → '/usr/lib/systemd/system/certmonger.service'.
```


```bash
getcert add-ca -c IPA -e /usr/libexec/certmonger/ipa-sumbit
```

```
There is already a CA with the nickname "IPA".
```

```bash

getcert list-cas

```

```
CA 'SelfSign':
	is-default: no
	ca-type: INTERNAL:SELF
	next-serial-number: 01
CA 'IPA':
	is-default: no
	ca-type: EXTERNAL
	helper-location: /usr/libexec/certmonger/ipa-submit
CA 'dogtag-ipa-renew-agent':
	is-default: no
	ca-type: EXTERNAL
	helper-location: /usr/libexec/certmonger/dogtag-ipa-renew-agent-submit
CA 'local':
	is-default: no
	ca-type: EXTERNAL
	helper-location: /usr/libexec/certmonger/local-submit
```

```bash
ipa-server-install
```





## Сборка

* https://altlinux.space/korney3g1/libadmix

```bash
cd ./libadmix/
git checkout sisyphus 

gear-hsh

gear-rpm -ba

apt-get install rpm-macros-rust rpm-build-rust python3-dev python3-module-maturin python3-module-pyproject-installer

gear-rpm -ba
```


* https://altlinux.space/korney3g1/freeipa-server-gpo


```bash
cd freeipa-server-gpo

git checkout -b move_to_admix


gear-rpm -ba


```



# other


ipactl restart

ipa-gpo-install

kinit admin

 apt-get install rpm-build make gear


chown fad:fad /home/fad/PowerOptions.xml


chown fad:fad admin:///home/fad/PowerOptions.xml


apt-get install /home/fad/RPM/RPMS/x86_64/python3-module-admix-0.1.0-alt1.x86_64.rpm


apt-get install /home/fad/RPM/RPMS/x86_64/freeipa-server-gpo-0.0.8-alt1.x86_64.rpm

gear-rpm -ba


apt-get install python3-module-pyproject-installer


cd /usr/share/ipa/ui/js/plugins/chain/

cd /home/fad/git/freeipa-server-gpo/

cd /usr/share/ipa/ui/js/plugins/chain/

cd /home/fad/git/gp-web-ui-integration/

cd /usr/share/ipa/ui/js/plugins/chain/


-----------------

apt-get install $(rpmspec -q --buildrequires ./admix.spec)

rpmspec -q --buildrequires ./admix.spec 

rpmspec -q --requires ./admix.spec 

rpmspec --requires ./admix.spec 




--------

git clone https://altlinux.space/korney3g1/libadmix.git


git clone https://altlinux.space/korney3g1/freeipa-server-gpo.git


git checkout move_to_admix 

gear-rpm -ba