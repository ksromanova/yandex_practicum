Необходимо защитить данные клиентов страховой компании «Хоть потоп». В данном проекте нужно разработать метод преобразования данных, чтобы по ним было сложно восстановить персональную информацию. Необходимо корректность его работы.

Нужно защитить данные, чтобы при преобразовании качество моделей машинного обучения не ухудшилось. Подбирать наилучшую модель не требуется.
## Постановка задачи
**Этапы выполнения проекта:**
* Загрузить и изучить данные.
* Ответить на вопрос и обосновать решение. 

        Признаки умножают на обратимую матрицу. Изменится ли качество линейной регрессии? 
        (Её можно обучить заново.)

        a. Изменится. Приведите примеры матриц.
        b. Не изменится. Укажите, как связаны параметры линейной регрессии в исходной задаче и в преобразованной.
* Предложить алгоритм преобразования данных для решения задачи. Обосновать, почему качество линейной регрессии не поменяется.
* Запрограммировать данный алгоритм, применив матричные операции. Проверить, что качество линейной регрессии из sklearn не отличается до и после преобразования. Применить метрику R2.

**Описание данных**

*Признаки:* пол, возраст и зарплата застрахованного, количество членов его семьи.

*Целевой признак:* количество страховых выплат клиенту за последние 5 лет.

Набор данных находится в файле /datasets/insurance.csv.

**Используемые библиотеки:**

- [chart_studio.plotly](https://plotly.com/python/)
- [cufflinks](https://github.com/santosjorge/cufflinks)
- [pandas](https://pandas.pydata.org/)
- [seaborn](https://seaborn.pydata.org/)
- [scipy.stats.spearmanr](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.spearmanr.html)
- [sklearn.model_selection.train_test_split](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.train_test_split.html)
- [sklearn.linear_model.LinearRegression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html)
- [sklearn.metrics.r2_score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.r2_score.html)
- [statsmodels.api](https://www.statsmodels.org/stable/index.html)
- [statsmodels.formula.api.ols](https://www.statsmodels.org/stable/generated/statsmodels.formula.api.ols.html)
- [numpy](https://numpy.org/)
- [matplotlib](https://matplotlib.org/)
- [plotly.graph_objs](https://plotly.com/python/graph-objects/)
- [plotly.offline.iplot](https://plotly.com/python/offline/)
- [warnings](https://docs.python.org/3/library/warnings.html)
