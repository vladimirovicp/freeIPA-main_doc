

## set

```
'\\\\example.test\\SysVol\\example.test\\Policies\\{16D7EE44-417B-4A76-BE92-B0C5C1030A82}','Machine','Software\\\\BaseALT\\\\Policies\\\\Laps\\\\AdministratorAccountName','test 27.04.2026','Machine/categories/ALT System/inherited/LAPS/policies/ALT_LAPS:Administrator Account Name'
```

Отправляем получает True

## get_current_value

```
'\\\\example.test\\SysVol\\example.test\\Policies\\{16D7EE44-417B-4A76-BE92-B0C5C1030A82}','Machine','Software\\\\BaseALT\\\\Policies\\\\Laps\\\\AdministratorAccountName'
```

получаем в ответ:

```
'{"value_data": "test 27.04.2026", "value_type": "REG_SZ"}'
```

Сработало!!!

---

Следующий пример:


## set
```
'\\\\example.test\\SysVol\\example.test\\Policies\\{16D7EE44-417B-4A76-BE92-B0C5C1030A82}','Machine','Software\\\\BaseALT\\\\Policies\\\\Laps\\\\AdministratorAccountName','{"state":"enabled","values":{"Software\\BaseALT\\Policies\\Laps\\PostAuthenticationResetDelay":24,"Software\\BaseALT\\Policies\\Laps\\PostAuthenticationActions":"0"}}','Machine/categories/ALT System/inherited/LAPS/policies/ALT_LAPS:Administrator Account Name'
```


Отправляем получает True


## get_current_value

```
'\\\\example.test\\SysVol\\example.test\\Policies\\{16D7EE44-417B-4A76-BE92-B0C5C1030A82}','Machine','Software\\\\BaseALT\\\\Policies\\\\Laps\\\\AdministratorAccountName'
```

получаем в ответ:

```
'{"value_data": "", "value_type": "REG_SZ"}'

```

---

## set
```
'\\\\example.test\\SysVol\\example.test\\Policies\\{16D7EE44-417B-4A76-BE92-B0C5C1030A82}','Machine','Software\\\\BaseALT\\\\Policies\\\\Laps\\\\AdministratorAccountName','{"state":}','Machine/categories/ALT System/inherited/LAPS/policies/ALT_LAPS:Administrator Account Name'
```


Отправляем получает True

## get_current_value

```
'{"value_data": "{\\"state\\":}", "value_type": "REG_SZ"}'

```


---
