---
title: Использование ML.NET для анализа тональности методом двоичной классификации
description: На примере двоичной классификации с использованием ML.NET вы сможете узнать, как использовать прогнозирование тональности для выбора соответствующих действий.
ms.date: 03/07/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: d7e46b489506f4adad843ba5315afde4c7689b4e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723326"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a>Учебник. Использование ML.NET для анализа тональности методом двоичной классификации

В этом практическом руководстве показано, как создать классификатор тональности для прогнозирования положительной или отрицательной тональности на основе ML.NET в консольном приложении .NET Core на языке C# с помощью Visual Studio 2017. В сфере машинного обучения этот тип прогнозирования называется двоичной классификацией.

> [!NOTE]
> В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен. Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Сейчас в этом руководстве и соответствующем примере используется **ML.NET версии 0.11**. Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

В этом руководстве вы узнаете, как:
> [!div class="checklist"]
> * Определение проблемы
> * Выбор подходящего алгоритма машинного обучения
> * подготавливать данные;
> * Преобразование данных
> * Обучение модели
> * Оценка модели
> * Прогнозирование с помощью обученной модели
> * Развертывание и прогнозирование с помощью загруженной модели

## <a name="sentiment-analysis-sample-overview"></a>Обзор примера для анализа тональности

В качестве примера мы используем консольное приложение, которое использует ML.NET для обучения модели, которая классифицирует и прогнозирует тональность по двоичному признаку: положительная или отрицательная. Набор данных тональности Yelp был взят из Калифорнийского Университета в Ирвайне (UCI) и делится на два набора данных — для обучения и для тестирования. Для анализа качества в примере модель оценивается по набору данных для тестирования. 

Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).

## <a name="prerequisites"></a>Предварительные требования

* [Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".

* [ZIP-файл набора данных предложений с меткой тональности UCI](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip).

## <a name="machine-learning-workflow"></a>Рабочий процесс машинного обучения

В этом руководстве используется рабочий процесс машинного обучения, который определяет порядок выполнения действий в процессе.

Вот основные этапы этого рабочего процесса:

1. **определение проблемы**;
2. **Подготовка данных**.
   * **Загрузка данных**.
   * **Извлечение компонентов (преобразование данных)**.
3. **Сборка и обучение**. 
   * **Обучение модели**.
   * **оценка модели**;
4. **Развертывание модели**
   * **Использование модели для прогнозирования**

### <a name="understand-the-problem"></a>Определение проблемы

Прежде всего необходимо понять суть проблемы, что позволит разбить ее на отдельные фрагменты для построения и обучения модели. Разделение проблемы позволяет прогнозировать и оценивать результаты.

В этом руководстве ставится следующая задача: определение тональности поступившего на веб-сайт комментария, чтобы выполнить для него соответствующее действие.

Эта проблему можно разбить на следующие элементы: текст и значение тональности для данных, по которым вы будете обучать модель, и прогнозируемое значение тональности, которое вы будете оценивать и затем использовать в работе.

После этого нужно дать **определение** тональности, которое поможет выбрать задачу машинного обучения.

## <a name="select-the-appropriate-machine-learning-algorithm"></a>Выбор подходящего алгоритма машинного обучения

Для этой проблемы вам известны следующие факты.

Данные для обучения: комментарии на веб-сайте могут быть положительными (1) или отрицательными (0) (**тональность**).

Определите **тональность** для новых комментариев на веб-сайте, например для следующих примеров:

* Здесь отличные официанты. Молодцы!
* В этом заведении отвратительный суп.

Для этого сценария лучше всего подходит алгоритм классификации в машинном обучении.

### <a name="about-the-classification-algorithm"></a>Алгоритм классификации

Классификацией называют алгоритм машинного обучения, который использует данные для **определения** категории, типа или класса для некоторого элемента или ряда данных. Например, классификацию можно использовать для следующих действий:

* определение положительной или отрицательной тональности;
* сортировка сообщений электронной почты на спам, нежелательную почту и нужные сообщения;
* диагностика раковых заболеваний по лабораторным пробам, взятых у пациентов;
* распределение клиентов по категориям с разной готовностью реагировать на рекламную акцию.

Алгоритмы классификации обычно относятся к одному из следующих типов:

* Двоичная: A или B.
* Многоклассовая: несколько категорий, которые прогнозируются по одной модели.

Так как комментарии с сайта необходимо классифицировать как положительные или отрицательные, используется алгоритм двоичной классификации. 

## <a name="create-a-console-application"></a>Создание консольного приложения

1. Откройте Visual Studio 2017. Выберите **Файл** > **Создать** > **Проект** в меню. В диалоговом окне **Новый проект** выберите узел **Visual C#**, а затем — узел **.NET Core**. Выберите шаблон проекта **Консольное приложение (.NET Core)**. В текстовом поле **Имя** введите "Анализ тональности" и нажмите кнопку **ОК**.

2. Создайте каталог с именем *Data* в папке проекта, чтобы сохранить в нем файлы с наборами данных:

    В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**. Введите имя папки Data и нажмите клавишу "ВВОД".

3. Установите **пакет NuGet для Microsoft.ML**:

    В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**. Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**. Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.

### <a name="prepare-your-data"></a>подготавливать данные;

1. Скачайте [ZIP-файл набора данных предложений с меткой тональности UCI (ссылка дана в следующем примечании)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) и распакуйте его.

2. Скопируйте файл `yelp_labelled.txt` в созданный каталог *Data*.

> [!NOTE]
> Наборы данных в этом руководстве взяты из документа "From Group to Individual Labels using Deep Features" (От групповых до индивидуальных меток с использованием функций глубокого обучения), Котциас (Kotzias) и др., KDD 2015, и размещены в репозитории машинного обучения UCI Д. Дуа (D. Dua) и Э. Карра Танискиду (E. Karra Taniskidou) (2017). UCI Machine Learning Repository (Репозиторий машинного обучения UCI) [http://archive.ics.uci.edu/ml]. Ирвайн, Калифорния: Калифорнийский университет, Школа информационных технологий и компьютерных наук.

3. В обозревателе решений щелкните правой кнопкой мыши файл `yelp_labeled.txt` и выберите пункт **Свойства**. В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.

### <a name="create-classes-and-define-paths"></a>Создание классов и определение путей

Добавьте следующие новые операторы `using` в начало файла *Program.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddUsings "Add necessary usings")]

Создайте два глобальных поля для хранения пути к недавно скачанному файлу набора данных и файлу сохраненной модели:

* `_dataPath` содержит путь к набору данных, используемому для обучения модели;
* `_modelPath` содержит путь, по которому сохраняется обученная модель.

Добавьте следующий код в строку прямо перед методом `Main`, чтобы указать эти пути:

[!code-csharp[Declare global variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DeclareGlobalVariables "Declare global variables")]

Вам потребуется создать несколько классов для входных данных и прогнозов. Добавьте в проект новый класс:

1. В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.

1. В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentData.cs*. Теперь нажмите кнопку **Добавить**.

    Файл *SentimentData.cs* откроется в редакторе кода. Добавьте следующий оператор `using` в начало файла *SentimentData.cs*.

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#AddUsings "Add necessary usings")]

Удалите из файла *SentimentData.cs* существующее определение класса и добавьте следующий код с двумя классами `SentimentData` и `SentimentPrediction`:

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#DeclareTypes "Declare data record types")]

Класс входного набора данных `SentimentData` содержит параметры `string` — для комментария (`SentimentText`) и `bool` (`Sentiment`) — для определения положительной или отрицательной тональности. Для обоих полей указаны атрибуты <xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29>. Этот атрибут позволяет описать порядок полей в файле данных.  Кроме того, свойство `Sentiment` имеет атрибут <xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A>, который позволяет обозначить его как поле `Label`. Класс `SentimentPrediction` используется для прогнозирования после обучения модели. Он имеет один параметр типа boolean (`Sentiment`) и атрибут `PredictedLabel` `ColumnName`. Параметр `Label` используется для создания и обучения модели, а также для оценки модели по разделенному набору данных для тестирования. `PredictedLabel` используется для прогнозирования и оценки. Для оценки применяются входные обучающие данные, прогнозируемые значения и модель.

При создании модели с использованием ML.NET сначала необходимо создать <xref:Microsoft.ML.MLContext>. Концептуально `MLContext` сопоставимо с использованием `DbContext` в Entity Framework. Среда предоставляет контекст для вашего задания Машинного обучения, который можно использовать для отслеживания исключений и ведения журнала.

### <a name="initialize-variables-in-main"></a>Инициализация переменных в методе Main

Создайте переменную с именем `mlContext` и инициализируйте ее с новым экземпляром `MLContext`.  Замените строку `Console.WriteLine("Hello World!")` в методе `Main` следующим кодом:

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateMLContext "Create the ML Context")]

Добавьте в следующую строку метода `Main` приведенный ниже код:

[!code-csharp[CallLoadData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallLoadData)]

Метод `LoadData` выполняет следующие задачи:

* загрузка данных;
* Разделяет скачанный набор данных на наборы данных для обучения и тестирования.
* Возвращает два набора данных — для обучения и для тестирования.

Создайте метод `LoadData` сразу после метода `Main`, вставив в него следующий код:

```csharp
public static (IDataView trainSet, IDataView testSet) LoadData(MLContext mlContext)
{

}
```
## <a name="load-the-data"></a>Загрузка данных

Так как созданный ранее тип модели данных `SentimentData` соответствует схеме набора данных, вы можете объединить инициализацию, сопоставление и загрузку набора данных в одной строке кода с использованием оболочки `MLContext.Data.ReadFromTextFile` для <xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29>. В результате возвратится <xref:Microsoft.Data.DataView.IDataView>. 

 Точно так же как входные и выходные данные `Transforms`, `DataView` является основным типом конвейера данных, сравнимым с `IEnumerable` для `LINQ`.

В ML.NET данные аналогичны представлению SQL. Они схематизированы, неоднородны, и к ним применено отложенное вычисление. Объект является первой частью конвейера. Он загружает данные. Для этого руководства он загружает набор данных с комментариями и соответствующей токсичной или нетоксичной тональностью. Это позволяет создать и обучить модель.

 Добавьте следующий код в первую строку метода `LoadData`:

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadData "loading dataset")]

### <a name="split-the-dataset-for-model-training-and-testing"></a>Разделение набора данных для обучения и тестирования модели

Затем для обучения модели необходимо использовать набор данных для обучения, а для оценки модели — набор данных для тестирования. Используйте параметр `MLContext.BinaryClassification.TrainTestSplit` который заключает в оболочку <xref:Microsoft.ML.StaticPipe.TrainingStaticExtensions.TrainTestSplit%2A>, чтобы разделить загруженный набор данных на наборы данных для обучения и тестирования и вернуть их в <xref:Microsoft.ML.TrainCatalogBase.TrainTestData>. С помощью параметра `testFraction` можно указать, какие данные необходимо добавить в набор для тестирования. По умолчанию параметр имеет значение 10%, но в этом примере необходимо задать 20%, чтобы использовать дополнительные данные для оценки.  

Чтобы разделить скачанные данные на необходимые наборы данных, добавьте код в следующей строке метода `LoadData`:

[!code-csharp[SplitData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SplitData "Split the Data")]

Верните `splitDataView` в конце метода `LoadData`.

[!code-csharp[ReturnSplitData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a>Сборка и обучение модели

В следующей строке кода в методе `Main` добавьте приведенный ниже вызов метода `BuildAndTrainModel`:

[!code-csharp[CallBuildAndTrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallBuildAndTrainModel)]

Метод `BuildAndTrainModel` выполняет следующие задачи:

* извлечение и преобразование данных;
* обучение модели;
* прогноз тональности на основе тестовых данных;
* возвращение модели.

Создайте метод `Train` сразу после метода `Main`, вставив в него следующий код:

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
{

}
```

Обратите внимание, что в метод Train передаются два параметра: `MLContext` для контекста (`mlContext`) и `IDataView` набора данных для обучения (`splitTrainSet`). 

## <a name="extract-and-transform-the-data"></a>Извлечение и преобразование данных

Предварительная обработка и очистка данных — это очень важные задачи, которые нужно выполнить перед использованием набора данных для машинного обучения. Необработанные данные часто содержат много шума, недостаточно надежны и в них могут быть пропуски. Использование данных напрямую без этих задач моделирования может дать неправильные результаты.

Конвейеры преобразования ML.NET создают пользовательский набор преобразований, которые применяются к данным перед началом обучения или проверки. Основной целью преобразования является [присвоение признаков](../resources/glossary.md#feature-engineering). Алгоритмы Машинного обучения определяют данные с [присвоенными признаками](../resources/glossary.md#feature), поэтому следующим шагом является преобразование текстовых данных в формат, который распознают наши алгоритмы Машинного обучения. Этот формат — [числовой вектор](../resources/glossary.md#numerical-feature-vector).

Далее вызовите `mlContext.Transforms.Text.FeaturizeText`, который преобразовывает текстовый столбец (`SentimentText`) в числовой вектор под названием `Features`, используемый в алгоритмах Машинного обучения. Это вызов программы-оболочки, возвращающий <xref:Microsoft.ML.Data.EstimatorChain%601>, который фактически будет конвейером. Присвойте ему имя `pipeline`, так как затем вы добавите обучающую систему в `EstimatorChain`. Добавьте следующую строку кода:

[!code-csharp[FeaturizeText](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#FeaturizeText "Featurize the text")]

>[!WARNING]
> В ML.NET версии 0.10 изменился порядок параметров преобразования. Процесс будет происходить без ошибок, пока вы не запустите приложение и не создадите модель. Используйте имена параметров для преобразования, как показано в предыдущем фрагменте кода.

Это этап предварительной обработки и присвоения признаков. Дополнительные компоненты из ML.NET могут дать более точные результаты для вашей модели.

## <a name="choose-a-learning-algorithm"></a>Выбор алгоритма обучения

Чтобы добавить обучающую систему, вызовите метод программы-оболочки `mlContext.BinaryClassification.Trainers.FastTree`, возвращающий объект <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer>. Это средство обучения по дереву принятия решений, которое мы применим для нашего конвейера. `FastTreeBinaryClassificationTrainer` добавляется в `pipeline` и принимает `SentimentText` с присвоенными признаками (`Features`) и входные параметры `Label`, чтобы пройти обучение по историческим данным.

Добавьте следующий код в метод `BuildAndTrainModel`:

[!code-csharp[FastTreeBinaryClassificationTrainer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddTrainer "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a>Обучение модели

Обучения модели <xref:Microsoft.ML.Data.TransformerChain%601> выполняется по набору данных, который вы ранее скачали и преобразовали. После определения средства оценки вы обучите модель с помощью метода <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A>, предоставляя уже загруженные данные для обучения. В результате возвращается модель, необходимая для выполнения прогнозов. `pipeline.Fit()` обучает конвейер и возвращает `Transformer` на основе переданного типа `DataView`. Эксперимент не выполняется, пока метод `.Fit()` не запустится.

Добавьте следующий код в метод `BuildAndTrainModel`:

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TrainModel "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a>Сохранение и возврат обученной модели для оценки

На этом этапе у вас есть модель типа <xref:Microsoft.ML.Data.TransformerChain%601>, которую можно интегрировать с любыми имеющимися или новыми приложениями .NET. Выполните возврат модели в конце метода `BuildAndTrainModel`.

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a>Оценка модели

Итак, вы завершили создание и обучение модели, и теперь ее можно оценить по другому набору данных, чтобы проверить ее точность и качество прогнозирования. В методе `Evaluate` передается для оценки модель, созданная в `BuildAndTrainModel`. Создайте метод `Evaluate` сразу после метода `BuildAndTrainModel` как показано в следующем коде:

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
{

}
```

Метод `Evaluate` выполняет следующие задачи:

* загрузка тестового набора данных;
* создание средства оценки двоичной классификации;
* оценка модели и создание метрик;
* отображение метрик.

Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `Train`, используя следующий код:

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallEvaluate "Call the Evaluate method")]

Далее вы будете использовать параметр машинного обучения `model` (преобразователь) и параметр `splitTestSet` для ввода признаков и возврата прогнозов. В качестве следующей строки в методе `Evaluate` добавьте приведенный ниже код:

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TransformData "Predict using the Transformer")]

Метод `mlContext.BinaryClassification.Evaluate` вычисляет метрики качества для `PredictionModel` на основе указанного набора данных. Он возвращает объект <xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics>, содержащий общие метрики, вычисляемые с помощью средств оценки двоичной классификации. Чтобы отобразить их для оценки качества модели, сначала метрики необходимо получить. Добавьте в следующую строку метода `Evaluate` приведенный ниже код:

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Evaluate "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a>Отображение метрик для проверки модели

Используйте следующий код для отображения метрик, передачи результатов и выполнения действий по ним:

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayMetrics "Display selected metrics")]

Чтобы сохранить модель в ZIP-файл, для вызова метода `SaveModelAsFile` добавьте в качестве следующей строки в `Evaluate` приведенный ниже код:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallSaveModel "Save the model")]

## <a name="save-the-model-as-azip-file"></a>Сохранение модели в качестве ZIP-файла

Создайте метод `SaveModelAsFile` сразу после метода `Evaluate`, вставив в него следующий код:

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

Метод `SaveModelAsFile` выполняет следующие задачи:

* сохранение модели в качестве ZIP-файла.

Далее создайте метод для сохранения модели, чтобы ее можно было использовать повторно, а также применять в других приложениях. `ITransformer` содержит метод <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)>, который принимает глобальное поле `_modelPath`, и <xref:System.IO.Stream>. Чтобы сохранить модель в качестве ZIP-файла, мы создадим `FileStream` непосредственно перед вызовом метода `SaveTo`. В качестве следующей строки в методе `SaveModelAsFile` добавьте приведенный ниже код:

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SaveModel "Add the SaveTo Method")]

## <a name="deploy-and-predict-with-a-loaded-model"></a>Развертывание и прогнозирование с помощью загруженной модели

Вы также можете просмотреть, куда был записан файл, написав консольное сообщение с `_modelPath`, используя следующий код:

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a>Прогнозирование результатов для тестовых данных с помощью сохраненной модели

Создайте метод `UseModelWithSingleItem` сразу после метода `Evaluate`, вставив в него следующий код:

```csharp
private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
{

}
```

Метод `UseModelWithSingleItem` выполняет следующие задачи:

* создание отдельного комментария тестовых данных;
* прогноз тональности на основе тестовых данных;
* объединение тестовых данных и прогнозов для создания отчетов;
* отображение результатов прогнозирования.

Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `Evaluate`, используя следующий код:

[!code-csharp[CallUseModelWithSingleItem](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

Несмотря на то что `model` представляет собой `transformer`, который обрабатывает многочисленные строки данных, достаточно распространенным сценарием рабочей среды является прогнозирование на основе отдельных примеров. <xref:Microsoft.ML.PredictionEngine%602> — это программа-оболочка, возвращаемая из метода `CreatePredictionEngine`. Давайте добавим следующий код в качестве первой строки в методе `Predict` для создания `PredictionEngine`:

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]
  
Добавьте комментарий для проверки прогнозирования обученной модели в методе `Predict`, создав экземпляр `SentimentData`:

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

 Это можно использовать для прогнозирования положительной или отрицательной тональности одного экземпляра данных комментария. Чтобы получить прогноз, примените <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> для данных. Обратите внимание, что входные данные имеют строковый формат, а модель выполняет присвоение признаков. Конвейер синхронизируется во время обучения и прогнозирования. Вам не нужно писать для прогнозирования отдельный код предварительной обработки и присвоения признаков. Кроме того, этот API выполняет как пакетное, так и разовое прогнозирование.

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Predict "Create a prediction of sentiment")]

### <a name="use-the-model-prediction"></a>Использование модели. Прогнозирование

Отобразите `SentimentText` и соответствующие прогнозы тональности, чтобы поделиться результатами и выполнить соответствующие действия. Этот этап называется вводом в эксплуатацию, после которого возвращаемые данные можно включить в операционные политики. Создайте отображение для результатов с помощью следующего кода <xref:System.Console.WriteLine?displayProperty=nameWithType>:

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#OutputPrediction "Display prediction output")]

## <a name="deploy-and-predict-with-a-loaded-model"></a>Развертывание и прогнозирование с помощью загруженной модели

Создайте метод `UseLoadedModelWithBatchItems` непосредственно перед методом `SaveModelAsFile`, вставив в него следующий код:

```csharp
public static void UseLoadedModelWithBatchItems(MLContext mlContext)
{

}
```

Метод `UseLoadedModelWithBatchItems` выполняет следующие задачи:

* создание пакетных тестовых данных;
* прогноз тональности на основе тестовых данных;
* объединение тестовых данных и прогнозов для создания отчетов;
* отображение результатов прогнозирования.

Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `UseModelWithSingleItem`, используя следующий код:

[!code-csharp[CallPredictModelLoaded](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseLoadedModelWithBatchItems "Call the CallUseLoadedModelWithBatchItems method")]

Добавьте новые комментарии, чтобы проверить прогнозы обученной модели, в метод `UseLoadedModelWithBatchItems`:

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssues "Create test data for predictions")]

Загрузите модель

[!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadModel "Load the model")]

Теперь у вас есть готовая модель, и ее можно использовать для прогнозирования токсичной или нетоксичной тональности по данным комментариев с помощью метода <xref:Microsoft.ML.ITransformer.Transform%2A>. Чтобы получить прогноз, примените `Predict` для новых данных. Обратите внимание, что входные данные имеют строковый формат, а модель выполняет присвоение признаков. Конвейер синхронизируется во время обучения и прогнозирования. Вам не нужно писать для прогнозирования отдельный код предварительной обработки и присвоения признаков. Кроме того, этот API выполняет как пакетное, так и разовое прогнозирование. Добавьте в метод `UseLoadedModelWithBatchItems` приведенный ниже код для прогнозирования:

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="use-the-loaded-model-for-prediction"></a>Использование загруженной модели для прогнозирования

Отобразите `SentimentText` и соответствующие прогнозы тональности, чтобы поделиться результатами и выполнить соответствующие действия. Этот этап называется вводом в эксплуатацию, после которого возвращаемые данные можно включить в операционные политики. Создайте заголовок для результатов с помощью следующего кода <xref:System.Console.WriteLine?displayProperty=nameWithType>:

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddInfoMessage "Display prediction outputs")]

Перед отображением результатов прогнозирования объедините данные о тональности с прогнозами, чтобы просмотреть исходные комментарии и прогнозы тональности. В следующем коде для этого используется метод <xref:System.Linq.Enumerable.Zip%2A>, а после него нужно добавить следующий код:

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#BuildSentimentPredictionPairs "Build the pairs of sentiment data and predictions")]

Теперь, когда вы объединили в один класс `SentimentText` и `Sentiment`, можно отобразить результаты с помощью метода <xref:System.Console.WriteLine?displayProperty=nameWithType>:

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayResults "Display the predictions")]

Так как выводимые имена элементов кортежа появились только в C# версии 7.1, а для этого проекта по умолчанию устанавливается версия языка C# 7.0, необходимо изменить это значение до C# 7.1 или более поздней версии.
Для этого в **обозревателе решений** щелкните узел проекта правой кнопкой мыши и выберите пункт **Свойства**. Откройте вкладку **Сборка** и нажмите на кнопку **Дополнительно**. В раскрывающемся списке выберите **C# 7.1** (или более позднюю версию). Нажмите кнопку **OK**.

## <a name="results"></a>Результаты

Результаты выполнения должны выглядеть примерно так, как показано ниже. В процессе работы конвейер выводит сообщения. Вы можете видеть предупреждения или обработанные сообщения. Для удобства они удалены из следующих результатов.

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 79.14%
Auc: 86.27%
F1Score: 80.60%

=============== End of model evaluation ===============
The model is saved to C:\Tutorials\SentimentAnalysis\bin\Debug\netcoreapp2.1\Data\Model.zip

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.4641322
=============== End of Predictions ===============


=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1391833
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9819039
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

Поздравляем! Вы успешно создали модель машинного обучения для классификации и прогнозирования тональности сообщений. 

Построение успешных моделей — итеративный процесс. Изначально эта модель имеет низкое качество, так как в руководстве используются небольшие наборы данных для быстрого обучения. Если вам требуется модель более высокого качества, можно попытаться улучшить ее, использовав более крупные наборы данных для обучения или выбрав другие алгоритмы обучения с разными гиперпараметрами для каждого алгоритма.

Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы узнали, как:
> [!div class="checklist"]
> * Определение проблемы
> * Выбор подходящего алгоритма машинного обучения
> * подготавливать данные;
> * Преобразование данных
> * Обучение модели
> * Оценка модели
> * Прогнозирование с помощью обученной модели
> * Развертывание и прогнозирование с помощью загруженной модели

Переходите к следующему руководству:
> [!div class="nextstepaction"]
> [Классификация задач](github-issue-classification.md)
