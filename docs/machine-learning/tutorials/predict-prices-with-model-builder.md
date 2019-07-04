---
title: Прогнозирование цен с помощью регрессии с использованием построителя моделей
description: В этом учебнике показано, как создать модель регрессии с помощью построителя моделей ML.NET, чтобы прогнозировать цены, в частности плату за проезд в такси по Нью-Йорку.
author: luisquintanilla
ms.author: luquinta
ms.date: 06/26/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: db9788e3065a0f2f21d712b2d4826efea2d8a829
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410582"
---
# <a name="predict-prices-using-regression-with-model-builder"></a><span data-ttu-id="89fbe-103">Прогнозирование цен с помощью регрессии с использованием построителя моделей</span><span class="sxs-lookup"><span data-stu-id="89fbe-103">Predict prices using regression with Model Builder</span></span>

<span data-ttu-id="89fbe-104">Узнайте, как с помощью построителя моделей ML.NET создать [модель регрессии](../resources/glossary.md#regression) для прогнозирования цен.</span><span class="sxs-lookup"><span data-stu-id="89fbe-104">Learn how to use ML.NET Model Builder to build a [regression model](../resources/glossary.md#regression) to predict prices.</span></span>  <span data-ttu-id="89fbe-105">Консольное приложение .NET, разрабатываемое в этом учебнике, прогнозирует плату за проезд в такси по Нью-Йорку на основе исторических данных.</span><span class="sxs-lookup"><span data-stu-id="89fbe-105">The .NET console app that you develop in this tutorial predicts taxi fares based on historical New York taxi fare data.</span></span>

<span data-ttu-id="89fbe-106">Шаблон прогнозирования цен, имеющийся в построителе моделей, можно использовать для любых сценариев, предполагающих прогнозирование числовых значений.</span><span class="sxs-lookup"><span data-stu-id="89fbe-106">The Model Builder price prediction template can be used for any scenario requiring a numerical prediction value.</span></span> <span data-ttu-id="89fbe-107">Примерами могут служить прогнозирование цен на недвижимость, спроса и продаж.</span><span class="sxs-lookup"><span data-stu-id="89fbe-107">Example scenarios include: house price prediction, demand prediction, and sales forecasting.</span></span>

<span data-ttu-id="89fbe-108">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="89fbe-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="89fbe-109">Подготовка и анализ данных</span><span class="sxs-lookup"><span data-stu-id="89fbe-109">Prepare and understand the data</span></span>
> * <span data-ttu-id="89fbe-110">Выбор сценария</span><span class="sxs-lookup"><span data-stu-id="89fbe-110">Choose a scenario</span></span>
> * <span data-ttu-id="89fbe-111">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="89fbe-111">Load the data</span></span>
> * <span data-ttu-id="89fbe-112">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="89fbe-112">Train the model</span></span>
> * <span data-ttu-id="89fbe-113">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="89fbe-113">Evaluate the model</span></span>
> * <span data-ttu-id="89fbe-114">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="89fbe-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="89fbe-115">Построитель моделей в настоящее время находится на этапе предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="89fbe-115">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="89fbe-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="89fbe-116">Pre-requisites</span></span>

<span data-ttu-id="89fbe-117">Список необходимых условий и инструкции по установке см. в [руководстве по установке построителя моделей](../how-to-guides/install-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="89fbe-117">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="89fbe-118">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="89fbe-118">Create a console application</span></span>

1. <span data-ttu-id="89fbe-119">Создайте **консольное приложение .NET Core** с именем TaxiFarePrediction.</span><span class="sxs-lookup"><span data-stu-id="89fbe-119">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

1. <span data-ttu-id="89fbe-120">Установите пакет NuGet для **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="89fbe-120">Install the **Microsoft.ML** NuGet Package:</span></span>

    <span data-ttu-id="89fbe-121">В **обозревателе решений** щелкните правой кнопкой мыши проект *TaxiFarePrediction* и выберите пункт **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="89fbe-121">In **Solution Explorer**, right-click the *TaxiFarePrediction* project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="89fbe-122">Выберите в качестве источника пакета "nuget.org", откройте вкладку **Обзор**, найдите **Microsoft.ML**, выберите пакет в списке и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="89fbe-122">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select the package in the list, and select the **Install** button.</span></span> <span data-ttu-id="89fbe-123">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="89fbe-123">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="89fbe-124">Подготовка и анализ данных</span><span class="sxs-lookup"><span data-stu-id="89fbe-124">Prepare and understand the data</span></span>

1. <span data-ttu-id="89fbe-125">Создайте каталог с именем *Data* в папке проекта, чтобы сохранить в нем файлы набора данных.</span><span class="sxs-lookup"><span data-stu-id="89fbe-125">Create a directory named *Data* in your project to store the data set files.</span></span>

1. <span data-ttu-id="89fbe-126">Скачайте набор данных [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) и сохраните его в папке *Data*, созданной в предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="89fbe-126">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) data set and save it to the *Data* folder you created at the previous step.</span></span> <span data-ttu-id="89fbe-127">Этот набор данных используется для обучения и оценки модели машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="89fbe-127">This data set is used to train and evaluate the machine learning model.</span></span> <span data-ttu-id="89fbe-128">Он взят из [набора данных NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span><span class="sxs-lookup"><span data-stu-id="89fbe-128">This data set is originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

1. <span data-ttu-id="89fbe-129">В **обозревателе решений** щелкните правой кнопкой мыши файл *taxi-fare-train.csv* и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="89fbe-129">In **Solution Explorer**, right-click the *taxi-fare-train.csv* file and select **Properties**.</span></span> <span data-ttu-id="89fbe-130">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="89fbe-130">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="89fbe-131">Каждая строка в наборе данных `taxi-fare-train.csv` содержит сведения о поездках в такси.</span><span class="sxs-lookup"><span data-stu-id="89fbe-131">Each row in the `taxi-fare-train.csv` data set contains details of trips made by a taxi.</span></span> 

1. <span data-ttu-id="89fbe-132">Откройте набор данных **taxi-fare-train.csv**.</span><span class="sxs-lookup"><span data-stu-id="89fbe-132">Open the **taxi-fare-train.csv** data set</span></span>

    <span data-ttu-id="89fbe-133">Предоставленный набор данных содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="89fbe-133">The provided data set contains the following columns:</span></span>

    * <span data-ttu-id="89fbe-134">**vendor_id:** идентификатор поставщика услуг такси — это признак.</span><span class="sxs-lookup"><span data-stu-id="89fbe-134">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
    * <span data-ttu-id="89fbe-135">**rate_code:** тип тарифа для поездки на такси — это признак.</span><span class="sxs-lookup"><span data-stu-id="89fbe-135">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
    * <span data-ttu-id="89fbe-136">**passenger_count:** число пассажиров в поездке — это признак.</span><span class="sxs-lookup"><span data-stu-id="89fbe-136">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
    * <span data-ttu-id="89fbe-137">**trip_time_in_secs:** время, затраченное на поездку.</span><span class="sxs-lookup"><span data-stu-id="89fbe-137">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="89fbe-138">Вам требуется спрогнозировать плату за одну поездку до того, как поездка будет завершена.</span><span class="sxs-lookup"><span data-stu-id="89fbe-138">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="89fbe-139">На этот момент вам неизвестна продолжительность поездки.</span><span class="sxs-lookup"><span data-stu-id="89fbe-139">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="89fbe-140">Таким образом, продолжительность поездки не является признаком и соответствующий столбец следует исключить из модели.</span><span class="sxs-lookup"><span data-stu-id="89fbe-140">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
    * <span data-ttu-id="89fbe-141">**trip_distance:** расстояние поездки — это признак.</span><span class="sxs-lookup"><span data-stu-id="89fbe-141">**trip_distance:** The distance of the trip is a feature.</span></span>
    * <span data-ttu-id="89fbe-142">**payment_type:** метод оплаты (наличные или кредитная карта) — это признак.</span><span class="sxs-lookup"><span data-stu-id="89fbe-142">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
    * <span data-ttu-id="89fbe-143">**fare_amount:** общая сумма, уплаченная за поездку на такси, — это метка.</span><span class="sxs-lookup"><span data-stu-id="89fbe-143">**fare_amount:** The total taxi fare paid is the label.</span></span>

<span data-ttu-id="89fbe-144">`label` — это столбец для прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="89fbe-144">The `label` is the column you want to predict.</span></span> <span data-ttu-id="89fbe-145">Цель задачи регрессии — прогнозирование числового значения.</span><span class="sxs-lookup"><span data-stu-id="89fbe-145">When performing a regression task, the goal is to predict a numerical value.</span></span> <span data-ttu-id="89fbe-146">В этом сценарии прогнозируется стоимость поездки в такси.</span><span class="sxs-lookup"><span data-stu-id="89fbe-146">In this price prediction scenario, the cost of a taxi ride is being predicted.</span></span> <span data-ttu-id="89fbe-147">Поэтому меткой является **fare_amount**.</span><span class="sxs-lookup"><span data-stu-id="89fbe-147">Therefore, the **fare_amount** is the label.</span></span> <span data-ttu-id="89fbe-148">Выбранные признаки (`features`) — это входные данные, которые вы предоставляете модели для прогнозирования метки (`label`).</span><span class="sxs-lookup"><span data-stu-id="89fbe-148">The identified `features` are the inputs you give the model to predict the `label`.</span></span> <span data-ttu-id="89fbe-149">В данном случае признаками или входными данными для прогнозирования стоимости поездки служат все остальные столбцы.</span><span class="sxs-lookup"><span data-stu-id="89fbe-149">In this case, the rest of the columns are used as features or inputs to predict the fare amount.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="89fbe-150">Выбор сценария</span><span class="sxs-lookup"><span data-stu-id="89fbe-150">Choose a scenario</span></span>

<span data-ttu-id="89fbe-151">Чтобы обучить модель, нужно выбрать один из доступных сценариев машинного обучения в построителе моделей.</span><span class="sxs-lookup"><span data-stu-id="89fbe-151">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> <span data-ttu-id="89fbe-152">В этом случае используется сценарий `Price Prediction`.</span><span class="sxs-lookup"><span data-stu-id="89fbe-152">In this case, the scenario is `Price Prediction`.</span></span> <span data-ttu-id="89fbe-153">Более полный список см. в [обзорной статье по построителю моделей](../automate-training-with-model-builder.md#scenarios).</span><span class="sxs-lookup"><span data-stu-id="89fbe-153">For a more extensive list visit the [Model Builder overview article](../automate-training-with-model-builder.md#scenarios).</span></span>

1. <span data-ttu-id="89fbe-154">В **обозревателе решений** щелкните правой кнопкой мыши проект *TaxiFarePrediction* и выберите **Добавить** > **Машинное обучение**.</span><span class="sxs-lookup"><span data-stu-id="89fbe-154">In **Solution Explorer**, right-click the *TaxiFarePrediction* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="89fbe-155">На этапе выбора сценария выберите *Прогнозирование цен*.</span><span class="sxs-lookup"><span data-stu-id="89fbe-155">In the scenario step of the Model Builder tool, select *Price Prediction* scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="89fbe-156">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="89fbe-156">Load the data</span></span>

<span data-ttu-id="89fbe-157">Построитель моделей принимает данные из двух источников: базы данных SQL Server либо локального файла CSV или TSV.</span><span class="sxs-lookup"><span data-stu-id="89fbe-157">Model Builder accepts data from two sources, a SQL Server database or a local file csv or tsv file.</span></span> <span data-ttu-id="89fbe-158">Дополнительные сведения о требованиях к формату данных см. [здесь](../how-to-guides/install-model-builder.md#limitations).</span><span class="sxs-lookup"><span data-stu-id="89fbe-158">For more information on data format requirements, visit the following [link](../how-to-guides/install-model-builder.md#limitations).</span></span>

1. <span data-ttu-id="89fbe-159">На этапе добавления данных выберите в раскрывающемся списке источников данных пункт *Прогнозирование цен*.</span><span class="sxs-lookup"><span data-stu-id="89fbe-159">In the data step of the Model Builder tool, select *File* from the data source dropdown.</span></span>
1. <span data-ttu-id="89fbe-160">Нажмите кнопку рядом с текстовым полем *Выберите файл* и выберите в проводнике файл *taxi-fare-test.csv* в каталоге *Data*.</span><span class="sxs-lookup"><span data-stu-id="89fbe-160">Select the button next to the *Select a file* text box and use File Explorer to browse and select the *taxi-fare-test.csv* in the *Data* directory</span></span>
1. <span data-ttu-id="89fbe-161">В раскрывающемся списке *Метка или прогнозируемый столбец* выберите *fare_amount* и перейдите к шагу обучения в построителе моделей.</span><span class="sxs-lookup"><span data-stu-id="89fbe-161">Choose *fare_amount* in the *Label or Column to Predict* dropdown and navigate to the train step of the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="89fbe-162">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="89fbe-162">Train the model</span></span>

<span data-ttu-id="89fbe-163">Задачей машинного обучения, используемой в этом учебнике для обучения модели прогнозирования цен, является регрессия.</span><span class="sxs-lookup"><span data-stu-id="89fbe-163">The machine learning task used to train the price prediction model in this tutorial is regression.</span></span> <span data-ttu-id="89fbe-164">В процессе обучения построитель моделей обучает отдельные модели с помощью различных алгоритмов и параметров регрессии, определяя оптимальную модель для вашего набора данных.</span><span class="sxs-lookup"><span data-stu-id="89fbe-164">During the model training process, Model Builder trains separate models using different regression algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="89fbe-165">Время, требуемое для обучения модели, пропорционально объему данных.</span><span class="sxs-lookup"><span data-stu-id="89fbe-165">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="89fbe-166">Чтобы выбрать подходящее значение для поля `Time to train (seconds)`, можно опираться на следующую таблицу:</span><span class="sxs-lookup"><span data-stu-id="89fbe-166">Use this chart as guidance to select an adequate value for the `Time to train (seconds)` field:</span></span>

<span data-ttu-id="89fbe-167">Размер набора данных</span><span class="sxs-lookup"><span data-stu-id="89fbe-167">\*Dataset Size</span></span>  | <span data-ttu-id="89fbe-168">Тип набора данных</span><span class="sxs-lookup"><span data-stu-id="89fbe-168">Dataset Type</span></span>       | <span data-ttu-id="89fbe-169">Среднее Время обучения</span><span class="sxs-lookup"><span data-stu-id="89fbe-169">Avg. Time to train\*</span></span>
------------- | ------------------ | --------------
<span data-ttu-id="89fbe-170">0–10 МБ</span><span class="sxs-lookup"><span data-stu-id="89fbe-170">0 - 10 Mb</span></span>     | <span data-ttu-id="89fbe-171">Числа и текст</span><span class="sxs-lookup"><span data-stu-id="89fbe-171">Numeric and Text</span></span>   | <span data-ttu-id="89fbe-172">10 с</span><span class="sxs-lookup"><span data-stu-id="89fbe-172">10 sec</span></span>
<span data-ttu-id="89fbe-173">10–100 МБ</span><span class="sxs-lookup"><span data-stu-id="89fbe-173">10 - 100 Mb</span></span>   | <span data-ttu-id="89fbe-174">Числа и текст</span><span class="sxs-lookup"><span data-stu-id="89fbe-174">Numeric and Text</span></span>   | <span data-ttu-id="89fbe-175">10 мин</span><span class="sxs-lookup"><span data-stu-id="89fbe-175">10 min</span></span>
<span data-ttu-id="89fbe-176">100–500 МБ</span><span class="sxs-lookup"><span data-stu-id="89fbe-176">100 - 500 Mb</span></span>  | <span data-ttu-id="89fbe-177">Числа и текст</span><span class="sxs-lookup"><span data-stu-id="89fbe-177">Numeric and Text</span></span>   | <span data-ttu-id="89fbe-178">30 мин</span><span class="sxs-lookup"><span data-stu-id="89fbe-178">30 min</span></span>
<span data-ttu-id="89fbe-179">500 МБ — 1 ГБ</span><span class="sxs-lookup"><span data-stu-id="89fbe-179">500 - 1 Gb</span></span>    | <span data-ttu-id="89fbe-180">Числа и текст</span><span class="sxs-lookup"><span data-stu-id="89fbe-180">Numeric and Text</span></span>   | <span data-ttu-id="89fbe-181">60 мин</span><span class="sxs-lookup"><span data-stu-id="89fbe-181">60 min</span></span>
<span data-ttu-id="89fbe-182">Более 1 ГБ</span><span class="sxs-lookup"><span data-stu-id="89fbe-182">1 Gb+</span></span>         | <span data-ttu-id="89fbe-183">Числа и текст</span><span class="sxs-lookup"><span data-stu-id="89fbe-183">Numeric and Text</span></span>   | <span data-ttu-id="89fbe-184">Более 3 часов</span><span class="sxs-lookup"><span data-stu-id="89fbe-184">3 hour+</span></span>

1. <span data-ttu-id="89fbe-185">Так как размер файла с данными для обучения превышает 10 МБ, используйте для поля *Время обучения (в секундах)* значение 600 секунд (10 минут).</span><span class="sxs-lookup"><span data-stu-id="89fbe-185">Because the training data file is more than 10MB, use 600 seconds (10 minutes) as the value for *Time to train (seconds)*.</span></span>
2. <span data-ttu-id="89fbe-186">Выберите *Начать обучение*.</span><span class="sxs-lookup"><span data-stu-id="89fbe-186">Select *Start Training*.</span></span>

<span data-ttu-id="89fbe-187">В процессе обучения сведения о ходе выполнения отображаются в разделе `Progress` шага обучения.</span><span class="sxs-lookup"><span data-stu-id="89fbe-187">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

- <span data-ttu-id="89fbe-188">"Состояние" — это состояние завершения процесса обучения.</span><span class="sxs-lookup"><span data-stu-id="89fbe-188">Status displays the completion status of the training process.</span></span>
- <span data-ttu-id="89fbe-189">"Наибольшая точность" — это точность модели, которая на данный момент определена построителем моделей как лучшая.</span><span class="sxs-lookup"><span data-stu-id="89fbe-189">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="89fbe-190">Точность зависит от того, насколько правильный прогноз был сделан моделью на основе тестовых данных.</span><span class="sxs-lookup"><span data-stu-id="89fbe-190">Higher accuracy means the model predicted more correctly on test data.</span></span> 
- <span data-ttu-id="89fbe-191">"Лучший алгоритм" — это название алгоритма, который на данный момент определен построителем моделей как лучший.</span><span class="sxs-lookup"><span data-stu-id="89fbe-191">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
- <span data-ttu-id="89fbe-192">"Последний алгоритм" — это название алгоритма, который использовался построителем моделей для обучения модели последним.</span><span class="sxs-lookup"><span data-stu-id="89fbe-192">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

<span data-ttu-id="89fbe-193">По завершении обучения перейдите к шагу оценки.</span><span class="sxs-lookup"><span data-stu-id="89fbe-193">Once training is complete, navigate to the evaluate step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="89fbe-194">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="89fbe-194">Evaluate the model</span></span>

<span data-ttu-id="89fbe-195">Результат обучения — одна модель с наивысшей точностью.</span><span class="sxs-lookup"><span data-stu-id="89fbe-195">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="89fbe-196">В шаге оценки в разделе результатов будет указан алгоритм, используемый оптимальной моделью, в поле *Лучшая модель*, а также метрики в поле *Качество лучшей модели (достоверность аппроксимации)* .</span><span class="sxs-lookup"><span data-stu-id="89fbe-196">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the *Best Model* entry along with metrics in *Best Model Quality (RSquared)*.</span></span> <span data-ttu-id="89fbe-197">Кроме того, приводится сводная таблица с пятью лучшими моделями и их метриками.</span><span class="sxs-lookup"><span data-stu-id="89fbe-197">Additionally, a summary table containing top five models and their metrics.</span></span> <span data-ttu-id="89fbe-198">Дополнительные сведения об оценке метрик модели см. [здесь](https://docs.microsoft.com/dotnet/machine-learning/resources/metrics).</span><span class="sxs-lookup"><span data-stu-id="89fbe-198">Visit the following link to learn more about [evaluating model metrics](https://docs.microsoft.com/dotnet/machine-learning/resources/metrics).</span></span>

<span data-ttu-id="89fbe-199">Если вас не удовлетворяют метрики точности, самые простые способы повысить точность модели — увеличить длительность обучения или использовать больше данных.</span><span class="sxs-lookup"><span data-stu-id="89fbe-199">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span>

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="89fbe-200">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="89fbe-200">Use the model for predictions</span></span>

<span data-ttu-id="89fbe-201">В результате процесса обучения создаются два проекта.</span><span class="sxs-lookup"><span data-stu-id="89fbe-201">Two projects will be created as a result of the training process.</span></span>

- <span data-ttu-id="89fbe-202">TaxiFarePredictionML.ConsoleApp: консольное приложение .NET с кодом обучения и использования модели.</span><span class="sxs-lookup"><span data-stu-id="89fbe-202">TaxiFarePredictionML.ConsoleApp: A .NET Console application that contains the model training and consumption code.</span></span>
- <span data-ttu-id="89fbe-203">TaxiFarePredictionML.Model: библиотека классов .NET Standard с моделями данных, которые определяют схему входных и выходных данных модели, а также хранимую версию оптимальной модели.</span><span class="sxs-lookup"><span data-stu-id="89fbe-203">TaxiFarePredictionML.Model: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the persisted version of the best performing model during training.</span></span>

1. <span data-ttu-id="89fbe-204">В разделе кода в построителе моделей выберите элемент **Добавленные проекты**, чтобы добавить проекты в решение.</span><span class="sxs-lookup"><span data-stu-id="89fbe-204">In the code section of the Model Builder tool, select **Added Projects** to add the projects to the solution.</span></span>
1. <span data-ttu-id="89fbe-205">В обозревателе решений щелкните правой кнопкой мыши проект *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="89fbe-205">In solution explorer, right-click the *TaxiFarePrediction* project.</span></span> <span data-ttu-id="89fbe-206">Затем выберите **Добавить > Существующий элемент**.</span><span class="sxs-lookup"><span data-stu-id="89fbe-206">Then, select **Add > Existing Item**.</span></span> <span data-ttu-id="89fbe-207">В раскрывающемся списке типов файлов выберите пункт `All Files` (Все файлы), перейдите в каталог проекта *TaxiFarePredictionML.Model* и выберите файл `MLModel.zip`.</span><span class="sxs-lookup"><span data-stu-id="89fbe-207">For file type drop down, select `All Files`, navigate to the *TaxiFarePredictionML.Model* project directory and select the `MLModel.zip` file.</span></span> <span data-ttu-id="89fbe-208">Затем щелкните добавленный файл `MLModel.zip` правой кнопкой мыши и выберите пункт *Свойства*.</span><span class="sxs-lookup"><span data-stu-id="89fbe-208">Then right-click the recently added `MLModel.zip` file and select *Properties*.</span></span> <span data-ttu-id="89fbe-209">Для параметра "Копировать в выходной каталог" выберите в раскрывающемся списке пункт *Копировать, если новее*.</span><span class="sxs-lookup"><span data-stu-id="89fbe-209">For the Copy to Output Directory option, select *Copy if Newer* from the dropdown.</span></span>
1. <span data-ttu-id="89fbe-210">Щелкните правой кнопкой мыши проект *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="89fbe-210">Right-click *TaxiFarePrediction* project.</span></span> <span data-ttu-id="89fbe-211">Выберите **Добавить > Ссылка**.</span><span class="sxs-lookup"><span data-stu-id="89fbe-211">Then, **Add > Reference**.</span></span> <span data-ttu-id="89fbe-212">Выберите узел **Проекты > Решение**, установите в списке флажок рядом с проектом *TaxiFarePredictionML.Model* и нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="89fbe-212">Choose the **Projects > Solution** node and from the list, check the *TaxiFarePredictionML.Model* project and select OK.</span></span>

4. <span data-ttu-id="89fbe-213">Откройте файл *Program.cs* в проекте *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="89fbe-213">Open the *Program.cs* file in the *TaxiFarePrediction* project.</span></span>
5. <span data-ttu-id="89fbe-214">Добавьте операторы using:</span><span class="sxs-lookup"><span data-stu-id="89fbe-214">Add the following using statements:</span></span>

    ```csharp
    using System;
    using Microsoft.ML;
    using TaxiFarePredictionML.Model.DataModels;
    ```

6. <span data-ttu-id="89fbe-215">Добавьте метод `ConsumeModel` в класс `Program`.</span><span class="sxs-lookup"><span data-stu-id="89fbe-215">Add the `ConsumeModel` method to the `Program` class.</span></span> <span data-ttu-id="89fbe-216">Метод `ConsumeModel` создаст `PredictionEngine` на основе модели, созданной построителем моделей, с целью составления прогнозов на основе новых данных и вывода их в консоль.</span><span class="sxs-lookup"><span data-stu-id="89fbe-216">The `ConsumeModel` will create a `PredictionEngine` based on the model generated by Model Builder to make predictions on new data and print them out to the console.</span></span>

    ```csharp
    static ModelOutput ConsumeModel(ModelInput input)
    {
        // 1. Load the model
        MLContext mlContext = new MLContext();
        ITransformer mlModel = mlContext.Model.Load("MLModel.zip", out var modelInputSchema);

        // 2. Create PredictionEngine
        var predictionEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(mlModel);

        // 3. Use PredictionEngine to use model on input data
        ModelOutput result = predictionEngine.Predict(input);

        // 4. Return prediction result
        return result;
    }
    ```

7. <span data-ttu-id="89fbe-217">Добавьте в метод `Main` приведенный ниже код и запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="89fbe-217">Add the following code to the `Main` method and run the application.</span></span>

    ```csharp
    // Create sample data
    ModelInput input = new ModelInput()
    {
        Vendor_id = "CMT",
        Rate_code = 1,
        Passenger_count = 1,
        Trip_time_in_secs = 1271,
        Trip_distance = 3.8f,
        Payment_type = "CRD"
    };

    // Make prediction
    ModelOutput prediction = ConsumeModel(input);

    // Print Prediction
    Console.WriteLine($"Predicted Fare: {prediction.Score}");
    Console.ReadKey();
    ```

    <span data-ttu-id="89fbe-218">Выходные данные программы должны выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="89fbe-218">The output generated by the program should look similar to the snippet below:</span></span>

    ```bash
    Predicted Fare: 16.82245
    ```

<span data-ttu-id="89fbe-219">Если на созданные проекты нужно будет сослаться позднее в другом решении, их можно найти в каталоге `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.</span><span class="sxs-lookup"><span data-stu-id="89fbe-219">If you need to reference the generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="89fbe-220">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="89fbe-220">Next Steps</span></span>

<span data-ttu-id="89fbe-221">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="89fbe-221">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="89fbe-222">Подготовка и анализ данных</span><span class="sxs-lookup"><span data-stu-id="89fbe-222">Prepare and understand the data</span></span>
> * <span data-ttu-id="89fbe-223">Выбор сценария</span><span class="sxs-lookup"><span data-stu-id="89fbe-223">Choose a scenario</span></span>
> * <span data-ttu-id="89fbe-224">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="89fbe-224">Load the data</span></span>
> * <span data-ttu-id="89fbe-225">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="89fbe-225">Train the model</span></span>
> * <span data-ttu-id="89fbe-226">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="89fbe-226">Evaluate the model</span></span>
> * <span data-ttu-id="89fbe-227">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="89fbe-227">Use the model for predictions</span></span>

<span data-ttu-id="89fbe-228">Перейдите к одному из следующих руководств, чтобы узнать, как развернуть модель:</span><span class="sxs-lookup"><span data-stu-id="89fbe-228">Advance to either of the following how-to articles to learn how to deploy your model.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="89fbe-229">Развертывание модели в Функциях Azure</span><span class="sxs-lookup"><span data-stu-id="89fbe-229">Deploy a model to Azure Functions</span></span>](../how-to-guides/serve-model-serverless-azure-functions-ml-net.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="89fbe-230">Развертывание модели в веб-API</span><span class="sxs-lookup"><span data-stu-id="89fbe-230">Deploy a model to a Web API</span></span>](../how-to-guides/serve-model-web-api-ml-net.md)
