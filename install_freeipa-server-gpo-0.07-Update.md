# freeipa-server-gpo 0.07

```bash
apt-get remove freeipa-server-gpo
[root@ipa ~]# apt-get update
```

p11
```bash
[root@ipa ~]# apt-repo add 417532
[root@ipa ~]# apt-get update
```

```bash
[root@ipa ~]# apt-get install freeipa-server-gpo
```
```bash
[root@ipa ~]# kinit admin
```
Password for admin@ALT.TEST: 12345678

```bash
[root@ipa ~]# ipa-gpo-install
```

Что бы изменения сработали надо сделать перезапуск системной службы
```bash
systemctl restart gpuiservice.service
```


Если при создании политик в графике будет возникать ошибка ,то нужно один раз перезагрузить сервис oddjobd

```
systemctl restart oddjobd.service
```

Новый пароль Password for admin@ALT.TEST: 12345679


```
ipactl restart
```