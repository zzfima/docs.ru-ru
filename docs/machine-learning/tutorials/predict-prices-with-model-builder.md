---
title: Прогнозирование цен с помощью регрессии с использованием построителя моделей
description: В этом учебнике показано, как создать модель регрессии с помощью построителя моделей ML.NET, чтобы прогнозировать цены, в частности плату за проезд в такси по Нью-Йорку.
author: luisquintanilla
ms.author: luquinta
ms.date: 07/15/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 1bdbe31e16408da2d7dfe17941c90a022f3d8c32
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107144"
---
# <a name="predict-prices-using-regression-with-model-builder"></a><span data-ttu-id="9bc16-103">Прогнозирование цен с помощью регрессии с использованием построителя моделей</span><span class="sxs-lookup"><span data-stu-id="9bc16-103">Predict prices using regression with Model Builder</span></span>

<span data-ttu-id="9bc16-104">Узнайте, как с помощью построителя моделей ML.NET создать модель регрессии для прогнозирования цен.</span><span class="sxs-lookup"><span data-stu-id="9bc16-104">Learn how to use ML.NET Model Builder to build a regression model() to predict prices.</span></span>  <span data-ttu-id="9bc16-105">Консольное приложение .NET, разрабатываемое в этом учебнике, прогнозирует плату за проезд в такси по Нью-Йорку на основе исторических данных.</span><span class="sxs-lookup"><span data-stu-id="9bc16-105">The .NET console app that you develop in this tutorial predicts taxi fares based on historical New York taxi fare data.</span></span>

<span data-ttu-id="9bc16-106">Шаблон прогнозирования цен, имеющийся в построителе моделей, можно использовать для любых сценариев, предполагающих прогнозирование числовых значений.</span><span class="sxs-lookup"><span data-stu-id="9bc16-106">The Model Builder price prediction template can be used for any scenario requiring a numerical prediction value.</span></span> <span data-ttu-id="9bc16-107">Примерами могут служить прогнозирование цен на недвижимость, спроса и продаж.</span><span class="sxs-lookup"><span data-stu-id="9bc16-107">Example scenarios include: house price prediction, demand prediction, and sales forecasting.</span></span>

<span data-ttu-id="9bc16-108">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="9bc16-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="9bc16-109">Подготовка и анализ данных</span><span class="sxs-lookup"><span data-stu-id="9bc16-109">Prepare and understand the data</span></span>
> - <span data-ttu-id="9bc16-110">Выбор сценария</span><span class="sxs-lookup"><span data-stu-id="9bc16-110">Choose a scenario</span></span>
> - <span data-ttu-id="9bc16-111">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="9bc16-111">Load the data</span></span>
> - <span data-ttu-id="9bc16-112">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="9bc16-112">Train the model</span></span>
> - <span data-ttu-id="9bc16-113">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="9bc16-113">Evaluate the model</span></span>
> - <span data-ttu-id="9bc16-114">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="9bc16-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="9bc16-115">Построитель моделей в настоящее время находится на этапе предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="9bc16-115">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="9bc16-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9bc16-116">Pre-requisites</span></span>

<span data-ttu-id="9bc16-117">Список необходимых условий и инструкции по установке см. в [руководстве по установке построителя моделей](../how-to-guides/install-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="9bc16-117">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="9bc16-118">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="9bc16-118">Create a console application</span></span>

1. <span data-ttu-id="9bc16-119">Создайте **консольное приложение .NET Core** с именем TaxiFarePrediction.</span><span class="sxs-lookup"><span data-stu-id="9bc16-119">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="9bc16-120">Подготовка и анализ данных</span><span class="sxs-lookup"><span data-stu-id="9bc16-120">Prepare and understand the data</span></span>

1. <span data-ttu-id="9bc16-121">Создайте каталог с именем *Data* в папке проекта, чтобы сохранить в нем файлы набора данных.</span><span class="sxs-lookup"><span data-stu-id="9bc16-121">Create a directory named *Data* in your project to store the data set files.</span></span>

1. <span data-ttu-id="9bc16-122">Набор данных, используемый для обучения и оценки модели машинного обучения, создан на основе данных Комиссии по лицензированию перевозок автотранспортом города Нью-Йорк (TLC).</span><span class="sxs-lookup"><span data-stu-id="9bc16-122">The data set used to train and evaluate the machine learning model is originally from the NYC TLC Taxi Trip data set.</span></span>

    <span data-ttu-id="9bc16-123">Скачать набор данных можно по [этой ссылке](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).</span><span class="sxs-lookup"><span data-stu-id="9bc16-123">To download the data set, navigate to the [taxi-fare-train.csv download link](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).</span></span>

    <span data-ttu-id="9bc16-124">При загрузке страницы щелкните правой кнопкой мыши в любом месте и выберите в меню команду **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="9bc16-124">When the page loads, right-click anywhere on the page and select **Save as**.</span></span>

    <span data-ttu-id="9bc16-125">В диалоговом окне **Сохранить как** сохраните файл в созданную ранее папку *Data*.</span><span class="sxs-lookup"><span data-stu-id="9bc16-125">Use the **Save As Dialog** to save the file in the *Data* folder you created at the previous step.</span></span>

1. <span data-ttu-id="9bc16-126">В **обозревателе решений** щелкните правой кнопкой мыши файл *taxi-fare-train.csv* и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9bc16-126">In **Solution Explorer**, right-click the *taxi-fare-train.csv* file and select **Properties**.</span></span> <span data-ttu-id="9bc16-127">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="9bc16-127">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="9bc16-128">Каждая строка в наборе данных `taxi-fare-train.csv` содержит сведения о поездках в такси.</span><span class="sxs-lookup"><span data-stu-id="9bc16-128">Each row in the `taxi-fare-train.csv` data set contains details of trips made by a taxi.</span></span>

1. <span data-ttu-id="9bc16-129">Откройте набор данных **taxi-fare-train.csv**.</span><span class="sxs-lookup"><span data-stu-id="9bc16-129">Open the **taxi-fare-train.csv** data set</span></span>

    <span data-ttu-id="9bc16-130">Предоставленный набор данных содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="9bc16-130">The provided data set contains the following columns:</span></span>

    - <span data-ttu-id="9bc16-131">**vendor_id:** идентификатор поставщика услуг такси — это признак.</span><span class="sxs-lookup"><span data-stu-id="9bc16-131">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
    - <span data-ttu-id="9bc16-132">**rate_code:** тип тарифа для поездки на такси — это признак.</span><span class="sxs-lookup"><span data-stu-id="9bc16-132">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
    - <span data-ttu-id="9bc16-133">**passenger_count:** число пассажиров в поездке — это признак.</span><span class="sxs-lookup"><span data-stu-id="9bc16-133">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
    - <span data-ttu-id="9bc16-134">**trip_time_in_secs:** время, затраченное на поездку.</span><span class="sxs-lookup"><span data-stu-id="9bc16-134">**trip_time_in_secs:** The amount of time the trip took.</span></span>
    - <span data-ttu-id="9bc16-135">**trip_distance:** расстояние поездки — это признак.</span><span class="sxs-lookup"><span data-stu-id="9bc16-135">**trip_distance:** The distance of the trip is a feature.</span></span>
    - <span data-ttu-id="9bc16-136">**payment_type:** метод оплаты (наличные или кредитная карта) — это признак.</span><span class="sxs-lookup"><span data-stu-id="9bc16-136">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
    - <span data-ttu-id="9bc16-137">**fare_amount:** общая сумма, уплаченная за поездку на такси, — это метка.</span><span class="sxs-lookup"><span data-stu-id="9bc16-137">**fare_amount:** The total taxi fare paid is the label.</span></span>

<span data-ttu-id="9bc16-138">`label` — это столбец для прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="9bc16-138">The `label` is the column you want to predict.</span></span> <span data-ttu-id="9bc16-139">Цель задачи регрессии — прогнозирование числового значения.</span><span class="sxs-lookup"><span data-stu-id="9bc16-139">When performing a regression task, the goal is to predict a numerical value.</span></span> <span data-ttu-id="9bc16-140">В этом сценарии прогнозируется стоимость поездки в такси.</span><span class="sxs-lookup"><span data-stu-id="9bc16-140">In this price prediction scenario, the cost of a taxi ride is being predicted.</span></span> <span data-ttu-id="9bc16-141">Поэтому меткой является **fare_amount**.</span><span class="sxs-lookup"><span data-stu-id="9bc16-141">Therefore, the **fare_amount** is the label.</span></span> <span data-ttu-id="9bc16-142">Выбранные признаки (`features`) — это входные данные, которые вы предоставляете модели для прогнозирования метки (`label`).</span><span class="sxs-lookup"><span data-stu-id="9bc16-142">The identified `features` are the inputs you give the model to predict the `label`.</span></span> <span data-ttu-id="9bc16-143">В данном случае признаками или входными данными для прогнозирования стоимости поездки служат все остальные столбцы.</span><span class="sxs-lookup"><span data-stu-id="9bc16-143">In this case, the rest of the columns are used as features or inputs to predict the fare amount.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="9bc16-144">Выбор сценария</span><span class="sxs-lookup"><span data-stu-id="9bc16-144">Choose a scenario</span></span>

<span data-ttu-id="9bc16-145">Чтобы обучить модель, нужно выбрать один из доступных сценариев машинного обучения в построителе моделей.</span><span class="sxs-lookup"><span data-stu-id="9bc16-145">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> <span data-ttu-id="9bc16-146">В этом случае используется сценарий `Price Prediction`.</span><span class="sxs-lookup"><span data-stu-id="9bc16-146">In this case, the scenario is `Price Prediction`.</span></span>

1. <span data-ttu-id="9bc16-147">В **обозревателе решений** щелкните правой кнопкой мыши проект *TaxiFarePrediction* и выберите **Добавить** > **Машинное обучение**.</span><span class="sxs-lookup"><span data-stu-id="9bc16-147">In **Solution Explorer**, right-click the *TaxiFarePrediction* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="9bc16-148">На этапе выбора сценария выберите *Прогнозирование цен*.</span><span class="sxs-lookup"><span data-stu-id="9bc16-148">In the scenario step of the Model Builder tool, select *Price Prediction* scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="9bc16-149">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="9bc16-149">Load the data</span></span>

<span data-ttu-id="9bc16-150">Построитель моделей принимает данные из двух источников: базы данных SQL Server или локального файла в формате CSV или TSV.</span><span class="sxs-lookup"><span data-stu-id="9bc16-150">Model Builder accepts data from two sources, a SQL Server database or a local file in csv or tsv format.</span></span>

1. <span data-ttu-id="9bc16-151">На этапе добавления данных выберите в раскрывающемся списке источников данных пункт *Прогнозирование цен*.</span><span class="sxs-lookup"><span data-stu-id="9bc16-151">In the data step of the Model Builder tool, select *File* from the data source dropdown.</span></span>
1. <span data-ttu-id="9bc16-152">Нажмите кнопку рядом с текстовым полем *Выберите файл* и выберите в проводнике файл *taxi-fare-test.csv* в каталоге *Data*.</span><span class="sxs-lookup"><span data-stu-id="9bc16-152">Select the button next to the *Select a file* text box and use File Explorer to browse and select the *taxi-fare-test.csv* in the *Data* directory</span></span>
1. <span data-ttu-id="9bc16-153">В раскрывающемся списке *Метка или прогнозируемый столбец* выберите *fare_amount* и перейдите к шагу обучения в построителе моделей.</span><span class="sxs-lookup"><span data-stu-id="9bc16-153">Choose *fare_amount* in the *Label or Column to Predict* dropdown and navigate to the train step of the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="9bc16-154">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="9bc16-154">Train the model</span></span>

<span data-ttu-id="9bc16-155">Задачей машинного обучения, используемой в этом учебнике для обучения модели прогнозирования цен, является регрессия.</span><span class="sxs-lookup"><span data-stu-id="9bc16-155">The machine learning task used to train the price prediction model in this tutorial is regression.</span></span> <span data-ttu-id="9bc16-156">В процессе обучения построитель моделей обучает отдельные модели с помощью различных алгоритмов и параметров регрессии, определяя оптимальную модель для вашего набора данных.</span><span class="sxs-lookup"><span data-stu-id="9bc16-156">During the model training process, Model Builder trains separate models using different regression algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="9bc16-157">Время, требуемое для обучения модели, пропорционально объему данных.</span><span class="sxs-lookup"><span data-stu-id="9bc16-157">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="9bc16-158">Чтобы выбрать подходящее значение для поля `Time to train (seconds)`, можно опираться на следующую таблицу:</span><span class="sxs-lookup"><span data-stu-id="9bc16-158">Use this chart as guidance to select an adequate value for the `Time to train (seconds)` field:</span></span>

<span data-ttu-id="9bc16-159">Размер набора данных</span><span class="sxs-lookup"><span data-stu-id="9bc16-159">\*Dataset Size</span></span>  | <span data-ttu-id="9bc16-160">Тип набора данных</span><span class="sxs-lookup"><span data-stu-id="9bc16-160">Dataset Type</span></span>       | <span data-ttu-id="9bc16-161">Среднее Время обучения</span><span class="sxs-lookup"><span data-stu-id="9bc16-161">Avg. Time to train\*</span></span>
------------- | ------------------ | --------------
<span data-ttu-id="9bc16-162">0–10 МБ</span><span class="sxs-lookup"><span data-stu-id="9bc16-162">0 - 10 Mb</span></span>     | <span data-ttu-id="9bc16-163">Числа и текст</span><span class="sxs-lookup"><span data-stu-id="9bc16-163">Numeric and Text</span></span>   | <span data-ttu-id="9bc16-164">10 с</span><span class="sxs-lookup"><span data-stu-id="9bc16-164">10 sec</span></span>
<span data-ttu-id="9bc16-165">10–100 МБ</span><span class="sxs-lookup"><span data-stu-id="9bc16-165">10 - 100 Mb</span></span>   | <span data-ttu-id="9bc16-166">Числа и текст</span><span class="sxs-lookup"><span data-stu-id="9bc16-166">Numeric and Text</span></span>   | <span data-ttu-id="9bc16-167">10 мин</span><span class="sxs-lookup"><span data-stu-id="9bc16-167">10 min</span></span>
<span data-ttu-id="9bc16-168">100–500 МБ</span><span class="sxs-lookup"><span data-stu-id="9bc16-168">100 - 500 Mb</span></span>  | <span data-ttu-id="9bc16-169">Числа и текст</span><span class="sxs-lookup"><span data-stu-id="9bc16-169">Numeric and Text</span></span>   | <span data-ttu-id="9bc16-170">30 мин</span><span class="sxs-lookup"><span data-stu-id="9bc16-170">30 min</span></span>
<span data-ttu-id="9bc16-171">500 МБ — 1 ГБ</span><span class="sxs-lookup"><span data-stu-id="9bc16-171">500 - 1 Gb</span></span>    | <span data-ttu-id="9bc16-172">Числа и текст</span><span class="sxs-lookup"><span data-stu-id="9bc16-172">Numeric and Text</span></span>   | <span data-ttu-id="9bc16-173">60 мин</span><span class="sxs-lookup"><span data-stu-id="9bc16-173">60 min</span></span>
<span data-ttu-id="9bc16-174">Более 1 ГБ</span><span class="sxs-lookup"><span data-stu-id="9bc16-174">1 Gb+</span></span>         | <span data-ttu-id="9bc16-175">Числа и текст</span><span class="sxs-lookup"><span data-stu-id="9bc16-175">Numeric and Text</span></span>   | <span data-ttu-id="9bc16-176">Более 3 часов</span><span class="sxs-lookup"><span data-stu-id="9bc16-176">3 hour+</span></span>

1. <span data-ttu-id="9bc16-177">Так как размер файла с данными для обучения превышает 10 МБ, используйте для поля *Время обучения (в секундах)* значение 600 секунд (10 минут).</span><span class="sxs-lookup"><span data-stu-id="9bc16-177">Because the training data file is more than 10MB, use 600 seconds (10 minutes) as the value for *Time to train (seconds)*.</span></span>
2. <span data-ttu-id="9bc16-178">Выберите *Начать обучение*.</span><span class="sxs-lookup"><span data-stu-id="9bc16-178">Select *Start Training*.</span></span>

<span data-ttu-id="9bc16-179">В процессе обучения сведения о ходе выполнения отображаются в разделе `Progress` шага обучения.</span><span class="sxs-lookup"><span data-stu-id="9bc16-179">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

- <span data-ttu-id="9bc16-180">"Состояние" — это состояние завершения процесса обучения.</span><span class="sxs-lookup"><span data-stu-id="9bc16-180">Status displays the completion status of the training process.</span></span>
- <span data-ttu-id="9bc16-181">"Наибольшая точность" — это точность модели, которая на данный момент определена построителем моделей как лучшая.</span><span class="sxs-lookup"><span data-stu-id="9bc16-181">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="9bc16-182">Точность зависит от того, насколько правильный прогноз был сделан моделью на основе тестовых данных.</span><span class="sxs-lookup"><span data-stu-id="9bc16-182">Higher accuracy means the model predicted more correctly on test data.</span></span>
- <span data-ttu-id="9bc16-183">"Лучший алгоритм" — это название алгоритма, который на данный момент определен построителем моделей как лучший.</span><span class="sxs-lookup"><span data-stu-id="9bc16-183">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
- <span data-ttu-id="9bc16-184">"Последний алгоритм" — это название алгоритма, который использовался построителем моделей для обучения модели последним.</span><span class="sxs-lookup"><span data-stu-id="9bc16-184">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

<span data-ttu-id="9bc16-185">По завершении обучения перейдите к шагу оценки.</span><span class="sxs-lookup"><span data-stu-id="9bc16-185">Once training is complete, navigate to the evaluate step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="9bc16-186">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="9bc16-186">Evaluate the model</span></span>

<span data-ttu-id="9bc16-187">Результат обучения — одна модель с наивысшей точностью.</span><span class="sxs-lookup"><span data-stu-id="9bc16-187">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="9bc16-188">В шаге оценки в разделе результатов будет указан алгоритм, используемый оптимальной моделью, в поле *Лучшая модель*, а также метрики в поле *Качество лучшей модели (достоверность аппроксимации)* .</span><span class="sxs-lookup"><span data-stu-id="9bc16-188">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the *Best Model* entry along with metrics in *Best Model Quality (RSquared)*.</span></span> <span data-ttu-id="9bc16-189">Кроме того, приводится сводная таблица с пятью лучшими моделями и их метриками.</span><span class="sxs-lookup"><span data-stu-id="9bc16-189">Additionally, a summary table containing top five models and their metrics.</span></span>

<span data-ttu-id="9bc16-190">Если вас не удовлетворяют метрики точности, самые простые способы повысить точность модели — увеличить длительность обучения или использовать больше данных.</span><span class="sxs-lookup"><span data-stu-id="9bc16-190">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="9bc16-191">Если все в порядке, переходите к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="9bc16-191">Otherwise, navigate to the code step.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="9bc16-192">Добавление кода для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="9bc16-192">Add the code to make predictions</span></span>

<span data-ttu-id="9bc16-193">В результате процесса обучения создаются два проекта.</span><span class="sxs-lookup"><span data-stu-id="9bc16-193">Two projects will be created as a result of the training process.</span></span>

- <span data-ttu-id="9bc16-194">TaxiFarePredictionML.ConsoleApp: консольное приложение .NET Core с кодом обучения и использования модели.</span><span class="sxs-lookup"><span data-stu-id="9bc16-194">TaxiFarePredictionML.ConsoleApp: A .NET Core Console application that contains the model training and consumption code.</span></span>
- <span data-ttu-id="9bc16-195">TaxiFarePredictionML.Model: библиотека классов .NET Standard с моделями данных, которые определяют схему входных и выходных данных модели, а также хранимую версию оптимальной модели.</span><span class="sxs-lookup"><span data-stu-id="9bc16-195">TaxiFarePredictionML.Model: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the persisted version of the best performing model during training.</span></span>

1. <span data-ttu-id="9bc16-196">На шаге добавления кода в построителе моделей выберите **Добавить проекты**, чтобы добавить автоматически созданные проекты в решение.</span><span class="sxs-lookup"><span data-stu-id="9bc16-196">In the code step of the Model Builder tool, select **Add Projects** to add the auto-generated projects to the solution.</span></span>
1. <span data-ttu-id="9bc16-197">Щелкните правой кнопкой мыши проект *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="9bc16-197">Right-click *TaxiFarePrediction* project.</span></span> <span data-ttu-id="9bc16-198">Выберите **Добавить > Ссылка**.</span><span class="sxs-lookup"><span data-stu-id="9bc16-198">Then, **Add > Reference**.</span></span> <span data-ttu-id="9bc16-199">Выберите узел **Проекты > Решение**, установите в списке флажок рядом с проектом *TaxiFarePredictionML.Model* и нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="9bc16-199">Choose the **Projects > Solution** node and from the list, check the *TaxiFarePredictionML.Model* project and select OK.</span></span>
1. <span data-ttu-id="9bc16-200">Откройте файл *Program.cs* в проекте *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="9bc16-200">Open the *Program.cs* file in the *TaxiFarePrediction* project.</span></span>
1. <span data-ttu-id="9bc16-201">Добавьте следующие операторы using, ссылающиеся на пакет NuGet *Microsoft.ML* и проект *TaxiFarePredictionML.Model*:</span><span class="sxs-lookup"><span data-stu-id="9bc16-201">Add the following using statements to reference the *Microsoft.ML* NuGet package and *TaxiFarePredictionML.Model* project:</span></span>

    ```csharp
    using System;
    using Microsoft.ML;
    using TaxiFarePredictionML.Model.DataModels;
    ```

1. <span data-ttu-id="9bc16-202">Добавьте метод `ConsumeModel` в класс `Program`.</span><span class="sxs-lookup"><span data-stu-id="9bc16-202">Add the `ConsumeModel` method to the `Program` class.</span></span>

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

    <span data-ttu-id="9bc16-203">`ConsumeModel` загружает обученную модель, создает [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) для модели и с помощью этой подсистемы прогнозирования делает прогнозы по новым данным.</span><span class="sxs-lookup"><span data-stu-id="9bc16-203">The `ConsumeModel` will load the trained model, create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) for the model and use it to make predictions on new data.</span></span>

1. <span data-ttu-id="9bc16-204">Чтобы сделать прогноз по новым данным с помощью модели, создайте экземпляр класса `ModelInput` и используйте метод `ConsumeModel`.</span><span class="sxs-lookup"><span data-stu-id="9bc16-204">To make a prediction on new data using the model, create a new instance of the `ModelInput` class and use the `ConsumeModel` method.</span></span> <span data-ttu-id="9bc16-205">Обратите внимание, что данные о суммах, уплаченных за поездку на такси, отсутствуют во входных данных.</span><span class="sxs-lookup"><span data-stu-id="9bc16-205">Notice that the fare amount is not part of the input.</span></span> <span data-ttu-id="9bc16-206">Это сделано для того, чтобы модель сама спрогнозировала их.</span><span class="sxs-lookup"><span data-stu-id="9bc16-206">This is because the model will generate the prediction for it.</span></span> <span data-ttu-id="9bc16-207">Добавьте в метод `Main` приведенный ниже код и запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="9bc16-207">Add the following code to the `Main` method and run the application</span></span>

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

    <span data-ttu-id="9bc16-208">Выходные данные программы должны выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="9bc16-208">The output generated by the program should look similar to the snippet below:</span></span>

    ```bash
    Predicted Fare: 16.82245
    ```

<span data-ttu-id="9bc16-209">Если на созданные проекты нужно будет сослаться позднее в другом решении, их можно найти в каталоге `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.</span><span class="sxs-lookup"><span data-stu-id="9bc16-209">If you need to reference the generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9bc16-210">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="9bc16-210">Next Steps</span></span>

<span data-ttu-id="9bc16-211">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="9bc16-211">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="9bc16-212">Подготовка и анализ данных</span><span class="sxs-lookup"><span data-stu-id="9bc16-212">Prepare and understand the data</span></span>
> - <span data-ttu-id="9bc16-213">Выбор сценария</span><span class="sxs-lookup"><span data-stu-id="9bc16-213">Choose a scenario</span></span>
> - <span data-ttu-id="9bc16-214">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="9bc16-214">Load the data</span></span>
> - <span data-ttu-id="9bc16-215">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="9bc16-215">Train the model</span></span>
> - <span data-ttu-id="9bc16-216">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="9bc16-216">Evaluate the model</span></span>
> - <span data-ttu-id="9bc16-217">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="9bc16-217">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="9bc16-218">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="9bc16-218">Additional Resources</span></span>

<span data-ttu-id="9bc16-219">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="9bc16-219">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="9bc16-220">Сценарии для построителя моделей</span><span class="sxs-lookup"><span data-stu-id="9bc16-220">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenarios)
- [<span data-ttu-id="9bc16-221">Регрессия</span><span class="sxs-lookup"><span data-stu-id="9bc16-221">Regression</span></span>](../resources/glossary.md#regression)
- [<span data-ttu-id="9bc16-222">Метрики модели регрессии</span><span class="sxs-lookup"><span data-stu-id="9bc16-222">Regression Model Metrics</span></span>](../resources/metrics.md#metrics-for-regression)
- [<span data-ttu-id="9bc16-223">Набор данных о поездках на такси, предоставленный Комиссией по лицензированию перевозок автотранспортом города Нью-Йорк (TLC)</span><span class="sxs-lookup"><span data-stu-id="9bc16-223">NYC TLC Taxi Trip data set</span></span>](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)
