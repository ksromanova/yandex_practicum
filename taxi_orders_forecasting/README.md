#  Описание проекта

Компания «Чётенькое такси» собрала исторические данные о заказах такси в аэропортах. Чтобы привлекать больше водителей в период пиковой нагрузки, нужно спрогнозировать количество заказов такси на следующий час. Необходимо построить модель для такого предсказания.

Значение метрики *RMSE* на тестовой выборке должно быть не больше 48.

Нужно:

1. Загрузить данные и выполнить их ресемплирование по одному часу.
2. Проанализировать данные.
3. Обучить разные модели с различными гиперпараметрами. Сделать тестовую выборку размером 10% от исходных данных.
4. Проверить данные на тестовой выборке и сделать выводы.


Данные лежат в файле `taxi.csv`. Количество заказов находится в столбце `num_orders` (от англ. *number of orders*, «число заказов»).
# Описание проекта
**Цель проекта:** Необходимо спрогнозировать количество заказов такси на следующий час, построив модель для такого предсказания.

**Задача:** Значение метрики RMSE на тестовой выборке должно быть не больше 48.


**Шаги выполнения проекта**
* Загрузить данные и выполнить их ресемплирование по одному часу.
* Проанализировать данные.
* Обучить разные модели с различными гиперпараметрами. Сделать тестовую выборку размером 10% от исходных данных.
* Проверить данные на тестовой выборке и сделать выводы.

**Используемые библиотеки:**

- [lightgbm](https://lightgbm.readthedocs.io/en/latest/): для построения моделей градиентного бустинга над решающими деревьями
- [pandas](https://pandas.pydata.org/): для обработки и анализа данных, представленных в виде таблицы
- [numpy](https://numpy.org/): для работы с многомерными массивами и матрицами, а также для выполнения вычислительных задач
- [matplotlib.pyplot](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.html): для создания графиков и визуализации данных
- [sklearn.ensemble.RandomForestRegressor](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html): для построения модели случайного леса регрессии
- [sklearn.linear_model.LinearRegression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html): для построения линейной регрессии
- [sklearn.metrics.mean_squared_error](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.mean_squared_error.html): для вычисления среднеквадратичной ошибки модели
- [sklearn.metrics.SCORERS](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.SCORERS.html): для доступа к встроенным метрикам качества модели в scikit-learn
- [sklearn.model_selection.RandomizedSearchCV](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.RandomizedSearchCV.html): для случайного поиска гиперпараметров модели
- [sklearn.model_selection.TimeSeriesSplit](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.TimeSeriesSplit.html): для разделения временных данных на обучающий и тестовый наборы с учетом последовательности
- [sklearn.model_selection.GridSearchCV](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html): для поиска по сетке гиперпараметров модели
- [scipy.stats.randint](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.randint.html): для генерации случайных целых чисел в указанном диапазоне
- [statsmodels.tsa.seasonal.seasonal_decompose](https://www.statsmodels.org/stable/generated/statsmodels.tsa.seasonal.seasonal_decompose.html): для декомпозиции временных данных на тренд, сезонность и остатки

