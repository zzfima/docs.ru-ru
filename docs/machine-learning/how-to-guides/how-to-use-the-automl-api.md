---
title: Использование API автоматизированного машинного обучения в ML.NET
description: API автоматизированного машинного обучения в ML.NET автоматизирует процесс создания моделей и создает модель, готовую к развертыванию. Сведения о параметрах, которые можно использовать для настройки задач автоматизированного машинного обучения.
ms.date: 04/24/2019
ms.custom: mvc,how-to
ms.openlocfilehash: d624b999384dd92d41033e385d01fe556e10a065
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960416"
---
# <a name="how-to-use-the-mlnet-automated-machine-learning-api"></a><span data-ttu-id="7b60d-104">Использование API автоматизированного машинного обучения в ML.NET</span><span class="sxs-lookup"><span data-stu-id="7b60d-104">How to use the ML.NET automated machine learning API</span></span>

<span data-ttu-id="7b60d-105">Автоматизированное машинное обучение (AutoML) автоматизирует процесс применения машинного обучения к данным.</span><span class="sxs-lookup"><span data-stu-id="7b60d-105">Automated machine learning (AutoML) automates the process of applying machine learning to data.</span></span> <span data-ttu-id="7b60d-106">При наличии набора данных вы можете провести **эксперимент** AutoML для выполнения итераций по различным способам определения признаков, алгоритмам машинного обучения и гиперпараметрам для выбора оптимальной модели.</span><span class="sxs-lookup"><span data-stu-id="7b60d-106">Given a dataset, you can run an AutoML **experiment** to iterate over different data featurizations, machine learning algorithms, and hyperparameters to select the best model.</span></span>

> [!NOTE]
> <span data-ttu-id="7b60d-107">Этот раздел ссылается на API автоматизированного машинного обучения для ML.NET, который сейчас находится на этапе предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="7b60d-107">This topic refers to the automated machine learning API for ML.NET, which is currently in preview.</span></span> <span data-ttu-id="7b60d-108">Изложенная здесь информация может изменяться.</span><span class="sxs-lookup"><span data-stu-id="7b60d-108">Material may be subject to change.</span></span>

## <a name="load-data"></a><span data-ttu-id="7b60d-109">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="7b60d-109">Load data</span></span>

<span data-ttu-id="7b60d-110">Автоматизированное машинное обучение поддерживает загрузку набора данных в [IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="7b60d-110">Automated machine learning supports loading a dataset into an [IDataView](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="7b60d-111">Данные могут иметь форму файлов данных с разделением знаками табуляции (TSV) и файлов данных с разделителями-запятыми (CSV).</span><span class="sxs-lookup"><span data-stu-id="7b60d-111">Data can be in the form of tab-separated value (TSV) files and comma separated value (CSV) files.</span></span>

<span data-ttu-id="7b60d-112">Пример</span><span class="sxs-lookup"><span data-stu-id="7b60d-112">Example:</span></span>

```csharp
using Microsoft.ML;
using Microsoft.ML.AutoML;
    ...
    MLContext mlContext = new MLContext();
    IDataView trainDataView = mlContext.Data.LoadFromTextFile<SentimentIssue>("my-data-file.csv", hasHeader: true);
```

## <a name="select-the-machine-learning-task-type"></a><span data-ttu-id="7b60d-113">Выбор типа задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="7b60d-113">Select the machine learning task type</span></span>
<span data-ttu-id="7b60d-114">Прежде чем создавать эксперимент, определите, какую задачу машинного обучения нужно решить.</span><span class="sxs-lookup"><span data-stu-id="7b60d-114">Before creating an experiment, determine the kind of machine learning problem you want to solve.</span></span> <span data-ttu-id="7b60d-115">Автоматизированное машинное обучение поддерживает следующие задачи машинного обучения:</span><span class="sxs-lookup"><span data-stu-id="7b60d-115">Automated machine learning supports the following ML tasks:</span></span>
* <span data-ttu-id="7b60d-116">Двоичная классификация</span><span class="sxs-lookup"><span data-stu-id="7b60d-116">Binary Classification</span></span>
* <span data-ttu-id="7b60d-117">Многоклассовая классификация</span><span class="sxs-lookup"><span data-stu-id="7b60d-117">Multiclass Classification</span></span>
* <span data-ttu-id="7b60d-118">Регрессия</span><span class="sxs-lookup"><span data-stu-id="7b60d-118">Regression</span></span>

## <a name="create-experiment-settings"></a><span data-ttu-id="7b60d-119">Создание параметров эксперимента</span><span class="sxs-lookup"><span data-stu-id="7b60d-119">Create experiment settings</span></span>

<span data-ttu-id="7b60d-120">Создайте параметры эксперимента для определенного типа задачи машинного обучения:</span><span class="sxs-lookup"><span data-stu-id="7b60d-120">Create experiment settings for the determined ML task type:</span></span>

* <span data-ttu-id="7b60d-121">Двоичная классификация</span><span class="sxs-lookup"><span data-stu-id="7b60d-121">Binary Classification</span></span>

  ```csharp
  var experimentSettings = new BinaryExperimentSettings();
  ```

* <span data-ttu-id="7b60d-122">Многоклассовая классификация</span><span class="sxs-lookup"><span data-stu-id="7b60d-122">Multiclass Classification</span></span>

  ```csharp
  var experimentSettings = new MulticlassExperimentSettings();
  ```

* <span data-ttu-id="7b60d-123">Регрессия</span><span class="sxs-lookup"><span data-stu-id="7b60d-123">Regression</span></span>

  ```csharp
  var experimentSettings = new RegressionExperimentSettings();
  ```

## <a name="configure-experiment-settings"></a><span data-ttu-id="7b60d-124">Настройка параметров эксперимента</span><span class="sxs-lookup"><span data-stu-id="7b60d-124">Configure experiment settings</span></span>

<span data-ttu-id="7b60d-125">Эксперименты можно гибко настраивать.</span><span class="sxs-lookup"><span data-stu-id="7b60d-125">Experiments are highly configurable.</span></span> <span data-ttu-id="7b60d-126">Полный список параметров конфигурации см. в [документации по API AutoML](https://docs.microsoft.com/dotnet/api/?view=automl-dotnet).</span><span class="sxs-lookup"><span data-stu-id="7b60d-126">See the [AutoML API docs](https://docs.microsoft.com/dotnet/api/?view=automl-dotnet) for a full list of configuration settings.</span></span>

<span data-ttu-id="7b60d-127">Ниже приведены некоторые примеры таких ситуаций.</span><span class="sxs-lookup"><span data-stu-id="7b60d-127">Some examples include:</span></span>

1. <span data-ttu-id="7b60d-128">Укажите максимальное время выполнения эксперимента.</span><span class="sxs-lookup"><span data-stu-id="7b60d-128">Specify the maximum time that the experiment is allowed to run.</span></span>

    ```csharp
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    ```

1. <span data-ttu-id="7b60d-129">Используйте токен отмены для отмены эксперимента до запланированного завершения.</span><span class="sxs-lookup"><span data-stu-id="7b60d-129">Use a cancellation token to cancel the experiment before it is scheduled to finish.</span></span>

    ```csharp
    experimentSettings.CancellationToken = cts.Token;

    // Cancel experiment after the user presses any key
    CancelExperimentAfterAnyKeyPress(cts);
    ```

1. <span data-ttu-id="7b60d-130">Укажите другую метрику оптимизации.</span><span class="sxs-lookup"><span data-stu-id="7b60d-130">Specify a different optimizing metric.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.OptimizingMetric = RegressionMetric.MeanSquaredError;
    ```

1. <span data-ttu-id="7b60d-131">Параметр `CacheDirectory` является указателем на каталог, где будут храниться все модели, обученные в рамках задачи AutoML.</span><span class="sxs-lookup"><span data-stu-id="7b60d-131">The `CacheDirectory` setting is a pointer to a directory where all models trained during the AutoML task will be saved.</span></span> <span data-ttu-id="7b60d-132">Если для `CacheDirectory` задано значение NULL, модели будут храниться в памяти, а не записываться на диск.</span><span class="sxs-lookup"><span data-stu-id="7b60d-132">If `CacheDirectory` is set to null, models will be kept in memory instead of written to disk.</span></span>
 
    ```csharp
    experimentSettings.CacheDirectory = null;
    ```

1. <span data-ttu-id="7b60d-133">Укажите автоматизированному машинному обучению не использовать определенные алгоритмы обучения.</span><span class="sxs-lookup"><span data-stu-id="7b60d-133">Instruct automated ML not to use certain trainers.</span></span>

    <span data-ttu-id="7b60d-134">Стандартный оптимизируемый список алгоритмов обучения рассматривается для каждой конкретной задачи.</span><span class="sxs-lookup"><span data-stu-id="7b60d-134">A default list of trainers to optimize are explored per task.</span></span> <span data-ttu-id="7b60d-135">Этот список можно изменить для конкретного эксперимента.</span><span class="sxs-lookup"><span data-stu-id="7b60d-135">This list can be modified for each experiment.</span></span> <span data-ttu-id="7b60d-136">Например, из списка можно удалить алгоритмы обучения, которые медленно выполняются для вашего набора данных.</span><span class="sxs-lookup"><span data-stu-id="7b60d-136">For instance, trainers that run slowly on your dataset can be removed from the list.</span></span> <span data-ttu-id="7b60d-137">Чтобы выполнить оптимизацию под один конкретный алгоритм обучения, вызовите `experimentSettings.Trainers.Clear()`, а затем добавьте требуемый алгоритм обучения.</span><span class="sxs-lookup"><span data-stu-id="7b60d-137">To optimize on one specific trainer call `experimentSettings.Trainers.Clear()`, then add the trainer that you want to use.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.Trainers.Remove(RegressionTrainer.LbfgsPoissonRegression);
    experimentSettings.Trainers.Remove(RegressionTrainer.OnlineGradientDescent);
    ```

<span data-ttu-id="7b60d-138">Список поддерживаемых алгоритмов обучения каждой задачи машинного обучения приведен по соответствующей ссылке ниже.</span><span class="sxs-lookup"><span data-stu-id="7b60d-138">The list of supported trainers per ML task can be found at the corresponding link below:</span></span>
* [<span data-ttu-id="7b60d-139">Поддерживаемые алгоритмы двоичной классификации</span><span class="sxs-lookup"><span data-stu-id="7b60d-139">Supported Binary Classification Algorithms</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationTrainer)
* [<span data-ttu-id="7b60d-140">Поддерживаемые алгоритмы многоклассовой классификации</span><span class="sxs-lookup"><span data-stu-id="7b60d-140">Supported Multiclass Classification Algorithms</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationTrainer)
* [<span data-ttu-id="7b60d-141">Поддерживаемые алгоритмы регрессии</span><span class="sxs-lookup"><span data-stu-id="7b60d-141">Supported Regression Algorithms</span></span>](xref:Microsoft.ML.AutoML.RegressionTrainer)

## <a name="optimizing-metric"></a><span data-ttu-id="7b60d-142">Метрика оптимизации</span><span class="sxs-lookup"><span data-stu-id="7b60d-142">Optimizing metric</span></span>

<span data-ttu-id="7b60d-143">Как показано в примере выше, метрика оптимизации определяет метрику, оптимизируемую при обучении модели.</span><span class="sxs-lookup"><span data-stu-id="7b60d-143">The optimizing metric, as shown in the example above, determines the metric to be optimized during model training.</span></span> <span data-ttu-id="7b60d-144">Доступная для выбора метрика оптимизации определяется выбранным вами типом задачи.</span><span class="sxs-lookup"><span data-stu-id="7b60d-144">The optimizing metric you can select is determined by the task type you choose.</span></span> <span data-ttu-id="7b60d-145">Ниже приведен список доступных метрик.</span><span class="sxs-lookup"><span data-stu-id="7b60d-145">Below is a list of available metrics.</span></span>

|[<span data-ttu-id="7b60d-146">Двоичная классификация</span><span class="sxs-lookup"><span data-stu-id="7b60d-146">Binary Classification</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationMetric) | [<span data-ttu-id="7b60d-147">Многоклассовая классификация</span><span class="sxs-lookup"><span data-stu-id="7b60d-147">Multiclass Classification</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric) |[<span data-ttu-id="7b60d-148">Регрессия</span><span class="sxs-lookup"><span data-stu-id="7b60d-148">Regression</span></span>](xref:Microsoft.ML.AutoML.RegressionMetric)
|-- |-- |--
|<span data-ttu-id="7b60d-149">Достоверность</span><span class="sxs-lookup"><span data-stu-id="7b60d-149">Accuracy</span></span>| <span data-ttu-id="7b60d-150">LogLoss</span><span class="sxs-lookup"><span data-stu-id="7b60d-150">LogLoss</span></span> | <span data-ttu-id="7b60d-151">RSquared</span><span class="sxs-lookup"><span data-stu-id="7b60d-151">RSquared</span></span>
|<span data-ttu-id="7b60d-152">AreaUnderPrecisionRecallCurve</span><span class="sxs-lookup"><span data-stu-id="7b60d-152">AreaUnderPrecisionRecallCurve</span></span> | <span data-ttu-id="7b60d-153">LogLossReduction</span><span class="sxs-lookup"><span data-stu-id="7b60d-153">LogLossReduction</span></span> | <span data-ttu-id="7b60d-154">MeanAbsoluteError</span><span class="sxs-lookup"><span data-stu-id="7b60d-154">MeanAbsoluteError</span></span>
|<span data-ttu-id="7b60d-155">AreaUnderRocCurve</span><span class="sxs-lookup"><span data-stu-id="7b60d-155">AreaUnderRocCurve</span></span> | <span data-ttu-id="7b60d-156">MacroAccuracy</span><span class="sxs-lookup"><span data-stu-id="7b60d-156">MacroAccuracy</span></span> | <span data-ttu-id="7b60d-157">MeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="7b60d-157">MeanSquaredError</span></span>
|<span data-ttu-id="7b60d-158">F1Score</span><span class="sxs-lookup"><span data-stu-id="7b60d-158">F1Score</span></span> | <span data-ttu-id="7b60d-159">MicroAccuracy</span><span class="sxs-lookup"><span data-stu-id="7b60d-159">MicroAccuracy</span></span> | <span data-ttu-id="7b60d-160">RootMeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="7b60d-160">RootMeanSquaredError</span></span>
|<span data-ttu-id="7b60d-161">NegativePrecision</span><span class="sxs-lookup"><span data-stu-id="7b60d-161">NegativePrecision</span></span> | <span data-ttu-id="7b60d-162">TopKAccuracy</span><span class="sxs-lookup"><span data-stu-id="7b60d-162">TopKAccuracy</span></span>
|<span data-ttu-id="7b60d-163">NegativeRecall</span><span class="sxs-lookup"><span data-stu-id="7b60d-163">NegativeRecall</span></span> |
|<span data-ttu-id="7b60d-164">PositivePrecision</span><span class="sxs-lookup"><span data-stu-id="7b60d-164">PositivePrecision</span></span>
|<span data-ttu-id="7b60d-165">PositiveRecall</span><span class="sxs-lookup"><span data-stu-id="7b60d-165">PositiveRecall</span></span>

## <a name="data-pre-processing-and-featurization"></a><span data-ttu-id="7b60d-166">Предварительная обработка данных и определение признаков</span><span class="sxs-lookup"><span data-stu-id="7b60d-166">Data pre-processing and featurization</span></span>

<span data-ttu-id="7b60d-167">Предварительная обработка данных выполняется по умолчанию, при этом следующие действия выполняются автоматически:</span><span class="sxs-lookup"><span data-stu-id="7b60d-167">Data pre-processing happens by default and the following steps are performed automatically for you:</span></span>

1. <span data-ttu-id="7b60d-168">отсев признаков без полезной информации;</span><span class="sxs-lookup"><span data-stu-id="7b60d-168">Drop features with no useful information</span></span>

    <span data-ttu-id="7b60d-169">отсев признаков без полезной информации из наборов для обучения и проверки.</span><span class="sxs-lookup"><span data-stu-id="7b60d-169">Drop features with no useful information from training and validation sets.</span></span> <span data-ttu-id="7b60d-170">Сюда входят признаки, для которых отсутствуют все значения, во всех строках указано одинаковое значение или наблюдается чрезвычайно высокая кратность (например, хэши, идентификаторы или GUID).</span><span class="sxs-lookup"><span data-stu-id="7b60d-170">These include features with all values missing, same value across all rows or with extremely high cardinality (e.g., hashes, IDs or GUIDs).</span></span>

1. <span data-ttu-id="7b60d-171">Определение и подстановка отсутствующих значений</span><span class="sxs-lookup"><span data-stu-id="7b60d-171">Missing value indication and imputation</span></span>

    <span data-ttu-id="7b60d-172">Заполнение ячеек с отсутствующими значениями значением по умолчанию для указанного типа данных.</span><span class="sxs-lookup"><span data-stu-id="7b60d-172">Fill missing value cells with the default value for the datatype.</span></span> <span data-ttu-id="7b60d-173">Добавление признаков-индикаторов с тем же числом ячеек, что и у входного столбца.</span><span class="sxs-lookup"><span data-stu-id="7b60d-173">Append indicator features with the same number of slots as the input column.</span></span> <span data-ttu-id="7b60d-174">Значение в добавленных признаках-индикаторах равно `1`, если значение во входном столбце отсутствует, и `0` в противном случае.</span><span class="sxs-lookup"><span data-stu-id="7b60d-174">The value in the appended indicator features is `1` if the value in the input column is missing and `0` otherwise.</span></span>

1. <span data-ttu-id="7b60d-175">Создание дополнительных признаков</span><span class="sxs-lookup"><span data-stu-id="7b60d-175">Generate additional features</span></span>
    
    <span data-ttu-id="7b60d-176">Для текстовых признаков: признаки набора слов с использованием униграмм и трехсимвольных грамм (триграмм).</span><span class="sxs-lookup"><span data-stu-id="7b60d-176">For text features: Bag-of-word features using unigrams and tri-character-grams.</span></span>
    
    <span data-ttu-id="7b60d-177">Для категориальных признаков: прямое кодирование для функций с низкой кратностью и прямое кодирование с хэшем для категориальных признаков с высокой кратностью.</span><span class="sxs-lookup"><span data-stu-id="7b60d-177">For categorical features: One-hot encoding for low cardinality features, and one-hot-hash encoding for high cardinality categorical features.</span></span>

1. <span data-ttu-id="7b60d-178">Преобразования и кодировки</span><span class="sxs-lookup"><span data-stu-id="7b60d-178">Transformations and encodings</span></span>

    <span data-ttu-id="7b60d-179">Текстовые признаки с очень малым числом уникальных значений преобразуются в категориальные признаки.</span><span class="sxs-lookup"><span data-stu-id="7b60d-179">Text features with very few unique values transformed into categorical features.</span></span> <span data-ttu-id="7b60d-180">В зависимости от кратности категориальных признаков выполните прямое кодирование или прямое кодирование с хэшем.</span><span class="sxs-lookup"><span data-stu-id="7b60d-180">Depending on cardinality of categorical features, perform one-hot encoding or one-hot hash encoding.</span></span>

## <a name="exit-criteria"></a><span data-ttu-id="7b60d-181">Условия выхода</span><span class="sxs-lookup"><span data-stu-id="7b60d-181">Exit criteria</span></span>

<span data-ttu-id="7b60d-182">Определите критерии для выполнения своей задачи:</span><span class="sxs-lookup"><span data-stu-id="7b60d-182">Define the criteria to complete your task:</span></span>

1. <span data-ttu-id="7b60d-183">Выход по истечении периода времени: используя `MaxExperimentTimeInSeconds` в параметрах эксперимента, можно определить время выполнения задачи в секундах.</span><span class="sxs-lookup"><span data-stu-id="7b60d-183">Exit after a length of time - Using `MaxExperimentTimeInSeconds` in your experiment settings you can define how long in seconds that an task should continue to run.</span></span>

1. <span data-ttu-id="7b60d-184">Выход по токену отмены: можно использовать токен отмены, который позволяет отменить задачу до ее запланированного завершения.</span><span class="sxs-lookup"><span data-stu-id="7b60d-184">Exit on a cancellation token -  You can use a cancellation token that lets you cancel the task before it is scheduled to finish.</span></span>

    ```csharp
    var cts = new CancellationTokenSource();
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    experimentSettings.CancellationToken = cts.Token;
    ```

## <a name="create-an-experiment"></a><span data-ttu-id="7b60d-185">Создание эксперимента</span><span class="sxs-lookup"><span data-stu-id="7b60d-185">Create an experiment</span></span>

<span data-ttu-id="7b60d-186">После настройки параметров эксперимента вы готовы создать эксперимент.</span><span class="sxs-lookup"><span data-stu-id="7b60d-186">Once you have configured the experiment settings, you are ready to create the experiment.</span></span>

```csharp
RegressionExperiment experiment = mlContext.Auto().CreateRegressionExperiment(experimentSettings);
```

## <a name="run-the-experiment"></a><span data-ttu-id="7b60d-187">Запуск эксперимента</span><span class="sxs-lookup"><span data-stu-id="7b60d-187">Run the experiment</span></span>

<span data-ttu-id="7b60d-188">Запуск эксперимента активирует предварительную обработку данных, выбор алгоритмов обучения и настройку гиперпараметров.</span><span class="sxs-lookup"><span data-stu-id="7b60d-188">Running the experiment triggers data pre-processing, learning algorithm selection, and hyperparameter tuning.</span></span> <span data-ttu-id="7b60d-189">AutoML продолжит создавать сочетания определения признаков, алгоритмов машинного обучения и гиперпараметров до достижения `MaxExperimentTimeInSeconds` или прекращения эксперимента.</span><span class="sxs-lookup"><span data-stu-id="7b60d-189">AutoML will continue to generate combinations of featurization, learning algorithms, and hyperparameters until the `MaxExperimentTimeInSeconds` is reached or the experiment is terminated.</span></span>

```csharp
ExperimentResult<RegressionMetrics> experimentResult = experiment
    .Execute(trainingDataView, LabelColumnName, progressHandler: progressHandler);
```

<span data-ttu-id="7b60d-190">Изучите другие перегрузки `Execute()`, если хотите передать данные проверки, сведения о назначении столбцов или алгоритмы предварительного определения признаков.</span><span class="sxs-lookup"><span data-stu-id="7b60d-190">Explore other overloads for `Execute()` if you want to pass in validation data, column information indicating the column purpose, or prefeaturizers.</span></span>

## <a name="training-modes"></a><span data-ttu-id="7b60d-191">Режимы обучения</span><span class="sxs-lookup"><span data-stu-id="7b60d-191">Training modes</span></span>

### <a name="training-dataset"></a><span data-ttu-id="7b60d-192">Обучающий набор данных</span><span class="sxs-lookup"><span data-stu-id="7b60d-192">Training dataset</span></span>

<span data-ttu-id="7b60d-193">AutoML предоставляет перегруженный метод выполнения эксперимента, который позволяет вам предоставлять обучающие данные.</span><span class="sxs-lookup"><span data-stu-id="7b60d-193">AutoML provides an overloaded experiment execute method which allows you to provide training data.</span></span> <span data-ttu-id="7b60d-194">На внутреннем уровне система автоматизированного машинного обучения делит данные на части для обучения и проверки.</span><span class="sxs-lookup"><span data-stu-id="7b60d-194">Internally, automated ML divides the data into train-validate splits.</span></span>

```csharp
experiment.Execute(trainDataView);   
```

### <a name="custom-validation-dataset"></a><span data-ttu-id="7b60d-195">Настраиваемый набор данных для проверки</span><span class="sxs-lookup"><span data-stu-id="7b60d-195">Custom validation dataset</span></span>

<span data-ttu-id="7b60d-196">Используйте настраиваемый набор данных для проверки, если случайное разбиение недопустимо, как это обычно бывает с данными временных рядов.</span><span class="sxs-lookup"><span data-stu-id="7b60d-196">Use custom validation dataset if random split is not acceptable, as is usually the case with time series data.</span></span> <span data-ttu-id="7b60d-197">Вы можете указать собственный набор данных для проверки.</span><span class="sxs-lookup"><span data-stu-id="7b60d-197">You can specify your own validation dataset.</span></span> <span data-ttu-id="7b60d-198">Модель будет оценена относительно указанного набора данных для проверки вместо одного или нескольких случайных наборов данных.</span><span class="sxs-lookup"><span data-stu-id="7b60d-198">The model will be evaluated against the validation dataset specified instead of one or more random datasets.</span></span>

```csharp
experiment.Execute(trainDataView, validationDataView);   
```

## <a name="explore-model-metrics"></a><span data-ttu-id="7b60d-199">Изучение метрик модели</span><span class="sxs-lookup"><span data-stu-id="7b60d-199">Explore model metrics</span></span>

<span data-ttu-id="7b60d-200">После каждой итерации эксперимента машинного обучения метрики, связанные с соответствующей задачей, сохраняются.</span><span class="sxs-lookup"><span data-stu-id="7b60d-200">After each iteration of an ML experiment, metrics relating to that task are stored.</span></span>

<span data-ttu-id="7b60d-201">Например, можно обратиться к метрикам проверки из лучшего выполнения:</span><span class="sxs-lookup"><span data-stu-id="7b60d-201">For example, we can access validation metrics from the best run:</span></span>

```csharp
RegressionMetrics metrics = experimentResult.BestRun.ValidationMetrics;
Console.WriteLine($"R-Squared: {metrics.RSquared:0.##}");
Console.WriteLine($"Root Mean Squared Error: {metrics.RootMeanSquaredError:0.##}");
```

<span data-ttu-id="7b60d-202">Ниже приведены все доступные метрики для каждой задачи машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="7b60d-202">The following are all the available metrics per ML task:</span></span>
* [<span data-ttu-id="7b60d-203">Метрики двоичной классификации</span><span class="sxs-lookup"><span data-stu-id="7b60d-203">Binary classification metrics</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationMetric)
* [<span data-ttu-id="7b60d-204">Метрики многоклассовой классификации</span><span class="sxs-lookup"><span data-stu-id="7b60d-204">Multiclass classification metrics</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric)
* [<span data-ttu-id="7b60d-205">Метрики регрессии</span><span class="sxs-lookup"><span data-stu-id="7b60d-205">Regression metrics</span></span>](xref:Microsoft.ML.AutoML.RegressionMetric)

## <a name="see-also"></a><span data-ttu-id="7b60d-206">См. также</span><span class="sxs-lookup"><span data-stu-id="7b60d-206">See also</span></span>

<span data-ttu-id="7b60d-207">Полные примеры кода и не только см. в репозитории GitHub [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state).</span><span class="sxs-lookup"><span data-stu-id="7b60d-207">For full code samples and more visit the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state) GitHub repository.</span></span>
