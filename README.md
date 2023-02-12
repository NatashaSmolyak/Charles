# Charles
### Задание 1.  
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
### Решение.  
1.	Создаем GET-запрос в Postman.

![image](https://user-images.githubusercontent.com/110128771/218327633-76be3ff0-adb9-4103-9d30-0d5c6723ab05.png)

2.	В Charles выполняем команду: Proxy/Breakpoint Settings.
3.	В окне Breakpoints Settings включаем чек-бокс Enable Breakpoints.
4.	Нажимаем кнопку Add.
5.	В окне Edit Breakpoint:
   -	В поле Host вводим GET-запрос: http://162.55.220.72:5005/get_method?name=Nata&age=51
   -	Нажимаем TAB. 
   -	Устанавливаем чек-бокс Response.
   -	Нажимаем ОК.

<div id="screen" align="center" dir="auto">
<p dir="auto"> <img src="https://user-images.githubusercontent.com/110128771/218328101-410308b0-4e33-46ee-9b1f-f9a47bc49296.png" style="max-width: 100%;">
</p> </div>

6.	В Postman отправляем запрос с помощью кнопки SEND.
7.	В Charles переходим на вкладку Edit Response,  на вкладке JSON Text подменяем имя и нажимаем на кнопку Execute.
![image](https://user-images.githubusercontent.com/110128771/218328115-fd0a8191-bf00-4c11-96ea-d6d2424653df.png)
8.	В Postman получаем ответ с измененным именем. 
	![image](https://user-images.githubusercontent.com/110128771/218327722-732d2532-78ad-489a-8da9-e697cc1b4527.png)
