---
title: Использование ML.NET для анализа тональности методом двоичной классификации
description: На примере двоичной классификации с использованием ML.NET вы сможете узнать, как использовать прогнозирование тональности для выбора соответствующих действий.
ms.date: 02/15/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: d6d5cae107e25000add5c8430a35131a79696bc2
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56092765"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a>Учебник. Использование ML.NET для анализа тональности методом двоичной классификации

> [!NOTE]
> В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен. Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

В этом практическом руководстве демонстрируется создание классификатора тональности на основе ML.NET в консольном приложении .NET Core на языке C# с помощью Visual Studio 2017.

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

В качестве примера мы используем консольное приложение, которое использует ML.NET для обучения модели, которая классифицирует и прогнозирует тональность по двоичному признаку: положительная или отрицательная. Также оно оценивает качество модели по второму набору данных. Наборы данных для анализа тональности взяты из проекта WikiDetox.

Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).

## <a name="prerequisites"></a>Предварительные требования

* [Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".

* [Файл с рабочими данными в формате строк, разделенных знаками табуляции из Wikipedia detox (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).
* [Файл с тестовыми данными в формате строк, разделенных знаками табуляции из Wikipedia detox (wikiPedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).

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

Данные для обучения: комментарии на веб-сайте могут быть токсичными (1) и нетоксичными (0) (**тональность**).
Определите **тональность** для новых комментариев на веб-сайте (токсичные или нетоксичные), например, для следующих примеров:

* Воздержитесь от добавления ерунды в Википедию.
* Он просто лучший, и в статье надо об этом сказать.

Для этого сценария лучше всего подходит алгоритм классификации в машинном обучении.

### <a name="about-the-classification-task"></a>Сведения о задаче классификации

Классификацией называют алгоритм машинного обучения, который использует данные для **определения** категории, типа или класса для некоторого элемента или ряда данных. Например, классификацию можно использовать для следующих действий:

* определение положительной или отрицательной тональности;
* сортировка сообщений электронной почты на спам, нежелательную почту и нужные сообщения;
* диагностика раковых заболеваний по лабораторным пробам, взятых у пациентов;
* распределение клиентов по категориям с разной готовностью реагировать на рекламную акцию.

Алгоритмы классификации обычно относятся к одному из следующих типов:

* Двоичная: A или B.
* Многоклассовая: несколько категорий, которые прогнозируются по одной модели.

## <a name="create-a-console-application"></a>Создание консольного приложения

1. Откройте Visual Studio 2017. Выберите **Файл** > **Создать** > **Проект** в меню. В диалоговом окне **Новый проект** выберите узел **Visual C#**, а затем — узел **.NET Core**. Выберите шаблон проекта **Консольное приложение (.NET Core)**. В текстовом поле **Имя** введите "Анализ тональности" и нажмите кнопку **ОК**.

2. Создайте каталог с именем *Data* в папке проекта, чтобы сохранить в нем файлы с наборами данных:

    В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**. Введите имя папки Data и нажмите клавишу "ВВОД".

3. Установите **пакет NuGet для Microsoft.ML**:

    В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**. Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**. Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.

### <a name="prepare-your-data"></a>подготавливать данные;

1. Скачайте файлы [Wikipedia-detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) и [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) с наборами данных и сохраните их в ранее созданную папку *Data*. Первый из этих наборов данных обучает модель машинного обучения, а второй позволяет оценить точность полученной модели.

2. В обозревателе решений щелкните правой кнопкой мыши каждый из файлов \*.tsv и выберите **Свойства**. В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.

### <a name="create-classes-and-define-paths"></a>Создание классов и определение путей

Добавьте следующие новые операторы `using` в начало файла *Program.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#1 "Add necessary usings")]

Нужно создать три глобальных поля для хранения путей к недавно скачанным файлам и глобальную переменную для `TextLoader`:

* `_trainDataPath` содержит путь к набору данных, используемому для обучения модели;
* `_testDataPath` содержит путь к набору данных, используемому для оценки модели;
* `_modelPath` содержит путь, по которому сохраняется обученная модель.
* `_textLoader` представляет собой <xref:Microsoft.ML.Data.TextLoader>, используемый для загрузки и преобразования наборов данных.

Добавьте следующий код в строку прямо перед методом `Main`, чтобы указать эти пути и переменную `_textLoader`:

[!code-csharp[Declare global variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare global variables")]

Вам потребуется создать несколько классов для входных данных и прогнозов. Добавьте в проект новый класс:

1. В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.

1. В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentData.cs*. Теперь нажмите кнопку **Добавить**.

    Файл *SentimentData.cs* откроется в редакторе кода. Добавьте следующий оператор `using` в начало файла *SentimentData.cs*.

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

Удалите из файла *SentimentData.cs* существующее определение класса и добавьте следующий код с двумя классами `SentimentData` и `SentimentPrediction`:

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

Класс `SentimentData` содержит входной набор данных. У него есть `float` (`Sentiment`) для значения тональности (положительная или отрицательное) и строковый параметр (`SentimentText`) для текста комментария. Для обоих полей указаны атрибуты `Column`. Этот атрибут позволяет описать порядок полей в файле данных и указывает, какое поле является `Label`. Класс `SentimentPrediction` используется для прогнозирования после обучения модели. Он имеет один параметр типа boolean (`Sentiment`) и атрибут `PredictedLabel` `ColumnName`. `Label` используется для создания и обучения модели, а также для оценки модели по второму набору данных. `PredictedLabel` используется для прогнозирования и оценки. Для оценки применяются входные обучающие данные, прогнозируемые значения и модель.

При создании модели с использованием ML.NET сначала необходимо создать `MLContext`. Концептуально это сопоставимо с использованием `DbContext` в Entity Framework. Среда предоставляет контекст для вашего задания Машинного обучения, который можно использовать для отслеживания исключений и ведения журнала.

### <a name="initialize-variables-in-main"></a>Инициализация переменных в методе Main

Создайте переменную с именем `mlContext` и инициализируйте ее с новым экземпляром `MLContext`.  Замените строку `Console.WriteLine("Hello World!")` в методе `Main` следующим кодом:

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Create the ML Context")]

Затем, чтобы настроить загрузку данных, инициализируйте глобальную переменную `_textLoader` для повторного использования.  При создании `TextLoader` с использованием `MLContext.Data.CreateTextLoader` вы передаете необходимый контекст и класс <xref:Microsoft.ML.Data.TextLoader.Arguments>, который включает настройку.

 Укажите схему данных, передав в загрузчик массив объектов <xref:Microsoft.ML.Data.TextLoader.Column>, содержащий имена всех столбцов и их типы. Вы определили схему данных ранее при создании класса `SentimentData`. Для нашей схемы первый столбец (метка) — это <xref:System.Boolean> (прогноз), а второй столбец (SentimentText) — это функция текстового или строкового типа, используемая для прогнозирования тональности.
Класс `TextLoader` возвращает полностью инициализированный <xref:Microsoft.ML.Data.TextLoader>.  

Чтобы инициализировать глобальную переменную `_textLoader` и повторно использовать ее для необходимых наборов данных, добавьте следующий код после инициализации `mlContext`:

[!code-csharp[initTextLoader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#4 "Initialize the TextLoader")]

Добавьте в следующую строку метода `Main` приведенный ниже код:

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Train your model")]

Метод `Train` выполняет следующие задачи:

* загрузка данных;
* извлечение и преобразование данных;
* обучение модели;
* прогноз тональности на основе тестовых данных;
* возвращение модели.

Создайте метод `Train` сразу после метода `Main`, вставив в него следующий код:

```csharp
 public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

Обратите внимание, что в метод Train передаются два параметра: `MLContext` для контекста (`mlContext`) и <xref:System.String> для пути к набору данных (`dataPath`). Вы будете использовать этот метод несколько раз для обучения и тестирования.

## <a name="load-the-data"></a>Загрузка данных

Вы загрузите данные с использованием глобальной переменной `_textLoader` с параметром `dataPath`. В результате возвратится <xref:Microsoft.Data.DataView.IDataView>. Точно так же как входные и выходные данные `Transforms`, `DataView` является основным типом конвейера данных, сравнимым с `IEnumerable` для `LINQ`.

В ML.NET данные аналогичны представлению SQL. Они схематизированы, неоднородны, и к ним применено отложенное вычисление. Объект является первой частью конвейера. Он загружает данные. Для этого руководства он загружает набор данных с комментариями и соответствующей токсичной или нетоксичной тональностью. Это позволяет создать и обучить модель.

 Добавьте следующий код в первую строку метода `Train`:

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "loading training dataset")]

## <a name="extract-and-transform-the-data"></a>Извлечение и преобразование данных

Предварительная обработка и очистка данных — это очень важные задачи, которые нужно выполнить перед использованием набора данных для машинного обучения. Необработанные данные часто содержат много шума, недостаточно надежны и в них могут быть пропуски. Использование данных напрямую без этих задач моделирования может дать неправильные результаты.

Конвейеры преобразования ML.NET создают пользовательский набор преобразований, которые применяются к данным перед началом обучения или проверки. Основной целью преобразования является [присвоение признаков](../resources/glossary.md#feature-engineering). Алгоритмы Машинного обучения определяют данные с [присвоенными признаками](../resources/glossary.md#feature), поэтому следующим шагом является преобразование текстовых данных в формат, который распознают наши алгоритмы Машинного обучения. Этот формат — [числовой вектор](../resources/glossary.md#numerical-feature-vector).

Далее вызовите `mlContext.Transforms.Text.FeaturizeText`, который преобразовывает текстовый столбец (`SentimentText`) в числовой вектор под названием `Features`, используемый в алгоритмах Машинного обучения. Это вызов программы-оболочки, возвращающий <xref:Microsoft.ML.Data.EstimatorChain%601>, который фактически будет конвейером. Присвойте ему имя `pipeline`, так как затем вы добавите обучающую систему в `EstimatorChain`. Добавьте следующую строку кода:

[!code-csharp[TextFeaturizingEstimator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizingEstimator")]

Это этап предварительной обработки и присвоения признаков. Дополнительные компоненты из ML.NET могут дать более точные результаты для вашей модели.

## <a name="choose-a-learning-algorithm"></a>Выбор алгоритма обучения

Чтобы добавить обучающую систему, вызовите метод программы-оболочки `mlContext.Transforms.Text.FeaturizeText`, возвращающий объект <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer>. Это средство обучения по дереву принятия решений, которое мы применим для нашего конвейера. `FastTreeBinaryClassificationTrainer` добавляется в `pipeline` и принимает `SentimentText` с присвоенными признаками (`Features`) и входные параметры `Label`, чтобы пройти обучение по историческим данным.

Добавьте следующий код в метод `Train`:

[!code-csharp[FastTreeBinaryClassificationTrainer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a>Обучение модели

Обучения модели <xref:Microsoft.ML.Data.TransformerChain%601> выполняется по набору данных, который вы ранее скачали и преобразовали. После определения средства оценки вы обучите модель с помощью <xref:Microsoft.ML.Data.EstimatorChain%601.Fit*>, предоставляя уже загруженные данные для обучения. В результате возвращается модель, необходимая для выполнения прогнозов. `pipeline.Fit()` обучает конвейер и возвращает `Transformer` на основе переданного типа `DataView`. Эксперимент не выполняется, пока этот процесс не закончится.

Добавьте следующий код в метод `Train`:

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a>Сохранение и возврат обученной модели для оценки

На этом этапе у вас есть модель типа <xref:Microsoft.ML.Data.TransformerChain%601>, которую можно интегрировать с любыми имеющимися или новыми приложениями .NET. Выполните возврат модели в конце метода `Train`.

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Return the model")]

## <a name="evaluate-the-model"></a>Оценка модели

Итак, вы завершили создание и обучение модели, и теперь ее можно оценить по другому набору данных, чтобы проверить ее точность и качество прогнозирования. В методе `Evaluate` передается для оценки модель, созданная в `Train`. Создайте метод `Evaluate` сразу после метода `Train` как показано в следующем коде:

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

Метод `Evaluate` выполняет следующие задачи:

* загрузка тестового набора данных;
* создание средства двоичной оценки;
* оценка модели и создание метрик;
* отображение метрик.

Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `Train`, используя следующий код:

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Call the Evaluate method")]

Вы загрузите тестовый набор данных с использованием ранее инициализированной глобальной переменной `_textLoader` с глобальным полем `_testDataPath`. С помощью этого набора данных вы можете оценить модели для проверки ее качества. Добавьте следующий код в метод `Evaluate`:

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Load the test dataset")]

Далее вы будете использовать параметр машинного обучения `model` (преобразователь) для ввода признаков и возврата прогнозов. В качестве следующей строки в методе `Evaluate` добавьте приведенный ниже код:

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Predict using the Transformer")]

Метод `BinaryClassificationContext.Evaluate` вычисляет метрики качества для `PredictionModel` на основе указанного набора данных. Он возвращает объект `BinaryClassificationEvaluator.CalibratedResult`, содержащий общие метрики, вычисляемые с помощью средств оценки двоичной классификации. Чтобы отобразить их для оценки качества модели, сначала метрики необходимо получить. Добавьте в следующую строку метода `Evaluate` приведенный ниже код:

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a>Отображение метрик для проверки модели

Используйте следующий код для отображения метрик, передачи результатов и выполнения действий по ним:

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Display selected metrics")]

Чтобы сохранить модель в ZIP-файл, для вызова метода `SaveModelAsFile` добавьте в качестве следующей строки в `Evaluate` приведенный ниже код:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#23 "Save the model")]

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

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#24 "Add the SaveTo Method")]
Развертывание и прогнозирование с помощью загруженной модели Вы также можете просмотреть, куда был записан файл, написав консольное сообщение с `_modelPath`, используя следующий код:

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a>Прогнозирование результатов для тестовых данных с помощью сохраненной модели

Создайте метод `Predict` сразу после метода `Evaluate`, вставив в него следующий код:

```csharp
private static void Predict(MLContext mlContext, ITransformer model)
{

}
```

Метод `Predict` выполняет следующие задачи:

* создание отдельного комментария тестовых данных;
* прогноз тональности на основе тестовых данных;
* объединение тестовых данных и прогнозов для создания отчетов;
* отображение результатов прогнозирования.

Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `Evaluate`, используя следующий код:

[!code-csharp[CallPredict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Call the Predict method")]

Несмотря на то что `model` представляет собой `transformer`, который обрабатывает многочисленные строки данных, достаточно распространенным сценарием рабочей среды является прогнозирование на основе отдельных примеров. <xref:Microsoft.ML.PredictionEngine%602> — это программа-оболочка, возвращаемая из метода `CreatePredictionEngine`. Давайте добавим следующий код в качестве первой строки в методе `Predict` для создания `PredictionEngine`:

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Create the PredictionEngine")]
  
Добавьте комментарий для проверки прогнозирования обученной модели в методе `Predict`, создав экземпляр `SentimentData`:

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for single prediction")]

 Это можно использовать для прогнозирования токсичной или нетоксичной тональности одного экземпляра данных комментария. Чтобы получить прогноз, примените <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> для данных. Обратите внимание, что входные данные имеют строковый формат, а модель выполняет присвоение признаков. Конвейер синхронизируется во время обучения и прогнозирования. Вам не нужно писать для прогнозирования отдельный код предварительной обработки и присвоения признаков. Кроме того, этот API выполняет как пакетное, так и разовое прогнозирование.

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create a prediction of sentiment")]

### <a name="using-the-model-prediction"></a>Использование модели: прогнозирование

Отобразите `SentimentText` и соответствующие прогнозы тональности, чтобы поделиться результатами и выполнить соответствующие действия. Этот этап называется вводом в эксплуатацию, после которого возвращаемые данные можно включить в операционные политики. Создайте отображение для результатов с помощью следующего кода <xref:System.Console.WriteLine?displayProperty=nameWithType>:

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction output")]

## <a name="deploy-and-predict-with-a-loaded-model"></a>Развертывание и прогнозирование с помощью загруженной модели

Создайте метод `PredictWithModelLoadedFromFile` непосредственно перед методом `SaveModelAsFile`, вставив в него следующий код:

```csharp
public static void PredictWithModelLoadedFromFile(MLContext mlContext)
{

}
```

Метод `PredictWithModelLoadedFromFile` выполняет следующие задачи:

* создание пакетных тестовых данных;
* прогноз тональности на основе тестовых данных;
* объединение тестовых данных и прогнозов для создания отчетов;
* отображение результатов прогнозирования.

Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `Predict`, используя следующий код:

[!code-csharp[CallPredictModelLoaded](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#25 "Call the PredictWithModelLoadedFromFile method")]

Добавьте новые комментарии, чтобы проверить прогнозы обученной модели, в метод `PredictWithModelLoadedFromFile`:

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#26 "Create test data for predictions")]

Загрузите модель

[!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#27 "Load the model")]

Теперь у вас есть готовая модель, и ее можно использовать для прогнозирования токсичной или нетоксичной тональности по данным комментариев с помощью метода <xref:Microsoft.ML.Core.Data.ITransformer.Transform%2A>. Чтобы получить прогноз, примените `Predict` для новых данных. Обратите внимание, что входные данные имеют строковый формат, а модель выполняет присвоение признаков. Конвейер синхронизируется во время обучения и прогнозирования. Вам не нужно писать для прогнозирования отдельный код предварительной обработки и присвоения признаков. Кроме того, этот API выполняет как пакетное, так и разовое прогнозирование. Добавьте в метод `PredictWithModelLoadedFromFile` приведенный ниже код для прогнозирования:

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#28 "Create predictions of sentiments")]

### <a name="using-the-loaded-model-for-prediction"></a>Использование загружаемой модели для прогнозирования

Отобразите `SentimentText` и соответствующие прогнозы тональности, чтобы поделиться результатами и выполнить соответствующие действия. Этот этап называется вводом в эксплуатацию, после которого возвращаемые данные можно включить в операционные политики. Создайте заголовок для результатов с помощью следующего кода <xref:System.Console.WriteLine?displayProperty=nameWithType>:

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#29 "Display prediction outputs")]

Перед отображением результатов прогнозирования объедините данные о тональности с прогнозами, чтобы просмотреть исходные комментарии и прогнозы тональности. В следующем коде для этого используется метод <xref:System.Linq.Enumerable.Zip%2A>, а после него нужно добавить следующий код:

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#30 "Build the pairs of sentiment data and predictions")]

Теперь, когда вы объединили в один класс `SentimentText` и `Sentiment`, можно отобразить результаты с помощью метода <xref:System.Console.WriteLine?displayProperty=nameWithType>:

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#31 "Display the predictions")]

Так как выводимые имена элементов кортежа появились только в C# версии 7.1, а для этого проекта по умолчанию устанавливается версия языка C# 7.0, необходимо изменить это значение до C# 7.1 или более поздней версии.
Для этого в **обозревателе решений** щелкните узел проекта правой кнопкой мыши и выберите пункт **Свойства**. Откройте вкладку **Сборка** и нажмите на кнопку **Дополнительно**. В раскрывающемся списке выберите **C# 7.1** (или более позднюю версию). Нажмите кнопку **OK**.

## <a name="results"></a>Результаты

Результаты выполнения должны выглядеть примерно так, как показано ниже. В процессе работы конвейер выводит сообщения. Вы можете видеть предупреждения или обработанные сообщения. Для удобства они удалены из следующих результатов.

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 94.44%
Auc: 98.77%
F1Score: 94.74%
=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.5297049
=============== End of Predictions ===============

=============== New iteration of Model ===============
=============== Create and Train the Model ===============
=============== End of training ===============


The model is saved to: C:\Tutorial\SentimentAnalysis\bin\Debug\netcoreapp2.1\Data\Model.zip

=============== Prediction Test of loaded model with a multiple sample ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.4585565
Sentiment: I love this article. | Prediction: Not Toxic | Probability: 0.09454837

```

Поздравляем! Вы успешно создали модель машинного обучения для классификации и прогнозирования тональности сообщений. Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).

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
