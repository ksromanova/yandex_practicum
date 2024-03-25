# Описание проекта
Сервис по продаже автомобилей с пробегом «Не бит, не крашен» разрабатывает приложение для привлечения новых клиентов. В нём можно быстро узнать рыночную стоимость своего автомобиля. В вашем распоряжении исторические данные: технические характеристики, комплектации и цены автомобилей. Вам нужно построить модель для определения стоимости. 

Заказчику важны:

- качество предсказания;
- скорость предсказания;
- время обучения.
## Описание проекта

Сервис по продаже автомобилей с пробегом «Не бит, не крашен» разрабатывает приложение, чтобы привлечь новых клиентов. В нём можно будет узнать рыночную стоимость своего автомобиля. 
Необходимо построить модель, которая умеет её определять. Имеются данные о технических характеристиках, комплектации и ценах других автомобилей.

**Критерии, которые важны заказчику:**

* качество предсказания;
* время обучения модели;
* время предсказания модели.

**Основные шаги:**

* Загрузить данные, путь к файлу: /datasets/autos.csv.
* Изучить данные. Заполнить пропущенные значения и обработать аномалии в столбцах. Если среди признаков имеются неинформативные, удалить их.
* Подготовить выборки для обучения моделей.
* Обучить разные модели, одна из которых — LightGBM, как минимум одна — не бустинг. Для каждой модели попробовать разные гиперпараметры.
* Проанализировать время обучения, время предсказания и качество моделей.
* Опираясь на критерии заказчика, выбрать лучшую модель, проверить её качество на тестовой выборке.

**Примечания:**

- Применить метрику RMSE для оценки качества моделей.
- Значение метрики RMSE должно быть меньше 2500.
- Построить LightGBM модель.
- Получить время выполнения ячейки кода Jupyter Notebook специальной командой.
- Изменить только два-три параметра у модели градиентного бустинга, так как она может долго обучаться.
- Если Jupyter Notebook перестанет работать, удалить лишние переменные оператором del:
`del features_train`

**Описание данных**

Данные находятся в файле /datasets/autos.csv.

*Признаки:*

* `DateCrawled` — дата скачивания анкеты из базы
* `VehicleType` — тип автомобильного кузова
* `RegistrationYear` — год регистрации автомобиля
* `Gearbox` — тип коробки передач
* `Power` — мощность (л. с.)
* `Model` — модель автомобиля
* `Kilometer` — пробег (км)
* `RegistrationMonth` — месяц регистрации автомобиля
* `FuelType` — тип топлива
* `Brand` — марка автомобиля
* `Repaired` — была машина в ремонте или нет
* `DateCreated` — дата создания анкеты
* `NumberOfPictures` — количество фотографий автомобиля
* `PostalCode` — почтовый индекс владельца анкеты (пользователя)
* `LastSeen` — дата последней активности пользователя

*Целевой признак:*
`Price` — цена (евро)

"**Используемые библиотеки:**"
- [catboost](https://catboost.ai/)
- [datetime](https://docs.python.org/3/library/datetime.html)
- [lightgbm](https://lightgbm.readthedocs.io/en/latest/)
- [scipy.stats.spearmanr](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.spearmanr.html)
- [sklearn.ensemble.RandomForestClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html)
- [sklearn.impute.SimpleImputer](https://scikit-learn.org/stable/modules/generated/sklearn.impute.SimpleImputer.html)
- [sklearn.model_selection.GridSearchCV](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html)
- [sklearn.metrics.mean_squared_error](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.mean_squared_error.html)
- [sklearn.model_selection.train_test_split](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.train_test_split.html)
- [sklearn.preprocessing.OneHotEncoder](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.OneHotEncoder.html)
- [sklearn.tree.DecisionTreeClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html)
- [matplotlib](https://matplotlib.org/)
- [numpy](https://numpy.org/)
- [optuna](https://optuna.org/)
- [pandas](https://pandas.pydata.org/)
- [plotly.graph_objs](https://plotly.com/python/graph-objects/)
- [plotly.offline.iplot](https://plotly.com/python/offline/)
- [plotly.express](https://plotly.com/python/plotly-express/)
- [time](https://docs.python.org/3/library/time.html)
- [warnings](https://docs.python.org/3/library/warnings.html)
