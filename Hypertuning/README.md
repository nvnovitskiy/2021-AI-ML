# Лабораторная работа №3

## Задание на лабораторную работу:

Разработать собственную реализацию методов Grid Search и Random Search. Данные методы должны находить гиперпараметры модели, которые обеспечивают минимальное значение ошибки согласно варианту. Использовать наборы данных, полученные при выполнении лабораторной работы №1. Вид ошибки определяется в зависимости от варианта:

* Чётный номер варианта – ошибка первого рода
* Нечётный номер вариант – ошибка второго рода.

## Результаты, которые необходимо получить в итоге:

1. Значения гиперпараметров классификаторов (_KNeighborsClassifier_ и _DecisionTreeClassifier_).
2. Таблицу, содержащую значения F-меры, точности и полноты для каждого класса при использовании оптимальных значений параметров классификации.
3. Выводы о плюсах и минусах используемых методов поиска оптимальных параметров.

## Значения гиперпараметров классификаторов (_KNeighborsClassifier_ и _DecisionTreeClassifier_)

DecisionTreeClassifier RandomSearch:

{'min_samples_split': 0.01, 'min_samples_leaf': 0.08, 'max_depth': 10.0}

DecisionTreeClassifier GridSearch:

{'max_depth': 5.0, 'min_samples_leaf': 0.01, 'min_samples_split': 0.04000000000000001}

KNeighborsClassifier RandomSearch:

{'weights': 'uniform', 'p': 1, 'n_neighbors': 9, 'metric': 'manhattan', 'algorithm': 'kd_tree'}

KNeighborsClassifier GridSearch:

{'algorithm': 'auto', 'metric': 'minkowski', 'n_neighbors': 7, 'p': 1, 'weights': 'uniform'}

## Таблицу, содержащую значения F-меры, точности и полноты для каждого класса при использовании оптимальных значений параметров классификации.

DecisionTreeClassifier RandomSearch:

![first](https://github.com/witssaa/2021-AI-ML/blob/main/Hypertuning/images/dtc_with_random_search.png)

DecisionTreeClassifier GridSearch:

![second](https://github.com/witssaa/2021-AI-ML/blob/main/Hypertuning/images/dtc_with_grid_search.png)

KNeighborsClassifier RandomSearch:

![third](https://github.com/witssaa/2021-AI-ML/blob/main/Hypertuning/images/knn_with_random_search.png)

KNeighborsClassifier GridSearch:

![fourth](https://github.com/witssaa/2021-AI-ML/blob/main/Hypertuning/images/knn_with_grid_search.png)

## Выводы о плюсах и минусах используемых методов поиска оптимальных параметров

1. Поиск по сетке работает медленнее случайного поиска. Так как оба метода поиска дают прирост качества (средняя оценка на кросс-валидации), то для первичной настройки гиперпараметров, возможно, лучше сначала пробовать случайный поиск из-за скорости работы. Если же не получается добиться желаемого качества, то можно использовать поиск по сетке.

2. Случайный поиск хоть и не является "информативным" методом (он не полагается на прошлые результаты оценки), он обычно находит лучшие значения, чем значения по умолчанию.

3. Поиск по сетке работает медленнее, но даёт результат лучше, чем случайный поиск.

4. Важно сказать, что настройка гиперпараметров не всегда является хорошим решением для увеличения качества, потому что она может привести к переобучению. Использование настройки с учётом кросс-валидации должно минимизировать этот риск, но он все равно имеет место быть.
