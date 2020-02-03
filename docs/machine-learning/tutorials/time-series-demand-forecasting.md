---
title: Учебник. Прогнозирование спроса на прокат велосипедов (временные ряды)
description: В этом руководстве показано, как прогнозировать спрос для службы проката велосипедов с помощью одномерного анализа временных рядов и библиотеки ML.NET.
ms.date: 11/07/2019
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 026421d7b1b2a0e39118ae712780ca7fc8f6e444
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921255"
---
# <a name="tutorial-forecast-bike-rental-service-demand-with-time-series-analysis-and-mlnet"></a><span data-ttu-id="fc7f7-103">Учебник. Прогнозирование спроса для службы проката велосипедов с помощью анализа временных рядов и ML.NET</span><span class="sxs-lookup"><span data-stu-id="fc7f7-103">Tutorial: Forecast bike rental service demand with time series analysis and ML.NET</span></span>

<span data-ttu-id="fc7f7-104">Сведения о том, как прогнозировать спрос для службы проката велосипедов с помощью одномерного анализа временных рядов по данным, которые хранятся в базе данных SQL Server, с применением ML.NET.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-104">Learn how to forecast demand for a bike rental service using univariate time series analysis on data stored in a SQL Server database with ML.NET.</span></span>

<span data-ttu-id="fc7f7-105">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="fc7f7-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="fc7f7-106">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="fc7f7-106">Understand the problem</span></span>
> * <span data-ttu-id="fc7f7-107">загружать данные из базы данных;</span><span class="sxs-lookup"><span data-stu-id="fc7f7-107">Load data from a database</span></span>
> * <span data-ttu-id="fc7f7-108">создавать модели прогнозирования;</span><span class="sxs-lookup"><span data-stu-id="fc7f7-108">Create a forecasting model</span></span>
> * <span data-ttu-id="fc7f7-109">выполнять оценку модели прогнозирования;</span><span class="sxs-lookup"><span data-stu-id="fc7f7-109">Evaluate forecasting model</span></span>
> * <span data-ttu-id="fc7f7-110">сохранять модели прогнозирования;</span><span class="sxs-lookup"><span data-stu-id="fc7f7-110">Save a forecasting model</span></span>
> * <span data-ttu-id="fc7f7-111">применять модели прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-111">Use a forecasting model</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fc7f7-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="fc7f7-112">Prerequisites</span></span>

- <span data-ttu-id="fc7f7-113">[Visual Studio 2017 версии 15.6 или более поздней](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="fc7f7-113">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="time-series-forecasting-sample-overview"></a><span data-ttu-id="fc7f7-114">Общие сведения о примере прогнозирования по временным рядам</span><span class="sxs-lookup"><span data-stu-id="fc7f7-114">Time series forecasting sample overview</span></span>

<span data-ttu-id="fc7f7-115">Этот пример содержит **консольное приложение .NET Core на языке C#** , которое прогнозирует спрос для службы проката велосипедов с помощью алгоритма одномерного анализа временных рядов, называемого анализом сингулярного спектра.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-115">This sample is a **C# .NET Core console application** that forecasts demand for bike rentals using a univariate time series analysis algorithm known as Single Spectrum Analysis.</span></span> <span data-ttu-id="fc7f7-116">Код для этого примера можно найти в репозитории [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-116">The code for this sample can be found on the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) repository on GitHub.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="fc7f7-117">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="fc7f7-117">Understand the problem</span></span>

<span data-ttu-id="fc7f7-118">Для эффективной работы крайне важную роль играет правильное управление запасами.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-118">In order to run an efficient operation, inventory management plays a key role.</span></span> <span data-ttu-id="fc7f7-119">Слишком большой запас товаров означает, что значительная его часть хранится на полках и не приносит дохода.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-119">Having too much of a product in stock means unsold products sitting on the shelves not generating any revenue.</span></span> <span data-ttu-id="fc7f7-120">Слишком малый запас приводит к потере продаж, а клиенты уходят к конкурентам.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-120">Having too little product leads to lost sales and customers purchasing from competitors.</span></span> <span data-ttu-id="fc7f7-121">Это означает, что постоянно актуален вопрос об оптимальном уровне складских запасов.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-121">Therefore, the constant question is, what is the optimal amount of inventory to keep on hand?</span></span> <span data-ttu-id="fc7f7-122">Анализ временных рядов помогает ответить на этот вопрос путем изучения исторических данных, выявления закономерностей и прогнозирования на их основе значений на некоторый период вперед.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-122">Time-series analysis helps provide an answer to these questions by looking at historical data, identifying patterns, and using this information to forecast values some time in the future.</span></span>

<span data-ttu-id="fc7f7-123">Для анализа данных в этом руководстве используется метод одномерного анализа временных рядов.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-123">The technique for analyzing data used in this tutorial is univariate time-series analysis.</span></span> <span data-ttu-id="fc7f7-124">В ходе одномерного анализа временных рядов просматриваются значения одного численного параметра, измеряемого через определенные интервалы на протяжении некоторого периода времени, например ежемесячные данные о продажах.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-124">Univariate time-series analysis takes a look at a single numerical observation over a period of time at specific intervals such as monthly sales.</span></span>

<span data-ttu-id="fc7f7-125">В этом руководстве применяется алгоритм [Анализ сингулярного спектра (SSA)](http://ssa.cf.ac.uk/zhigljavsky/pdfs/SSA/SSA_encyclopedia.pdf).</span><span class="sxs-lookup"><span data-stu-id="fc7f7-125">The algorithm used in this tutorial is [Single Spectrum Analysis(SSA)](http://ssa.cf.ac.uk/zhigljavsky/pdfs/SSA/SSA_encyclopedia.pdf).</span></span> <span data-ttu-id="fc7f7-126">SSA разбивает временной ряд на набор основных компонентов.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-126">SSA works by decomposing a time-series into a set of principal components.</span></span> <span data-ttu-id="fc7f7-127">Эти компоненты можно интерпретировать как части одного сигнала: тенденции, шумы, сезонные колебания и многие другие факторы.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-127">These components can be interpreted as the parts of a signal that correspond to trends, noise, seasonality, and many other factors.</span></span> <span data-ttu-id="fc7f7-128">Полученные компоненты реконструируются и применяются для прогнозирования значений на будущие периоды.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-128">Then, these components are reconstructed and used to forecast values some time in the future.</span></span>

## <a name="create-console-application"></a><span data-ttu-id="fc7f7-129">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="fc7f7-129">Create console application</span></span>

1. <span data-ttu-id="fc7f7-130">Создайте **консольное приложение .NET Core на C#** с именем BikeDemandForecasting.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-130">Create a new **C# .NET Core console application** called "BikeDemandForecasting".</span></span>
1. <span data-ttu-id="fc7f7-131">Установите пакет NuGet для **Microsoft.ML** версии **1.4.0**</span><span class="sxs-lookup"><span data-stu-id="fc7f7-131">Install **Microsoft.ML** version **1.4.0** NuGet package</span></span>
    1. <span data-ttu-id="fc7f7-132">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-132">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    1. <span data-ttu-id="fc7f7-133">Выберите nuget.org в качестве источника пакета, щелкните вкладку **Обзор** и найдите **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-133">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**.</span></span>
    1. <span data-ttu-id="fc7f7-134">Установите флажок **Включить предварительные версии**.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-134">Check the **Include prerelease** checkbox.</span></span>
    1. <span data-ttu-id="fc7f7-135">Нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-135">Select the **Install** button.</span></span>
    1. <span data-ttu-id="fc7f7-136">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**. Затем нажмите кнопку **Принимаю** в диалоговом окне "Принятие условий лицензионного соглашения", если вы согласны с условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-136">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>
    1. <span data-ttu-id="fc7f7-137">Повторите эти действия для **System.Data.SqlClient** версии **4.7.0** и **Microsoft.ML.TimeSeries** версии **1.4.0**.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-137">Repeat these steps for **System.Data.SqlClient** version **4.7.0** and **Microsoft.ML.TimeSeries** version **1.4.0**.</span></span>

### <a name="prepare-and-understand-the-data"></a><span data-ttu-id="fc7f7-138">Подготовка и анализ данных</span><span class="sxs-lookup"><span data-stu-id="fc7f7-138">Prepare and understand the data</span></span>

1. <span data-ttu-id="fc7f7-139">Создайте каталог с именем *Data*.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-139">Create a directory called *Data*.</span></span>
1. <span data-ttu-id="fc7f7-140">Скачайте [файл базы данных *DailyDemand.mdf*](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Data/DailyDemand.mdf) и сохраните его в каталоге *Data*.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-140">Download the [*DailyDemand.mdf* database file](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Data/DailyDemand.mdf) and save it to the *Data* directory.</span></span>

> [!NOTE]
> <span data-ttu-id="fc7f7-141">Данные, используемые в этом руководстве, получены из [набора данных UCI по аренде велосипедов](https://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset).</span><span class="sxs-lookup"><span data-stu-id="fc7f7-141">The data used in this tutorial comes from the [UCI Bike Sharing Dataset](https://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset).</span></span> <span data-ttu-id="fc7f7-142">Хади Фанаит (Hadi Fanaee-T) и Жуан Гама (Joao Gama), 'Event labeling combining ensemble detectors and background knowledge' (Маркировка событий по сочетанию множества датчиков и предварительных знаний), Progress in Artificial Intelligence (2013): стр. 1–15, Springer Berlin Heidelberg, [ссылка на веб-страницу](https://link.springer.com/article/10.1007%2Fs13748-013-0040-3).</span><span class="sxs-lookup"><span data-stu-id="fc7f7-142">Fanaee-T, Hadi, and Gama, Joao, 'Event labeling combining ensemble detectors and background knowledge', Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin Heidelberg, [Web Link](https://link.springer.com/article/10.1007%2Fs13748-013-0040-3).</span></span>

<span data-ttu-id="fc7f7-143">Исходный набор данных содержит несколько столбцов, соответствующих сезонности и погоде.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-143">The original dataset contains several columns corresponding to seasonality and weather.</span></span> <span data-ttu-id="fc7f7-144">Для сокращения объема, поскольку для алгоритма в этом руководстве нужны значения только из одного числового столбца, мы уплотнили исходный набор данных, сохранив только следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="fc7f7-144">For brevity and because the algorithm used in this tutorial only requires the values from a single numerical column, the original dataset has been condensed to include only the following columns:</span></span>

- <span data-ttu-id="fc7f7-145">**dteday**: дата наблюдения.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-145">**dteday**: The date of the observation.</span></span>
- <span data-ttu-id="fc7f7-146">**year**: закодированный год наблюдения (0 = 2011, 1 = 2012).</span><span class="sxs-lookup"><span data-stu-id="fc7f7-146">**year**: The encoded year of the observation (0=2011, 1=2012).</span></span>
- <span data-ttu-id="fc7f7-147">**cnt**: общее число арендованных велосипедов за этот день.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-147">**cnt**: The total number of bike rentals for that day.</span></span>

<span data-ttu-id="fc7f7-148">Исходный набор данных сопоставляется с таблицей базы данных в базе данных SQL Server, которая имеет следующую схему.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-148">The original dataset is mapped to a database table with the following schema in a SQL Server database.</span></span>

```SQL
CREATE TABLE [Rentals] (
    [RentalDate] DATE NOT NULL,
    [Year] INT NOT NULL,
    [TotalRentals] INT NOT NULL
);
```

<span data-ttu-id="fc7f7-149">Ниже приводится пример этих данных.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-149">The following is a sample of the data:</span></span>

| <span data-ttu-id="fc7f7-150">RentalDate</span><span class="sxs-lookup"><span data-stu-id="fc7f7-150">RentalDate</span></span> | <span data-ttu-id="fc7f7-151">Год</span><span class="sxs-lookup"><span data-stu-id="fc7f7-151">Year</span></span> | <span data-ttu-id="fc7f7-152">TotalRentals</span><span class="sxs-lookup"><span data-stu-id="fc7f7-152">TotalRentals</span></span> |
| --- | --- | --- |
|<span data-ttu-id="fc7f7-153">1/1/2011</span><span class="sxs-lookup"><span data-stu-id="fc7f7-153">1/1/2011</span></span>|<span data-ttu-id="fc7f7-154">0</span><span class="sxs-lookup"><span data-stu-id="fc7f7-154">0</span></span>|<span data-ttu-id="fc7f7-155">985</span><span class="sxs-lookup"><span data-stu-id="fc7f7-155">985</span></span>|
|<span data-ttu-id="fc7f7-156">1/2/2011</span><span class="sxs-lookup"><span data-stu-id="fc7f7-156">1/2/2011</span></span>|<span data-ttu-id="fc7f7-157">0</span><span class="sxs-lookup"><span data-stu-id="fc7f7-157">0</span></span>|<span data-ttu-id="fc7f7-158">801</span><span class="sxs-lookup"><span data-stu-id="fc7f7-158">801</span></span>|
|<span data-ttu-id="fc7f7-159">1/3/2011</span><span class="sxs-lookup"><span data-stu-id="fc7f7-159">1/3/2011</span></span>|<span data-ttu-id="fc7f7-160">0</span><span class="sxs-lookup"><span data-stu-id="fc7f7-160">0</span></span>|<span data-ttu-id="fc7f7-161">1349</span><span class="sxs-lookup"><span data-stu-id="fc7f7-161">1349</span></span>|

### <a name="create-input-and-output-classes"></a><span data-ttu-id="fc7f7-162">Создание классов входных и выходных данных</span><span class="sxs-lookup"><span data-stu-id="fc7f7-162">Create input and output classes</span></span>

1. <span data-ttu-id="fc7f7-163">Откройте файл *Program.cs* и замените существующие инструкции `using` следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-163">Open *Program.cs* file and replace the existing `using` statements with the following:</span></span>

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L1-L8)]

1. <span data-ttu-id="fc7f7-164">Создайте класс `ModelInput`.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-164">Create `ModelInput` class.</span></span> <span data-ttu-id="fc7f7-165">Добавьте приведенный ниже код в класс `Program`.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-165">Below the `Program` class, add the following code.</span></span>

    [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L120-L127)]

    <span data-ttu-id="fc7f7-166">Класс `ModelInput` содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="fc7f7-166">The `ModelInput` class contains the following columns:</span></span>

    - <span data-ttu-id="fc7f7-167">**RentalDate**: дата наблюдения.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-167">**RentalDate**: The date of the observation.</span></span>
    - <span data-ttu-id="fc7f7-168">**Year**: закодированный год наблюдения (0 = 2011, 1 = 2012).</span><span class="sxs-lookup"><span data-stu-id="fc7f7-168">**Year**: The encoded year of the observation (0=2011, 1=2012).</span></span>
    - <span data-ttu-id="fc7f7-169">**TotalRentals**: общее число арендованных велосипедов за этот день.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-169">**TotalRentals**: The total number of bike rentals for that day.</span></span>

1. <span data-ttu-id="fc7f7-170">Создайте класс `ModelOutput` под только что созданным классом `ModelInput`.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-170">Create `ModelOutput` class below the newly created `ModelInput` class.</span></span>

    [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L129-L136)]

    <span data-ttu-id="fc7f7-171">Класс `ModelOutput` содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="fc7f7-171">The `ModelOutput` class contains the following columns:</span></span>

    - <span data-ttu-id="fc7f7-172">**ForecastedRentals**: прогнозируемые значения для прогнозируемого периода.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-172">**ForecastedRentals**: The predicted values for the forecasted period.</span></span>
    - <span data-ttu-id="fc7f7-173">**LowerBoundRentals**: минимальные прогнозируемые значения для прогнозируемого периода.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-173">**LowerBoundRentals**: The predicted minimum values for the forecasted period.</span></span>
    - <span data-ttu-id="fc7f7-174">**UpperBoundRentals**: максимальные прогнозируемые значения для прогнозируемого периода.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-174">**UpperBoundRentals**: The predicted maximum values for the forecasted period.</span></span>

### <a name="define-paths-and-initialize-variables"></a><span data-ttu-id="fc7f7-175">Определение путей и инициализация переменных</span><span class="sxs-lookup"><span data-stu-id="fc7f7-175">Define paths and initialize variables</span></span>

1. <span data-ttu-id="fc7f7-176">В методе `Main` определите переменные, которые будут хранить расположение данных, строку подключения и расположение для обученной модели.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-176">Inside the `Main` method, define variables to store the location of your data, connection string, and where to save the trained model.</span></span>

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L16-L19)]

1. <span data-ttu-id="fc7f7-177">Инициализируйте переменную `mlContext` новым экземпляром [`MLContext`](xref:Microsoft.ML.MLContext), добавив следующую строку в метод `Main`.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-177">Initialize the `mlContext` variable with a new instance of [`MLContext`](xref:Microsoft.ML.MLContext) by adding the following line to the `Main` method.</span></span>

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L21)]

    <span data-ttu-id="fc7f7-178">Класс [`MLContext`](xref:Microsoft.ML.MLContext) будет стартовой точкой для любых операций ML.NET. При инициализации класса mlContext создается новая среда ML.NET, которая может использоваться всеми объектами в рабочем процессе создания модели.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-178">The [`MLContext`](xref:Microsoft.ML.MLContext) class is a starting point for all ML.NET operations, and initializing mlContext creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="fc7f7-179">По существу он аналогичен классу `DBContext` в Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-179">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="fc7f7-180">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="fc7f7-180">Load the data</span></span>

1. <span data-ttu-id="fc7f7-181">Создайте `DatabaseLoader`, который загружает записи с типом `ModelInput`.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-181">Create `DatabaseLoader` that loads records of type `ModelInput`.</span></span>

    [!code-csharp [CreateDBLoader](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L23)]

1. <span data-ttu-id="fc7f7-182">Определите запрос для загрузки данных из базы данных.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-182">Define the query to load the data from the database.</span></span>

    [!code-csharp [DefineSQLQuery](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L25)]

    <span data-ttu-id="fc7f7-183">Алгоритмы ML.NET предполагают, что данные имеют тип [`Single`](xref:System.Single).</span><span class="sxs-lookup"><span data-stu-id="fc7f7-183">ML.NET algorithms expect data to be of type [`Single`](xref:System.Single).</span></span> <span data-ttu-id="fc7f7-184">Следовательно, полученные из базы данных числовые значения, тип которых отличается от [`Real`](xref:System.Data.SqlDbType) (значение одиночной точности с плавающей запятой), необходимо преобразовать в [`Real`](xref:System.Data.SqlDbType).</span><span class="sxs-lookup"><span data-stu-id="fc7f7-184">Therefore, numerical values coming from the database that are not of type [`Real`](xref:System.Data.SqlDbType), a single-precision floating-point value, have to be converted to [`Real`](xref:System.Data.SqlDbType).</span></span>

    <span data-ttu-id="fc7f7-185">Столбцы `Year` и `TotalRental` в базе данных имеют целочисленные типы.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-185">The `Year` and `TotalRental` columns are both integer types in the database.</span></span> <span data-ttu-id="fc7f7-186">С помощью встроенной функции `CAST` они приводятся к типу `Real`.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-186">Using the `CAST` built-in function, they are both cast to `Real`.</span></span>

1. <span data-ttu-id="fc7f7-187">Создайте `DatabaseSource` для подключения к базе данных и выполните запрос.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-187">Create a `DatabaseSource` to connect to the database and execute the query.</span></span>

    [!code-csharp [CreateDBSource](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L27-L29)]

1. <span data-ttu-id="fc7f7-188">Загрузите данные в `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-188">Load the data into an `IDataView`.</span></span>

    [!code-csharp [LoadData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L31)]

1. <span data-ttu-id="fc7f7-189">Набор данных содержит данные за два года.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-189">The dataset contains two years worth of data.</span></span> <span data-ttu-id="fc7f7-190">Для обучения используются только данные за первый год, а данные за второй год откладываются для сравнения фактических значений с прогнозом, созданным моделью.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-190">Only data from the first year is used for training, the second year is held out to compare the actual values against the forecast produced by the model.</span></span> <span data-ttu-id="fc7f7-191">Отфильтруйте данные с помощью преобразования [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*).</span><span class="sxs-lookup"><span data-stu-id="fc7f7-191">Filter the data using the [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) transform.</span></span>

    [!code-csharp [SplitData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L33-L34)]

    <span data-ttu-id="fc7f7-192">Для отбора данных за первый год извлекаются те строки, у которых значение в столбце `Year` меньше 1. Для этого параметру `upperBound` присваивается значение 1.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-192">For the first year, only the values in the `Year` column less than 1 are selected by setting the `upperBound` parameter to 1.</span></span> <span data-ttu-id="fc7f7-193">И наоборот, для данных за второй год извлекаются те строки, у которых это значение равно 1. Для этого параметру `lowerBound` присваивается значение 1.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-193">Conversely, for the second year, values greater than or equal to 1 are selected by setting the `lowerBound` parameter to 1.</span></span>

## <a name="define-time-series-analysis-pipeline"></a><span data-ttu-id="fc7f7-194">Определение конвейера анализа временных рядов</span><span class="sxs-lookup"><span data-stu-id="fc7f7-194">Define time series analysis pipeline</span></span>

1. <span data-ttu-id="fc7f7-195">Определите конвейер, который использует [SsaForecastingEstimator](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator) для прогнозирования значений в наборе данных временных рядов.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-195">Define a pipeline that uses the [SsaForecastingEstimator](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator) to forecast values in a time-series dataset.</span></span>

    [!code-csharp [DefinePipeline](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L36-L45)]

    <span data-ttu-id="fc7f7-196">`forecastingPipeline` принимает 365 точек данных за первый год и разделяет набор данных временных рядов на выборки за 30-дневные (помесячные) интервалы, как указано в параметре `seriesLength`.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-196">The `forecastingPipeline` takes 365 data points for the first year and samples or splits the time-series dataset into 30-day (monthly) intervals as specified by the `seriesLength` parameter.</span></span> <span data-ttu-id="fc7f7-197">Каждая из этих выборок анализируется по еженедельным (7-дневным) периодам.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-197">Each of these samples is analyzed through weekly or a 7-day window.</span></span> <span data-ttu-id="fc7f7-198">При определении прогнозируемого значения для предстоящих периодов используются значения за предыдущие семь дней.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-198">When determining what the forecasted value for the next period(s) is, the values from previous seven days are used to make a prediction.</span></span> <span data-ttu-id="fc7f7-199">Модель настроена на прогнозирование семи предстоящих периодов, как определено параметром `horizon`.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-199">The model is set to forecast seven periods into the future as defined by the `horizon` parameter.</span></span> <span data-ttu-id="fc7f7-200">Прогноз является лишь предположением, то есть не всегда будет на 100 % точным.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-200">Because a forecast is an informed guess, it's not always 100% accurate.</span></span> <span data-ttu-id="fc7f7-201">Поэтому нам лучше получить диапазон значений, который определяется верхней и нижней границами для наилучшего и наихудшего сценариев.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-201">Therefore, it's good to know the range of values in the best and worst-case scenarios as defined by the upper and lower bounds.</span></span> <span data-ttu-id="fc7f7-202">В нашем примере для определения нижней и верхней границ устанавливается уровень достоверности 95 %.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-202">In this case, the level of confidence for the lower and upper bounds is set to 95%.</span></span> <span data-ttu-id="fc7f7-203">Вы можете увеличить или уменьшить этот уровень достоверности.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-203">The confidence level can be increased or decreased accordingly.</span></span> <span data-ttu-id="fc7f7-204">Чем выше значение уровня достоверности, тем шире диапазон между верхней и нижней границами.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-204">The higher the value, the wider the range is between the upper and lower bounds to achieve the desired level of confidence.</span></span>

1. <span data-ttu-id="fc7f7-205">Используйте метод [`Fit`](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator.Fit*), чтобы обучить модель и подогнать данные по ранее определенным `forecastingPipeline`.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-205">Use the [`Fit`](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator.Fit*) method to train the model and fit the data to the previously defined `forecastingPipeline`.</span></span>

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L47)]

## <a name="evaluate-the-model"></a><span data-ttu-id="fc7f7-206">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="fc7f7-206">Evaluate the model</span></span>

<span data-ttu-id="fc7f7-207">Оцените точность модели, создав прогноз данных на следующий год и сравнив их с фактическими значениями.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-207">Evaluate how well the model performs by forecasting next year's data and comparing it against the actual values.</span></span>

1. <span data-ttu-id="fc7f7-208">Добавьте новый служебный метод `Evaluate` под методом `Main`.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-208">Below the `Main` method, create a new utility method called `Evaluate`.</span></span>

    ```csharp
    static void Evaluate(IDataView testData, ITransformer model, MLContext mlContext)
    {

    }
    ```

1. <span data-ttu-id="fc7f7-209">В методе `Evaluate` примените метод [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) с обученной моделью, чтобы спрогнозировать данные на следующий год.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-209">Inside the `Evaluate` method, forecast the second year's data by using the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method with the trained model.</span></span>

    [!code-csharp [EvaluateForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L62)]

1. <span data-ttu-id="fc7f7-210">Чтобы получить фактические значения из примера данных, используйте метод [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*).</span><span class="sxs-lookup"><span data-stu-id="fc7f7-210">Get the actual values from the data by using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method.</span></span>

    [!code-csharp [GetActualRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L65-L67)]

1. <span data-ttu-id="fc7f7-211">Чтобы получить прогнозируемые значения, используйте метод [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*).</span><span class="sxs-lookup"><span data-stu-id="fc7f7-211">Get the forecast values by using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method.</span></span>

    [!code-csharp [GetForecastRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L70-L72)]

1. <span data-ttu-id="fc7f7-212">Вычислите разницу между реальными и прогнозируемыми значениями, которая обычно называется ошибкой.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-212">Calculate the difference between the actual and forecast values, commonly referred to as the error.</span></span>

    [!code-csharp [CalculateError](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L75)]

1. <span data-ttu-id="fc7f7-213">Для оценки точности модели вычислите среднюю абсолютную погрешность и среднеквадратическую погрешность.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-213">Measure performance by computing the Mean Absolute Error and Root Mean Squared Error values.</span></span>

    [!code-csharp [CalculateMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L78-L79)]

    <span data-ttu-id="fc7f7-214">Для оценки точности используются следующие метрики.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-214">To evaluate performance, the following metrics are used:</span></span>

    - <span data-ttu-id="fc7f7-215">**Средняя абсолютная погрешность**. Оценивает, насколько близки прогнозы к фактическому значению.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-215">**Mean Absolute Error**: Measures how close predictions are to the actual value.</span></span> <span data-ttu-id="fc7f7-216">Принимает значения в диапазоне от 0 до бесконечности.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-216">This value ranges between 0 and infinity.</span></span> <span data-ttu-id="fc7f7-217">Чем ближе это значение к 0, тем лучше качество модели.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-217">The closer to 0, the better the quality of the model.</span></span>
    - <span data-ttu-id="fc7f7-218">**Среднеквадратическая погрешность**. Суммирует ошибки в модели.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-218">**Root Mean Squared Error**: Summarizes the error in the model.</span></span> <span data-ttu-id="fc7f7-219">Принимает значения в диапазоне от 0 до бесконечности.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-219">This value ranges between 0 and infinity.</span></span> <span data-ttu-id="fc7f7-220">Чем ближе это значение к 0, тем лучше качество модели.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-220">The closer to 0, the better the quality of the model.</span></span>

1. <span data-ttu-id="fc7f7-221">Выведите значения метрик на консоль.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-221">Output the metrics to the console.</span></span>

    [!code-csharp [OutputMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L82-L85)]

1. <span data-ttu-id="fc7f7-222">Используйте метод `Evaluate` в методе `Main`.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-222">Use the `Evaluate` method inside the `Main` method.</span></span>

    [!code-csharp [EvaluateModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L49)]

## <a name="save-the-model"></a><span data-ttu-id="fc7f7-223">Сохранение модели</span><span class="sxs-lookup"><span data-stu-id="fc7f7-223">Save the model</span></span>

<span data-ttu-id="fc7f7-224">Если вы довольны поведением модели, сохраните ее для использования в других приложениях.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-224">If you're satisfied with your model, save it for later use in other applications.</span></span>

1. <span data-ttu-id="fc7f7-225">В методе `Main` создайте [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="fc7f7-225">In the `Main` method, create a [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602).</span></span> <span data-ttu-id="fc7f7-226">[`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602) — это удобный метод для создания единичных прогнозов.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-226">[`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602) is a convenience method to make single predictions.</span></span>

    [!code-csharp [CreateTimeSeriesEngine](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L51)]

1. <span data-ttu-id="fc7f7-227">Сохраните модель в файл с именем `MLModel.zip`, которое задано ранее определенной переменной `modelPath`.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-227">Save the model to a file called `MLModel.zip` as specified by the previously defined `modelPath` variable.</span></span> <span data-ttu-id="fc7f7-228">Выполните метод [`Checkpoint`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.CheckPoint*), чтобы сохранить модель.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-228">Use the [`Checkpoint`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.CheckPoint*) method to save the model.</span></span>

    [!code-csharp [SaveModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L52)]

## <a name="use-the-model-to-forecast-demand"></a><span data-ttu-id="fc7f7-229">Применение модели для прогнозирования спроса</span><span class="sxs-lookup"><span data-stu-id="fc7f7-229">Use the model to forecast demand</span></span>

1. <span data-ttu-id="fc7f7-230">Добавьте новый служебный метод `Forecast` под методом `Evaluate`.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-230">Below the `Evaluate` method, create a new utility method called `Forecast`.</span></span>

    ```csharp
    static void Forecast(IDataView testData, int horizon, TimeSeriesPredictionEngine<ModelInput, ModelOutput> forecaster, MLContext mlContext)
    {

    }
    ```

1. <span data-ttu-id="fc7f7-231">В методе `Forecast` вызовите метод [`Predict`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.Predict*), чтобы получить прогноз по прокату на следующие семь дней.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-231">Inside the `Forecast` method, use the [`Predict`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.Predict*) method to forecast rentals for the next seven days.</span></span>

    [!code-csharp [SingleForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L91)]

1. <span data-ttu-id="fc7f7-232">Сравните фактические и прогнозируемые значения по семи периодам.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-232">Align the actual and forecast values for seven periods.</span></span>

    [!code-csharp [GetForecastOutput](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L93-L108)]

1. <span data-ttu-id="fc7f7-233">В цикле извлекайте выходные данные прогноза и выводите их на консоль.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-233">Iterate through the forecast output and display it on the console.</span></span>

    [!code-csharp [DisplayForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L111-L116)]

## <a name="run-the-application"></a><span data-ttu-id="fc7f7-234">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="fc7f7-234">Run the application</span></span>

1. <span data-ttu-id="fc7f7-235">Из метода `Main` вызовите метод `Forecast`.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-235">Inside the `Main` method, call the `Forecast` method.</span></span>

    [!code-csharp [BuildForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L54)]

1. <span data-ttu-id="fc7f7-236">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-236">Run the application.</span></span> <span data-ttu-id="fc7f7-237">Должен отобразиться результат, аналогичный приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-237">Output similar to that below should appear on the console.</span></span> <span data-ttu-id="fc7f7-238">Для краткости выходные данные были сжаты.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-238">For brevity, the output has been condensed.</span></span>

    ```text
    Evaluation Metrics
    ---------------------
    Mean Absolute Error: 726.416
    Root Mean Squared Error: 987.658

    Rental Forecast
    ---------------------
    Date: 1/1/2012
    Actual Rentals: 2294
    Lower Estimate: 1197.842
    Forecast: 2334.443
    Upper Estimate: 3471.044

    Date: 1/2/2012
    Actual Rentals: 1951
    Lower Estimate: 1148.412
    Forecast: 2360.861
    Upper Estimate: 3573.309
    ```

<span data-ttu-id="fc7f7-239">Сверка фактических и прогнозируемых значений показывает следующие связи:</span><span class="sxs-lookup"><span data-stu-id="fc7f7-239">Inspection of the actual and forecasted values shows the following relationships:</span></span>

![Сравнение фактических и прогнозируемых значений](./media/time-series-demand-forecasting/forecast.png)

<span data-ttu-id="fc7f7-241">Хотя прогнозируемые значения и не дают точного совпадения с реальными данными о прокате, они предоставляют достаточно узкий диапазон значений, который позволяет оптимизировать использование ресурсов организации.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-241">While the forecasted values are not predicting the exact number of rentals, they provide a more narrow range of values that allows an operation to optimize their use of resources.</span></span>

<span data-ttu-id="fc7f7-242">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="fc7f7-242">Congratulations!</span></span> <span data-ttu-id="fc7f7-243">Вы успешно создали модель машинного обучения для прогнозирования спроса на прокат велосипедов.</span><span class="sxs-lookup"><span data-stu-id="fc7f7-243">You've now successfully built a time series machine learning model to forecast bike rental demand.</span></span>

<span data-ttu-id="fc7f7-244">Исходный код для этого руководства можно найти в репозитории [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand).</span><span class="sxs-lookup"><span data-stu-id="fc7f7-244">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fc7f7-245">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="fc7f7-245">Next steps</span></span>

- [<span data-ttu-id="fc7f7-246">Задачи машинного обучения в ML.NET</span><span class="sxs-lookup"><span data-stu-id="fc7f7-246">Machine learning tasks in ML.NET</span></span>](../resources/tasks.md)
- [<span data-ttu-id="fc7f7-247">Повышение уровня точности модели</span><span class="sxs-lookup"><span data-stu-id="fc7f7-247">Improve model accuracy</span></span>](../resources/improve-machine-learning-model-ml-net.md)
