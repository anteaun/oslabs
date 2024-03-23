# Приложение для создания и обработки матричных теоретико-игровых моделей
Данное приложение позволяет создавать матричную модель игры (как вручную, так и загрузкой из файла) детально ее настраивать, обрабатывать матрицу с помощью различных алгоритмов решения матричный игр, выгружать матрицу в файл. Также реализована поддержка истории изменений. На скриншоте представлен общий интерфейс, а далее следует обзор всех конкретных возможностей приложения.\\
![interface](https://github.com/vsmpei/mpei-sm-lab1/tree/master/Images/interface.png)
## Создание модели
При ручном создании модели нужно указать имена игроков и количество стратегий каждого игрока. Будет создана матрица, в которой пока нет названий стратегий, а все веса равны нулю.
|Элемент приложения|Результат работы|
|:-:|:-:|
|![create](https://github.com/vsmpei/mpei-sm-lab1/tree/master/Images/create.png)|![create_m](https://github.com/vsmpei/mpei-sm-lab1/tree/master/Images/create_m.png)|
## Настройка модели
### Задание стратегий
Для ручного задания стратегии нужно указать имя игрока, номер новой стратегии и ее название. 
|Элемент приложения|Результат работы|
|:-:|:-:|
|![strategy](https://github.com/vsmpei/mpei-sm-lab1/tree/master/Images/strategy.png)|![strategy_m](https://github.com/vsmpei/mpei-sm-lab1/tree/master/Images/strategy_m.png)|
### Добавление весов
Для ручного добавления весов нужно указать названия стратегий обоих игроков, образующих ситуацию, и значение веса - выигрыш первого игрока в этой ситации. 
|Элемент приложения|Результат работы|
|:-:|:-:|
|![weight](https://github.com/vsmpei/mpei-sm-lab1/tree/master/Images/weigth.png)|![weigth_m](https://github.com/vsmpei/mpei-sm-lab1/tree/master/Images/weigth_m.png)|
## Решение игры
### Поиск максимина и минимакса
Принцип максимина - максимизация своего результата при наихудшем (для себя) выборе соперника. Максимин ищется для первого игрока. Для второго игрока ищется минимакс - обратный максимину. При совпадении максимина и минимакса это значение явлется седловой точкой, и ситуация считается возможным решением игры. В данном примере максимин и минимакс равны -4, и решением игры считается ситуация (Действие 3; Действие 2).
|Матрица игры|Результат решения|
|:-:|:-:|
|![maxmin_m](https://github.com/vsmpei/mpei-sm-lab1/tree/master/Images/maxmin_m.png)|![maxmin](https://github.com/vsmpei/mpei-sm-lab1/tree/master/Images/maxmin.png)|
### Удаление строго доминируемых стратегий
Принцип удаления строго доминируемых стратегий заключается в том, что игрок исключает стратегию, выигрыши которой в каждой ситуации меньше, чем в хотя бы одной другой стратегии. Последовательное поочередное исключение таких стратегий может привести к решению игры. В данном примере у каждого игрока последовательно дважды исключаются строго доминируемые стратегии, что приводит к решению игры в ситуации (Действие 2; Действие 1).  
|Начальная матрица|Первая итерация|Вторая итерация|
|:-:|:-:|:-:|
|![strogo_1](https://github.com/vsmpei/mpei-sm-lab1/tree/master/Images/strogo_1.png)|![strogo_2](https://github.com/vsmpei/mpei-sm-lab1/tree/master/Images/strogo_2.png)|![strogo_3](https://github.com/vsmpei/mpei-sm-lab1/tree/master/Images/strogo_3.png)|
### Удаление слабо доминируемых стратегий
Принцип удаления слабо доминируемых стратегий заключается в том, что игрок исключает стратегию, выигрыши которой в каждой ситуации меньше либо равны выигрышам в хотя бы одной другой стратегии. Последовательное поочередное исключение таких стратегий может привести к решению игры. В данном примере у каждого игрока последовательно дважды исключаются слабо доминируемые стратегии, что приводит к решению игры в ситуации (Действие 2; Действие 1).  
|Начальная матрица|Первая итерация|Вторая итерация|
|:-:|:-:|:-:|
|![slabo_1](https://github.com/vsmpei/mpei-sm-lab1/tree/master/Images/slabo_1.png)|![slabo_2](https://github.com/vsmpei/mpei-sm-lab1/tree/master/Images/slabo_2.png)|![slabo_3](https://github.com/vsmpei/mpei-sm-lab1/tree/master/Images/slabo_3.png)|

