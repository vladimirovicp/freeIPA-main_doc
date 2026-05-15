
```
    kinit admin
```

## list_children 

```bash
ipa gpo-list-children
```

Machine

![image](img/gpui-console/20260515_141331.jpg)

Machine/categories

![image](img/gpui-console/20260515_141551.jpg)

Machine/categories/ALT System

!Обрати внимание, на то, что зависит от языка системы!
![image](img/gpui-console/20260515_141853.png)


Machine/categories/Система ALT
![image](img/gpui-console/20260515_142109.jpg)

Machine/categories/Система ALT/inherited
![image](img/gpui-console/20260515_142416.jpg)

Machine/categories/Система ALT/inherited/LAPS
![image](img/gpui-console/20260515_142630.jpg)

Machine/categories/Система ALT/inherited/LAPS/policies
![image](img/gpui-console/20260515_152304.jpg)

Выбераем например: Имя учетной записи администратора

В результате мы получили следующий путь:

``` Machine/categories/Система ALT/inherited/LAPS/policies/Имя учетной записи администратора```


## Get Прочитаем значения

```bash
ipa gpo-get-policy
```

![image](img/gpui-console/20260515_154202.jpg)

Данные path мы получаем из data

```data: Read_Path_GPT('Software\\BaseALT\\Policies\\Laps\\AdministratorAccountName')```

```path = Software\\BaseALT\\Policies\\Laps\\AdministratorAccountName```

## Set Записываем

В объекте политики нужно взять File System Path

в моем случаи https://ipa.example.test/ipa/ui/#/e/gpo/details/test
```
File System Path = \\example.test\SysVol\example.test\Policies\{16D7EE44-417B-4A76-BE92-B0C5C1030A82}
```

НАДО ДОПИСАТЬ!




## get_current_value

```bash
ipa gpo-get-current-value
```

```name_gpt = \\example.test\SysVol\example.test\Policies\{16D7EE44-417B-4A76-BE92-B0C5C1030A82}```
```target = Machine```
```path = Software\\BaseALT\\Policies\\Laps\\AdministratorAccountName```

![image](img/gpui-console/20260515_160105.png)
