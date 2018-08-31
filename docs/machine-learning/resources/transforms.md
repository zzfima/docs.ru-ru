---
title: Преобразования данных
description: Ознакомьтесь с различными преобразованиями данных, которые поддерживаются в ML.NET.
ms.date: 08/08/2018
author: jralexander
ms.author: johalex
ms.openlocfilehash: 3c483f4a263052eb15435775a47f514893eee049
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43000859"
---
# <a name="data-transforms"></a>Преобразования данных

В следующих таблицах представлены сведения о всех преобразованиях данных, которые поддерживаются в ML.NET (выберите тип преобразования данных для перехода к соответствующей таблице):

* [Категориальные](#categorical)
* [Объединение и разделение](#combiners-and-segregators)
* [Выбор признака](#feature-selection)
* [Создатели признаков](#featurizers)
* [Анализ меток](#label-parsing)
* [Отсутствующие значения](#missing-values)
* [Нормализация](#normalization)
* [Фильтры строк](#row-filters)
* [Схема](#schema)
* [Обработка текста и создание признаков](#text-processing-and-featurization)
* [Прочее](#miscellaneous)

> [!NOTE]
> ML.NET сейчас находится на этапе предварительной версии. В настоящее время поддерживаются не все преобразования данных. Чтобы отправить запрос на определенное преобразование, создайте заявку [в репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/issues).

## <a name="categorical"></a>Категориальные

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.CategoricalHashOneHotVectorizer> | Кодирует категориальную переменную на основе хэша. |
| <xref:Microsoft.ML.Transforms.CategoricalOneHotVectorizer> | Кодирует категориальную переменную прямым кодированием на основе словаря терминов. |

## <a name="combiners-and-segregators"></a>Объединение и разделение

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.CombinerByContiguousGroupId> | Группирует значения скалярного столбца в вектор на основе идентификатора смежной группы. |
| <xref:Microsoft.ML.Transforms.FeatureCombiner> | Объединяет все признаки в один столбец признаков. |
| <xref:Microsoft.ML.Transforms.ManyHeterogeneousModelCombiner> | Объединяет последовательность TransformModels и PredictorModel в единую модель PredictorModel. |
| <xref:Microsoft.ML.Transforms.ModelCombiner> | Объединяет последовательность TransformModels в одну модель. |
| <xref:Microsoft.ML.Transforms.Segregator> | Разделяет столбцы векторов на последовательности строк; операция, противоположная группированию. |
| <xref:Microsoft.ML.Transforms.TwoHeterogeneousModelCombiner> | Объединяет TransformModel и PredictorModel в единую модель PredictorModel. |

## <a name="feature-selection"></a>Выбор признаков

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.FeatureSelectorByCount> | Выбирает слоты, для которых число значений не по умолчанию не меньше порогового значения. |
| <xref:Microsoft.ML.Transforms.FeatureSelectorByMutualInformation> | Выбирает первые k слотов из всех указанных столбцов, упорядоченных по общей информации, с помощью столбца метки. |

## <a name="featurizers"></a>Создатели признаков

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.HashConverter> | Преобразует значения столбца в хэш-коды. Это преобразование принимает числовые и текстовые входные данные в столбцах с одиночными и векторными значениями. |
| <xref:Microsoft.ML.Transforms.TreeLeafFeaturizer> | Обучает совокупность деревьев или загружает ее из файла, а затем сопоставляет вектор числовых признаков с тремя выходными данными: 1. Вектор, содержащий выходные данные отдельного дерева в совокупности. 2. Вектор, указывающий листья, на которые приходится вектор признаков в совокупности деревьев. 3. Вектор, указывающий пути, на которые приходится вектор признаков в совокупности деревьев. Если указаны файл модели и средство обучения, вектор будет использовать файл модели. Если не указано ни то, ни другое, вектор будет обучать модель FastTree по умолчанию. Это позволяет обрабатывать ключевые метки путем обучения модели регрессии в направлении к необязательно перемещенным индексам. |

## <a name="label-parsing"></a>Анализ меток

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Dictionarizer> | Преобразует входные значения (слова, числа и др.) для индексации в словаре. |
| <xref:Microsoft.ML.Transforms.LabelColumnKeyBooleanConverter> | Преобразует метку в ключ или bool (при необходимости), чтобы сделать ее пригодной для классификации. |
| <xref:Microsoft.ML.Transforms.LabelIndicator> | Переназначение метки, используемое OVA. |
| <xref:Microsoft.ML.Transforms.LabelToFloatConverter> | Преобразует метку в число с плавающей запятой, чтобы сделать ее пригодной для регрессии. |
| <xref:Microsoft.ML.Transforms.PredictedLabelColumnOriginalValueConverter> | Преобразует спрогнозированный столбец меток в исходные значения, если он не имеет тип bool. |

## <a name="missing-values"></a>Отсутствующие значения

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.MissingValueHandler> | Обрабатывает отсутствующие значения, заменяя их на значение по умолчанию или на среднее, минимальное или максимальное значение (только для столбцов без текста). Столбец индикаторов при необходимости можно объединить, если тип входного столбца является числовым. |
| <xref:Microsoft.ML.Transforms.MissingValueIndicator> | Создает выходной столбец с логическими данными с тем же числом слотов, что и входной столбец, где выходное значение равно true, если значение во входном столбце отсутствует. |
| <xref:Microsoft.ML.Transforms.MissingValuesDropper> | Удаляет NA из векторных столбцов. |
| <xref:Microsoft.ML.Transforms.MissingValuesRowDropper> | Отфильтровывает строки, содержащие отсутствующие значения. |
| <xref:Microsoft.ML.Transforms.MissingValueSubstitutor> | Создает выходной столбец того же типа и размера, что и входной столбец, где отсутствующие значения заменяются значением по умолчанию или средним, минимальным или максимальным значением (только для столбцов без текста). |

## <a name="normalization"></a>Нормализация

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.BinNormalizer> | Значения присваиваются в ячейки одинаковой плотности, и значение сопоставляется со своим параметром bin_number / number_of_bins. |
| <xref:Microsoft.ML.Transforms.ConditionalNormalizer> | Нормализует столбцы только при необходимости. |
| <xref:Microsoft.ML.Transforms.GlobalContrastNormalizer> | Выполняет глобальную нормализацию разницы на входных значениях: Y = (s * X – M) / D, где s — это масштаб, M — среднее значение, а D — норма L2 или стандартное отклонение. | 
| <xref:Microsoft.ML.Transforms.LogMeanVarianceNormalizer> | Нормализует данные с учетом вычисленного среднего значения и отклонения логарифма данных. |
| <xref:Microsoft.ML.Transforms.LpNormalizer> | Нормализует векторы (строки) по отдельности, изменяя их масштаб и приводя его к норме (L2, L1 или LInf). Выполняет следующую операцию для вектора X: Y = (X – M) / D, где M является средним значением и D — это норма L2, L1 или LInf. |
| <xref:Microsoft.ML.Transforms.MeanVarianceNormalizer> | Нормализует данные с учетом вычисленного среднего значения и отклонения данных. |
| <xref:Microsoft.ML.Transforms.MinMaxNormalizer> | Нормализует данные с учетом минимальных и максимальных значений данных. |
| <xref:Microsoft.ML.Transforms.SupervisedBinNormalizer> | Похоже на <xref:Microsoft.ML.Transforms.BinNormalizer>, но вычисляет ячейки в зависимости от корреляции со столбцом меток, а не одинаковой плотности. Новое значение — bin_number / number_of_bins. |

## <a name="row-filters"></a>Фильтры строк

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.RowRangeFilter> | Фильтрует представление данных в столбце типа Single, Double или Key (смежные). Сохраняет значения, которые находятся в указанном диапазоне минимума и максимума. Значения, не являющиеся числами, всегда отфильтровываются. Если входное значение имеет тип Key, минимум и максимум рассчитываются как процент от количества значений. |
| <xref:Microsoft.ML.Transforms.RowSkipAndTakeFilter> | Позволяет ограничить входные данные подмножеством строк с необязательным смещением. Может использоваться для разбиения данных по страницам. |
| <xref:Microsoft.ML.Transforms.RowSkipFilter> | Позволяет ограничить входные данные до подмножества строк, пропуская несколько строк. |
| <xref:Microsoft.ML.Transforms.RowTakeFilter> | Позволяет ограничить входные данные до подмножества строк, взяв первые N строк. |

## <a name="schema"></a>Схема

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.ColumnConcatenator> | Объединяет два столбца с одним типом элемента. |
| <xref:Microsoft.ML.Transforms.ColumnCopier> | Дублирует столбцы из набора данных.|
| <xref:Microsoft.ML.Transforms.ColumnDropper> | Удаляет столбцы из набора данных. |
| <xref:Microsoft.ML.Transforms.ColumnSelector> | Выбирает набор столбцов, удаляя остальные. |
| <xref:Microsoft.ML.Transforms.ColumnTypeConverter> | Преобразует столбец в другой тип с использованием стандартных преобразований. |
| <xref:Microsoft.ML.Transforms.KeyToTextConverter> | KeyToValueTransform использует метаданные KeyValues для сопоставления индексов ключей с соответствующими значениями в метаданных KeyValues. |
| <xref:Microsoft.ML.Transforms.NGramTranslator> | Создает контейнер n-грамм (ряд последовательных значений длиной 1-n) в заданном векторе ключей. Для этого создает словарь n-грамм и использует идентификатор в словаре как индекс в контейнере. | 
| <xref:Microsoft.ML.Transforms.OptionalColumnCreator> | Если исходный столбец не существует после десериализации, создает столбец с правильным типом и значениями по умолчанию. |

## <a name="text-processing-and-featurization"></a>Обработка текста и создание признаков

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.CharacterTokenizer> | Создатель маркеров на основе символов, который рассматривает текст как последовательность символов. |
| <xref:Microsoft.ML.Transforms.TextFeaturizer> | Преобразование, которое превращает коллекцию текстовых документов в векторы числовых признаков. Векторы признаков — это нормализованное число n-грамм (слово и (или) символ) в определенном тексте с созданными маркерами. |
| <xref:Microsoft.ML.Transforms.TextToKeyConverter> | Преобразует входные значения (слова, числа и др.) для индексации в словаре. |
| <xref:Microsoft.ML.Transforms.WordEmbeddings> | Преобразование, которое превращает векторы маркеров текста в числовые векторы с помощью предварительно обученной модели. Дополнительные сведения об этом методе см. на странице Википедии [Векторное представление слов](https://en.wikipedia.org/wiki/Word_embedding). |
| <xref:Microsoft.ML.Transforms.WordTokenizer> | Входные данные для этого преобразования — текст, а выходные данные — вектор текста, содержащий слова (маркеры) в исходном тексте. В качестве разделителя используется пробел, но можно указать любой другой символ (или несколько символов). |

## <a name="miscellaneous"></a>Прочее

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.ApproximateBootstrapSampler> | Составляет приблизительную выборку начальной загрузки. |
| <xref:Microsoft.ML.Transforms.BinaryPredictionScoreColumnsRenamer> | Для двоичного прогнозирования переименовывает столбцы PredictedLabel и Score, чтобы включить в них имя положительного класса.|
| <xref:Microsoft.ML.Transforms.DataCache> | Выполняет кэширование с помощью указанного параметра. |
| <xref:Microsoft.ML.Transforms.DatasetScorer> | Оценивает набор данных с помощью модели прогнозирования. |
| <xref:Microsoft.ML.Transforms.DatasetTransformScorer> | Оценивает набор данных с помощью модели преобразования. |
| <xref:Microsoft.ML.Transforms.NoOperation> | Ничего не делает. |
| <xref:Microsoft.ML.Transforms.RandomNumberGenerator> | Добавляет столбец с созданной последовательностью чисел. |
| <xref:Microsoft.ML.Transforms.ScoreColumnSelector> | Выбирает только последние столбцы оценки и дополнительные столбцы, указанные в аргументах. |
| <xref:Microsoft.ML.Transforms.Scorer> | Превращает модель прогнозирования в модель преобразования. |
| <xref:Microsoft.ML.Transforms.SentimentAnalyzer> | Использует предварительно обученную модель тональности для оценки входных строк. |
| <xref:Microsoft.ML.Transforms.TrainTestDatasetSplitter> | Разделяет набор данных на наборы обучения и тестирования. |
