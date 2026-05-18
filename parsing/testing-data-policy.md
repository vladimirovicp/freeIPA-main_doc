

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











