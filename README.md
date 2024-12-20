## Домашнее задание 3
Демонстрация SOLID принципов

### Цель:
Практическое применение SOLID принципов.


### Описание/Пошаговая инструкция выполнения домашнего задания:
- На примере реализации игры «Угадай число» продемонстрировать практическое применение SOLID принципов.
- Программа рандомно генерирует число, пользователь должен угадать это число.
- При каждом вводе числа программа пишет больше или меньше отгадываемого.
- Кол-во попыток отгадывания и диапазон чисел должен задаваться из настроек.


### Отчет по выполнению ДЗ
- Выполнил в стилистике чистой архитектуры, но всё в одном проекте, разнес элементы  по папкам.
- Использование SOLID принципов:
  - **SRP** - постарался  сделать так что бы в каждом классе был функционал связанный только с одним элементом (или действием), другими словами  у класса была только одна причина для изменения.
  **Пример**: Класс *RandomNumberGeneratorService* занимается только генерацией рандомных чисел, и единственная причина для его изменения - изменение логики рандомайзера.
  - **OCP** - програмные сущности открыты для расшинения, закрыты для изменения.
  Это реализовано за счет повсеместной инъекции зависимостей, т.е. передачи интерфейсов в классы, а не конкретных объектов.
  **Пример**: В класс *GameService* передается *IRandomGeneratorService* и если например для тестов нужно использовать другой генератор, класс *GameService* не нужно менять.
  - **LSP** - один из вариантов определения для этого принципа, который мне понравился, звучик так:
  "подкласс не должен требовать от вызывающего кода больше, чем базовый класс, и не должен предоставлять вызывающему коду меньше, чем базовый класс"
  В коде в папке LSP попробовал продемонстрировать нарушение данного принципа.
  Класс *RandomNumberGeneratorService_LSP_violation* наследует от *RandomNumberGeneratorService_Base* при этом требует большего от вызываюего кода чем базовый класс - нужно в конструктор передавать данные. При этом предоставляет меньше базового класса - метод Generate не работает, а выдает исключение.
  - **ISP** -  интерфейсы не содержат методы, которые не нужны тем классам, которые их реализуют.
  Для примера создал  интерфейс   *IBaseGameService* который содержит только методы начать и  закончить игру.
  - **DIP** - принцип инверсии зависимостей достигается за счёт того что модули верхних уровней не зависят от модулей нижних уровней. Оба типа модулей зависят от абстракций.
 Везда в классы верхнего уровня происходит инъекция абстракций (т.е. модули верхнено уровня зависят от абстаркций), а модули нижнего уровня реализуют интерфейсы (т.е. модули нижнего уровня тоже зависят от абстракций)



  
