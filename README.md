# Web-версия

Версия документации: 0.1
## Определение материальных свойств композита
1. Сначала нужно создать сетку с разбиением,
соответствующим композиту на странице **Models->Mesh generation**
2. Нужно указать имя модели, число элементов по каждой оси кубического объема
(так, для n = 1 общее число элементов будет 1, для n = 2 - 8, для n = 3 - 64...)
3. Выбрать тип связности: 3-3 VM и 3-3 MV обеспечивают связность по обоим компонентам, 
различные виды 3-0 обеспечивают связность для первой компоненты, а поведение пор меняется в зависимости от разрешения или запрета "слипания".
При запрете можно получить изолированные поры фиксированных размеров или запретить выход пор на поверхность.
4. Для каждого типа связности нужно указать целевой процент включений, а для некоторых - дополнительные параметры (например, размеры пор)
5. Настройка Generation Level отвечает за размер домена в представительном объеме. Чем больше - тем точнее целевые проценты, но тем дольше строится сетка.
6. В списке моделей можно открыть детали (кнопка Stats) и выгрузить сетки в разных форматах. Модели, для
которых получены сетки с близким к целевому процентом включений, отмечаются галочкой, те, для которых генерация не удалась - итоговый процент сильно отличается от целевого - красным восклицательным знаком.\
7. Далее нужно перейти на страницу Models->Solutions и привязать к геометрии материальные свойства.
Для каждой из фаз нужно указать материал из библиотеки материалов и выбрать степени свободы в узлах.
Тип конечного элемента пока менять не нужно.
8. Далее нужно сохранить модель с новым именем, после чего будет открыта страница для задания граничных условий.
9. В качестве решателя рекомендуется выбрать CSparseLU. Для определения свойств материала нужно нажать одну из кнопок:
    **IdentifyElectric** - для электростатической задачи
    **IdentifyElastic** - для упругой задачи
    **IdentifyPiezo** - для пьезоэлектрической задачи
    При идентификации материала самостоятельно писать граничные условия не нужно.
10. После нажатия на кнопку Solve вы увидите (возможно, не сразу) результат решения последней краевой задачи из набора решенных.
Чтобы посмотреть остальные результаты, откройте вкладку Postprocessor, найдите в списке задач свою задачу и нажмите Results
11. Выберите пункт Material Properties Int. и получите матрицы рассчитанных свойств.
12. Вы можете оставить Issue в этом репозитории, если возникли проблемы или вы столкнулись с ошибкой.
13. Чтобы посмотреть на геометрию модели, нужно в разделе PostProcessor нажать на кнопку `Show->Вид модели->Модель`. 


