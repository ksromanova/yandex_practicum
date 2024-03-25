# Описание проекта

Из «Бета-Банка» стали уходить клиенты. Каждый месяц. Немного, но заметно. Банковские маркетологи посчитали: сохранять текущих клиентов дешевле, чем привлекать новых.

Нужно спрогнозировать, уйдёт клиент из банка в ближайшее время или нет. Вам предоставлены исторические данные о поведении клиентов и расторжении договоров с банком. 

Постройте модель с предельно большим значением *F1*-меры. Чтобы сдать проект успешно, нужно довести метрику до 0.59. Проверьте *F1*-меру на тестовой выборке самостоятельно.

Дополнительно измеряйте *AUC-ROC*, сравнивайте её значение с *F1*-мерой.

## Описание задачи
Нужно обучить модель, которая сможет предсказывать уход клиента 'Бета-Банка'. 
Этапы решения данной задачи:
1. Загрузить и подготовить данные. Пояснить порядок действий.
2. Исследовать баланс классов, обучить модель без учёта дисбаланса. Кратко описать выводы.
3. Улучшить качество модели, учитывая дисбаланс классов. Обучить разные модели и найти лучшую. Кратко описать выводы.
4. Провести финальное тестирование.

**Используемые библиотеки:**

- [numpy](https://numpy.org/): для работы с массивами и матрицами
- [pandas](https://pandas.pydata.org/): для работы с данными в виде таблиц и серий
- [seaborn](https://seaborn.pydata.org/): для визуализации данных
- [sklearn.ensemble.RandomForestClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html): для обучения модели случайного леса
- [sklearn.linear_model.LogisticRegression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html): для обучения логистической регрессии
- [sklearn.metrics](https://scikit-learn.org/stable/modules/classes.html#module-sklearn.metrics): для оценки качества модели (accuracy_score, confusion_matrix, f1_score, recall_score, precision_score, precision_recall_curve, roc_auc_score, roc_curve)
- [sklearn.model_selection.train_test_split](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.train_test_split.html): для разделения данных на обучающий и тестовый наборы
- [sklearn.preprocessing.StandardScaler](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html): для масштабирования признаков
- [sklearn.tree.DecisionTreeClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html): для обучения модели дерева принятия решений
- [sklearn.utils.shuffle](https://scikit-learn.org/stable/modules/generated/sklearn.utils.shuffle.html): для случайного перемешивания данных
- [matplotlib.pyplot](https://matplotlib.org/): для визуализации данных
- [tqdm](https://github.com/tqdm/tqdm): для отображения прогресса выполнения итераций
