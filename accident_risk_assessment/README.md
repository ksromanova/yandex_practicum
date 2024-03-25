## Описание проекта

Для каршеринговой компании необходимо создать систему, оценивающую риск ДТП по выбранному маршруту. Риск в данном случае - это вероятность ДТП с любым повреждением транспортного средства (ТС). После того как водитель забронировал ТС, селд за руль и построил маршрут, система должна оценить уровень риска. Если уровень риска высок, водитель увидит предупреждение и рекомендации по маршруту.

Идея данной системы в на момент начала этого проекта была на стадии обчуждения и проработки, а четких алгоритмов работы и аналогичных решений на рынке не существовало.

**Задача** - понять, возможно ли предсказать ДТП, основываясь на иторических данных одного из регионов.

Предложения заказчика по решению данной задачи:

* Создать модель предсказания ДТП. Целевой признак - `at_fault` (таблица `parties`).
        - Тип виновника для модели - только машина "car";
        - Выбрать случаи, когда ДТП привело к любым повреждениям транспортного средства, кроме типа "SCRATCH" (царапина);
        - Необходимо ограничитьсчя данными за 2012 год - они самые свежие;
        - Обязательное условие - учесть фактор возраста автомобиля. 
* На основе модели исследовать основные факторы ДТП
* Понять, могут ли результаты моделирования и анализ важности факторов ответить на вопросы:
        - Можно ли создать адекватную состему оценки водительского риска при выдаче авто?
        - Какие еще факторы надо учесть?
        - Нужно ли оборудовать авто какими-либо датчиками и камерой?

Шаги выполнения исследовательского проекта:

1. Загрузить таблицы SQL

2. Провести первичное исследование таблиц

        - Все ли таблицы имеют набор данных?
        - Соответствует ли количество таблиц условию задачи?
        - Имеется ли общий ключ для связи таблиц
        
3. Провести статистический анализ факторов ДТП.

       3.1 Выяснить в какие месяцы происходит наибольшее количество аварий. Проанализировать весь период наблюдений (таблица `collisions`)
       
            - Создать SQL-запрос
            - Построить график
            - Сделать вывод
            
       3.2 Первое совещание рабочей группы скоро состоится. Чтобы обсуждение было конструктивным, каждый сотрудник должен понимать данные. Для этого необходимо создать подходящие аналитические задачи и поручить их решение коллегам. Примеры задач:

            - Провести анализ серьёзности повреждений транспортного средства, исходя из состояния дороги в момент ДТП 
            (связать collisions и parties);
            - Найти самые частые причины ДТП (таблица parties).

           3.2.1 Создать не менее шести задач для коллег, опираясь на примеры и таблицы. 
           3.2.2 Прописать порядок решения для двух задач из списка. Обязательное условие — решение этих задач должно включать связь не менее 2-х таблиц.

4. Создать модель для оценки водительского риска. 
    
       4.1 Подготовить набор данных на основе первичного предположения заказчика:

            - Выбрать тип виновника — только машина (car).
            - Взять случаи, когда ДТП привело к любым значимым повреждениям автомобиля любого из участников —
            все, кроме типа SCRATCH (царапина).
            - Для моделирования взять данные только за 2012 год.
            - Подготовка исходной таблицы должна проводиться с помощью sql-запроса.
            
       4.2 Провести первичный отбор факторов, необходимых для модели.
       
            Изучить описание факторов. Нужно отобрать те, которые могут влиять на вероятность ДТП. Лучше, если выбор будет аргументирован.
            
       4.3 Провести статистическое исследование отобранных факторов.
       
            - По результату исследовательского анализа внести корректировки, если они нужны. Сделать вывод.
            - Если необходимо, категоризировать исходные данные, провести масштабирование.
            - Подготовить обучающую и тестовую выборки.

5. Найти лучшую модель.

       5.1 Смоделировать не менее 3-х типов моделей с перебором гиперпараметров
       5.2 Выбрать метрику для оценки модели, исходя из поставленной бизнесом задачи. Обосновать свой выбор.
       5.3 Оформить вывод в виде сравнительной таблицы.

6. Проверить лучшую модель в работе.

       6.1 Провести графический анализ «Матрица ошибок». Вывести полноту и точность на график.
       6.2 Проанализировать важность основных факторов, влияющих на вероятность ДТП. 
       6.3 Для одного из выявленных важных факторов провести дополнительное исследование:

        - Показать график зависимости фактора и целевой переменной.
        - Предложить, чем можно оборудовать автомобиль, чтобы учесть этот фактор во время посадки водителя.

7. Сделать общий вывод по модели.
        
       7.1 Кратко описать лучшую модель.
       7.2 Сделать вывод: насколько возможно создание адекватной системы оценки риска при выдаче авто?
       7.3 Какие факторы ещё необходимо собирать, чтобы улучшить модель?

**Краткое описание таблиц**

* `collisions` — общая информация о ДТП

Имеет уникальный `case_id`. Эта таблица описывает общую информацию о ДТП. Например, где оно произошло и когда.

* `parties` — информация об участниках ДТП

Имеет неуникальный `case_id`, который сопоставляется с соответствующим ДТП в таблице `collisions`. Каждая строка здесь описывает одну из сторон, участвующих в ДТП. Если столкнулись две машины, в этой таблице должно быть две строки с совпадением `case_id`. Если нужен уникальный идентификатор, это `case_id` и `party_number`.

* `vehicles` — информация о пострадавших машинах

Имеет неуникальные `case_id` и неуникальные `party_number`, которые сопоставляются с таблицей `collisions` и таблицей `parties`. Если нужен уникальный идентификатор, это `case_id` и `party_number`.

"**Используемые библиотеки:**"
**Используемые библиотеки:**
- [calendar](https://docs.python.org/3/library/calendar.html)
- [datetime](https://docs.python.org/3/library/datetime.html)
- [time](https://docs.python.org/3/library/time.html)
- [sqlalchemy.create_engine](https://docs.sqlalchemy.org/en/21/core/engines.html)

- [numpy](https://numpy.org/)
- [pandas](https://pandas.pydata.org/)
- [scipy.stats.randint](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.randint.html)
- [scipy.stats.spearmanr](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.spearmanr.html)

- [matplotlib](https://matplotlib.org/)
- [seaborn](https://seaborn.pydata.org/)

- [sklearn.ensemble.RandomForestClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html)
- [sklearn.feature_extraction.text.TfidfVectorizer](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html)
- [sklearn.impute.SimpleImputer](https://scikit-learn.org/stable/modules/generated/sklearn.impute.SimpleImputer.html)
- [sklearn.metrics.confusion_matrix](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.confusion_matrix.html)
- [sklearn.metrics.f1_score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.f1_score.html)
- [sklearn.metrics.precision_score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.precision_score.html)
- [sklearn.metrics.recall_score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.recall_score.html)
- [sklearn.metrics.roc_auc_score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.roc_auc_score.html)
- [sklearn.model_selection.GridSearchCV](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html)
- [sklearn.model_selection.RandomizedSearchCV](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.RandomizedSearchCV.html)
- [sklearn.model_selection.train_test_split](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.train_test_split.html)
- [sklearn.preprocessing.OneHotEncoder](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.OneHotEncoder.html)
- [sklearn.preprocessing.StandardScaler](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html)
- [sklearn.tree.DecisionTreeClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html)

- [catboost](https://catboost.ai/)
- [lightgbm](https://lightgbm.readthedocs.io/en/latest/)
- [optuna](https://optuna.org/)

- [plotly.express](https://plotly.com/python/plotly-express/)
- [plotly.figure_factory](https://plotly.com/python/figure-factory/)
- [plotly.graph_objs](https://plotly.com/python/graph-objects/)
- [plotly.offline.iplot](https://plotly.com/python/offline/)
- [plotly.offline.init_notebook_mode](https://plotly.com/python/offline/)