# Charles Proxy. 
### Задание 1. На страничке представлен алгоритм выполнения первого задания. 
```
Method: GET, EndPoint: /get_method
request url params: 
 name: str
 age: int
response: 
[
    “Str”,
    “Str”
]
```
> Сделать в **BreakPoint** и в **Rewrite**. 
> Подменить url в Charles, чтобы в запросе ушло имя которые вы вписали в Postman, а вернулось то, которое вы подставили в Charles.
### Решение. BreakPoint.
1. Создаем GET-запрос в **Postman**.
<div id="screen" align="center" dir="auto">
<p dir="auto"> <img src="https://user-images.githubusercontent.com/110128771/218327633-76be3ff0-adb9-4103-9d30-0d5c6723ab05.png")
</p> </div>

2. В **Charles** выполняем команду: **Proxy/Breakpoint Settings**.
3. В окне **Breakpoints Settings** включаем чек-бокс **Enable Breakpoints**.
4. Нажимаем кнопку **Add**.
5. В окне **Edit Breakpoint**:
   -	В поле **Host** вводим GET-запрос: http://162.55.220.72:5005/get_method?name=Nata&age=51
   -	Нажимаем **TAB** на клавиатуре. 
   -	Устанавливаем чек-бокс **Request**.
   -	Нажимаем **ОК**.

<div id="screen" align="center" dir="auto">
<p dir="auto"> <img src="https://user-images.githubusercontent.com/110128771/218409147-1eca4a1e-f69a-4f72-bdd8-e4b5862798f5.png">
</p> </div>

6.	В **Postman** отправляем запрос с помощью кнопки **SEND**.
7.	В **Charles** переходим на вкладку **Breakpoint/Edit Request/URL**, подменяем имя и нажимаем на кнопку **Execute**.
![image](https://user-images.githubusercontent.com/110128771/218409592-1736d3c5-1d1d-4921-bdf5-c8c13a8f373e.png)
7.	Видим, что в перехваченном запросе,  значение ключа name изменилось.
![image](https://user-images.githubusercontent.com/110128771/218412978-46b67f3f-dd64-4b36-9fb3-f091f0ce72ec.png)

8.	В **Postman** пришел ответ с измененным значением.
![image](https://user-images.githubusercontent.com/110128771/218413107-25c4a936-76c8-4c13-913c-fa75b054a4d3.png)

### Решение. Rewrite.
1.	Используем  созданный ранее GET-запрос.
2.	В **Charles** выполняем команду: **Tools/Rewrite**.
3.	В окне **Rewrite Settings** включаем чек-бокс **Enable Rewrite**.
4.	Нажимаем кнопку **Add**.
5.	В  области **Location** нажимаем кнопку **Add**.
6.	В окне **Edit location**:
   - В поле **Host** вводим GET-запрос: http://162.55.220.72:5005/get_method?name=Nata&age=51
   - Нажимаем **TAB** на клавиатуре. 
   - Нажимаем **ОК**.
7.	В  области **Type**  нажимаем кнопку **Add**.
8.	В окне **Rewrite Rule**:
   - Для параметра **Type** из списка выбираем значение **Modify Query Param**.
   - В области **Where** устанавливаем чек-бокс **Request**.
   - В области **Match** вводим исходные «ключ-значение».
   - В области **Replace** вводим «ключ-значение», которым будем заменять исходное значение.
   - Нажимаем **ОК**.
     
<div id="screen" align="center" dir="auto">
<p dir="auto"> <img src="https://user-images.githubusercontent.com/110128771/218439630-1a0fb93e-fa8d-4764-86d4-b8848a969937.png">
</p> </div>

9.	В  окне **Rewrite Settings** нажимаем кнопку **ОК**.
<div id="screen" align="center" dir="auto">
<p dir="auto"> <img src="https://user-images.githubusercontent.com/110128771/218442984-405d3976-cdfb-4b74-abe1-2ef441833583.png">
</p> </div>

10.	В **Postman** отправляем запрос, анализируем результат.

![image](https://user-images.githubusercontent.com/110128771/218443102-20a1fe9e-6805-49f3-94c4-d0ebffce105b.png)
