---
title: Использование API автоматизированного машинного обучения в ML.NET
description: API автоматизированного машинного обучения в ML.NET автоматизирует процесс создания моделей и создает модель, готовую к развертыванию. Сведения о параметрах, которые можно использовать для настройки задач автоматизированного машинного обучения.
ms.date: 11/7/2019
ms.custom: mvc,how-to
ms.openlocfilehash: c1c18decc48bc1499aa55210becff305cdec4a53
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977119"
---
# <a name="how-to-use-the-mlnet-automated-machine-learning-api"></a>Использование API автоматизированного машинного обучения в ML.NET

Автоматизированное машинное обучение (AutoML) автоматизирует процесс применения машинного обучения к данным. При наличии набора данных вы можете провести **эксперимент** AutoML для выполнения итераций по различным способам определения признаков, алгоритмам машинного обучения и гиперпараметрам для выбора оптимальной модели.

> [!NOTE]
> Этот раздел ссылается на API автоматизированного машинного обучения для ML.NET, который сейчас находится на этапе предварительной версии. Изложенная здесь информация может изменяться.

## <a name="load-data"></a>Загрузка данных

Автоматизированное машинное обучение поддерживает загрузку набора данных в [IDataView](xref:Microsoft.ML.IDataView). Данные могут иметь форму файлов данных с разделением знаками табуляции (TSV) и файлов данных с разделителями-запятыми (CSV).

Пример.

```csharp
using Microsoft.ML;
using Microsoft.ML.AutoML;
    // ...
    MLContext mlContext = new MLContext();
    IDataView trainDataView = mlContext.Data.LoadFromTextFile<SentimentIssue>("my-data-file.csv", hasHeader: true);
```

## <a name="select-the-machine-learning-task-type"></a>Выбор типа задачи машинного обучения

Прежде чем создавать эксперимент, определите, какую задачу машинного обучения нужно решить. Автоматизированное машинное обучение поддерживает следующие задачи машинного обучения:

* Двоичная классификация
* Многоклассовая классификация
* Регрессия

## <a name="create-experiment-settings"></a>Создание параметров эксперимента

Создайте параметры эксперимента для определенного типа задачи машинного обучения:

* Двоичная классификация

  ```csharp
  var experimentSettings = new BinaryExperimentSettings();
  ```

* Многоклассовая классификация

  ```csharp
  var experimentSettings = new MulticlassExperimentSettings();
  ```

* Регрессия

  ```csharp
  var experimentSettings = new RegressionExperimentSettings();
  ```

## <a name="configure-experiment-settings"></a>Настройка параметров эксперимента

Эксперименты можно гибко настраивать. Полный список параметров конфигурации см. в [документации по API AutoML](https://docs.microsoft.com/dotnet/api/microsoft.ml.automl?view=ml-dotnet-preview).

Ниже приведены некоторые примеры таких ситуаций.

1. Укажите максимальное время выполнения эксперимента.

    ```csharp
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    ```

1. Используйте токен отмены для отмены эксперимента до запланированного завершения.

    ```csharp
    experimentSettings.CancellationToken = cts.Token;

    // Cancel experiment after the user presses any key
    CancelExperimentAfterAnyKeyPress(cts);
    ```

1. Укажите другую метрику оптимизации.

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.OptimizingMetric = RegressionMetric.MeanSquaredError;
    ```

1. Параметр `CacheDirectory` является указателем на каталог, где будут храниться все модели, обученные в рамках задачи AutoML. Если для `CacheDirectory` задано значение NULL, модели будут храниться в памяти, а не записываться на диск.

    ```csharp
    experimentSettings.CacheDirectory = null;
    ```

1. Укажите автоматизированному машинному обучению не использовать определенные алгоритмы обучения.

    Стандартный оптимизируемый список алгоритмов обучения рассматривается для каждой конкретной задачи. Этот список можно изменить для конкретного эксперимента. Например, из списка можно удалить алгоритмы обучения, которые медленно выполняются для вашего набора данных. Чтобы выполнить оптимизацию под один конкретный алгоритм обучения, вызовите `experimentSettings.Trainers.Clear()`, а затем добавьте требуемый алгоритм обучения.

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.Trainers.Remove(RegressionTrainer.LbfgsPoissonRegression);
    experimentSettings.Trainers.Remove(RegressionTrainer.OnlineGradientDescent);
    ```

Список поддерживаемых алгоритмов обучения каждой задачи машинного обучения приведен по соответствующей ссылке ниже.

* [Поддерживаемые алгоритмы двоичной классификации](xref:Microsoft.ML.AutoML.BinaryClassificationTrainer)
* [Поддерживаемые алгоритмы многоклассовой классификации](xref:Microsoft.ML.AutoML.MulticlassClassificationTrainer)
* [Поддерживаемые алгоритмы регрессии](xref:Microsoft.ML.AutoML.RegressionTrainer)

## <a name="optimizing-metric"></a>Метрика оптимизации

Как показано в примере выше, метрика оптимизации определяет метрику, оптимизируемую при обучении модели. Доступная для выбора метрика оптимизации определяется выбранным вами типом задачи. Ниже приведен список доступных метрик.

|[Двоичная классификация](xref:Microsoft.ML.AutoML.BinaryClassificationMetric) | [Многоклассовая классификация](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric) |[Регрессия](xref:Microsoft.ML.AutoML.RegressionMetric)
|-- |-- |--
|Достоверность| LogLoss | RSquared
|AreaUnderPrecisionRecallCurve | LogLossReduction | MeanAbsoluteError
|AreaUnderRocCurve | MacroAccuracy | MeanSquaredError
|F1Score | MicroAccuracy | RootMeanSquaredError
|NegativePrecision | TopKAccuracy
|NegativeRecall |
|PositivePrecision
|PositiveRecall

## <a name="data-pre-processing-and-featurization"></a>Предварительная обработка данных и определение признаков

> [!NOTE]
> В столбце признака поддерживаются только типы <xref:System.Boolean>, <xref:System.Single> и <xref:System.String>.

Предварительная обработка данных выполняется по умолчанию, при этом следующие действия выполняются автоматически:

1. отсев признаков без полезной информации;

    отсев признаков без полезной информации из наборов для обучения и проверки. Сюда входят признаки, для которых отсутствуют все значения, во всех строках указано одинаковое значение или наблюдается чрезвычайно высокая кратность (например, хэши, идентификаторы или GUID).

1. Определение и подстановка отсутствующих значений

    Заполнение ячеек с отсутствующими значениями значением по умолчанию для указанного типа данных. Добавление признаков-индикаторов с тем же числом ячеек, что и у входного столбца. Значение в добавленных признаках-индикаторах равно `1`, если значение во входном столбце отсутствует, и `0` в противном случае.

1. Создание дополнительных признаков

    Для текстовых признаков: признаки набора слов с использованием униграмм и трехсимвольных грамм (триграмм).

    Для категориальных признаков: прямое кодирование для функций с низкой кратностью и прямое кодирование с хэшем для категориальных признаков с высокой кратностью.

1. Преобразования и кодировки

    Текстовые признаки с очень малым числом уникальных значений преобразуются в категориальные признаки. В зависимости от кратности категориальных признаков выполните прямое кодирование или прямое кодирование с хэшем.

## <a name="exit-criteria"></a>Условия выхода

Определите критерии для выполнения своей задачи:

1. Выход по истечении периода времени: используя `MaxExperimentTimeInSeconds` в параметрах эксперимента, можно определить время выполнения задачи в секундах.

1. Выход по токену отмены: можно использовать токен отмены, который позволяет отменить задачу до ее запланированного завершения.

    ```csharp
    var cts = new CancellationTokenSource();
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    experimentSettings.CancellationToken = cts.Token;
    ```

## <a name="create-an-experiment"></a>Создание эксперимента

После настройки параметров эксперимента вы готовы создать эксперимент.

```csharp
RegressionExperiment experiment = mlContext.Auto().CreateRegressionExperiment(experimentSettings);
```

## <a name="run-the-experiment"></a>Запуск эксперимента

Запуск эксперимента активирует предварительную обработку данных, выбор алгоритмов обучения и настройку гиперпараметров. AutoML продолжит создавать сочетания определения признаков, алгоритмов машинного обучения и гиперпараметров до достижения `MaxExperimentTimeInSeconds` или прекращения эксперимента.

```csharp
ExperimentResult<RegressionMetrics> experimentResult = experiment
    .Execute(trainingDataView, LabelColumnName, progressHandler: progressHandler);
```

Изучите другие перегрузки `Execute()`, если хотите передать данные проверки, сведения о назначении столбцов или алгоритмы предварительного определения признаков.

## <a name="training-modes"></a>Режимы обучения

### <a name="training-dataset"></a>Обучающий набор данных

AutoML предоставляет перегруженный метод выполнения эксперимента, который позволяет вам предоставлять обучающие данные. На внутреннем уровне система автоматизированного машинного обучения делит данные на части для обучения и проверки.

```csharp
experiment.Execute(trainDataView);
```

### <a name="custom-validation-dataset"></a>Настраиваемый набор данных для проверки

Используйте настраиваемый набор данных для проверки, если случайное разбиение недопустимо, как это обычно бывает с данными временных рядов. Вы можете указать собственный набор данных для проверки. Модель будет оценена относительно указанного набора данных для проверки вместо одного или нескольких случайных наборов данных.

```csharp
experiment.Execute(trainDataView, validationDataView);
```

## <a name="explore-model-metrics"></a>Изучение метрик модели

После каждой итерации эксперимента машинного обучения метрики, связанные с соответствующей задачей, сохраняются.

Например, можно обратиться к метрикам проверки из лучшего выполнения:

```csharp
RegressionMetrics metrics = experimentResult.BestRun.ValidationMetrics;
Console.WriteLine($"R-Squared: {metrics.RSquared:0.##}");
Console.WriteLine($"Root Mean Squared Error: {metrics.RootMeanSquaredError:0.##}");
```

Ниже приведены все доступные метрики для каждой задачи машинного обучения.

* [Метрики двоичной классификации](xref:Microsoft.ML.AutoML.BinaryClassificationMetric)
* [Метрики многоклассовой классификации](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric)
* [Метрики регрессии](xref:Microsoft.ML.AutoML.RegressionMetric)

## <a name="see-also"></a>См. также

Полные примеры кода и не только см. в репозитории GitHub [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state).
