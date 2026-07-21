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
apt-get install freeipa-server-dns


ipa-server-install
```



https://www.altlinux.org/Update/Sisyphus

https://www.altlinux.org/Debuginfo

https://www.altlinux.org/FreeIPA/%D0%98%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F_%D1%81_AD

Примечание: Если при добавлении зоны перенаправления появляется предупреждение об ошибке проверки DNSSEC, это означает что удалённый DNS-сервер не использует DNSSEC. Рекомендуется включить DNSSEC на удаленном DNS-сервере.
Если включить проверку DNSSEC на удаленном DNS-сервере нельзя, можно отключить DNSSEC на сервере FreeIPA. Для этого в файле /etc/bind/ipa-options-ext.conf следует привести параметр dnssec-validation к виду:

```
dnssec-validation no;
```

И перезапустить службу DNS:

```
# systemctl restart bind.service
```