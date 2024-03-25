# Проект для «Викишоп»
## Описание проекта
Интернет-магазин «Викишоп» запускает новый сервис. Теперь пользователи могут редактировать и дополнять описания товаров, как в вики-сообществах. То есть клиенты предлагают свои правки и комментируют изменения других. 

**Цель:** Создать инструмент, который будет искать токсичные комментарии и отправлять их на модерацию. 

**Задача:** Обучить модель классифицировать комментарии на позитивные и негативные на наборе данных с разметкой о токсичности правок.

Необходимо построить модель со значением метрики качества ***F1*** не меньше **0.75**. 

**Шаги выполнения проекта**

1. Загрузить и подготовить данные.
2. Обучить разные модели. 
3. Сделать выводы.

**Описание данных**

Данные находятся в файле `toxic_comments.csv`. Столбец *text* в нём содержит текст комментария, а *toxic* — целевой признак.

**Используемые библиотеки:**

- [matplotlib.pyplot](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.html): для создания графиков и визуализации данных
- [nltk](https://www.nltk.org/): для обработки естественного языка, включая токенизацию, анализ частоты слов и т.д.
- [numpy](https://numpy.org/): для работы с многомерными массивами и матрицами, а также для выполнения вычислительных задач
- [pandas](https://pandas.pydata.org/): для обработки и анализа данных, представленных в виде таблицы
- [plotly.graph_objects](https://plotly.com/python/graph-objects/): для создания интерактивных графиков и визуализации данных
- [re](https://docs.python.org/3/library/re.html): для работы с регулярными выражениями
- [scipy.stats.randint](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.randint.html): для работы с генерацией случайных чисел и статистическими распределениями
- [seaborn](https://seaborn.pydata.org/): для создания красивых и информативных статистических графиков
- [sklearn.ensemble.GradientBoostingClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.GradientBoostingClassifier.html): для обучения модели градиентного бустинга
- [sklearn.ensemble.RandomForestClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html): для обучения модели случайного леса
- [sklearn.feature_extraction.text.CountVectorizer](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.CountVectorizer.html): для преобразования текстовых данных в числовые признаки
- [sklearn.feature_extraction.text.TfidfVectorizer](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html): для преобразования текстовых данных в числовые признаки с использованием метода TF-IDF
- [sklearn.linear_model.LogisticRegression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html): для обучения логистической регрессии
- [sklearn.metrics.f1_score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.f1_score.html): для вычисления F1-меры
- [sklearn.model_selection.RandomizedSearchCV](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.RandomizedSearchCV.html): для поиска оптимальных параметров модели с помощью случайного поиска
- [sklearn.model_selection.train_test_split](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.train_test_split.html): для разделения данных на обучающий и тестовый наборы
- [sklearn.pipeline.Pipeline](https://scikit-learn.org/stable/modules/generated/sklearn.pipeline.Pipeline.html): для создания конвейеров обработки данных и построения моделей
- [spacy](https://spacy.io/): для обработки и анализа текстовых данных
- [tqdm.notebook](https://tqdm.github.io/): для создания красивых и информативных прогресс-баров в блокноте
- [wordcloud.WordCloud](https://amueller.github.io/word_cloud/): для создания облака слов на основе текстовых данных
