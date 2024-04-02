# Тема 10. Декораторы и исключения.
Отчет по Теме #10 выполнил(а):
- Галеев Андрей Назарович
- ИНО ЗБ ПОАС-22-1

| Задание |  Сам_раб |
| ------ |  ------ |
| Задание 1 | + |
| Задание 2 | + |
| Задание 3 | + | 
| Задание 4 | + | 
| Задание 5 | + |

знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Самостоятельная работа №1
### Вовочка решил заняться спортивным программированием на python, но для этого он должен знать за какое время выполняется его программа. 

```python
import time
def calculate_execution_time(func):
    def wrapper(*args, **kwargs):
        start_time = time.time()
        result = func(*args, **kwargs)
        end_time = time.time()
        execution_time = end_time - start_time
        print(f"Время выполнения функции '{func.__name__}': {execution_time:.6f} секунд")
        return result
    return wrapper
@calculate_execution_time
def fibonacci():
    fib1 = fib2 = 1
    for i in range(2, 200):
        fib1, fib2 = fib2, fib1 + fib2
        print(fib2)
if __name__ == '__main__':
    fibonacci()
    print()
```
### Результат.
![Меню]().


## Выводы

Успешное выполнение данной задачи

## Самостоятельная работа №2
### Создайте пустой файл и файл, в котором есть какая-то информация. Напишите код программы. 

```python
try:
    #Чтение из пустого файла
    with open("empty.txt", "r") as file:
        data = file.read()
        if not data:
            raise Exception("Файл пустой")
        print("Данные из файла 'empty.txt':")
        print(data)
except Exception as e:
    print("Ошибка:", e)
print()

try:
    #Чтение из файла с информацией
    with open("data.txt", "r") as file:
        data = file.read()
        if not data:
            raise Exception("Файл пустой")
        print("Данные из файла 'data.txt':")
        print(data)
except Exception as e:
    print("Ошибка:", e)

```
### Результат.
![Меню]().

## Выводы

Успешное выполнение данной задачи
  
## Самостоятельная работа №3
### Напишите функцию, которая будет складывать 2 и введенное пользователем число, но если пользователь введет строку или другой неподходящий тип данных, то в консоль выведется ошибка "Неподходящий тип данных. Ожидалось число."

```python
def add_two_to_input():
    try:
        user_input = input("Введите число: ")
        number = int(user_input)
        result = 2 + number
        print("Результат сложения: ", result)
    except ValueError:
        print("Неподходящий тип данных. Ожидалось число.")

#Входные данные - число
add_two_to_input()

#Входные данные - строка
add_two_to_input()

```
### Результат.
![Меню]().

## Выводы

Успешное выполнение данной задачи
  
## Самостоятельная работа №4
### Создайте собственный декоратор, который будет использоваться для двух любых вами придуманных функций.

```python
#Создаем декоратор для проверки наличия аутентификации
def authentication_required(func):
    def wrapper(user_authenticated):
        if user_authenticated:
            return func(user_authenticated)
        else:
            print("Ауентификация прошла успешно, пожалуйста зайдите в аккаунт")
    return wrapper

#Функции, которые будут использовать декоратор
authentication_required
def view_profile(user):
    print(f"Просмотр профиля: {user}")

authentication_required
def change_password(user):
    print(f"Смена пароля для пользователя: {user}")
#Функция выполнения декорированных функции
view_profile("Андрей")
change_password(None)
```
### Результат.
![Меню]().

## Выводы
Успешный заход в профиль или же смена пароля

  
## Самостоятельная работа №5
### Создайте собственное исключение, которое будет использоваться в двух любых фрагментах кода. 


```python
#Исключение ошибка входа в аккаунт
class LoginError(Exception):
    def __init__(self, message):
        self.message = message
        super().__init__(message)

#Первое исключение
try:
    username = "Andrey"
    password = "12345"
    if username != "Andrey" or password != "1234567890":
        raise LoginError("Неправильное имя или пароль, повторите снова.")
except LoginError as error:
    print(f"Login Error: {error}")

#Второе исключение
try:
    username = "Andrey"
    password = "1234"
    if username != "Andrey" and password != "1234":
        raise LoginError("Всё верно, вы успешно вошли")
except LoginError as accept:
    print(f"Login Error: {accept}")
```
### Результат.
![Меню]().

## Выводы
Успешный вход или не заход при попытки войти в аккаунт.

## Общие выводы по теме
Разбор декораторов и исключений в Python
