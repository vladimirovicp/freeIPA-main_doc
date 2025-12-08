# install

```bash
hostnamectl set-hostname ipa.alt.test
reboot
```

```bash
hostname
ipa.alt.test
```

```bash
apt-get update
apt-get install haveged
systemctl enable --now haveged

apt-get install freeipa-server-dns
```

```bash
ipa-server-install

Do you want to configure integrated DNS (BIND)? [no]: yes
Server host name [ipa.alt.test]:
Please confirm the domain name [alt.test]:
Please provide a realm name [ALT.TEST]: 
Directory Manager password:12345678
IPA admin password: 12345678

Do you want to configure DNS forwarders? [yes]:yes
Following DNS servers are configured in /etc/resolv.conf: 127.0.0.1
Do you want to configure these servers as DNS forwarders? [yes]:no
Enter an IP address for a DNS forwarder, or press Enter to skip: 
No DNS forwarders configured
Do you want to search for missing reverse zones? [yes]: yes

Checking DNS domain 2.0.10.in-addr.arpa., please wait ...
Checking DNS domain 0.0.0.0.0.0.0.0.0.0.0.0.0.0.d.f.ip6.arpa., please wait ...
Do you want to create reverse zone for IP 10.0.2.15 [yes]: yes

Please specify the reverse zone name [2.0.10.in-addr.arpa.]: 

Checking DNS domain 2.0.10.in-addr.arpa., please wait ...
Do you want to create reverse zone for IP fd00::a00:27ff:fe9e:7241 [yes]:

Please specify the reverse zone name [0.0.0.0.0.0.0.0.0.0.0.0.0.0.d.f.ip6.arpa.]:

NetBIOS domain name [ALT]:

Do you want to configure CHRONY with NTP server or pool address? [no]:


Continue to configure the system with these values? [no]: yes


Setup complete

Next steps:
	1. You must make sure these network ports are open:
		TCP Ports:
		  * 80, 443: HTTP/HTTPS
		  * 389, 636: LDAP/LDAPS
		  * 88, 464: kerberos
		  * 53: bind
		UDP Ports:
		  * 88, 464: kerberos
		  * 53: bind
		  * 123: ntp

	2. You can now obtain a kerberos ticket using the command: 'kinit admin'
	   This ticket will allow you to use the IPA tools (e.g., ipa user-add)
	   and the web user interface.

Be sure to back up the CA certificates stored in /root/cacert.p12
These files are required to create replicas. The password for these
files is the Directory Manager password
The ipa-server-install command was successful


ipactl status

Directory Service: RUNNING
krb5kdc Service: RUNNING
kadmin Service: RUNNING
named Service: RUNNING
httpd Service: RUNNING
ipa-custodia Service: RUNNING
pki-tomcatd Service: RUNNING
ipa-otpd Service: RUNNING
ipa-dnskeysyncd Service: RUNNING
ipa: INFO: The ipactl command was successful

kinit admin
Password for admin@ALT.TEST: 12345678

klist

Valid starting       Expires              Service principal
05.12.2025 23:02:24  06.12.2025 22:15:00  krbtgt/ALT.TEST@ALT.TEST

? - apt-get install ntpdate
? - ntpdate -q localhost

ipa dnszone-show alt.test

  Имя зоны: alt.test.
  Активная зона: True
  Полномочный сервер имён: ipa.alt.test.
  Адрес электронной почты администратора: hostmaster.alt.test.
  Номер SOA: 1764960517
  Обновление SOA: 3600
  Повторный запрос SOA: 900
  Окончание действия SOA: 1209600
  Минимальный срок жизни SOA: 3600
  Политика обновления BIND: grant ALT.TEST krb5-self * A; grant ALT.TEST
                            krb5-self * AAAA; grant ALT.TEST krb5-self * SSHFP;
  Динамическое обновление: True
  Разрешить запрос: any;
  Разрешить перенос: none;


ipa dnszone-show 2.0.10.in-addr.arpa.

 Имя зоны: 2.0.10.in-addr.arpa.
  Активная зона: True
  Полномочный сервер имён: ipa.alt.test.
  Адрес электронной почты администратора: hostmaster.alt.test.
  Номер SOA: 1764960486
  Обновление SOA: 3600
  Повторный запрос SOA: 900
  Окончание действия SOA: 1209600
  Минимальный срок жизни SOA: 3600
  Политика обновления BIND: grant ALT.TEST krb5-subdomain 2.0.10.in-addr.arpa.
                            PTR;
  Динамическое обновление: True
  Разрешить запрос: any;
  Разрешить перенос: none;
```
