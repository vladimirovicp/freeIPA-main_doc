# gpo-get-current-value
Получить текущее значение из файла политики GPO

# gpo-list-children
Получить список дочерних политик по заданному пути


Path: пусто
```
[
  {
    "name": "meta"
  },
  {
    "name": "Machine"
  },
  {
    "name": "User"
  }
]
```


# gpo-set-policy
Установить значение политики в GPO

# gpo-get-policy
Получить значение политики по пути

Path: пусто
получим все что есть



# other

```bash
apt-get install d-feet
```

запуск root d-feetd-feet


хранение 
```
var/lib/samba/syslov/domain.alt/Polices/{A34C94C4-FEF6-444A-B49E-23E29CC3864B}/Machine/Registry.pol
var/lib/samba/syslov/domain.alt/Polices/{A34C94C4-FEF6-444A-B49E-23E29CC3864B}/Machine/Preferences/

```

тут пусто
```
/var/cache/samba/gpo_cache/SMB.BASEALT.RU/POLICIES/{74FF0072-E7F6-47AD-BD21-070377BBF950}/USER
```


```
[root@ipa ~]# systemctl status gpuiservice.service 
```
Если disabled 
Loaded: loaded (/usr/lib/systemd/system/gpuiservice.service; disabled; preset: disabled)

то он рестарт не делает
тогда 
```
systemctl enable gpuiservice.service
```
```
systemctl status gpuiservice.service
```

Loaded: loaded (/usr/lib/systemd/system/gpuiservice.service; enabled; preset: disabled)


Примеры


gpo-list-children 

Machine/categories/ALT System/inherited/GNOME Settings/inherited/Accessibility/policies


gpo-get-policy
/Machine/categories/ALT System/inherited/GNOME Settings/inherited/Accessibility/policies/ALT_Accessibility_Gnome:Accessibility Menu
