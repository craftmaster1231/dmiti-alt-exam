# Дискретные задачи многокритериальной оптимизации.

## Несколько понятий.

### Пусть есть множество каких-то объектов. У каждого объекта есть какие-то параметры. Надо выбрать из этого множества лучшие объекты по парметрам. 
### Для каждого параметра надо выбрать, лучший "воображаемый" объект должен минимизировать его, или максимизировать. 
### Множество Парето - такое подмножество объектов, для которых нельзя во всем множестве выбрать объект, который будет лучше по всем параметрам.
    
    На простых примерах: 
    1. Большое и кислое яблоко и маленькое, но сладкое. В случае, когда мы хотим и сладкое и большое яблоко - это множество Парето.
    2. Дорогой, но крепкий телефон и  дешевый, но хрупкий. В случая, когда наша цель минимизировать затраты и максимизироать надежность, - это множество Парето.
    
## Первая программа будет обрабатывать несколько точек и находить среди них множество Парето. 

### *Каков алгоритм?*

У каждой точки будет свой идентификатор, просто номер.

По определению множества Парето,
мне надо проверить для каждой точки,
есть ли точки, которые лучше нее по **всем** параметрам.

*Буду называть такие точки просто теми, которые лучше,
а те, что лучше не по всем параметрам - несравнимыми.*

*Те, что хуже по всем параметрам буду называть худшими 
для другой точки*

Так и сделаю. Для каждой точки проверю все остальные.
Если для какой-то точки нашлась точка лучше,
то она не входит в множество, а если она несравнима 
со всеми, и не хуже никакой, то она входит в множество Парето. 

Таким образом, у меня останутся только те точки, которые
входят в множество Парето.
