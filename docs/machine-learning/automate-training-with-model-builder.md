---
title: Построитель моделей и принципы его работы
description: Сведения об использовании построителя моделей ML.NET для автоматического обучения модели машинного обучения
ms.date: 01/07/2020
ms.custom: overview
ms.openlocfilehash: ac704b7961a8442a9174cdef5a4cd2a619236a4e
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777394"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a><span data-ttu-id="4ed09-103">Построитель моделей и принципы его работы</span><span class="sxs-lookup"><span data-stu-id="4ed09-103">What is Model Builder and how does it work?</span></span>

<span data-ttu-id="4ed09-104">Построитель моделей ML.NET — это интуитивно понятное графическое расширение Visual Studio для создания, обучения и развертывания пользовательских моделей машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="4ed09-104">ML.NET Model Builder is an intuitive graphical Visual Studio extension to build, train, and deploy custom machine learning models.</span></span>

<span data-ttu-id="4ed09-105">Построитель моделей использует автоматизированное машинное обучение (AutoML) для анализа различных алгоритмов и параметров машинного обучения и выбора наиболее подходящих из них для конкретного сценария.</span><span class="sxs-lookup"><span data-stu-id="4ed09-105">Model Builder uses automated machine learning (AutoML) to explore different machine learning algorithms and settings to help you find the one that best suits your scenario.</span></span>

<span data-ttu-id="4ed09-106">Для работы с построителем моделей не нужно быть экспертом в области машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="4ed09-106">You don't need machine learning expertise to use Model Builder.</span></span> <span data-ttu-id="4ed09-107">Все, что требуется, — это данные и проблема, которую нужно решить.</span><span class="sxs-lookup"><span data-stu-id="4ed09-107">All you need is some data, and a problem to solve.</span></span> <span data-ttu-id="4ed09-108">Построитель моделей генерирует код для добавления модели в приложение .NET.</span><span class="sxs-lookup"><span data-stu-id="4ed09-108">Model Builder generates the code to add the model to your .NET application.</span></span>

![Анимация: пользовательский интерфейс расширения "Построитель моделей" для Visual Studio](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> <span data-ttu-id="4ed09-110">Построитель моделей в настоящее время находится на этапе предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="4ed09-110">Model Builder is currently in Preview.</span></span>

## <a name="scenarios"></a><span data-ttu-id="4ed09-111">Сценарии</span><span class="sxs-lookup"><span data-stu-id="4ed09-111">Scenarios</span></span>

<span data-ttu-id="4ed09-112">Построитель моделей может создавать модели машинного обучения для приложения на основе множества различных сценариев.</span><span class="sxs-lookup"><span data-stu-id="4ed09-112">You can bring many different scenarios to Model Builder, to generate a machine learning model for your application.</span></span>

<span data-ttu-id="4ed09-113">Сценарий описывает тип прогноза, который нужно сделать с использованием данных.</span><span class="sxs-lookup"><span data-stu-id="4ed09-113">A scenario is a description of the type of prediction you want to make using your data.</span></span> <span data-ttu-id="4ed09-114">Пример:</span><span class="sxs-lookup"><span data-stu-id="4ed09-114">For example:</span></span>

- <span data-ttu-id="4ed09-115">прогнозирование будущего объема продаж продукта на основе исторических данных по продажам;</span><span class="sxs-lookup"><span data-stu-id="4ed09-115">predict future product sales volume based on historical sales data</span></span>
- <span data-ttu-id="4ed09-116">классификация тональности как положительной или отрицательной на основе отзывов клиентов;</span><span class="sxs-lookup"><span data-stu-id="4ed09-116">classify sentiments as positive or negative based on customer reviews</span></span>
- <span data-ttu-id="4ed09-117">определение того, является ли банковская операция мошеннической;</span><span class="sxs-lookup"><span data-stu-id="4ed09-117">detect whether a banking transaction is fraudulent</span></span>
- <span data-ttu-id="4ed09-118">направление проблем, с которыми обращаются клиенты, на рассмотрение соответствующим сотрудникам компании.</span><span class="sxs-lookup"><span data-stu-id="4ed09-118">route customer feedback issues to the correct team in your company</span></span>

### <a name="which-machine-learning-scenario-is-right-for-me"></a><span data-ttu-id="4ed09-119">Выбор подходящего сценария машинного обучения</span><span class="sxs-lookup"><span data-stu-id="4ed09-119">Which machine learning scenario is right for me?</span></span>

<span data-ttu-id="4ed09-120">В построителе моделей необходимо выбрать сценарий.</span><span class="sxs-lookup"><span data-stu-id="4ed09-120">In Model Builder, you need to select a scenario.</span></span> <span data-ttu-id="4ed09-121">Тип сценария зависит от того, какой прогноз вы пытаетесь сделать.</span><span class="sxs-lookup"><span data-stu-id="4ed09-121">The type of scenario depends on what type of prediction you are trying to make.</span></span>

#### <a name="predict-a-category-when-there-are-only-two-categories"></a><span data-ttu-id="4ed09-122">Прогнозирование категории (при наличии только двух категорий)</span><span class="sxs-lookup"><span data-stu-id="4ed09-122">Predict a category (when there are only two categories)</span></span>

<span data-ttu-id="4ed09-123">Двоичная классификация служит для разделения данных на две категории (да или нет, успех или неудача, истина или ложь, положительные или отрицательные).</span><span class="sxs-lookup"><span data-stu-id="4ed09-123">Binary classification is used to categorize data into two categories (yes/no; pass/fail; true/false; positive/negative).</span></span>

![Схема с примерами двоичной классификации, включая обнаружение мошенничества, устранение рисков и блокировку приложений](media/binary-classification-examples.png)

<span data-ttu-id="4ed09-125">Анализ тональности можно использовать для определения положительной или отрицательной тональности отзыва клиента.</span><span class="sxs-lookup"><span data-stu-id="4ed09-125">Sentiment analysis can be used to predict positive or negative sentiment of customer feedback.</span></span> <span data-ttu-id="4ed09-126">Это пример такой задачи машинного обучения, как двоичная классификация.</span><span class="sxs-lookup"><span data-stu-id="4ed09-126">It is an example of the binary classification machine learning task.</span></span>

<span data-ttu-id="4ed09-127">Если ваш сценарий требует классификации на две категории, вы можете использовать этот шаблон со своим набором данных.</span><span class="sxs-lookup"><span data-stu-id="4ed09-127">If your scenario requires classification into two categories, you can use this template with your own dataset.</span></span>

#### <a name="predict-a-category-when-there-are-three-or-more-categories"></a><span data-ttu-id="4ed09-128">Прогнозирование категории (при наличии трех или более категорий)</span><span class="sxs-lookup"><span data-stu-id="4ed09-128">Predict a category (when there are three or more categories)</span></span>

<span data-ttu-id="4ed09-129">Многоклассовая классификация служит для разделения данных на три или более категорий.</span><span class="sxs-lookup"><span data-stu-id="4ed09-129">Multiclass classification can be used to categorize data into three or more classes.</span></span>

![Примеры многоклассовой классификации, включая классификацию документов и продуктов, маршрутизацию запросов в службу поддержки и определение приоритетности клиентских проблем](media/multiclass-classification-examples.png)

<span data-ttu-id="4ed09-131">С помощью классификации проблем можно разделять проблемы, о которых сообщают клиенты (например, на GitHub), на категории исходя из их названий и описаний.</span><span class="sxs-lookup"><span data-stu-id="4ed09-131">Issue classification can be used to categorize customer feedback (for example, on GitHub) issues using the issue title and description.</span></span> <span data-ttu-id="4ed09-132">Это пример такой задачи машинного обучения, как многоклассовая классификация.</span><span class="sxs-lookup"><span data-stu-id="4ed09-132">It is an example of the multi-class classification machine learning task.</span></span>

<span data-ttu-id="4ed09-133">Шаблон многоклассовой классификации можно использовать для сценария, который предполагает разделение данных на три или более категорий.</span><span class="sxs-lookup"><span data-stu-id="4ed09-133">You can use the issue classification template for your scenario if you want to categorize data into three or more categories.</span></span>

#### <a name="predict-a-number"></a><span data-ttu-id="4ed09-134">Прогнозирование числа</span><span class="sxs-lookup"><span data-stu-id="4ed09-134">Predict a number</span></span>

<span data-ttu-id="4ed09-135">Регрессия служит для прогнозирования числовых значений.</span><span class="sxs-lookup"><span data-stu-id="4ed09-135">Regression is used to predict numbers.</span></span>

![Схема с примерами регрессии, включая прогнозирование цен, прогнозирование продаж и прогнозное обслуживание](media/regression-examples.png)

<span data-ttu-id="4ed09-137">С помощью прогнозирования цен можно прогнозировать цены на недвижимость исходя из местоположения, площади и других характеристик объекта недвижимости.</span><span class="sxs-lookup"><span data-stu-id="4ed09-137">Price prediction can be used to predict house prices using location, size, and other characteristics of the house.</span></span> <span data-ttu-id="4ed09-138">Это пример такой задачи машинного обучения, как регрессия.</span><span class="sxs-lookup"><span data-stu-id="4ed09-138">It is an example of the regression machine learning task.</span></span>

<span data-ttu-id="4ed09-139">Шаблон прогнозирования цен можно использовать для сценария, который предполагает прогнозирование числовых значений на основе собственного набора данных.</span><span class="sxs-lookup"><span data-stu-id="4ed09-139">You can use the price prediction template for your scenario if you want to predict a numerical value with your own dataset.</span></span>

#### <a name="classify-images-into-categories"></a><span data-ttu-id="4ed09-140">Классификация изображений по категориям</span><span class="sxs-lookup"><span data-stu-id="4ed09-140">Classify images into categories</span></span>

<span data-ttu-id="4ed09-141">Этот сценарий является особым случаем многоклассовой классификации, при котором входные данные, которые нужно классифицировать, представляют собой набор изображений.</span><span class="sxs-lookup"><span data-stu-id="4ed09-141">This scenario is a special case of multiclass classification, where the input data to be categorized is a set of images.</span></span>

<span data-ttu-id="4ed09-142">Классификация изображений помогает идентифицировать изображения разных категорий.</span><span class="sxs-lookup"><span data-stu-id="4ed09-142">Image classification can be used to identify images of different categories.</span></span> <span data-ttu-id="4ed09-143">Например, различные виды рельефа, животных или производственного брака.</span><span class="sxs-lookup"><span data-stu-id="4ed09-143">For example, different types of terrain or animals or manufacturing defects.</span></span>

<span data-ttu-id="4ed09-144">Вы можете использовать шаблон классификации изображений для своего сценария, если у вас есть набор изображений и вы хотите классифицировать изображения по различным категориям.</span><span class="sxs-lookup"><span data-stu-id="4ed09-144">You can use the image classification template for your scenario if you have a set of images, and you want to classify the images into different categories.</span></span>

#### <a name="custom-scenario"></a><span data-ttu-id="4ed09-145">Пользовательский сценарий</span><span class="sxs-lookup"><span data-stu-id="4ed09-145">Custom scenario</span></span>

<span data-ttu-id="4ed09-146">Пользовательский сценарий позволяет выбрать сценарий вручную.</span><span class="sxs-lookup"><span data-stu-id="4ed09-146">The custom scenario allows you to manually choose your scenario.</span></span>

## <a name="data"></a><span data-ttu-id="4ed09-147">Data</span><span class="sxs-lookup"><span data-stu-id="4ed09-147">Data</span></span>

<span data-ttu-id="4ed09-148">После выбора сценария построитель моделей попросит вас предоставить набор данных.</span><span class="sxs-lookup"><span data-stu-id="4ed09-148">Once you have chosen your scenario, Model Builder asks you to provide a dataset.</span></span> <span data-ttu-id="4ed09-149">Данные используются для обучения, оценки и выбора оптимальной модели для сценария.</span><span class="sxs-lookup"><span data-stu-id="4ed09-149">The data is used to train, evaluate, and choose the best model for your scenario.</span></span>

![Схема, демонстрирующая этапы работы построителя моделей](media/model-builder-steps.png)

<span data-ttu-id="4ed09-151">Построитель моделей поддерживает наборы данных в форматах TSV, CSV, TXT, а также в формате базы данных SQL.</span><span class="sxs-lookup"><span data-stu-id="4ed09-151">Model Builder supports datasets in .tsv, .csv, .txt formats, as well as SQL database format.</span></span> <span data-ttu-id="4ed09-152">При использовании TXT-файла добавьте в него строку заголовка и разделите столбцы с помощью символов `,`, `;` или `/t`.</span><span class="sxs-lookup"><span data-stu-id="4ed09-152">If you have a .txt file, columns should be separated with `,`, `;` or `/t` and the file must have a header row.</span></span>

<span data-ttu-id="4ed09-153">При использовании набора данных, состоящего из изображений, поддерживаются файлы с такими расширениями: `.jpg` и `.png`.</span><span class="sxs-lookup"><span data-stu-id="4ed09-153">If the dataset is made up of images, the supported file types are `.jpg` and `.png`.</span></span>

<span data-ttu-id="4ed09-154">Дополнительные сведения см. в статье [Загрузка данных для обучения в построитель моделей](how-to-guides/load-data-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="4ed09-154">For more information, see [Load training data into Model Builder](how-to-guides/load-data-model-builder.md).</span></span>

### <a name="choose-the-output-to-predict-label"></a><span data-ttu-id="4ed09-155">Выбор результата для прогнозирования (метка)</span><span class="sxs-lookup"><span data-stu-id="4ed09-155">Choose the output to predict (label)</span></span>

<span data-ttu-id="4ed09-156">Набор данных — это таблица, строки которой содержат образцы для обучения, а столбцы — атрибуты.</span><span class="sxs-lookup"><span data-stu-id="4ed09-156">A dataset is a table of rows of training examples, and columns of attributes.</span></span> <span data-ttu-id="4ed09-157">В каждой строке есть:</span><span class="sxs-lookup"><span data-stu-id="4ed09-157">Each row has:</span></span>

- <span data-ttu-id="4ed09-158">**метка** (атрибут, который нужно спрогнозировать);</span><span class="sxs-lookup"><span data-stu-id="4ed09-158">a **label** (the attribute that you want to predict)</span></span>
- <span data-ttu-id="4ed09-159">**признаки** (атрибуты, исходя из которых прогнозируется метка).</span><span class="sxs-lookup"><span data-stu-id="4ed09-159">**features** (attributes that are used as inputs to predict the label).</span></span>

<span data-ttu-id="4ed09-160">В сценарии прогнозирования цен на недвижимость признаками могут быть:</span><span class="sxs-lookup"><span data-stu-id="4ed09-160">For the house-price prediction scenario, the features could be:</span></span>

- <span data-ttu-id="4ed09-161">площадь дома;</span><span class="sxs-lookup"><span data-stu-id="4ed09-161">the square footage of the house</span></span>
- <span data-ttu-id="4ed09-162">количество спален и ванных комнат;</span><span class="sxs-lookup"><span data-stu-id="4ed09-162">the number of bedrooms and bathrooms</span></span>
- <span data-ttu-id="4ed09-163">почтовый индекс.</span><span class="sxs-lookup"><span data-stu-id="4ed09-163">the zip code</span></span>

<span data-ttu-id="4ed09-164">Метка — это историческая цена на дом данной площади, с данным количеством спален и ванных комнат, а также почтовым индексом.</span><span class="sxs-lookup"><span data-stu-id="4ed09-164">The label is the historical house price for that row of square footage, bedroom, and bathroom values and zip code.</span></span>

![Таблица цен на недвижимость, содержащая признаки (площадь, количество комнат, почтовый индекс) и метку (цена)](media/model-builder-data.png)

### <a name="example-datasets"></a><span data-ttu-id="4ed09-166">Примеры наборов данных</span><span class="sxs-lookup"><span data-stu-id="4ed09-166">Example datasets</span></span>

<span data-ttu-id="4ed09-167">Если у вас нет собственного набора данных, можно воспользоваться одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="4ed09-167">If you don't have your own data yet, try out one of these datasets:</span></span>

|<span data-ttu-id="4ed09-168">Сценарий</span><span class="sxs-lookup"><span data-stu-id="4ed09-168">Scenario</span></span>|<span data-ttu-id="4ed09-169">Задача машинного обучения</span><span class="sxs-lookup"><span data-stu-id="4ed09-169">ML task</span></span>|<span data-ttu-id="4ed09-170">Data</span><span class="sxs-lookup"><span data-stu-id="4ed09-170">Data</span></span>|<span data-ttu-id="4ed09-171">Метка</span><span class="sxs-lookup"><span data-stu-id="4ed09-171">Label</span></span>|<span data-ttu-id="4ed09-172">Функции</span><span class="sxs-lookup"><span data-stu-id="4ed09-172">Features</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="4ed09-173">Прогнозирование цен</span><span class="sxs-lookup"><span data-stu-id="4ed09-173">Price prediction</span></span>|<span data-ttu-id="4ed09-174">регрессия</span><span class="sxs-lookup"><span data-stu-id="4ed09-174">regression</span></span>|[<span data-ttu-id="4ed09-175">данные по платам за такси</span><span class="sxs-lookup"><span data-stu-id="4ed09-175">taxi fare data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|<span data-ttu-id="4ed09-176">Плата</span><span class="sxs-lookup"><span data-stu-id="4ed09-176">Fare</span></span>|<span data-ttu-id="4ed09-177">Время поездки, расстояние</span><span class="sxs-lookup"><span data-stu-id="4ed09-177">Trip time, distance</span></span>|
|<span data-ttu-id="4ed09-178">Обнаружение аномалий</span><span class="sxs-lookup"><span data-stu-id="4ed09-178">Anomaly detection</span></span>|<span data-ttu-id="4ed09-179">двоичная классификация</span><span class="sxs-lookup"><span data-stu-id="4ed09-179">binary classification</span></span>|[<span data-ttu-id="4ed09-180">данные по продажам продуктов</span><span class="sxs-lookup"><span data-stu-id="4ed09-180">product sales data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|<span data-ttu-id="4ed09-181">Продажи продукта</span><span class="sxs-lookup"><span data-stu-id="4ed09-181">Product Sales</span></span>|<span data-ttu-id="4ed09-182">Месяц</span><span class="sxs-lookup"><span data-stu-id="4ed09-182">Month</span></span>|
|<span data-ttu-id="4ed09-183">Анализ тональности</span><span class="sxs-lookup"><span data-stu-id="4ed09-183">Sentiment analysis</span></span>|<span data-ttu-id="4ed09-184">двоичная классификация</span><span class="sxs-lookup"><span data-stu-id="4ed09-184">binary classification</span></span>|[<span data-ttu-id="4ed09-185">данные по комментариям на веб-сайте</span><span class="sxs-lookup"><span data-stu-id="4ed09-185">website comment data</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|<span data-ttu-id="4ed09-186">Метка (0 — отрицательная тональность, 1 — положительная)</span><span class="sxs-lookup"><span data-stu-id="4ed09-186">Label (0 when negative sentiment, 1 when positive)</span></span>|<span data-ttu-id="4ed09-187">Комментарий, год</span><span class="sxs-lookup"><span data-stu-id="4ed09-187">Comment, Year</span></span>|
|<span data-ttu-id="4ed09-188">Обнаружение мошенничества</span><span class="sxs-lookup"><span data-stu-id="4ed09-188">Fraud detection</span></span>|<span data-ttu-id="4ed09-189">двоичная классификация</span><span class="sxs-lookup"><span data-stu-id="4ed09-189">binary classification</span></span>|[<span data-ttu-id="4ed09-190">данные по кредитным картам</span><span class="sxs-lookup"><span data-stu-id="4ed09-190">credit card data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|<span data-ttu-id="4ed09-191">Класс (1 — мошенничество, 0 — нет)</span><span class="sxs-lookup"><span data-stu-id="4ed09-191">Class (1 when fraudulent, 0 otherwise)</span></span>|<span data-ttu-id="4ed09-192">Сумма, V1–V28 (анонимизированные признаки)</span><span class="sxs-lookup"><span data-stu-id="4ed09-192">Amount, V1-V28 (anonymized features)</span></span>|
|<span data-ttu-id="4ed09-193">Классификация текста</span><span class="sxs-lookup"><span data-stu-id="4ed09-193">Text classification</span></span>|<span data-ttu-id="4ed09-194">многоклассовая классификация</span><span class="sxs-lookup"><span data-stu-id="4ed09-194">multiclass classification</span></span>|[<span data-ttu-id="4ed09-195">Данные по проблемам на GitHub</span><span class="sxs-lookup"><span data-stu-id="4ed09-195">GitHub issue data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|<span data-ttu-id="4ed09-196">Область</span><span class="sxs-lookup"><span data-stu-id="4ed09-196">Area</span></span>|<span data-ttu-id="4ed09-197">Название, описание</span><span class="sxs-lookup"><span data-stu-id="4ed09-197">Title, Description</span></span>|
|<span data-ttu-id="4ed09-198">Классификация изображений</span><span class="sxs-lookup"><span data-stu-id="4ed09-198">Image classification</span></span>|<span data-ttu-id="4ed09-199">многоклассовая классификация</span><span class="sxs-lookup"><span data-stu-id="4ed09-199">multiclass classification</span></span>|[<span data-ttu-id="4ed09-200">Изображения с цветами</span><span class="sxs-lookup"><span data-stu-id="4ed09-200">Flowers images</span></span>](http://download.tensorflow.org/example_images/flower_photos.tgz)|<span data-ttu-id="4ed09-201">Вид цветов: маргаритки, одуванчики, розы, подсолнухи, тюльпаны</span><span class="sxs-lookup"><span data-stu-id="4ed09-201">The type of flower: daisy, dandelion, roses, sunflowers, tulips</span></span>|<span data-ttu-id="4ed09-202">Данные изображения</span><span class="sxs-lookup"><span data-stu-id="4ed09-202">The image data itself</span></span>|

## <a name="train"></a><span data-ttu-id="4ed09-203">Обучение</span><span class="sxs-lookup"><span data-stu-id="4ed09-203">Train</span></span>

<span data-ttu-id="4ed09-204">После выбора сценария, данных и метки построитель моделей обучает модель.</span><span class="sxs-lookup"><span data-stu-id="4ed09-204">Once you select your scenario, data, and label, Model Builder trains the model.</span></span>

### <a name="what-is-training"></a><span data-ttu-id="4ed09-205">Сведения об обучении</span><span class="sxs-lookup"><span data-stu-id="4ed09-205">What is training?</span></span>

<span data-ttu-id="4ed09-206">Обучение — это автоматический процесс, посредством которого построитель моделей учит модель отвечать на вопросы в рамках сценария.</span><span class="sxs-lookup"><span data-stu-id="4ed09-206">Training is an automatic process by which Model Builder teaches your model how to answer questions for your scenario.</span></span> <span data-ttu-id="4ed09-207">После обучения модель может делать прогнозы на основе новых входных данных.</span><span class="sxs-lookup"><span data-stu-id="4ed09-207">Once trained, your model can make predictions with input data that it has not seen before.</span></span> <span data-ttu-id="4ed09-208">Например, если модель прогнозирует цены на недвижимость и на рынке появляется новый дом, она может спрогнозировать цену его продажи.</span><span class="sxs-lookup"><span data-stu-id="4ed09-208">For example, if you are predicting house prices and a new house comes on the market, you can predict its sale price.</span></span>

<span data-ttu-id="4ed09-209">Так как построитель моделей использует автоматизированное машинное обучение (AutoML), во время обучения вводить данные или производить настройку не нужно.</span><span class="sxs-lookup"><span data-stu-id="4ed09-209">Because Model Builder uses automated machine learning (AutoML), it does not require any input or tuning from you during training.</span></span>

### <a name="how-long-should-i-train-for"></a><span data-ttu-id="4ed09-210">Требуемая длительность обучения</span><span class="sxs-lookup"><span data-stu-id="4ed09-210">How long should I train for?</span></span>

<span data-ttu-id="4ed09-211">С помощью AutoML построитель моделей изучает несколько моделей, определяя самую эффективную.</span><span class="sxs-lookup"><span data-stu-id="4ed09-211">Model Builder uses AutoML to explore multiple models to find you the best performing model.</span></span>

<span data-ttu-id="4ed09-212">Более длительное время обучения позволяет AutoML исследовать больше моделей с более широким диапазоном параметров.</span><span class="sxs-lookup"><span data-stu-id="4ed09-212">Longer training periods allow AutoML to explore more models with a wider range of settings.</span></span>

<span data-ttu-id="4ed09-213">В приведенной ниже таблице указано обобщенное среднее время, необходимое для получения хорошей эффективности для набора примеров наборов данных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4ed09-213">The table below summarizes the average time taken to get good performance for a suite of example datasets, on a local machine.</span></span>

|<span data-ttu-id="4ed09-214">Размер набора данных</span><span class="sxs-lookup"><span data-stu-id="4ed09-214">Dataset size</span></span>|<span data-ttu-id="4ed09-215">Среднее время обучения</span><span class="sxs-lookup"><span data-stu-id="4ed09-215">Average time to train</span></span>|
|------------|---------------------|
|<span data-ttu-id="4ed09-216">0–10 МБ</span><span class="sxs-lookup"><span data-stu-id="4ed09-216">0 - 10 MB</span></span>|<span data-ttu-id="4ed09-217">10 с</span><span class="sxs-lookup"><span data-stu-id="4ed09-217">10 sec</span></span>|
|<span data-ttu-id="4ed09-218">10–100 МБ</span><span class="sxs-lookup"><span data-stu-id="4ed09-218">10 - 100 MB</span></span>|<span data-ttu-id="4ed09-219">10 мин</span><span class="sxs-lookup"><span data-stu-id="4ed09-219">10 min</span></span>|
|<span data-ttu-id="4ed09-220">100–500 МБ</span><span class="sxs-lookup"><span data-stu-id="4ed09-220">100 - 500 MB</span></span>|<span data-ttu-id="4ed09-221">30 мин</span><span class="sxs-lookup"><span data-stu-id="4ed09-221">30 min</span></span>|
|<span data-ttu-id="4ed09-222">500 МБ — 1 ГБ</span><span class="sxs-lookup"><span data-stu-id="4ed09-222">500 - 1 GB</span></span>|<span data-ttu-id="4ed09-223">60 мин</span><span class="sxs-lookup"><span data-stu-id="4ed09-223">60 min</span></span>|
|<span data-ttu-id="4ed09-224">Более 1 ГБ</span><span class="sxs-lookup"><span data-stu-id="4ed09-224">1 GB+</span></span>|<span data-ttu-id="4ed09-225">Более 3 часов</span><span class="sxs-lookup"><span data-stu-id="4ed09-225">3+ hours</span></span>|

<span data-ttu-id="4ed09-226">Это ориентировочные числа.</span><span class="sxs-lookup"><span data-stu-id="4ed09-226">These numbers are a guide only.</span></span> <span data-ttu-id="4ed09-227">Точная продолжительность обучения зависит от:</span><span class="sxs-lookup"><span data-stu-id="4ed09-227">The exact length of training is dependent on:</span></span>

- <span data-ttu-id="4ed09-228">количества признаков (столбцов), используемых в качестве входных данных для модели;</span><span class="sxs-lookup"><span data-stu-id="4ed09-228">the number of features (columns) being used to as input to the model</span></span>
- <span data-ttu-id="4ed09-229">типа столбцов;</span><span class="sxs-lookup"><span data-stu-id="4ed09-229">the type of columns</span></span>
- <span data-ttu-id="4ed09-230">задачи машинного обучения;</span><span class="sxs-lookup"><span data-stu-id="4ed09-230">the ML task</span></span>
- <span data-ttu-id="4ed09-231">производительности ЦП, диска и памяти компьютера, используемого для обучения.</span><span class="sxs-lookup"><span data-stu-id="4ed09-231">the CPU, disk and memory performance of the machine used for training</span></span>

## <a name="evaluate"></a><span data-ttu-id="4ed09-232">Оценка</span><span class="sxs-lookup"><span data-stu-id="4ed09-232">Evaluate</span></span>

<span data-ttu-id="4ed09-233">Оценка — это процесс измерения эффективности модели.</span><span class="sxs-lookup"><span data-stu-id="4ed09-233">Evaluation is the process of measuring how good your model is.</span></span> <span data-ttu-id="4ed09-234">Построитель моделей использует обученную модель для составления прогнозов на основе новых данных с последующим измерением их точности.</span><span class="sxs-lookup"><span data-stu-id="4ed09-234">Model Builder uses the trained model to make predictions with new test data, and then measures how good the predictions are.</span></span>

<span data-ttu-id="4ed09-235">Построитель моделей разделяет обучающие данные на набор для обучения и тестовый набор.</span><span class="sxs-lookup"><span data-stu-id="4ed09-235">Model Builder splits the training data into a training set and a test set.</span></span> <span data-ttu-id="4ed09-236">Обучающие данные (80 %) служат для обучения модели, а тестовые (20 %) резервируются для ее оценки.</span><span class="sxs-lookup"><span data-stu-id="4ed09-236">The training data (80%) is used to train your model and the test data (20%) is held back to evaluate your model.</span></span> 

### <a name="how-do-i-understand-my-model-performance"></a><span data-ttu-id="4ed09-237">Как определить эффективность модели?</span><span class="sxs-lookup"><span data-stu-id="4ed09-237">How do I understand my model performance?</span></span>

<span data-ttu-id="4ed09-238">Сценарий сопоставляется с задачей машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="4ed09-238">A scenario maps to a machine learning task.</span></span> <span data-ttu-id="4ed09-239">Каждая задача машинного обучения имеет собственный набор метрик оценки.</span><span class="sxs-lookup"><span data-stu-id="4ed09-239">Each ML task has its own set of evaluation metrics.</span></span>

#### <a name="regression-for-example-price-prediction"></a><span data-ttu-id="4ed09-240">Регрессия (например, прогнозирование цены)</span><span class="sxs-lookup"><span data-stu-id="4ed09-240">Regression (for example, Price Prediction)</span></span>

<span data-ttu-id="4ed09-241">Метрика по умолчанию для регрессии — коэффициент детерминации, для которого допустимо значение в диапазоне от 0 до 1.</span><span class="sxs-lookup"><span data-stu-id="4ed09-241">The default metric for regression problems is RSquared, the value of RSquared ranges between 0 and 1.</span></span> <span data-ttu-id="4ed09-242">1 — наилучшее из возможных значений. Чем ближе значение коэффициента детерминации к 1, тем выше эффективность вашей модели.</span><span class="sxs-lookup"><span data-stu-id="4ed09-242">1 is the best possible value or in other words the closer the value of RSquared to 1 the better your model is performing.</span></span>

<span data-ttu-id="4ed09-243">Другие метрики, такие как абсолютная потеря, квадратичная потеря и среднеквадратичная потеря, являются дополнительными. Их можно использовать для анализа модели и сравнения ее с другими моделями регрессии.</span><span class="sxs-lookup"><span data-stu-id="4ed09-243">Other metrics reported such as absolute-loss, squared-loss, and RMS loss are additional metrics, which can be used to understand how your model is performing and comparing it against other regression models.</span></span>

#### <a name="binary-classification-for-example-sentiment-analysis"></a><span data-ttu-id="4ed09-244">Двоичная классификация (например, анализ тональности)</span><span class="sxs-lookup"><span data-stu-id="4ed09-244">Binary Classification (for example, Sentiment Analysis)</span></span>

<span data-ttu-id="4ed09-245">Метрика по умолчанию для задач классификации — точность.</span><span class="sxs-lookup"><span data-stu-id="4ed09-245">The default metric for classification problems is accuracy.</span></span> <span data-ttu-id="4ed09-246">Точность — это доля правильных прогнозов, которые модель делает на основе тестового набора данных.</span><span class="sxs-lookup"><span data-stu-id="4ed09-246">Accuracy defines the proportion of correct predictions your model is making over the test dataset.</span></span> <span data-ttu-id="4ed09-247">Чем ближе она к 100 % или 1,0, тем лучше.</span><span class="sxs-lookup"><span data-stu-id="4ed09-247">The closer to 100% or 1.0 the better it is.</span></span>

<span data-ttu-id="4ed09-248">Чтобы модель считалась приемлемой, другие метрики, например площадь под кривой, которая представляет собой отношение доли истинно положительных результатов к доле ложноположительных результатов, должны превышать 0,50.</span><span class="sxs-lookup"><span data-stu-id="4ed09-248">Other metrics reported such as AUC (Area under the curve), which measures the true positive rate vs. the false positive rate should be greater than 0.50 for models to be acceptable.</span></span>

<span data-ttu-id="4ed09-249">Дополнительные метрики, такие как показатель F1, можно использовать для контроля баланса между точностью и полнотой.</span><span class="sxs-lookup"><span data-stu-id="4ed09-249">Additional metrics like F1 score can be used to control the balance between Precision and Recall.</span></span>

#### <a name="multi-class-classification-for-example-issue-classification-image-classification"></a><span data-ttu-id="4ed09-250">Многоклассовая классификация (например, классификация неполадок, классификация изображений)</span><span class="sxs-lookup"><span data-stu-id="4ed09-250">Multi-Class Classification (for example, Issue Classification, Image Classification)</span></span>

<span data-ttu-id="4ed09-251">Метрика по умолчанию для многоклассовой классификации — микроточность.</span><span class="sxs-lookup"><span data-stu-id="4ed09-251">The default metric for Multi-class classification is Micro Accuracy.</span></span> <span data-ttu-id="4ed09-252">Чем ближе значение микроточности к 100 % или 1,0, тем лучше.</span><span class="sxs-lookup"><span data-stu-id="4ed09-252">The closer the Micro Accuracy to 100% or 1.0 the better it is.</span></span>

<span data-ttu-id="4ed09-253">Еще одна важная метрика для многоклассовой классификации — макроточность. Подобно микроточности, чем ближе ее значение к 1,0, тем лучше.</span><span class="sxs-lookup"><span data-stu-id="4ed09-253">Another important metric for Multi-class classification is Macro-accuracy, similar to Micro-accuracy the closer to 1.0 the better it is.</span></span> <span data-ttu-id="4ed09-254">Ниже приведены лучшие определения этих двух типов точности:</span><span class="sxs-lookup"><span data-stu-id="4ed09-254">A good way to think about these two types of accuracy is:</span></span>

- <span data-ttu-id="4ed09-255">Микроточность — как часто входящий запрос передается подходящей команде сотрудников?</span><span class="sxs-lookup"><span data-stu-id="4ed09-255">Micro-accuracy: How often does an incoming ticket get classified to the right team?</span></span>
- <span data-ttu-id="4ed09-256">Макроточность — как часто входящий запрос подходит для команды в среднем случае?</span><span class="sxs-lookup"><span data-stu-id="4ed09-256">Macro-accuracy: For an average team, how often is an incoming ticket correct for their team?</span></span>

### <a name="more-information-on-evaluation-metrics"></a><span data-ttu-id="4ed09-257">Дополнительные сведения о метриках оценки</span><span class="sxs-lookup"><span data-stu-id="4ed09-257">More information on evaluation metrics</span></span>

<span data-ttu-id="4ed09-258">Дополнительные сведения см. в статье [Метрики оценки модели](resources/metrics.md).</span><span class="sxs-lookup"><span data-stu-id="4ed09-258">For more information, see [model evaluation metrics](resources/metrics.md).</span></span>

## <a name="improve"></a><span data-ttu-id="4ed09-259">Улучшение</span><span class="sxs-lookup"><span data-stu-id="4ed09-259">Improve</span></span>

<span data-ttu-id="4ed09-260">Если точность модели недостаточно высока, можно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="4ed09-260">If your model performance score is not as good as you want it to be, you can:</span></span>

- <span data-ttu-id="4ed09-261">Увеличить время обучения.</span><span class="sxs-lookup"><span data-stu-id="4ed09-261">Train for a longer period of time.</span></span> <span data-ttu-id="4ed09-262">Чем дольше длится обучение, тем больше алгоритмов и параметров может опробовать система машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="4ed09-262">With more time, the automated machine learning engine to try more algorithms and settings.</span></span>

- <span data-ttu-id="4ed09-263">Добавить больше данных.</span><span class="sxs-lookup"><span data-stu-id="4ed09-263">Add more data.</span></span> <span data-ttu-id="4ed09-264">Иногда для подготовки качественной модели машинного обучения недостаточно данных.</span><span class="sxs-lookup"><span data-stu-id="4ed09-264">Sometimes the amount of data is not sufficient to train a high-quality machine learning model.</span></span>

- <span data-ttu-id="4ed09-265">Сбалансировать данные.</span><span class="sxs-lookup"><span data-stu-id="4ed09-265">Balance your data.</span></span> <span data-ttu-id="4ed09-266">Для задач классификации обучающий набор должен быть сбалансирован по всем категориям.</span><span class="sxs-lookup"><span data-stu-id="4ed09-266">For classification tasks, make sure that the training set is balanced across the categories.</span></span> <span data-ttu-id="4ed09-267">Например, если имеются четыре класса для 100 образцов, причем первые два класса (тег1 и тег2) используются для 90 записей, а другие два (тег3 и тег4) — для остальных 10 записей, несбалансированность данных может сказаться на правильности прогнозирования классов тег3 и тег4.</span><span class="sxs-lookup"><span data-stu-id="4ed09-267">For example, if you have four classes for 100 training examples, and the two first classes (tag1 and tag2) are used for 90 records, but the other two (tag3 and tag4) are only used on the remaining 10 records, the lack of balanced data may cause your model to struggle to correctly predict tag3 or tag4.</span></span>

## <a name="code"></a><span data-ttu-id="4ed09-268">Код</span><span class="sxs-lookup"><span data-stu-id="4ed09-268">Code</span></span>

<span data-ttu-id="4ed09-269">После этапа оценки построитель моделей предоставляет файл модели и код, с помощью которого можно добавить модель в свое приложение.</span><span class="sxs-lookup"><span data-stu-id="4ed09-269">After the evaluation phase, Model Builder outputs a model file, and code that you can use to add the model to your application.</span></span> <span data-ttu-id="4ed09-270">Модели ML.NET сохраняются как ZIP-файлы.</span><span class="sxs-lookup"><span data-stu-id="4ed09-270">ML.NET models are saved as a zip file.</span></span> <span data-ttu-id="4ed09-271">Код для загрузки и использования модели добавляется в решение как новый проект.</span><span class="sxs-lookup"><span data-stu-id="4ed09-271">The code to load and use your model is added as a new project in your solution.</span></span> <span data-ttu-id="4ed09-272">Кроме того, построитель моделей добавляет для примера консольное приложение, которое можно запустить, чтобы увидеть модель в действии.</span><span class="sxs-lookup"><span data-stu-id="4ed09-272">Model Builder also adds a sample console app that you can run to see your model in action.</span></span>

<span data-ttu-id="4ed09-273">Построитель моделей также выводит код, использовавшийся для создания модели, чтобы можно было понять, как именно она формировалась.</span><span class="sxs-lookup"><span data-stu-id="4ed09-273">In addition, Model Builder outputs the code that generated the model, so that you can understand the steps used to generate the model.</span></span> <span data-ttu-id="4ed09-274">Код обучения модели можно использовать для повторного обучения на основе новых данных.</span><span class="sxs-lookup"><span data-stu-id="4ed09-274">You can also use the model training code to retrain your model with new data.</span></span>

## <a name="whats-next"></a><span data-ttu-id="4ed09-275">Что дальше?</span><span class="sxs-lookup"><span data-stu-id="4ed09-275">What's next?</span></span>

<span data-ttu-id="4ed09-276">[Установите](how-to-guides/install-model-builder.md) расширение "Построитель моделей" для Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4ed09-276">[Install](how-to-guides/install-model-builder.md) the Model Builder Visual Studio extension</span></span>

<span data-ttu-id="4ed09-277">Попробуйте [сценарий прогнозирования цен или любой сценарий регрессии](tutorials/predict-prices-with-model-builder.md)</span><span class="sxs-lookup"><span data-stu-id="4ed09-277">Try [price prediction or any regression scenario](tutorials/predict-prices-with-model-builder.md)</span></span>
