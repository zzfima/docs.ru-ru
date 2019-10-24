---
title: Учебник. Анализ комментариев на веб-сайте — двоичная классификация
description: В этом руководстве показано, как создать консольное приложение .NET Core, которое классифицирует мнения, выраженные в комментариях с веб-сайта, и предпринимает соответствующие действия. Двоичный классификатор тональности использует C# в Visual Studio.
ms.date: 09/30/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: e241ae8c0d39e6573b40c69611985f7095114629
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320148"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-with-binary-classification-in-mlnet"></a><span data-ttu-id="5b5db-104">Учебник. Анализ мнений пользователей в комментариях с веб-сайта с помощью двоичной классификации в ML.NET</span><span class="sxs-lookup"><span data-stu-id="5b5db-104">Tutorial: Analyze sentiment of website comments with binary classification in ML.NET</span></span>

<span data-ttu-id="5b5db-105">В этом руководстве показано, как создать консольное приложение .NET Core, которое классифицирует мнения, выраженные в комментариях с веб-сайта, и предпринимает соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="5b5db-105">This tutorial shows you how to create a .NET Core console application that classifies sentiment from website comments and takes the appropriate action.</span></span> <span data-ttu-id="5b5db-106">Двоичный классификатор тональности использует C# в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="5b5db-106">The binary sentiment classifier uses C# in Visual Studio 2017.</span></span>

<span data-ttu-id="5b5db-107">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="5b5db-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="5b5db-108">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="5b5db-108">Create a console application</span></span>
> - <span data-ttu-id="5b5db-109">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="5b5db-109">Prepare data</span></span>
> - <span data-ttu-id="5b5db-110">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="5b5db-110">Load the data</span></span>
> - <span data-ttu-id="5b5db-111">Сборка и обучение модели</span><span class="sxs-lookup"><span data-stu-id="5b5db-111">Build and train the model</span></span>
> - <span data-ttu-id="5b5db-112">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="5b5db-112">Evaluate the model</span></span>
> - <span data-ttu-id="5b5db-113">Использование модели для прогноза</span><span class="sxs-lookup"><span data-stu-id="5b5db-113">Use the model to make a prediction</span></span>
> - <span data-ttu-id="5b5db-114">Просмотр результатов</span><span class="sxs-lookup"><span data-stu-id="5b5db-114">See the results</span></span>

<span data-ttu-id="5b5db-115">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="5b5db-115">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5b5db-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="5b5db-116">Prerequisites</span></span>

- <span data-ttu-id="5b5db-117">[Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="5b5db-117">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed</span></span>

- <span data-ttu-id="5b5db-118">[Набор данных — предложения с меткой тональности UCI](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (ZIP-файл)</span><span class="sxs-lookup"><span data-stu-id="5b5db-118">[UCI Sentiment Labeled Sentences dataset](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (ZIP file)</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="5b5db-119">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="5b5db-119">Create a console application</span></span>

1. <span data-ttu-id="5b5db-120">Создайте **консольное приложение .NET Core** с именем SentimentAnalysis.</span><span class="sxs-lookup"><span data-stu-id="5b5db-120">Create a **.NET Core Console Application** called "SentimentAnalysis".</span></span>

2. <span data-ttu-id="5b5db-121">Создайте каталог с именем *Data* в проекте, чтобы сохранять файлы набора данных.</span><span class="sxs-lookup"><span data-stu-id="5b5db-121">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="5b5db-122">Установите **пакет NuGet для Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="5b5db-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="5b5db-123">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="5b5db-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="5b5db-124">Выберите nuget.org в качестве источника пакета, а затем выберите вкладку **Обзор**. Найдите **Microsoft.ML**, выберите пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="5b5db-124">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="5b5db-125">Продолжите установку, соглашаясь с условиями лицензии для выбранного пакета.</span><span class="sxs-lookup"><span data-stu-id="5b5db-125">Proceed with the installation by agreeing to the license terms for the package you choose.</span></span> <span data-ttu-id="5b5db-126">Сделайте то же самое для пакета **Microsoft.ML.FastTree** в NuGet.</span><span class="sxs-lookup"><span data-stu-id="5b5db-126">Do the same for the **Microsoft.ML.FastTree** NuGet package.</span></span>

## <a name="prepare-your-data"></a><span data-ttu-id="5b5db-127">подготавливать данные;</span><span class="sxs-lookup"><span data-stu-id="5b5db-127">Prepare your data</span></span>

> [!NOTE]
> <span data-ttu-id="5b5db-128">Наборы данных в этом руководстве взяты из статьи From Group to Individual Labels using Deep Features ("Переход от групповых меток к индивидуальным при помощи глубинных признаков"), Котциас (Kotzias) и</span><span class="sxs-lookup"><span data-stu-id="5b5db-128">The datasets for this tutorial are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="5b5db-129">др.,</span><span class="sxs-lookup"><span data-stu-id="5b5db-129">al,.</span></span> <span data-ttu-id="5b5db-130">KDD 2015, и размещены в репозитории машинного обучения UCI Д. Дуа (D. Dua) и Э. Карра Танискиду (E. Karra Taniskidou) (2017).</span><span class="sxs-lookup"><span data-stu-id="5b5db-130">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="5b5db-131">UCI Machine Learning Repository (Репозиторий машинного обучения UCI) [http://archive.ics.uci.edu/ml ].</span><span class="sxs-lookup"><span data-stu-id="5b5db-131">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="5b5db-132">Ирвайн, Калифорния: Калифорнийский университет, Школа информационных технологий и компьютерных наук.</span><span class="sxs-lookup"><span data-stu-id="5b5db-132">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

1. <span data-ttu-id="5b5db-133">Скачайте [ZIP-файл набора данных предложений с меткой тональности UCI](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) и извлеките его содержимое.</span><span class="sxs-lookup"><span data-stu-id="5b5db-133">Download [UCI Sentiment Labeled Sentences dataset ZIP file](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="5b5db-134">Скопируйте файл `yelp_labelled.txt` в созданный каталог *Data*.</span><span class="sxs-lookup"><span data-stu-id="5b5db-134">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

3. <span data-ttu-id="5b5db-135">В обозревателе решений щелкните правой кнопкой мыши файл `yelp_labeled.txt` и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="5b5db-135">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="5b5db-136">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="5b5db-136">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="5b5db-137">Создание классов и определение путей</span><span class="sxs-lookup"><span data-stu-id="5b5db-137">Create classes and define paths</span></span>

1. <span data-ttu-id="5b5db-138">Добавьте следующие новые операторы `using` в начало файла *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="5b5db-138">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="5b5db-139">Добавьте следующий код в строку прямо над методом `Main`, чтобы создать поле для хранения недавно скачанного пути к файлу набора данных:</span><span class="sxs-lookup"><span data-stu-id="5b5db-139">Add the following code to the line right above the `Main` method, to create a field to hold the recently downloaded dataset file path:</span></span>

    [!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DeclareGlobalVariables "Declare global variables")]

1. <span data-ttu-id="5b5db-140">Затем создайте классы для входных данных и прогнозов.</span><span class="sxs-lookup"><span data-stu-id="5b5db-140">Next, create classes for your input data and predictions.</span></span> <span data-ttu-id="5b5db-141">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="5b5db-141">Add a new class to your project:</span></span>

    - <span data-ttu-id="5b5db-142">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="5b5db-142">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

    - <span data-ttu-id="5b5db-143">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="5b5db-143">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="5b5db-144">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5b5db-144">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="5b5db-145">Файл *SentimentData.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="5b5db-145">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="5b5db-146">Добавьте следующий оператор `using` в начало файла *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="5b5db-146">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="5b5db-147">Удалите из файла *SentimentData.cs* существующее определение класса и добавьте следующий код с двумя классами `SentimentData` и `SentimentPrediction`:</span><span class="sxs-lookup"><span data-stu-id="5b5db-147">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

    [!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#DeclareTypes "Declare data record types")]

### <a name="how-the-data-was-prepared"></a><span data-ttu-id="5b5db-148">Как вы подготовили данные</span><span class="sxs-lookup"><span data-stu-id="5b5db-148">How the data was prepared</span></span>
<span data-ttu-id="5b5db-149">Класс входного набора данных, `SentimentData`, имеет `string` для комментариев пользователя (`SentimentText`) и `bool` (`Sentiment`) значение 1 (положительная) или 0 (отрицательная) для определения тональности.</span><span class="sxs-lookup"><span data-stu-id="5b5db-149">The input dataset class, `SentimentData`, has a `string` for user comments (`SentimentText`) and a `bool` (`Sentiment`) value of either 1 (positive) or 0 (negative) for sentiment.</span></span> <span data-ttu-id="5b5db-150">Оба поля имеют атрибуты [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29), которые описывают порядок файла данных каждого поля.</span><span class="sxs-lookup"><span data-stu-id="5b5db-150">Both fields have [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attributes attached to them, which describes the data file order of each field.</span></span>  <span data-ttu-id="5b5db-151">Кроме того, свойство `Sentiment` имеет атрибут[ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A), чтобы обозначить его как поле `Label`.</span><span class="sxs-lookup"><span data-stu-id="5b5db-151">In addition, the `Sentiment` property has a [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) attribute to designate it as the `Label` field.</span></span> <span data-ttu-id="5b5db-152">В примере файла ниже отсутствует строка заголовка. Сам файл выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5b5db-152">The following example file doesn't have a header row, and looks like this:</span></span>

|<span data-ttu-id="5b5db-153">SentimentText</span><span class="sxs-lookup"><span data-stu-id="5b5db-153">SentimentText</span></span>                         |<span data-ttu-id="5b5db-154">Тональность (метка)</span><span class="sxs-lookup"><span data-stu-id="5b5db-154">Sentiment (Label)</span></span> |
|--------------------------------------|----------|
|<span data-ttu-id="5b5db-155">Официантка немного медленная.</span><span class="sxs-lookup"><span data-stu-id="5b5db-155">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="5b5db-156">0</span><span class="sxs-lookup"><span data-stu-id="5b5db-156">0</span></span>     |
|<span data-ttu-id="5b5db-157">Корочка так себе.</span><span class="sxs-lookup"><span data-stu-id="5b5db-157">Crust is not good.</span></span>                    |    <span data-ttu-id="5b5db-158">0</span><span class="sxs-lookup"><span data-stu-id="5b5db-158">0</span></span>     |
|<span data-ttu-id="5b5db-159">Ого... Отличное место.</span><span class="sxs-lookup"><span data-stu-id="5b5db-159">Wow... Loved this place.</span></span>              |    <span data-ttu-id="5b5db-160">1</span><span class="sxs-lookup"><span data-stu-id="5b5db-160">1</span></span>     |
|<span data-ttu-id="5b5db-161">Обслуживание очень быстрое.</span><span class="sxs-lookup"><span data-stu-id="5b5db-161">Service was very prompt.</span></span>              |    <span data-ttu-id="5b5db-162">1</span><span class="sxs-lookup"><span data-stu-id="5b5db-162">1</span></span>     |

<span data-ttu-id="5b5db-163">`SentimentPrediction` — этот класс прогноза используется после обучения модели.</span><span class="sxs-lookup"><span data-stu-id="5b5db-163">`SentimentPrediction` is the prediction class used after model training.</span></span> <span data-ttu-id="5b5db-164">Он наследует от `SentimentData` таким образом, чтобы входные данные `SentimentText` могли отображаться вместе с выходными данными прогноза.</span><span class="sxs-lookup"><span data-stu-id="5b5db-164">It inherits from `SentimentData` so that the input `SentimentText` can be displayed along with the output prediction.</span></span> <span data-ttu-id="5b5db-165">Логическое значение `Prediction` является значением, которое модель прогнозирует при предоставлении новых входных данных `SentimentText`.</span><span class="sxs-lookup"><span data-stu-id="5b5db-165">The `Prediction` boolean is the value that the model predicts when supplied with new input `SentimentText`.</span></span>

<span data-ttu-id="5b5db-166">Класс выходных данных `SentimentPrediction` содержит два свойства, вычисляемые в модели: `Score` — необработанная оценка, вычисляемая в модели, и `Probability` — оценка, откалиброванная по вероятности того, что текст имеет положительную тональность.</span><span class="sxs-lookup"><span data-stu-id="5b5db-166">The output class `SentimentPrediction` contains two other properties calculated by the model: `Score` - the raw score calculated by the model, and `Probability` - the score calibrated to the likelihood of the text having positive sentiment.</span></span>

<span data-ttu-id="5b5db-167">В этом учебнике самым важным свойством является `Prediction`.</span><span class="sxs-lookup"><span data-stu-id="5b5db-167">For this tutorial, the most important property is `Prediction`.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="5b5db-168">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="5b5db-168">Load the data</span></span>
<span data-ttu-id="5b5db-169">Данные в ML.NET представлены [классом IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="5b5db-169">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="5b5db-170">`IDataView` позволяет гибко и полно описывать табличные данные (числовые и текстовые).</span><span class="sxs-lookup"><span data-stu-id="5b5db-170">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="5b5db-171">Данные можно загружать в объект `IDataView` из текстового файла или в режиме реального времени (например, из базы данных SQL или файлов журнала).</span><span class="sxs-lookup"><span data-stu-id="5b5db-171">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="5b5db-172">[Класс MLContext](xref:Microsoft.ML.MLContext) является отправной точкой для всех операций ML.NET.</span><span class="sxs-lookup"><span data-stu-id="5b5db-172">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="5b5db-173">Инициализация `mlContext` создает новую среду ML.NET, которую могут совместно использовать объекты рабочего процесса создания модели.</span><span class="sxs-lookup"><span data-stu-id="5b5db-173">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="5b5db-174">По существу он аналогичен классу `DBContext` в Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="5b5db-174">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="5b5db-175">Необходимо подготовить приложение и затем загружать данные.</span><span class="sxs-lookup"><span data-stu-id="5b5db-175">You prepare the app, and then load data:</span></span>

1. <span data-ttu-id="5b5db-176">Замените строку `Console.WriteLine("Hello World!")` в методе `Main` следующим кодом, чтобы объявить и инициализировать переменную mlContext:</span><span class="sxs-lookup"><span data-stu-id="5b5db-176">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

    [!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateMLContext "Create the ML Context")]

2. <span data-ttu-id="5b5db-177">Добавьте в следующую строку метода `Main()` приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="5b5db-177">Add the following as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallLoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallLoadData)]

3. <span data-ttu-id="5b5db-178">Создайте метод `LoadData()` сразу после метода `Main()`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="5b5db-178">Create the `LoadData()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static TrainTestData LoadData(MLContext mlContext)
    {

    }
    ```

    <span data-ttu-id="5b5db-179">Метод `LoadData()` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="5b5db-179">The `LoadData()` method executes the following tasks:</span></span>

    - <span data-ttu-id="5b5db-180">загрузка данных;</span><span class="sxs-lookup"><span data-stu-id="5b5db-180">Loads the data.</span></span>
    - <span data-ttu-id="5b5db-181">Разделяет скачанный набор данных на наборы данных для обучения и тестирования.</span><span class="sxs-lookup"><span data-stu-id="5b5db-181">Splits the loaded dataset into train and test datasets.</span></span>
    - <span data-ttu-id="5b5db-182">Возвращает два набора данных — для обучения и для тестирования.</span><span class="sxs-lookup"><span data-stu-id="5b5db-182">Returns the split train and test datasets.</span></span>

4. <span data-ttu-id="5b5db-183">Добавьте следующий код в первую строку метода `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="5b5db-183">Add the following code as the first line of the `LoadData()` method:</span></span>

    [!code-csharp[LoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadData "loading dataset")]

    <span data-ttu-id="5b5db-184">Метод [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) определяет схему данных и считывает файл.</span><span class="sxs-lookup"><span data-stu-id="5b5db-184">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="5b5db-185">Он принимает переменные, содержащие пути к данным, и возвращает объект `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="5b5db-185">It takes in the data path variables and returns an `IDataView`.</span></span>

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="5b5db-186">Разделение набора данных для обучения и тестирования модели</span><span class="sxs-lookup"><span data-stu-id="5b5db-186">Split the dataset for model training and testing</span></span>

<span data-ttu-id="5b5db-187">При подготовке модели можно использовать часть набора данных для обучения, а другую часть — для проверки точности модели.</span><span class="sxs-lookup"><span data-stu-id="5b5db-187">When preparing a model, you use part of the dataset to train it and part of the dataset to test the model's accuracy.</span></span>

1. <span data-ttu-id="5b5db-188">Чтобы разделить скачанные данные на необходимые наборы данных, добавьте код в следующей строке метода `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="5b5db-188">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData()` method:</span></span>

    [!code-csharp[SplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SplitData "Split the Data")]

    <span data-ttu-id="5b5db-189">Приведенный выше код использует метод [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A), чтобы разделить загруженный набор данных на учебный и проверочный наборы данных, и возвращает их в класс [TrainTestData](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData).</span><span class="sxs-lookup"><span data-stu-id="5b5db-189">The previous code uses the [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) method to split the loaded dataset into train and test datasets and return them in the [TrainTestData](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) class.</span></span> <span data-ttu-id="5b5db-190">Укажите процент тестовых данных с помощью параметра `testFraction`.</span><span class="sxs-lookup"><span data-stu-id="5b5db-190">Specify the test set percentage of data with the `testFraction`parameter.</span></span> <span data-ttu-id="5b5db-191">Значение по умолчанию — 10 %, но в этом случае лучше использовать 20 % для оценки большего объема данных.</span><span class="sxs-lookup"><span data-stu-id="5b5db-191">The default is 10%, in this case you use 20% to evaluate more data.</span></span>

2. <span data-ttu-id="5b5db-192">Верните `splitDataView` в конце метода `LoadData()`.</span><span class="sxs-lookup"><span data-stu-id="5b5db-192">Return the `splitDataView` at the end of the `LoadData()` method:</span></span>

    [!code-csharp[ReturnSplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="5b5db-193">Сборка и обучение модели</span><span class="sxs-lookup"><span data-stu-id="5b5db-193">Build and train the model</span></span>

1. <span data-ttu-id="5b5db-194">В следующей строке кода в методе `Main()` добавьте приведенный ниже вызов метода `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="5b5db-194">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallBuildAndTrainModel)]

    <span data-ttu-id="5b5db-195">Метод `BuildAndTrainModel()` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="5b5db-195">The `BuildAndTrainModel()` method executes the following tasks:</span></span>

    - <span data-ttu-id="5b5db-196">извлечение и преобразование данных;</span><span class="sxs-lookup"><span data-stu-id="5b5db-196">Extracts and transforms the data.</span></span>
    - <span data-ttu-id="5b5db-197">обучение модели;</span><span class="sxs-lookup"><span data-stu-id="5b5db-197">Trains the model.</span></span>
    - <span data-ttu-id="5b5db-198">прогноз тональности на основе тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="5b5db-198">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="5b5db-199">возвращение модели.</span><span class="sxs-lookup"><span data-stu-id="5b5db-199">Returns the model.</span></span>

2. <span data-ttu-id="5b5db-200">Создайте метод `BuildAndTrainModel()` сразу после метода `Main()`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="5b5db-200">Create the `BuildAndTrainModel()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
    {

    }
    ```

### <a name="extract-and-transform-the-data"></a><span data-ttu-id="5b5db-201">Извлечение и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="5b5db-201">Extract and transform the data</span></span>

1. <span data-ttu-id="5b5db-202">Добавьте следующую строку кода для вызова `FeaturizeText`:</span><span class="sxs-lookup"><span data-stu-id="5b5db-202">Call `FeaturizeText` as the next line of code:</span></span>

    [!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#FeaturizeText "Featurize the text")]

    <span data-ttu-id="5b5db-203">Метод `FeaturizeText()` в приведенном выше коде преобразует текстовый столбец (`SentimentText`) в числовой столбец типа ключа `Features`, который используется алгоритмом машинного обучения: он добавляет его как новый столбец набора данных:</span><span class="sxs-lookup"><span data-stu-id="5b5db-203">The `FeaturizeText()` method in the previous code converts the text column (`SentimentText`) into a numeric key type `Features` column used by the machine learning algorithm and adds it as a new dataset column:</span></span>

    |<span data-ttu-id="5b5db-204">SentimentText</span><span class="sxs-lookup"><span data-stu-id="5b5db-204">SentimentText</span></span>                         |<span data-ttu-id="5b5db-205">Тональность</span><span class="sxs-lookup"><span data-stu-id="5b5db-205">Sentiment</span></span> |<span data-ttu-id="5b5db-206">Функции</span><span class="sxs-lookup"><span data-stu-id="5b5db-206">Features</span></span>              |
    |--------------------------------------|----------|----------------------|
    |<span data-ttu-id="5b5db-207">Официантка немного медленная.</span><span class="sxs-lookup"><span data-stu-id="5b5db-207">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="5b5db-208">0</span><span class="sxs-lookup"><span data-stu-id="5b5db-208">0</span></span>     |<span data-ttu-id="5b5db-209">[0.76, 0.65, 0.44, …]</span><span class="sxs-lookup"><span data-stu-id="5b5db-209">[0.76, 0.65, 0.44, …]</span></span> |
    |<span data-ttu-id="5b5db-210">Корочка так себе.</span><span class="sxs-lookup"><span data-stu-id="5b5db-210">Crust is not good.</span></span>                    |    <span data-ttu-id="5b5db-211">0</span><span class="sxs-lookup"><span data-stu-id="5b5db-211">0</span></span>     |<span data-ttu-id="5b5db-212">[0.98, 0.43, 0.54, …]</span><span class="sxs-lookup"><span data-stu-id="5b5db-212">[0.98, 0.43, 0.54, …]</span></span> |
    |<span data-ttu-id="5b5db-213">Ого... Отличное место.</span><span class="sxs-lookup"><span data-stu-id="5b5db-213">Wow... Loved this place.</span></span>              |    <span data-ttu-id="5b5db-214">1</span><span class="sxs-lookup"><span data-stu-id="5b5db-214">1</span></span>     |<span data-ttu-id="5b5db-215">[0.35, 0.73, 0.46, …]</span><span class="sxs-lookup"><span data-stu-id="5b5db-215">[0.35, 0.73, 0.46, …]</span></span> |
    |<span data-ttu-id="5b5db-216">Обслуживание очень быстрое.</span><span class="sxs-lookup"><span data-stu-id="5b5db-216">Service was very prompt.</span></span>              |    <span data-ttu-id="5b5db-217">1</span><span class="sxs-lookup"><span data-stu-id="5b5db-217">1</span></span>     |<span data-ttu-id="5b5db-218">[0.39, 0, 0.75, …]</span><span class="sxs-lookup"><span data-stu-id="5b5db-218">[0.39, 0, 0.75, …]</span></span>    |

### <a name="add-a-learning-algorithm"></a><span data-ttu-id="5b5db-219">Добавление алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="5b5db-219">Add a learning algorithm</span></span>

<span data-ttu-id="5b5db-220">Это приложение использует алгоритм классификации, который классифицирует элементы или строки данных.</span><span class="sxs-lookup"><span data-stu-id="5b5db-220">This app uses a classification algorithm that categorizes items or rows of data.</span></span> <span data-ttu-id="5b5db-221">Приложение классифицирует комментарии веб-сайта как положительные или отрицательные, поэтому это задача двоичной классификации.</span><span class="sxs-lookup"><span data-stu-id="5b5db-221">The app categorizes website comments as either positive or negative, so use the binary classification task.</span></span>

<span data-ttu-id="5b5db-222">Добавьте задачу машинного обучения к определениям преобразований данных, добавив следующее в следующей строке кода в `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="5b5db-222">Append the machine learning task to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[SdcaLogisticRegressionBinaryTrainer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddTrainer "Add a SdcaLogisticRegressionBinaryTrainer")]

<span data-ttu-id="5b5db-223">[SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) — ваш алгоритм обучения классификации.</span><span class="sxs-lookup"><span data-stu-id="5b5db-223">The [SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) is your classification training algorithm.</span></span> <span data-ttu-id="5b5db-224">Он добавляется в `estimator` и принимает `SentimentText` с присвоенными признаками (`Features`) и входные параметры `Label`, чтобы пройти обучение по историческим данным.</span><span class="sxs-lookup"><span data-stu-id="5b5db-224">This is appended to the `estimator` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="5b5db-225">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="5b5db-225">Train the model</span></span>

<span data-ttu-id="5b5db-226">Обучите модель на основе данных `splitTrainSet` и получите обученную модель, добавив в метод `BuildAndTrainModel()` следующие строки кода:</span><span class="sxs-lookup"><span data-stu-id="5b5db-226">Fit the model to the `splitTrainSet` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TrainModel "Train the model")]

<span data-ttu-id="5b5db-227">Метод [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) обучает модель путем преобразования набора данных и применения обучения.</span><span class="sxs-lookup"><span data-stu-id="5b5db-227">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model by transforming the dataset and applying the training.</span></span>

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="5b5db-228">Возврат обученной модели для оценки</span><span class="sxs-lookup"><span data-stu-id="5b5db-228">Return the model trained to use for evaluation</span></span>

 <span data-ttu-id="5b5db-229">Выполните возврат модели в конце метода `BuildAndTrainModel()`.</span><span class="sxs-lookup"><span data-stu-id="5b5db-229">Return the model at the end of the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="5b5db-230">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="5b5db-230">Evaluate the model</span></span>

<span data-ttu-id="5b5db-231">После обучения модели с помощью проверочных данных производится валидация производительности модели.</span><span class="sxs-lookup"><span data-stu-id="5b5db-231">After your model is trained, use your test data validate the model's performance.</span></span>

1. <span data-ttu-id="5b5db-232">Создайте метод `Evaluate()` сразу после `BuildAndTrainModel()`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="5b5db-232">Create the `Evaluate()` method, just after `BuildAndTrainModel()`, with the following code:</span></span>

    ```csharp
    public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
    {

    }
    ```

    <span data-ttu-id="5b5db-233">Метод `Evaluate()` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="5b5db-233">The `Evaluate()` method executes the following tasks:</span></span>

    - <span data-ttu-id="5b5db-234">загрузка тестового набора данных;</span><span class="sxs-lookup"><span data-stu-id="5b5db-234">Loads the test dataset.</span></span>
    - <span data-ttu-id="5b5db-235">создание средства оценки BinaryClassification;</span><span class="sxs-lookup"><span data-stu-id="5b5db-235">Creates the BinaryClassification evaluator.</span></span>
    - <span data-ttu-id="5b5db-236">оценка модели и создание метрик;</span><span class="sxs-lookup"><span data-stu-id="5b5db-236">Evaluates the model and creates metrics.</span></span>
    - <span data-ttu-id="5b5db-237">отображение метрик.</span><span class="sxs-lookup"><span data-stu-id="5b5db-237">Displays the metrics.</span></span>

2. <span data-ttu-id="5b5db-238">Добавьте вызов нового метода из метода `Main()`, сразу после вызова метода `BuildAndTrainModel()`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="5b5db-238">Add a call to the new method from the `Main()` method, right under the `BuildAndTrainModel()` method call, using the following code:</span></span>

    [!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallEvaluate "Call the Evaluate method")]

3. <span data-ttu-id="5b5db-239">Преобразуйте данные `splitTestSet`, добавив в метод `Evaluate()` следующий код:</span><span class="sxs-lookup"><span data-stu-id="5b5db-239">Transform the `splitTestSet` data by adding the following code to `Evaluate()`:</span></span>

    [!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TransformData "Predict using the Transformer")]

    <span data-ttu-id="5b5db-240">Предыдущий код использует метод [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A), чтобы сделать прогнозы для нескольких входных строк тестового набора данных.</span><span class="sxs-lookup"><span data-stu-id="5b5db-240">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple provided input rows of a test dataset.</span></span>

4. <span data-ttu-id="5b5db-241">Оцените модель, добавив в метод `Evaluate()` следующую строку кода:</span><span class="sxs-lookup"><span data-stu-id="5b5db-241">Evaluate the model by adding the following as the next line of code in the `Evaluate()` method:</span></span>

    [!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Evaluate "Compute Metrics")]

<span data-ttu-id="5b5db-242">После получения прогноза (`predictions`) метод [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) оценивает модель, сравнивая спрогнозированные значения с фактическими метками (`Labels`) в тестовом наборе данных, а затем возвращает объект [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) как метрики эффективности модели.</span><span class="sxs-lookup"><span data-stu-id="5b5db-242">Once you have the prediction set (`predictions`), the [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns a [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) object on how the model is performing.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="5b5db-243">Отображение метрик для проверки модели</span><span class="sxs-lookup"><span data-stu-id="5b5db-243">Displaying the metrics for model validation</span></span>

<span data-ttu-id="5b5db-244">Воспользуйтесь приведенным ниже кодом, чтобы отобразить метрики.</span><span class="sxs-lookup"><span data-stu-id="5b5db-244">Use the following code to display the metrics:</span></span>

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayMetrics "Display selected metrics")]

- <span data-ttu-id="5b5db-245">Метрика `Accuracy` возвращает точность модели — это доля правильных прогнозов в тестовом наборе.</span><span class="sxs-lookup"><span data-stu-id="5b5db-245">The `Accuracy` metric gets the accuracy of a model, which is the proportion of correct predictions in the test set.</span></span>

- <span data-ttu-id="5b5db-246">Метрика `AreaUnderRocCurve` показывает уверенность модели в правильности классификации с положительными и отрицательными классами.</span><span class="sxs-lookup"><span data-stu-id="5b5db-246">The `AreaUnderRocCurve` metric indicates how confident the model is correctly classifying the positive and negative classes.</span></span> <span data-ttu-id="5b5db-247">Значение `AreaUnderRocCurve` должно быть максимально близким к единице.</span><span class="sxs-lookup"><span data-stu-id="5b5db-247">You want the `AreaUnderRocCurve` to be as close to one as possible.</span></span>

- <span data-ttu-id="5b5db-248">Метрика `F1Score` содержит F1-оценку модели, который является мерой баланса между [точностью](../resources/glossary.md#precision) и [полнотой](../resources/glossary.md#recall).</span><span class="sxs-lookup"><span data-stu-id="5b5db-248">The `F1Score` metric gets the model's F1 score, which is a measure of balance between [precision](../resources/glossary.md#precision) and [recall](../resources/glossary.md#recall).</span></span>  <span data-ttu-id="5b5db-249">Значение `F1Score` должно быть максимально близким к единице.</span><span class="sxs-lookup"><span data-stu-id="5b5db-249">You want the `F1Score` to be as close to one as possible.</span></span>

### <a name="predict-the-test-data-outcome"></a><span data-ttu-id="5b5db-250">Прогнозировать результаты для тестовых данных</span><span class="sxs-lookup"><span data-stu-id="5b5db-250">Predict the test data outcome</span></span>

1. <span data-ttu-id="5b5db-251">Создайте метод `UseModelWithSingleItem()` сразу после метода `Evaluate()`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="5b5db-251">Create the `UseModelWithSingleItem()` method, just after the `Evaluate()` method, using the following code:</span></span>

    ```csharp
    private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="5b5db-252">Метод `UseModelWithSingleItem()` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="5b5db-252">The `UseModelWithSingleItem()` method executes the following tasks:</span></span>

    - <span data-ttu-id="5b5db-253">создание отдельного комментария тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="5b5db-253">Creates a single comment of test data.</span></span>
    - <span data-ttu-id="5b5db-254">прогноз тональности на основе тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="5b5db-254">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="5b5db-255">объединение тестовых данных и прогнозов для создания отчетов;</span><span class="sxs-lookup"><span data-stu-id="5b5db-255">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="5b5db-256">отображение результатов прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="5b5db-256">Displays the predicted results.</span></span>

2. <span data-ttu-id="5b5db-257">Добавьте вызов нового метода из метода `Main()`, сразу после вызова метода `Evaluate()`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="5b5db-257">Add a call to the new method from the `Main()` method, right under the `Evaluate()` method call, using the following code:</span></span>

    [!code-csharp[CallUseModelWithSingleItem](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

3. <span data-ttu-id="5b5db-258">Давайте добавим следующий код в качестве первой строки в методе `UseModelWithSingleItem()`:</span><span class="sxs-lookup"><span data-stu-id="5b5db-258">Add the following code to create as the first line in the `UseModelWithSingleItem()` Method:</span></span>

    [!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

    <span data-ttu-id="5b5db-259">Класс [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) представляет собой удобный API, позволяющий осуществить прогнозирование на основе единственного экземпляра данных.</span><span class="sxs-lookup"><span data-stu-id="5b5db-259">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="5b5db-260">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) не является потокобезопасным.</span><span class="sxs-lookup"><span data-stu-id="5b5db-260">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="5b5db-261">Допустимо использовать в средах прототипов или средах с одним потоком.</span><span class="sxs-lookup"><span data-stu-id="5b5db-261">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="5b5db-262">Для улучшенной производительности и потокобезопасности в рабочей среде используйте службу `PredictionEnginePool`, которая создает [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) объектов [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) для использования во всем приложении.</span><span class="sxs-lookup"><span data-stu-id="5b5db-262">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="5b5db-263">Ознакомьтесь с этим руководством о том, как [использовать `PredictionEnginePool` в ASP.NET Core Web API](https://docs.microsoft.com/en-us/dotnet/machine-learning/how-to-guides/serve-model-web-api-ml-net#register-predictionenginepool-for-use-in-the-application)</span><span class="sxs-lookup"><span data-stu-id="5b5db-263">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](https://docs.microsoft.com/en-us/dotnet/machine-learning/how-to-guides/serve-model-web-api-ml-net#register-predictionenginepool-for-use-in-the-application)</span></span>

    > [!NOTE]
    > <span data-ttu-id="5b5db-264">Расширение службы `PredictionEnginePool` сейчас доступно в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="5b5db-264">`PredictionEnginePool` service extension is currently in preview.</span></span>
    
4. <span data-ttu-id="5b5db-265">Добавьте комментарий для проверки прогнозирования обученной модели в методе `UseModelWithSingleItem()`, создав экземпляр `SentimentData`:</span><span class="sxs-lookup"><span data-stu-id="5b5db-265">Add a comment to test the trained model's prediction in the `UseModelWithSingleItem()` method by creating an instance of `SentimentData`:</span></span>

    [!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

5. <span data-ttu-id="5b5db-266">Передайте данные тестового комментария в [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602), добавив следующие строки кода в метод `UseModelWithSingleItem()`:</span><span class="sxs-lookup"><span data-stu-id="5b5db-266">Pass the test comment data to the [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) by adding the following as the next lines of code in the `UseModelWithSingleItem()` method:</span></span>

    [!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Predict "Create a prediction of sentiment")]

    <span data-ttu-id="5b5db-267">Функция [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) создает прогноз по одной строке данных.</span><span class="sxs-lookup"><span data-stu-id="5b5db-267">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data.</span></span>

6. <span data-ttu-id="5b5db-268">Выведите `SentimentText` и соответствующий прогноз тональности, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="5b5db-268">Display `SentimentText` and corresponding sentiment prediction using the following code:</span></span>

    [!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#OutputPrediction "Display prediction output")]

## <a name="use-the-model-for-prediction"></a><span data-ttu-id="5b5db-269">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="5b5db-269">Use the model for prediction</span></span>

### <a name="deploy-and-predict-batch-items"></a><span data-ttu-id="5b5db-270">Развертывание и прогнозирование элементов пакета</span><span class="sxs-lookup"><span data-stu-id="5b5db-270">Deploy and predict batch items</span></span>

1. <span data-ttu-id="5b5db-271">Создайте метод `UseModelWithBatchItems()` сразу после метода `UseModelWithSingleItem()`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="5b5db-271">Create the `UseModelWithBatchItems()` method, just after the `UseModelWithSingleItem()` method, using the following code:</span></span>

    ```csharp
    public static void UseModelWithBatchItems(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="5b5db-272">Метод `UseModelWithBatchItems()` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="5b5db-272">The `UseModelWithBatchItems()` method executes the following tasks:</span></span>

    - <span data-ttu-id="5b5db-273">создание пакетных тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="5b5db-273">Creates batch test data.</span></span>
    - <span data-ttu-id="5b5db-274">прогноз тональности на основе тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="5b5db-274">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="5b5db-275">объединение тестовых данных и прогнозов для создания отчетов;</span><span class="sxs-lookup"><span data-stu-id="5b5db-275">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="5b5db-276">отображение результатов прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="5b5db-276">Displays the predicted results.</span></span>

2. <span data-ttu-id="5b5db-277">Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `UseModelWithSingleItem()`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="5b5db-277">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem()` method call, using the following code:</span></span>

    [!code-csharp[CallPredictModelBatchItems](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithBatchItems "Call the CallUseModelWithBatchItems method")]

3. <span data-ttu-id="5b5db-278">Добавьте новые комментарии, чтобы проверить прогнозы обученной модели, в метод `UseModelWithBatchItems()`:</span><span class="sxs-lookup"><span data-stu-id="5b5db-278">Add some comments to test the trained model's predictions in the `UseModelWithBatchItems()` method:</span></span>

    [!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssues "Create test data for predictions")]

### <a name="predict-comment-sentiment"></a><span data-ttu-id="5b5db-279">Предсказание тональности на основе комментариев</span><span class="sxs-lookup"><span data-stu-id="5b5db-279">Predict comment sentiment</span></span>

<span data-ttu-id="5b5db-280">Использование модели для прогнозирования тональности комментариев с помощью метода [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A):</span><span class="sxs-lookup"><span data-stu-id="5b5db-280">Use the model to predict the comment data sentiment using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="combine-and-display-the-predictions"></a><span data-ttu-id="5b5db-281">Объедините и отобразите прогнозы</span><span class="sxs-lookup"><span data-stu-id="5b5db-281">Combine and display the predictions</span></span>

<span data-ttu-id="5b5db-282">Создайте заголовок для результатов с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="5b5db-282">Create a header for the predictions using the following code:</span></span>

[!code-csharp[OutputHeaders](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="5b5db-283">Так как `SentimentPrediction` наследуется от `SentimentData`, `Transform()` метод заполняет `SentimentText` прогнозируемыми полями.</span><span class="sxs-lookup"><span data-stu-id="5b5db-283">Because `SentimentPrediction` is inherited from `SentimentData`, the `Transform()` method populated `SentimentText` with the predicted fields.</span></span> <span data-ttu-id="5b5db-284">В ходе обработки ML.NET каждый компонент добавляет столбцы, что упрощает отображение результатов:</span><span class="sxs-lookup"><span data-stu-id="5b5db-284">As the ML.NET process processes, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayResults "Display the predictions")]

## <a name="results"></a><span data-ttu-id="5b5db-285">Результаты</span><span class="sxs-lookup"><span data-stu-id="5b5db-285">Results</span></span>

<span data-ttu-id="5b5db-286">Результаты выполнения должны выглядеть примерно так, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="5b5db-286">Your results should be similar to the following.</span></span> <span data-ttu-id="5b5db-287">Во время обработки отображаются сообщения.</span><span class="sxs-lookup"><span data-stu-id="5b5db-287">During processing, messages are displayed.</span></span> <span data-ttu-id="5b5db-288">Вы можете видеть предупреждения или обработанные сообщения.</span><span class="sxs-lookup"><span data-stu-id="5b5db-288">You may see warnings, or processing messages.</span></span> <span data-ttu-id="5b5db-289">Для удобства они удалены из следующих результатов.</span><span class="sxs-lookup"><span data-stu-id="5b5db-289">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 83.96%
Auc: 90.51%
F1Score: 84.04%

=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.1027377
=============== End of Predictions ===============

=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1369192
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9960636
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

<span data-ttu-id="5b5db-290">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="5b5db-290">Congratulations!</span></span> <span data-ttu-id="5b5db-291">Вы успешно создали модель машинного обучения для классификации и прогнозирования тональности сообщений.</span><span class="sxs-lookup"><span data-stu-id="5b5db-291">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span>

<span data-ttu-id="5b5db-292">Построение успешных моделей — итеративный процесс.</span><span class="sxs-lookup"><span data-stu-id="5b5db-292">Building successful models is an iterative process.</span></span> <span data-ttu-id="5b5db-293">Изначально эта модель имеет низкое качество, так как в руководстве используются небольшие наборы данных для быстрого обучения.</span><span class="sxs-lookup"><span data-stu-id="5b5db-293">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="5b5db-294">Если вам требуется модель более высокого качества, можно попытаться улучшить ее, использовав более крупные наборы данных для обучения или выбрав другие алгоритмы обучения с разными [гиперпараметрами](../resources/glossary.md##hyperparameter) для каждого алгоритма.</span><span class="sxs-lookup"><span data-stu-id="5b5db-294">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different [hyper-parameters](../resources/glossary.md##hyperparameter) for each algorithm.</span></span>

<span data-ttu-id="5b5db-295">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="5b5db-295">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5b5db-296">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="5b5db-296">Next steps</span></span>

<span data-ttu-id="5b5db-297">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="5b5db-297">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="5b5db-298">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="5b5db-298">Create a console application</span></span>
> - <span data-ttu-id="5b5db-299">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="5b5db-299">Prepare data</span></span>
> - <span data-ttu-id="5b5db-300">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="5b5db-300">Load the data</span></span>
> - <span data-ttu-id="5b5db-301">Сборка и обучение модели</span><span class="sxs-lookup"><span data-stu-id="5b5db-301">Build and train the model</span></span>
> - <span data-ttu-id="5b5db-302">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="5b5db-302">Evaluate the model</span></span>
> - <span data-ttu-id="5b5db-303">Использование модели для прогноза</span><span class="sxs-lookup"><span data-stu-id="5b5db-303">Use the model to make a prediction</span></span>
> - <span data-ttu-id="5b5db-304">Просмотр результатов</span><span class="sxs-lookup"><span data-stu-id="5b5db-304">See the results</span></span>

<span data-ttu-id="5b5db-305">Переходите к следующему руководству:</span><span class="sxs-lookup"><span data-stu-id="5b5db-305">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="5b5db-306">Классификация задач</span><span class="sxs-lookup"><span data-stu-id="5b5db-306">Issue Classification</span></span>](github-issue-classification.md)
