# Тема 8. Введение в ООП.
Отчет по Теме #8 выполнил(а):
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
### Самостоятельно создайте класс и его объект.

```python
#Создание класса цветы
class Flowers: 
    def __init__(self,color):
        self.color=color
#Создание объекта цветы
roses = Flowers(3) 

```
### Результат.
![Меню]().


## Выводы

Успешное выполнение данной задачи

## Самостоятельная работа №2
### Самостоятельно создайте атрибуты и методы для ранее созданного класса.

```python
class Flowers:
    def __init__(self,length,color):
        #создание цвета и длины цветов
        self.color=color
        self.length=length
roses= Flowers("red", 15)
print(roses.color)
print(roses.length)
```
### Результат.
![Меню]().

## Выводы

Успешное выполнение данной задачи
  
## Самостоятельная работа №3
### Самостоятельно реализуйте наследование, продолжая работать ранее созданным классом. 

```python

class Flowers:
    def __init__(self,name):
        self.name=name

#Наследование класса Flowers
class roses(Flowers): 
    def sunpower(self):
        print(f"{self.name} sunpower")

roses = Flowers("Roses")
print(roses.name)


```
### Результат.
![Меню]().

## Выводы

Успешное выполнение данной задачи
  
## Самостоятельная работа №4
### Самостоятельно реализуйте инкапсуляцию

```python
class Flowers:
    def __init__(self, name, color):
        #Название
        self._name = name  
        #Цвет
        self._color = color  
#Метод инкапсуляции
    def sunpower(self):
        print(f" {self._name} sun powering and have {self._color} color")

roses = Flowers("Roses", "red")
print(roses._name)
roses.sunpower()

```
### Результат.
![Меню]().

## Выводы

Успешное выполнение данной задачи
  
## Самостоятельная работа №5
### Самостоятельно реализуйте полиморфизм. 


```python
class Flowers:
    def area(self):
        pass
#Наследование класса Flowers
class Roses(Flowers):  
    def __init__(self, name, color):
        #Название
        self._name = name  
        #Цвет
        self._color = color  
roses = Roses("Rose","Red")

print("Roses name:", roses._name)
print("Roses color:", roses._color )

#Наследование класса Flowers
class Tulipe(Flowers): 
    def __init__(self, length):
        #Длина
        self.length = length  
tulipe = Tulipe(14)
print("Tulipe length:", tulipe.length)

```
### Результат.
![Меню]().

## Выводы

Успешное выполнение данной задачи
  


## Общие выводы по теме
Базовый разбор знаний в ООП, взаимодействий классов и их наследований
