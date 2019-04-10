---
title: Использование ML.NET для сценариев многоклассовой классификации задач GitHub
description: Узнайте, как использовать ML.NET для сценариев многоклассовой классификации, чтобы назначать задачи GitHub определенным областям.
ms.date: 03/12/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: fc21a37fe585ed4b9880ec86ee26815e0668108c
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/04/2019
ms.locfileid: "58920991"
---
# <a name="tutorial-use-mlnet-in-a-multiclass-classification-scenario-to-classify-github-issues"></a>Учебник. Использование ML.NET для сценариев многоклассовой классификации задач GitHub

В этом практическом руководстве демонстрируется создание классификатора задач GitHub с помощью ML.NET в консольном приложении .NET Core на языке C# в Visual Studio 2017.

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

> [!NOTE]
> В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен. Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Сейчас в этом руководстве и соответствующем примере используется **ML.NET версии 0.11**. Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

## <a name="github-issue-sample-overview"></a>Обзор примера задачи GitHub

Пример представляет собой консольное приложение, использующее ML.NET для обучения модели, которая классифицирует и прогнозирует метку области для задачи GitHub. Также оно оценивает качество модели по второму набору данных. Наборы данных для задачи взяты из GitHub-репозитория dotnet/corefx.

Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).

## <a name="prerequisites"></a>Предварительные требования

* [Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".

* [Файл задач GitHub с разделением знаками табуляции (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).
* [Файл с тестовыми данными задач GitHub с разделением знаками табуляции (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).

## <a name="machine-learning-workflow"></a>Рабочий процесс машинного обучения

В этом руководстве используется рабочий процесс машинного обучения, который определяет порядок выполнения действий в процессе.

Вот основные этапы этого рабочего процесса:

1. **Определение проблемы**
2. **подготавливать данные;**
   * **Загрузка данных**
   * **Извлечение компонентов (преобразование данных)**
3. **Сборка и обучение** 
   * **Обучение модели**
   * **Оценка модели**
4. **Развертывание модели**
   * **Использование модели для прогнозирования**

### <a name="understand-the-problem"></a>Определение проблемы

Прежде всего необходимо понять суть проблемы, что позволит разбить ее на отдельные фрагменты для построения и обучения модели. Разделение проблемы на составляющие позволяет прогнозировать и оценивать результаты.

Рассматриваемая в этом руководстве проблема: определить, к какой области относятся входящие задачи GitHub, чтобы корректно помечать их для дальнейшей приоритизации и планирования.

Проблему можно разделить на следующие части:

* текст названия задачи;
* текст описания задачи;
* значение области для обучающих данных модели;
* прогнозируемое значение области, которое можно оценить и затем использовать на практике.

После этого нужно **определить** область, что поможет выбрать задачу машинного обучения.

## <a name="select-the-appropriate-machine-learning-algorithm"></a>Выбор подходящего алгоритма машинного обучения

Для этой проблемы вам известны следующие факты.

Обучающие данные

Задачам GitHub можно присваивать метки в нескольких областях (**Area**), как в следующих примерах:

* area-System.Numerics
* area-System.Xml
* area-Infrastructure
* area-System.Linq
* area-System.IO

Вы можете спрогнозировать **область** новой задачи GitHub, как в следующих примерах:

* Contract.Assert и Debug.Assert
* Защита полей от записи в System.Xml

Для этого сценария лучше всего подходит алгоритм классификации в машинном обучении.

### <a name="about-the-classification-learning-algorithm"></a>Об алгоритме обучения классификации

Классификацией называют алгоритм машинного обучения, который использует данные для **определения** категории, типа или класса для некоторого элемента или ряда данных. Например, классификацию можно использовать для следующих действий:

* определение положительной или отрицательной тональности;
* сортировка сообщений электронной почты на спам, нежелательную почту и нужные сообщения;
* диагностика раковых заболеваний по лабораторным пробам, взятых у пациентов;
* распределение клиентов по категориям с разной готовностью реагировать на рекламную акцию.

Варианты использования обучающих алгоритмов классификации обычно относятся к одному из следующих типов:

* Двоичная: A или B.
* Многоклассовая: несколько категорий, которые прогнозируются по одной модели.

Для таких проблем используйте обучающий алгоритм многоклассовой классификации, поскольку прогноз категории проблемы может относиться к нескольким категориям (многоклассовая), а не только к двум (двоичная).

## <a name="create-a-console-application"></a>Создание консольного приложения

### <a name="create-a-project"></a>Создание проекта

1. Откройте Visual Studio 2017. Выберите **Файл** > **Создать** > **Проект** в меню. В диалоговом окне **Новый проект** выберите узел **Visual C#**, а затем — узел **.NET Core**. Выберите шаблон проекта **Консольное приложение (.NET Core)**. В текстовое поле **Имя** введите GitHubIssueClassification, а затем нажмите кнопку **ОК**.

2. Создайте каталог с именем *Data* в папке проекта, чтобы сохранить в нем файлы с наборами данных:

    В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**. Введите имя папки Data и нажмите клавишу "ВВОД".

3. Создайте каталог с именем *Models* в папке проекта, чтобы сохранить модель:

    В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**. Введите "Models" и нажмите ВВОД.

4. Установите **пакет NuGet для Microsoft.ML**:

    В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**. Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**. Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.

### <a name="prepare-your-data"></a>подготавливать данные;

1. Скачайте наборы данных [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) и [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) и сохраните их в ранее созданную папку *Data*. Первый из этих наборов данных обучает модель машинного обучения, а второй позволяет оценить точность полученной модели.

2. В обозревателе решений щелкните правой кнопкой мыши каждый из файлов \*.tsv и выберите **Свойства**. В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.

### <a name="create-classes-and-define-paths"></a>Создание классов и определение путей

Добавьте следующие новые операторы `using` в начало файла *Program.cs*:

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddUsings)]

Создайте три глобальных поля для хранения путей к недавно скачанным файлам и глобальные переменные для `MLContext`, `DataView`, `PredictionEngine` и `TextLoader`:

* `_trainDataPath` содержит путь к набору данных, используемому для обучения модели;
* `_testDataPath` содержит путь к набору данных, используемому для оценки модели;
* `_modelPath` содержит путь, по которому сохраняется обученная модель.
* `_mlContext` соответствует классу <xref:Microsoft.ML.MLContext>, предоставляющему контекст для обработки;
* `_trainingDataView` представляет собой интерфейс <xref:Microsoft.Data.DataView.IDataView>, используемый для обработки обучающего набора данных;
* `_predEngine` соответствует классу <xref:Microsoft.ML.PredictionEngine%602>, используемому для одиночных прогнозов;
* `_reader` представляет собой <xref:Microsoft.ML.Data.TextLoader>, используемый для загрузки и преобразования наборов данных.

Добавьте следующий код в строку непосредственно над методом `Main`, чтобы указать эти пути и другие переменные:

[!code-csharp[DeclareGlobalVariables](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DeclareGlobalVariables)]

Создайте несколько классов для входных данных и прогнозов. Добавьте в проект новый класс:

1. В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.

1. В диалоговом окне **Добавление нового элемента** выберите **Класс** и в поле **Имя** укажите *GitHubIssueData.cs*. Теперь нажмите кнопку **Добавить**.

    Файл *GitHubIssueData.cs* откроется в редакторе кода. Добавьте следующий оператор `using` в начало файла *GitHubIssueData.cs*:

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#AddUsings)]

Удалите из файла *GitHubIssueData.cs* существующее определение класса и добавьте следующий код с двумя классами `GitHubIssue` и `IssuePrediction`:

[!code-csharp[DeclareGlobalVariables](~/samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#DeclareTypes)]

`GitHubIssue` является классом входного набора данных и имеет следующие поля <xref:System.String>:

* `ID` содержит значение идентификатора задачи GitHub.
* `Area` содержит значение метки `Area`.
* `Title` содержит название задачи GitHub.
* `Description` содержит описание задачи GitHub.

`IssuePrediction` используется для прогнозирования после обучения модели. Он имеет один параметр типа `string` (`Area`) и атрибут `PredictedLabel` `ColumnName`. `Label` используется для создания и обучения модели, а также для оценки модели по второму набору данных. `PredictedLabel` используется для прогнозирования и оценки. Для оценки применяются входные обучающие данные, прогнозируемые значения и модель.

При создании модели с использованием ML.NET сначала необходимо создать <xref:Microsoft.ML.MLContext>. `MLContext` сопоставимо с использованием `DbContext` в Entity Framework. Среда предоставляет контекст для вашего задания Машинного обучения, который можно использовать для отслеживания исключений и ведения журнала.

### <a name="initialize-variables-in-main"></a>Инициализация переменных в методе Main

Инициализируйте глобальную переменную `_mlContext` в новом экземпляре `MLContext` со случайным начальным значением (`seed: 0`) для получения воспроизводимых и детерминированных результатов при множестве циклов обучения.  Замените строку `Console.WriteLine("Hello World!")` в методе `Main` следующим кодом:

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a>Загрузка данных

Затем инициализируйте глобальную переменную `_trainingDataView` <xref:Microsoft.Data.DataView.IDataView> и загрузите данные с параметром `_trainDataPath`.

 Точно так же как входные и выходные данные [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer), `DataView` является основным типом конвейера данных, сравнимым с `IEnumerable` для `LINQ`.

В ML.NET данные аналогичны `SQL view`. Они схематизированы, неоднородны, и к ним применено отложенное вычисление. Объект является первой частью конвейера. Он загружает данные. В этом руководстве он загружает набор данных с названиями и описаниями задач, а также с соответствующей меткой области GitHub. `DataView` используется для создания и обучения модели.

Так как созданный ранее тип модели данных `GitHubIssue` соответствует схеме набора данных, вы можете объединить инициализацию, сопоставление и загрузку набора данных в одной строке кода.

Загрузите данные с помощью оболочки `MLContext.Data.LoadFromTextFile` для [метода LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29). Он возвращает <xref:Microsoft.Data.DataView.IDataView> для вывода схемы набора данных из типа модели данных `GitHubIssue` и использует заголовок набора данных. 

Вы определили схему данных ранее при создании класса `GitHubIssue`. Для схемы:

* Первый столбец `ID` (идентификатор задачи GitHub).
* Второй столбец `Area` (прогноз для обучения).
* Третий столбец `Title` (название задачи GitHub) является первым [признаком](../resources/glossary.md##feature), используемым для прогнозирования `Area`
* Четвертый столбец `Description` является вторым признаком, используемым для прогнозирования `Area`

Чтобы инициализировать и загрузить глобальную переменную `_trainingDataView` для ее использования в конвейере, добавьте после инициализации `mlContext` следующий код:

[!code-csharp[LoadTrainData](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTrainData)]

Добавьте в следующую строку метода `Main` приведенный ниже код:

[!code-csharp[CallProcessData](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallProcessData)]

Метод `ProcessData` выполняет следующие задачи:

* извлечение и преобразование данных;
* возвращение конвейера обработки.

Создайте метод `ProcessData` сразу после метода `Main`, вставив в него следующий код:

```csharp
public static IEstimator<ITransformer> ProcessData()
{

}
```

## <a name="extract-features-and-transform-the-data"></a>Извлечение компонентов и преобразование данных

Предварительная обработка и очистка данных — это очень важные задачи, которые нужно выполнить перед использованием набора данных для машинного обучения. Необработанные данные часто содержат много шума, недостаточно надежны и в них могут быть пропуски. Использование данных напрямую без этих задач моделирования может дать неправильные результаты.

Конвейеры преобразования ML.NET создают пользовательский набор `transforms`, который применяется к данным перед началом обучения или проверки. Основной целью преобразования является [присвоение признаков](../resources/glossary.md#feature-engineering). Алгоритмы Машинного обучения определяют данные с [присвоенными признаками](../resources/glossary.md#feature), поэтому следующим шагом является преобразование текстовых данных в формат, который распознают наши алгоритмы Машинного обучения. Этот формат — [числовой вектор](../resources/glossary.md#numerical-feature-vector).

При выполнении следующих шагов мы будем называть столбцы по именам, определенным в классе `GitHubIssue`.

При обучении и оценке модели значения в столбце **Label** по умолчанию рассматриваются как правильные значения для прогноза. Поскольку нам необходимо спрогнозировать метку области GitHub для `GitHubIssue`, скопируйте столбец `Area` в столбец **Label**. Для этого используйте `MLContext.Transforms.Conversion.MapValueToKey`, что является оболочкой для класса преобразования <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A>.  `MapValueToKey` возвращает <xref:Microsoft.ML.Data.EstimatorChain%601>, что фактически станет конвейером. Присвойте ему имя `pipeline`, так как затем вы добавите обучающую систему в `EstimatorChain`. Добавьте следующую строку кода:

[!code-csharp[MapValueToKey](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#MapValueToKey)]

 Такое присвоение задает значения ключа различным значениям в каждом из столбцов, и оно используется в алгоритме машинного обучения. Затем вызовите `mlContext.Transforms.Text.FeaturizeText`, который присваивает столбцы текста (`Title` и `Description`) числовому вектору `TitleFeaturized` и `DescriptionFeaturized` соответственно. Добавьте присвоение признаков для обоих столбцов в конвейере, используя следующий код:

[!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#FeaturizeText)]

>[!WARNING]
> В ML.NET версии 0.10 изменился порядок параметров преобразования. Ошибка не возникнет до момента сборки. Используйте имена параметров для преобразования, как показано в предыдущем фрагменте кода.

Последний шаг на этапе подготовки данных заключается в объединении всех столбцов признаков в столбце **Features** с помощью класса преобразования `Concatenate`. По умолчанию алгоритм обучения обрабатывает только признаки, представленные в столбце **Features**. Добавьте это преобразование в конвейер, используя следующий код:

[!code-csharp[Concatenate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Concatenate)]

 Затем добавьте <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A> для кэширования DataView, которое может ускорить обучение при многократных итерациях по данным, используя следующий код:

[!code-csharp[AppendCache](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AppendCache)]

> [!WARNING]
> Используйте AppendCacheCheckpoint для небольших и средних наборов данных для ускорения обучения. НЕ используйте AppendCacheCheckpoint (удалите .AppendCacheCheckpoint()) при обработке очень больших наборов данных.

Выполните возврат конвейера в конце метода `ProcessData`.

[!code-csharp[ReturnPipeline](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnPipeline)]

На этом этапе выполняется предварительная обработка и присвоение признаков. Дополнительные компоненты из ML.NET могут дать более точные результаты для вашей модели.

## <a name="build-and-train-the-model"></a>Сборка и обучение модели

В следующей строке кода в методе `Main` добавьте приведенный ниже вызов метода `BuildAndTrainModel`:

[!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallBuildAndTrainModel)]

Метод `BuildAndTrainModel` выполняет следующие задачи:

* создание класса алгоритма обучения;
* обучение модели;
* прогнозирование области на основе обучающих данных;
* сохранение модели в файл `.zip`;
* возвращение модели.

Создайте метод `BuildAndTrainModel` сразу после метода `Main`, вставив в него следующий код:

```csharp
public static IEstimator<ITransformer> BuildAndTrainModel(IDataView trainingDataView, IEstimator<ITransformer> pipeline)
{

}
```

Обратите внимание, что в метод BuildAndTrainModel передаются два параметра — `IDataView` для обучающего набора данных (`trainingDataView`) и <xref:Microsoft.ML.Data.EstimatorChain%601> для конвейера обработки, созданного в ProcessData (`pipeline`).

 Добавьте следующий код в первую строку метода `BuildAndTrainModel`:

### <a name="choose-a-learning-algorithm"></a>Выбор алгоритма обучения

Чтобы добавить алгоритм обучения, вызовите метод оболочки `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent`, возвращающий объект <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer>.  `SdcaMultiClassTrainer` добавляется в `pipeline` и принимает в качестве входных параметров `Title` и `Description` (`Features`) с присвоенными признаками, а также `Label` для обучения по историческим данным. Для возврата в исходное доступное для чтения состояние необходимо также сопоставить метку со значением. Выполните оба эти действия, используя следующий код:

[!code-csharp[AddTrainer](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTrainer)]

### <a name="train-the-model"></a>Обучение модели

Обучения модели <xref:Microsoft.ML.Data.TransformerChain%601> выполняется по набору данных, который вы ранее скачали и преобразовали. После определения средства оценки вы обучите модель с помощью <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A>, предоставляя уже загруженные данные для обучения. Этот метод возвращает модель, необходимую для прогнозирования. `trainingPipeline.Fit()` обучает конвейер и возвращает `Transformer` на основе переданного типа `DataView`. Эксперимент не выполняется, пока метод `.Fit()` не запустится.

Добавьте следующий код в метод `BuildAndTrainModel`:

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#TrainModel)]

Несмотря на то, что `model` представляет собой `transformer`, который обрабатывает многочисленные строки данных, достаточно распространенным сценарием рабочей среды является прогнозирование на основе отдельных примеров. <xref:Microsoft.ML.PredictionEngine%602> — это программа-оболочка, возвращаемая из метода `CreatePredictionEngine`. Давайте добавим в следующей строке метода `BuildAndTrainModel` указанный ниже код для создания `PredictionEngine`:

[!code-csharp[CreatePredictionEngine1](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine1)]

### <a name="predict-with-the-trained-model"></a>Прогнозирование с помощью обученной модели

Добавьте задачу GitHub для тестирования прогноза обученной модели в методе `Predict`, создав экземпляр `GitHubIssue`:

[!code-csharp[CreateTestIssue1](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateTestIssue1)]

Его можно использовать для прогнозирования метки `Area` в одном экземпляре данных задачи. Чтобы получить прогноз, примените <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> для данных. Входные данные имеют строковый формат, а модель выполняет присвоение признаков. Конвейер синхронизируется во время обучения и прогнозирования. Вам не нужно писать для прогнозирования отдельный код предварительной обработки и присвоения признаков. Кроме того, этот API выполняет как пакетное, так и разовое прогнозирование.

[!code-csharp[Predict](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Predict)]

### <a name="using-the-model-prediction-results"></a>Использование модели: результаты прогнозирования

Отобразите `GitHubIssue` и соответствующий прогноз метки `Area`, чтобы поделиться результатами и обработать их должным образом.  Создайте отображение для результатов с помощью следующего кода <xref:System.Console.WriteLine?displayProperty=nameWithType>:

[!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a>Возврат обученной модели для оценки

Выполните возврат модели в конце метода `BuildAndTrainModel`.

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a>Оценка модели

Итак, вы завершили создание и обучение модели, и теперь ее можно оценить по другому набору данных, чтобы проверить ее точность и качество прогнозирования. В методе `Evaluate` передается для оценки модель, созданная в `BuildAndTrainModel`. Создайте метод `Evaluate` сразу после метода `BuildAndTrainModel` как показано в следующем коде:

```csharp
public static void Evaluate()
{

}
```

Метод `Evaluate` выполняет следующие задачи:

* загрузка тестового набора данных;
* создание средства оценки многоклассовой классификации;
* оценка модели и создание метрик;
* отображение метрик.

Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `BuildAndTrainModel`, используя следующий код:

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallEvaluate)]

Как и для обучающего набора данных ранее, вы можете объединить инициализацию, сопоставление и загрузку тестового набора данных в одной строке кода. С помощью этого набора данных вы можете оценить модели для проверки ее качества. Добавьте следующий код в метод `Evaluate`:

[!code-csharp[LoadTestDataset](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTestDataset)]

`MulticlassClassificationContext.Evaluate` является оболочкой для метода <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A>, который вычисляет метрики качества для модели по указанному набору данных. Он возвращает объект <xref:Microsoft.ML.Data.MultiClassClassifierMetrics>, содержащий общие метрики, вычисляемые средствами оценки многоклассовой классификации.
Чтобы отобразить метрики для оценки качества модели, сначала их необходимо получить.
Используйте метод `Transform` (преобразователь) для глобальной переменной `_trainedModel` машинного обучения для ввода признаков и возврата прогнозов. В качестве следующей строки в методе `Evaluate` добавьте приведенный ниже код:

[!code-csharp[Evaluate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Evaluate)]

Для многоклассовой классификации выполняется оценка следующих метрик:

* Микроточность — на метрику точности в равной степени влияет каждая пара "пример-класс".  Значение микроточности должно быть максимально близко к 1.

* Макроточность — на метрику точности в равной степени влияет каждый класс. Миноритарным классам назначается тот же вес, что и более крупным. Значение макроточности должно быть максимально близко к 1.

* Логарифмические потери — см. термин [логарифмические потери](../resources/glossary.md#log-loss). Значение логарифмических потерь должно быть максимально близко к нулю.

* Минимизация логарифмических потерь — находится в диапазоне [-inf, 100], где 100 — идеальный прогноз, а 0 — среднее прогнозное значение. Значение минимизации логарифмических потерь должно быть максимально близко к нулю.

### <a name="displaying-the-metrics-for-model-validation"></a>Отображение метрик для проверки модели

Используйте следующий код для отображения метрик, передачи результатов и выполнения действий по ним:

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayMetrics)]

### <a name="save-the-trained-and-evaluated-model"></a>Сохранение обученной и вычисленной модели

На этом этапе у вас есть модель типа <xref:Microsoft.ML.Data.TransformerChain%601>, которую можно интегрировать с любыми имеющимися или новыми приложениями .NET. Чтобы сохранить обученную модель в ZIP-файл, добавьте приведенный ниже код вызова метода `SaveModelAsFile` в качестве следующей строки в `BuildAndTrainModel`:

[!code-csharp[CallSaveModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallSaveModel)]

## <a name="save-the-model-as-a-zip-file"></a>Сохранение модели в качестве ZIP-файла

Создайте метод `SaveModelAsFile` сразу после метода `Evaluate`, вставив в него следующий код:

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

Метод `SaveModelAsFile` выполняет следующие задачи:

* сохранение модели в качестве ZIP-файла.

Далее создайте метод для сохранения модели, чтобы ее можно было использовать повторно, а также применять в других приложениях. `ITransformer` содержит метод <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)>, который принимает глобальное поле `_modelPath`, и <xref:System.IO.Stream>. Чтобы сохранить модель в качестве ZIP-файла, мы создадим `FileStream` непосредственно перед вызовом метода `SaveTo`. В качестве следующей строки в методе `SaveModelAsFile` добавьте приведенный ниже код:

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SaveModel)]

Вы также можете просмотреть, куда был записан файл, написав консольное сообщение с `_modelPath`, используя следующий код:

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="deploy-and-predict-with-a-loaded-model"></a>Развертывание и прогнозирование с помощью загруженной модели

Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `Evaluate`, используя следующий код:

[!code-csharp[CallPredictIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallPredictIssue)]

Создайте метод `PredictIssue` сразу после метода `Evaluate` (и непосредственно перед методом `SaveModelAsFile`), вставив в него следующий код:

```csharp
private static void PredictIssue()
{

}
```

Метод `PredictIssue` выполняет следующие задачи:

* создание одной задачи с тестовыми данными;
* прогнозирование области на основе тестовых данных;
* объединение тестовых данных и прогнозов для создания отчетов;
* отображение результатов прогнозирования.

Сначала загрузите сохраненную ранее модель, используя следующий код:

[!code-csharp[LoadModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadModel)]

Добавьте задачу GitHub для тестирования прогноза обученной модели в методе `Predict`, создав экземпляр `GitHubIssue`:

[!code-csharp[AddTestIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTestIssue)]

[!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]
  
Теперь, когда у вас есть модель, ее можно использовать для прогнозирования метки области GitHub у одного экземпляра данных задачи GitHub. Чтобы получить прогноз, примените <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> для данных. Входные данные имеют строковый формат, а модель выполняет присвоение признаков. Конвейер синхронизируется во время обучения и прогнозирования. Вам не нужно писать для прогнозирования отдельный код предварительной обработки и присвоения признаков. Кроме того, этот API выполняет как пакетное, так и разовое прогнозирование. Добавьте в метод `PredictIssue` приведенный ниже код для прогнозирования:

[!code-csharp[PredictIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a>Использование загружаемой модели для прогнозирования

Отобразите `Area`, чтобы категоризировать задачу и обработать ее должным образом. Создайте отображение для результатов с помощью следующего кода <xref:System.Console.WriteLine?displayProperty=nameWithType>:

[!code-csharp[DisplayResults](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayResults)]

## <a name="results"></a>Результаты

Результаты выполнения должны выглядеть примерно так, как показано ниже. В процессе работы конвейер выводит сообщения. Вы можете видеть предупреждения или обработанные сообщения. Для удобства эти сообщения удалены из следующих результатов.

```console
=============== Single Prediction just-trained-model - Result: area-System.Net ===============
The model is saved to C:\Users\johalex\dotnet-samples\samples\machine-learning\tutorials\GitHubIssueClassification\bin\Debug\netcoreapp2.0\..\..\..\Models\model.zip
*************************************************************************************************************
*       Metrics for Multi-class Classification model - Test Data
*------------------------------------------------------------------------------------------------------------
*       MicroAccuracy:    0.74
*       MacroAccuracy:    0.687
*       LogLoss:          .932
*       LogLossReduction: 63.852
*************************************************************************************************************
=============== Single Prediction - Result: area-System.Data ===============
```

Поздравляем! Вы успешно создали модель машинного обучения для классификации и прогнозирования метки области у задачи GitHub. Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).

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
> [Прогнозирование платы за такси](taxi-fare.md)
