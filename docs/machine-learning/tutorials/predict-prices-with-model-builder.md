---
title: Учебник. Прогнозирование цен с помощью регрессии с использованием построителя моделей
description: В этом учебнике показано, как создать модель регрессии с помощью построителя моделей ML.NET, чтобы прогнозировать цены, в частности плату за проезд в такси по Нью-Йорку.
author: luisquintanilla
ms.author: luquinta
ms.date: 10/08/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: bd6acd83df4d2d5f19d30da847212d60b1576199
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977356"
---
# <a name="tutorial-predict-prices-using-regression-with-model-builder"></a><span data-ttu-id="fbca7-103">Учебник. Прогнозирование цен с помощью регрессии с использованием построителя моделей</span><span class="sxs-lookup"><span data-stu-id="fbca7-103">Tutorial: Predict prices using regression with Model Builder</span></span>

<span data-ttu-id="fbca7-104">Узнайте, как с помощью построителя моделей ML.NET создать модель регрессии для прогнозирования цен.</span><span class="sxs-lookup"><span data-stu-id="fbca7-104">Learn how to use ML.NET Model Builder to build a regression model to predict prices.</span></span>  <span data-ttu-id="fbca7-105">Консольное приложение .NET, разрабатываемое в этом учебнике, прогнозирует плату за проезд в такси по Нью-Йорку на основе исторических данных.</span><span class="sxs-lookup"><span data-stu-id="fbca7-105">The .NET console app that you develop in this tutorial predicts taxi fares based on historical New York taxi fare data.</span></span>

<span data-ttu-id="fbca7-106">Шаблон прогнозирования цен, имеющийся в построителе моделей, можно использовать для любых сценариев, предполагающих прогнозирование числовых значений.</span><span class="sxs-lookup"><span data-stu-id="fbca7-106">The Model Builder price prediction template can be used for any scenario requiring a numerical prediction value.</span></span> <span data-ttu-id="fbca7-107">Примерами могут служить прогнозирование цен на недвижимость, спроса и продаж.</span><span class="sxs-lookup"><span data-stu-id="fbca7-107">Example scenarios include: house price prediction, demand prediction, and sales forecasting.</span></span>

<span data-ttu-id="fbca7-108">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="fbca7-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="fbca7-109">Подготовка и анализ данных</span><span class="sxs-lookup"><span data-stu-id="fbca7-109">Prepare and understand the data</span></span>
> - <span data-ttu-id="fbca7-110">Выбор сценария</span><span class="sxs-lookup"><span data-stu-id="fbca7-110">Choose a scenario</span></span>
> - <span data-ttu-id="fbca7-111">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="fbca7-111">Load the data</span></span>
> - <span data-ttu-id="fbca7-112">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="fbca7-112">Train the model</span></span>
> - <span data-ttu-id="fbca7-113">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="fbca7-113">Evaluate the model</span></span>
> - <span data-ttu-id="fbca7-114">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="fbca7-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="fbca7-115">Построитель моделей в настоящее время находится на этапе предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="fbca7-115">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="fbca7-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="fbca7-116">Pre-requisites</span></span>

<span data-ttu-id="fbca7-117">Список необходимых условий и инструкции по установке см. в [руководстве по установке построителя моделей](../how-to-guides/install-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="fbca7-117">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="fbca7-118">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="fbca7-118">Create a console application</span></span>

1. <span data-ttu-id="fbca7-119">Создайте **консольное приложение .NET Core** с именем TaxiFarePrediction.</span><span class="sxs-lookup"><span data-stu-id="fbca7-119">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="fbca7-120">Подготовка и анализ данных</span><span class="sxs-lookup"><span data-stu-id="fbca7-120">Prepare and understand the data</span></span>

1. <span data-ttu-id="fbca7-121">Создайте каталог с именем *Data* в папке проекта, чтобы сохранить в нем файлы набора данных.</span><span class="sxs-lookup"><span data-stu-id="fbca7-121">Create a directory named *Data* in your project to store the data set files.</span></span>

1. <span data-ttu-id="fbca7-122">Набор данных, используемый для обучения и оценки модели машинного обучения, создан на основе данных Комиссии по лицензированию перевозок автотранспортом города Нью-Йорк (TLC).</span><span class="sxs-lookup"><span data-stu-id="fbca7-122">The data set used to train and evaluate the machine learning model is originally from the NYC TLC Taxi Trip data set.</span></span>

    1. <span data-ttu-id="fbca7-123">Скачать набор данных можно по [этой ссылке](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).</span><span class="sxs-lookup"><span data-stu-id="fbca7-123">To download the data set, navigate to the [taxi-fare-train.csv download link](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).</span></span>

    1. <span data-ttu-id="fbca7-124">При загрузке страницы щелкните правой кнопкой мыши в любом месте и выберите в меню команду **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="fbca7-124">When the page loads, right-click anywhere on the page and select **Save as**.</span></span>

    1. <span data-ttu-id="fbca7-125">В диалоговом окне **Сохранить как** сохраните файл в созданную ранее папку *Data*.</span><span class="sxs-lookup"><span data-stu-id="fbca7-125">Use the **Save As Dialog** to save the file in the *Data* folder you created at the previous step.</span></span>

1. <span data-ttu-id="fbca7-126">В **обозревателе решений** щелкните правой кнопкой мыши файл *taxi-fare-train.csv* и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="fbca7-126">In **Solution Explorer**, right-click the *taxi-fare-train.csv* file and select **Properties**.</span></span> <span data-ttu-id="fbca7-127">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="fbca7-127">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="fbca7-128">Каждая строка в наборе данных `taxi-fare-train.csv` содержит сведения о поездках в такси.</span><span class="sxs-lookup"><span data-stu-id="fbca7-128">Each row in the `taxi-fare-train.csv` data set contains details of trips made by a taxi.</span></span>

1. <span data-ttu-id="fbca7-129">Откройте набор данных **taxi-fare-train.csv**.</span><span class="sxs-lookup"><span data-stu-id="fbca7-129">Open the **taxi-fare-train.csv** data set</span></span>

    <span data-ttu-id="fbca7-130">Предоставленный набор данных содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="fbca7-130">The provided data set contains the following columns:</span></span>

    - <span data-ttu-id="fbca7-131">**vendor_id:** идентификатор поставщика услуг такси — это признак.</span><span class="sxs-lookup"><span data-stu-id="fbca7-131">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
    - <span data-ttu-id="fbca7-132">**rate_code:** тип тарифа для поездки на такси — это признак.</span><span class="sxs-lookup"><span data-stu-id="fbca7-132">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
    - <span data-ttu-id="fbca7-133">**passenger_count:** число пассажиров в поездке — это признак.</span><span class="sxs-lookup"><span data-stu-id="fbca7-133">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
    - <span data-ttu-id="fbca7-134">**trip_time_in_secs:** время, затраченное на поездку.</span><span class="sxs-lookup"><span data-stu-id="fbca7-134">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="fbca7-135">Вам требуется спрогнозировать плату за одну поездку до того, как поездка будет завершена.</span><span class="sxs-lookup"><span data-stu-id="fbca7-135">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="fbca7-136">На этот момент вам неизвестна продолжительность поездки.</span><span class="sxs-lookup"><span data-stu-id="fbca7-136">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="fbca7-137">Таким образом, продолжительность поездки не является признаком и соответствующий столбец следует исключить из модели.</span><span class="sxs-lookup"><span data-stu-id="fbca7-137">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
    - <span data-ttu-id="fbca7-138">**trip_distance:** расстояние поездки — это признак.</span><span class="sxs-lookup"><span data-stu-id="fbca7-138">**trip_distance:** The distance of the trip is a feature.</span></span>
    - <span data-ttu-id="fbca7-139">**payment_type:** метод оплаты (наличные или кредитная карта) — это признак.</span><span class="sxs-lookup"><span data-stu-id="fbca7-139">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
    - <span data-ttu-id="fbca7-140">**fare_amount:** общая сумма, уплаченная за поездку на такси, — это метка.</span><span class="sxs-lookup"><span data-stu-id="fbca7-140">**fare_amount:** The total taxi fare paid is the label.</span></span>

<span data-ttu-id="fbca7-141">`label` — это столбец для прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="fbca7-141">The `label` is the column you want to predict.</span></span> <span data-ttu-id="fbca7-142">Цель задачи регрессии — прогнозирование числового значения.</span><span class="sxs-lookup"><span data-stu-id="fbca7-142">When performing a regression task, the goal is to predict a numerical value.</span></span> <span data-ttu-id="fbca7-143">В этом сценарии прогнозируется стоимость поездки в такси.</span><span class="sxs-lookup"><span data-stu-id="fbca7-143">In this price prediction scenario, the cost of a taxi ride is being predicted.</span></span> <span data-ttu-id="fbca7-144">Поэтому меткой является **fare_amount**.</span><span class="sxs-lookup"><span data-stu-id="fbca7-144">Therefore, the **fare_amount** is the label.</span></span> <span data-ttu-id="fbca7-145">Выбранные признаки (`features`) — это входные данные, которые вы предоставляете модели для прогнозирования метки (`label`).</span><span class="sxs-lookup"><span data-stu-id="fbca7-145">The identified `features` are the inputs you give the model to predict the `label`.</span></span> <span data-ttu-id="fbca7-146">В этом случае остальные столбцы, исключая **trip_time_in_secs**, используются в качестве признаков или входных данных для прогнозирования стоимости поездки.</span><span class="sxs-lookup"><span data-stu-id="fbca7-146">In this case, the rest of the columns with the exception of **trip_time_in_secs** are used as features or inputs to predict the fare amount.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="fbca7-147">Выбор сценария</span><span class="sxs-lookup"><span data-stu-id="fbca7-147">Choose a scenario</span></span>

<span data-ttu-id="fbca7-148">Чтобы обучить модель, нужно выбрать один из доступных сценариев машинного обучения в построителе моделей.</span><span class="sxs-lookup"><span data-stu-id="fbca7-148">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> <span data-ttu-id="fbca7-149">В этом случае используется сценарий `Price Prediction`.</span><span class="sxs-lookup"><span data-stu-id="fbca7-149">In this case, the scenario is `Price Prediction`.</span></span>

1. <span data-ttu-id="fbca7-150">В **обозревателе решений** щелкните правой кнопкой мыши проект *TaxiFarePrediction* и выберите **Добавить** > **Машинное обучение**.</span><span class="sxs-lookup"><span data-stu-id="fbca7-150">In **Solution Explorer**, right-click the *TaxiFarePrediction* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="fbca7-151">На этапе выбора сценария выберите *Прогнозирование цен*.</span><span class="sxs-lookup"><span data-stu-id="fbca7-151">In the scenario step of the Model Builder tool, select *Price Prediction* scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="fbca7-152">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="fbca7-152">Load the data</span></span>

<span data-ttu-id="fbca7-153">Построитель моделей принимает данные из двух источников: базы данных SQL Server или локального файла в формате CSV или TSV.</span><span class="sxs-lookup"><span data-stu-id="fbca7-153">Model Builder accepts data from two sources, a SQL Server database or a local file in csv or tsv format.</span></span>

1. <span data-ttu-id="fbca7-154">На этапе добавления данных выберите в раскрывающемся списке источников данных пункт *Прогнозирование цен*.</span><span class="sxs-lookup"><span data-stu-id="fbca7-154">In the data step of the Model Builder tool, select *File* from the data source dropdown.</span></span>
1. <span data-ttu-id="fbca7-155">Нажмите кнопку рядом с текстовым полем *Выберите файл* и выберите в проводнике файл *taxi-fare-test.csv* в каталоге *Data*.</span><span class="sxs-lookup"><span data-stu-id="fbca7-155">Select the button next to the *Select a file* text box and use File Explorer to browse and select the *taxi-fare-test.csv* in the *Data* directory</span></span>
1. <span data-ttu-id="fbca7-156">Выберите *fare_amount* в раскрывающемся списке *Column to Predict (Label)* (Метка для прогнозирования (или столбец)).</span><span class="sxs-lookup"><span data-stu-id="fbca7-156">Choose *fare_amount* in the *Column to Predict (Label)* dropdown.</span></span>
1. <span data-ttu-id="fbca7-157">Разверните раскрывающийся список *Входные столбцы (признаки)* и снимите флажок в столбце *trip_time_in_secs*, чтобы исключить его в качестве признака во время обучения.</span><span class="sxs-lookup"><span data-stu-id="fbca7-157">Expand the *Input Columns (Features)* dropdown and uncheck the *trip_time_in_secs* column to exclude it as a feature during training.</span></span>  <span data-ttu-id="fbca7-158">Перейдите к этапу обучение средства создания модели.</span><span class="sxs-lookup"><span data-stu-id="fbca7-158">Navigate to the train step of the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="fbca7-159">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="fbca7-159">Train the model</span></span>

<span data-ttu-id="fbca7-160">Задачей машинного обучения, используемой в этом учебнике для обучения модели прогнозирования цен, является регрессия.</span><span class="sxs-lookup"><span data-stu-id="fbca7-160">The machine learning task used to train the price prediction model in this tutorial is regression.</span></span> <span data-ttu-id="fbca7-161">В процессе обучения построитель моделей обучает отдельные модели с помощью различных алгоритмов и параметров регрессии, определяя оптимальную модель для вашего набора данных.</span><span class="sxs-lookup"><span data-stu-id="fbca7-161">During the model training process, Model Builder trains separate models using different regression algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="fbca7-162">Время, требуемое для обучения модели, пропорционально объему данных.</span><span class="sxs-lookup"><span data-stu-id="fbca7-162">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="fbca7-163">Построитель моделей автоматически выбирает значение по умолчанию для параметра **Time to train (seconds)** (Время обучения в секундах) в зависимости от размера источника данных.</span><span class="sxs-lookup"><span data-stu-id="fbca7-163">Model Builder automatically selects a default value for **Time to train (seconds)** based on the size of your data source.</span></span>

1. <span data-ttu-id="fbca7-164">Оставьте значение по умолчанию для параметра *Time to train (seconds)* (Время обучения в секундах), если только вы не хотите проводить обучение более длительное время.</span><span class="sxs-lookup"><span data-stu-id="fbca7-164">Leave the default value as is for *Time to train (seconds)* unless you prefer to train for a longer time.</span></span>
2. <span data-ttu-id="fbca7-165">Выберите *Начать обучение*.</span><span class="sxs-lookup"><span data-stu-id="fbca7-165">Select *Start Training*.</span></span>

<span data-ttu-id="fbca7-166">В процессе обучения сведения о ходе выполнения отображаются в разделе `Progress` шага обучения.</span><span class="sxs-lookup"><span data-stu-id="fbca7-166">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

- <span data-ttu-id="fbca7-167">"Состояние" — это состояние завершения процесса обучения.</span><span class="sxs-lookup"><span data-stu-id="fbca7-167">Status displays the completion status of the training process.</span></span>
- <span data-ttu-id="fbca7-168">"Наибольшая точность" — это точность модели, которая на данный момент определена построителем моделей как лучшая.</span><span class="sxs-lookup"><span data-stu-id="fbca7-168">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="fbca7-169">Точность зависит от того, насколько правильный прогноз был сделан моделью на основе тестовых данных.</span><span class="sxs-lookup"><span data-stu-id="fbca7-169">Higher accuracy means the model predicted more correctly on test data.</span></span>
- <span data-ttu-id="fbca7-170">"Лучший алгоритм" — это название алгоритма, который на данный момент определен построителем моделей как лучший.</span><span class="sxs-lookup"><span data-stu-id="fbca7-170">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
- <span data-ttu-id="fbca7-171">"Последний алгоритм" — это название алгоритма, который использовался построителем моделей для обучения модели последним.</span><span class="sxs-lookup"><span data-stu-id="fbca7-171">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

<span data-ttu-id="fbca7-172">По завершении обучения перейдите к шагу оценки.</span><span class="sxs-lookup"><span data-stu-id="fbca7-172">Once training is complete, navigate to the evaluate step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="fbca7-173">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="fbca7-173">Evaluate the model</span></span>

<span data-ttu-id="fbca7-174">Результат обучения — одна модель с наивысшей точностью.</span><span class="sxs-lookup"><span data-stu-id="fbca7-174">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="fbca7-175">В шаге оценки в разделе результатов будет указан алгоритм, используемый оптимальной моделью, в поле *Лучшая модель*, а также метрики в поле *Качество лучшей модели (достоверность аппроксимации)* .</span><span class="sxs-lookup"><span data-stu-id="fbca7-175">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the *Best Model* entry along with metrics in *Best Model Quality (RSquared)*.</span></span> <span data-ttu-id="fbca7-176">Кроме того, приводится сводная таблица с пятью лучшими моделями и их метриками.</span><span class="sxs-lookup"><span data-stu-id="fbca7-176">Additionally, a summary table containing top five models and their metrics.</span></span>

<span data-ttu-id="fbca7-177">Если вас не удовлетворяют метрики точности, самые простые способы повысить точность модели — увеличить длительность обучения или использовать больше данных.</span><span class="sxs-lookup"><span data-stu-id="fbca7-177">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="fbca7-178">Если все в порядке, переходите к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="fbca7-178">Otherwise, navigate to the code step.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="fbca7-179">Добавление кода для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="fbca7-179">Add the code to make predictions</span></span>

<span data-ttu-id="fbca7-180">В результате процесса обучения создаются два проекта.</span><span class="sxs-lookup"><span data-stu-id="fbca7-180">Two projects will be created as a result of the training process.</span></span>

- <span data-ttu-id="fbca7-181">TaxiFarePredictionML.ConsoleApp: консольное приложение .NET Core с кодом обучения и примера использования модели.</span><span class="sxs-lookup"><span data-stu-id="fbca7-181">TaxiFarePredictionML.ConsoleApp: A .NET Core Console application that contains the model training and sample consumption code.</span></span>
- <span data-ttu-id="fbca7-182">TaxiFarePredictionML.Model: библиотека классов .NET Standard с моделями данных, которые определяют схему входных и выходных данных модели, а также хранимую версию оптимальной модели во время обучения и вспомогательный класс с именем `ConsumeModel` для формирования прогнозов.</span><span class="sxs-lookup"><span data-stu-id="fbca7-182">TaxiFarePredictionML.Model: A .NET Standard class library containing the data models that define the schema of input and output model data, the saved version of the best performing model during training and a helper class called `ConsumeModel` to make predictions.</span></span>

1. <span data-ttu-id="fbca7-183">На шаге добавления кода в построителе моделей выберите **Добавить проекты**, чтобы добавить автоматически созданные проекты в решение.</span><span class="sxs-lookup"><span data-stu-id="fbca7-183">In the code step of the Model Builder tool, select **Add Projects** to add the auto-generated projects to the solution.</span></span>
1. <span data-ttu-id="fbca7-184">Откройте файл *Program.cs* в проекте *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="fbca7-184">Open the *Program.cs* file in the *TaxiFarePrediction* project.</span></span>
1. <span data-ttu-id="fbca7-185">Добавьте следующее, используя оператор для ссылки на проект *TaxiFarePredictionML.Model*:</span><span class="sxs-lookup"><span data-stu-id="fbca7-185">Add the following using statement to reference the *TaxiFarePredictionML.Model* project:</span></span>

    ```csharp
    using System;
    using TaxiFarePredictionML.Model;
    ```

1. <span data-ttu-id="fbca7-186">Чтобы сделать прогноз на основе новых данных с помощью модели, создайте новый экземпляр класса `ModelInput` внутри метода `Main` приложения.</span><span class="sxs-lookup"><span data-stu-id="fbca7-186">To make a prediction on new data using the model, create a new instance of the `ModelInput` class inside the `Main` method of your application.</span></span> <span data-ttu-id="fbca7-187">Обратите внимание, что данные о суммах, уплаченных за поездку на такси, отсутствуют во входных данных.</span><span class="sxs-lookup"><span data-stu-id="fbca7-187">Notice that the fare amount is not part of the input.</span></span> <span data-ttu-id="fbca7-188">Это сделано для того, чтобы модель сама спрогнозировала их.</span><span class="sxs-lookup"><span data-stu-id="fbca7-188">This is because the model will generate the prediction for it.</span></span>

    ```csharp
    // Create sample data
    ModelInput input = new ModelInput()
    {
        Vendor_id = "CMT",
        Rate_code = 1,
        Passenger_count = 1,
        Trip_distance = 3.8f,
        Payment_type = "CRD"
    };
    ```

1. <span data-ttu-id="fbca7-189">Используйте метод `Predict` из класса `ConsumeModel`.</span><span class="sxs-lookup"><span data-stu-id="fbca7-189">Use the `Predict` method from the `ConsumeModel` class.</span></span> <span data-ttu-id="fbca7-190">Метод `Predict` загружает обученную модель, создает [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) для модели и использует эту подсистему для создания прогнозов на основе новых данных.</span><span class="sxs-lookup"><span data-stu-id="fbca7-190">The `Predict` method loads the trained model, create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) for the model and uses it to make predictions on new data.</span></span>

    ```csharp
    // Make prediction
    ModelOutput prediction = ConsumeModel.Predict(input);

    // Print Prediction
    Console.WriteLine($"Predicted Fare: {prediction.Score}");
    Console.ReadKey();
    ```

1. <span data-ttu-id="fbca7-191">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="fbca7-191">Run the application.</span></span>

    <span data-ttu-id="fbca7-192">Выходные данные программы должны выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="fbca7-192">The output generated by the program should look similar to the snippet below:</span></span>

    ```bash
    Predicted Fare: 14.96086
    ```

<span data-ttu-id="fbca7-193">Если на созданные проекты нужно будет сослаться позднее в другом решении, их можно найти в каталоге `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.</span><span class="sxs-lookup"><span data-stu-id="fbca7-193">If you need to reference the generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fbca7-194">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="fbca7-194">Next Steps</span></span>

<span data-ttu-id="fbca7-195">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="fbca7-195">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="fbca7-196">Подготовка и анализ данных</span><span class="sxs-lookup"><span data-stu-id="fbca7-196">Prepare and understand the data</span></span>
> - <span data-ttu-id="fbca7-197">Выбор сценария</span><span class="sxs-lookup"><span data-stu-id="fbca7-197">Choose a scenario</span></span>
> - <span data-ttu-id="fbca7-198">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="fbca7-198">Load the data</span></span>
> - <span data-ttu-id="fbca7-199">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="fbca7-199">Train the model</span></span>
> - <span data-ttu-id="fbca7-200">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="fbca7-200">Evaluate the model</span></span>
> - <span data-ttu-id="fbca7-201">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="fbca7-201">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="fbca7-202">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="fbca7-202">Additional Resources</span></span>

<span data-ttu-id="fbca7-203">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="fbca7-203">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="fbca7-204">Сценарии для построителя моделей</span><span class="sxs-lookup"><span data-stu-id="fbca7-204">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenarios)
- [<span data-ttu-id="fbca7-205">Регрессия</span><span class="sxs-lookup"><span data-stu-id="fbca7-205">Regression</span></span>](../resources/glossary.md#regression)
- [<span data-ttu-id="fbca7-206">Метрики модели регрессии</span><span class="sxs-lookup"><span data-stu-id="fbca7-206">Regression Model Metrics</span></span>](../resources/metrics.md#metrics-for-regression)
- [<span data-ttu-id="fbca7-207">Набор данных о поездках на такси, предоставленный Комиссией по лицензированию перевозок автотранспортом города Нью-Йорк (TLC)</span><span class="sxs-lookup"><span data-stu-id="fbca7-207">NYC TLC Taxi Trip data set</span></span>](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
