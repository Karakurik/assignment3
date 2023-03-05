# ADT и здание
1. Отразить в ADT следующую предметную область:
    1. Здание. У здания есть строковый адрес и этажи (ссылка на 1-й этаж)
    1. Этаж бывает жилым, чердаком или коммерческим
    1. У каждого жилого этажа есть 2 постояльца и лестница на следующий этаж (просто ссылка на этаж)
    1. У каждого коммерческого этажа есть несколько заведений (минимум 1) и лестница на следующий этаж (да, в этом доме можно открыть свою кальянную на 5 этаже, даже если всего этажей 10 :kekw:)
    1. Чердак может быть обычным, либо тоже коммерческим, но только с 1 заведением.
    1. У постояльца есть возраст (>0) и пол (м/ж).
1. При создании здания необходимо убедиться, что все входные данные не нарушают логику обозначенной модели. Иначе, возвращать соответствующий тип ошибки (на разные невалидные параметры разный тип ошибки). Использование функции `require` запрещено. 
1. Реализовать функцию `fold` аккумулирующую целое число во время обхода здания. На каждом этаже аккумулируемое значение пересчитывается с помощью функции `f`, параметрами которой служат текущее значение аккумулятора и этаж (Первый параметр, это текущий аккумулятор. Второй, текущий этаж)
Здание обходить снизу вверх. Аккумулятор изначально равен `accumulator`. Вы можете менять сигнатуру типов в fold, если посчитаете это необходимым.
    ```scala
    def fold(building: Building, accumulator: Int)(f: (Int, ResidentialFloor) => Int): Int = ???
    ```
1. Используя функцию `fold` посчитать количество этажей, где есть хотя бы один мужчина старше `olderThan`
(если нет таких, то 0)
    ```scala
    def countOldManFloors(building: Building, olderThan: Int): Int = ???
    ```
1. Используя функцию `fold` посчитать максимальный возраст женщины в здании
(если нет женщин, то 0)
    ```scala
    def womanMaxAge(building: Building): Int = ???
    ```
1. Используя функцию `fold` посчитать кол-во коммерческих заведений в здании (если нет, то 0)
    ```scala
    def countCommercial(building: Building): Int = ???
    ```
1. Используя свою собственную функцию, похожую на `fold`, посчитать среднее кол-во коммерческих заведений в зданиях (если нет, то 0). Если знаете, как работать с тайп параметрами в функциях, то можно изменить сигнатуру самой функции `fold`, и использовать ее.
    ```scala
    def countCommercial(building: Array[Building]): Double = ???
    ```
1. Используя свою собственную функцию, похожую на `fold`, посчитать среднее кол-во мужчин на четных этажах (если нет, то 0)
    ```scala
    def evenFloorsMenAvg(building: Building): Double = ???
    ```
1. Напишите тесты в BuildingSpec.scala. На функцию fold отдельные тесты писать не обязательно
