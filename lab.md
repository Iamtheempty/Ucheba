# Тема 9. Концепции и принципы ООП.
Отчет по Теме #9 выполнил(а):
- Галеев Андрей Назарович
- ИНО ЗБ ПОАС-22-1

| Задание |  Сам_раб |
| ------ |  ------ |
| Задание 1 | + |


знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Самостоятельная работа №1
### Задание с помидорами

```python
#Создание класса Томаты
class Tomato: 
    states = {'Семяна': 0, 'Цветение': 1, 'Зреет': 2, 'Спелый': 3}
    def __init__(self, index):  
        self._index = index
        self._state = self.states['Семяна']

    def grow(self):  
        if self._state < 3:
            self._state += 1

    def is_ripe(self):
        return True if self._state == 3 else False
#Создание класса Томантный куст
class TomatoBush:  

    def __init__(self, num):
        self.tomatoes = [Tomato(index) for index in range(1, num + 1)]

    def grow_all(self):
        for tomato in self.tomatoes:
            tomato.grow()
#Функция проверки помидоров на зрелость
    def all_are_ripe(self): 
        return all([tomato.is_ripe() for tomato in self.tomatoes])

    def give_away_all(self):
        self.tomatoes = []

#Создание класса Садовник
class Gardener:  

    def __init__(self, name, plant):
        self.name = name
        self._plant = plant

    def work(self):
        self._plant.grow_all()
#Функция проверки сбора зрелых помидоров
    def harvest(self): 
        if self._plant.all_are_ripe():
            print('Урожай собран!')
            self._plant.give_away_all()
        else:
            print('Томаты еще не дозрели')
#Функция справки по садовоству
    @staticmethod
    def knowledge_base():
        print('Справка по садоводству:')
        print('1. Не забывайте регулярно поливать и подкармливать растения')
        print('2. Определите правильное расстояние между растениями, чтобы они не мешали друг другу в росте')
        print('3. Удалите поврежденные листья и плоды, чтобы предотвратить распространение болезней')
    
Gardener.knowledge_base()
#Создание объектов классов для Томатного куста и Садовника
bush = TomatoBush(5)
gardener = Gardener('Andrew', bush)
gardener.work()
gardener.work()
gardener.work()

def harvest_tomatoes(unripe=True):
    if unripe:
        print("Попробуйте собрать урожай, когда томаты дозреют")
    else:
        print("Томаты уже спелые, можно начинать сбор урожая")

#Фунция проверки на сбор урожая, когда томаты еще не спелые
harvest_tomatoes(unripe=True)

#Фунция сбора урожая
gardener.harvest()
#Фунция ухода за кустом, пока томаты не дозреют
gardener.work()
gardener.harvest()
gardener.work()
#Фунция сбора урожая после дозревания всех томатов
gardener.work()
gardener.harvest()
```
### Результат.
![Меню]().


## Выводы

Данная задача была успешно выполнена
