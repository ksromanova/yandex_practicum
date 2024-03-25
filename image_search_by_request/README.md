# Описание проекта

Поручено разработать демонстрационную версию поиска изображений по запросу.

Для демонстрационной версии нужно обучить модель, которая получит векторное представление изображения, векторное представление текста, а на выходе выдаст число от 0 до 1 — покажет, насколько текст и картинка подходят друг другу.

## Описание данных

В файле `train_dataset.csv` собрана информация, необходимая для обучения: имя файла изображения, идентификатор описания и текст описания. Для одной картинки может быть доступно до 5 описаний. Идентификатор описания имеет формат `<имя файла изображения>#<порядковый номер описания>`.

В папке `train_images` содержатся изображения для тренировки модели.

В файле `CrowdAnnotations.tsv` — данные по соответствию изображения и описания, полученные с помощью краудсорсинга. Номера колонок и соответствующий тип данных:

1. Имя файла изображения.
2. Идентификатор описания.
3. Доля людей, подтвердивших, что описание соответствует изображению.
4. Количество человек, подтвердивших, что описание соответствует изображению.
5. Количество человек, подтвердивших, что описание не соответствует изображению.

В файле `ExpertAnnotations.tsv` содержатся данные по соответствию изображения и описания, полученные в результате опроса экспертов. Номера колонок и соответствующий тип данных:

1. Имя файла изображения.
2. Идентификатор описания.

3, 4, 5 — оценки трёх экспертов.

Эксперты ставят оценки по шкале от 1 до 4, где 1 — изображение и запрос совершенно не соответствуют друг другу, 2 — запрос содержит элементы описания изображения, но в целом запрос тексту не соответствует, 3 — запрос и текст соответствуют с точностью до некоторых деталей, 4 — запрос и текст соответствуют полностью.

В файле `test_queries.csv` находится информация, необходимая для тестирования: идентификатор запроса, текст запроса и релевантное изображение. Для одной картинки может быть доступно до 5 описаний. Идентификатор описания имеет формат `<имя файла изображения>#<порядковый номер описания>`.

В папке `test_images` содержатся изображения для тестирования модели.

**Используемые библиотеки:**

- [google.colab](https://colab.research.google.com/notebooks/intro.ipynb): для доступа к Google Colab и управления средой выполнения
- [keras.preprocessing.image.ImageDataGenerator](https://keras.io/api/preprocessing/image/): для предобработки изображений в нейронных сетях с помощью Keras
- [lightgbm.LGBMRegressor](https://lightgbm.readthedocs.io/en/latest/pythonapi/lightgbm.LGBMRegressor.html): для обучения градиентного бустинга на деревьях решений с помощью LightGBM
- [matplotlib.pyplot](https://matplotlib.org/): для создания графиков и визуализации данных
- [nltk](https://www.nltk.org/): для естественной обработки текста и анализа
- [numpy](https://numpy.org/): для работы с массивами и выполнения математических операций
- [os](https://docs.python.org/3/library/os.html): для взаимодействия с операционной системой
- [pandas](https://pandas.pydata.org/): для работы с данными в виде таблиц и серий
- [PIL.Image](https://pillow.readthedocs.io/en/stable/reference/Image.html): для обработки изображений с помощью Python Imaging Library (PIL)
- [plotly.express](https://plotly.com/python/plotly-express/): для создания интерактивных графиков и визуализации данных
- [re](https://docs.python.org/3/library/re.html): для работы с регулярными выражениями в Python
- [scipy.spatial.distance](https://docs.scipy.org/doc/scipy/reference/spatial.distance.html): для работы с расстояниями и метриками расстояний в SciPy
- [scikit-learn](https://scikit-learn.org/stable/): для машинного обучения и анализа данных
- [spacy](https://spacy.io/): для обработки естественного языка и анализа текста
- [tensorflow](https://www.tensorflow.org/): для создания и обучения нейронных сетей с использованием TensorFlow
- [torch](https://pytorch.org/): для создания и обучения нейронных сетей с использованием PyTorch
- [torchvision.models.resnet50](https://pytorch.org/vision/stable/models.html#torchvision.models.resnet50): предварительно обученная модель ResNet-50 для компьютерного зрения в PyTorch
- [torchvision.transforms](https://pytorch.org/vision/stable/transforms.html): для преобразования изображений в PyTorch
- [transformers.BertModel](https://huggingface.co/transformers/model_doc/bert.html#bertmodel): для использования модели BERT
- [transformers.BertTokenizer](https://huggingface.co/transformers/model_doc/bert.html#berttokenizer): для токенизации текста с использованием токенизатора BERT
- [tqdm.notebook](https://github.com/tqdm/tqdm): для отображения прогресса выполнения итераций в Jupyter Notebook
- [wordcloud.WordCloud](https://amueller.github.io/word_cloud/index.html): для создания облака слов из текстовых данных
- [zipfile](https://docs.python.org/3/library/zipfile.html): для работы с архивами ZIP в Python
