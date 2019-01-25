# Overview Page Example for Fiori Elements Workshop (RU)

## 1. Создание проекта
Создаем проект по шаблону **OVP**, выбираем фильтр по коллекции `Orders`.
Используем OData-сервис https://services.odata.org/V2/Northwind/Northwind.svc

## 2. List Card
Добавим в проект базовые аннотации. Теперь через визард добавим **List Card**, где выведем список последних заказов (сервис обновлялся 20 лет назад, так что информация максимально полезная). Информацию в список можно добавлять с помощью `DataField`. Также можно использовать `DataPoint`, которые можно подсветить аннотациями `Criticality`. Добавим несколько `DataField` и `DataPoint`.
В **Extended List** помещается до трех элементов, в **Condenced** - до шести. Порядок расположения такой - если есть `DataPoint`, он располагается в правой колонке сверху. Остальные слоты равномерно заполняются `DataField`. 

## 3. Analytical Card
Добавим карточку с графиком по продажам. Будем работать с коллекцией `Summary_of_Sales_by_Year`. Добавим на нее аннотацию `Chart`. `MeasureAttribute` - `Subtotal`, `DimensionAttribute` - `ShippedDate`. Чтобы уменьшить количество отображаемых столбцов добавим аннотацию `PresentationVariant` со свойством `MaxItems`. Чтобы аннотация `PresentationVariant` заработала, нужно добавить в `manifest` поле `presentationAnnotationPath` со ссылкой на `Qualifier` нашего `PresentationVariant`. Тоже самое нужно сделать с `Chart`, в `manifest` это свойство `chartAnnotationPath`.

## 4. Table Card
Добавим карточку с таблицей. Создаем ее через визард и прописываем `LineItem` c `DataField` для каждой колонки. Чтобы отображались заголовки колонок, каждому `DataField` нужно добавить `Label`.