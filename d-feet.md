Путь хранения данных freeIPA - /var/lib/freeipa/sysvol

# d-feet


Запуск d-feet производится из под root

![image](img/d-feet/20260327_160530.png)


В окне d-feet в поисковике напиши alt ну до методов добираемся как на скрине

![image](img/d-feet/20260327_161022.png)


## list_children


Пройдемся по путям:

'Machine'

![image](img/d-feet/20260327_161834.png)

'Machine/categories'

![image](img/d-feet/20260327_162201.png)

'Machine/categories/ALT System'

![image](img/d-feet/20260327_162447.png)


'Machine/categories/ALT System/inherited'

![image](img/d-feet/20260327_163731.png)


Выберем например категорию LAPS

'Machine/categories/ALT System/inherited/LAPS'

![image](img/d-feet/20260327_164222.png)


посмотрим политики

'Machine/categories/ALT System/inherited/LAPS/policies'

![image](img/d-feet/20260327_164453.png)


Выбираем первую политику ALT_LAPS:Administrator Account Name

обрати внимание, что что бы мы не вписали в list_children далее, в результате мы будем получать политики

'Machine/categories/ALT System/inherited/LAPS/policies/ALT_LAPS:Administrator Account Name'
изменений никаких нет, тоже самое, что и 'Machine/categories/ALT System/inherited/LAPS/policies'


![image](img/d-feet/20260327_164947.png)

Или например введем 123, результат не изменится

'Machine/categories/ALT System/inherited/LAPS/policies/123'

![image](img/d-feet/20260327_165124.png)