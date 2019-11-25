---
title: Построитель моделей и принципы его работы
description: Сведения об использовании построителя моделей ML.NET для автоматического обучения модели машинного обучения
author: natke
ms.date: 08/07/2019
ms.custom: overview
ms.openlocfilehash: 77fe56dba3532617ad9fb0c89bfaac7c8e031ce7
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971526"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a><span data-ttu-id="37bd2-103">Построитель моделей и принципы его работы</span><span class="sxs-lookup"><span data-stu-id="37bd2-103">What is Model Builder and how does it work?</span></span>

<span data-ttu-id="37bd2-104">Построитель моделей ML.NET — это интуитивно понятное графическое расширение Visual Studio для создания, обучения и развертывания пользовательских моделей машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="37bd2-104">ML.NET Model Builder is an intuitive graphical Visual Studio extension to build, train, and deploy custom machine learning models.</span></span>

<span data-ttu-id="37bd2-105">Построитель моделей использует автоматизированное машинное обучение (AutoML) для анализа различных алгоритмов и параметров машинного обучения и выбора наиболее подходящих из них для конкретного сценария.</span><span class="sxs-lookup"><span data-stu-id="37bd2-105">Model Builder uses automated machine learning (AutoML) to explore different machine learning algorithms and settings to help you find the one that best suits your scenario.</span></span>

<span data-ttu-id="37bd2-106">Для работы с построителем моделей не нужно быть экспертом в области машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="37bd2-106">You don't need machine learning expertise to use Model Builder.</span></span> <span data-ttu-id="37bd2-107">Все, что требуется, — это данные и проблема, которую нужно решить.</span><span class="sxs-lookup"><span data-stu-id="37bd2-107">All you need is some data, and a problem to solve.</span></span> <span data-ttu-id="37bd2-108">Построитель моделей генерирует код для добавления модели в приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="37bd2-108">Model Builder generates the code to add the model to your .NET application.</span></span>

![Анимация: пользовательский интерфейс расширения "Построитель моделей" для Visual Studio](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> <span data-ttu-id="37bd2-110">Построитель моделей в настоящее время находится на этапе предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="37bd2-110">Model Builder is currently in Preview.</span></span>

## <a name="scenarios"></a><span data-ttu-id="37bd2-111">Сценарии</span><span class="sxs-lookup"><span data-stu-id="37bd2-111">Scenarios</span></span>

<span data-ttu-id="37bd2-112">Построитель моделей может создавать модели машинного обучения для приложения на основе множества различных сценариев.</span><span class="sxs-lookup"><span data-stu-id="37bd2-112">You can bring many different scenarios to Model Builder, to generate a machine learning model for your application.</span></span>

<span data-ttu-id="37bd2-113">Сценарий описывает тип прогноза, который нужно сделать с использованием данных.</span><span class="sxs-lookup"><span data-stu-id="37bd2-113">A scenario is a description of the type of prediction you want to make using your data.</span></span> <span data-ttu-id="37bd2-114">Например:</span><span class="sxs-lookup"><span data-stu-id="37bd2-114">For example:</span></span>

- <span data-ttu-id="37bd2-115">прогнозирование будущего объема продаж продукта на основе исторических данных по продажам;</span><span class="sxs-lookup"><span data-stu-id="37bd2-115">predict future product sales volume based on historical sales data</span></span>
- <span data-ttu-id="37bd2-116">классификация тональности как положительной или отрицательной на основе отзывов клиентов;</span><span class="sxs-lookup"><span data-stu-id="37bd2-116">classify sentiments as positive or negative based on customer reviews</span></span>
- <span data-ttu-id="37bd2-117">определение того, является ли банковская операция мошеннической;</span><span class="sxs-lookup"><span data-stu-id="37bd2-117">detect whether a banking transaction is fraudulent</span></span>
- <span data-ttu-id="37bd2-118">направление проблем, с которыми обращаются клиенты, на рассмотрение соответствующим сотрудникам компании.</span><span class="sxs-lookup"><span data-stu-id="37bd2-118">route customer feedback issues to the correct team in your company</span></span>

## <a name="choose-a-model-type"></a><span data-ttu-id="37bd2-119">Выбор типа модели</span><span class="sxs-lookup"><span data-stu-id="37bd2-119">Choose a model type</span></span>

<span data-ttu-id="37bd2-120">В построителе моделей необходимо выбрать тип модели машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="37bd2-120">In Model Builder, you need to select a machine learning model type.</span></span> <span data-ttu-id="37bd2-121">Тип модели зависит от того, какой прогноз вы пытаетесь сделать.</span><span class="sxs-lookup"><span data-stu-id="37bd2-121">The type of model depends on what sort of prediction you are trying to make.</span></span>

<span data-ttu-id="37bd2-122">Если прогнозируется число, тип модели машинного обучения называется `regression`.</span><span class="sxs-lookup"><span data-stu-id="37bd2-122">For scenarios that predict a number, the machine learning model type is called `regression`.</span></span>

<span data-ttu-id="37bd2-123">Если прогнозируется категория, тип модели — `classification`.</span><span class="sxs-lookup"><span data-stu-id="37bd2-123">For scenarios that predict a category, the model type is `classification`.</span></span> <span data-ttu-id="37bd2-124">Существуют два типа классификации:</span><span class="sxs-lookup"><span data-stu-id="37bd2-124">There are two types of classification:</span></span>

- <span data-ttu-id="37bd2-125">при наличии только двух категорий — `binary classification`;</span><span class="sxs-lookup"><span data-stu-id="37bd2-125">where there are only 2 categories: `binary classification`.</span></span>
- <span data-ttu-id="37bd2-126">при наличии трех или более категорий — `multiclass classification`.</span><span class="sxs-lookup"><span data-stu-id="37bd2-126">where there are three or more categories: `multiclass classification`.</span></span>

### <a name="which-model-type-is-right-for-me"></a><span data-ttu-id="37bd2-127">Какой тип модели подойдет лучше всего?</span><span class="sxs-lookup"><span data-stu-id="37bd2-127">Which model type is right for me?</span></span>

#### <a name="predict-a-category-when-there-are-only-two-categories"></a><span data-ttu-id="37bd2-128">Прогнозирование категории (при наличии только двух категорий)</span><span class="sxs-lookup"><span data-stu-id="37bd2-128">Predict a category (when there are only two categories)</span></span>

<span data-ttu-id="37bd2-129">Двоичная классификация служит для разделения данных на две категории (да или нет, успех или неудача, истина или ложь, положительные или отрицательные).</span><span class="sxs-lookup"><span data-stu-id="37bd2-129">Binary classification is used to categorize data into two categories (yes/no; pass/fail; true/false; positive/negative).</span></span>

![Схема с примерами двоичной классификации, включая обнаружение мошенничества, устранение рисков и блокировку приложений](media/binary-classification-examples.png)

<span data-ttu-id="37bd2-131">Анализ тональности можно использовать для определения положительной или отрицательной тональности отзыва клиента.</span><span class="sxs-lookup"><span data-stu-id="37bd2-131">Sentiment analysis can be used to predict positive or negative sentiment of customer feedback.</span></span> <span data-ttu-id="37bd2-132">Это пример модели двоичной классификации.</span><span class="sxs-lookup"><span data-stu-id="37bd2-132">It is an example of a binary classification model type.</span></span>

<span data-ttu-id="37bd2-133">Если ваш сценарий требует классификации на две категории, вы можете использовать этот шаблон со своим набором данных.</span><span class="sxs-lookup"><span data-stu-id="37bd2-133">If your scenario requires classification into two categories, you can use this template with your own dataset.</span></span>

#### <a name="predict-a-category-when-there-are-three-or-more-categories"></a><span data-ttu-id="37bd2-134">Прогнозирование категории (при наличии трех или более категорий)</span><span class="sxs-lookup"><span data-stu-id="37bd2-134">Predict a category (when there are three or more categories)</span></span>

<span data-ttu-id="37bd2-135">Многоклассовая классификация служит для разделения данных на три или более категорий.</span><span class="sxs-lookup"><span data-stu-id="37bd2-135">Multiclass classification can be used to categorize data into three or more classes.</span></span>

![Примеры многоклассовой классификации, включая классификацию документов и продуктов, маршрутизацию запросов в службу поддержки и определение приоритетности клиентских проблем](media/multiclass-classification-examples.png)

<span data-ttu-id="37bd2-137">С помощью классификации проблем можно разделять проблемы, о которых сообщают клиенты (например, на GitHub), на категории исходя из их названий и описаний.</span><span class="sxs-lookup"><span data-stu-id="37bd2-137">Issue classification can be used to categorize customer feedback (for example, on GitHub) issues using the issue title and description.</span></span> <span data-ttu-id="37bd2-138">Это пример модели многоклассовой классификации.</span><span class="sxs-lookup"><span data-stu-id="37bd2-138">It is an example of the multi-class classification model type.</span></span>

<span data-ttu-id="37bd2-139">Шаблон многоклассовой классификации можно использовать для сценария, который предполагает разделение данных на три или более категорий.</span><span class="sxs-lookup"><span data-stu-id="37bd2-139">You can use the issue classification template for your scenario if you want to categorize data into three or more categories.</span></span>

#### <a name="predict-a-number"></a><span data-ttu-id="37bd2-140">Прогнозирование числа</span><span class="sxs-lookup"><span data-stu-id="37bd2-140">Predict a number</span></span>

<span data-ttu-id="37bd2-141">Регрессия служит для прогнозирования числовых значений.</span><span class="sxs-lookup"><span data-stu-id="37bd2-141">Regression is used to predict numbers.</span></span>

![Схема с примерами регрессии, включая прогнозирование цен, прогнозирование продаж и прогнозное обслуживание](media/regression-examples.png)

<span data-ttu-id="37bd2-143">С помощью прогнозирования цен можно прогнозировать цены на недвижимость исходя из местоположения, площади и других характеристик объекта недвижимости.</span><span class="sxs-lookup"><span data-stu-id="37bd2-143">Price prediction can be used to predict house prices using location, size, and other characteristics of the house.</span></span> <span data-ttu-id="37bd2-144">Это пример модели регрессии.</span><span class="sxs-lookup"><span data-stu-id="37bd2-144">It is an example of a regression model type.</span></span>

<span data-ttu-id="37bd2-145">Шаблон прогнозирования цен можно использовать для сценария, который предполагает прогнозирование числовых значений на основе собственного набора данных.</span><span class="sxs-lookup"><span data-stu-id="37bd2-145">You can use the price prediction template for your scenario if you want to predict a numerical value with your own dataset.</span></span>

#### <a name="custom-scenario-choose-your-model-type"></a><span data-ttu-id="37bd2-146">Пользовательский сценарий (выбор типа модели)</span><span class="sxs-lookup"><span data-stu-id="37bd2-146">Custom scenario (choose your model type)</span></span>

<span data-ttu-id="37bd2-147">Пользовательский сценарий позволяет выбрать тип модели вручную.</span><span class="sxs-lookup"><span data-stu-id="37bd2-147">The custom scenario allows you to manually choose your model type.</span></span>

## <a name="data"></a><span data-ttu-id="37bd2-148">Data</span><span class="sxs-lookup"><span data-stu-id="37bd2-148">Data</span></span>

<span data-ttu-id="37bd2-149">После выбора типа модели построитель моделей попросит вас предоставить набор данных.</span><span class="sxs-lookup"><span data-stu-id="37bd2-149">Once you have chosen your model type, Model Builder asks you to provide a dataset.</span></span> <span data-ttu-id="37bd2-150">Данные используются для обучения, оценки и выбора оптимальной модели для сценария.</span><span class="sxs-lookup"><span data-stu-id="37bd2-150">The data is used to train, evaluate, and choose the best model for your scenario.</span></span>

![Схема, демонстрирующая этапы работы построителя моделей](media/model-builder-steps.png)

### <a name="choose-the-output-to-predict-label"></a><span data-ttu-id="37bd2-152">Выбор результата для прогнозирования (метка)</span><span class="sxs-lookup"><span data-stu-id="37bd2-152">Choose the output to predict (label)</span></span>

<span data-ttu-id="37bd2-153">Набор данных — это таблица, строки которой содержат образцы для обучения, а столбцы — атрибуты.</span><span class="sxs-lookup"><span data-stu-id="37bd2-153">A dataset is a table of rows of training examples, and columns of attributes.</span></span> <span data-ttu-id="37bd2-154">В каждой строке есть:</span><span class="sxs-lookup"><span data-stu-id="37bd2-154">Each row has:</span></span>

- <span data-ttu-id="37bd2-155">**метка** (атрибут, который нужно спрогнозировать);</span><span class="sxs-lookup"><span data-stu-id="37bd2-155">a **label** (the attribute that you want to predict)</span></span>
- <span data-ttu-id="37bd2-156">**признаки** (атрибуты, исходя из которых прогнозируется метка).</span><span class="sxs-lookup"><span data-stu-id="37bd2-156">**features** (attributes that are used as inputs to predict the label).</span></span>

<span data-ttu-id="37bd2-157">В сценарии прогнозирования цен на недвижимость признаками могут быть:</span><span class="sxs-lookup"><span data-stu-id="37bd2-157">For the house-price prediction scenario, the features could be:</span></span>

- <span data-ttu-id="37bd2-158">площадь дома;</span><span class="sxs-lookup"><span data-stu-id="37bd2-158">the square footage of the house</span></span>
- <span data-ttu-id="37bd2-159">количество спален и ванных комнат;</span><span class="sxs-lookup"><span data-stu-id="37bd2-159">the number of bedrooms and bathrooms</span></span>
- <span data-ttu-id="37bd2-160">почтовый индекс.</span><span class="sxs-lookup"><span data-stu-id="37bd2-160">the zip code</span></span>

<span data-ttu-id="37bd2-161">Метка — это историческая цена на дом данной площади, с данным количеством спален и ванных комнат, а также почтовым индексом.</span><span class="sxs-lookup"><span data-stu-id="37bd2-161">The label is the historical house price for that row of square footage, bedroom, and bathroom values and zip code.</span></span>

![Таблица цен на недвижимость, содержащая признаки (площадь, количество комнат, почтовый индекс) и метку (цена)](media/model-builder-data.png)

### <a name="example-datasets"></a><span data-ttu-id="37bd2-163">Примеры наборов данных</span><span class="sxs-lookup"><span data-stu-id="37bd2-163">Example datasets</span></span>

<span data-ttu-id="37bd2-164">Если у вас нет собственного набора данных, можно воспользоваться одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="37bd2-164">If you don't have your own data yet, try out one of these datasets:</span></span>

|<span data-ttu-id="37bd2-165">Сценарий</span><span class="sxs-lookup"><span data-stu-id="37bd2-165">Scenario</span></span>|<span data-ttu-id="37bd2-166">Тип модели</span><span class="sxs-lookup"><span data-stu-id="37bd2-166">Model Type</span></span>|<span data-ttu-id="37bd2-167">Data</span><span class="sxs-lookup"><span data-stu-id="37bd2-167">Data</span></span>|<span data-ttu-id="37bd2-168">Метка</span><span class="sxs-lookup"><span data-stu-id="37bd2-168">Label</span></span>|<span data-ttu-id="37bd2-169">Функции</span><span class="sxs-lookup"><span data-stu-id="37bd2-169">Features</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="37bd2-170">Прогнозирование цен</span><span class="sxs-lookup"><span data-stu-id="37bd2-170">Price prediction</span></span>|<span data-ttu-id="37bd2-171">регрессия;</span><span class="sxs-lookup"><span data-stu-id="37bd2-171">regression</span></span>|[<span data-ttu-id="37bd2-172">данные по платам за такси</span><span class="sxs-lookup"><span data-stu-id="37bd2-172">taxi fare data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|<span data-ttu-id="37bd2-173">Плата</span><span class="sxs-lookup"><span data-stu-id="37bd2-173">Fare</span></span>|<span data-ttu-id="37bd2-174">Время поездки, расстояние</span><span class="sxs-lookup"><span data-stu-id="37bd2-174">Trip time, distance</span></span>|
|<span data-ttu-id="37bd2-175">Обнаружение аномалий</span><span class="sxs-lookup"><span data-stu-id="37bd2-175">Anomaly detection</span></span>|<span data-ttu-id="37bd2-176">двоичная классификация;</span><span class="sxs-lookup"><span data-stu-id="37bd2-176">binary classification</span></span>|[<span data-ttu-id="37bd2-177">данные по продажам продуктов</span><span class="sxs-lookup"><span data-stu-id="37bd2-177">product sales data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|<span data-ttu-id="37bd2-178">Продажи продукта</span><span class="sxs-lookup"><span data-stu-id="37bd2-178">Product Sales</span></span>|<span data-ttu-id="37bd2-179">Месяц</span><span class="sxs-lookup"><span data-stu-id="37bd2-179">Month</span></span>|
|<span data-ttu-id="37bd2-180">Анализ мнений</span><span class="sxs-lookup"><span data-stu-id="37bd2-180">Sentiment analysis</span></span>|<span data-ttu-id="37bd2-181">двоичная классификация;</span><span class="sxs-lookup"><span data-stu-id="37bd2-181">binary classification</span></span>|[<span data-ttu-id="37bd2-182">данные по комментариям на веб-сайте</span><span class="sxs-lookup"><span data-stu-id="37bd2-182">website comment data</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|<span data-ttu-id="37bd2-183">Метка (0 — отрицательная тональность, 1 — положительная)</span><span class="sxs-lookup"><span data-stu-id="37bd2-183">Label (0 when negative sentiment, 1 when positive)</span></span>|<span data-ttu-id="37bd2-184">Комментарий, год</span><span class="sxs-lookup"><span data-stu-id="37bd2-184">Comment, Year</span></span>|
|<span data-ttu-id="37bd2-185">Обнаружение мошенничества.</span><span class="sxs-lookup"><span data-stu-id="37bd2-185">Fraud detection</span></span>|<span data-ttu-id="37bd2-186">двоичная классификация;</span><span class="sxs-lookup"><span data-stu-id="37bd2-186">binary classification</span></span>|[<span data-ttu-id="37bd2-187">данные по кредитным картам</span><span class="sxs-lookup"><span data-stu-id="37bd2-187">credit card data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|<span data-ttu-id="37bd2-188">Класс (1 — мошенничество, 0 — нет)</span><span class="sxs-lookup"><span data-stu-id="37bd2-188">Class (1 when fraudulent, 0 otherwise)</span></span>|<span data-ttu-id="37bd2-189">Сумма, V1–V28 (анонимизированные признаки)</span><span class="sxs-lookup"><span data-stu-id="37bd2-189">Amount, V1-V28 (anonymized features)</span></span>|
|<span data-ttu-id="37bd2-190">Классификация текста</span><span class="sxs-lookup"><span data-stu-id="37bd2-190">Text classification</span></span>|<span data-ttu-id="37bd2-191">классификация по нескольким классам.</span><span class="sxs-lookup"><span data-stu-id="37bd2-191">multiclass classification</span></span>|[<span data-ttu-id="37bd2-192">Данные по проблемам на GitHub</span><span class="sxs-lookup"><span data-stu-id="37bd2-192">GitHub issue data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|<span data-ttu-id="37bd2-193">Область</span><span class="sxs-lookup"><span data-stu-id="37bd2-193">Area</span></span>|<span data-ttu-id="37bd2-194">Название, описание</span><span class="sxs-lookup"><span data-stu-id="37bd2-194">Title, Description</span></span>|

## <a name="train"></a><span data-ttu-id="37bd2-195">Обучение</span><span class="sxs-lookup"><span data-stu-id="37bd2-195">Train</span></span>

<span data-ttu-id="37bd2-196">После выбора сценария, данных и метки построитель моделей обучает модель.</span><span class="sxs-lookup"><span data-stu-id="37bd2-196">Once you select your scenario, data, and label, Model Builder trains the model.</span></span>

### <a name="what-is-training"></a><span data-ttu-id="37bd2-197">Сведения об обучении</span><span class="sxs-lookup"><span data-stu-id="37bd2-197">What is training?</span></span>

<span data-ttu-id="37bd2-198">Обучение — это автоматический процесс, посредством которого построитель моделей учит модель отвечать на вопросы в рамках сценария.</span><span class="sxs-lookup"><span data-stu-id="37bd2-198">Training is an automatic process by which Model Builder teaches your model how to answer questions for your scenario.</span></span> <span data-ttu-id="37bd2-199">После обучения модель может делать прогнозы на основе новых входных данных.</span><span class="sxs-lookup"><span data-stu-id="37bd2-199">Once trained, your model can make predictions with input data that it has not seen before.</span></span> <span data-ttu-id="37bd2-200">Например, если модель прогнозирует цены на недвижимость и на рынке появляется новый дом, она может спрогнозировать цену его продажи.</span><span class="sxs-lookup"><span data-stu-id="37bd2-200">For example, if you are predicting house prices and a new house comes on the market, you can predict its sale price.</span></span>

<span data-ttu-id="37bd2-201">Так как построитель моделей использует автоматизированное машинное обучение (AutoML), во время обучения вводить данные или производить настройку не нужно.</span><span class="sxs-lookup"><span data-stu-id="37bd2-201">Because Model Builder uses automated machine learning (AutoML), it does not require any input or tuning from you during training.</span></span>

## <a name="evaluate"></a><span data-ttu-id="37bd2-202">Оценка</span><span class="sxs-lookup"><span data-stu-id="37bd2-202">Evaluate</span></span>

<span data-ttu-id="37bd2-203">Оценка — это процесс использования обученной модели для составления прогнозов на основе новых данных с последующим измерением их точности.</span><span class="sxs-lookup"><span data-stu-id="37bd2-203">Evaluation is the process of using the trained model to make predictions with new test data, and then measuring how good the predictions are.</span></span>

<span data-ttu-id="37bd2-204">Построитель моделей разделяет обучающие данные на набор для обучения и тестовый набор.</span><span class="sxs-lookup"><span data-stu-id="37bd2-204">Model Builder splits the training data into a training set and a test set.</span></span> <span data-ttu-id="37bd2-205">Обучающие данные (80 %) служат для обучения модели, а тестовые (20 %) резервируются для ее оценки.</span><span class="sxs-lookup"><span data-stu-id="37bd2-205">The training data (80%) is used to train your model and the test data (20%) is held back to evaluate your model.</span></span> <span data-ttu-id="37bd2-206">Построитель моделей использует метрики для измерения качества модели.</span><span class="sxs-lookup"><span data-stu-id="37bd2-206">Model Builder uses metrics to measure how good the model is.</span></span> <span data-ttu-id="37bd2-207">Используемые метрики зависят от типа модели.</span><span class="sxs-lookup"><span data-stu-id="37bd2-207">The specific metrics used are dependent on the type of model.</span></span> <span data-ttu-id="37bd2-208">Дополнительные сведения см. в статье [Метрики оценки модели](resources/metrics.md).</span><span class="sxs-lookup"><span data-stu-id="37bd2-208">For more information, see [model evaluation metrics](resources/metrics.md).</span></span>

## <a name="improve"></a><span data-ttu-id="37bd2-209">Улучшение</span><span class="sxs-lookup"><span data-stu-id="37bd2-209">Improve</span></span>

<span data-ttu-id="37bd2-210">Если точность модели недостаточно высока, можно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="37bd2-210">If your model performance score is not as good as you want it to be, you can:</span></span>

- <span data-ttu-id="37bd2-211">Увеличить время обучения.</span><span class="sxs-lookup"><span data-stu-id="37bd2-211">Train for a longer period of time.</span></span> <span data-ttu-id="37bd2-212">Чем дольше длится обучение, тем больше алгоритмов и параметров может опробовать система машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="37bd2-212">With more time, the automated machine learning engine to try more algorithms and settings.</span></span>

- <span data-ttu-id="37bd2-213">Добавить больше данных.</span><span class="sxs-lookup"><span data-stu-id="37bd2-213">Add more data.</span></span> <span data-ttu-id="37bd2-214">Иногда для подготовки качественной модели машинного обучения недостаточно данных.</span><span class="sxs-lookup"><span data-stu-id="37bd2-214">Sometimes the amount of data is not sufficient to train a high-quality machine learning model.</span></span>

- <span data-ttu-id="37bd2-215">Сбалансировать данные.</span><span class="sxs-lookup"><span data-stu-id="37bd2-215">Balance your data.</span></span> <span data-ttu-id="37bd2-216">Для задач классификации обучающий набор должен быть сбалансирован по всем категориям.</span><span class="sxs-lookup"><span data-stu-id="37bd2-216">For classification tasks, make sure that the training set is balanced across the categories.</span></span> <span data-ttu-id="37bd2-217">Например, если имеются четыре класса для 100 образцов, причем первые два класса (тег1 и тег2) используются для 90 записей, а другие два (тег3 и тег4) — для остальных 10 записей, несбалансированность данных может сказаться на правильности прогнозирования классов тег3 и тег4.</span><span class="sxs-lookup"><span data-stu-id="37bd2-217">For example, if you have four classes for 100 training examples, and the two first classes (tag1 and tag2) are used for 90 records, but the other two (tag3 and tag4) are only used on the remaining 10 records, the lack of balanced data may cause your model to struggle to correctly predict tag3 or tag4.</span></span>

## <a name="code"></a><span data-ttu-id="37bd2-218">Код</span><span class="sxs-lookup"><span data-stu-id="37bd2-218">Code</span></span>

<span data-ttu-id="37bd2-219">После этапа оценки построитель моделей предоставляет файл модели и код, с помощью которого можно добавить модель в свое приложение.</span><span class="sxs-lookup"><span data-stu-id="37bd2-219">After the evaluation phase, Model Builder outputs a model file, and code that you can use to add the model to your application.</span></span> <span data-ttu-id="37bd2-220">Модели ML.NET сохраняются как ZIP-файлы.</span><span class="sxs-lookup"><span data-stu-id="37bd2-220">ML.NET models are saved as a zip file.</span></span> <span data-ttu-id="37bd2-221">Код для загрузки и использования модели добавляется в решение как новый проект.</span><span class="sxs-lookup"><span data-stu-id="37bd2-221">The code to load and use your model is added as a new project in your solution.</span></span> <span data-ttu-id="37bd2-222">Кроме того, построитель моделей добавляет для примера консольное приложение, которое можно запустить, чтобы увидеть модель в действии.</span><span class="sxs-lookup"><span data-stu-id="37bd2-222">Model Builder also adds a sample console app that you can run to see your model in action.</span></span>

<span data-ttu-id="37bd2-223">Построитель моделей также выводит код, использовавшийся для создания модели, чтобы можно было понять, как именно она формировалась.</span><span class="sxs-lookup"><span data-stu-id="37bd2-223">In addition, Model Builder outputs the code that generated the model, so that you can understand the steps used to generate the model.</span></span> <span data-ttu-id="37bd2-224">Код обучения модели можно использовать для повторного обучения на основе новых данных.</span><span class="sxs-lookup"><span data-stu-id="37bd2-224">You can also use the model training code to retrain your model with new data.</span></span>

## <a name="whats-next"></a><span data-ttu-id="37bd2-225">Что дальше?</span><span class="sxs-lookup"><span data-stu-id="37bd2-225">What's next?</span></span>

<span data-ttu-id="37bd2-226">[Установите](how-to-guides/install-model-builder.md) расширение "Построитель моделей" для Visual Studio</span><span class="sxs-lookup"><span data-stu-id="37bd2-226">[Install](how-to-guides/install-model-builder.md) the Model Builder Visual Studio extension</span></span>

<span data-ttu-id="37bd2-227">Попробуйте [сценарий прогнозирования цен или любой сценарий регрессии](tutorials/predict-prices-with-model-builder.md)</span><span class="sxs-lookup"><span data-stu-id="37bd2-227">Try [price prediction or any regression scenario](tutorials/predict-prices-with-model-builder.md)</span></span>
