# Тема 7. Работа с файлами (ввод, вывод).
Отчет по Теме #7 выполнил(а):
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
### Найдите в интернете любую статью (объем статьи не менее 200 слов), 

```python
from collections import Counter
import re

with open('Cryone.txt') as file:
    data = file.read()

#Преобразование текста в список слов
words = re.findall(r'\w+', data.lower())

word_count = len(words)

word_freq = Counter(words)
most_common_word = word_freq.most_common(1)[0][0]
print(f"Количество слов в статье: {word_count}")
print(f"Самое часто встречающееся слово: {most_common_word}")

```
### Результат.
![Меню]().


## Выводы

Успешное выполнение данной задачи.

## Самостоятельная работа №2
### У вас появилась потребность в ведении книги расходов,

```python
def add_expense(date, category, amount):
    with open('expenses.txt', 'a') as file:
        file.write(f"{date},{category},{amount}\n")
    print("Расход успешно добавлен.")


def display_expenses():
    with open('expenses.txt', 'r') as file:
        for line in file:
            print(line.strip())


open('expenses.txt', 'a').close()

while True:
    print("1. Добавить расход")
    print("2. Вывести все расходы")
    print("3. Выход")

    choice = input("Выберите действие: ")

    if choice == '1':
        date = input("Введите дату расхода: ")
        category = input("Введите категорию расхода: ")
        amount = input("Введите сумму расхода: ")

        add_expense(date, category, amount)

    elif choice == '2':
        print("Существующие расходы:")
        display_expenses()

    elif choice == '3':
        break
```
### Результат.
![Меню]().

## Выводы

Успешное выполнение данной задачи.
  
## Самостоятельная работа №3
### Имеется файл input.txt с текстом на латинице. 

```python
def count_statistics(file_path):
    with open(file_path, 'r') as file:
        text = file.read()

        letters_count = sum(1 for char in text if char.isalpha() and char.isascii())

        words_count = len(text.split())

        lines_count = text.count('\n') + 1  

        print(f"Input file contains: \n {letters_count} letters,\n {words_count} words, \n {lines_count} lines.")


file_path = 'input.txt'
count_statistics(file_path)

```
### Результат.
![Меню]().

## Выводы

Успешное выполнение данной задачи.
  
## Самостоятельная работа №4
### Напишите программу, которая получает на вход предложение, выводит его в терминал

```python
def censor_sentence(sentence, banned_words):
    censored_sentence = sentence
    for word in banned_words:
        censored_sentence = censored_sentence.replace(word, '*' * len(word))
        censored_sentence = censored_sentence.replace(word.capitalize(), '*' * len(word))
        censored_sentence = censored_sentence.replace(word.upper(), '*' * len(word))
        censored_sentence = censored_sentence.replace(word.lower(), '*' * len(word))
    return censored_sentence

with open('input.txt', 'r') as file:
    banned_words = file.read().split()

input_sentence = input("Введите предложение: ")
censored_output = censor_sentence(input_sentence, banned_words)
print(censored_output)
```
### Результат.
![Меню]().

## Выводы

Успешное выполнение данной задачи.
  
## Самостоятельная работа №5
### Напишите программу, которая будет изменять слова Cry в строках на Funny и запишет в отдельный текстовой файл на выходе


```python
with open('Cryone.txt', 'r') as file:
    lines = file.readlines()

#Заменяем все слова "Сry" на "Funny"
liness = [line.replace('Сry', 'Funny') for line in lines]

#Создание файла для записи
with open('Crytwo.txt', 'w') as file:
#Записываем измененные строки в файл
    file.writelines(liness))

```
### Результат.
![Меню]().

## Выводы

Успешное выполнение данной задачи.
  


## Общие выводы по теме
Работа с текстовыми файлами в Python, их сортировка.
