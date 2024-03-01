## Тестовое задание Backend/Django для HardQode
## Построение системы для обучения
Суть задания заключается в проверке знаний построения связей в БД и умение правильно строить запросы без ошибок N+1.

### Построение архитектуры(6 баллов)
В этом задании у нас есть три бизнес-задачи на хранение:
1. Создать сущность продукта. У продукта должен быть создатель этого продукта(автор/преподаватель). Название продукта, дата и время старта, стоимость **(1 балл)**
2. Определить, каким образом мы будем понимать, что у пользователя(клиент/студент) есть доступ к продукту. **(2 балл)**
3. Создать сущность урока. Урок может принадлежать только одному продукту.. В уроке должна быть базовая информация: название, ссылка на видео. **(1 балл)**
4. Создать сущность группы. По каждому продукту есть несколько групп пользователей, которые занимаются в этом продукте. Минимальное и максимальное количество юзеров в группе задается внутри продукта. Группа содержит следующую информацию: ученики, которые состоят в группе, название группы, принадлежность группы к продукту **(2 балла)**

### Написание запросов и реализация логики распределения(11 баллов)
В этом пункте потребуется использовать выполненную вами в прошлом задании архитектуру:
1. При получении доступа к продукту, распределять пользователя в группу. Если продукт ещё не начался, то можно пересобрать группы так, чтобы везде было примерно одинаковое количество участников.
   По-умолчанию алгоритм распределения должен работать заполняя до максимального значения **(5 баллов)**.
   **+3 балла** дается за реализацию алгоритма распределения по группам так, чтобы в каждой группе количество участников не отличалось больше, чем на 1. При этом, минимальные и максимальные значения участников в группе должны быть учтены.
2. Реализовать API на список продуктов, доступных для покупки, которое бы включало в себя основную информацию о продукте и количество уроков, которые принадлежат продукту. **(2 балла)**
3. Реализовать API с выведением списка уроков по конкретному продукту к которому пользователь имеет доступ. **(1 балл)**.

### Результат выполнения:
1. Выполненная архитектура на базе данных SQLite с использованием Django.
2. Реализованные API на базе готовой архитектуры.

#### Если вы все сделали, но хотите еще, то можете реализовать API для отображения статистики по продуктам.
Необходимо отобразить список всех продуктов на платформе, к каждому продукту приложить информацию:
1. Количество учеников занимающихся на продукте.
2. На сколько % заполнены группы? (среднее значение по количеству участников в группах от максимального значения участников в группе).
3. Процент приобретения продукта (рассчитывается исходя из количества полученных доступов к продукту деленное на общее количество пользователей на платформе).
_За это задание не ставится баллов, но при выборе между 2 кандидатами - оно нам поможет._
