---
title: Прогнозирование платы с помощью алгоритма обучения регрессии с использованием ML.NET
description: Прогнозирование платы с помощью алгоритма обучения регрессии с использованием ML.NET.
author: aditidugar
ms.author: johalex
ms.date: 03/05/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 543411f58f2d7c5c4e8658bd90cf52c7a3291ec3
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678410"
---
# <a name="tutorial-predict-prices-using-a-regression-learner-with-mlnet"></a><span data-ttu-id="12b06-103">Учебник. Прогнозирование платы с помощью алгоритма обучения регрессии с использованием ML.NET</span><span class="sxs-lookup"><span data-stu-id="12b06-103">Tutorial: Predict prices using a regression learner with ML.NET</span></span>

<span data-ttu-id="12b06-104">В этом руководстве описано, как с помощью ML.NET создать [модель регрессии](../resources/glossary.md#regression) для прогнозирования цен, особенно платы за проезд в такси в городе Нью-Йорке.</span><span class="sxs-lookup"><span data-stu-id="12b06-104">This tutorial illustrates how to use ML.NET to build a [regression model](../resources/glossary.md#regression) for predicting prices, specifically, New York City taxi fares.</span></span>

> [!NOTE]
> <span data-ttu-id="12b06-105">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="12b06-105">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="12b06-106">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="12b06-106">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="12b06-107">Сейчас в этом руководстве и соответствующем примере используется **ML.NET версии 0.10**.</span><span class="sxs-lookup"><span data-stu-id="12b06-107">This tutorial and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="12b06-108">Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="12b06-108">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="12b06-109">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="12b06-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="12b06-110">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="12b06-110">Understand the problem</span></span>
> * <span data-ttu-id="12b06-111">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="12b06-111">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="12b06-112">Подготовка и анализ данных</span><span class="sxs-lookup"><span data-stu-id="12b06-112">Prepare and understand the data</span></span>
> * <span data-ttu-id="12b06-113">Создание конвейера обучения</span><span class="sxs-lookup"><span data-stu-id="12b06-113">Create a learning pipeline</span></span>
> * <span data-ttu-id="12b06-114">Загрузка и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="12b06-114">Load and transform the data</span></span>
> * <span data-ttu-id="12b06-115">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="12b06-115">Choose a learning algorithm</span></span>
> * <span data-ttu-id="12b06-116">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="12b06-116">Train the model</span></span>
> * <span data-ttu-id="12b06-117">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="12b06-117">Evaluate the model</span></span>
> * <span data-ttu-id="12b06-118">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="12b06-118">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="12b06-119">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="12b06-119">Prerequisites</span></span>

* <span data-ttu-id="12b06-120">[Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="12b06-120">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="12b06-121">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="12b06-121">Understand the problem</span></span>

<span data-ttu-id="12b06-122">Рассматриваемая проблема основана на сценарии прогнозирования платы за поездку на такси в Нью-Йорке.</span><span class="sxs-lookup"><span data-stu-id="12b06-122">This problem is about predicting the fare of a taxi trip in New York City.</span></span> <span data-ttu-id="12b06-123">На первый взгляд может показаться, что плата зависит только от расстояния.</span><span class="sxs-lookup"><span data-stu-id="12b06-123">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="12b06-124">Но службы такси в Нью-Йорке изменяют плату с учетом еще нескольких факторов, таких как наличие дополнительных пассажиров или оплата кредитной картой вместо наличных.</span><span class="sxs-lookup"><span data-stu-id="12b06-124">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="12b06-125">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="12b06-125">Select the appropriate machine learning task</span></span>

<span data-ttu-id="12b06-126">Вы хотите спрогнозировать стоимость, которая является реальным значением, зависящим от других факторов в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="12b06-126">You want to predict the price value, which is a real value, based on the other factors in the data set.</span></span> <span data-ttu-id="12b06-127">Для этого нужно выбрать задачу машинного обучения [регрессия](../resources/glossary.md#regression).</span><span class="sxs-lookup"><span data-stu-id="12b06-127">To do that you choose a [regression](../resources/glossary.md#regression) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="12b06-128">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="12b06-128">Create a console application</span></span>

1. <span data-ttu-id="12b06-129">Откройте Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="12b06-129">Open Visual Studio 2017.</span></span> <span data-ttu-id="12b06-130">Выберите **Файл** > **Создать** > **Проект** в меню.</span><span class="sxs-lookup"><span data-stu-id="12b06-130">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="12b06-131">В диалоговом окне **Новый проект** выберите узел **Visual C#**, а затем — узел **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="12b06-131">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="12b06-132">Выберите шаблон проекта **Консольное приложение (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="12b06-132">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="12b06-133">В текстовое поле **Имя** введите TaxiFarePrediction, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="12b06-133">In the **Name** text box, type "TaxiFarePrediction" and then select the **OK** button.</span></span>

1. <span data-ttu-id="12b06-134">Создайте каталог с именем *Data* в папке проекта, чтобы хранить в нем наборы данных и файлы модели:</span><span class="sxs-lookup"><span data-stu-id="12b06-134">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="12b06-135">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="12b06-135">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="12b06-136">Введите имя папки Data и нажмите клавишу "ВВОД".</span><span class="sxs-lookup"><span data-stu-id="12b06-136">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="12b06-137">Установите пакет NuGet для **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="12b06-137">Install the **Microsoft.ML** NuGet Package:</span></span>

    <span data-ttu-id="12b06-138">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="12b06-138">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="12b06-139">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку **Обзор**, выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="12b06-139">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="12b06-140">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="12b06-140">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="12b06-141">Подготовка и анализ данных</span><span class="sxs-lookup"><span data-stu-id="12b06-141">Prepare and understand the data</span></span>

1. <span data-ttu-id="12b06-142">Скачайте наборы данных [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) и [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv), сохранив их в созданной на предыдущем шаге папке *Data*.</span><span class="sxs-lookup"><span data-stu-id="12b06-142">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="12b06-143">Эти наборы данных используются для обучения модели машинного обучения и последующей оценки точности этой модели.</span><span class="sxs-lookup"><span data-stu-id="12b06-143">We use these data sets to train the machine learning model and then evaluate how accurate the model is.</span></span> <span data-ttu-id="12b06-144">Эти наборы данных взяты из [наборов данных NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span><span class="sxs-lookup"><span data-stu-id="12b06-144">These data sets are originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

1. <span data-ttu-id="12b06-145">В **обозревателе решений** щелкните правой кнопкой мыши каждый из файлов \*.csv и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="12b06-145">In **Solution Explorer**, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="12b06-146">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="12b06-146">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

1. <span data-ttu-id="12b06-147">Откройте набор данных **taxi-fare-train.csv** и просмотрите заголовки столбцов в первой строке.</span><span class="sxs-lookup"><span data-stu-id="12b06-147">Open the **taxi-fare-train.csv** data set and look at column headers in the first row.</span></span> <span data-ttu-id="12b06-148">Теперь изучите каждый из столбцов.</span><span class="sxs-lookup"><span data-stu-id="12b06-148">Take a look at each of the columns.</span></span> <span data-ttu-id="12b06-149">Разберитесь, какие данные в них хранятся, и определите, какие столбцы являются **признаками**, а в каком содержится **метка**.</span><span class="sxs-lookup"><span data-stu-id="12b06-149">Understand the data and decide which columns are **features** and which one is the **label**.</span></span>

<span data-ttu-id="12b06-150">**Метка** — это столбец, значения в котором вы хотите спрогнозировать.</span><span class="sxs-lookup"><span data-stu-id="12b06-150">The **label** is the identifier of the column you want to predict.</span></span> <span data-ttu-id="12b06-151">Выбранные **признаки** используются для прогнозирования метки.</span><span class="sxs-lookup"><span data-stu-id="12b06-151">The identified **features** are used to predict the label.</span></span>

<span data-ttu-id="12b06-152">Предоставленный набор данных содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="12b06-152">The provided data set contains the following columns:</span></span>

* <span data-ttu-id="12b06-153">**vendor_id:** идентификатор поставщика услуг такси — это признак.</span><span class="sxs-lookup"><span data-stu-id="12b06-153">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="12b06-154">**rate_code:** тип тарифа для поездки на такси — это признак.</span><span class="sxs-lookup"><span data-stu-id="12b06-154">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="12b06-155">**passenger_count:** число пассажиров в поездке — это признак.</span><span class="sxs-lookup"><span data-stu-id="12b06-155">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="12b06-156">**trip_time_in_secs:** время, затраченное на поездку.</span><span class="sxs-lookup"><span data-stu-id="12b06-156">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="12b06-157">Вам требуется спрогнозировать плату за одну поездку до того, как поездка будет завершена.</span><span class="sxs-lookup"><span data-stu-id="12b06-157">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="12b06-158">На этот момент вам неизвестна продолжительность поездки.</span><span class="sxs-lookup"><span data-stu-id="12b06-158">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="12b06-159">Таким образом, продолжительность поездки не является признаком и соответствующий столбец следует исключить из модели.</span><span class="sxs-lookup"><span data-stu-id="12b06-159">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
* <span data-ttu-id="12b06-160">**trip_distance:** расстояние поездки — это признак.</span><span class="sxs-lookup"><span data-stu-id="12b06-160">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="12b06-161">**payment_type:** метод оплаты (наличные или кредитная карта) — это признак.</span><span class="sxs-lookup"><span data-stu-id="12b06-161">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="12b06-162">**fare_amount:** общая сумма, уплаченная за поездку на такси, — это метка.</span><span class="sxs-lookup"><span data-stu-id="12b06-162">**fare_amount:** The total taxi fare paid is the label.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="12b06-163">Создание классов данных</span><span class="sxs-lookup"><span data-stu-id="12b06-163">Create data classes</span></span>

<span data-ttu-id="12b06-164">Создайте классы для входных данных и прогнозов:</span><span class="sxs-lookup"><span data-stu-id="12b06-164">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="12b06-165">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="12b06-165">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="12b06-166">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *TaxiTrip.cs*.</span><span class="sxs-lookup"><span data-stu-id="12b06-166">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="12b06-167">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="12b06-167">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="12b06-168">Добавьте следующие директивы `using` в новый файл.</span><span class="sxs-lookup"><span data-stu-id="12b06-168">Add the following `using` directives to the new file:</span></span>

   [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="12b06-169">Удалите из файла *TaxiTrip.cs* существующее определение класса и добавьте следующий код с двумя классами `TaxiTrip` и `TaxiTripFarePrediction`:</span><span class="sxs-lookup"><span data-stu-id="12b06-169">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="12b06-170">Класс `TaxiTrip` содержит входные данные и определения для каждого из столбцов в этом наборе данных.</span><span class="sxs-lookup"><span data-stu-id="12b06-170">`TaxiTrip` is the input data class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="12b06-171">Используйте атрибут <xref:Microsoft.ML.Data.ColumnAttribute>, чтобы указать индексы исходных столбцов в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="12b06-171">Use the <xref:Microsoft.ML.Data.ColumnAttribute> attribute to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="12b06-172">Класс `TaxiTripFarePrediction` представляет результаты прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="12b06-172">The `TaxiTripFarePrediction` class represents predicted results.</span></span> <span data-ttu-id="12b06-173">Он содержит одно поле типа float `FareAmount`, к которому применен атрибут `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute>.</span><span class="sxs-lookup"><span data-stu-id="12b06-173">It has a single float field, `FareAmount`, with a `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> attribute applied.</span></span> <span data-ttu-id="12b06-174">В случае задачи регрессии столбец **Оценка** содержит прогнозируемые значения метки.</span><span class="sxs-lookup"><span data-stu-id="12b06-174">In case of the regression task the **Score** column contains predicted label values.</span></span>

> [!NOTE]
> <span data-ttu-id="12b06-175">Используйте тип `float` для представления значений с плавающей запятой в классах данных ввода и прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="12b06-175">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="12b06-176">Определение путей к данным и модели</span><span class="sxs-lookup"><span data-stu-id="12b06-176">Define data and model paths</span></span>

<span data-ttu-id="12b06-177">Добавьте следующие новые операторы `using` в начало файла *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="12b06-177">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="12b06-178">Необходимо создать три поля, которые будут содержать пути к файлам с наборами данных и к файлу для сохранения модели, а также глобальную переменную для `TextLoader`:</span><span class="sxs-lookup"><span data-stu-id="12b06-178">You need to create three fields to hold the paths to the files with data sets and the file to save the model, and a global variable for the `TextLoader`:</span></span>

* <span data-ttu-id="12b06-179">`_trainDataPath` содержит путь к файлу с набором данных, используемым для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="12b06-179">`_trainDataPath` contains the path to the file with the data set used to train the model.</span></span>
* <span data-ttu-id="12b06-180">`_testDataPath` содержит путь к файлу с набором данных, используемым для оценки модели.</span><span class="sxs-lookup"><span data-stu-id="12b06-180">`_testDataPath` contains the path to the file with the data set used to evaluate the model.</span></span>
* <span data-ttu-id="12b06-181">`_modelPath` содержит путь к файлу для сохранения обучаемой модели.</span><span class="sxs-lookup"><span data-stu-id="12b06-181">`_modelPath` contains the path to the file where the trained model is stored.</span></span>
* <span data-ttu-id="12b06-182">`_textLoader` представляет собой <xref:Microsoft.ML.Data.TextLoader>, используемый для загрузки и преобразования наборов данных.</span><span class="sxs-lookup"><span data-stu-id="12b06-182">`_textLoader` is the <xref:Microsoft.ML.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="12b06-183">Добавьте следующий код прямо перед методом `Main`, чтобы указать эти пути и переменную `_textLoader`:</span><span class="sxs-lookup"><span data-stu-id="12b06-183">Add the following code right above the `Main` method to specify those paths and for the `_textLoader` variable:</span></span>

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="12b06-184">При создании модели с использованием ML.NET сначала необходимо создать контекст машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="12b06-184">When building a model with ML.NET you start by creating an ML Context.</span></span> <span data-ttu-id="12b06-185">Концептуально это сопоставимо с использованием `DbContext` в Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="12b06-185">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="12b06-186">Среда предоставляет контекст для вашего задания машинного обучения, который можно использовать для отслеживания исключений и ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="12b06-186">The environment provides a context for your machine learning job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="12b06-187">Инициализация переменных в методе Main</span><span class="sxs-lookup"><span data-stu-id="12b06-187">Initialize variables in Main</span></span>

<span data-ttu-id="12b06-188">Создайте переменную с именем `mlContext` и инициализируйте ее с новым экземпляром `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="12b06-188">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="12b06-189">Замените строку `Console.WriteLine("Hello World!")` в методе `Main` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="12b06-189">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create the ML Context")]

<span data-ttu-id="12b06-190">Затем, чтобы настроить загрузку данных, инициализируйте глобальную переменную `_textLoader` для повторного использования.</span><span class="sxs-lookup"><span data-stu-id="12b06-190">Next, to setup for data loading initialize the `_textLoader` global variable in order to reuse it.</span></span> <span data-ttu-id="12b06-191">При создании `TextLoader` вы передаете необходимый контекст и класс <xref:Microsoft.ML.Data.TextLoader.Arguments>, который включает настройку.</span><span class="sxs-lookup"><span data-stu-id="12b06-191">When you create a `TextLoader`, you pass in the context needed and the <xref:Microsoft.ML.Data.TextLoader.Arguments> class which enables customization.</span></span> <span data-ttu-id="12b06-192">Укажите схему данных, передав в `TextLoader` массив объектов <xref:Microsoft.ML.Data.TextLoader.Column>, содержащий имена всех столбцов и их типы.</span><span class="sxs-lookup"><span data-stu-id="12b06-192">Specify the data schema by passing an array of <xref:Microsoft.ML.Data.TextLoader.Column> objects to the `TextLoader` containing all the column names and their types.</span></span> <span data-ttu-id="12b06-193">Мы определили схему данных ранее при создании класса `TaxiTrip`.</span><span class="sxs-lookup"><span data-stu-id="12b06-193">We defined the data schema previously when we created our `TaxiTrip` class.</span></span>

<span data-ttu-id="12b06-194">Класс `TextLoader` возвращает полностью инициализированный <xref:Microsoft.ML.Data.TextLoader>.</span><span class="sxs-lookup"><span data-stu-id="12b06-194">The `TextLoader` class returns a fully initialized <xref:Microsoft.ML.Data.TextLoader></span></span>  

<span data-ttu-id="12b06-195">Чтобы инициализировать глобальную переменную `_textLoader` и повторно использовать ее для необходимых наборов данных, добавьте следующий код после инициализации `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="12b06-195">To initialize the `_textLoader` global variable in order to reuse it for the needed datasets, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[initTextLoader](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Initialize the TextLoader")]

<span data-ttu-id="12b06-196">В качестве следующей строки кода в методе `Main` добавьте приведенный ниже код, чтобы вызвать метод `Train`:</span><span class="sxs-lookup"><span data-stu-id="12b06-196">Add the following as the next line of code in the `Main` method to call the `Train` method:</span></span>

[!code-csharp[Train](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Train your model")]

<span data-ttu-id="12b06-197">Метод `Train` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="12b06-197">The `Train` method executes the following tasks:</span></span>

* <span data-ttu-id="12b06-198">загрузка данных;</span><span class="sxs-lookup"><span data-stu-id="12b06-198">Loads the data.</span></span>
* <span data-ttu-id="12b06-199">извлечение и преобразование данных;</span><span class="sxs-lookup"><span data-stu-id="12b06-199">Extracts and transforms the data.</span></span>
* <span data-ttu-id="12b06-200">обучение модели;</span><span class="sxs-lookup"><span data-stu-id="12b06-200">Trains the model.</span></span>
* <span data-ttu-id="12b06-201">сохранение модели в качестве ZIP-файла;</span><span class="sxs-lookup"><span data-stu-id="12b06-201">Saves the model as .zip file.</span></span>
* <span data-ttu-id="12b06-202">возвращение модели.</span><span class="sxs-lookup"><span data-stu-id="12b06-202">Returns the model.</span></span>

<span data-ttu-id="12b06-203">Метод `Train` обучает модель.</span><span class="sxs-lookup"><span data-stu-id="12b06-203">The `Train` method trains the model.</span></span> <span data-ttu-id="12b06-204">Создайте этот метод сразу под `Main`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="12b06-204">Create that method just below `Main`, using the following code:</span></span>

```csharp
public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

<span data-ttu-id="12b06-205">Мы передаем два параметра в метод `Train`: `MLContext` для контекста (`mlContext`) и строку для пути к набору данных (`dataPath`).</span><span class="sxs-lookup"><span data-stu-id="12b06-205">We are passing two parameters into the `Train` method; an `MLContext` for the context (`mlContext`), and a string for the dataset path (`dataPath`).</span></span> <span data-ttu-id="12b06-206">Мы будем повторно использовать этот метод для загрузки наборов данных.</span><span class="sxs-lookup"><span data-stu-id="12b06-206">We're going to reuse this method for loading datasets.</span></span>

## <a name="load-and-transform-data"></a><span data-ttu-id="12b06-207">Загрузка и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="12b06-207">Load and transform data</span></span>

<span data-ttu-id="12b06-208">Мы загрузим данные с использованием глобальной переменной `_textLoader` с параметром `dataPath`.</span><span class="sxs-lookup"><span data-stu-id="12b06-208">We'll load the data using the `_textLoader` global variable with the `dataPath` parameter.</span></span> <span data-ttu-id="12b06-209">В результате возвратится <xref:Microsoft.Data.DataView.IDataView>.</span><span class="sxs-lookup"><span data-stu-id="12b06-209">It returns a <xref:Microsoft.Data.DataView.IDataView>.</span></span> <span data-ttu-id="12b06-210">Точно так же как входные и выходные данные преобразования, `IDataView` является основным типом конвейера данных, сравнимым с `IEnumerable` для `LINQ`.</span><span class="sxs-lookup"><span data-stu-id="12b06-210">As the input and output of Transforms, an `IDataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="12b06-211">В ML.NET данные аналогичны представлению SQL.</span><span class="sxs-lookup"><span data-stu-id="12b06-211">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="12b06-212">Они схематизированы, неоднородны, и к ним применено отложенное вычисление.</span><span class="sxs-lookup"><span data-stu-id="12b06-212">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="12b06-213">Объект является первой частью конвейера. Он загружает данные.</span><span class="sxs-lookup"><span data-stu-id="12b06-213">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="12b06-214">В этом руководстве он загружает набор данных со сведениями о поездке на такси, необходимыми для прогнозирования платы.</span><span class="sxs-lookup"><span data-stu-id="12b06-214">For this tutorial, it loads a dataset with taxi trip information useful to predict fares.</span></span> <span data-ttu-id="12b06-215">Это позволяет создать и обучить модель.</span><span class="sxs-lookup"><span data-stu-id="12b06-215">This is used to create the model, and train it.</span></span>

 <span data-ttu-id="12b06-216">Добавьте следующий код в первую строку метода `Train`:</span><span class="sxs-lookup"><span data-stu-id="12b06-216">Add the following code as the first line of the `Train` method:</span></span>

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "loading training dataset")]

<span data-ttu-id="12b06-217">При выполнении следующих шагов ссылки на столбцы будут задаваться по именам, определенным в классе `TaxiTrip`.</span><span class="sxs-lookup"><span data-stu-id="12b06-217">In the next steps we refer to the columns by the names defined in the `TaxiTrip` class.</span></span>

<span data-ttu-id="12b06-218">При обучении и оценке модели значения в столбце **Label** по умолчанию рассматриваются как правильные значения для прогноза.</span><span class="sxs-lookup"><span data-stu-id="12b06-218">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="12b06-219">Поскольку нам необходимо спрогнозировать плату за поездку на такси, скопируйте столбец `FareAmount` в столбец **Label**.</span><span class="sxs-lookup"><span data-stu-id="12b06-219">As we want to predict the taxi trip fare, copy the `FareAmount` column into the **Label** column.</span></span> <span data-ttu-id="12b06-220">Для этого используйте класс преобразования `CopyColumnsEstimator` и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="12b06-220">To do that, use the `CopyColumnsEstimator` transformation class, and add the following code:</span></span>

[!code-csharp[CopyColumnsEstimator](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Use the CopyColumnsEstimator")]

<span data-ttu-id="12b06-221">Алгоритм, который обучает модель, принимает **числовые** признаки, поэтому значения категориальных данных (`VendorId`, `RateCode` и `PaymentType`) нужно преобразовать в числа.</span><span class="sxs-lookup"><span data-stu-id="12b06-221">The algorithm that trains the model requires **numeric** features, so you have to transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) values into numbers.</span></span> <span data-ttu-id="12b06-222">Для этого используйте класс преобразования `OneHotEncodingEstimator`, который присваивает разные числовые значения ключа разным значениям в каждом из столбцов, и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="12b06-222">To do that, use the `OneHotEncodingEstimator` transformation class, which assigns different numeric key values to the different values in each of the columns, and add the following code:</span></span>

[!code-csharp[OneHotEncodingEstimator](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Use the OneHotEncodingEstimator")]

<span data-ttu-id="12b06-223">Последний шаг на этапе подготовки данных заключается в объединении всех столбцов признаков в столбце **Features** с помощью класса преобразования `ColumnConcatenatingEstimator`.</span><span class="sxs-lookup"><span data-stu-id="12b06-223">The last step in data preparation combines all of the feature columns into the **Features** column using the `ColumnConcatenatingEstimator` transformation class.</span></span> <span data-ttu-id="12b06-224">По умолчанию алгоритм обучения обрабатывает только признаки, представленные в столбце **Features**.</span><span class="sxs-lookup"><span data-stu-id="12b06-224">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="12b06-225">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="12b06-225">Add the following code:</span></span>

[!code-csharp[ColumnConcatenatingEstimator](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Use the ColumnConcatenatingEstimator")]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="12b06-226">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="12b06-226">Choose a learning algorithm</span></span>

<span data-ttu-id="12b06-227">После добавления данных в конвейер и их преобразования в правильный входной формат мы выбираем алгоритм обучения (**средство обучения**).</span><span class="sxs-lookup"><span data-stu-id="12b06-227">After adding the data to the pipeline and transforming it into the correct input format, we select a learning algorithm (**learner**).</span></span> <span data-ttu-id="12b06-228">Алгоритм обучения осуществляет обучение модели.</span><span class="sxs-lookup"><span data-stu-id="12b06-228">The learner trains the model.</span></span> <span data-ttu-id="12b06-229">Для решения этой проблемы мы выбрали задачу **регрессии**, поэтому мы используем алгоритм обучения `FastTreeRegressionTrainer`, который является одним из регрессионных алгоритмов обучения, предоставляемых ML.NET.</span><span class="sxs-lookup"><span data-stu-id="12b06-229">We chose a **regression** task for this problem, so we use a `FastTreeRegressionTrainer` learner, which is one of the regression learners provided by ML.NET.</span></span>

<span data-ttu-id="12b06-230">Алгоритм обучения `FastTreeRegressionTrainer` использует метод градиентного бустинга.</span><span class="sxs-lookup"><span data-stu-id="12b06-230">The `FastTreeRegressionTrainer` learner utilizes gradient boosting.</span></span> <span data-ttu-id="12b06-231">Градиентный бустинг — это метод машинного обучения для проблем регрессии.</span><span class="sxs-lookup"><span data-stu-id="12b06-231">Gradient boosting is a machine learning technique for regression problems.</span></span> <span data-ttu-id="12b06-232">Он пошагово создает каждое дерево регрессии.</span><span class="sxs-lookup"><span data-stu-id="12b06-232">It builds each regression tree in a step-wise fashion.</span></span> <span data-ttu-id="12b06-233">Он также использует предварительно определенную функцию для оценки ошибки на каждом этапе и исправления ошибок для следующего этапа.</span><span class="sxs-lookup"><span data-stu-id="12b06-233">It uses a pre-defined loss function to measure the error in each step and correct for it in the next.</span></span> <span data-ttu-id="12b06-234">Результатом является модель прогнозирования, фактически собранная из нескольких более слабых моделей прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="12b06-234">The result is a prediction model that is actually an ensemble of weaker prediction models.</span></span> <span data-ttu-id="12b06-235">Дополнительные сведения о градиентном бустинге см. в статье [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression) (Регрессия для дерева принятия решений с бустингом).</span><span class="sxs-lookup"><span data-stu-id="12b06-235">For more information about gradient boosting, see [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span></span>

<span data-ttu-id="12b06-236">Добавьте следующий код в метод `Train`, чтобы добавить `FastTreeRegressionTrainer` в код обработки данных, который вы добавили на предыдущем шаге:</span><span class="sxs-lookup"><span data-stu-id="12b06-236">Add the following code into the `Train` method to add the `FastTreeRegressionTrainer` to the data processing code added in the previous step:</span></span>

[!code-csharp[FastTreeRegressionTrainer](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Add the FastTreeRegressionTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="12b06-237">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="12b06-237">Train the model</span></span>

<span data-ttu-id="12b06-238">Последним шагом является обучение модели.</span><span class="sxs-lookup"><span data-stu-id="12b06-238">The final step is to train the model.</span></span> <span data-ttu-id="12b06-239">Обучение модели <xref:Microsoft.ML.Data.TransformerChain> выполняется по набору данных, который вы ранее загрузили и преобразовали.</span><span class="sxs-lookup"><span data-stu-id="12b06-239">We train the model, <xref:Microsoft.ML.Data.TransformerChain>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="12b06-240">После определения средства оценки мы обучаем модель с помощью <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A>, предоставляя уже загруженные данные для обучения.</span><span class="sxs-lookup"><span data-stu-id="12b06-240">Once the estimator has been defined, we train the model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="12b06-241">В результате возвращается модель, необходимая для выполнения прогнозов.</span><span class="sxs-lookup"><span data-stu-id="12b06-241">This returns a model to use for predictions.</span></span> <span data-ttu-id="12b06-242">`pipeline.Fit()` обучает конвейер и возвращает `Transformer` на основе переданного типа `DataView`.</span><span class="sxs-lookup"><span data-stu-id="12b06-242">`pipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="12b06-243">Эксперимент не выполняется, пока этот процесс не закончится.</span><span class="sxs-lookup"><span data-stu-id="12b06-243">The experiment is not executed until this happens.</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#11 "Train the model")]

<span data-ttu-id="12b06-244">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="12b06-244">And that's it!</span></span> <span data-ttu-id="12b06-245">Вы успешно обучили модель машинного обучения, которая умеет прогнозировать плату за проезд в такси в городе Нью-Йорк.</span><span class="sxs-lookup"><span data-stu-id="12b06-245">You have successfully trained a machine learning model that can predict taxi fares in NYC.</span></span> <span data-ttu-id="12b06-246">Рассмотрим, каким образом можно оценить точность модели и использовать ее для прогнозирования величины платы за поездку на такси.</span><span class="sxs-lookup"><span data-stu-id="12b06-246">Now let's take a look to understand how accurate the model is and learn how to use it to predict taxi fare values.</span></span>

### <a name="save-the-model"></a><span data-ttu-id="12b06-247">Сохранение модели</span><span class="sxs-lookup"><span data-stu-id="12b06-247">Save the model</span></span>

<span data-ttu-id="12b06-248">На этом этапе у вас есть модель типа <xref:Microsoft.ML.Data.TransformerChain>, которую можно интегрировать с любыми имеющимися или новыми приложениями .NET.</span><span class="sxs-lookup"><span data-stu-id="12b06-248">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="12b06-249">Чтобы сохранить модель в ZIP-файл, добавьте следующий код в конец метода `Train`:</span><span class="sxs-lookup"><span data-stu-id="12b06-249">To save the model to a .zip file, add the following code at the end of the `Train` method:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Save the model as a .zip file and return the model")]

## <a name="save-the-model-as-a-zip-file"></a><span data-ttu-id="12b06-250">Сохранение модели в качестве ZIP-файла</span><span class="sxs-lookup"><span data-stu-id="12b06-250">Save the model as a .zip file</span></span>

<span data-ttu-id="12b06-251">Создайте метод `SaveModelAsFile` сразу после метода `Train`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="12b06-251">Create the `SaveModelAsFile` method, just after the `Train` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="12b06-252">Метод `SaveModelAsFile` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="12b06-252">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="12b06-253">сохранение модели в качестве ZIP-файла.</span><span class="sxs-lookup"><span data-stu-id="12b06-253">Saves the model as a .zip file.</span></span>

<span data-ttu-id="12b06-254">Нам нужно создать метод для сохранения модели, чтобы ее можно было использовать повторно, а также применять в других приложениях.</span><span class="sxs-lookup"><span data-stu-id="12b06-254">We need to create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="12b06-255">`ITransformer` содержит метод <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)>, который принимает глобальное поле `_modelPath`, и <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="12b06-255">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="12b06-256">Так как нам необходимо сохранить модель в качестве ZIP-файла, мы создадим `FileStream` непосредственно перед вызовом метода `SaveTo`.</span><span class="sxs-lookup"><span data-stu-id="12b06-256">Since we want to save this as a zip file, we'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="12b06-257">В качестве следующей строки в методе `SaveModelAsFile` добавьте приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="12b06-257">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Add the SaveTo Method")]

<span data-ttu-id="12b06-258">Мы также можем показать, куда был записан файл, написав консольное сообщение с `_modelPath`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="12b06-258">We could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="evaluate-the-model"></a><span data-ttu-id="12b06-259">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="12b06-259">Evaluate the model</span></span>

<span data-ttu-id="12b06-260">Оценка — это процесс проверки того, насколько хорошо модель позволяет спрогнозировать значения метки.</span><span class="sxs-lookup"><span data-stu-id="12b06-260">Evaluation is the process of checking how well the model predicts label values.</span></span> <span data-ttu-id="12b06-261">Важно, чтобы модель возвращала хорошие прогнозы по данным, которые не использовались для ее обучения.</span><span class="sxs-lookup"><span data-stu-id="12b06-261">It's important that the model makes good predictions on data that was not used to train the model.</span></span> <span data-ttu-id="12b06-262">Для такой оценки можно, например, разделить данные на обучающий и тестовый наборы данных, как вы и сделали в рамках этого руководства.</span><span class="sxs-lookup"><span data-stu-id="12b06-262">One way to do this is to split the data into training and test data sets, as it's done in this tutorial.</span></span> <span data-ttu-id="12b06-263">Теперь, когда вы завершили обучение модели по обучающему набору данных, вы можете проверить ее работу по тестовым данным.</span><span class="sxs-lookup"><span data-stu-id="12b06-263">Now that you've trained the model on the training data, you can see how well it performs on the test data.</span></span>

<span data-ttu-id="12b06-264">Метод `Evaluate` осуществляет оценку модели.</span><span class="sxs-lookup"><span data-stu-id="12b06-264">The `Evaluate` method evaluates the model.</span></span> <span data-ttu-id="12b06-265">Чтобы создать этот метод, добавьте следующий код под методом `Train`:</span><span class="sxs-lookup"><span data-stu-id="12b06-265">To create that method, add the following code below the `Train` method:</span></span>

```csharp
private static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```
<span data-ttu-id="12b06-266">Метод `Evaluate` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="12b06-266">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="12b06-267">загрузка тестового набора данных;</span><span class="sxs-lookup"><span data-stu-id="12b06-267">Loads the test dataset.</span></span>
* <span data-ttu-id="12b06-268">создание средства оценки регрессии;</span><span class="sxs-lookup"><span data-stu-id="12b06-268">Creates the regression evaluator.</span></span>
* <span data-ttu-id="12b06-269">оценка модели и создание метрик;</span><span class="sxs-lookup"><span data-stu-id="12b06-269">Evaluates the model and creates metrics.</span></span>
* <span data-ttu-id="12b06-270">отображение метрик.</span><span class="sxs-lookup"><span data-stu-id="12b06-270">Displays the metrics.</span></span>

<span data-ttu-id="12b06-271">Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `Train`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="12b06-271">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Call the Evaluate method")]

<span data-ttu-id="12b06-272">Мы загрузим тестовый набор данных с использованием ранее инициализированной глобальной переменной `_textLoader` с глобальным полем `_testDataPath`.</span><span class="sxs-lookup"><span data-stu-id="12b06-272">We'll load the test dataset using the previously initialized  `_textLoader` global variable with the `_testDataPath` global field.</span></span> <span data-ttu-id="12b06-273">С помощью этого набора данных вы можете оценить модели для проверки ее качества.</span><span class="sxs-lookup"><span data-stu-id="12b06-273">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="12b06-274">Добавьте следующий код в метод `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="12b06-274">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Load the test dataset")]

<span data-ttu-id="12b06-275">Затем мы будем использовать параметр машинного обучения `model` (преобразователь) для ввода признаков и возврата прогнозов.</span><span class="sxs-lookup"><span data-stu-id="12b06-275">Next, we'll use the machine learning `model` parameter (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="12b06-276">В качестве следующей строки в методе `Evaluate` добавьте приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="12b06-276">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Predict using the Transformer")]

<span data-ttu-id="12b06-277">Метод `RegressionContext.Evaluate` вычисляет метрики качества для `PredictionModel` на основе указанного набора данных.</span><span class="sxs-lookup"><span data-stu-id="12b06-277">The `RegressionContext.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="12b06-278">Возвращает объект <xref:Microsoft.ML.Data.RegressionMetrics>, который содержит общие метрики, вычисляемые с помощью средств оценки регрессии.</span><span class="sxs-lookup"><span data-stu-id="12b06-278">It returns a <xref:Microsoft.ML.Data.RegressionMetrics> object that contains the overall metrics computed by regression evaluators.</span></span> <span data-ttu-id="12b06-279">Чтобы отобразить их для оценки качества модели, сначала метрики необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="12b06-279">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="12b06-280">Добавьте в следующую строку метода `Evaluate` приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="12b06-280">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Compute Metrics")]

<span data-ttu-id="12b06-281">Добавьте следующий код, чтобы оценить модель и создать для нее метрики оценки:</span><span class="sxs-lookup"><span data-stu-id="12b06-281">Add the following code to evaluate the model and produce the evaluation metrics:</span></span>

```csharp
Console.WriteLine();
Console.WriteLine($"*************************************************");
Console.WriteLine($"*       Model quality metrics evaluation         ");
Console.WriteLine($"*------------------------------------------------");
```

<span data-ttu-id="12b06-282">Также в качестве метрики для оценки регрессионных моделей используется [коэффициент детерминации](../resources/glossary.md#coefficient-of-determination).</span><span class="sxs-lookup"><span data-stu-id="12b06-282">[RSquared](../resources/glossary.md#coefficient-of-determination) is another evaluation metric of the regression models.</span></span> <span data-ttu-id="12b06-283">Коэффициент детерминации может иметь значения в диапазоне от 0 до 1.</span><span class="sxs-lookup"><span data-stu-id="12b06-283">RSquared takes values between 0 and 1.</span></span> <span data-ttu-id="12b06-284">Чем ближе его значение к 1, тем лучше модель.</span><span class="sxs-lookup"><span data-stu-id="12b06-284">The closer its value is to 1, the better the model is.</span></span> <span data-ttu-id="12b06-285">Чтобы отображать значение коэффициента детерминации, добавьте следующий код в метод `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="12b06-285">Add the following code into the `Evaluate` method to display the RSquared value:</span></span>

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#18 "Display the RSquared metric.")]

<span data-ttu-id="12b06-286">[Среднеквадратичное отклонение](../resources/glossary.md##root-of-mean-squared-error-rmse) является одной из метрик, используемых для оценки регрессионной модели.</span><span class="sxs-lookup"><span data-stu-id="12b06-286">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) is one of the evaluation metrics of the regression model.</span></span> <span data-ttu-id="12b06-287">Чем ниже это отклонение, тем лучше модель.</span><span class="sxs-lookup"><span data-stu-id="12b06-287">The lower it is, the better the model is.</span></span> <span data-ttu-id="12b06-288">Чтобы отображать значение среднеквадратичного отклонения, добавьте следующий код в метод `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="12b06-288">Add the following code into the `Evaluate` method to display the RMS value:</span></span>

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#19 "Display the RMS metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="12b06-289">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="12b06-289">Use the model for predictions</span></span>


## <a name="predict-the-test-data-outcome-with-the-model-and-a-single-comment"></a><span data-ttu-id="12b06-290">Прогнозирование результатов тестовых данных с помощью модели и одного комментария</span><span class="sxs-lookup"><span data-stu-id="12b06-290">Predict the test data outcome with the model and a single comment</span></span>

<span data-ttu-id="12b06-291">Создайте метод `TestSinglePrediction` сразу после метода `Evaluate`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="12b06-291">Create the `TestSinglePrediction` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void TestSinglePrediction(MLContext mlContext)
{

}
```

<span data-ttu-id="12b06-292">Метод `TestSinglePrediction` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="12b06-292">The `TestSinglePrediction` method executes the following tasks:</span></span>

* <span data-ttu-id="12b06-293">создание отдельного комментария тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="12b06-293">Creates a single comment of test data.</span></span>
* <span data-ttu-id="12b06-294">прогнозирование суммы оплаты на основе тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="12b06-294">Predicts fare amount based on test data.</span></span>
* <span data-ttu-id="12b06-295">объединение тестовых данных и прогнозов для создания отчетов;</span><span class="sxs-lookup"><span data-stu-id="12b06-295">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="12b06-296">отображение результатов прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="12b06-296">Displays the predicted results.</span></span>

<span data-ttu-id="12b06-297">Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `Evaluate`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="12b06-297">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallTestSinglePrediction](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#20 "Call the TestSinglePrediction method")]

<span data-ttu-id="12b06-298">Так как нам необходимо загрузить модель из сохраненного ZIP-файла, мы создадим `FileStream` непосредственно перед вызовом метода `Load`.</span><span class="sxs-lookup"><span data-stu-id="12b06-298">Since we want to load the model from the zip file we saved, we'll create the `FileStream` immediately before calling the `Load` method.</span></span> <span data-ttu-id="12b06-299">В качестве следующей строки в методе `TestSinglePrediction` добавьте приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="12b06-299">Add the following code to the `TestSinglePrediction` method as the next line:</span></span>

[!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#21 "Load the model")]

<span data-ttu-id="12b06-300">Несмотря на то что `model` представляет собой `transformer`, который обрабатывает многочисленные строки данных, достаточно распространенным сценарием рабочей среды является прогнозирование на основе отдельных примеров.</span><span class="sxs-lookup"><span data-stu-id="12b06-300">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="12b06-301"><xref:Microsoft.ML.PredictionEngine%602> — это программа-оболочка, возвращаемая из метода `CreatePredictionEngine`.</span><span class="sxs-lookup"><span data-stu-id="12b06-301">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="12b06-302">Давайте добавим в следующей строке метода `TestSinglePrediction` указанный ниже код для создания `PredictionEngine`:</span><span class="sxs-lookup"><span data-stu-id="12b06-302">Let's add the following code to create the `PredictionEngine` as the next line in the `TestSinglePrediction` Method:</span></span>

[!code-csharp[MakePredictionEngine](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#22 "Create the PredictionFunction")]
  
<span data-ttu-id="12b06-303">Для этого руководства в этом классе используется один тестовый проход.</span><span class="sxs-lookup"><span data-stu-id="12b06-303">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="12b06-304">Позже можно добавить другие сценарии и поэкспериментировать с этой моделью.</span><span class="sxs-lookup"><span data-stu-id="12b06-304">Later you can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="12b06-305">Добавьте поездку для проверки прогнозирования стоимости обученной моделью с помощью метода `TestSinglePrediction`, создав экземпляр `TaxiTrip`:</span><span class="sxs-lookup"><span data-stu-id="12b06-305">Add a trip to test the trained model's prediction of cost in the `TestSinglePrediction` method by creating an instance of `TaxiTrip`:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#23 "Create test data for single prediction")]

 <span data-ttu-id="12b06-306">Мы можем использовать это для прогнозирования платы на основе одного экземпляра данных поездки на такси.</span><span class="sxs-lookup"><span data-stu-id="12b06-306">We can use that to predict the fare based on a single instance of the taxi trip data.</span></span> <span data-ttu-id="12b06-307">Чтобы получить прогноз, примените <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> для данных.</span><span class="sxs-lookup"><span data-stu-id="12b06-307">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="12b06-308">Обратите внимание, что входные данные имеют строковый формат, а модель выполняет присвоение признаков.</span><span class="sxs-lookup"><span data-stu-id="12b06-308">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="12b06-309">Конвейер синхронизируется во время обучения и прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="12b06-309">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="12b06-310">Вам не нужно писать для прогнозирования отдельный код предварительной обработки и присвоения признаков. Кроме того, этот API выполняет как пакетное, так и разовое прогнозирование.</span><span class="sxs-lookup"><span data-stu-id="12b06-310">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#24 "Create a prediction of taxi fare")]

<span data-ttu-id="12b06-311">Чтобы отобразить прогнозируемую плату за указанную поездку, добавьте в метод `TestSinglePrediction` следующий код:</span><span class="sxs-lookup"><span data-stu-id="12b06-311">To display the predicted fare of the specified trip, add the following code into the `TestSinglePrediction` method:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#25 "Display the prediction.")]

<span data-ttu-id="12b06-312">Запустите программу, чтобы узнать прогноз платы за такси для тестового примера.</span><span class="sxs-lookup"><span data-stu-id="12b06-312">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="12b06-313">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="12b06-313">Congratulations!</span></span> <span data-ttu-id="12b06-314">Вы успешно создали модель машинного обучения для прогнозирования платы за проезд в такси, оценили ее точность и использовали ее для получения прогнозов.</span><span class="sxs-lookup"><span data-stu-id="12b06-314">You've now successfully built a machine learning model for predicting taxi trip fares, evaluated its accuracy, and used it to make predictions.</span></span> <span data-ttu-id="12b06-315">Исходный код для этого руководства можно найти в репозитории GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).</span><span class="sxs-lookup"><span data-stu-id="12b06-315">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="12b06-316">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="12b06-316">Next steps</span></span>

<span data-ttu-id="12b06-317">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="12b06-317">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="12b06-318">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="12b06-318">Understand the problem</span></span>
> * <span data-ttu-id="12b06-319">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="12b06-319">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="12b06-320">Подготовка и анализ данных</span><span class="sxs-lookup"><span data-stu-id="12b06-320">Prepare and understand the data</span></span>
> * <span data-ttu-id="12b06-321">Создание конвейера обучения</span><span class="sxs-lookup"><span data-stu-id="12b06-321">Create a learning pipeline</span></span>
> * <span data-ttu-id="12b06-322">Загрузка и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="12b06-322">Load and transform the data</span></span>
> * <span data-ttu-id="12b06-323">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="12b06-323">Choose a learning algorithm</span></span>
> * <span data-ttu-id="12b06-324">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="12b06-324">Train the model</span></span>
> * <span data-ttu-id="12b06-325">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="12b06-325">Evaluate the model</span></span>
> * <span data-ttu-id="12b06-326">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="12b06-326">Use the model for predictions</span></span>

<span data-ttu-id="12b06-327">Переходите к следующему руководству.</span><span class="sxs-lookup"><span data-stu-id="12b06-327">Advance to the next tutorial to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="12b06-328">Кластеризация ирисов Фишера</span><span class="sxs-lookup"><span data-stu-id="12b06-328">Iris clustering</span></span>](iris-clustering.md)
