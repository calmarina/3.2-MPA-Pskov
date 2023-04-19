# 3.2-MPA-OKN-Pskov
## Состав команды 
Студенты БГП191
1. Арина Андреева
2. Юлия Веденина 
3. Кира Захарова
4. Эмиль Тулиганов
## Карта ОКН 
ссылка
## Краткая информация о городе:
Псков — один из старейших городов России, который был основан в 903 году княгиней Ольгой на слияния двух рек Великая и ПсковА. А между ними на возвышенности располагается главная и одна из старейших достопримечательностей – ансамбль Псковского кремля. В целом, большинство объектов культурного наследия располагаются на правом берегу реки Великой в исторической части города. Практически все они сконцентрированы в стенах окольного города – исторического Кремля, которые сейчас практически полностью разрушены, но остаются в парках и на центральных улицах, как историческая память, объекты культурного наследия, придавая городу ещё более исторических антураж. В Пскове проживает около 200 тыс. жителей, но население ежегодно уменьшается из-за сильного влияния и притяжения более крупных, современных и развитых городов – Москвы и Санкт-Петербурга. При этом Псков ежегодно входит в рейтинги самых популярных направлений для туризма (бюджетного и исторического). За последние годы город преобразился в лучшую сторону, были отреставрированы многие здание, однако даже в центральной части города есть объекты, которые рушатся от старости несмотря на то, что являются ОКНами. В Пскове располагается 10 объектов всемирного наследия Юнеско, а также в городе располагается более 50 религиозных объектов (церквей, храмов и соборов), которыми очень славится Псковский регион.
## Описание используемых данных с указанием источников:
Первостепенно мы обратились к выгрузке всех данных по Пскову с сайта https://extract.bbbike.org/. Используемые слои: buildings, только полигоны. Затем воспользовались OSM и Яндекс.картами для уточнения ряда объектов при очистке данных. Слой с точками ОКН, который был приложен в инструкции. Архив с границами субъектов РФ для оформления карты и данных в границах города.
## Описание основных методов
1. Работа с данными OSM: 
- выгрузка слоя со зданиями
- очистка от некорректной геометрии с помощью Fix geometry
2. Работа с данные ОКН:
- импорт таблицы с данными по ОКН в слой Qgis;
- очистка атрибутивной таблицы от пустых полей;
- привязка точек ОКН к слою полигонов зданий через Join attributes by location;
- разделение зданий-ОКН и обычных зданий через Select by location.
3. Работа с веб-картографированием на Python:
- создана сетка, по которой была рассчитана плотность ОКН
- создана карта с помощью библиотеки Folium.
- на карту добавлены полигоны ОКН-зданий и точки ОКН, не являющихся зданиями;
- созданы кластеры точек
- добавлен функционал отслеживания позиции курсора
- добавлен функционал разворачивания карты в полноэкранный режим
- добавлен функционал поиска ОКН по всем объектам на карте
- добавлен функционал переключения слоёв точек и кластеров.
## Что было самым сложным в работе?
Работа с новыми библиотеками в программе, а также их установка. В процессе работы возникло много проблем с установкой библиотек, так как программа вылетала из-за их количества и часто выдавала ошибки в работе. Также было несколько муторно синхронизировать директории всех используемых файлов.
## Что получилось в работе и вы можете этим гордиться?
В результате мы достигли цели, к которой стремились. Получилось отобразить все объект ОКН и их плотность на карте. Мы разделили и отобразили данные по типам в зависимости от привязки к зданиям (полигоны и точки), получилось внедрить в карту поиск по названиям как точек, так и зданий. Также настроено отображение объектов и их кластеров в зависимости от масштаба.
## Что не получилось и почему (опционально)
Возможно из-за ограничений Folium, не получилось сделать единый поиск по зданиям и точкам, только по отдельности. Мы пытались, но у нас не получилось. P.S. была идея сделать один невидимый слой с точками для настройки этого поиска, но что-то пошло не так. 
