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
> Подменить url в Charles чтобы в запросе ушло имя которые вы вписали в Postman, а вернулось то, которое вы подставили в Charles.
### Решение. BreakPoint.
1. Создаем GET-запрос в **Postman**.

![image](https://user-images.githubusercontent.com/110128771/218327633-76be3ff0-adb9-4103-9d30-0d5c6723ab05.png)

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
8.	В **Postman** видим, что в параметрах запроса изменилось значение ключа **name**. 
	![image](https://user-images.githubusercontent.com/110128771/218327722-732d2532-78ad-489a-8da9-e697cc1b4527.png)
