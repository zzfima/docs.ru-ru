---
title: Преобразования данных
description: Изучите компоненты проектирования признаков, поддерживаемые в ML.NET.
ms.date: 04/02/2019
ms.openlocfilehash: ca410b475c556db5ad4c3862fb79755b455d6830
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75739587"
---
# <a name="data-transformations"></a>Преобразования данных

Преобразования данных используются, чтобы:

- подготовить данные для обучения модели;
- применить импортированную модель в формате TensorFlow или ONNX;
- обработать данных после передачи через модель.

В этом руководстве рассматриваются преобразования, которые возвращают классы, реализующие интерфейс [IEstimator](xref:Microsoft.ML.IEstimator%601). Преобразования данных можно соединять в цепочки. Каждое преобразование принимает и выводит данные определенных типов и форматов, которые указаны в связанной справочной документации.

Некоторым преобразованиям данных требуются данные для обучения, чтобы вычислять их параметры. Например, преобразователь <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> позволяет вычислить среднее значение и дисперсию данных для обучения при выполнении операции `Fit()` и использует эти параметры в операции `Transform()`.

Другим преобразованиям данных не требуются данные для обучения. Например, преобразование <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale%2A> позволяет выполнять операцию `Transform()` без изучения данных для обучения при выполнении операции `Fit()`.

## <a name="column-mapping-and-grouping"></a>Сопоставление и группирование столбцов

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A> | Объединение одного или нескольких входных столбцов в новый выходной столбец |
| <xref:Microsoft.ML.TransformExtensionsCatalog.CopyColumns%2A> | Копирование и переименование одного или нескольких входных столбцов |
| <xref:Microsoft.ML.TransformExtensionsCatalog.DropColumns%2A> | Удаление одного или нескольких входных столбцов |
| <xref:Microsoft.ML.TransformExtensionsCatalog.SelectColumns%2A> | Выбор одного или нескольких столбцов для хранения входных данных |

## <a name="normalization-and-scaling"></a>Нормализация и масштабирование

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> | Вычитание среднего значения (данные для обучения) и деление на значение дисперсии (данные для обучения) |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLogMeanVariance%2A> | Нормализация на основе логарифма данных для обучения |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLpNorm%2A> | Масштабирование входных векторов на основе [lp-norm](https://en.wikipedia.org/wiki/Lp_space#The_p-norm_in_finite_dimensions), где p — 1, 2 или бесконечность. Значение по умолчанию — норма l2 (Евклидово расстояние) |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeGlobalContrast%2A> | Масштабирование каждого значения в строке путем вычитания среднего значения данных в строке и деления либо на стандартное отклонение, либо на норму l2 (данных в строке) и умножения на настраиваемый коэффициент масштабирования (значение по умолчанию — 2) |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A> | Назначение двоичного индекса в качестве входного значения и деление на число ячеек для получения значения с плавающей запятой от 0 до 1. Границы ячеек вычисляются для равномерного распределения между ними данных для обучения |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeSupervisedBinning%2A> | Назначьте входное значение для ячейки в зависимости от корреляции со столбцом меток |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A> | Масштабирование входных значений на основе разницы между минимальным и максимальным значениями в данных для обучения |

## <a name="conversions-between-data-types"></a>Преобразования между типами данных

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.ConvertType%2A> | Преобразование типа входного столбца в новый тип |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValue%2A> | Сопоставление значений с ключами (категориями) на основе предоставленного словаря сопоставлений |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> | Сопоставление значений с ключами (категориями) путем создания сопоставлений на основе входных данных |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue%2A> | Обратное преобразование ключей в исходное значение |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToVector%2A> | Обратное преобразование ключей в векторы исходных значений |
| <xref:Microsoft.ML.ConversionsCatalog.MapKeyToBinaryVector%2A> | Обратное преобразование ключей в двоичный вектор исходных значений |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash%2A> | Хэширование значения во входном столбце |

## <a name="text-transformations"></a>Преобразования текста

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.TextCatalog.FeaturizeText%2A> | Преобразование текстового столбца в массив float счетчиков нормализованных n-грамм и символьных n-грамм |
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A> | Разбиение одного или нескольких текстовых столбцов на отдельные слова |
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoCharactersAsKeys%2A> | Разбиение одного или нескольких текстовых столбцов на отдельные массивы float в пределах набора тем |
| <xref:Microsoft.ML.TextCatalog.NormalizeText%2A> | Изменение регистра, удаление диакритических знаков, знаков препинания и цифр |
| <xref:Microsoft.ML.TextCatalog.ProduceNgrams%2A> | Преобразование текстового столбца в контейнер n-грамм (ряд последовательных слов)|
| <xref:Microsoft.ML.TextCatalog.ProduceWordBags%2A> | Преобразование текстового столбца в контейнер векторов n-грамм |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedNgrams%2A> | Преобразование текстового столбца в вектор счетчиков хэшированных n-грамм |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedWordBags%2A> | Преобразование текстового столбца в контейнер счетчиков хэшированных n-грамм |
| <xref:Microsoft.ML.TextCatalog.RemoveDefaultStopWords%2A>  | Удаление стоп-слов по умолчанию для указанного языка из входных столбцов |
| <xref:Microsoft.ML.TextCatalog.RemoveStopWords%2A> | Удаление указанного стоп-слова из входных столбцов |
| <xref:Microsoft.ML.TextCatalog.LatentDirichletAllocation%2A> | Преобразование документа (в виде вектора значений с плавающей запятой) в вектор значений с плавающей запятой на основе набора тем |
| <xref:Microsoft.ML.TextCatalog.ApplyWordEmbedding%2A> | Преобразование векторов токенов текста в векторы предложений с помощью предварительно обученной модели |

## <a name="image-transformations"></a>Преобразование изображений

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale%2A> | Преобразование изображения в оттенки серого |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToImage%2A> | Преобразование вектора пикселей в <xref:Microsoft.ML.Transforms.Image.ImageDataViewType> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels%2A> | Преобразование пикселей из входного изображения в вектор чисел |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages%2A> | Загрузка изображений из папки в память |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages%2A> | Изменение размеров изображений |
| <xref:Microsoft.ML.OnnxCatalog.DnnFeaturizeImage%2A> | Применяет предварительно обученную модель глубокой нейронной сети (DNN) для преобразования входного изображения в вектор признаков. |

## <a name="categorical-data-transformations"></a>Преобразование категориальных данных

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding%2A> | Преобразование одного или нескольких текстовых столбцов в векторы с использованием [прямой](https://en.wikipedia.org/wiki/One-hot) кодировки |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotHashEncoding%2A> | Преобразование одного или нескольких текстовых столбцов в векторы с использованием прямой кодировки на основе хэша |

## <a name="time-series-data-transformations"></a>Преобразования данных временных рядов

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectAnomalyBySrCnn%2A> | Обнаружение аномалий во входных данных временных рядов с помощью алгоритма спектрального остатка (SR) |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectChangePointBySsa%2A> | Обнаружение точек изменений в данных временных рядов с помощью анализа сингулярного спектра (SSA) |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectIidChangePoint%2A> | Обнаружение точек изменения в независимых и одинаково распределенных (IID) данных временных рядов с использованием адаптивных оценок плотности ядра и показателей мартингала |
| <xref:Microsoft.ML.TimeSeriesCatalog.ForecastBySsa%2A> | Прогнозирование данных временных рядов с помощью анализа сингулярного спектра (SSA) |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectSpikeBySsa%2A> | Обнаружение пиков данных временных рядов с помощью анализа сингулярного спектра (SSA) |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectIidSpike%2A> | Обнаружение пиков в независимых и одинаково распределенных (IID) данных временных рядов с использованием адаптивных оценок плотности ядра и показателей мартингала |

## <a name="missing-values"></a>Отсутствующие значения

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.ExtensionsCatalog.IndicateMissingValues%2A> | Создание логического выходного столбца, который будет иметь значение true, если во входном столбце не указано значение |
| <xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A> | Создание выходного столбца, значение которого будет задано по умолчанию, если отсутствует значение из входного столбца. В противном случае по умолчанию будет задано значение из входного столбца. |

## <a name="feature-selection"></a>Выбор признаков

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnCount%2A> | Выбор признаков, у которых значения, заданные не по умолчанию, превышают порог |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnMutualInformation%2A> | Выбор признаков, от которых больше всего зависят данные в столбце метки |

## <a name="feature-transformations"></a>Преобразования признаков

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.KernelExpansionCatalog.ApproximatedKernelMap%2A> | Сопоставление каждого входного вектора с пространством признаков нижнего измерения, где внутренние продукты приближены к функции ядра, чтобы эти признаки можно было использовать в качестве входных для линейных алгоритмов. |
| <xref:Microsoft.ML.PcaCatalog.ProjectToPrincipalComponents%2A> | Уменьшение измерений входного вектора признаков путем применения алгоритма анализа основных компонентов. |

## <a name="explainability-transformations"></a>Преобразования объясняемости

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.ExplainabilityCatalog.CalculateFeatureContribution%2A> | Вычисление результатов вклада для каждого элемента вектора признаков |

## <a name="calibration-transformations"></a>Преобразования калибровки

| Transform | Определение |
| --- | --- |
|<xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Platt%28System.String%2CSystem.String%2CSystem.String%29> | Преобразует необработанный показатель двоичного классификатора в вероятность класса с помощью логистической регрессии с параметрами, оцененными с помощью обучающих данных |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Platt%28System.Double%2CSystem.Double%2CSystem.String%29> | Преобразует необработанный показатель двоичного классификатора в вероятность класса с помощью логистической регрессии с фиксированными параметрами |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Naive%2A> | Преобразует необработанный показатель двоичного классификатора в вероятность класса путем назначения оценки ячейкам и вычисления вероятности на основе распределения между ячейками. |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Isotonic%2A> | Преобразует необработанную оценку двоичного классификатора в вероятность класса путем назначения оценки ячейкам, где расположение границ и размер ячеек оцениваются с помощью обучающих данных.  |

## <a name="deep-learning-transformations"></a>Преобразование глубокого обучения

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel%2A> | Преобразование входных данных в импортированную модель ONNX |
| <xref:Microsoft.ML.TensorflowCatalog.LoadTensorFlowModel%2A> | Преобразование входных данных в импортированную модель TensorFlow |

## <a name="custom-transformations"></a>Пользовательские преобразования

| Transform | Определение |
| --- | --- |
| <xref:Microsoft.ML.CustomMappingCatalog.CustomMapping%2A> | Преобразование существующих столбцов в новые с помощью пользовательского сопоставления |
