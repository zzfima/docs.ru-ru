---
title: Использование API автоматизированного машинного обучения в ML.NET
description: API автоматизированного машинного обучения в ML.NET автоматизирует процесс создания моделей и создает модель, готовую к развертыванию. Сведения о параметрах, которые можно использовать для настройки задач автоматизированного машинного обучения.
ms.date: 12/18/2019
ms.custom: mvc,how-to
ms.openlocfilehash: b322c484282d025033d747d2093f7b5b4d216fde
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636566"
---
# <a name="how-to-use-the-mlnet-automated-machine-learning-api"></a><span data-ttu-id="bc168-104">Использование API автоматизированного машинного обучения в ML.NET</span><span class="sxs-lookup"><span data-stu-id="bc168-104">How to use the ML.NET automated machine learning API</span></span>

<span data-ttu-id="bc168-105">Автоматизированное машинное обучение (AutoML) автоматизирует процесс применения машинного обучения к данным.</span><span class="sxs-lookup"><span data-stu-id="bc168-105">Automated machine learning (AutoML) automates the process of applying machine learning to data.</span></span> <span data-ttu-id="bc168-106">При наличии набора данных вы можете провести **эксперимент** AutoML для выполнения итераций по различным способам определения признаков, алгоритмам машинного обучения и гиперпараметрам для выбора оптимальной модели.</span><span class="sxs-lookup"><span data-stu-id="bc168-106">Given a dataset, you can run an AutoML **experiment** to iterate over different data featurizations, machine learning algorithms, and hyperparameters to select the best model.</span></span>

> [!NOTE]
> <span data-ttu-id="bc168-107">Этот раздел ссылается на API автоматизированного машинного обучения для ML.NET, который сейчас находится на этапе предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="bc168-107">This topic refers to the automated machine learning API for ML.NET, which is currently in preview.</span></span> <span data-ttu-id="bc168-108">Изложенная здесь информация может изменяться.</span><span class="sxs-lookup"><span data-stu-id="bc168-108">Material may be subject to change.</span></span>

## <a name="load-data"></a><span data-ttu-id="bc168-109">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="bc168-109">Load data</span></span>

<span data-ttu-id="bc168-110">Автоматизированное машинное обучение поддерживает загрузку набора данных в [IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="bc168-110">Automated machine learning supports loading a dataset into an [IDataView](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="bc168-111">Данные могут иметь форму файлов данных с разделением знаками табуляции (TSV) и файлов данных с разделителями-запятыми (CSV).</span><span class="sxs-lookup"><span data-stu-id="bc168-111">Data can be in the form of tab-separated value (TSV) files and comma separated value (CSV) files.</span></span>

<span data-ttu-id="bc168-112">Пример.</span><span class="sxs-lookup"><span data-stu-id="bc168-112">Example:</span></span>

```csharp
using Microsoft.ML;
using Microsoft.ML.AutoML;
    // ...
    MLContext mlContext = new MLContext();
    IDataView trainDataView = mlContext.Data.LoadFromTextFile<SentimentIssue>("my-data-file.csv", hasHeader: true);
```

## <a name="select-the-machine-learning-task-type"></a><span data-ttu-id="bc168-113">Выбор типа задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="bc168-113">Select the machine learning task type</span></span>

<span data-ttu-id="bc168-114">Прежде чем создавать эксперимент, определите, какую задачу машинного обучения нужно решить.</span><span class="sxs-lookup"><span data-stu-id="bc168-114">Before creating an experiment, determine the kind of machine learning problem you want to solve.</span></span> <span data-ttu-id="bc168-115">Автоматизированное машинное обучение поддерживает следующие задачи машинного обучения:</span><span class="sxs-lookup"><span data-stu-id="bc168-115">Automated machine learning supports the following ML tasks:</span></span>

* <span data-ttu-id="bc168-116">Двоичная классификация</span><span class="sxs-lookup"><span data-stu-id="bc168-116">Binary Classification</span></span>
* <span data-ttu-id="bc168-117">Многоклассовая классификация</span><span class="sxs-lookup"><span data-stu-id="bc168-117">Multiclass Classification</span></span>
* <span data-ttu-id="bc168-118">Регрессия</span><span class="sxs-lookup"><span data-stu-id="bc168-118">Regression</span></span>
* <span data-ttu-id="bc168-119">Рекомендация</span><span class="sxs-lookup"><span data-stu-id="bc168-119">Recommendation</span></span>

## <a name="create-experiment-settings"></a><span data-ttu-id="bc168-120">Создание параметров эксперимента</span><span class="sxs-lookup"><span data-stu-id="bc168-120">Create experiment settings</span></span>

<span data-ttu-id="bc168-121">Создайте параметры эксперимента для определенного типа задачи машинного обучения:</span><span class="sxs-lookup"><span data-stu-id="bc168-121">Create experiment settings for the determined ML task type:</span></span>

* <span data-ttu-id="bc168-122">Двоичная классификация</span><span class="sxs-lookup"><span data-stu-id="bc168-122">Binary Classification</span></span>

  ```csharp
  var experimentSettings = new BinaryExperimentSettings();
  ```

* <span data-ttu-id="bc168-123">Многоклассовая классификация</span><span class="sxs-lookup"><span data-stu-id="bc168-123">Multiclass Classification</span></span>

  ```csharp
  var experimentSettings = new MulticlassExperimentSettings();
  ```

* <span data-ttu-id="bc168-124">Регрессия</span><span class="sxs-lookup"><span data-stu-id="bc168-124">Regression</span></span>

  ```csharp
  var experimentSettings = new RegressionExperimentSettings();
  ```

* <span data-ttu-id="bc168-125">Рекомендация</span><span class="sxs-lookup"><span data-stu-id="bc168-125">Recommendation</span></span>

  ```csharp
  var experimentSettings = new RecommendationExperimentSettings();
  ```

## <a name="configure-experiment-settings"></a><span data-ttu-id="bc168-126">Настройка параметров эксперимента</span><span class="sxs-lookup"><span data-stu-id="bc168-126">Configure experiment settings</span></span>

<span data-ttu-id="bc168-127">Эксперименты можно гибко настраивать.</span><span class="sxs-lookup"><span data-stu-id="bc168-127">Experiments are highly configurable.</span></span> <span data-ttu-id="bc168-128">Полный список параметров конфигурации см. в [документации по API AutoML](https://docs.microsoft.com/dotnet/api/microsoft.ml.automl?view=ml-dotnet-preview).</span><span class="sxs-lookup"><span data-stu-id="bc168-128">See the [AutoML API docs](https://docs.microsoft.com/dotnet/api/microsoft.ml.automl?view=ml-dotnet-preview) for a full list of configuration settings.</span></span>

<span data-ttu-id="bc168-129">Ниже приведены некоторые примеры таких ситуаций.</span><span class="sxs-lookup"><span data-stu-id="bc168-129">Some examples include:</span></span>

1. <span data-ttu-id="bc168-130">Укажите максимальное время выполнения эксперимента.</span><span class="sxs-lookup"><span data-stu-id="bc168-130">Specify the maximum time that the experiment is allowed to run.</span></span>

    ```csharp
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    ```

1. <span data-ttu-id="bc168-131">Используйте токен отмены для отмены эксперимента до запланированного завершения.</span><span class="sxs-lookup"><span data-stu-id="bc168-131">Use a cancellation token to cancel the experiment before it is scheduled to finish.</span></span>

    ```csharp
    experimentSettings.CancellationToken = cts.Token;

    // Cancel experiment after the user presses any key
    CancelExperimentAfterAnyKeyPress(cts);
    ```

1. <span data-ttu-id="bc168-132">Укажите другую метрику оптимизации.</span><span class="sxs-lookup"><span data-stu-id="bc168-132">Specify a different optimizing metric.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.OptimizingMetric = RegressionMetric.MeanSquaredError;
    ```

1. <span data-ttu-id="bc168-133">Параметр `CacheDirectory` является указателем на каталог, где будут храниться все модели, обученные в рамках задачи AutoML.</span><span class="sxs-lookup"><span data-stu-id="bc168-133">The `CacheDirectory` setting is a pointer to a directory where all models trained during the AutoML task will be saved.</span></span> <span data-ttu-id="bc168-134">Если для `CacheDirectory` задано значение NULL, модели будут храниться в памяти, а не записываться на диск.</span><span class="sxs-lookup"><span data-stu-id="bc168-134">If `CacheDirectory` is set to null, models will be kept in memory instead of written to disk.</span></span>

    ```csharp
    experimentSettings.CacheDirectory = null;
    ```

1. <span data-ttu-id="bc168-135">Укажите автоматизированному машинному обучению не использовать определенные алгоритмы обучения.</span><span class="sxs-lookup"><span data-stu-id="bc168-135">Instruct automated ML not to use certain trainers.</span></span>

    <span data-ttu-id="bc168-136">Стандартный оптимизируемый список алгоритмов обучения рассматривается для каждой конкретной задачи.</span><span class="sxs-lookup"><span data-stu-id="bc168-136">A default list of trainers to optimize are explored per task.</span></span> <span data-ttu-id="bc168-137">Этот список можно изменить для конкретного эксперимента.</span><span class="sxs-lookup"><span data-stu-id="bc168-137">This list can be modified for each experiment.</span></span> <span data-ttu-id="bc168-138">Например, из списка можно удалить алгоритмы обучения, которые медленно выполняются для вашего набора данных.</span><span class="sxs-lookup"><span data-stu-id="bc168-138">For instance, trainers that run slowly on your dataset can be removed from the list.</span></span> <span data-ttu-id="bc168-139">Чтобы выполнить оптимизацию под один конкретный алгоритм обучения, вызовите `experimentSettings.Trainers.Clear()`, а затем добавьте требуемый алгоритм обучения.</span><span class="sxs-lookup"><span data-stu-id="bc168-139">To optimize on one specific trainer call `experimentSettings.Trainers.Clear()`, then add the trainer that you want to use.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.Trainers.Remove(RegressionTrainer.LbfgsPoissonRegression);
    experimentSettings.Trainers.Remove(RegressionTrainer.OnlineGradientDescent);
    ```

<span data-ttu-id="bc168-140">Список поддерживаемых алгоритмов обучения каждой задачи машинного обучения приведен по соответствующей ссылке ниже.</span><span class="sxs-lookup"><span data-stu-id="bc168-140">The list of supported trainers per ML task can be found at the corresponding link below:</span></span>

* [<span data-ttu-id="bc168-141">Поддерживаемые алгоритмы двоичной классификации</span><span class="sxs-lookup"><span data-stu-id="bc168-141">Supported Binary Classification Algorithms</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationTrainer)
* [<span data-ttu-id="bc168-142">Поддерживаемые алгоритмы многоклассовой классификации</span><span class="sxs-lookup"><span data-stu-id="bc168-142">Supported Multiclass Classification Algorithms</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationTrainer)
* [<span data-ttu-id="bc168-143">Поддерживаемые алгоритмы регрессии</span><span class="sxs-lookup"><span data-stu-id="bc168-143">Supported Regression Algorithms</span></span>](xref:Microsoft.ML.AutoML.RegressionTrainer)
* [<span data-ttu-id="bc168-144">Поддерживаемые алгоритмы рекомендаций</span><span class="sxs-lookup"><span data-stu-id="bc168-144">Supported Recommendation Algorithms</span></span>](xref:Microsoft.ML.AutoML.RecommendationTrainer)

## <a name="optimizing-metric"></a><span data-ttu-id="bc168-145">Метрика оптимизации</span><span class="sxs-lookup"><span data-stu-id="bc168-145">Optimizing metric</span></span>

<span data-ttu-id="bc168-146">Как показано в примере выше, метрика оптимизации определяет метрику, оптимизируемую при обучении модели.</span><span class="sxs-lookup"><span data-stu-id="bc168-146">The optimizing metric, as shown in the example above, determines the metric to be optimized during model training.</span></span> <span data-ttu-id="bc168-147">Доступная для выбора метрика оптимизации определяется выбранным вами типом задачи.</span><span class="sxs-lookup"><span data-stu-id="bc168-147">The optimizing metric you can select is determined by the task type you choose.</span></span> <span data-ttu-id="bc168-148">Ниже приведен список доступных метрик.</span><span class="sxs-lookup"><span data-stu-id="bc168-148">Below is a list of available metrics.</span></span>

|[<span data-ttu-id="bc168-149">Двоичная классификация</span><span class="sxs-lookup"><span data-stu-id="bc168-149">Binary Classification</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationMetric) | [<span data-ttu-id="bc168-150">Многоклассовая классификация</span><span class="sxs-lookup"><span data-stu-id="bc168-150">Multiclass Classification</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric) |[<span data-ttu-id="bc168-151">Рекомендации и регрессии</span><span class="sxs-lookup"><span data-stu-id="bc168-151">Regression & Recommendation</span></span>](xref:Microsoft.ML.AutoML.RegressionMetric)
|-- |-- |--
|<span data-ttu-id="bc168-152">Достоверность</span><span class="sxs-lookup"><span data-stu-id="bc168-152">Accuracy</span></span>| <span data-ttu-id="bc168-153">LogLoss</span><span class="sxs-lookup"><span data-stu-id="bc168-153">LogLoss</span></span> | <span data-ttu-id="bc168-154">RSquared</span><span class="sxs-lookup"><span data-stu-id="bc168-154">RSquared</span></span>
|<span data-ttu-id="bc168-155">AreaUnderPrecisionRecallCurve</span><span class="sxs-lookup"><span data-stu-id="bc168-155">AreaUnderPrecisionRecallCurve</span></span> | <span data-ttu-id="bc168-156">LogLossReduction</span><span class="sxs-lookup"><span data-stu-id="bc168-156">LogLossReduction</span></span> | <span data-ttu-id="bc168-157">MeanAbsoluteError</span><span class="sxs-lookup"><span data-stu-id="bc168-157">MeanAbsoluteError</span></span>
|<span data-ttu-id="bc168-158">AreaUnderRocCurve</span><span class="sxs-lookup"><span data-stu-id="bc168-158">AreaUnderRocCurve</span></span> | <span data-ttu-id="bc168-159">MacroAccuracy</span><span class="sxs-lookup"><span data-stu-id="bc168-159">MacroAccuracy</span></span> | <span data-ttu-id="bc168-160">MeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="bc168-160">MeanSquaredError</span></span>
|<span data-ttu-id="bc168-161">F1Score</span><span class="sxs-lookup"><span data-stu-id="bc168-161">F1Score</span></span> | <span data-ttu-id="bc168-162">MicroAccuracy</span><span class="sxs-lookup"><span data-stu-id="bc168-162">MicroAccuracy</span></span> | <span data-ttu-id="bc168-163">RootMeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="bc168-163">RootMeanSquaredError</span></span>
|<span data-ttu-id="bc168-164">NegativePrecision</span><span class="sxs-lookup"><span data-stu-id="bc168-164">NegativePrecision</span></span> | <span data-ttu-id="bc168-165">TopKAccuracy</span><span class="sxs-lookup"><span data-stu-id="bc168-165">TopKAccuracy</span></span>
|<span data-ttu-id="bc168-166">NegativeRecall</span><span class="sxs-lookup"><span data-stu-id="bc168-166">NegativeRecall</span></span> |
|<span data-ttu-id="bc168-167">PositivePrecision</span><span class="sxs-lookup"><span data-stu-id="bc168-167">PositivePrecision</span></span>
|<span data-ttu-id="bc168-168">PositiveRecall</span><span class="sxs-lookup"><span data-stu-id="bc168-168">PositiveRecall</span></span>

## <a name="data-pre-processing-and-featurization"></a><span data-ttu-id="bc168-169">Предварительная обработка данных и определение признаков</span><span class="sxs-lookup"><span data-stu-id="bc168-169">Data pre-processing and featurization</span></span>

> [!NOTE]
> <span data-ttu-id="bc168-170">В столбце признака поддерживаются только типы <xref:System.Boolean>, <xref:System.Single> и <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="bc168-170">The feature column only supported types of <xref:System.Boolean>, <xref:System.Single>, and <xref:System.String>.</span></span>

<span data-ttu-id="bc168-171">Предварительная обработка данных выполняется по умолчанию, при этом следующие действия выполняются автоматически:</span><span class="sxs-lookup"><span data-stu-id="bc168-171">Data pre-processing happens by default and the following steps are performed automatically for you:</span></span>

1. <span data-ttu-id="bc168-172">отсев признаков без полезной информации;</span><span class="sxs-lookup"><span data-stu-id="bc168-172">Drop features with no useful information</span></span>

    <span data-ttu-id="bc168-173">отсев признаков без полезной информации из наборов для обучения и проверки.</span><span class="sxs-lookup"><span data-stu-id="bc168-173">Drop features with no useful information from training and validation sets.</span></span> <span data-ttu-id="bc168-174">Сюда входят признаки, для которых отсутствуют все значения, во всех строках указано одинаковое значение или наблюдается чрезвычайно высокая кратность (например, хэши, идентификаторы или GUID).</span><span class="sxs-lookup"><span data-stu-id="bc168-174">These include features with all values missing, same value across all rows or with extremely high cardinality (e.g., hashes, IDs or GUIDs).</span></span>

1. <span data-ttu-id="bc168-175">Определение и подстановка отсутствующих значений</span><span class="sxs-lookup"><span data-stu-id="bc168-175">Missing value indication and imputation</span></span>

    <span data-ttu-id="bc168-176">Заполнение ячеек с отсутствующими значениями значением по умолчанию для указанного типа данных.</span><span class="sxs-lookup"><span data-stu-id="bc168-176">Fill missing value cells with the default value for the datatype.</span></span> <span data-ttu-id="bc168-177">Добавление признаков-индикаторов с тем же числом ячеек, что и у входного столбца.</span><span class="sxs-lookup"><span data-stu-id="bc168-177">Append indicator features with the same number of slots as the input column.</span></span> <span data-ttu-id="bc168-178">Значение в добавленных признаках-индикаторах равно `1`, если значение во входном столбце отсутствует, и `0` в противном случае.</span><span class="sxs-lookup"><span data-stu-id="bc168-178">The value in the appended indicator features is `1` if the value in the input column is missing and `0` otherwise.</span></span>

1. <span data-ttu-id="bc168-179">Создание дополнительных признаков</span><span class="sxs-lookup"><span data-stu-id="bc168-179">Generate additional features</span></span>

    <span data-ttu-id="bc168-180">Для текстовых признаков: признаки набора слов с использованием униграмм и трехсимвольных грамм (триграмм).</span><span class="sxs-lookup"><span data-stu-id="bc168-180">For text features: Bag-of-word features using unigrams and tri-character-grams.</span></span>

    <span data-ttu-id="bc168-181">Для категориальных признаков: прямое кодирование для функций с низкой кратностью и прямое кодирование с хэшем для категориальных признаков с высокой кратностью.</span><span class="sxs-lookup"><span data-stu-id="bc168-181">For categorical features: One-hot encoding for low cardinality features, and one-hot-hash encoding for high cardinality categorical features.</span></span>

1. <span data-ttu-id="bc168-182">Преобразования и кодировки</span><span class="sxs-lookup"><span data-stu-id="bc168-182">Transformations and encodings</span></span>

    <span data-ttu-id="bc168-183">Текстовые признаки с очень малым числом уникальных значений преобразуются в категориальные признаки.</span><span class="sxs-lookup"><span data-stu-id="bc168-183">Text features with very few unique values transformed into categorical features.</span></span> <span data-ttu-id="bc168-184">В зависимости от кратности категориальных признаков выполните прямое кодирование или прямое кодирование с хэшем.</span><span class="sxs-lookup"><span data-stu-id="bc168-184">Depending on cardinality of categorical features, perform one-hot encoding or one-hot hash encoding.</span></span>

## <a name="exit-criteria"></a><span data-ttu-id="bc168-185">Условия выхода</span><span class="sxs-lookup"><span data-stu-id="bc168-185">Exit criteria</span></span>

<span data-ttu-id="bc168-186">Определите критерии для выполнения своей задачи:</span><span class="sxs-lookup"><span data-stu-id="bc168-186">Define the criteria to complete your task:</span></span>

1. <span data-ttu-id="bc168-187">Выход по истечении периода времени: используя `MaxExperimentTimeInSeconds` в параметрах эксперимента, можно определить время выполнения задачи в секундах.</span><span class="sxs-lookup"><span data-stu-id="bc168-187">Exit after a length of time - Using `MaxExperimentTimeInSeconds` in your experiment settings you can define how long in seconds that an task should continue to run.</span></span>

1. <span data-ttu-id="bc168-188">Выход по токену отмены: можно использовать токен отмены, который позволяет отменить задачу до ее запланированного завершения.</span><span class="sxs-lookup"><span data-stu-id="bc168-188">Exit on a cancellation token -  You can use a cancellation token that lets you cancel the task before it is scheduled to finish.</span></span>

    ```csharp
    var cts = new CancellationTokenSource();
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    experimentSettings.CancellationToken = cts.Token;
    ```

## <a name="create-an-experiment"></a><span data-ttu-id="bc168-189">Создание эксперимента</span><span class="sxs-lookup"><span data-stu-id="bc168-189">Create an experiment</span></span>

<span data-ttu-id="bc168-190">После настройки параметров эксперимента вы готовы создать эксперимент.</span><span class="sxs-lookup"><span data-stu-id="bc168-190">Once you have configured the experiment settings, you are ready to create the experiment.</span></span>

```csharp
RegressionExperiment experiment = mlContext.Auto().CreateRegressionExperiment(experimentSettings);
```

## <a name="run-the-experiment"></a><span data-ttu-id="bc168-191">Запуск эксперимента</span><span class="sxs-lookup"><span data-stu-id="bc168-191">Run the experiment</span></span>

<span data-ttu-id="bc168-192">Запуск эксперимента активирует предварительную обработку данных, выбор алгоритмов обучения и настройку гиперпараметров.</span><span class="sxs-lookup"><span data-stu-id="bc168-192">Running the experiment triggers data pre-processing, learning algorithm selection, and hyperparameter tuning.</span></span> <span data-ttu-id="bc168-193">AutoML продолжит создавать сочетания определения признаков, алгоритмов машинного обучения и гиперпараметров до достижения `MaxExperimentTimeInSeconds` или прекращения эксперимента.</span><span class="sxs-lookup"><span data-stu-id="bc168-193">AutoML will continue to generate combinations of featurization, learning algorithms, and hyperparameters until the `MaxExperimentTimeInSeconds` is reached or the experiment is terminated.</span></span>

```csharp
ExperimentResult<RegressionMetrics> experimentResult = experiment
    .Execute(trainingDataView, LabelColumnName, progressHandler: progressHandler);
```

<span data-ttu-id="bc168-194">Изучите другие перегрузки `Execute()`, если хотите передать данные проверки, сведения о назначении столбцов или алгоритмы предварительного определения признаков.</span><span class="sxs-lookup"><span data-stu-id="bc168-194">Explore other overloads for `Execute()` if you want to pass in validation data, column information indicating the column purpose, or prefeaturizers.</span></span>

## <a name="training-modes"></a><span data-ttu-id="bc168-195">Режимы обучения</span><span class="sxs-lookup"><span data-stu-id="bc168-195">Training modes</span></span>

### <a name="training-dataset"></a><span data-ttu-id="bc168-196">Обучающий набор данных</span><span class="sxs-lookup"><span data-stu-id="bc168-196">Training dataset</span></span>

<span data-ttu-id="bc168-197">AutoML предоставляет перегруженный метод выполнения эксперимента, который позволяет вам предоставлять обучающие данные.</span><span class="sxs-lookup"><span data-stu-id="bc168-197">AutoML provides an overloaded experiment execute method which allows you to provide training data.</span></span> <span data-ttu-id="bc168-198">На внутреннем уровне система автоматизированного машинного обучения делит данные на части для обучения и проверки.</span><span class="sxs-lookup"><span data-stu-id="bc168-198">Internally, automated ML divides the data into train-validate splits.</span></span>

```csharp
experiment.Execute(trainDataView);
```

### <a name="custom-validation-dataset"></a><span data-ttu-id="bc168-199">Настраиваемый набор данных для проверки</span><span class="sxs-lookup"><span data-stu-id="bc168-199">Custom validation dataset</span></span>

<span data-ttu-id="bc168-200">Используйте настраиваемый набор данных для проверки, если случайное разбиение недопустимо, как это обычно бывает с данными временных рядов.</span><span class="sxs-lookup"><span data-stu-id="bc168-200">Use custom validation dataset if random split is not acceptable, as is usually the case with time series data.</span></span> <span data-ttu-id="bc168-201">Вы можете указать собственный набор данных для проверки.</span><span class="sxs-lookup"><span data-stu-id="bc168-201">You can specify your own validation dataset.</span></span> <span data-ttu-id="bc168-202">Модель будет оценена относительно указанного набора данных для проверки вместо одного или нескольких случайных наборов данных.</span><span class="sxs-lookup"><span data-stu-id="bc168-202">The model will be evaluated against the validation dataset specified instead of one or more random datasets.</span></span>

```csharp
experiment.Execute(trainDataView, validationDataView);
```

## <a name="explore-model-metrics"></a><span data-ttu-id="bc168-203">Изучение метрик модели</span><span class="sxs-lookup"><span data-stu-id="bc168-203">Explore model metrics</span></span>

<span data-ttu-id="bc168-204">После каждой итерации эксперимента машинного обучения метрики, связанные с соответствующей задачей, сохраняются.</span><span class="sxs-lookup"><span data-stu-id="bc168-204">After each iteration of an ML experiment, metrics relating to that task are stored.</span></span>

<span data-ttu-id="bc168-205">Например, можно обратиться к метрикам проверки из лучшего выполнения:</span><span class="sxs-lookup"><span data-stu-id="bc168-205">For example, we can access validation metrics from the best run:</span></span>

```csharp
RegressionMetrics metrics = experimentResult.BestRun.ValidationMetrics;
Console.WriteLine($"R-Squared: {metrics.RSquared:0.##}");
Console.WriteLine($"Root Mean Squared Error: {metrics.RootMeanSquaredError:0.##}");
```

<span data-ttu-id="bc168-206">Ниже приведены все доступные метрики для каждой задачи машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="bc168-206">The following are all the available metrics per ML task:</span></span>

* [<span data-ttu-id="bc168-207">Метрики двоичной классификации</span><span class="sxs-lookup"><span data-stu-id="bc168-207">Binary classification metrics</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationMetric)
* [<span data-ttu-id="bc168-208">Метрики многоклассовой классификации</span><span class="sxs-lookup"><span data-stu-id="bc168-208">Multiclass classification metrics</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric)
* [<span data-ttu-id="bc168-209">Метрики рекомендаций и регрессии</span><span class="sxs-lookup"><span data-stu-id="bc168-209">Regression & recommendation metrics</span></span>](xref:Microsoft.ML.AutoML.RegressionMetric)

## <a name="see-also"></a><span data-ttu-id="bc168-210">См. также</span><span class="sxs-lookup"><span data-stu-id="bc168-210">See also</span></span>

<span data-ttu-id="bc168-211">Полные примеры кода и не только см. в репозитории GitHub [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state).</span><span class="sxs-lookup"><span data-stu-id="bc168-211">For full code samples and more visit the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state) GitHub repository.</span></span>
