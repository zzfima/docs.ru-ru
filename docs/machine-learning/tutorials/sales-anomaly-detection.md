---
title: Учебник. Обнаружение аномалий в данных о продажах товаров
description: Узнайте, как создать приложение для обнаружения аномалий в данных о продажах товаров. В этом руководстве в Visual Studio 2019 с помощью C# создается консольное приложение .NET Core.
ms.date: 06/11/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: 3e3e368ed3bcb35e7e2c8bdf08abe71afd4ae87c
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306231"
---
# <a name="tutorial-detect-anomalies-in-product-sales-with-mlnet"></a><span data-ttu-id="1ae08-104">Учебник. Обнаружение аномалий в данных о продажах товаров с помощью ML.NET</span><span class="sxs-lookup"><span data-stu-id="1ae08-104">Tutorial: Detect anomalies in product sales with ML.NET</span></span>

<span data-ttu-id="1ae08-105">Узнайте, как создать приложение для обнаружения аномалий в данных о продажах товаров.</span><span class="sxs-lookup"><span data-stu-id="1ae08-105">Learn how to build an anomaly detection application for product sales data.</span></span> <span data-ttu-id="1ae08-106">В этом руководстве в Visual Studio с помощью C# создается консольное приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1ae08-106">This tutorial creates a .NET Core console application using C# in Visual Studio.</span></span>

<span data-ttu-id="1ae08-107">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="1ae08-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="1ae08-108">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="1ae08-108">Load the data</span></span>
> * <span data-ttu-id="1ae08-109">Обучение модели для обнаружения пиковых аномалий</span><span class="sxs-lookup"><span data-stu-id="1ae08-109">Train the model for spike anomaly detection</span></span>
> * <span data-ttu-id="1ae08-110">Обнаружение пиковых аномалий с помощью обученной модели</span><span class="sxs-lookup"><span data-stu-id="1ae08-110">Detect spike anomalies with the trained model</span></span>
> * <span data-ttu-id="1ae08-111">Обучение модели для обнаружения аномалий в точке изменений</span><span class="sxs-lookup"><span data-stu-id="1ae08-111">Train the model for change point anomaly detection</span></span>
> * <span data-ttu-id="1ae08-112">Обнаружение аномалий в точке изменений с помощью обученной модели</span><span class="sxs-lookup"><span data-stu-id="1ae08-112">Detect change point anomalies with the trained model</span></span>

<span data-ttu-id="1ae08-113">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="1ae08-113">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1ae08-114">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="1ae08-114">Prerequisites</span></span>

* <span data-ttu-id="1ae08-115">[Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="1ae08-115">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span>

* [<span data-ttu-id="1ae08-116">Набор данных product-sales.csv</span><span class="sxs-lookup"><span data-stu-id="1ae08-116">The product-sales.csv dataset</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)

>[!NOTE]
> <span data-ttu-id="1ae08-117">Формат данных в `product-sales.csv` основан на наборе данных Shampoo Sales Over a Three Year Period, изначально опубликованном DataMarket и предоставленном Time Series Data Library (TSDL), за авторством Роба Нундмана (Rob Hyndman).</span><span class="sxs-lookup"><span data-stu-id="1ae08-117">The data format in `product-sales.csv` is based on the dataset “Shampoo Sales Over a Three Year Period” originally sourced from DataMarket and provided by Time Series Data Library (TSDL), created by Rob Hyndman.</span></span> <span data-ttu-id="1ae08-118">Набор данных Shampoo Sales Over a Three Year Period предоставляется по стандартной открытой лицензии DataMarket.</span><span class="sxs-lookup"><span data-stu-id="1ae08-118">“Shampoo Sales Over a Three Year Period” Dataset Licensed Under the DataMarket Default Open License.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="1ae08-119">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="1ae08-119">Create a console application</span></span>

1. <span data-ttu-id="1ae08-120">Создайте **консольное приложение .NET Core** с именем ProductSalesAnomalyDetection.</span><span class="sxs-lookup"><span data-stu-id="1ae08-120">Create a **.NET Core Console Application** called "ProductSalesAnomalyDetection".</span></span>

2. <span data-ttu-id="1ae08-121">Создайте каталог с именем *Data* в проекте, чтобы сохранять файлы набора данных.</span><span class="sxs-lookup"><span data-stu-id="1ae08-121">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="1ae08-122">Установите **пакет NuGet для Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="1ae08-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="1ae08-123">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="1ae08-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="1ae08-124">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите в списке пакет **v1.0.0** и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="1ae08-124">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select the **v1.0.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="1ae08-125">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="1ae08-125">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="1ae08-126">Повторите эти действия для пакета **Microsoft.ML.TimeSeries v0.12.0**.</span><span class="sxs-lookup"><span data-stu-id="1ae08-126">Repeat these steps for **Microsoft.ML.TimeSeries v0.12.0**.</span></span>

4. <span data-ttu-id="1ae08-127">Добавьте следующие операторы `using` в начало файла *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="1ae08-127">Add the following `using` statements at the top of your *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="1ae08-128">Скачивание данных</span><span class="sxs-lookup"><span data-stu-id="1ae08-128">Download your data</span></span>

1. <span data-ttu-id="1ae08-129">Скачайте набор данных и сохраните его в ранее созданную папку *Data*:</span><span class="sxs-lookup"><span data-stu-id="1ae08-129">Download the dataset and save it to the *Data* folder you previously created:</span></span>

   * <span data-ttu-id="1ae08-130">Щелкните файл [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) правой кнопкой мыши и выберите команду "Сохранить ссылку (объект) как...".</span><span class="sxs-lookup"><span data-stu-id="1ae08-130">Right click on [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="1ae08-131">Файл \*.csv нужно сохранить в папке *Data*. Если вы сохранили файл \*.csv в другом месте, переместите его в папку *Data*.</span><span class="sxs-lookup"><span data-stu-id="1ae08-131">Make sure you either save the \*.csv file to the *Data* folder, or after you save it elsewhere, move the \*.csv file to the *Data* folder.</span></span>

2. <span data-ttu-id="1ae08-132">В обозревателе решений щелкните правой кнопкой мыши файл \*.csv и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1ae08-132">In Solution Explorer, right-click the \*.csv file and select **Properties**.</span></span> <span data-ttu-id="1ae08-133">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="1ae08-133">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="1ae08-134">В следующей таблице представлены данные из вашего файла \*.csv:</span><span class="sxs-lookup"><span data-stu-id="1ae08-134">The following table is a data preview from your \*.csv file:</span></span>

|<span data-ttu-id="1ae08-135">Месяц.</span><span class="sxs-lookup"><span data-stu-id="1ae08-135">Month</span></span>  |<span data-ttu-id="1ae08-136">ProductSales</span><span class="sxs-lookup"><span data-stu-id="1ae08-136">ProductSales</span></span> |
|-------|-------------|
|<span data-ttu-id="1ae08-137">1-Jan</span><span class="sxs-lookup"><span data-stu-id="1ae08-137">1-Jan</span></span>  |    <span data-ttu-id="1ae08-138">271</span><span class="sxs-lookup"><span data-stu-id="1ae08-138">271</span></span>      |
|<span data-ttu-id="1ae08-139">2-Jan</span><span class="sxs-lookup"><span data-stu-id="1ae08-139">2-Jan</span></span>  |    <span data-ttu-id="1ae08-140">150,9</span><span class="sxs-lookup"><span data-stu-id="1ae08-140">150.9</span></span>    |
|<span data-ttu-id="1ae08-141">.....</span><span class="sxs-lookup"><span data-stu-id="1ae08-141">.....</span></span>  |    <span data-ttu-id="1ae08-142">.....</span><span class="sxs-lookup"><span data-stu-id="1ae08-142">.....</span></span>    |
|<span data-ttu-id="1ae08-143">1-Feb</span><span class="sxs-lookup"><span data-stu-id="1ae08-143">1-Feb</span></span>  |    <span data-ttu-id="1ae08-144">199,3</span><span class="sxs-lookup"><span data-stu-id="1ae08-144">199.3</span></span>    |
|<span data-ttu-id="1ae08-145">.....</span><span class="sxs-lookup"><span data-stu-id="1ae08-145">.....</span></span>  |    <span data-ttu-id="1ae08-146">.....</span><span class="sxs-lookup"><span data-stu-id="1ae08-146">.....</span></span>    |

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="1ae08-147">Создание классов и определение путей</span><span class="sxs-lookup"><span data-stu-id="1ae08-147">Create classes and define paths</span></span>

<span data-ttu-id="1ae08-148">Далее определите структуру данных для входного класса.</span><span class="sxs-lookup"><span data-stu-id="1ae08-148">Next, define your input class data structure.</span></span>

<span data-ttu-id="1ae08-149">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="1ae08-149">Add a new class to your project:</span></span>

1. <span data-ttu-id="1ae08-150">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите команду **Добавить > Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="1ae08-150">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="1ae08-151">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *ProductSalesData.cs*.</span><span class="sxs-lookup"><span data-stu-id="1ae08-151">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *ProductSalesData.cs*.</span></span> <span data-ttu-id="1ae08-152">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1ae08-152">Then, select the **Add** button.</span></span>

<span data-ttu-id="1ae08-153">Файл *ProductSalesData.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="1ae08-153">The *ProductSalesData.cs* file opens in the code editor.</span></span> <span data-ttu-id="1ae08-154">Добавьте следующую инструкцию `using` в начало файла *ProductSalesData.cs*:</span><span class="sxs-lookup"><span data-stu-id="1ae08-154">Add the following `using` statement to the top of *ProductSalesData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="1ae08-155">Удалите из файла *ProductSalesData.cs* существующее определение класса и добавьте следующий код с двумя классами `ProductSalesData` и `ProductSalesPrediction`:</span><span class="sxs-lookup"><span data-stu-id="1ae08-155">Remove the existing class definition and add the following code, which has two classes `ProductSalesData` and `ProductSalesPrediction`, to the *ProductSalesData.cs* file:</span></span>

[!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/ProductSalesData.cs#DeclareTypes "Declare data record types")]

<span data-ttu-id="1ae08-156">`ProductSalesData` — это класс входных данных.</span><span class="sxs-lookup"><span data-stu-id="1ae08-156">`ProductSalesData` specifies an input data class.</span></span> <span data-ttu-id="1ae08-157">Атрибут [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) определяет столбцы в наборе данных, которые следует загрузить (по индексам).</span><span class="sxs-lookup"><span data-stu-id="1ae08-157">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span> 

<span data-ttu-id="1ae08-158">Добавьте следующие новые операторы `using` в начало файла *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="1ae08-158">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="1ae08-159">Создайте два глобальных поля для хранения пути к недавно скачанному файлу набора данных и файлу сохраненной модели:</span><span class="sxs-lookup"><span data-stu-id="1ae08-159">You need to create two global fields to hold the recently downloaded dataset file path and the saved model file path:</span></span>

* <span data-ttu-id="1ae08-160">`_dataPath` содержит путь к набору данных, используемому для обучения модели;</span><span class="sxs-lookup"><span data-stu-id="1ae08-160">`_dataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="1ae08-161">`_docsize` содержит количество записей в файле набора данных.</span><span class="sxs-lookup"><span data-stu-id="1ae08-161">`_docsize` has the number of records in dataset file.</span></span> <span data-ttu-id="1ae08-162">Вы будете использовать эти сведения для вычисления `pvalueHistoryLength`.</span><span class="sxs-lookup"><span data-stu-id="1ae08-162">You'll use this to calculate `pvalueHistoryLength`.</span></span>

<span data-ttu-id="1ae08-163">Добавьте следующий код в строку прямо перед методом `Main`, чтобы указать эти пути:</span><span class="sxs-lookup"><span data-stu-id="1ae08-163">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DeclareGlobalVariables "Declare global variables")]

<span data-ttu-id="1ae08-164">[Класс MLContext](xref:Microsoft.ML.MLContext) является отправной точкой для любых операций ML.NET. В результате инициализации класса `mlContext` создается среда ML.NET, которая может использоваться всеми объектами в рамках процесса создания модели.</span><span class="sxs-lookup"><span data-stu-id="1ae08-164">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="1ae08-165">По существу он аналогичен классу `DBContext` в Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="1ae08-165">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="1ae08-166">Инициализация переменных в методе Main</span><span class="sxs-lookup"><span data-stu-id="1ae08-166">Initialize variables in Main</span></span>

<span data-ttu-id="1ae08-167">Замените строку `Console.WriteLine("Hello World!")` в методе `Main` следующим кодом, чтобы объявить и инициализировать переменную `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="1ae08-167">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the `mlContext` variable:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateMLContext "Create the ML Context")]

### <a name="load-the-data"></a><span data-ttu-id="1ae08-168">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="1ae08-168">Load the data</span></span>

<span data-ttu-id="1ae08-169">Данные в ML.NET представлены [классом IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="1ae08-169">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="1ae08-170">`IDataView` позволяет гибко и полно описывать табличные данные (числовые и текстовые).</span><span class="sxs-lookup"><span data-stu-id="1ae08-170">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="1ae08-171">Данные можно загружать в объект `IDataView` из текстового файла или в режиме реального времени (например, из базы данных SQL или файлов журнала).</span><span class="sxs-lookup"><span data-stu-id="1ae08-171">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span> <span data-ttu-id="1ae08-172">Добавьте в следующую строку метода `Main()` приведенный ниже код.</span><span class="sxs-lookup"><span data-stu-id="1ae08-172">Add the following code as the next line of the `Main()` method:</span></span>

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#LoadData "loading dataset")]

<span data-ttu-id="1ae08-173">Метод [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) определяет схему данных и считывает файл.</span><span class="sxs-lookup"><span data-stu-id="1ae08-173">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="1ae08-174">Он принимает переменные, содержащие пути к данным, и возвращает объект `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="1ae08-174">It takes in the data path variables and returns an `IDataView`.</span></span>

## <a name="ml-task---time-series-anomaly-detection"></a><span data-ttu-id="1ae08-175">Задача машинного обучения — обнаружение аномалий временных рядов</span><span class="sxs-lookup"><span data-stu-id="1ae08-175">ML task - time series anomaly detection</span></span> 

<span data-ttu-id="1ae08-176">Функция обнаружения аномалий регистрирует неожиданные или необычные события или особенности поведения.</span><span class="sxs-lookup"><span data-stu-id="1ae08-176">Anomaly detection flags unexpected or unusual events or behaviors.</span></span> <span data-ttu-id="1ae08-177">Кроме того, она подсказывает, где нужно искать проблему, и помогает ответить на вопрос "Является ли это странным?".</span><span class="sxs-lookup"><span data-stu-id="1ae08-177">It gives clues where to look for problems and helps you answer the question "Is this weird?".</span></span>

![Является ли это странным](./media/sales-anomaly-detection/anomalydetection.png)

<span data-ttu-id="1ae08-179">Обнаружение аномалий — это процесс обнаружения выбросов временных рядов данных, точек заданных входных временных рядов, где поведение отличается от ожидаемого или является "странным".</span><span class="sxs-lookup"><span data-stu-id="1ae08-179">Anomaly detection is the process of detecting time-series data outliers; points on a given input time-series where the behavior isn't what was expected, or "weird".</span></span>

<span data-ttu-id="1ae08-180">Это может оказаться полезным во многих ситуациях.</span><span class="sxs-lookup"><span data-stu-id="1ae08-180">This can be useful in lots of ways.</span></span> <span data-ttu-id="1ae08-181">Например:</span><span class="sxs-lookup"><span data-stu-id="1ae08-181">For instance:</span></span>

<span data-ttu-id="1ae08-182">При наличии автомобиля вы, возможно, захотите узнать, правильны ли показания датчика масла или возникла утечка.</span><span class="sxs-lookup"><span data-stu-id="1ae08-182">If you have a car, you might want to know: Is this oil gauge reading normal, or do I have a leak?</span></span>
<span data-ttu-id="1ae08-183">Если вы отслеживаете энергопотребление, то захотите узнать, имеет ли место простой.</span><span class="sxs-lookup"><span data-stu-id="1ae08-183">If you're monitoring power consumption, you’d want to know: Is there an outage?</span></span>

<span data-ttu-id="1ae08-184">Существуют два вида аномалий временных рядов, которые можно обнаружить.</span><span class="sxs-lookup"><span data-stu-id="1ae08-184">There are two types of time series anomalies that can be detected:</span></span> 

* <span data-ttu-id="1ae08-185">**Пиковые значения** указывают временные всплески аномального поведения в системе.</span><span class="sxs-lookup"><span data-stu-id="1ae08-185">**Spikes** indicate temporary bursts of anomalous behavior in the system.</span></span> 

* <span data-ttu-id="1ae08-186">**Точки изменений** указывают начало устойчивых изменений с течением времени в системе.</span><span class="sxs-lookup"><span data-stu-id="1ae08-186">**Change points** indicate the beginning of persistent changes over time in the system.</span></span> 

<span data-ttu-id="1ae08-187">В ML.NET алгоритмы обнаружения пиковых значений IID или обнаружения точек изменений IID подходят для [независимых и одинаково распределенных наборов данных](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).</span><span class="sxs-lookup"><span data-stu-id="1ae08-187">In ML.NET, The IID Spike Detection or IID Change point Detection algorithms are suited for [independent and identically distributed datasets](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).</span></span> 

<span data-ttu-id="1ae08-188">Вы проанализируете одни и те же данные о продажах продукта для обнаружения пиковых значений и точек изменений.</span><span class="sxs-lookup"><span data-stu-id="1ae08-188">You'll analyze the same product sales data to detect spikes and change points.</span></span> <span data-ttu-id="1ae08-189">Процесс создания и обучения модели одинаков для обоих видов обнаружения; основное различие заключается в используемом алгоритме обнаружения.</span><span class="sxs-lookup"><span data-stu-id="1ae08-189">The building and training model process is the same for spike detection and change point detection; the main difference is the specific detection algorithm used.</span></span>

## <a name="spike-detection"></a><span data-ttu-id="1ae08-190">Обнаружение пиковых значений</span><span class="sxs-lookup"><span data-stu-id="1ae08-190">Spike detection</span></span> 

<span data-ttu-id="1ae08-191">Целью обнаружения пиковых значений является выявление внезапных, но при этом временных всплесков, которые значительно отличаются от большинства значений данных временных рядов.</span><span class="sxs-lookup"><span data-stu-id="1ae08-191">The goal of spike detection is to identify sudden yet temporary bursts that significantly differ from the majority of the time series data values.</span></span> <span data-ttu-id="1ae08-192">Важно своевременно обнаружить эти подозрительные редкие элементы, события или наблюдения, чтобы свести их влияние к минимуму.</span><span class="sxs-lookup"><span data-stu-id="1ae08-192">It's important to detect these suspicious rare items, events or observations in a timely manner to be minimized.</span></span> <span data-ttu-id="1ae08-193">Для обнаружения разнообразных аномалий, таких как простои, кибератаки и вирусное веб-содержимое, можно использовать описанный ниже подход.</span><span class="sxs-lookup"><span data-stu-id="1ae08-193">The following approach can be used to detect a variety of anomalies such as: outages, cyber-attacks, or viral web content.</span></span> <span data-ttu-id="1ae08-194">На следующем рисунке представлен пример пиковых значений в наборе данных временных рядов.</span><span class="sxs-lookup"><span data-stu-id="1ae08-194">The following image is an example of spikes in a time series dataset:</span></span>

![SpikeDetection](./media/sales-anomaly-detection/SpikeDetection.png)

### <a name="create-the-detectspike-method"></a><span data-ttu-id="1ae08-196">Создание метода DetectSpike()</span><span class="sxs-lookup"><span data-stu-id="1ae08-196">Create the DetectSpike() method</span></span>

<span data-ttu-id="1ae08-197">В следующей строке кода в методе `Main()` добавьте приведенный ниже вызов метода `DetectSpike()`:</span><span class="sxs-lookup"><span data-stu-id="1ae08-197">Add the following call to the `DetectSpike()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallDetectSpike](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectSpike)]

<span data-ttu-id="1ae08-198">Метод `DetectSpike()` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="1ae08-198">The `DetectSpike()` method executes the following tasks:</span></span>

* <span data-ttu-id="1ae08-199">обучение модели;</span><span class="sxs-lookup"><span data-stu-id="1ae08-199">Trains the model.</span></span>
* <span data-ttu-id="1ae08-200">Обнаруживает пиковые значения на основе исторических данных о продажах.</span><span class="sxs-lookup"><span data-stu-id="1ae08-200">Detects spikes based on historical sales data.</span></span>
* <span data-ttu-id="1ae08-201">Отображает результаты.</span><span class="sxs-lookup"><span data-stu-id="1ae08-201">Displays the results.</span></span>

<span data-ttu-id="1ae08-202">Создайте метод `DetectSpike()` сразу после метода `Main()`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="1ae08-202">Create the `DetectSpike()` method, just after the `Main()` method, using the following code:</span></span>

```csharp
static void DetectSpike(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

<span data-ttu-id="1ae08-203">Используйте [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator), чтобы обучить модель для обнаружения пиковых значений.</span><span class="sxs-lookup"><span data-stu-id="1ae08-203">Use the [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator) to train the model for spike detection.</span></span> <span data-ttu-id="1ae08-204">Добавьте его в метод `DetectChangepoint()` со следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="1ae08-204">Add it to the `DetectChangepoint()` method with the following code:</span></span>

[!code-csharp[AddSpikeTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddSpikeTrainer)]

<span data-ttu-id="1ae08-205">Обучите модель на основе данных `productSales`, добавив следующую строку кода в метод `DetectSpike()`:</span><span class="sxs-lookup"><span data-stu-id="1ae08-205">Fit the model to the `productSales` data by adding the following as the next line of code in the `DetectSpike()` method:</span></span>

[!code-csharp[TrainModel1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel1)]

<span data-ttu-id="1ae08-206">Метод [Fit()](xref:Microsoft.ML.Data.TrivialEstimator%601.Fit%2A) обучает модель путем преобразования набора данных и применения обучения.</span><span class="sxs-lookup"><span data-stu-id="1ae08-206">The [Fit()](xref:Microsoft.ML.Data.TrivialEstimator%601.Fit%2A) method trains your model by transforming the dataset and applying the training.</span></span>

<span data-ttu-id="1ae08-207">Добавьте указанный ниже код для преобразования данных `productSales` в следующую строку метода `DetectSpike()`:</span><span class="sxs-lookup"><span data-stu-id="1ae08-207">Add the following line of code to transform the `productSales` data as the next line in the `DetectSpike()` method:</span></span>

[!code-csharp[TransformData1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData1)]

<span data-ttu-id="1ae08-208">Предыдущий код использует метод [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A), чтобы сделать прогнозы для нескольких входных строк тестового набора данных.</span><span class="sxs-lookup"><span data-stu-id="1ae08-208">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple provided input rows of a test dataset.</span></span>

<span data-ttu-id="1ae08-209">Преобразуйте `transformedData` в строго типизированный `IEnumerable` для более удобного отображения с помощью метода [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A), используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="1ae08-209">Convert your `transformedData` into a strongly-typed `IEnumerable` for easier display using the [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) method with the following code:</span></span>

[!code-csharp[CreateEnumerable1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable1)]

<span data-ttu-id="1ae08-210">Создайте отображаемую строку заголовка с помощью следующего кода <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="1ae08-210">Create a display header line using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayHeader1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader1)]

<span data-ttu-id="1ae08-211">В результатах обнаружения пиковых значений будут отображены следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="1ae08-211">You'll display the following information in your spike detection results:</span></span>

* <span data-ttu-id="1ae08-212">`Alert` указывает на оповещение о пиковом значении для заданной точки данных.</span><span class="sxs-lookup"><span data-stu-id="1ae08-212">`Alert` indicates a spike alert for a given data point.</span></span>

* <span data-ttu-id="1ae08-213">`Score` является значением `ProductSales` для заданной точки данных в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="1ae08-213">`Score` is the `ProductSales` value for a given data point in the dataset.</span></span>

* <span data-ttu-id="1ae08-214">`P-Value` — "P" означает вероятность.</span><span class="sxs-lookup"><span data-stu-id="1ae08-214">`P-Value` The "P" stands for probability.</span></span> <span data-ttu-id="1ae08-215">Указывает, с какой вероятностью эта точка данных является аномалией.</span><span class="sxs-lookup"><span data-stu-id="1ae08-215">This indicates how likely this data point is an anomaly.</span></span> 

<span data-ttu-id="1ae08-216">Используйте следующий код, чтобы выполнить итерацию по `predictions` `IEnumerable` и отобразить результаты:</span><span class="sxs-lookup"><span data-stu-id="1ae08-216">Use the following code to iterate through the `predictions` `IEnumerable` and display the results:</span></span>

[!code-csharp[DisplayResults1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults1)]

## <a name="spike-detection-results"></a><span data-ttu-id="1ae08-217">Результаты обнаружения пиковых значений</span><span class="sxs-lookup"><span data-stu-id="1ae08-217">Spike detection results</span></span>

<span data-ttu-id="1ae08-218">Результаты выполнения должны выглядеть примерно так, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="1ae08-218">Your results should be similar to the following.</span></span> <span data-ttu-id="1ae08-219">Во время обработки отображаются сообщения.</span><span class="sxs-lookup"><span data-stu-id="1ae08-219">During processing, messages are displayed.</span></span> <span data-ttu-id="1ae08-220">Вы можете видеть предупреждения или обработанные сообщения.</span><span class="sxs-lookup"><span data-stu-id="1ae08-220">You may see warnings, or processing messages.</span></span> <span data-ttu-id="1ae08-221">Для удобства они удалены из следующих результатов.</span><span class="sxs-lookup"><span data-stu-id="1ae08-221">These have been removed from the following results for clarity.</span></span>

```console
Detect temporary changes in pattern
=============== Training the model ===============
=============== End of training process ===============
Alert   Score   P-Value
0       271.00  0.50
0       150.90  0.00
0       188.10  0.41
0       124.30  0.13
0       185.30  0.47
0       173.50  0.47
0       236.80  0.19
0       229.50  0.27
0       197.80  0.48
0       127.90  0.13
1       341.50  0.00 <-- Spike detected
0       190.90  0.48
0       199.30  0.48
0       154.50  0.24
0       215.10  0.42
0       278.30  0.19
0       196.40  0.43
0       292.00  0.17
0       231.00  0.45
0       308.60  0.18
0       294.90  0.19
1       426.60  0.00 <-- Spike detected
0       269.50  0.47
0       347.30  0.21
0       344.70  0.27
0       445.40  0.06
0       320.90  0.49
0       444.30  0.12
0       406.30  0.29
0       442.40  0.21
1       580.50  0.00 <-- Spike detected
0       412.60  0.45
1       687.00  0.01 <-- Spike detected
0       480.30  0.40
0       586.30  0.20
0       651.90  0.14
```

## <a name="change-point-detection"></a><span data-ttu-id="1ae08-222">Обнаружение точек изменений</span><span class="sxs-lookup"><span data-stu-id="1ae08-222">Change point detection</span></span>

<span data-ttu-id="1ae08-223">`Change points` — это постоянные изменения в распределении значений по потоку событий временных рядов, такие как изменения уровня и тенденции.</span><span class="sxs-lookup"><span data-stu-id="1ae08-223">`Change points` are persistent changes in a time series event stream distribution of values, like level changes and trends.</span></span> <span data-ttu-id="1ae08-224">Эти постоянные изменения длятся гораздо дольше, чем `spikes`, и могут указывать на катастрофические события.</span><span class="sxs-lookup"><span data-stu-id="1ae08-224">These persistent changes last much longer than `spikes` and could indicate catastrophic event(s).</span></span> <span data-ttu-id="1ae08-225">`Change points` обычно не видны невооруженным глазом, но могут быть обнаружены в данных с помощью таких подходов, которые описаны в следующем методе.</span><span class="sxs-lookup"><span data-stu-id="1ae08-225">`Change points` are not usually visible to the naked eye, but can be detected in your data using approaches such as in the following method.</span></span>  <span data-ttu-id="1ae08-226">На следующем рисунке представлен пример обнаружения точек изменений.</span><span class="sxs-lookup"><span data-stu-id="1ae08-226">The following image is an example of a change point detection:</span></span>

![ChangePointDetection](./media/sales-anomaly-detection/ChangePointDetection.png)

### <a name="create-the-detectchangepoint-method"></a><span data-ttu-id="1ae08-228">Создание метода DetectChangepoint()</span><span class="sxs-lookup"><span data-stu-id="1ae08-228">Create the DetectChangepoint() method</span></span>

<span data-ttu-id="1ae08-229">В следующей строке кода в методе `Main()` добавьте приведенный ниже вызов метода `DetectChangepoint()`:</span><span class="sxs-lookup"><span data-stu-id="1ae08-229">Add the following call to the `DetectChangepoint()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallDetectChangepoint](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectChangepoint)]

<span data-ttu-id="1ae08-230">Метод `DetectChangepoint()` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="1ae08-230">The `DetectChangepoint()` method executes the following tasks:</span></span>

* <span data-ttu-id="1ae08-231">обучение модели;</span><span class="sxs-lookup"><span data-stu-id="1ae08-231">Trains the model.</span></span>
* <span data-ttu-id="1ae08-232">Обнаруживает точки изменений на основе исторических данных о продажах.</span><span class="sxs-lookup"><span data-stu-id="1ae08-232">Detects change points based on historical sales data.</span></span>
* <span data-ttu-id="1ae08-233">Отображает результаты.</span><span class="sxs-lookup"><span data-stu-id="1ae08-233">Displays the results.</span></span>

<span data-ttu-id="1ae08-234">Создайте метод `DetectChangepoint()` сразу после метода `Main()`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="1ae08-234">Create the `DetectChangepoint()` method, just after the `Main()` method, using the following code:</span></span>

```csharp
static void DetectChangepoint(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

<span data-ttu-id="1ae08-235">[IidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) используется для обучения модели для обнаружения точек изменений.</span><span class="sxs-lookup"><span data-stu-id="1ae08-235">The [iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) is used to train the model for change point detection.</span></span> <span data-ttu-id="1ae08-236">Добавьте его в метод `DetectChangepoint()` со следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="1ae08-236">Add it to the `DetectChangepoint()` method with the following code:</span></span>

[!code-csharp[AddChangepointTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddChangepointTrainer)]

<span data-ttu-id="1ae08-237">Как и раньше, обучите модель на основе данных `productSales`, добавив следующую строку кода в метод `DetectChangePoint()`:</span><span class="sxs-lookup"><span data-stu-id="1ae08-237">As you did previously, fit the model to the `productSales` data by adding the following as the next line of code in the `DetectChangePoint()` method:</span></span>

[!code-csharp[TrainModel2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel2)]

<span data-ttu-id="1ae08-238">Используйте метод `Transform()` для преобразования данных `Training`, добавив в `DetectChangePoint()` следующий код:</span><span class="sxs-lookup"><span data-stu-id="1ae08-238">Use the `Transform()` method to transform the `Training` data by adding the following code to `DetectChangePoint()`:</span></span>

[!code-csharp[TransformData2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData2)]

<span data-ttu-id="1ae08-239">Как и ранее, преобразуйте `transformedData` в строго типизированный `IEnumerable` для более удобного отображения с помощью метода `CreateEnumerable()`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="1ae08-239">As you did previously, convert your `transformedData` into a strongly-typed `IEnumerable` for easier display using the `CreateEnumerable()`method with the following code:</span></span>

[!code-csharp[CreateEnumerable2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable2)]

<span data-ttu-id="1ae08-240">Создайте отображаемый заголовок, добавив в следующую строку метода `DetectChangePoint()` приведенный ниже код.</span><span class="sxs-lookup"><span data-stu-id="1ae08-240">Create a display header with the following code as the next line in the `DetectChangePoint()` method:</span></span>

[!code-csharp[DisplayHeader2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader2)]

<span data-ttu-id="1ae08-241">В результатах обнаружения точек изменений будут отображены следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="1ae08-241">You'll display the following information in your change point detection results:</span></span>

* <span data-ttu-id="1ae08-242">`Alert` указывает на оповещение о точке изменений для заданной точки данных.</span><span class="sxs-lookup"><span data-stu-id="1ae08-242">`Alert` indicates a change point alert for a given data point.</span></span>
* <span data-ttu-id="1ae08-243">`Score` является значением `ProductSales` для заданной точки данных в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="1ae08-243">`Score` is the `ProductSales` value for a given data point in the dataset.</span></span>
* <span data-ttu-id="1ae08-244">`P-Value` — "P" означает вероятность.</span><span class="sxs-lookup"><span data-stu-id="1ae08-244">`P-Value` The "P" stands for probability.</span></span> <span data-ttu-id="1ae08-245">Указывает, с какой вероятностью эта точка данных является аномалией.</span><span class="sxs-lookup"><span data-stu-id="1ae08-245">This indicates how likely this data point is an anomaly.</span></span> 
* <span data-ttu-id="1ae08-246">`Martingale value` — используется для определения того, насколько "странной" является точка данных, на основе последовательности P-значений.</span><span class="sxs-lookup"><span data-stu-id="1ae08-246">`Martingale value` is used to identify how "weird" a data point is, based on the sequence of P-values.</span></span>  

<span data-ttu-id="1ae08-247">Используйте следующий код, чтобы выполнить итерацию по `predictions` `IEnumerable` и отобразить результаты:</span><span class="sxs-lookup"><span data-stu-id="1ae08-247">Iterate through the `predictions` `IEnumerable` and display the results with the following code:</span></span>

[!code-csharp[DisplayResults2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults2)]

## <a name="change-point-detection-results"></a><span data-ttu-id="1ae08-248">Результаты обнаружения точек изменений</span><span class="sxs-lookup"><span data-stu-id="1ae08-248">Change point detection results</span></span>

<span data-ttu-id="1ae08-249">Результаты выполнения должны выглядеть примерно так, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="1ae08-249">Your results should be similar to the following.</span></span> <span data-ttu-id="1ae08-250">Во время обработки отображаются сообщения.</span><span class="sxs-lookup"><span data-stu-id="1ae08-250">During processing, messages are displayed.</span></span> <span data-ttu-id="1ae08-251">Вы можете видеть предупреждения или обработанные сообщения.</span><span class="sxs-lookup"><span data-stu-id="1ae08-251">You may see warnings, or processing messages.</span></span> <span data-ttu-id="1ae08-252">Для удобства они удалены из следующих результатов.</span><span class="sxs-lookup"><span data-stu-id="1ae08-252">These have been removed from the following results for clarity.</span></span>

```console
Detect Persistent changes in pattern
=============== Training the model Using Change Point Detection Algorithm===============
=============== End of training process ===============
Alert   Score   P-Value Martingale value
0       271.00  0.50    0.00
0       150.90  0.00    2.33
0       188.10  0.41    2.80
0       124.30  0.13    9.16
0       185.30  0.47    9.77
0       173.50  0.47    10.41
0       236.80  0.19    24.46
0       229.50  0.27    42.38
1       197.80  0.48    44.23 <-- alert is on, predicted changepoint
0       127.90  0.13    145.25
0       341.50  0.00    0.01
0       190.90  0.48    0.01
0       199.30  0.48    0.00
0       154.50  0.24    0.00
0       215.10  0.42    0.00
0       278.30  0.19    0.00
0       196.40  0.43    0.00
0       292.00  0.17    0.01
0       231.00  0.45    0.00
0       308.60  0.18    0.00
0       294.90  0.19    0.00
0       426.60  0.00    0.00
0       269.50  0.47    0.00
0       347.30  0.21    0.00
0       344.70  0.27    0.00
0       445.40  0.06    0.02
0       320.90  0.49    0.01
0       444.30  0.12    0.02
0       406.30  0.29    0.01
0       442.40  0.21    0.01
0       580.50  0.00    0.01
0       412.60  0.45    0.01
0       687.00  0.01    0.12
0       480.30  0.40    0.08
0       586.30  0.20    0.03
0       651.90  0.14    0.09
```

<span data-ttu-id="1ae08-253">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="1ae08-253">Congratulations!</span></span> <span data-ttu-id="1ae08-254">Вы успешно создали модели машинного обучения для обнаружения аномалий в виде пиковых значений и точек изменений в данных о продажах.</span><span class="sxs-lookup"><span data-stu-id="1ae08-254">You've now successfully built machine learning models for detecting spikes and change point anomalies in sales data.</span></span>

<span data-ttu-id="1ae08-255">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="1ae08-255">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) repository.</span></span>

<span data-ttu-id="1ae08-256">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="1ae08-256">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="1ae08-257">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="1ae08-257">Load the data</span></span>
> * <span data-ttu-id="1ae08-258">Обучение модели для обнаружения пиковых аномалий</span><span class="sxs-lookup"><span data-stu-id="1ae08-258">Train the model for spike anomaly detection</span></span>
> * <span data-ttu-id="1ae08-259">Обнаружение пиковых аномалий с помощью обученной модели</span><span class="sxs-lookup"><span data-stu-id="1ae08-259">Detect spike anomalies with the trained model</span></span>
> * <span data-ttu-id="1ae08-260">Обучение модели для обнаружения аномалий в точке изменений</span><span class="sxs-lookup"><span data-stu-id="1ae08-260">Train the model for change point anomaly detection</span></span>
> * <span data-ttu-id="1ae08-261">Обнаружение аномалий в точке изменений с помощью обученной модели</span><span class="sxs-lookup"><span data-stu-id="1ae08-261">Detect change point anomalies with the trained mode</span></span>

## <a name="next-steps"></a><span data-ttu-id="1ae08-262">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="1ae08-262">Next steps</span></span>

<span data-ttu-id="1ae08-263">Ознакомьтесь с примерами машинного обучения в репозитории GitHub, чтобы подробнее изучить расширенный пример с обнаружением аномалий для энергопотребления.</span><span class="sxs-lookup"><span data-stu-id="1ae08-263">Check out the Machine Learning samples GitHub repository to explore a Power Consumption Anomaly Detection sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="1ae08-264">Репозиторий GitHub dotnet/machinelearning-samples</span><span class="sxs-lookup"><span data-stu-id="1ae08-264">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PowerMeterReadings)
