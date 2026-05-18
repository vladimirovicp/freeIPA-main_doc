

const NAME_GPT = '\\\\example.test\\SysVol\\example.test\\Policies\\{16D7EE44-417B-4A76-BE92-B0C5C1030A82}';
const TARGET = 'Machine';
const PATH = 'Software\\\\BaseALT\\\\Policies\\\\Laps\\\\PostAuthenticationResetDelay';
const VALUE = 'enabled;111';
const METADATA = 'Machine/categories/Система ALT/inherited/LAPS/policies/ALT_LAPS:LAPS_PostAuthenticationActions';



## get_current_value

```bash
ipa gpo-get-current-value
```

**NAME_GPT :** '\\\\example.test\\SysVol\\example.test\\Policies\\{16D7EE44-417B-4A76-BE92-B0C5C1030A82}';
**TARGET:** 'Machine';
**PATH :** 'Software\\\\BaseALT\\\\Policies\\\\Laps\\\\PostAuthenticationResetDelay';



## Set

```bash
ipa gpo-set-policy
```

**NAME_GPT :** '\\\\example.test\\SysVol\\example.test\\Policies\\{16D7EE44-417B-4A76-BE92-B0C5C1030A82}';
**TARGET:** 'Machine';
**PATH :** 'Software\\\\BaseALT\\\\Policies\\\\Laps\\\\PostAuthenticationResetDelay';
**VALUE :** 'test';


![image](/parsing/img/20260518_150540.jpg)



Перепроверю все ли верно ввёл

```bash
ipa gpo-list-children
```

![image](/parsing/img/20260518_151820.jpg)

```
Machine/categories/Система ALT/inherited/LAPS/policies/Действия после проверки подлинности
```

## get

```bash
ipa gpo-get-policy
```

```
Machine/categories/Система ALT/inherited/LAPS/policies/Действия после проверки подлинности
```

![image](/parsing/img/20260518_152354.jpg)

![image](/parsing/img/20260518_152523.jpg)

![image](/parsing/img/20260518_152620.jpg)



```
Software\\BaseALT\\Policies\\Laps\\PostAuthenticationResetDelay
```

Поиграем со слешами...

## Set 

**NAME_GPT :**  ```\\example.test\SysVol\example.test\Policies\{16D7EE44-417B-4A76-BE92-B0C5C1030A82}```

**TARGET:**  ```Machine```

**PATH :** ```Software\\BaseALT\\Policies\\Laps\\PostAuthenticationResetDelay```

**VALUE :**  ```test-8```



![image](/parsing/img/20260518_153752.jpg)


![image](/parsing/img/20260518_153851.jpg)
























