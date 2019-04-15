---
title: Прогнозирование платы с помощью алгоритма обучения регрессии с использованием ML.NET
description: Прогнозирование платы с помощью алгоритма обучения регрессии с использованием ML.NET.
author: aditidugar
ms.author: johalex
ms.date: 03/20/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 79b8abd0fb01062900b2ae4e14c02d8844bb6ef9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295982"
---
# <a name="tutorial-predict-prices-using-a-regression-learner-with-mlnet"></a>Учебник. Прогнозирование платы с помощью алгоритма обучения регрессии с использованием ML.NET

В этом руководстве описано, как с помощью ML.NET создать [модель регрессии](../resources/glossary.md#regression) для прогнозирования цен, особенно платы за проезд в такси в городе Нью-Йорке.

> [!NOTE]
> В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен. Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Сейчас в этом руководстве и соответствующем примере используется **ML.NET версии 0.11**. Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

В этом руководстве вы узнаете, как:
> [!div class="checklist"]
> * Определение проблемы
> * Выбор подходящей задачи машинного обучения
> * Подготовка и анализ данных
> * Создание конвейера обучения
> * Загрузка и преобразование данных
> * Выбор алгоритма обучения
> * Обучение модели
> * Оценка модели
> * Использование модели для прогнозирования

## <a name="prerequisites"></a>Предварительные требования

* [Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".

## <a name="understand-the-problem"></a>Определение проблемы

Рассматриваемая проблема основана на сценарии прогнозирования платы за поездку на такси в Нью-Йорке. На первый взгляд может показаться, что плата зависит только от расстояния. Но службы такси в Нью-Йорке изменяют плату с учетом еще нескольких факторов, таких как наличие дополнительных пассажиров или оплата кредитной картой вместо наличных.

## <a name="select-the-appropriate-machine-learning-task"></a>Выбор подходящей задачи машинного обучения

Вы хотите спрогнозировать стоимость, которая является реальным значением, зависящим от других факторов в наборе данных. Для этого нужно выбрать задачу машинного обучения [регрессия](../resources/glossary.md#regression).

## <a name="create-a-console-application"></a>Создание консольного приложения

1. Откройте Visual Studio 2017. Выберите **Файл** > **Создать** > **Проект** в меню. В диалоговом окне **Новый проект** выберите узел **Visual C#**, а затем — узел **.NET Core**. Выберите шаблон проекта **Консольное приложение (.NET Core)**. В текстовое поле **Имя** введите TaxiFarePrediction, а затем нажмите кнопку **ОК**.

1. Создайте каталог с именем *Data* в папке проекта, чтобы хранить в нем наборы данных и файлы модели:

    В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**. Введите имя папки Data и нажмите клавишу "ВВОД".

1. Установите пакет NuGet для **Microsoft.ML**:

    В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**. Выберите nuget.org в качестве источника пакетов, перейдите на вкладку **Обзор**, выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**. Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.

## <a name="prepare-and-understand-the-data"></a>Подготовка и анализ данных

1. Скачайте наборы данных [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) и [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv), сохранив их в созданной на предыдущем шаге папке *Data*. Эти наборы данных используются для обучения модели машинного обучения и последующей оценки точности этой модели. Эти наборы данных взяты из [наборов данных NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).

1. В **обозревателе решений** щелкните правой кнопкой мыши каждый из файлов \*.csv и выберите **Свойства**. В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.

1. Откройте набор данных **taxi-fare-train.csv** и просмотрите заголовки столбцов в первой строке. Теперь изучите каждый из столбцов. Разберитесь, какие данные в них хранятся, и определите, какие столбцы являются **признаками**, а в каком содержится **метка**.

**Метка** — это столбец, значения в котором вы хотите спрогнозировать. Выбранные **признаки** используются для прогнозирования метки.

Предоставленный набор данных содержит следующие столбцы:

* **vendor_id:** идентификатор поставщика услуг такси — это признак.
* **rate_code:** тип тарифа для поездки на такси — это признак.
* **passenger_count:** число пассажиров в поездке — это признак.
* **trip_time_in_secs:** время, затраченное на поездку. Вам требуется спрогнозировать плату за одну поездку до того, как поездка будет завершена. На этот момент вам неизвестна продолжительность поездки. Таким образом, продолжительность поездки не является признаком и соответствующий столбец следует исключить из модели.
* **trip_distance:** расстояние поездки — это признак.
* **payment_type:** метод оплаты (наличные или кредитная карта) — это признак.
* **fare_amount:** общая сумма, уплаченная за поездку на такси, — это метка.

## <a name="create-data-classes"></a>Создание классов данных

Создайте классы для входных данных и прогнозов:

1. В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.
1. В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *TaxiTrip.cs*. Теперь нажмите кнопку **Добавить**.
1. Добавьте следующие директивы `using` в новый файл.

   [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

Удалите из файла *TaxiTrip.cs* существующее определение класса и добавьте следующий код с двумя классами `TaxiTrip` и `TaxiTripFarePrediction`:

[!code-csharp[DefineTaxiTrip](~/samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

`TaxiTrip`  — это класс входных данных, который содержит определения для всех столбцов в наборе данных. Используйте атрибут <xref:Microsoft.ML.Data.LoadColumnAttribute>, чтобы указать индексы исходных столбцов в наборе данных.

Класс `TaxiTripFarePrediction` представляет результаты прогнозирования. Он содержит одно поле типа float `FareAmount`, к которому применен атрибут `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute>. В случае задачи регрессии столбец **Оценка** содержит прогнозируемые значения метки.

> [!NOTE]
> Используйте тип `float` для представления значений с плавающей запятой в классах данных ввода и прогнозирования.

## <a name="define-data-and-model-paths"></a>Определение путей к данным и модели

Добавьте следующие новые операторы `using` в начало файла *Program.cs*:

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

Необходимо создать три поля, которые будут содержать пути к файлам с наборами данных и к файлу для сохранения модели:

* `_trainDataPath` содержит путь к файлу с набором данных, используемым для обучения модели.
* `_testDataPath` содержит путь к файлу с набором данных, используемым для оценки модели.
* `_modelPath` содержит путь к файлу для сохранения обучаемой модели.

Добавьте следующий код прямо перед методом `Main`, чтобы указать эти пути и переменную `_textLoader`:

[!code-csharp[InitializePaths](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

При создании модели с использованием ML.NET сначала необходимо создать контекст машинного обучения. Концептуально это сопоставимо с использованием `DbContext` в Entity Framework. Среда предоставляет контекст для вашего задания машинного обучения, который можно использовать для отслеживания исключений и ведения журнала.

### <a name="initialize-variables-in-main"></a>Инициализация переменных в методе Main

Создайте переменную с именем `mlContext` и инициализируйте ее с новым экземпляром `MLContext`.  Замените строку `Console.WriteLine("Hello World!")` в методе `Main` следующим кодом:

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create the ML Context")]

В качестве следующей строки кода в методе `Main` добавьте приведенный ниже код, чтобы вызвать метод `Train`:

[!code-csharp[Train](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Train your model")]

Метод `Train` выполняет следующие задачи:

* загрузка данных;
* извлечение и преобразование данных;
* обучение модели;
* сохранение модели в качестве ZIP-файла;
* возвращение модели.

Метод `Train` обучает модель. Создайте этот метод сразу под `Main`, используя следующий код:

```csharp
public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

Мы передаем два параметра в метод `Train`: `MLContext` для контекста (`mlContext`) и строку для пути к набору данных (`dataPath`). Мы будем повторно использовать этот метод для загрузки наборов данных.

## <a name="load-and-transform-data"></a>Загрузка и преобразование данных

Загрузите данные с помощью оболочки `MLContext.Data.LoadFromTextFile` для [метода LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29). В результате возвратится <xref:Microsoft.Data.DataView.IDataView>. 

Точно так же как входные и выходные данные `Transforms`, `DataView` является основным типом конвейера данных, сравнимым с `IEnumerable` для `LINQ`.

В ML.NET данные аналогичны представлению SQL. Они схематизированы, неоднородны, и к ним применено отложенное вычисление. Объект является первой частью конвейера. Он загружает данные. В этом руководстве он загружает набор данных со сведениями о ценах на поездки на такси. Это позволяет создать и обучить модель.

Добавьте следующий код в первую строку метода `Train`:

[!code-csharp[LoadTrainData](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "loading training dataset")]

При выполнении следующих шагов ссылки на столбцы будут задаваться по именам, определенным в классе `TaxiTrip`.

При обучении и оценке модели значения в столбце **Label** по умолчанию рассматриваются как правильные значения для прогноза. Поскольку нам необходимо спрогнозировать плату за поездку на такси, скопируйте столбец `FareAmount` в столбец **Label**. Для этого используйте класс преобразования `CopyColumnsEstimator` и добавьте следующий код:

[!code-csharp[CopyColumnsEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Use the CopyColumnsEstimator")]

Алгоритм, который обучает модель, принимает **числовые** признаки, поэтому значения категориальных данных (`VendorId`, `RateCode` и `PaymentType`) нужно преобразовать в числа (`VendorIdEncoded`, `RateCodeEncoded` и `PaymentTypeEncoded`). Для этого используйте класс преобразования Microsoft.ML.Transforms.OneHotEncodingTransformer>, который присваивает разные числовые значения ключа разным значениям в каждом из столбцов, и добавьте следующий код:

[!code-csharp[OneHotEncodingEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Use the OneHotEncodingEstimator")]

Последний шаг на этапе подготовки данных заключается в объединении всех столбцов признаков в столбце **Features** с помощью класса преобразования `mlContext.Transforms.Concatenate`. По умолчанию алгоритм обучения обрабатывает только признаки, представленные в столбце **Features**. Добавьте следующий код:

[!code-csharp[ColumnConcatenatingEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Use the ColumnConcatenatingEstimator")]

## <a name="choose-a-learning-algorithm"></a>Выбор алгоритма обучения

После добавления данных в конвейер и их преобразования в правильный входной формат мы выбираем алгоритм обучения (**средство обучения**). Алгоритм обучения осуществляет обучение модели. Для решения этой проблемы мы выбрали задачу **регрессии**, поэтому мы используем алгоритм обучения `FastTreeRegressionTrainer`, который является одним из регрессионных алгоритмов обучения, предоставляемых ML.NET.

Алгоритм обучения `FastTreeRegressionTrainer` использует метод градиентного усиления. Градиентный бустинг — это метод машинного обучения для проблем регрессии. Он пошагово создает каждое дерево регрессии. Он также использует предварительно определенную функцию для оценки ошибки на каждом этапе и исправления ошибок для следующего этапа. Результатом является модель прогнозирования, фактически собранная из нескольких более слабых моделей прогнозирования. Дополнительные сведения о градиентном бустинге см. в статье [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression) (Регрессия для дерева принятия решений с бустингом).

Добавьте следующий код в метод `Train`, чтобы добавить `FastTreeRegressionTrainer` в код обработки данных, который вы добавили на предыдущем шаге:

[!code-csharp[FastTreeRegressionTrainer](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Add the FastTreeRegressionTrainer")]

## <a name="train-the-model"></a>Обучение модели

Последним шагом является обучение модели. Обучение модели <xref:Microsoft.ML.Data.TransformerChain> выполняется по набору данных, который вы ранее загрузили и преобразовали. После определения средства оценки мы обучаем модель с помощью <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A>, предоставляя уже загруженные данные для обучения. В результате возвращается модель, необходимая для выполнения прогнозов. `pipeline.Fit()` обучает конвейер и возвращает `Transformer` на основе переданного типа `DataView`. Эксперимент не выполняется, пока этот процесс не закончится.

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#11 "Train the model")]

### <a name="save-the-model"></a>Сохранение модели

На этом этапе у вас есть модель типа <xref:Microsoft.ML.Data.TransformerChain>, которую можно интегрировать с любыми имеющимися или новыми приложениями .NET. Чтобы сохранить модель в ZIP-файл, добавьте следующий код в конец метода `Train`:

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Save the model as a .zip file and return the model")]

## <a name="save-the-model-as-a-zip-file"></a>Сохранение модели в качестве ZIP-файла

Создайте метод `SaveModelAsFile` сразу после метода `Train`, вставив в него следующий код:

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

Метод `SaveModelAsFile` выполняет следующие задачи:

* сохранение модели в качестве ZIP-файла.

Нам нужно создать метод для сохранения модели, чтобы ее можно было использовать повторно, а также применять в других приложениях. `ITransformer` содержит метод <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)>, который принимает глобальное поле `_modelPath`, и <xref:System.IO.Stream>. Так как нам необходимо сохранить модель в качестве ZIP-файла, мы создадим `FileStream` непосредственно перед вызовом метода `SaveTo`. В качестве следующей строки в методе `SaveModelAsFile` добавьте приведенный ниже код:

[!code-csharp[SaveToMethod](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Add the SaveTo Method")]

Мы также можем показать, куда был записан файл, написав консольное сообщение с `_modelPath`, используя следующий код:

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="evaluate-the-model"></a>Оценка модели

Оценка — это процесс проверки того, насколько хорошо модель позволяет спрогнозировать значения метки. Важно, чтобы модель возвращала хорошие прогнозы по данным, которые не использовались для ее обучения. Для такой оценки можно, например, разделить данные на обучающий и тестовый наборы данных, как вы и сделали в рамках этого руководства. Теперь, когда вы завершили обучение модели по обучающему набору данных, вы можете проверить ее работу по тестовым данным.

Метод `Evaluate` осуществляет оценку модели. Чтобы создать этот метод, добавьте следующий код под методом `Train`:

```csharp
private static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```
Метод `Evaluate` выполняет следующие задачи:

* загрузка тестового набора данных;
* создание средства оценки регрессии;
* оценка модели и создание метрик;
* отображение метрик.

Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `Train`, используя следующий код:

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Call the Evaluate method")]

Загрузите тестовые данные с помощью программы-оболочки `MLContext.Data.LoadFromTextFile`. С помощью этого набора данных вы можете оценить модели для проверки ее качества. Добавьте следующий код в метод `Evaluate`:

[!code-csharp[LoadTestDataset](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Load the test dataset")]

Затем мы будем использовать параметр машинного обучения `model` (преобразователь) для ввода признаков и возврата прогнозов. В качестве следующей строки в методе `Evaluate` добавьте приведенный ниже код:

[!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Predict using the Transformer")]

Метод `RegressionContext.Evaluate` вычисляет метрики качества для `PredictionModel` на основе указанного набора данных. Возвращает объект <xref:Microsoft.ML.Data.RegressionMetrics>, который содержит общие метрики, вычисляемые с помощью средств оценки регрессии. Чтобы отобразить их для оценки качества модели, сначала метрики необходимо получить. Добавьте в следующую строку метода `Evaluate` приведенный ниже код:

[!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Compute Metrics")]

Добавьте следующий код, чтобы оценить модель и создать для нее метрики оценки:

```csharp
Console.WriteLine();
Console.WriteLine($"*************************************************");
Console.WriteLine($"*       Model quality metrics evaluation         ");
Console.WriteLine($"*------------------------------------------------");
```

Также в качестве метрики для оценки регрессионных моделей используется [коэффициент детерминации](../resources/glossary.md#coefficient-of-determination). Коэффициент детерминации может иметь значения в диапазоне от 0 до 1. Чем ближе его значение к 1, тем лучше модель. Чтобы отображать значение коэффициента детерминации, добавьте следующий код в метод `Evaluate`:

[!code-csharp[DisplayRSquared](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#18 "Display the RSquared metric.")]

[Среднеквадратичное отклонение](../resources/glossary.md##root-of-mean-squared-error-rmse) является одной из метрик, используемых для оценки регрессионной модели. Чем ниже это отклонение, тем лучше модель. Чтобы отображать значение среднеквадратичного отклонения, добавьте следующий код в метод `Evaluate`:

[!code-csharp[DisplayRMS](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#19 "Display the RMS metric.")]

## <a name="use-the-model-for-predictions"></a>Использование модели для прогнозирования

## <a name="predict-the-test-data-outcome-with-the-model-and-a-single-comment"></a>Прогнозирование результатов тестовых данных с помощью модели и одного комментария

Создайте метод `TestSinglePrediction` сразу после метода `Evaluate`, вставив в него следующий код:

```csharp
private static void TestSinglePrediction(MLContext mlContext)
{

}
```

Метод `TestSinglePrediction` выполняет следующие задачи:

* создание отдельного комментария тестовых данных;
* прогнозирование суммы оплаты на основе тестовых данных;
* объединение тестовых данных и прогнозов для создания отчетов;
* отображение результатов прогнозирования.

Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `Evaluate`, используя следующий код:

[!code-csharp[CallTestSinglePrediction](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#20 "Call the TestSinglePrediction method")]

Так как нам необходимо загрузить модель из сохраненного ZIP-файла, мы создадим `FileStream` непосредственно перед вызовом метода `Load`. В качестве следующей строки в методе `TestSinglePrediction` добавьте приведенный ниже код:

[!code-csharp[LoadTheModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#21 "Load the model")]

Несмотря на то что `model` представляет собой `transformer`, который обрабатывает многочисленные строки данных, достаточно распространенным сценарием рабочей среды является прогнозирование на основе отдельных примеров. <xref:Microsoft.ML.PredictionEngine%602> — это программа-оболочка, возвращаемая из метода `CreatePredictionEngine`. Давайте добавим в следующей строке метода `TestSinglePrediction` указанный ниже код для создания `PredictionEngine`:

[!code-csharp[MakePredictionEngine](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#22 "Create the PredictionFunction")]
  
Для этого руководства в этом классе используется один тестовый проход. Позже можно добавить другие сценарии и поэкспериментировать с этой моделью. Добавьте поездку для проверки прогнозирования стоимости обученной моделью с помощью метода `TestSinglePrediction`, создав экземпляр `TaxiTrip`:

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#23 "Create test data for single prediction")]

 Мы можем использовать это для прогнозирования платы на основе одного экземпляра данных поездки на такси. Чтобы получить прогноз, примените <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> для данных. Обратите внимание, что входные данные имеют строковый формат, а модель выполняет присвоение признаков. Конвейер синхронизируется во время обучения и прогнозирования. Вам не нужно писать для прогнозирования отдельный код предварительной обработки и присвоения признаков. Кроме того, этот API выполняет как пакетное, так и разовое прогнозирование.

[!code-csharp[Predict](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#24 "Create a prediction of taxi fare")]

Чтобы отобразить прогнозируемую плату за указанную поездку, добавьте в метод `TestSinglePrediction` следующий код:

[!code-csharp[Predict](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#25 "Display the prediction.")]

Запустите программу, чтобы узнать прогноз платы за такси для тестового примера.

Поздравляем! Вы успешно создали модель машинного обучения для прогнозирования платы за проезд в такси, оценили ее точность и использовали ее для получения прогнозов. Исходный код для этого руководства можно найти в репозитории GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы узнали, как:
> [!div class="checklist"]
> * Определение проблемы
> * Выбор подходящей задачи машинного обучения
> * Подготовка и анализ данных
> * Создание конвейера обучения
> * Загрузка и преобразование данных
> * Выбор алгоритма обучения
> * Обучение модели
> * Оценка модели
> * Использование модели для прогнозирования

Переходите к следующему руководству.
> [!div class="nextstepaction"]
> [Кластеризация ирисов Фишера](iris-clustering.md)
