# freeipa-server-gpo

[link github](https://github.com/danila-Skachedubov/freeipa-server-gpo)

На сегодняшний день пакеты в заданиях [link](https://packages.altlinux.org/ru/tasks/search/?q=freeipa-server-gpo)

Для установки используем ```apt-repo add 'номер задачи'```

```bash
[root@ipa ~]# apt-repo
```
```
rpm [p11] http://ftp.altlinux.org/pub/distributions/ALTLinux p11/branch/x86_64 classic
rpm [p11] http://ftp.altlinux.org/pub/distributions/ALTLinux p11/branch/x86_64-i586 classic
rpm [p11] http://ftp.altlinux.org/pub/distributions/ALTLinux p11/branch/noarch classic
```

```bash
[root@ipa ~]# apt-repo add 399023
[root@ipa ~]# apt-get update
```
Устанавливаем

```bash
apt-get install freeipa-server-gpo
ipa-gpo-install
```