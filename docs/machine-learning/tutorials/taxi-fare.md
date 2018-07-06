---
title: Использование ML.NET для прогнозирования платы за проезд в такси в Нью-Йорке (регрессия)
description: Сведения об использовании ML.NET в сценарии с моделью регрессии.
author: aditidugar
ms.author: johalex
ms.date: 06/18/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 9706dad0a8e32651496e0404be4501c2c70e9d75
ms.sourcegitcommit: ed7b4b9b77d35e94a35a2634e8c874f46603fb2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36948635"
---
# <a name="tutorial-use-mlnet-to-predict-new-york-taxi-fares-regression"></a><span data-ttu-id="f26d0-103">Руководство. Использование ML.NET для прогнозирования платы за проезд в такси в Нью-Йорке (регрессия)</span><span class="sxs-lookup"><span data-stu-id="f26d0-103">Tutorial: Use ML.NET to predict New York taxi fares (regression)</span></span>

> [!NOTE]
> <span data-ttu-id="f26d0-104">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="f26d0-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="f26d0-105">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="f26d0-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="f26d0-106">В этом руководства описано, как с помощью ML.NET создать [модель регрессии](../resources/glossary.md#regression) для прогнозирования платы за проезд в такси в городе Нью-Йорк.</span><span class="sxs-lookup"><span data-stu-id="f26d0-106">This tutorial illustrates how to use ML.NET to build a [regression model](../resources/glossary.md#regression) for predicting New York City taxi fares.</span></span>

<span data-ttu-id="f26d0-107">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="f26d0-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="f26d0-108">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="f26d0-108">Understand the problem</span></span>
> * <span data-ttu-id="f26d0-109">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="f26d0-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="f26d0-110">Подготовка и анализ данных</span><span class="sxs-lookup"><span data-stu-id="f26d0-110">Prepare and understand the data</span></span>
> * <span data-ttu-id="f26d0-111">Создание конвейера обучения</span><span class="sxs-lookup"><span data-stu-id="f26d0-111">Create a learning pipeline</span></span>
> * <span data-ttu-id="f26d0-112">Загрузка и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="f26d0-112">Load and transform the data</span></span>
> * <span data-ttu-id="f26d0-113">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="f26d0-113">Choose a learning algorithm</span></span>
> * <span data-ttu-id="f26d0-114">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="f26d0-114">Train the model</span></span>
> * <span data-ttu-id="f26d0-115">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="f26d0-115">Evaluate the model</span></span>
> * <span data-ttu-id="f26d0-116">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="f26d0-116">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f26d0-117">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f26d0-117">Prerequisites</span></span>

* <span data-ttu-id="f26d0-118">[Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="f26d0-118">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="f26d0-119">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="f26d0-119">Understand the problem</span></span>

<span data-ttu-id="f26d0-120">Рассматриваемая проблема основана на сценарии **прогнозирования платы за поездку на такси в городе Нью-Йорк**.</span><span class="sxs-lookup"><span data-stu-id="f26d0-120">This problem is centered around **predicting the fare of a taxi trip in New York City**.</span></span> <span data-ttu-id="f26d0-121">На первый взгляд может показаться, что плата зависит только от расстояния.</span><span class="sxs-lookup"><span data-stu-id="f26d0-121">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="f26d0-122">Но службы такси в Нью-Йорке изменяют плату с учетом еще нескольких факторов, таких как наличие дополнительных пассажиров или оплата кредитной картой вместо наличных.</span><span class="sxs-lookup"><span data-stu-id="f26d0-122">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="f26d0-123">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="f26d0-123">Select the appropriate machine learning task</span></span>

<span data-ttu-id="f26d0-124">Для прогнозирования платы за проезд в такси прежде всего нужно выбрать правильную задачу машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="f26d0-124">To predict the taxi fare, you first select the appropriate machine learning task.</span></span> <span data-ttu-id="f26d0-125">Вам нужно спрогнозировать реальное значение (значение цены в формате двойной точности) на основе других факторов в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="f26d0-125">You are looking to predict a real value (a double that represents price) based on the other factors in the dataset.</span></span> <span data-ttu-id="f26d0-126">Для этого выберите задачу [**регрессии**](../resources/glossary.md#regression).</span><span class="sxs-lookup"><span data-stu-id="f26d0-126">You choose a [**regression**](../resources/glossary.md#regression) task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="f26d0-127">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="f26d0-127">Create a console application</span></span>

1. <span data-ttu-id="f26d0-128">Откройте Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="f26d0-128">Open Visual Studio 2017.</span></span> <span data-ttu-id="f26d0-129">Выберите **Файл** > **Создать** > **Проект** в меню.</span><span class="sxs-lookup"><span data-stu-id="f26d0-129">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="f26d0-130">В диалоговом окне **Новый проект** выберите узел **Visual C#**, а затем — узел **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="f26d0-130">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="f26d0-131">Выберите шаблон проекта **Консольное приложение (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="f26d0-131">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="f26d0-132">В текстовое поле **Имя** введите TaxiFarePrediction, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f26d0-132">In the **Name** text box, type "TaxiFarePrediction" and then select the **OK** button.</span></span>

2. <span data-ttu-id="f26d0-133">Создайте каталог с именем *Data* в папке проекта, чтобы сохранить в нем файлы с наборами данных:</span><span class="sxs-lookup"><span data-stu-id="f26d0-133">Create a directory named *Data* in your project to save the data set files:</span></span>

    <span data-ttu-id="f26d0-134">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="f26d0-134">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="f26d0-135">Введите имя папки Data и нажмите клавишу "ВВОД".</span><span class="sxs-lookup"><span data-stu-id="f26d0-135">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="f26d0-136">Установите **пакет NuGet для Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="f26d0-136">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="f26d0-137">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="f26d0-137">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="f26d0-138">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку **Обзор**, выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="f26d0-138">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="f26d0-139">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="f26d0-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="f26d0-140">Подготовка и анализ данных</span><span class="sxs-lookup"><span data-stu-id="f26d0-140">Prepare and understand the data</span></span>

1. <span data-ttu-id="f26d0-141">Скачайте наборы данных [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) и [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv), сохранив их в созданной на предыдущем шаге папке *Data*.</span><span class="sxs-lookup"><span data-stu-id="f26d0-141">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="f26d0-142">Эти наборы данных используются для обучения модели машинного обучения и последующей оценки точности этой модели.</span><span class="sxs-lookup"><span data-stu-id="f26d0-142">We use these data sets to train the machine learning model and then evaluate how accurate the model is.</span></span> <span data-ttu-id="f26d0-143">Эти наборы данных взяты из [наборов данных NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span><span class="sxs-lookup"><span data-stu-id="f26d0-143">These data sets are originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

2. <span data-ttu-id="f26d0-144">В **обозревателе решений** щелкните правой кнопкой мыши каждый из файлов \*.csv и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f26d0-144">In **Solution Explorer**, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="f26d0-145">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Всегда**.</span><span class="sxs-lookup"><span data-stu-id="f26d0-145">Under **Advanced**, change the value of **Copy to Output Directory** to **Always**.</span></span>

3. <span data-ttu-id="f26d0-146">Откройте набор данных **taxi-fare-train.csv** и просмотрите заголовки столбцов в первой строке.</span><span class="sxs-lookup"><span data-stu-id="f26d0-146">Open the **taxi-fare-train.csv** data set and look at column headers in the first row.</span></span> <span data-ttu-id="f26d0-147">Теперь изучите каждый из столбцов.</span><span class="sxs-lookup"><span data-stu-id="f26d0-147">Take a look at each of the columns.</span></span> <span data-ttu-id="f26d0-148">Разберитесь, какие данные в них хранятся, и определите, какие столбцы являются **признаками**, а в каком содержится **метка**.</span><span class="sxs-lookup"><span data-stu-id="f26d0-148">Understand the data and decide which columns are **features** and which one is the **label**.</span></span>

<span data-ttu-id="f26d0-149">**Метка** — это столбец, значения в котором вы хотите спрогнозировать.</span><span class="sxs-lookup"><span data-stu-id="f26d0-149">The **label** is the identifier of the column you want to predict.</span></span> <span data-ttu-id="f26d0-150">Выбранные **признаки** используются для прогнозирования метки.</span><span class="sxs-lookup"><span data-stu-id="f26d0-150">The identified **features** are used to predict the label.</span></span>

<span data-ttu-id="f26d0-151">Предоставленный набор данных содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="f26d0-151">The provided data set contains the following columns:</span></span>

* <span data-ttu-id="f26d0-152">**vendor_id:** идентификатор поставщика такси — это признак.</span><span class="sxs-lookup"><span data-stu-id="f26d0-152">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="f26d0-153">**rate_code:** тип оплаты для поездки на такси — это признак.</span><span class="sxs-lookup"><span data-stu-id="f26d0-153">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="f26d0-154">**passenger_count:** число пассажиров в поездке — это признак.</span><span class="sxs-lookup"><span data-stu-id="f26d0-154">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="f26d0-155">**trip_time_in_secs:** время, затраченное на поездку.</span><span class="sxs-lookup"><span data-stu-id="f26d0-155">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="f26d0-156">Вам требуется спрогнозировать плату за одну поездку до того, как поездка будет завершена.</span><span class="sxs-lookup"><span data-stu-id="f26d0-156">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="f26d0-157">На этот момент вам неизвестна продолжительность поездки.</span><span class="sxs-lookup"><span data-stu-id="f26d0-157">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="f26d0-158">Таким образом, продолжительность поездки не является признаком и соответствующий столбец следует исключить из модели.</span><span class="sxs-lookup"><span data-stu-id="f26d0-158">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
* <span data-ttu-id="f26d0-159">**trip_distance:** расстояние поездки — это признак.</span><span class="sxs-lookup"><span data-stu-id="f26d0-159">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="f26d0-160">**payment_type:** метод оплаты (наличные или кредитная карта) — это признак.</span><span class="sxs-lookup"><span data-stu-id="f26d0-160">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="f26d0-161">**fare_amount:** общая сумма, оплаченная за поездку на такси — это метка.</span><span class="sxs-lookup"><span data-stu-id="f26d0-161">**fare_amount:** The total taxi fare paid is the label.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="f26d0-162">Создание классов данных</span><span class="sxs-lookup"><span data-stu-id="f26d0-162">Create data classes</span></span>

<span data-ttu-id="f26d0-163">Создайте классы для входных данных и прогнозов:</span><span class="sxs-lookup"><span data-stu-id="f26d0-163">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="f26d0-164">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="f26d0-164">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="f26d0-165">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *TaxiTrip.cs*.</span><span class="sxs-lookup"><span data-stu-id="f26d0-165">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="f26d0-166">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="f26d0-166">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="f26d0-167">Добавьте следующие директивы `using` в новый файл.</span><span class="sxs-lookup"><span data-stu-id="f26d0-167">Add the following `using` directives to the new file:</span></span>

   [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="f26d0-168">Удалите из файла *TaxiTrip.cs* существующее определение класса и добавьте следующий код с двумя классами `TaxiTrip` и `TaxiTripFarePrediction`:</span><span class="sxs-lookup"><span data-stu-id="f26d0-168">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="f26d0-169">Класс `TaxiTrip` содержит входные данные и определения для каждого из столбцов в этом наборе данных.</span><span class="sxs-lookup"><span data-stu-id="f26d0-169">`TaxiTrip` is the input data class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="f26d0-170">Используйте атрибут [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute), чтобы указать индексы исходных столбцов в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="f26d0-170">Use the [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) attribute to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="f26d0-171">Класс `TaxiTripFarePrediction` представляет прогнозируемые результаты.</span><span class="sxs-lookup"><span data-stu-id="f26d0-171">The `TaxiTripFarePrediction` class is used to represent predicted results.</span></span> <span data-ttu-id="f26d0-172">Он имеет одно поле типа float (`FareAmount`), к которому применен атрибут `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="f26d0-172">It has a single float (`FareAmount`) field with a `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) attribute applied.</span></span> <span data-ttu-id="f26d0-173">Столбец **Score** в ML.NET играет особую роль.</span><span class="sxs-lookup"><span data-stu-id="f26d0-173">The **Score** column is the special column in ML.NET.</span></span> <span data-ttu-id="f26d0-174">В него записываются прогнозируемые значения, получаемые моделью.</span><span class="sxs-lookup"><span data-stu-id="f26d0-174">The model outputs predicted values into that column.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="f26d0-175">Определение путей к данным и модели</span><span class="sxs-lookup"><span data-stu-id="f26d0-175">Define data and model paths</span></span>

<span data-ttu-id="f26d0-176">Вернитесь к файлу *Program.cs* и добавьте три поля, которые будут содержать пути к файлам с наборами данных и к файлу для сохранения модели.</span><span class="sxs-lookup"><span data-stu-id="f26d0-176">Go back to the *Program.cs* file and add three fields to hold the paths to the files with data sets and the file to save the model:</span></span>

* <span data-ttu-id="f26d0-177">`_datapath` содержит путь к файлу с набором данных, используемым для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="f26d0-177">`_datapath` contains the path to the file with the data set used to train the model.</span></span>
* <span data-ttu-id="f26d0-178">`_testdatapath` содержит путь к файлу с набором данных, используемым для оценки модели.</span><span class="sxs-lookup"><span data-stu-id="f26d0-178">`_testdatapath` contains the path to the file with the data set used to evaluate the model.</span></span>
* <span data-ttu-id="f26d0-179">`_modelpath` содержит путь к файлу для сохранения обучаемой модели.</span><span class="sxs-lookup"><span data-stu-id="f26d0-179">`_modelpath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="f26d0-180">Добавьте прямо перед методом `Main` следующий код, чтобы указать эти пути.</span><span class="sxs-lookup"><span data-stu-id="f26d0-180">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="f26d0-181">Чтобы этот код компилировался, добавьте следующие директивы `using` вверху файла *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="f26d0-181">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsingsForPaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Using statements for path definitions")]

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="f26d0-182">Создание конвейера обучения</span><span class="sxs-lookup"><span data-stu-id="f26d0-182">Create a learning pipeline</span></span>

<span data-ttu-id="f26d0-183">Добавьте дополнительные директивы `using` в начало файла *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="f26d0-183">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="f26d0-184">В `Main` замените `Console.WriteLine("Hello World!")` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="f26d0-184">In `Main`, replace the `Console.WriteLine("Hello World!")` with the following code:</span></span>

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

<span data-ttu-id="f26d0-185">Метод `Train` обучает модель.</span><span class="sxs-lookup"><span data-stu-id="f26d0-185">The `Train` method trains the model.</span></span> <span data-ttu-id="f26d0-186">Создайте этот метод сразу под `Main`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="f26d0-186">Create that method just below `Main`, using the following code:</span></span>

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

<span data-ttu-id="f26d0-187">Конвейер обучения загружает все данные и алгоритмы, необходимые для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="f26d0-187">The learning pipeline loads all of the data and algorithms necessary to train the model.</span></span> <span data-ttu-id="f26d0-188">Добавьте в метод `Train` следующий код:</span><span class="sxs-lookup"><span data-stu-id="f26d0-188">Add the following code into the `Train` method:</span></span>

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-data"></a><span data-ttu-id="f26d0-189">Загрузка и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="f26d0-189">Load and transform data</span></span>

<span data-ttu-id="f26d0-190">На первом этапе конвейера обучения выполняется загрузка данных из набора данных для обучения.</span><span class="sxs-lookup"><span data-stu-id="f26d0-190">The first step that the learning pipeline performs is loading data from the training data set.</span></span> <span data-ttu-id="f26d0-191">В нашем случае набор данных для обучения хранится в текстовом файле, путь к которому задан в поле `_datapath`.</span><span class="sxs-lookup"><span data-stu-id="f26d0-191">In our case, training data set is stored in the text file with a path defined by the `_datapath` field.</span></span> <span data-ttu-id="f26d0-192">Этот файл содержит заголовок с именами столбцов, поэтому при загрузке данных первую строку следует игнорировать.</span><span class="sxs-lookup"><span data-stu-id="f26d0-192">That file contains the header with the column names, so the first row should be ignored while loading data.</span></span> <span data-ttu-id="f26d0-193">Для разделения столбцов в этом файле используется запятая (",").</span><span class="sxs-lookup"><span data-stu-id="f26d0-193">Columns in the file are separated by the comma (",").</span></span> <span data-ttu-id="f26d0-194">Добавьте в метод `Train` следующий код:</span><span class="sxs-lookup"><span data-stu-id="f26d0-194">Add the following code into the `Train` method:</span></span>

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(useHeader: true, separator: ','));
```

<span data-ttu-id="f26d0-195">При выполнении следующих шагов ссылки на столбцы будут задаваться по именам, определенным в классе `TaxiTrip`.</span><span class="sxs-lookup"><span data-stu-id="f26d0-195">In the next steps we refer to the columns by the names defined in the `TaxiTrip` class.</span></span>

<span data-ttu-id="f26d0-196">При обучении и оценке модели значения в столбце **Label** рассматриваются как правильные значения для прогноза.</span><span class="sxs-lookup"><span data-stu-id="f26d0-196">When the model is trained and evaluated, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="f26d0-197">Поскольку нам необходимо спрогнозировать плату за поездку на такси, скопируйте столбец `FareAmount` в столбец **Label**.</span><span class="sxs-lookup"><span data-stu-id="f26d0-197">As we want to predict the taxi trip fare, copy the `FareAmount` column into the **Label** column.</span></span> <span data-ttu-id="f26d0-198">Для этого откройте файл <xref:Microsoft.ML.Transforms.ColumnCopier> и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="f26d0-198">To do that, use <xref:Microsoft.ML.Transforms.ColumnCopier> and add the following code:</span></span>

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

<span data-ttu-id="f26d0-199">Алгоритм, который обучает модель, принимает **числовые** признаки, поэтому значения категориальных данных (`VendorId`, `RateCode` и `PaymentType`) нужно преобразовать в числа.</span><span class="sxs-lookup"><span data-stu-id="f26d0-199">The algorithm that trains the model requires **numeric** features, so you have to transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) values into numbers.</span></span> <span data-ttu-id="f26d0-200">Для этого используйте <xref:Microsoft.ML.Transforms.CategoricalOneHotVectorizer>, который присваивает разные числовые значения ключа разным значениям в каждом из столбцов, и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="f26d0-200">To do that, use <xref:Microsoft.ML.Transforms.CategoricalOneHotVectorizer>, which assigns different numeric key values to the different values in each of the columns, and add the following code:</span></span>

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

<span data-ttu-id="f26d0-201">Последний шаг на этапе подготовки данных заключается в объединении всех столбцов признаков в столбце **Features** с помощью класса преобразования <xref:Microsoft.ML.Transforms.ColumnConcatenator>.</span><span class="sxs-lookup"><span data-stu-id="f26d0-201">The last step in data preparation combines all of the feature columns into the **Features** column using the <xref:Microsoft.ML.Transforms.ColumnConcatenator> transformation class.</span></span> <span data-ttu-id="f26d0-202">Этот шаг необходим, поскольку алгоритм обучения обрабатывает только признаки, представленные в столбце **Features**.</span><span class="sxs-lookup"><span data-stu-id="f26d0-202">This step is necessary as a learner processes only features from the **Features** column.</span></span> <span data-ttu-id="f26d0-203">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="f26d0-203">Add the following code:</span></span>

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

<span data-ttu-id="f26d0-204">Обратите внимание, что не включается столбец `TripTime`, который соответствует столбцу `trip_time_in_secs` в файле набора данных.</span><span class="sxs-lookup"><span data-stu-id="f26d0-204">Notice that the `TripTime` column, which corresponds to the `trip_time_in_secs` column in the data set file, isn't included.</span></span> <span data-ttu-id="f26d0-205">Вы уже определили, что он не будет полезным признаком для прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="f26d0-205">You already determined that it isn't a useful prediction feature.</span></span>

> [!NOTE]
> <span data-ttu-id="f26d0-206">Для успешного выполнения шагов их следует добавлять в конвейер в том порядке, который указан выше.</span><span class="sxs-lookup"><span data-stu-id="f26d0-206">These steps must be added to the pipeline in the order specified above for successful execution.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="f26d0-207">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="f26d0-207">Choose a learning algorithm</span></span>

<span data-ttu-id="f26d0-208">После добавления данных в конвейер и их преобразования в правильный входной формат выберите алгоритм обучения (**средство обучения**).</span><span class="sxs-lookup"><span data-stu-id="f26d0-208">After adding the data to the pipeline and transforming it into the correct input format, you select a learning algorithm (**learner**).</span></span> <span data-ttu-id="f26d0-209">Алгоритм обучения осуществляет обучение модели.</span><span class="sxs-lookup"><span data-stu-id="f26d0-209">The learner trains the model.</span></span> <span data-ttu-id="f26d0-210">Для решения этой проблемы вы выбрали **задачу регрессии**, поэтому был добавлен алгоритм обучения <xref:Microsoft.ML.Trainers.FastTreeRegressor>, который является одним из регрессионных алгоритмов обучения, предоставляемых ML.NET.</span><span class="sxs-lookup"><span data-stu-id="f26d0-210">You chose a **regression task** for this problem, so you add a <xref:Microsoft.ML.Trainers.FastTreeRegressor> learner, which is one of the regression learners provided by ML.NET.</span></span>

<span data-ttu-id="f26d0-211">Алгоритм обучения <xref:Microsoft.ML.Trainers.FastTreeRegressor> использует метод градиентного бустинга.</span><span class="sxs-lookup"><span data-stu-id="f26d0-211"><xref:Microsoft.ML.Trainers.FastTreeRegressor> learner utilizes gradient boosting.</span></span> <span data-ttu-id="f26d0-212">Градиентный бустинг — это метод машинного обучения для проблем регрессии.</span><span class="sxs-lookup"><span data-stu-id="f26d0-212">Gradient boosting is a machine learning technique for regression problems.</span></span> <span data-ttu-id="f26d0-213">Он пошагово создает каждое дерево регрессии.</span><span class="sxs-lookup"><span data-stu-id="f26d0-213">It builds each regression tree in a step-wise fashion.</span></span> <span data-ttu-id="f26d0-214">Он также использует предварительно определенную функцию для оценки ошибки на каждом этапе и исправления ошибок для следующего этапа.</span><span class="sxs-lookup"><span data-stu-id="f26d0-214">It uses a pre-defined loss function to measure the error in each step and correct for it in the next.</span></span> <span data-ttu-id="f26d0-215">Результатом является модель прогнозирования, фактически собранная из нескольких более слабых моделей прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="f26d0-215">The result is a prediction model that is actually an ensemble of weaker prediction models.</span></span> <span data-ttu-id="f26d0-216">Дополнительные сведения о градиентном бустинге см. в статье [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression) (Регрессия для дерева принятия решений с бустингом).</span><span class="sxs-lookup"><span data-stu-id="f26d0-216">For more information about gradient boosting, see [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span></span>

<span data-ttu-id="f26d0-217">Добавьте следующий код в метод `Train` после кода обработки данных, который вы добавили на предыдущем шаге:</span><span class="sxs-lookup"><span data-stu-id="f26d0-217">Add the following code into the `Train` method following the data processing code added in the previous step:</span></span>

```csharp
pipeline.Add(new FastTreeRegressor());
```

<span data-ttu-id="f26d0-218">Все предыдущие шаги добавляются в конвейер как отдельные инструкции, но в C# реализован удобный синтаксис для инициализации коллекций, который упрощает создание и инициализацию конвейера.</span><span class="sxs-lookup"><span data-stu-id="f26d0-218">You added all the preceding steps to the pipeline as individual statements, but C# has a handy collection initialization syntax that makes it simpler to create and initialize the pipeline.</span></span> <span data-ttu-id="f26d0-219">Замените весь код, который вы добавили ранее в метод `Train`, следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="f26d0-219">Replace the code you added so far to the `Train` method with the following code:</span></span>

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a><span data-ttu-id="f26d0-220">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="f26d0-220">Train the model</span></span>

<span data-ttu-id="f26d0-221">Последним шагом является обучение модели.</span><span class="sxs-lookup"><span data-stu-id="f26d0-221">The final step is to train the model.</span></span> <span data-ttu-id="f26d0-222">До этого момента действия в конвейере не выполнялись.</span><span class="sxs-lookup"><span data-stu-id="f26d0-222">Until this point, nothing in the pipeline has been executed.</span></span> <span data-ttu-id="f26d0-223">Метод `pipeline.Train<TInput, TOutput>` создает модель, которая принимает экземпляр типа `TInput` и возвращает экземпляр типа `TOutput`.</span><span class="sxs-lookup"><span data-stu-id="f26d0-223">The `pipeline.Train<TInput, TOutput>` method produces the model that takes in an instance of the `TInput` type and outputs an instance of the `TOutput` type.</span></span> <span data-ttu-id="f26d0-224">Добавьте в метод `Train` следующий код:</span><span class="sxs-lookup"><span data-stu-id="f26d0-224">Add the following code into the `Train` method:</span></span>

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

<span data-ttu-id="f26d0-225">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="f26d0-225">And that's it!</span></span> <span data-ttu-id="f26d0-226">Вы успешно обучили модель машинного обучения, которая умеет прогнозировать плату за проезд в такси в городе Нью-Йорк.</span><span class="sxs-lookup"><span data-stu-id="f26d0-226">You have successfully trained a machine learning model that can predict taxi fares in NYC.</span></span> <span data-ttu-id="f26d0-227">Рассмотрим, каким образом можно оценить точность модели и использовать ее для прогнозирования величины платы за поездку на такси.</span><span class="sxs-lookup"><span data-stu-id="f26d0-227">Now let's take a look to understand how accurate the model is and learn how to use it to predict taxi fare values.</span></span>

### <a name="save-the-model"></a><span data-ttu-id="f26d0-228">Сохранение модели</span><span class="sxs-lookup"><span data-stu-id="f26d0-228">Save the model</span></span>

<span data-ttu-id="f26d0-229">Прежде чем перейти к следующему шагу, сохраните модель в ZIP-файл, добавив следующий код в конце метода `Train`:</span><span class="sxs-lookup"><span data-stu-id="f26d0-229">Before you go onto the next step, save the model to a .zip file by adding the following code at the end of the `Train` method:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

<span data-ttu-id="f26d0-230">Когда вы добавляете инструкцию `await` в вызов `model.WriteAsync`, метод `Train` необходимо заменить асинхронным методом, который возвращает задачу.</span><span class="sxs-lookup"><span data-stu-id="f26d0-230">Adding the `await` statement to the `model.WriteAsync` call means that the `Train` method must be changed to an async method that returns a task.</span></span> <span data-ttu-id="f26d0-231">Измените сигнатуру `Train`, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="f26d0-231">Modify the signature of `Train` as shown in the following code:</span></span>

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

<span data-ttu-id="f26d0-232">Когда вы изменяете тип возвращаемого значения для метода `Train`, необходимо добавить `await` в код, который вызывает `Train` в методе `Main`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f26d0-232">Changing the return type of the `Train` method means you have to add an `await` to the code that calls `Train` in the `Main` method as shown in the following code:</span></span>

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

<span data-ttu-id="f26d0-233">Использование `await` в методе `Main` означает, что метод `Main` должен включать модификатор `async` и возвращать `Task`:</span><span class="sxs-lookup"><span data-stu-id="f26d0-233">Using `await` in the `Main` method means the `Main` method must have the `async` modifier and return a `Task`:</span></span>

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

<span data-ttu-id="f26d0-234">Также добавьте следующую директиву `using` в самое начало файла.</span><span class="sxs-lookup"><span data-stu-id="f26d0-234">You also need to add the following `using` directive at the top of the file:</span></span>

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

<span data-ttu-id="f26d0-235">Так как метод `async Main` реализован только в C# версии 7.1, а для этого проекта по умолчанию устанавливается версия языка C# 7.0, необходимо изменить версию до C# 7.1 или выше.</span><span class="sxs-lookup"><span data-stu-id="f26d0-235">Because the `async Main` method is the feature added in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span> <span data-ttu-id="f26d0-236">Для этого в **обозревателе решений** щелкните узел проекта правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f26d0-236">To do that, right-click the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="f26d0-237">Откройте вкладку **Сборка** и нажмите на кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="f26d0-237">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="f26d0-238">В раскрывающемся списке выберите **C# 7.1** (или более позднюю версию).</span><span class="sxs-lookup"><span data-stu-id="f26d0-238">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="f26d0-239">Нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="f26d0-239">Select the **OK** button.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="f26d0-240">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="f26d0-240">Evaluate the model</span></span>

<span data-ttu-id="f26d0-241">Оценка — это процесс проверки того, насколько хорошо модель позволяет спрогнозировать значения метки.</span><span class="sxs-lookup"><span data-stu-id="f26d0-241">Evaluation is the process of checking how well the model predicts label values.</span></span> <span data-ttu-id="f26d0-242">Важно, чтобы модель возвращала хорошие прогнозы по данным, которые не использовались для ее обучения.</span><span class="sxs-lookup"><span data-stu-id="f26d0-242">It's important that the model makes good predictions on data that was not used to train the model.</span></span> <span data-ttu-id="f26d0-243">Для такой оценки можно, например, разделить данные на обучающий и тестовый наборы данных, как вы и сделали в рамках этого учебника.</span><span class="sxs-lookup"><span data-stu-id="f26d0-243">One way to do this is to split the data into train and test data sets, as it's done in this tutorial.</span></span> <span data-ttu-id="f26d0-244">Теперь, когда вы завершили обучение модели по обучающему набору данных, вы можете проверить ее работу по тестовым данным.</span><span class="sxs-lookup"><span data-stu-id="f26d0-244">Now that you've trained the model on the train data, you can see how well it performs on the test data.</span></span>

<span data-ttu-id="f26d0-245">Вернитесь к методу `Main` и добавьте следующий код под вызовом метода `Train`:</span><span class="sxs-lookup"><span data-stu-id="f26d0-245">Go back to the `Main` method and add the following code beneath the call to the `Train`method:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

<span data-ttu-id="f26d0-246">Метод `Evaluate` осуществляет оценку модели.</span><span class="sxs-lookup"><span data-stu-id="f26d0-246">The `Evaluate` method evaluates the model.</span></span> <span data-ttu-id="f26d0-247">Чтобы создать этот метод, добавьте следующий код под методом `Train`:</span><span class="sxs-lookup"><span data-stu-id="f26d0-247">To create that method, add the following code below the `Train` method:</span></span>

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

<span data-ttu-id="f26d0-248">Добавьте следующий код в метод `Evaluate`, чтобы настроить загрузку тестовых данных:</span><span class="sxs-lookup"><span data-stu-id="f26d0-248">Add the following code into the `Evaluate` method to setup loading of the test data:</span></span>

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

<span data-ttu-id="f26d0-249">Добавьте следующий код, чтобы оценить модель и создать для нее метрики оценки:</span><span class="sxs-lookup"><span data-stu-id="f26d0-249">Add the following code to evaluate the model and produce the evaluation metrics:</span></span>

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

<span data-ttu-id="f26d0-250">[Среднеквадратичное отклонение](../resources/glossary.md##root-of-mean-squared-error-rmse) является одной из метрик, используемых для оценки регрессионной модели.</span><span class="sxs-lookup"><span data-stu-id="f26d0-250">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) is one of the evaluation metrics of the regression model.</span></span> <span data-ttu-id="f26d0-251">Чем ниже это отклонение, тем лучше модель.</span><span class="sxs-lookup"><span data-stu-id="f26d0-251">The lower it is, the better the model is.</span></span> <span data-ttu-id="f26d0-252">Чтобы отображать значение среднеквадратичного отклонения, добавьте следующий код в метод `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="f26d0-252">Add the following code into the `Evaluate` method to display the RMS value:</span></span>

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

<span data-ttu-id="f26d0-253">Также в качестве метрики для оценки регрессионных моделей используется [коэффициент детерминации](../resources/glossary.md#coefficient-of-determination).</span><span class="sxs-lookup"><span data-stu-id="f26d0-253">[RSquared](../resources/glossary.md#coefficient-of-determination) is another evaluation metric of the regression models.</span></span> <span data-ttu-id="f26d0-254">Коэффициент детерминации может иметь значения в диапазоне от 0 до 1.</span><span class="sxs-lookup"><span data-stu-id="f26d0-254">RSquared takes values between 0 and 1.</span></span> <span data-ttu-id="f26d0-255">Чем ближе его значение к 1, тем лучше модель.</span><span class="sxs-lookup"><span data-stu-id="f26d0-255">The closer its value is to 1, the better the model is.</span></span> <span data-ttu-id="f26d0-256">Чтобы отображать значение коэффициента детерминации, добавьте следующий код в метод `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="f26d0-256">Add the following code into the `Evaluate` method to display the RSquared value:</span></span>

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="f26d0-257">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="f26d0-257">Use the model for predictions</span></span>

<span data-ttu-id="f26d0-258">Теперь создайте класс для размещения сценариев тестирования, которые вы можете использовать для проверки правильности работы модели:</span><span class="sxs-lookup"><span data-stu-id="f26d0-258">Next, create a class to house test scenarios that you can use to make sure the model is working correctly:</span></span>

1. <span data-ttu-id="f26d0-259">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="f26d0-259">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="f26d0-260">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *TestTrips.cs*.</span><span class="sxs-lookup"><span data-stu-id="f26d0-260">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestTrips.cs*.</span></span> <span data-ttu-id="f26d0-261">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="f26d0-261">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="f26d0-262">Измените класс, чтобы он был статическим, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f26d0-262">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

<span data-ttu-id="f26d0-263">Для этого руководства в этом классе используется один тестовый проход.</span><span class="sxs-lookup"><span data-stu-id="f26d0-263">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="f26d0-264">Позже можно добавить другие сценарии и поэкспериментировать с этой моделью.</span><span class="sxs-lookup"><span data-stu-id="f26d0-264">Later you can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="f26d0-265">Добавьте в класс `TestTrips` следующий код:</span><span class="sxs-lookup"><span data-stu-id="f26d0-265">Add the following code into the `TestTrips` class:</span></span>

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

<span data-ttu-id="f26d0-266">Фактическая плата за эту поездку составляет 29,5.</span><span class="sxs-lookup"><span data-stu-id="f26d0-266">This trip's actual fare is 29.5.</span></span> <span data-ttu-id="f26d0-267">Используйте в качестве заполнителя значение 0, поскольку модель будет прогнозировать величину платы.</span><span class="sxs-lookup"><span data-stu-id="f26d0-267">Use 0 as a placeholder, as the model will predict the fare.</span></span>

<span data-ttu-id="f26d0-268">Чтобы спрогнозировать величину платы за конкретную поездку, вернитесь к файлу *Program.cs* и добавьте следующий код в метод `Main`:</span><span class="sxs-lookup"><span data-stu-id="f26d0-268">To predict the fare of the specified trip, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

<span data-ttu-id="f26d0-269">Запустите программу, чтобы узнать прогноз платы за такси для тестового примера.</span><span class="sxs-lookup"><span data-stu-id="f26d0-269">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="f26d0-270">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="f26d0-270">Congratulations!</span></span> <span data-ttu-id="f26d0-271">Вы успешно создали модель машинного обучения для прогнозирования платы за проезд в такси, оценили ее точность и использовали ее для получения прогнозов.</span><span class="sxs-lookup"><span data-stu-id="f26d0-271">You've now successfully built a machine learning model for predicting taxi trip fares, evaluated its accuracy, and used it to make predictions.</span></span> <span data-ttu-id="f26d0-272">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).</span><span class="sxs-lookup"><span data-stu-id="f26d0-272">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f26d0-273">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="f26d0-273">Next steps</span></span>

<span data-ttu-id="f26d0-274">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="f26d0-274">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="f26d0-275">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="f26d0-275">Understand the problem</span></span>
> * <span data-ttu-id="f26d0-276">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="f26d0-276">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="f26d0-277">Подготовка и анализ данных</span><span class="sxs-lookup"><span data-stu-id="f26d0-277">Prepare and understand the data</span></span>
> * <span data-ttu-id="f26d0-278">Создание конвейера обучения</span><span class="sxs-lookup"><span data-stu-id="f26d0-278">Create a learning pipeline</span></span>
> * <span data-ttu-id="f26d0-279">Загрузка и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="f26d0-279">Load and transform the data</span></span>
> * <span data-ttu-id="f26d0-280">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="f26d0-280">Choose a learning algorithm</span></span>
> * <span data-ttu-id="f26d0-281">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="f26d0-281">Train the model</span></span>
> * <span data-ttu-id="f26d0-282">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="f26d0-282">Evaluate the model</span></span>
> * <span data-ttu-id="f26d0-283">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="f26d0-283">Use the model for predictions</span></span>

<span data-ttu-id="f26d0-284">Извлеките наш репозиторий GitHub, чтобы продолжить обучение и получить дополнительные примеры.</span><span class="sxs-lookup"><span data-stu-id="f26d0-284">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="f26d0-285">Репозиторий GitHub dotnet/machinelearning</span><span class="sxs-lookup"><span data-stu-id="f26d0-285">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
