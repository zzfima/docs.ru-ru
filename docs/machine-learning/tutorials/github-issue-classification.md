---
title: Классификация задач на GitHub — многоклассовая классификация
description: Узнайте, как использовать ML.NET для сценариев многоклассовой классификации, чтобы назначать задачи GitHub определенным областям.
ms.date: 05/02/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: a4122d0cdfe6531275fabf94743882a82f2a13c1
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063523"
---
# <a name="tutorial-use-mlnet-in-a-multiclass-classification-scenario-to-classify-github-issues"></a><span data-ttu-id="017a7-103">Учебник. Использование ML.NET для сценариев многоклассовой классификации задач GitHub</span><span class="sxs-lookup"><span data-stu-id="017a7-103">Tutorial: Use ML.NET in a multiclass classification scenario to classify GitHub issues</span></span>

<span data-ttu-id="017a7-104">В этом практическом руководстве демонстрируется создание классификатора задач GitHub для обучения модели, классифицирующей и прогнозирующей метки области для задач на GitHub, с помощью ML.NET в консольном приложении .NET Core на языке C# в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="017a7-104">This sample tutorial illustrates using ML.NET to create a GitHub issue classifier to train a model that classifies and predicts the Area label for a GitHub issue via a .NET Core console application using C# in Visual Studio.</span></span>

<span data-ttu-id="017a7-105">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="017a7-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="017a7-106">подготавливать данные;</span><span class="sxs-lookup"><span data-stu-id="017a7-106">Prepare your data</span></span>
> * <span data-ttu-id="017a7-107">Преобразование данных</span><span class="sxs-lookup"><span data-stu-id="017a7-107">Transform the data</span></span>
> * <span data-ttu-id="017a7-108">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="017a7-108">Train the model</span></span>
> * <span data-ttu-id="017a7-109">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="017a7-109">Evaluate the model</span></span>
> * <span data-ttu-id="017a7-110">Прогнозирование с помощью обученной модели</span><span class="sxs-lookup"><span data-stu-id="017a7-110">Predict with the trained model</span></span>
> * <span data-ttu-id="017a7-111">Развертывание и прогнозирование с помощью загруженной модели</span><span class="sxs-lookup"><span data-stu-id="017a7-111">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="017a7-112">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="017a7-112">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="017a7-113">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="017a7-113">Prerequisites</span></span>

* <span data-ttu-id="017a7-114">[Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="017a7-114">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="017a7-115">[Файл задач GitHub с разделением знаками табуляции (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span><span class="sxs-lookup"><span data-stu-id="017a7-115">The [Github issues tab separated file (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span></span>
* <span data-ttu-id="017a7-116">[Файл с тестовыми данными задач GitHub с разделением знаками табуляции (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span><span class="sxs-lookup"><span data-stu-id="017a7-116">The [Github issues test tab separated file (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="017a7-117">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="017a7-117">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="017a7-118">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="017a7-118">Create a project</span></span>

1. <span data-ttu-id="017a7-119">Откройте Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="017a7-119">Open Visual Studio 2017.</span></span> <span data-ttu-id="017a7-120">Выберите **Файл** > **Создать** > **Проект** в меню.</span><span class="sxs-lookup"><span data-stu-id="017a7-120">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="017a7-121">В диалоговом окне **Новый проект** выберите узел **Visual C#**, а затем — узел **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="017a7-121">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="017a7-122">Выберите шаблон проекта **Консольное приложение (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="017a7-122">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="017a7-123">В текстовое поле **Имя** введите GitHubIssueClassification, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="017a7-123">In the **Name** text box, type "GitHubIssueClassification" and then select the **OK** button.</span></span>

2. <span data-ttu-id="017a7-124">Создайте каталог с именем *Data* в папке проекта, чтобы сохранить в нем файлы с наборами данных:</span><span class="sxs-lookup"><span data-stu-id="017a7-124">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="017a7-125">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="017a7-125">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="017a7-126">Введите имя папки Data и нажмите клавишу "ВВОД".</span><span class="sxs-lookup"><span data-stu-id="017a7-126">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="017a7-127">Создайте каталог с именем *Models* в папке проекта, чтобы сохранить модель:</span><span class="sxs-lookup"><span data-stu-id="017a7-127">Create a directory named *Models* in your project to save your model:</span></span>

    <span data-ttu-id="017a7-128">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="017a7-128">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="017a7-129">Введите "Models" и нажмите ВВОД.</span><span class="sxs-lookup"><span data-stu-id="017a7-129">Type "Models" and hit Enter.</span></span>

4. <span data-ttu-id="017a7-130">Установите **пакет NuGet для Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="017a7-130">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="017a7-131">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="017a7-131">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="017a7-132">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите из списка пакет **v 1.0.0** и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="017a7-132">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select the **v 1.0.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="017a7-133">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="017a7-133">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="017a7-134">подготавливать данные;</span><span class="sxs-lookup"><span data-stu-id="017a7-134">Prepare your data</span></span>

1. <span data-ttu-id="017a7-135">Скачайте наборы данных [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) и [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) и сохраните их в ранее созданную папку *Data*.</span><span class="sxs-lookup"><span data-stu-id="017a7-135">Download the [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) and the [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="017a7-136">Первый из этих наборов данных обучает модель машинного обучения, а второй позволяет оценить точность полученной модели.</span><span class="sxs-lookup"><span data-stu-id="017a7-136">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="017a7-137">В обозревателе решений щелкните правой кнопкой мыши каждый из файлов \*.tsv и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="017a7-137">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="017a7-138">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="017a7-138">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="017a7-139">Создание классов и определение путей</span><span class="sxs-lookup"><span data-stu-id="017a7-139">Create classes and define paths</span></span>

<span data-ttu-id="017a7-140">Добавьте следующие новые операторы `using` в начало файла *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="017a7-140">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddUsings)]

<span data-ttu-id="017a7-141">Создайте три глобальных поля для хранения путей к недавно скачанным файлам и глобальные переменные для `MLContext`, `DataView` и `PredictionEngine`:</span><span class="sxs-lookup"><span data-stu-id="017a7-141">Create three global fields to hold the paths to the recently downloaded files, and global variables for the `MLContext`,`DataView`, and `PredictionEngine`:</span></span>

* <span data-ttu-id="017a7-142">`_trainDataPath` содержит путь к набору данных, используемому для обучения модели;</span><span class="sxs-lookup"><span data-stu-id="017a7-142">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="017a7-143">`_testDataPath` содержит путь к набору данных, используемому для оценки модели;</span><span class="sxs-lookup"><span data-stu-id="017a7-143">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="017a7-144">`_modelPath` содержит путь, по которому сохраняется обученная модель.</span><span class="sxs-lookup"><span data-stu-id="017a7-144">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="017a7-145">`_mlContext` соответствует классу <xref:Microsoft.ML.MLContext>, предоставляющему контекст для обработки;</span><span class="sxs-lookup"><span data-stu-id="017a7-145">`_mlContext` is the <xref:Microsoft.ML.MLContext> that provides processing context.</span></span>
* <span data-ttu-id="017a7-146">`_trainingDataView` представляет собой интерфейс <xref:Microsoft.ML.IDataView>, используемый для обработки обучающего набора данных;</span><span class="sxs-lookup"><span data-stu-id="017a7-146">`_trainingDataView` is the <xref:Microsoft.ML.IDataView> used to process the training dataset.</span></span>
* <span data-ttu-id="017a7-147">`_predEngine` соответствует классу <xref:Microsoft.ML.PredictionEngine%602>, используемому для одиночных прогнозов;</span><span class="sxs-lookup"><span data-stu-id="017a7-147">`_predEngine` is the <xref:Microsoft.ML.PredictionEngine%602> used for single predictions.</span></span>

<span data-ttu-id="017a7-148">Добавьте следующий код в строку непосредственно над методом `Main`, чтобы указать эти пути и другие переменные:</span><span class="sxs-lookup"><span data-stu-id="017a7-148">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="017a7-149">Создайте несколько классов для входных данных и прогнозов.</span><span class="sxs-lookup"><span data-stu-id="017a7-149">Create some classes for your input data and predictions.</span></span> <span data-ttu-id="017a7-150">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="017a7-150">Add a new class to your project:</span></span>

1. <span data-ttu-id="017a7-151">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="017a7-151">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="017a7-152">В диалоговом окне **Добавление нового элемента** выберите **Класс** и в поле **Имя** укажите *GitHubIssueData.cs*.</span><span class="sxs-lookup"><span data-stu-id="017a7-152">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *GitHubIssueData.cs*.</span></span> <span data-ttu-id="017a7-153">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="017a7-153">Then, select the **Add** button.</span></span>

    <span data-ttu-id="017a7-154">Файл *GitHubIssueData.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="017a7-154">The *GitHubIssueData.cs* file opens in the code editor.</span></span> <span data-ttu-id="017a7-155">Добавьте следующий оператор `using` в начало файла *GitHubIssueData.cs*:</span><span class="sxs-lookup"><span data-stu-id="017a7-155">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#AddUsings)]

<span data-ttu-id="017a7-156">Удалите из файла *GitHubIssueData.cs* существующее определение класса и добавьте следующий код с двумя классами `GitHubIssue` и `IssuePrediction`:</span><span class="sxs-lookup"><span data-stu-id="017a7-156">Remove the existing class definition and add the following code, which has two classes `GitHubIssue` and `IssuePrediction`, to the *GitHubIssueData.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](~/samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#DeclareTypes)]

<span data-ttu-id="017a7-157">`label` — это столбец для прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="017a7-157">The `label` is the column you want to predict.</span></span> <span data-ttu-id="017a7-158">Определены `Features`входные данные, которые вы предоставляете модели для прогнозирования метки.</span><span class="sxs-lookup"><span data-stu-id="017a7-158">The identified `Features` are the inputs you give the model to predict the Label.</span></span>

<span data-ttu-id="017a7-159">Используйте атрибут [LoadColumnAttribute](xref:Microsoft.ML.Data.LoadColumnAttribute), чтобы указать индексы исходных столбцов в файле набора данных.</span><span class="sxs-lookup"><span data-stu-id="017a7-159">Use the [LoadColumnAttribute](xref:Microsoft.ML.Data.LoadColumnAttribute) to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="017a7-160">`GitHubIssue` является классом входного набора данных и имеет следующие поля <xref:System.String>:</span><span class="sxs-lookup"><span data-stu-id="017a7-160">`GitHubIssue` is the input dataset class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="017a7-161">Первый столбец `ID` (идентификатор задачи GitHub).</span><span class="sxs-lookup"><span data-stu-id="017a7-161">the first column `ID` (GitHub Issue ID)</span></span>
* <span data-ttu-id="017a7-162">Второй столбец `Area` (прогноз для обучения).</span><span class="sxs-lookup"><span data-stu-id="017a7-162">the second column `Area` (the prediction for training)</span></span>
* <span data-ttu-id="017a7-163">Третий столбец `Title` (название задачи GitHub) является первым `feature`, используемым для прогнозирования `Area`</span><span class="sxs-lookup"><span data-stu-id="017a7-163">the third column `Title` (GitHub issue title) is the first `feature` used for predicting the `Area`</span></span>
* <span data-ttu-id="017a7-164">Четвертый столбец `Description` является вторым `feature`, используемым для прогнозирования `Area`</span><span class="sxs-lookup"><span data-stu-id="017a7-164">the fourth column  `Description` is the second `feature` used for predicting the `Area`</span></span>

<span data-ttu-id="017a7-165">Класс `IssuePrediction` используется для прогнозирования после обучения модели.</span><span class="sxs-lookup"><span data-stu-id="017a7-165">`IssuePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="017a7-166">Он имеет один параметр типа `string` (`Area`) и атрибут `PredictedLabel` `ColumnName`.</span><span class="sxs-lookup"><span data-stu-id="017a7-166">It has a single `string` (`Area`) and a `PredictedLabel` `ColumnName` attribute.</span></span>  <span data-ttu-id="017a7-167">`PredictedLabel` используется для прогнозирования и оценки.</span><span class="sxs-lookup"><span data-stu-id="017a7-167">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="017a7-168">Для оценки применяются входные обучающие данные, прогнозируемые значения и модель.</span><span class="sxs-lookup"><span data-stu-id="017a7-168">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="017a7-169">Все операции ML.NET запускаются в [классе MLContext](xref:Microsoft.ML.MLContext).</span><span class="sxs-lookup"><span data-stu-id="017a7-169">All ML.NET operations start in the [MLContext](xref:Microsoft.ML.MLContext) class.</span></span> <span data-ttu-id="017a7-170">Инициализация `mlContext` создает новую среду ML.NET, которую могут совместно использовать объекты рабочего процесса создания модели.</span><span class="sxs-lookup"><span data-stu-id="017a7-170">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="017a7-171">По сути, он аналогичен классу `DBContext` в `Entity Framework`.</span><span class="sxs-lookup"><span data-stu-id="017a7-171">It's similar, conceptually, to `DBContext` in `Entity Framework`.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="017a7-172">Инициализация переменных в методе Main</span><span class="sxs-lookup"><span data-stu-id="017a7-172">Initialize variables in Main</span></span>

<span data-ttu-id="017a7-173">Инициализируйте глобальную переменную `_mlContext` в новом экземпляре `MLContext` со случайным начальным значением (`seed: 0`) для получения воспроизводимых и детерминированных результатов при множестве циклов обучения.</span><span class="sxs-lookup"><span data-stu-id="017a7-173">Initialize the `_mlContext` global variable  with a new instance of `MLContext` with a random seed (`seed: 0`) for repeatable/deterministic results across multiple trainings.</span></span>  <span data-ttu-id="017a7-174">Замените строку `Console.WriteLine("Hello World!")` в методе `Main` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="017a7-174">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a><span data-ttu-id="017a7-175">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="017a7-175">Load the data</span></span>

<span data-ttu-id="017a7-176">ML.NET использует [класс IDataView](xref:Microsoft.ML.IDataView) как гибкий и эффективный способ описания числовых или текстовых табличных данных.</span><span class="sxs-lookup"><span data-stu-id="017a7-176">ML.NET uses the [IDataView class](xref:Microsoft.ML.IDataView) as a flexible, efficient way of describing numeric or text tabular data.</span></span> <span data-ttu-id="017a7-177">`IDataView` может загружать данные из текстового файла или в режиме реального времени (например, из базы данных SQL или файлов журнала).</span><span class="sxs-lookup"><span data-stu-id="017a7-177">`IDataView` can load either text files or in real time (for example, SQL database or log files).</span></span>

<span data-ttu-id="017a7-178">Чтобы инициализировать и загрузить глобальную переменную `_trainingDataView` для ее использования в конвейере, добавьте после инициализации `mlContext` следующий код:</span><span class="sxs-lookup"><span data-stu-id="017a7-178">To initialize and load the `_trainingDataView` global variable in order to use it for the pipeline, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[LoadTrainData](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTrainData)]

<span data-ttu-id="017a7-179">Метод [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) определяет схему данных и считывает файл.</span><span class="sxs-lookup"><span data-stu-id="017a7-179">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="017a7-180">Он принимает переменные, содержащие пути к данным, и возвращает объект `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="017a7-180">It takes in the data path variables and returns an `IDataView`.</span></span>

<span data-ttu-id="017a7-181">Добавьте в следующую строку метода `Main` приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="017a7-181">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallProcessData](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallProcessData)]

<span data-ttu-id="017a7-182">Метод `ProcessData` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="017a7-182">The `ProcessData` method executes the following tasks:</span></span>

* <span data-ttu-id="017a7-183">извлечение и преобразование данных;</span><span class="sxs-lookup"><span data-stu-id="017a7-183">Extracts and transforms the data.</span></span>
* <span data-ttu-id="017a7-184">возвращение конвейера обработки.</span><span class="sxs-lookup"><span data-stu-id="017a7-184">Returns the processing pipeline.</span></span>

<span data-ttu-id="017a7-185">Создайте метод `ProcessData` сразу после метода `Main`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="017a7-185">Create the `ProcessData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static IEstimator<ITransformer> ProcessData()
{

}
```

## <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="017a7-186">Извлечение компонентов и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="017a7-186">Extract Features and transform the data</span></span>

<span data-ttu-id="017a7-187">Мы хотим прогнозировать метки области GitHub для `GitHubIssue`, поэтому стоит использовать метод [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) для преобразования столбца `Area` в числовой тип ключа столбца `Label` (формат, который принимают алгоритмы классификации) и добавить его как новый столбец набора данных:</span><span class="sxs-lookup"><span data-stu-id="017a7-187">As you want to predict the Area GitHub label for a `GitHubIssue`, use the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method to transform the `Area` column into a numeric key type `Label` column (a format accepted by classification algorithms) and add it as a new dataset column:</span></span>

[!code-csharp[MapValueToKey](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#MapValueToKey)]

<span data-ttu-id="017a7-188">Затем вызовите `mlContext.Transforms.Text.FeaturizeText`, который преобразует столбцы текста (`Title` и `Description`) в числовой вектор для вызываемых `TitleFeaturized` и `DescriptionFeaturized` соответственно.</span><span class="sxs-lookup"><span data-stu-id="017a7-188">Next, call `mlContext.Transforms.Text.FeaturizeText` which transforms the text (`Title` and `Description`) columns into a numeric vector for each called `TitleFeaturized` and `DescriptionFeaturized`.</span></span> <span data-ttu-id="017a7-189">Добавьте присвоение признаков для обоих столбцов в конвейере, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="017a7-189">Append the featurization for both columns to the pipeline with the following code:</span></span>

[!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#FeaturizeText)]

<span data-ttu-id="017a7-190">Последний шаг на этапе подготовки данных заключается в объединении всех столбцов признаков в столбце **Features** с помощью метода преобразования [Concatenate()](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A).</span><span class="sxs-lookup"><span data-stu-id="017a7-190">The last step in data preparation combines all of the feature columns into the **Features** column using the [Concatenate()](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A) method.</span></span> <span data-ttu-id="017a7-191">По умолчанию алгоритм обучения обрабатывает только признаки, представленные в столбце **Features**.</span><span class="sxs-lookup"><span data-stu-id="017a7-191">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="017a7-192">Добавьте это преобразование в конвейер, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="017a7-192">Append this transformation to the pipeline with the following code:</span></span>

[!code-csharp[Concatenate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Concatenate)]

 <span data-ttu-id="017a7-193">Затем добавьте <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A> для кэширования DataView, которое может ускорить обучение при многократных итерациях по данным, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="017a7-193">Next, append a <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A> to cache the DataView so when you iterate over the data multiple times using the cache might get better performance, as with the following code:</span></span>

[!code-csharp[AppendCache](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AppendCache)]

> [!WARNING]
> <span data-ttu-id="017a7-194">Используйте AppendCacheCheckpoint для небольших и средних наборов данных для ускорения обучения.</span><span class="sxs-lookup"><span data-stu-id="017a7-194">Use AppendCacheCheckpoint for small/medium datasets to lower training time.</span></span> <span data-ttu-id="017a7-195">НЕ используйте AppendCacheCheckpoint (удалите .AppendCacheCheckpoint()) при обработке очень больших наборов данных.</span><span class="sxs-lookup"><span data-stu-id="017a7-195">Do NOT use it (remove .AppendCacheCheckpoint()) when handling very large datasets.</span></span>

<span data-ttu-id="017a7-196">Выполните возврат конвейера в конце метода `ProcessData`.</span><span class="sxs-lookup"><span data-stu-id="017a7-196">Return the pipeline at the end of the `ProcessData` method.</span></span>

[!code-csharp[ReturnPipeline](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnPipeline)]

<span data-ttu-id="017a7-197">На этом этапе выполняется предварительная обработка и присвоение признаков.</span><span class="sxs-lookup"><span data-stu-id="017a7-197">This step handles preprocessing/featurization.</span></span> <span data-ttu-id="017a7-198">Дополнительные компоненты из ML.NET могут дать более точные результаты для вашей модели.</span><span class="sxs-lookup"><span data-stu-id="017a7-198">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="build-and-train-the-model"></a><span data-ttu-id="017a7-199">Сборка и обучение модели</span><span class="sxs-lookup"><span data-stu-id="017a7-199">Build and train the model</span></span>

<span data-ttu-id="017a7-200">В следующей строке кода в методе `Main` добавьте приведенный ниже вызов метода `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="017a7-200">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="017a7-201">Метод `BuildAndTrainModel` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="017a7-201">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="017a7-202">создание класса алгоритма обучения;</span><span class="sxs-lookup"><span data-stu-id="017a7-202">Creates the training algorithm class.</span></span>
* <span data-ttu-id="017a7-203">обучение модели;</span><span class="sxs-lookup"><span data-stu-id="017a7-203">Trains the model.</span></span>
* <span data-ttu-id="017a7-204">прогнозирование области на основе обучающих данных;</span><span class="sxs-lookup"><span data-stu-id="017a7-204">Predicts area based on training data.</span></span>
* <span data-ttu-id="017a7-205">возвращение модели.</span><span class="sxs-lookup"><span data-stu-id="017a7-205">Returns the model.</span></span>

<span data-ttu-id="017a7-206">Создайте метод `BuildAndTrainModel` сразу после метода `Main`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="017a7-206">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static IEstimator<ITransformer> BuildAndTrainModel(IDataView trainingDataView, IEstimator<ITransformer> pipeline)
{

}
```

### <a name="about-the-classification-task"></a><span data-ttu-id="017a7-207">Сведения о задаче классификации</span><span class="sxs-lookup"><span data-stu-id="017a7-207">About the classification task</span></span>

<span data-ttu-id="017a7-208">Классификацией называют задачу машинного обучения, которая использует данные для **определения** категории, типа или класса для некоторого элемента или ряда данных. Часто она имеет следующие виды:</span><span class="sxs-lookup"><span data-stu-id="017a7-208">Classification is a machine learning task that uses data to **determine** the category, type, or class of an item or row of data and is frequently one of the following types:</span></span>

* <span data-ttu-id="017a7-209">Двоичная: A или B.</span><span class="sxs-lookup"><span data-stu-id="017a7-209">Binary: either A or B.</span></span>
* <span data-ttu-id="017a7-210">Многоклассовая: несколько категорий, которые прогнозируются по одной модели.</span><span class="sxs-lookup"><span data-stu-id="017a7-210">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="017a7-211">Для таких проблем используйте обучающий алгоритм многоклассовой классификации, поскольку прогноз категории проблемы может относиться к нескольким категориям (многоклассовая), а не только к двум (двоичная).</span><span class="sxs-lookup"><span data-stu-id="017a7-211">For this type of problem, use a Multiclass classification learning algorithm, since your issue category prediction can be one of multiple categories (multiclass) rather than just two (binary).</span></span>

<span data-ttu-id="017a7-212">Добавьте алгоритм машинного обучения к определениям преобразований данных, добавив следующее в первой строке кода в `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="017a7-212">Append the machine learning algorithm to the data transformation definitions by adding the following as the first line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[AddTrainer](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTrainer)]

<span data-ttu-id="017a7-213">[SdcaMaximumEntropy](xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer) — ваш алгоритм обучения классификации по нескольким классам.</span><span class="sxs-lookup"><span data-stu-id="017a7-213">The [SdcaMaximumEntropy](xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer) is your multiclass classification training algorithm.</span></span> <span data-ttu-id="017a7-214">Он добавляется в `pipeline` и принимает в качестве входных параметров `Title` и `Description` (`Features`) с присвоенными признаками, а также `Label` для обучения по историческим данным.</span><span class="sxs-lookup"><span data-stu-id="017a7-214">This is appended to the `pipeline` and accepts the featurized `Title` and `Description` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="017a7-215">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="017a7-215">Train the model</span></span>

<span data-ttu-id="017a7-216">Обучите модель на основе данных `splitTrainSet` и получите обученную модель, добавив в метод `BuildAndTrainModel()` следующие строки кода:</span><span class="sxs-lookup"><span data-stu-id="017a7-216">Fit the model to the `splitTrainSet` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#TrainModel)]

<span data-ttu-id="017a7-217">Метод `Fit()` обучает модель путем преобразования набора данных и применения обучения.</span><span class="sxs-lookup"><span data-stu-id="017a7-217">The `Fit()`method trains your model by transforming the dataset and applying the training.</span></span>

<span data-ttu-id="017a7-218">Класс [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) представляет собой удобный API, позволяющий передать один экземпляр данных и осуществить прогнозирование на его основе.</span><span class="sxs-lookup"><span data-stu-id="017a7-218">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to pass in and then perform a prediction on a single instance of data.</span></span> <span data-ttu-id="017a7-219">Добавьте следующую строку кода в метод `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="017a7-219">Add this as the next line in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[CreatePredictionEngine1](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine1)]

### <a name="predict-with-the-trained-model"></a><span data-ttu-id="017a7-220">Прогнозирование с помощью обученной модели</span><span class="sxs-lookup"><span data-stu-id="017a7-220">Predict with the trained model</span></span>

<span data-ttu-id="017a7-221">Добавьте задачу GitHub для тестирования прогноза обученной модели в методе `Predict`, создав экземпляр `GitHubIssue`:</span><span class="sxs-lookup"><span data-stu-id="017a7-221">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[CreateTestIssue1](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateTestIssue1)]

<span data-ttu-id="017a7-222">Используйте функцию [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A), которая создает прогноз по одной строке данных.</span><span class="sxs-lookup"><span data-stu-id="017a7-222">Use the [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Predict)]

### <a name="using-the-model-prediction-results"></a><span data-ttu-id="017a7-223">Использование модели: результаты прогнозирования</span><span class="sxs-lookup"><span data-stu-id="017a7-223">Using the model: prediction results</span></span>

<span data-ttu-id="017a7-224">Отобразите `GitHubIssue` и соответствующий прогноз метки `Area`, чтобы поделиться результатами и обработать их должным образом.</span><span class="sxs-lookup"><span data-stu-id="017a7-224">Display `GitHubIssue` and corresponding `Area` label prediction in order to share the results and act on them accordingly.</span></span>  <span data-ttu-id="017a7-225">Создайте отображение для результатов с помощью следующего кода <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="017a7-225">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="017a7-226">Возврат обученной модели для оценки</span><span class="sxs-lookup"><span data-stu-id="017a7-226">Return the model trained to use for evaluation</span></span>

<span data-ttu-id="017a7-227">Выполните возврат модели в конце метода `BuildAndTrainModel`.</span><span class="sxs-lookup"><span data-stu-id="017a7-227">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a><span data-ttu-id="017a7-228">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="017a7-228">Evaluate the model</span></span>

<span data-ttu-id="017a7-229">Итак, вы завершили создание и обучение модели, и теперь ее можно оценить по другому набору данных, чтобы проверить ее точность и качество прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="017a7-229">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="017a7-230">В методе `Evaluate` передается для оценки модель, созданная в `BuildAndTrainModel`.</span><span class="sxs-lookup"><span data-stu-id="017a7-230">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="017a7-231">Создайте метод `Evaluate` сразу после метода `BuildAndTrainModel` как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="017a7-231">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate()
{

}
```

<span data-ttu-id="017a7-232">Метод `Evaluate` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="017a7-232">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="017a7-233">загрузка тестового набора данных;</span><span class="sxs-lookup"><span data-stu-id="017a7-233">Loads the test dataset.</span></span>
* <span data-ttu-id="017a7-234">создание средства оценки многоклассовой классификации;</span><span class="sxs-lookup"><span data-stu-id="017a7-234">Creates the multiclass evaluator.</span></span>
* <span data-ttu-id="017a7-235">оценка модели и создание метрик;</span><span class="sxs-lookup"><span data-stu-id="017a7-235">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="017a7-236">отображение метрик.</span><span class="sxs-lookup"><span data-stu-id="017a7-236">Displays the metrics.</span></span>

<span data-ttu-id="017a7-237">Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `BuildAndTrainModel`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="017a7-237">Add a call to the new method from the `Main` method, right under the `BuildAndTrainModel` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallEvaluate)]

<span data-ttu-id="017a7-238">Как и ранее с набором данных для обучения, загрузите тестовый набор данных, добавив следующий код в метод `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="017a7-238">As you did previously with the training dataset, load the test dataset by adding the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTestDataset)]

<span data-ttu-id="017a7-239">Метод [Evaluate()](xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A) вычисляет метрики качества для модели на основе указанного набора данных.</span><span class="sxs-lookup"><span data-stu-id="017a7-239">The [Evaluate()](xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A) method computes the quality metrics for the model using the specified dataset.</span></span> <span data-ttu-id="017a7-240">Он возвращает объект <xref:Microsoft.ML.Data.MulticlassClassificationMetrics>, содержащий общие метрики, вычисляемые средствами оценки многоклассовой классификации.</span><span class="sxs-lookup"><span data-stu-id="017a7-240">It returns a <xref:Microsoft.ML.Data.MulticlassClassificationMetrics> object that contains the overall metrics computed by multiclass classification evaluators.</span></span>
<span data-ttu-id="017a7-241">Чтобы отобразить метрики для оценки качества модели, сначала их необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="017a7-241">To display the metrics to determine the quality of the model, you need to get them first.</span></span>
<span data-ttu-id="017a7-242">Используйте метод [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) для глобальной переменной `_trainedModel` машинного обучения ([ITransformer](xref:Microsoft.ML.ITransformer)) для ввода признаков и возврата прогнозов.</span><span class="sxs-lookup"><span data-stu-id="017a7-242">Notice the use of the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method of the machine learning `_trainedModel` global variable (an [ITransformer](xref:Microsoft.ML.ITransformer)) to input the features and return predictions.</span></span> <span data-ttu-id="017a7-243">В качестве следующей строки в методе `Evaluate` добавьте приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="017a7-243">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[Evaluate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Evaluate)]

<span data-ttu-id="017a7-244">Для многоклассовой классификации выполняется оценка следующих метрик:</span><span class="sxs-lookup"><span data-stu-id="017a7-244">The following metrics are evaluated for multiclass classification:</span></span>

* <span data-ttu-id="017a7-245">Микроточность — на метрику точности в равной степени влияет каждая пара "пример-класс".</span><span class="sxs-lookup"><span data-stu-id="017a7-245">Micro Accuracy - Every sample-class pair contributes equally to the accuracy metric.</span></span>  <span data-ttu-id="017a7-246">Значение микроточности должно быть максимально близко к 1.</span><span class="sxs-lookup"><span data-stu-id="017a7-246">You want Micro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="017a7-247">Макроточность — на метрику точности в равной степени влияет каждый класс.</span><span class="sxs-lookup"><span data-stu-id="017a7-247">Macro Accuracy - Every class contributes equally to the accuracy metric.</span></span> <span data-ttu-id="017a7-248">Миноритарным классам назначается тот же вес, что и более крупным.</span><span class="sxs-lookup"><span data-stu-id="017a7-248">Minority classes are given equal weight as the larger classes.</span></span> <span data-ttu-id="017a7-249">Значение макроточности должно быть максимально близко к 1.</span><span class="sxs-lookup"><span data-stu-id="017a7-249">You want Macro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="017a7-250">Логарифмические потери — см. термин [логарифмические потери](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="017a7-250">Log-loss - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="017a7-251">Значение логарифмических потерь должно быть максимально близко к нулю.</span><span class="sxs-lookup"><span data-stu-id="017a7-251">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="017a7-252">Минимизация логарифмических потерь — находится в диапазоне [-inf, 100], где 100 — идеальный прогноз, а 0 — среднее прогнозное значение.</span><span class="sxs-lookup"><span data-stu-id="017a7-252">Log-loss reduction - Ranges from [-inf, 100], where 100 is perfect predictions and 0 indicates mean predictions.</span></span> <span data-ttu-id="017a7-253">Значение минимизации логарифмических потерь должно быть максимально близко к нулю.</span><span class="sxs-lookup"><span data-stu-id="017a7-253">You want Log-loss reduction to be as close to zero as possible.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="017a7-254">Отображение метрик для проверки модели</span><span class="sxs-lookup"><span data-stu-id="017a7-254">Displaying the metrics for model validation</span></span>

<span data-ttu-id="017a7-255">Используйте следующий код для отображения метрик, передачи результатов и выполнения действий по ним:</span><span class="sxs-lookup"><span data-stu-id="017a7-255">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayMetrics)]

## <a name="deploy-and-predict-with-a-model"></a><span data-ttu-id="017a7-256">Развертывание и прогнозирование с помощью модели</span><span class="sxs-lookup"><span data-stu-id="017a7-256">Deploy and Predict with a model</span></span>

<span data-ttu-id="017a7-257">Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `Evaluate`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="017a7-257">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredictIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallPredictIssue)]

<span data-ttu-id="017a7-258">Создайте метод `PredictIssue` сразу после метода `Evaluate` (и непосредственно перед методом `SaveModelAsFile`), вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="017a7-258">Create the `PredictIssue` method, just after the `Evaluate` method (and just before the `SaveModelAsFile` method), using the following code:</span></span>

```csharp
private static void PredictIssue()
{

}
```

<span data-ttu-id="017a7-259">Метод `PredictIssue` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="017a7-259">The `PredictIssue` method executes the following tasks:</span></span>

* <span data-ttu-id="017a7-260">создание одной задачи с тестовыми данными;</span><span class="sxs-lookup"><span data-stu-id="017a7-260">Creates a single issue of test data.</span></span>
* <span data-ttu-id="017a7-261">прогнозирование области на основе тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="017a7-261">Predicts Area based on test data.</span></span>
* <span data-ttu-id="017a7-262">объединение тестовых данных и прогнозов для создания отчетов;</span><span class="sxs-lookup"><span data-stu-id="017a7-262">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="017a7-263">отображение результатов прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="017a7-263">Displays the predicted results.</span></span>

<span data-ttu-id="017a7-264">Добавьте задачу GitHub для тестирования прогноза обученной модели в методе `Predict`, создав экземпляр `GitHubIssue`:</span><span class="sxs-lookup"><span data-stu-id="017a7-264">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[AddTestIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTestIssue)]

<span data-ttu-id="017a7-265">Как и ранее, создайте экземпляр `PredictionEngine` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="017a7-265">As you did previously, create a `PredictionEngine` instance with the following code:</span></span>

[!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]
  
<span data-ttu-id="017a7-266">Используйте `PredictionEngine` для прогнозирования метки области GitHub, добавив следующий код в метод прогноза `PredictIssue`:</span><span class="sxs-lookup"><span data-stu-id="017a7-266">Use the `PredictionEngine` to predict the Area GitHub label by adding the following code to the `PredictIssue` method for the prediction:</span></span>

[!code-csharp[PredictIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a><span data-ttu-id="017a7-267">Использование загружаемой модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="017a7-267">Using the loaded model for prediction</span></span>

<span data-ttu-id="017a7-268">Отобразите `Area`, чтобы категоризировать задачу и обработать ее должным образом.</span><span class="sxs-lookup"><span data-stu-id="017a7-268">Display `Area` in order to categorize the issue and act on it accordingly.</span></span> <span data-ttu-id="017a7-269">Создайте отображение для результатов с помощью следующего кода <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="017a7-269">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayResults](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayResults)]

## <a name="results"></a><span data-ttu-id="017a7-270">Результаты</span><span class="sxs-lookup"><span data-stu-id="017a7-270">Results</span></span>

<span data-ttu-id="017a7-271">Результаты выполнения должны выглядеть примерно так, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="017a7-271">Your results should be similar to the following.</span></span> <span data-ttu-id="017a7-272">В процессе работы конвейер выводит сообщения.</span><span class="sxs-lookup"><span data-stu-id="017a7-272">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="017a7-273">Вы можете видеть предупреждения или обработанные сообщения.</span><span class="sxs-lookup"><span data-stu-id="017a7-273">You may see warnings, or processing messages.</span></span> <span data-ttu-id="017a7-274">Для удобства эти сообщения удалены из следующих результатов.</span><span class="sxs-lookup"><span data-stu-id="017a7-274">These messages have been removed from the following results for clarity.</span></span>

```console
=============== Single Prediction just-trained-model - Result: area-System.Net ===============
*************************************************************************************************************
*       Metrics for Multi-class Classification model - Test Data
*------------------------------------------------------------------------------------------------------------
*       MicroAccuracy:    0.738
*       MacroAccuracy:    0.668
*       LogLoss:          .919
*       LogLossReduction: .643
*************************************************************************************************************
=============== Single Prediction - Result: area-System.Data ===============
```

<span data-ttu-id="017a7-275">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="017a7-275">Congratulations!</span></span> <span data-ttu-id="017a7-276">Вы успешно создали модель машинного обучения для классификации и прогнозирования метки области у задачи GitHub.</span><span class="sxs-lookup"><span data-stu-id="017a7-276">You've now successfully built a machine learning model for classifying and predicting an Area label for a GitHub issue.</span></span> <span data-ttu-id="017a7-277">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="017a7-277">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="017a7-278">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="017a7-278">Next steps</span></span>

<span data-ttu-id="017a7-279">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="017a7-279">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="017a7-280">подготавливать данные;</span><span class="sxs-lookup"><span data-stu-id="017a7-280">Prepare your data</span></span>
> * <span data-ttu-id="017a7-281">Преобразование данных</span><span class="sxs-lookup"><span data-stu-id="017a7-281">Transform the data</span></span>
> * <span data-ttu-id="017a7-282">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="017a7-282">Train the model</span></span>
> * <span data-ttu-id="017a7-283">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="017a7-283">Evaluate the model</span></span>
> * <span data-ttu-id="017a7-284">Прогнозирование с помощью обученной модели</span><span class="sxs-lookup"><span data-stu-id="017a7-284">Predict with the trained model</span></span>
> * <span data-ttu-id="017a7-285">Развертывание и прогнозирование с помощью загруженной модели</span><span class="sxs-lookup"><span data-stu-id="017a7-285">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="017a7-286">Переходите к следующему руководству:</span><span class="sxs-lookup"><span data-stu-id="017a7-286">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="017a7-287">Прогнозирование платы за такси</span><span class="sxs-lookup"><span data-stu-id="017a7-287">Taxi Fare Predictor</span></span>](taxi-fare.md)
