---
title: Преобразование данных машинного обучения в ML.NET
description: Изучите компоненты проектирования признаков, поддерживаемые в ML.NET.
author: JRAlexander
ms.custom: seodec18
ms.date: 01/14/2019
ms.openlocfilehash: e649c9a27f0409cb9cdfb554963b5c0e732991f2
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355418"
---
# <a name="machine-learning-data-transforms---mlnet"></a>Преобразование данных машинного обучения в ML.NET

В следующих таблицах содержатся сведения обо всех преобразованиях данных, поддерживаемых в ML.NET.

> [!NOTE]
> ML.NET сейчас находится на этапе предварительной версии. В настоящее время поддерживаются не все преобразования данных. Чтобы отправить запрос на определенное преобразование, создайте заявку [в репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/issues).

## <a name="combiners-and-segregators"></a>Объединение и разделение

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.GroupTransform> | Группирует значения скалярного столбца в вектор на основе идентификатора смежной группы. |
| <xref:Microsoft.ML.Transforms.UngroupTransform> | Разделяет столбцы векторов на последовательности строк; операция, обратная группированию. |

## <a name="conversions"></a>Преобразования

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Conversions.HashingTransformer> | Хэширует либо однозначные, либо векторные столбцы. Для векторных столбцов каждый слот хэшируется отдельно. Хэшировать можно текстовые значения или значения ключей. |
| <xref:Microsoft.ML.Transforms.Conversions.HashJoiningTransform> | Преобразует значения нескольких столбцов в хэш-коды. Это преобразование принимает числовые и текстовые входные данные в столбцах с одиночными и векторными значениями. |
| <xref:Microsoft.ML.Transforms.Conversions.KeyToBinaryVectorMappingTransformer> | Преобразует ключ в двоичный векторный столбец. |
| <xref:Microsoft.ML.Transforms.Conversions.KeyToValueMappingTransformer > | Использует метаданные KeyValues для сопоставления индексов ключей с соответствующими значениями в метаданных KeyValues. |
| <xref:Microsoft.ML.Transforms.Conversions.KeyToVectorMappingTransformer> | Преобразует ключ в векторный столбец. |
| <xref:Microsoft.ML.Transforms.Conversions.TypeConvertingTransformer> | Изменяет базовый тип столбца при условии, что тип может быть преобразован. |
| <xref:Microsoft.ML.Transforms.Conversions.ValueToKeyMappingTransformer> | Преобразует входные значения (слова, числа и др.) для индексации в словаре. |

## <a name="deep-learning"></a>Глубокое обучение

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.OnnxTransform> | Предоставляет данные для существующей модели ONNX и возвращает оценку (прогноз). |
| <xref:Microsoft.ML.Transforms.TensorFlowTransform> | Оценка с помощью предварительно обученной модели TensorFlow или повторного обучения модели TensorFlow. |

## <a name="feature-extraction"></a>Признак извлечения

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Text.CustomStopWordsRemovingTransform> | Удаляет указанный список стоп-слов, сравнивая отдельные токены (сравнение без учета регистра) со стоп-словами.|
| <xref:Microsoft.ML.ImageAnalytics.ImageGrayscaleTransform> | Преобразует один или несколько столбцов ImageType в представление того же изображения в оттенках серого.|
| <xref:Microsoft.ML.ImageAnalytics.ImageLoaderTransform> | Загружает один или несколько столбцов ReadOnlyMemory как ImageType. |
| <xref:Microsoft.ML.ImageAnalytics.ImagePixelExtractorTransform> | Преобразует один или несколько столбцов ImageType в векторное представление.|
| <xref:Microsoft.ML.ImageAnalytics.ImageResizerTransform> | Изменяет размер одного или нескольких столбцов ImageType до заданной высоты и ширины.|
| <xref:Microsoft.ML.Transforms.Text.LatentDirichletAllocationTransformer> | Реализует LightLDA — современную реализацию латентного размещения Дирихле.|
| <xref:Microsoft.ML.Transforms.LoadTransform> | Загружает определенные преобразования из указанного файла модели. Позволяет выборочное преобразование из сериализованной цепочки или применить предварительно обученное преобразование к другому (но все еще совместимому) представлению данных. |
| <xref:Microsoft.ML.Transforms.Text.NgramExtractingTransformer> | Создает контейнер n-грамм (ряд последовательных значений длиной 1-n) в заданном векторе ключей. Для этого создает словарь n-грамм и использует идентификатор в словаре как индекс в контейнере. |
| <xref:Microsoft.ML.Transforms.Text.NgramExtractorTransform> | Превращает коллекцию размеченного текста (вектор ReadOnlyMemory) или векторы ключей в векторы числовых признаков. Векторы признаков — это число n-грамм (ряд последовательных токенов-слов или ключей длиной 1-n). |
| <xref:Microsoft.ML.Transforms.Text.NgramHashExtractingTransformer> | Превращает коллекцию размеченного текста (вектор ReadOnlyMemory) в векторы числовых признаков с помощью хэширования. |
| <xref:Microsoft.ML.Transforms.Text.NgramHashingTransformer> | Создает контейнер n-грамм (ряд последовательных слов длиной 1-n) в заданном тексте. |
| <xref:Microsoft.ML.Transforms.Categorical.OneHotEncodingTransformer> | Преобразует категориальное значение в массив индикатора путем создания словаря категорий на основе данных и использования идентификатора в словаре в качестве индекса в массиве. |
| <xref:Microsoft.ML.Transforms.Projections.PcaTransform> | Вычисляет проекцию вектора признаков на подпространство низкого ранга. |
| <xref:Microsoft.ML.Transforms.Text.SentimentAnalyzingTransformer> | Использует предварительно обученную модель тональности для оценки входных строк. |
| <xref:Microsoft.ML.Transforms.Text.StopWordsRemovingTransformer> | Удаляет зависящий от языка список стоп-слов (наиболее распространенных слов) путем сравнения отдельных токенов (сравнение без учета регистра) со стоп-словами. |
| <xref:Microsoft.ML.Transforms.Text.WordBagBuildingTransformer> | Создает контейнер n-грамм (ряд последовательных слов) в заданном тексте. Для этого создает словарь n-грамм и использует идентификатор в словаре как индекс в контейнере. |
| <xref:Microsoft.ML.Transforms.Text.WordHashBagProducingTransformer> | Создает контейнер n-грамм (ряд последовательных слов длиной 1-n) в заданном тексте. Для этого хэширует каждую n-грамму и использует хэш-значения в качестве индекса в контейнере. |
| <xref:Microsoft.ML.Transforms.Text.WordTokenizingTransformer> | Разбивает текст на слова, используя символ или символы разделителя. |


## <a name="image-model-featurizers"></a>Модель изображения средства присвоения признаков

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.AlexNetExtension> | Это применяемый с <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> метод расширения для использования предварительно обученной модели [AlexNet](https://en.wikipedia.org/wiki/AlexNet). NuGet, содержащий это расширение, также обязательно содержит файл двоичной модели. |
| <xref:Microsoft.ML.Transforms.ResNet18Extension> | Это применяемый с <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> метод расширения для использования предварительно обученной модели ResNet18. NuGet, содержащий это расширение, также обязательно содержит файл двоичной модели. |
| <xref:Microsoft.ML.Transforms.ResNet50Extension> | Это применяемый с <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> метод расширения для использования предварительно обученной модели ResNet50. NuGet, содержащий это расширение, также обязательно содержит файл двоичной модели. |
| <xref:Microsoft.ML.Transforms.ResNet101Extension> | Это применяемый с <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> метод расширения для использования предварительно обученной модели ResNet101. NuGet, содержащий это расширение, также обязательно содержит файл двоичной модели. |

## <a name="label-parsing"></a>Анализ меток

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.LabelConvertTransform> |  Преобразует метки. |
| <xref:Microsoft.ML.Transforms.LabelIndicatorTransform> | Преобразует многоклассовые метки в двоичные метки True, False, в основном для использования с OVA.|

## <a name="missing-values"></a>Отсутствующие значения

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.MissingValueDroppingTransformer> | Удаляет отсутствующие значения из столбцов. |
| <xref:Microsoft.ML.Transforms.MissingValueIndicatorTransform> | Создает выходной столбец с логическими данными с тем же числом слотов, что и входной столбец, где выходное значение равно true, если значение во входном столбце отсутствует. |
| <xref:Microsoft.ML.Transforms.MissingValueReplacingTransformer> | Обрабатывает отсутствующие значения, заменяя их на значение по умолчанию или на среднее, минимальное или максимальное значение (только для столбцов без текста). |

## <a name="normalization"></a>Нормализация

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Projections.LpNormalizingTransformer> | Преобразование нормализации Lp-Norm (векторное или на уровне строки). |
| <xref:Microsoft.ML.Transforms.Normalizers.MeanVarDblAggregator> | Вычисляет среднее значение и дисперсию для столбца с векторным значением. Оно отслеживает текущее среднее значение и M2 (сумма квадратов различия значений от среднего значения), количество значений NaN и ненулевых значений элементов. |
| <xref:Microsoft.ML.Transforms.Normalizers.MeanVarSngAggregator> | Вычисляет среднее значение и дисперсию для столбца с векторным значением. Оно отслеживает текущее среднее значение и M2 (сумма квадратов различия значений от среднего значения), количество значений NaN и ненулевых значений элементов. |
| <xref:Microsoft.ML.Transforms.Normalizers.MinMaxDblAggregator> | Отслеживает min, max, количество неразреженных значений (vCount) и количество вызовов ProcessValue() (trainCount) для столбца с векторным значением. |
| <xref:Microsoft.ML.Transforms.Normalizers.NormalizeTransform> | Стандартизирует диапазоны признаков. |
| <xref:Microsoft.ML.Transforms.Normalizers.NormalizingTransformer> |Стандартизирует диапазоны признаков. |

## <a name="onnx"></a>Onnx

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.OnnxTransform> | Вычисляет предварительно обученные модели ONNX, которые используют стандарт ONNX версии 1.2 |

## <a name="preprocessing"></a>Предварительная обработка
| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.BootstrapSamplingTransformer> | Составляет приблизительную выборку начальной загрузки с помощью выборки Пуассона. |
| <xref:Microsoft.ML.Transforms.Projections.RandomFourierFeaturizingTransformer> | Создает случайный признак Фурье. |
| <xref:Microsoft.ML.Transforms.Text.TokenizingByCharactersTransformer> | Создатель маркеров на основе символов, который рассматривает текст как последовательность символов. |
| <xref:Microsoft.ML.Transforms.Projections.VectorWhiteningTransformer> | Упрощает оптимизацию для определения весовых коэффициентов. |

## <a name="row-filters"></a>Фильтры строк

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.RowShufflingTransformer> | Перемешивает случайную попытку курсора, используя пул с заданным количеством строк.  |
| <xref:Microsoft.ML.Transforms.SkipFilter> | Позволяет ограничить входные данные до подмножества строк, пропуская несколько строк. |
| <xref:Microsoft.ML.Transforms.SkipTakeFilter> | Позволяет ограничить входные данные подмножеством строк с необязательным смещением. Может использоваться для разбиения данных по страницам. При создании с помощью SkipTakeFilter.SkipArguments работает как `SkipFilter`.
| <xref:Microsoft.ML.Transforms.TakeFilter> | Позволяет ограничить входные данные до подмножества строк, взяв первые N строк. |


## <a name="schema"></a>Схема

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.ColumnCopyingTransformer> | Дублирует столбцы из набора данных.|
| <xref:Microsoft.ML.Transforms.ColumnSelectingTransformer> | Выбирает набор столбцов для удаления или сохранения заданного ввода. |
| <xref:Microsoft.ML.Transforms.FeatureSelection.SlotsDroppingTransformer> | Удаляет слоты из столбцов.|
| <xref:Microsoft.ML.Transforms.OptionalColumnTransform> | Создает новый столбец с указанным типом и значениями по умолчанию. |
| <xref:Microsoft.ML.Transforms.RangeFilter> | Фильтрует представление данных в столбце типа Single, Double или Key (смежные). Сохраняет значения, которые находятся в указанном диапазоне минимума и максимума. Значения, не являющиеся числами, всегда отфильтровываются. Если входное значение имеет тип Key, минимум и максимум рассчитываются как процент от количества значений. |

## <a name="tensorflow"></a>TensorFlow

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.TensorFlowTransform> | Либо вычисляет предварительно обученную модель TensorFlow, либо повторно обучает ее. |

## <a name="text-processing-and-featurization"></a>Обработка текста и создание признаков

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Text.TextNormalizingTransformer> | Преобразование нормализации текста, которое позволяет нормализовать регистр текста, удалить диакритические знаки, знаки пунктуации и (или) цифры. Преобразование обрабатывает ввод текста, а также вектор токенов или текста (вектор ReadOnlyMemory). |
| <xref:Microsoft.ML.Transforms.Text.TokenizingByCharactersTransformer> | Создатель маркеров на основе символов, который рассматривает текст как последовательность символов. |

## <a name="time-series"></a>Временной ряд

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.TimeSeriesProcessing.ExponentialAverageTransform> | Принимает взвешенное среднее значение: ExpAvg(y_t) = a * y_t + (1-a) * ExpAvg(y_(t-1)). |
| <xref:Microsoft.ML.TimeSeriesProcessing.IidChangePointDetector> | Реализует преобразование обнаружения точки изменения для последовательности i.i.d. (случайная выборка) на основе адаптивной ядерной оценки плотности и мартингалов. |
| <xref:Microsoft.ML.TimeSeriesProcessing.IidSpikeDetector> | Реализует преобразование обнаружения пиков для последовательности i.i.d. (случайная выборка) на основе адаптивной ядерной оценки плотности. |
| <xref:Microsoft.ML.TimeSeriesProcessing.MovingAverageTransform> | Предоставляет взвешенное среднее значение скользящего окна. |
| <xref:Microsoft.ML.TimeSeriesProcessing.PercentileThresholdTransform> | Решает, принадлежит ли текущее значение временного ряда к процентиле верхних значений скользящего окна. |
| <xref:Microsoft.ML.TimeSeriesProcessing.PValueTransform> | Вычисляет эмпирическое значение вероятности текущего значения ряда на основе других значений в скользящем окне. |
| <xref:Microsoft.ML.TimeSeriesProcessing.SlidingWindowTransform> | Выводит скользящее окно на временной ряд типа Single. |
| <xref:Microsoft.ML.TimeSeriesProcessing.SsaChangePointDetector> | Реализует преобразование обнаружения точки изменения на основе моделирования сингулярного спектра временного ряда. |
| <xref:Microsoft.ML.TimeSeriesProcessing.SsaSpikeDetector> | Реализует преобразование обнаружения пиков на основе моделирования сингулярного спектра временного ряда. |

## <a name="miscellaneous"></a>Прочее

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.Transforms.CompositeTransformer> | Создает составной DataTransform. |
| <xref:Microsoft.ML.Transforms.CustomMappingTransformer%602> | Формирует дополнительные столбцы для предоставленного `IDataView`. Оно не меняет количество строк и его можно увидеть в результате применения функции пользователя к каждой строке входных данных.|
| <xref:Microsoft.ML.Transforms.GenerateNumberTransform> | Добавляет столбец с созданной последовательностью чисел. |
| <xref:Microsoft.ML.Transforms.ProduceIdTransform> | Создает столбец с идентификатором курсора в качестве столбца. |
| <xref:Microsoft.ML.Transforms.RandomNumberGenerator> | Генерирует случайное число. |
