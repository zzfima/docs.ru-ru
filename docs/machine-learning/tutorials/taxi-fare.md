---
title: Использование ML.NET для прогнозирования платы за проезд в такси в Нью-Йорке (регрессия)
description: Сведения об использовании ML.NET в сценарии с моделью регрессии.
author: aditidugar
ms.author: johalex
ms.date: 06/05/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 048ed1d38408c1ba4901c554cae33d5552c9e303
ms.sourcegitcommit: 5b0802832fb9ad684d34e69b8644a16a5b7c4810
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2018
ms.locfileid: "34860707"
---
# <a name="tutorial-use-mlnet-to-predict-new-york-taxi-fares-regression"></a><span data-ttu-id="f671c-103">Руководство. Использование ML.NET для прогнозирования платы за проезд в такси в Нью-Йорке (регрессия)</span><span class="sxs-lookup"><span data-stu-id="f671c-103">Tutorial: Use ML.NET to predict New York taxi fares (regression)</span></span>

> [!NOTE]
> <span data-ttu-id="f671c-104">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="f671c-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="f671c-105">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="f671c-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="f671c-106">В этом руководства описано, как с помощью ML.NET создать [модель регрессии](../resources/glossary.md#regression) для прогнозирования платы за проезд в такси в городе Нью-Йорк.</span><span class="sxs-lookup"><span data-stu-id="f671c-106">This tutorial illustrates how to use ML.NET to build a [regression model](../resources/glossary.md#regression) for predicting New York City taxi fares.</span></span>

<span data-ttu-id="f671c-107">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="f671c-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="f671c-108">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="f671c-108">Understand the problem</span></span>
> * <span data-ttu-id="f671c-109">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="f671c-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="f671c-110">Анализ данных</span><span class="sxs-lookup"><span data-stu-id="f671c-110">Prepare and understand your data</span></span>
> * <span data-ttu-id="f671c-111">Создание конвейера обучения</span><span class="sxs-lookup"><span data-stu-id="f671c-111">Create a learning pipeline</span></span>
> * <span data-ttu-id="f671c-112">Загрузка и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="f671c-112">Load and transform your data</span></span>
> * <span data-ttu-id="f671c-113">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="f671c-113">Choose a learning algorithm</span></span>
> * <span data-ttu-id="f671c-114">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="f671c-114">Train the model</span></span>
> * <span data-ttu-id="f671c-115">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="f671c-115">Evaluate the model</span></span>
> * <span data-ttu-id="f671c-116">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="f671c-116">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f671c-117">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f671c-117">Prerequisites</span></span>

* <span data-ttu-id="f671c-118">[Visual Studio 2017 15.6 или более поздней версии](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="f671c-118">[Visual Studio 2017 15.6 or later](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="f671c-119">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="f671c-119">Understand the problem</span></span>

<span data-ttu-id="f671c-120">Рассматриваемая проблема основана на сценарии **прогнозирования платы за поездку на такси в городе Нью-Йорк**.</span><span class="sxs-lookup"><span data-stu-id="f671c-120">This problem is centered around **predicting the fare of a taxi trip in New York City**.</span></span> <span data-ttu-id="f671c-121">На первый взгляд может показаться, что плата зависит только от расстояния.</span><span class="sxs-lookup"><span data-stu-id="f671c-121">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="f671c-122">Но службы такси в Нью-Йорке изменяют плату с учетом еще нескольких факторов, таких как наличие дополнительных пассажиров или оплата кредитной картой вместо наличных.</span><span class="sxs-lookup"><span data-stu-id="f671c-122">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="f671c-123">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="f671c-123">Select the appropriate machine learning task</span></span>

<span data-ttu-id="f671c-124">Для прогнозирования платы за проезд в такси прежде всего нужно выбрать правильную задачу машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="f671c-124">To predict the taxi fare, you first select the appropriate machine learning task.</span></span> <span data-ttu-id="f671c-125">Вам нужно спрогнозировать реальное значение (значение цены в формате двойной точности) на основе других факторов в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="f671c-125">You are looking to predict a real value (a double that represents price) based on the other factors in the dataset.</span></span> <span data-ttu-id="f671c-126">Для этого выберите задачу [**регрессии**](../resources/glossary.md#regression).</span><span class="sxs-lookup"><span data-stu-id="f671c-126">You choose a [**regression**](../resources/glossary.md#regression) task.</span></span>

<span data-ttu-id="f671c-127">Процесс обучения модели определяет, какие факторы в наборе данных больше других влияют на окончательную плату за проезд.</span><span class="sxs-lookup"><span data-stu-id="f671c-127">The process of training the model identifies which factors in the dataset are most influential when predicting the final fare price.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="f671c-128">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="f671c-128">Create a console application</span></span>

1. <span data-ttu-id="f671c-129">Откройте Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="f671c-129">Open Visual Studio 2017.</span></span> <span data-ttu-id="f671c-130">Выберите **Файл** > **Создать** > **Проект** в меню.</span><span class="sxs-lookup"><span data-stu-id="f671c-130">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="f671c-131">В диалоговом окне **Новый проект** выберите узел **Visual C#**, а затем — узел **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="f671c-131">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="f671c-132">Выберите шаблон проекта **Консольное приложение (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="f671c-132">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="f671c-133">В текстовое поле **Имя** введите TaxiFarePrediction, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f671c-133">In the **Name** text box, type "TaxiFarePrediction" and then select the **OK** button.</span></span>

2. <span data-ttu-id="f671c-134">Создайте каталог с именем *Data* в папке проекта, чтобы сохранить в нем файлы с наборами данных:</span><span class="sxs-lookup"><span data-stu-id="f671c-134">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="f671c-135">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="f671c-135">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="f671c-136">Введите имя папки Data и нажмите клавишу "ВВОД".</span><span class="sxs-lookup"><span data-stu-id="f671c-136">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="f671c-137">Установите **пакет NuGet для Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="f671c-137">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="f671c-138">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="f671c-138">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="f671c-139">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="f671c-139">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="f671c-140">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="f671c-140">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-and-understand-your-data"></a><span data-ttu-id="f671c-141">Анализ данных</span><span class="sxs-lookup"><span data-stu-id="f671c-141">Prepare and understand your data</span></span>

1. <span data-ttu-id="f671c-142">Скачайте наборы данных [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) и [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv), сохранив их в ранее созданную папку *Data*.</span><span class="sxs-lookup"><span data-stu-id="f671c-142">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="f671c-143">Набор данных Taxi Trip обучает модель машинного обучения, а также позволяет оценить точность полученной модели.</span><span class="sxs-lookup"><span data-stu-id="f671c-143">The Taxi Trip data set trains the machine learning model and can be used to evaluate how accurate your model is.</span></span> <span data-ttu-id="f671c-144">Эти наборы данных взяты из [наборов данных NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span><span class="sxs-lookup"><span data-stu-id="f671c-144">These data sets are originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

2. <span data-ttu-id="f671c-145">В обозревателе решений щелкните правой кнопкой мыши каждый из файлов \*.csv и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f671c-145">In Solution Explorer, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="f671c-146">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Всегда**.</span><span class="sxs-lookup"><span data-stu-id="f671c-146">Under **Advanced**, change the value of **Copy to Output Directory** to **Always**.</span></span>

3. <span data-ttu-id="f671c-147">Откройте набор данных **taxi-fare-train.csv** в редакторе кода и просмотрите заголовки столбцов в первой строке.</span><span class="sxs-lookup"><span data-stu-id="f671c-147">Open the **taxi-fare-train.csv** data set in the code editor and look at column headers in the first row.</span></span> <span data-ttu-id="f671c-148">Теперь изучите каждый из столбцов.</span><span class="sxs-lookup"><span data-stu-id="f671c-148">Take a look at each of the columns.</span></span> <span data-ttu-id="f671c-149">Разберитесь, какие данные в них хранятся, и определите, какие столбцы являются **признаками**, а в каком содержится **метка**.</span><span class="sxs-lookup"><span data-stu-id="f671c-149">Understand the data and decide which columns are **features** and which is the **label**.</span></span>

<span data-ttu-id="f671c-150">**Метка** — это столбец, значения в котором вы хотите спрогнозировать.</span><span class="sxs-lookup"><span data-stu-id="f671c-150">The **label** is the identifier of the column you are trying to predict.</span></span> <span data-ttu-id="f671c-151">Выбранные **признаки** используются для прогнозирования метки.</span><span class="sxs-lookup"><span data-stu-id="f671c-151">The identified **features** are used to predict the label.</span></span>

* <span data-ttu-id="f671c-152">**vendor_id:** идентификатор поставщика такси — это признак.</span><span class="sxs-lookup"><span data-stu-id="f671c-152">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="f671c-153">**rate_code:** тип оплаты для поездки на такси — это признак.</span><span class="sxs-lookup"><span data-stu-id="f671c-153">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="f671c-154">**passenger_count:** число пассажиров в поездке — это признак.</span><span class="sxs-lookup"><span data-stu-id="f671c-154">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="f671c-155">**trip_time_in_secs:** время, затраченное на поездку.</span><span class="sxs-lookup"><span data-stu-id="f671c-155">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="f671c-156">Пока поездка не завершится, вы не сможете узнать ее продолжительность.</span><span class="sxs-lookup"><span data-stu-id="f671c-156">You won't know how long the trip takes until after it is completed.</span></span> <span data-ttu-id="f671c-157">Этот столбец можно исключить из модели.</span><span class="sxs-lookup"><span data-stu-id="f671c-157">You exclude this column from the model.</span></span>
* <span data-ttu-id="f671c-158">**trip_distance:** расстояние поездки — это признак.</span><span class="sxs-lookup"><span data-stu-id="f671c-158">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="f671c-159">**payment_type:** метод оплаты (наличные или кредитная карта) — это признак.</span><span class="sxs-lookup"><span data-stu-id="f671c-159">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="f671c-160">**fare_amount:** общая сумма, оплаченная за поездку на такси — это метка.</span><span class="sxs-lookup"><span data-stu-id="f671c-160">**fare_amount:** The total taxi fare paid is the label.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="f671c-161">Создание классов и определение путей</span><span class="sxs-lookup"><span data-stu-id="f671c-161">Create classes and define paths</span></span>

<span data-ttu-id="f671c-162">Добавьте следующие новые операторы `using` в начало файла *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="f671c-162">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="f671c-163">Также нужно создать три глобальные переменные для хранения путей к недавно скачанным файлам, а затем сохранить модель:</span><span class="sxs-lookup"><span data-stu-id="f671c-163">You need to create three global variables to hold the paths to the recently downloaded files and to save the model:</span></span>

* <span data-ttu-id="f671c-164">`_datapath` содержит путь к набору данных, который используется для обучения модели;</span><span class="sxs-lookup"><span data-stu-id="f671c-164">`_datapath` has the path to the data set used to train the model.</span></span>
* <span data-ttu-id="f671c-165">`_testdatapath` содержит путь к набору данных, который используется для оценки модели;</span><span class="sxs-lookup"><span data-stu-id="f671c-165">`_testdatapath` has the path to the data set used to evaluate the model.</span></span>
* <span data-ttu-id="f671c-166">`_modelpath` содержит путь к сохраненной обученной модели.</span><span class="sxs-lookup"><span data-stu-id="f671c-166">`_modelpath` has the path where the trained model is stored.</span></span>

<span data-ttu-id="f671c-167">Добавьте следующий код прямо перед `Main`, чтобы указать ссылки на скачанные файлы:</span><span class="sxs-lookup"><span data-stu-id="f671c-167">Add the following code to the line right above `Main` to specify the recently downloaded files:</span></span>

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="f671c-168">Теперь создайте классы для входных данных и прогнозов.</span><span class="sxs-lookup"><span data-stu-id="f671c-168">Next, create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="f671c-169">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="f671c-169">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="f671c-170">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *TaxiTrip.cs*.</span><span class="sxs-lookup"><span data-stu-id="f671c-170">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="f671c-171">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="f671c-171">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="f671c-172">Добавьте в новый файл следующие операторы `using`:</span><span class="sxs-lookup"><span data-stu-id="f671c-172">Add the following `using` statements to the new file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="f671c-173">Удалите из файла *TaxiTrip.cs* существующее определение класса и добавьте следующий код с двумя классами `TaxiTrip` и `TaxiTripFarePrediction`:</span><span class="sxs-lookup"><span data-stu-id="f671c-173">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="f671c-174">Класс `TaxiTrip` содержит входной набор данных и определения для каждого из столбцов в этом наборе данных.</span><span class="sxs-lookup"><span data-stu-id="f671c-174">`TaxiTrip` is the input data set class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="f671c-175">Класс `TaxiTripFarePrediction` используется для прогнозирования после обучения модели.</span><span class="sxs-lookup"><span data-stu-id="f671c-175">The `TaxiTripFarePrediction` class is used for prediction after the model has been trained.</span></span> <span data-ttu-id="f671c-176">Он имеет один параметр типа float (`FareAmount`) и к нему применен атрибут `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="f671c-176">It has a single float (`FareAmount`) and a `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) attribute applied.</span></span>

<span data-ttu-id="f671c-177">Теперь вернитесь к файлу **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="f671c-177">Now go back to the **Program.cs** file.</span></span> <span data-ttu-id="f671c-178">В `Main` замените `Console.WriteLine("Hello World!")` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="f671c-178">In `Main`, replace the `Console.WriteLine("Hello World!")` with the following code:</span></span>

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

<span data-ttu-id="f671c-179">Метод `Train` обучает модель.</span><span class="sxs-lookup"><span data-stu-id="f671c-179">The `Train` method trains your model.</span></span> <span data-ttu-id="f671c-180">Создайте эту функцию сразу под `Main`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="f671c-180">Create that function just below `Main`, using the following code:</span></span>

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="f671c-181">Создание конвейера обучения</span><span class="sxs-lookup"><span data-stu-id="f671c-181">Create a learning pipeline</span></span>

<span data-ttu-id="f671c-182">Конвейер обучения загружает все данные и алгоритмы, необходимые для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="f671c-182">The learning pipeline loads all of the data and algorithms necessary to train the model.</span></span> <span data-ttu-id="f671c-183">Добавьте в метод `Train()` следующий код:</span><span class="sxs-lookup"><span data-stu-id="f671c-183">Add the following code into the `Train()` method:</span></span>

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-your-data"></a><span data-ttu-id="f671c-184">Загрузка и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="f671c-184">Load and transform your data</span></span>

<span data-ttu-id="f671c-185">Загрузите данные в конвейер.</span><span class="sxs-lookup"><span data-stu-id="f671c-185">Next, load your data into the pipeline.</span></span> <span data-ttu-id="f671c-186">Укажите `_datapath`, созданный изначально, и разделитель для CSV-файла (,).</span><span class="sxs-lookup"><span data-stu-id="f671c-186">Point to the `_datapath` created initially and specify the delimiter of the .csv file (,).</span></span> <span data-ttu-id="f671c-187">Добавьте следующий код в метод `Train()` под последним шагом:</span><span class="sxs-lookup"><span data-stu-id="f671c-187">Add the following code into the `Train()` method underneath the last step:</span></span>

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(separator:','));
```

<span data-ttu-id="f671c-188">В коде, который вы создаете, ссылки на столбцы следует указывать без символов подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="f671c-188">You'll refer to the columns without the underscores in the code you're creating.</span></span> <span data-ttu-id="f671c-189">Скопируйте столбец `FareAmount` в новый столбец с именем Label с помощью функции `ColumnCopier()`.</span><span class="sxs-lookup"><span data-stu-id="f671c-189">Copy the `FareAmount` column into a new column called "Label" using the `ColumnCopier()` function.</span></span> <span data-ttu-id="f671c-190">Этот столбец является **меткой**.</span><span class="sxs-lookup"><span data-stu-id="f671c-190">This column is the **Label**.</span></span>

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

<span data-ttu-id="f671c-191">С помощью функции **проектирования признаков** преобразуйте данные так, чтобы их можно было эффективно использовать для машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="f671c-191">Conduct some **feature engineering** to transform the data so that it can be used effectively for machine learning.</span></span> <span data-ttu-id="f671c-192">Алгоритм, который обучает модель, принимает **числовые** признаки, поэтому категориальные данные (`VendorId`, `RateCode` и `PaymentType`) нужно преобразовать в числа.</span><span class="sxs-lookup"><span data-stu-id="f671c-192">The algorithm that trains the model requires **numeric** features, you transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) into numbers.</span></span> <span data-ttu-id="f671c-193">Функция `CategoricalOneHotVectorizer()` присваивает числовой ключ значениям в каждом из этих столбцов.</span><span class="sxs-lookup"><span data-stu-id="f671c-193">The `CategoricalOneHotVectorizer()` function assigns a numeric key to the values in each of these columns.</span></span> <span data-ttu-id="f671c-194">Для преобразования данных добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="f671c-194">Transform your data by adding this code:</span></span>

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

<span data-ttu-id="f671c-195">Последний шаг в процессе подготовки данных объединяет все **признаки** в один вектор с помощью функции `ColumnConcatenator()`.</span><span class="sxs-lookup"><span data-stu-id="f671c-195">The last step in data preparation combines all of your **features** into one vector using the `ColumnConcatenator()` function.</span></span> <span data-ttu-id="f671c-196">Этот обязательный шаг помогает алгоритму легко обрабатывать признаки.</span><span class="sxs-lookup"><span data-stu-id="f671c-196">This necessary step helps the algorithm easily process your features.</span></span> <span data-ttu-id="f671c-197">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="f671c-197">Add the following code:</span></span>

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

<span data-ttu-id="f671c-198">Обратите внимание, что столбец `trip_time_in_secs` не включается.</span><span class="sxs-lookup"><span data-stu-id="f671c-198">Notice that the `trip_time_in_secs` column isn't included.</span></span> <span data-ttu-id="f671c-199">Вы уже определили, что он не будет полезным признаком для прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="f671c-199">You already determined that it isn't a useful prediction feature.</span></span>

> [!NOTE]
> <span data-ttu-id="f671c-200">Для успешного выполнения шагов следует добавлять в конвейер в том порядке, который указан выше.</span><span class="sxs-lookup"><span data-stu-id="f671c-200">These steps must be added to Pipeline in the order specified above for successful execution.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="f671c-201">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="f671c-201">Choose a learning algorithm</span></span>

<span data-ttu-id="f671c-202">После добавления данных в конвейер и их преобразования в правильный входной формат выберите алгоритм обучения (**средство обучения**).</span><span class="sxs-lookup"><span data-stu-id="f671c-202">After adding the data to the pipeline and transforming it into the correct input format, you select a learning algorithm (**learner**).</span></span> <span data-ttu-id="f671c-203">Обучающий алгоритм подготавливает модель.</span><span class="sxs-lookup"><span data-stu-id="f671c-203">The learning algorithm trains the model.</span></span> <span data-ttu-id="f671c-204">Для этой проблемы вы выбрали **задачу регрессии**, поэтому добавьте в конвейер средство обучения с именем `FastTreeRegressor()`, которое использует **градиентный бустинг**.</span><span class="sxs-lookup"><span data-stu-id="f671c-204">You chose a **regression task** for this problem, so you add a learner called `FastTreeRegressor()` to the pipeline that utilizes **gradient boosting**.</span></span>

<span data-ttu-id="f671c-205">Градиентный бустинг — это метод машинного обучения для проблем регрессии.</span><span class="sxs-lookup"><span data-stu-id="f671c-205">Gradient boosting is a machine learning technique for regression problems.</span></span> <span data-ttu-id="f671c-206">Он пошагово создает каждое дерево регрессии.</span><span class="sxs-lookup"><span data-stu-id="f671c-206">It builds each regression tree in a step-wise fashion.</span></span> <span data-ttu-id="f671c-207">Он также использует предварительно определенную функцию для оценки ошибки на каждом этапе и исправления ошибок для следующего этапа.</span><span class="sxs-lookup"><span data-stu-id="f671c-207">It uses a pre-defined loss function to measure the error in each step and correct for it in the next.</span></span> <span data-ttu-id="f671c-208">Результатом является модель прогнозирования, фактически собранная из нескольких более слабых моделей прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="f671c-208">The result is a prediction model that is actually an ensemble of weaker prediction models.</span></span> <span data-ttu-id="f671c-209">Дополнительные сведения о градиентном бустинге см. в статье [Boosted Decision Tree Regression](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression) (Регрессия для дерева принятия решений с бустингом).</span><span class="sxs-lookup"><span data-stu-id="f671c-209">For more information about gradient boosting, see [Boosted Decision Tree Regression](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span></span>

<span data-ttu-id="f671c-210">Добавьте следующий код в метод `Train()` после кода обработки данных, который вы добавили на предыдущем шаге:</span><span class="sxs-lookup"><span data-stu-id="f671c-210">Add the following code into the `Train()` method following the data processing code added in the last step:</span></span>

```csharp
pipeline.Add(new FastTreeRegressor());
```

<span data-ttu-id="f671c-211">Все предыдущие шаги добавляются в конвейер как отдельные инструкции, но в C# реализован удобный синтаксис для инициализации коллекций, который упрощает создание и инициализацию конвейера.</span><span class="sxs-lookup"><span data-stu-id="f671c-211">You added all the preceding steps to the pipeline as individual statements, but C# has a handy collection initialization syntax that makes it simpler to create and initialize the pipeline.</span></span> <span data-ttu-id="f671c-212">Замените весь код, который вы добавили ранее в метод `Train()`, следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="f671c-212">Replace the code you added so far to the `Train()` method with the following code:</span></span>

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a><span data-ttu-id="f671c-213">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="f671c-213">Train the model</span></span>

<span data-ttu-id="f671c-214">Последним шагом является обучение модели.</span><span class="sxs-lookup"><span data-stu-id="f671c-214">The final step is to train the model.</span></span> <span data-ttu-id="f671c-215">До этого момента действия в конвейере не выполнялись.</span><span class="sxs-lookup"><span data-stu-id="f671c-215">Until this point, nothing in the pipeline has been executed.</span></span> <span data-ttu-id="f671c-216">Функция `pipeline.Train<T_Input, T_Output>()` принимает предварительно определенный тип класса `TaxiTrip` и возвращает тип `TaxiTripFarePrediction`.</span><span class="sxs-lookup"><span data-stu-id="f671c-216">The `pipeline.Train<T_Input, T_Output>()` function takes in the pre-defined `TaxiTrip` class type and outputs a `TaxiTripFarePrediction` type.</span></span> <span data-ttu-id="f671c-217">Добавьте этот готовый фрагмент кода в функцию `Train()`:</span><span class="sxs-lookup"><span data-stu-id="f671c-217">Add this final piece of code into the `Train()` function:</span></span>

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

<span data-ttu-id="f671c-218">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="f671c-218">And that's it!</span></span> <span data-ttu-id="f671c-219">Вы успешно обучили модель машинного обучения, которая умеет прогнозировать плату за проезд в такси в городе Нью-Йорк.</span><span class="sxs-lookup"><span data-stu-id="f671c-219">You have successfully trained a machine learning model that can predict taxi fares in NYC.</span></span> <span data-ttu-id="f671c-220">Теперь давайте посмотрим, насколько точная у вас модель и как ее правильно использовать.</span><span class="sxs-lookup"><span data-stu-id="f671c-220">Now take a look to understand how accurate your model is and learn how to consume it.</span></span>

## <a name="save-the-model"></a><span data-ttu-id="f671c-221">Сохранение модели</span><span class="sxs-lookup"><span data-stu-id="f671c-221">Save the model</span></span>

<span data-ttu-id="f671c-222">Прежде чем как перейти к следующему шагу, сохраните модель в ZIP-файл, добавив следующий код в конце функции `Train()`:</span><span class="sxs-lookup"><span data-stu-id="f671c-222">Before you go onto the next step, save your model to a .zip file by adding the following code at the end of your `Train()` function:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

<span data-ttu-id="f671c-223">Когда вы добавляете инструкцию `await` в вызов `model.WriteAsync()`, метод `Train()` необходимо заменить асинхронным методом, который возвращает `Task`.</span><span class="sxs-lookup"><span data-stu-id="f671c-223">Adding the `await` statement to the `model.WriteAsync()` call means that the `Train()` method must be changed to an async method that returns a `Task`.</span></span> <span data-ttu-id="f671c-224">Измените сигнатуру `Train`, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="f671c-224">Modify the signature of `Train` as shown in the following code:</span></span>

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

<span data-ttu-id="f671c-225">Когда вы изменяете тип возвращаемого значения для метода `Train`, необходимо добавить `await` в код, который вызывает `Train` в методе `Main`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f671c-225">Changing the return type of the `Train` method means you have to add an `await` to the code that calls `Train` in the `Main` method as shown in the following code:</span></span>

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

<span data-ttu-id="f671c-226">Добавление `await` в метод `Main`, означает, что метод `Main` должен включать модификатор `async` и возвращать `Task`:</span><span class="sxs-lookup"><span data-stu-id="f671c-226">Adding an `await` in your `Main` method means the `Main` method must have the `async` modifier and return a `Task`:</span></span>

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

<span data-ttu-id="f671c-227">Также добавьте следующую инструкцию using в самое начало файла.</span><span class="sxs-lookup"><span data-stu-id="f671c-227">You also need to add the following using statement at the top of the file:</span></span>

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

<span data-ttu-id="f671c-228">Так как метод `async Main` реализован только в C# версии 7.1, а для этого проекта по умолчанию устанавливается версия языка C# 7.0, необходимо изменить версию до C# 7.1 или выше.</span><span class="sxs-lookup"><span data-stu-id="f671c-228">Because the `async Main` method is a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="f671c-229">Для этого в **обозревателе решений** щелкните узел проекта правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f671c-229">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="f671c-230">Откройте вкладку **Сборка** и нажмите на кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="f671c-230">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="f671c-231">В раскрывающемся списке выберите **C# 7.1** (или более позднюю версию).</span><span class="sxs-lookup"><span data-stu-id="f671c-231">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="f671c-232">Нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="f671c-232">Select the **OK** button.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="f671c-233">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="f671c-233">Evaluate the model</span></span>

<span data-ttu-id="f671c-234">Оценка — это процесс проверки того, насколько хорошо работает модель.</span><span class="sxs-lookup"><span data-stu-id="f671c-234">Evaluation is the process of checking how well the model works.</span></span> <span data-ttu-id="f671c-235">Очень важно, чтобы модель возвращала хорошие прогнозы по данным, которые не использовались для ее обучения.</span><span class="sxs-lookup"><span data-stu-id="f671c-235">It's important that your model makes good predictions on data that it didn't use when it was trained.</span></span> <span data-ttu-id="f671c-236">Для такой оценки можно, например, разделить данные на обучающий и тестовый наборы данных, как вы и сделали с помощью этого руководства.</span><span class="sxs-lookup"><span data-stu-id="f671c-236">One way to do this is by splitting the data into train and test datasets, as you did in this tutorial.</span></span> <span data-ttu-id="f671c-237">Теперь, когда вы завершили обучение модели по обучающему набору данных, вы можете проверить ее работу по тестовым данным.</span><span class="sxs-lookup"><span data-stu-id="f671c-237">Now that you've trained the model on the train data, you can see how well it performs on the test data.</span></span>

<span data-ttu-id="f671c-238">Вернитесь к функции `Main` и добавьте следующий код под вызовом метода `Train()`:</span><span class="sxs-lookup"><span data-stu-id="f671c-238">Go back to your `Main` function and add the following code beneath the call to the `Train()`method:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

<span data-ttu-id="f671c-239">Функция `Evaluate()` вычисляет модель.</span><span class="sxs-lookup"><span data-stu-id="f671c-239">The `Evaluate()` function evaluates your model.</span></span> <span data-ttu-id="f671c-240">Создайте эту функцию под `Train()`.</span><span class="sxs-lookup"><span data-stu-id="f671c-240">Create that function below `Train()`.</span></span> <span data-ttu-id="f671c-241">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="f671c-241">Add the following code:</span></span>

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

<span data-ttu-id="f671c-242">Загрузите тестовый данные с помощью функции `TextLoader()`.</span><span class="sxs-lookup"><span data-stu-id="f671c-242">Load the test data using the `TextLoader()` function.</span></span> <span data-ttu-id="f671c-243">Добавьте в метод `Evaluate()` следующий код:</span><span class="sxs-lookup"><span data-stu-id="f671c-243">Add the following code into the `Evaluate()` method:</span></span>

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

<span data-ttu-id="f671c-244">Добавьте следующий код, чтобы оценить модель и создать для нее метрики:</span><span class="sxs-lookup"><span data-stu-id="f671c-244">Add the following code to evaluate the model and produce the metrics for it:</span></span>

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

<span data-ttu-id="f671c-245">Одной из метрик оценки проблем регрессии является среднеквадратичное отклонение.</span><span class="sxs-lookup"><span data-stu-id="f671c-245">RMS is one metric for evaluating regression problems.</span></span> <span data-ttu-id="f671c-246">Чем ниже это отклонение, тем лучше модель.</span><span class="sxs-lookup"><span data-stu-id="f671c-246">The lower it is, the better your model.</span></span> <span data-ttu-id="f671c-247">Добавьте следующий код в функцию `Evaluate()`, чтобы вывести среднеквадратичное отклонение для вашей модели.</span><span class="sxs-lookup"><span data-stu-id="f671c-247">Add the following code into the `Evaluate()` function to print the RMS for your model.</span></span>

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

<span data-ttu-id="f671c-248">Еще одной метрикой оценки проблем регрессии является коэффициент детерминации.</span><span class="sxs-lookup"><span data-stu-id="f671c-248">RSquared is another metric for evaluating regression problems.</span></span> <span data-ttu-id="f671c-249">Этот коэффициент может принимать значения от 0 до 1.</span><span class="sxs-lookup"><span data-stu-id="f671c-249">RSquared will be a value between 0 and 1.</span></span> <span data-ttu-id="f671c-250">Чем он ближе к 1, тем лучше модель.</span><span class="sxs-lookup"><span data-stu-id="f671c-250">The closer you are to 1, the better your model.</span></span> <span data-ttu-id="f671c-251">Добавьте следующий код в функцию `Evaluate()`, чтобы вывести коэффициент детерминации для вашей модели.</span><span class="sxs-lookup"><span data-stu-id="f671c-251">Add the following code into the `Evaluate()` function to print the RSquared value for your model.</span></span>

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="f671c-252">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="f671c-252">Use the model for predictions</span></span>

<span data-ttu-id="f671c-253">Теперь создайте класс для размещения сценариев тестирования, которые вы можете использовать для проверки правильности работы модели.</span><span class="sxs-lookup"><span data-stu-id="f671c-253">Next, create a class to house test scenarios that you can use to make sure your model is working correctly:</span></span>

1. <span data-ttu-id="f671c-254">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="f671c-254">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="f671c-255">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *TestTrips.cs*.</span><span class="sxs-lookup"><span data-stu-id="f671c-255">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestTrips.cs*.</span></span> <span data-ttu-id="f671c-256">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="f671c-256">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="f671c-257">Измените класс, чтобы он был статическим, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f671c-257">Modify the class to be static like in the following example:</span></span>

[!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

<span data-ttu-id="f671c-258">Для этого руководства в этом классе используется один тестовый проход.</span><span class="sxs-lookup"><span data-stu-id="f671c-258">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="f671c-259">Позже можно добавить другие сценарии и поэкспериментировать с этим примером.</span><span class="sxs-lookup"><span data-stu-id="f671c-259">Later you can add other scenarios to experiment with this sample.</span></span> <span data-ttu-id="f671c-260">Добавьте в класс `TestTrips` следующий код:</span><span class="sxs-lookup"><span data-stu-id="f671c-260">Add the following code into the `TestTrips` class:</span></span>

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

<span data-ttu-id="f671c-261">Фактическая плата за проезд составляет 29,5, но в качестве заполнителя следует указать 0.</span><span class="sxs-lookup"><span data-stu-id="f671c-261">This trip's actual fare is 29.5, but use 0 as a placeholder.</span></span> <span data-ttu-id="f671c-262">Алгоритм машинного обучения спрогнозирует плат за проезд.</span><span class="sxs-lookup"><span data-stu-id="f671c-262">The machine learning algorithm will predict the fare.</span></span>

<span data-ttu-id="f671c-263">Добавьте приведенный ниже код в функцию `Main`.</span><span class="sxs-lookup"><span data-stu-id="f671c-263">Add the following code in your `Main` function.</span></span> <span data-ttu-id="f671c-264">Он выполняет проверку модели с помощью данных `TestTrip`:</span><span class="sxs-lookup"><span data-stu-id="f671c-264">It tests out your model using the `TestTrip` data:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

<span data-ttu-id="f671c-265">Запустите программу, чтобы узнать прогноз платы за такси для тестового примера.</span><span class="sxs-lookup"><span data-stu-id="f671c-265">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="f671c-266">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="f671c-266">Congratulations!</span></span> <span data-ttu-id="f671c-267">Вы успешно создали модель машинного обучения для прогнозирования платы за проезд в такси, оценили ее точность и протестировали ее работу.</span><span class="sxs-lookup"><span data-stu-id="f671c-267">You've now successfully built a machine learning model for predicting taxi fares, evaluated its accuracy, and tested it.</span></span> <span data-ttu-id="f671c-268">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).</span><span class="sxs-lookup"><span data-stu-id="f671c-268">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f671c-269">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="f671c-269">Next steps</span></span>

<span data-ttu-id="f671c-270">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="f671c-270">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="f671c-271">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="f671c-271">Understand the problem</span></span>
> * <span data-ttu-id="f671c-272">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="f671c-272">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="f671c-273">Анализ данных</span><span class="sxs-lookup"><span data-stu-id="f671c-273">Prepare and understand your data</span></span>
> * <span data-ttu-id="f671c-274">Создание конвейера обучения</span><span class="sxs-lookup"><span data-stu-id="f671c-274">Create a learning pipeline</span></span>
> * <span data-ttu-id="f671c-275">Загрузка и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="f671c-275">Load and transform your data</span></span>
> * <span data-ttu-id="f671c-276">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="f671c-276">Choose a learning algorithm</span></span>
> * <span data-ttu-id="f671c-277">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="f671c-277">Train the model</span></span>
> * <span data-ttu-id="f671c-278">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="f671c-278">Evaluate the model</span></span>
> * <span data-ttu-id="f671c-279">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="f671c-279">Use the model for predictions</span></span>

<span data-ttu-id="f671c-280">Извлеките наш репозиторий GitHub, чтобы продолжить обучение и получить дополнительные примеры.</span><span class="sxs-lookup"><span data-stu-id="f671c-280">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="f671c-281">Репозиторий GitHub dotnet/machinelearning</span><span class="sxs-lookup"><span data-stu-id="f671c-281">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
