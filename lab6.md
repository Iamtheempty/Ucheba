# Тема 6. Базовые коллекции: словари, кортежи.
Отчет по Теме #6 выполнил(а):
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
### При создании сайта у вас возникла потребность обрабатывать данные пользователя в странной форме, а потом переводить их в нужные вам форматы.

```python
#Ввод данных
user_input = input("Введите последовательность чисел, разделенных пробелом: ")

#Разбиваем введенную строку на отдельные числа
numbers = user_input.split()

numbers_list = list(map(int, numbers))
numbers_tuple = tuple(map(int, numbers))

print("Список из введенных чисел:", numbers_list)
print("Кортеж из введенных чисел:", numbers_tuple)
```
### Результат.
![Меню]().


## Выводы

Успешная работа данной задачи

## Самостоятельная работа №2
### Николай знает, что кортежи являются неизменяемыми, но он очень упрямый и всегда хочет доказать, что он прав. 

```python
def remove_first_element(tup, element):
    if element in tup:
        index = tup.index(element)
        new_tup = tup[:index] + tup[index+1:]
        return tuple(new_tup)
    return tup

#Примеры входных данных и ожидаемых результатов
inputs = [(1, 2, 3, 1), (1, 2, 3, 1, 2, 3, 4, 5, 2, 3, 4, 2, 4, 2), (2, 4, 6, 6, 4, 2)]
elements = [1, 3, 9]

#Проход по каждому примеру
for idx, tup in enumerate(inputs):
    element = elements[idx]
    result = remove_first_element(tup, element)
    print(f"Для входных данных {tup} и элемента {element}: {result}")
```
### Результат.
![Меню]().

## Выводы

Успешная работа данной задачи

  
## Самостоятельная работа №3
### Ребята поспорили кто из них одним нажатием на numpad наберет больше повторяющихся цифр, но не понимают, как узнать победителя. 

```python
from collections import Counter
def most_common_numbers(digits_str):
    digits_count = Counter(digits_str)
    most_common = digits_count.most_common(3)
    top3_most_common = {int(num): count for num, count in most_common}

    return dict(sorted(top3_most_common.items()))

digits_string = "66853865856274276"

result_dict = most_common_numbers(digits_string)


for key in sorted(result_dict.keys()):
    print(f"Цифра: {key}, Количество: {result_dict[key]}")
```
### Результат.
![Меню]().

## Выводы

Успешная работа данной задачи
  
## Самостоятельная работа №4
### Ваш хороший друг владеет офисом со входом по электронным картам, ему нужно чтобы вы написали программу, которая показывала в каком порядке сотрудники входили и выходили из офиса. 

```python
def find_employee_records(records, employee_id):
    start_index = -1
    end_index = -1
    count = 0
    for i, record in enumerate(records):
        if record == employee_id:
            count += 1
            if count == 1:
                start_index = i
            if count == 2:
                end_index = i

    if start_index == -1:
        return ()
    if end_index == -1:
        return records[start_index:]

    return records[start_index:end_index + 1]
#Пример
print(find_employee_records((1, 2, 3, 4),8)) 
print(find_employee_records((1, 8, 3, 4, 8, 8, 6, 2),8,)) 
print(find_employee_records((1, 3, 8, 5, 1, 2, 7), 8))
```
### Результат.
![Меню]().

## Выводы

Успешная работа данной задачи
  
## Самостоятельная работа №5
### Напишите код, который будет сортировать список товаров на складе, оставляя только товар в наличии 

```python
#Функция сортировки товара, который остался на складе после отгрузки
def sort(incoming_goods, outgoing_goods):
    inventory = []
    for item in incoming_goods:
        if item not in outgoing_goods:
            inventory.append(item)
    return inventory


first = ["Book", "Laptop", "Chair", "Table"]
out1 = ["Chair", "Laptop"]
assert sort(first , out1) == ["Book", "Table"]

two = ["Phone", "Smartphone", "Recorder"]
out2 = ["Phone", "Recorder"]
assert sort(two, out2 ) == ["Smartphone"]

three = ["AppleGlass", "Earphones", "Mouse","Keyboard"]
out3 = ["Keyboard", "Earphones"]
assert sort(three, out3) == ["AppleGlass", "Mouse"]
```
### Результат.
![Меню]().

## Выводы

Товар отсортирован и тесты пройдены

## Общие выводы по теме
Подробное изучение работы в Python, сортировка кортежей и списков.
