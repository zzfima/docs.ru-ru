---
title: Что такое ML.NET и принципы работы этой системы
description: ML.NET позволяет добавлять в приложения .NET возможности машинного обучения в автономном и подключенном режимах. Используя эту функцию, вы можете получать автоматические прогнозы на основе данных, доступных вашему приложению, без необходимости подключаться к сети для работы с ML.NET. В этой статье рассматриваются основы машинного обучения в ML.NET.
ms.date: 07/17/2019
ms.topic: overview
ms.custom: mvc
ms.author: nakersha
author: natke
ms.openlocfilehash: 23e71e86b75854042068b6a68f90cf995749ee58
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331582"
---
# <a name="what-is-mlnet-and-how-does-it-work"></a><span data-ttu-id="0ce72-105">Что такое ML.NET и принципы работы этой системы</span><span class="sxs-lookup"><span data-stu-id="0ce72-105">What is ML.NET and how does it work?</span></span>

<span data-ttu-id="0ce72-106">ML.NET позволяет добавлять в приложения .NET возможности машинного обучения в автономном и подключенном режимах.</span><span class="sxs-lookup"><span data-stu-id="0ce72-106">ML.NET gives you the ability to add machine learning to .NET applications, in either online or offline scenarios.</span></span> <span data-ttu-id="0ce72-107">Используя эту функцию, вы можете получать автоматические прогнозы на основе данных, доступных вашему приложению, без необходимости подключаться к сети.</span><span class="sxs-lookup"><span data-stu-id="0ce72-107">With this capability, you can make automatic predictions using the data available to your application without having to be connected to a network.</span></span> <span data-ttu-id="0ce72-108">В этой статье рассматриваются основы машинного обучения в ML.NET.</span><span class="sxs-lookup"><span data-stu-id="0ce72-108">This article explains the basics of machine learning in ML.NET.</span></span> 

<span data-ttu-id="0ce72-109">С помощью ML.NET можно получать прогнозы следующих типов:</span><span class="sxs-lookup"><span data-stu-id="0ce72-109">Examples of the type of predictions that you can make with ML.NET include:</span></span>

|||
|-|-|
|<span data-ttu-id="0ce72-110">Классификация/категоризация</span><span class="sxs-lookup"><span data-stu-id="0ce72-110">Classification/Categorization</span></span>|<span data-ttu-id="0ce72-111">Автоматическое разделение отзывов клиентов на положительные и отрицательные</span><span class="sxs-lookup"><span data-stu-id="0ce72-111">Automatically divide customer feedback into positive and negative categories</span></span>|
|<span data-ttu-id="0ce72-112">Регрессия/прогноз непрерывных значений</span><span class="sxs-lookup"><span data-stu-id="0ce72-112">Regression/Predict continuous values</span></span>|<span data-ttu-id="0ce72-113">Прогноз цены на дома, исходя из их размера и местонахождения</span><span class="sxs-lookup"><span data-stu-id="0ce72-113">Predict the price of houses based on size and location</span></span>|
|<span data-ttu-id="0ce72-114">Обнаружение аномалий</span><span class="sxs-lookup"><span data-stu-id="0ce72-114">Anomaly Detection</span></span>|<span data-ttu-id="0ce72-115">Обнаружение мошеннических банковских операций</span><span class="sxs-lookup"><span data-stu-id="0ce72-115">Detect fraudulent banking transactions</span></span> |
|<span data-ttu-id="0ce72-116">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="0ce72-116">Recommendations</span></span>|<span data-ttu-id="0ce72-117">Предложение продуктов, которые онлайн-покупатели могут захотеть купить, исходя из их предыдущих покупок</span><span class="sxs-lookup"><span data-stu-id="0ce72-117">Suggest products that online shoppers may want to buy, based on their previous purchases</span></span>|

## <a name="hello-mlnet-world"></a><span data-ttu-id="0ce72-118">Hello ML.NET World</span><span class="sxs-lookup"><span data-stu-id="0ce72-118">Hello ML.NET World</span></span>

<span data-ttu-id="0ce72-119">В следующем фрагменте кода показано простейшее приложение ML.NET.</span><span class="sxs-lookup"><span data-stu-id="0ce72-119">The code in the following snippet demonstrates the simplest ML.NET application.</span></span> <span data-ttu-id="0ce72-120">Код в этом примере создает модель линейной регрессии для прогнозирования цен на дома, исходя из их размера и стоимости.</span><span class="sxs-lookup"><span data-stu-id="0ce72-120">This example constructs a linear regression model to predict house prices using house size and price data.</span></span> <span data-ttu-id="0ce72-121">В реальных приложения данные и модель будут намного более сложными.</span><span class="sxs-lookup"><span data-stu-id="0ce72-121">In your real-life applications, your data and model will be much more complex.</span></span>

 ```csharp
    using System;
    using Microsoft.ML;
    using Microsoft.ML.Data;
    
    class Program
    {
        public class HouseData
        {
            public float Size { get; set; }
            public float Price { get; set; }
        }
    
        public class Prediction
        {
            [ColumnName("Score")]
            public float Price { get; set; }
        }
    
        static void Main(string[] args)
        {
            MLContext mlContext = new MLContext();
    
            // 1. Import or create training data
            HouseData[] houseData = {
                new HouseData() { Size = 1.1F, Price = 1.2F },
                new HouseData() { Size = 1.9F, Price = 2.3F },
                new HouseData() { Size = 2.8F, Price = 3.0F },
                new HouseData() { Size = 3.4F, Price = 3.7F } };
            IDataView trainingData = mlContext.Data.LoadFromEnumerable(houseData);

            // 2. Specify data preparation and model training pipeline
            var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
                .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));
    
            // 3. Train model
            var model = pipeline.Fit(trainingData);
    
            // 4. Make a prediction
            var size = new HouseData() { Size = 2.5F };
            var price = mlContext.Model.CreatePredictionEngine<HouseData, Prediction>(model).Predict(size);

            Console.WriteLine($"Predicted price for size: {size.Size*1000} sq ft= {price.Price*100:C}k");

            // Predicted price for size: 2500 sq ft= $261.98k
        }
    } 
```

## <a name="code-workflow"></a><span data-ttu-id="0ce72-122">Порядок работы с кодом</span><span class="sxs-lookup"><span data-stu-id="0ce72-122">Code workflow</span></span>

<span data-ttu-id="0ce72-123">На представленной ниже схеме показана структура кода приложения, а также итеративный процесс разработки модели.</span><span class="sxs-lookup"><span data-stu-id="0ce72-123">The following diagram represents the application code structure, as well as the iterative process of model development:</span></span>
- <span data-ttu-id="0ce72-124">Сбор и загрузка обучающих данных в объект **IDataView**</span><span class="sxs-lookup"><span data-stu-id="0ce72-124">Collect and load training data into an **IDataView** object</span></span>
- <span data-ttu-id="0ce72-125">Указание конвейера операций для извлечения функций и применение алгоритма машинного обучения</span><span class="sxs-lookup"><span data-stu-id="0ce72-125">Specify a pipeline of operations to extract features and apply a machine learning algorithm</span></span>
- <span data-ttu-id="0ce72-126">Обучение модели путем вызова функции **Fit()** для конвейера</span><span class="sxs-lookup"><span data-stu-id="0ce72-126">Train a model by calling **Fit()** on the pipeline</span></span>
- <span data-ttu-id="0ce72-127">Оценка модели и итерации для ее улучшения</span><span class="sxs-lookup"><span data-stu-id="0ce72-127">Evaluate the model and iterate to improve</span></span>
- <span data-ttu-id="0ce72-128">Сохранение модели в двоичном формате для использования в приложении</span><span class="sxs-lookup"><span data-stu-id="0ce72-128">Save the model into binary format, for use in an application</span></span>
- <span data-ttu-id="0ce72-129">Загрузка модели обратно в объект **ITransformer**</span><span class="sxs-lookup"><span data-stu-id="0ce72-129">Load the model back into an **ITransformer** object</span></span>
- <span data-ttu-id="0ce72-130">Прогнозирование с помощью функции **CreatePredictionEngine.Predict()**</span><span class="sxs-lookup"><span data-stu-id="0ce72-130">Make predictions by calling **CreatePredictionEngine.Predict()**</span></span>

![Процесс разработки приложения ML.NET, включая компоненты для создания данных, разработку конвейера, а также обучение, оценку и использование модели](./media/mldotnet-annotated-workflow.png) 

<span data-ttu-id="0ce72-132">Рассмотрим эти этапы более подробно.</span><span class="sxs-lookup"><span data-stu-id="0ce72-132">Let's dig a little deeper into those concepts.</span></span>

## <a name="machine-learning-model"></a><span data-ttu-id="0ce72-133">Модель машинного обучения</span><span class="sxs-lookup"><span data-stu-id="0ce72-133">Machine learning model</span></span>

<span data-ttu-id="0ce72-134">Модель ML.NET — это объект, содержащий преобразования для получения прогнозов на основе предоставленных вами данных.</span><span class="sxs-lookup"><span data-stu-id="0ce72-134">An ML.NET model is an object that contains transformations to perform on your input data to arrive at the predicted output.</span></span>

### <a name="basic"></a><span data-ttu-id="0ce72-135">Basic</span><span class="sxs-lookup"><span data-stu-id="0ce72-135">Basic</span></span>

<span data-ttu-id="0ce72-136">Самая базовая модель — это двухмерная линейная регрессия, где одно непрерывное количество пропорционально другому, как в приведенном выше примере с ценами на дома.</span><span class="sxs-lookup"><span data-stu-id="0ce72-136">The most basic model is two-dimensional linear regression, where one continuous quantity is proportional to another, as in the house price example above.</span></span> 

![Модель линейной регрессии с параметрами смещения и веса](./media/linear-regression-model.svg)

<span data-ttu-id="0ce72-138">Модель проста: $Цена = b + Размер \* w$.</span><span class="sxs-lookup"><span data-stu-id="0ce72-138">The model is simply: $Price = b + Size \* w$.</span></span> <span data-ttu-id="0ce72-139">Параметры $b$ и $w$ рассчитываются с помощью линии, проведенной через набор пар данных (размер, цена).</span><span class="sxs-lookup"><span data-stu-id="0ce72-139">The parameters $b$ and $w$ are estimated by fitting a line on a set of (size, price) pairs.</span></span> <span data-ttu-id="0ce72-140">Данные, используемые для поиска параметров модели, называется **обучающими**.</span><span class="sxs-lookup"><span data-stu-id="0ce72-140">The data used to find the parameters of the model is called **training data**.</span></span> <span data-ttu-id="0ce72-141">Входные данные модели машинного обучения называются **компонентами**.</span><span class="sxs-lookup"><span data-stu-id="0ce72-141">The inputs of a machine learning model are called **features**.</span></span> <span data-ttu-id="0ce72-142">В этом примере $Размер$ — единственный компонент.</span><span class="sxs-lookup"><span data-stu-id="0ce72-142">In this example, $Size$ is the only feature.</span></span> <span data-ttu-id="0ce72-143">Эталонные значения, которые используются для обучения модели машинного обучения, называются **метками**.</span><span class="sxs-lookup"><span data-stu-id="0ce72-143">The ground-truth values used to train a machine learning model are called **labels**.</span></span> <span data-ttu-id="0ce72-144">В этом примере метками служат значения параметра $Цена$ в обучающем наборе данных.</span><span class="sxs-lookup"><span data-stu-id="0ce72-144">Here, the $Price$ values in the training data set are the labels.</span></span>

### <a name="more-complex"></a><span data-ttu-id="0ce72-145">Более сложная модель</span><span class="sxs-lookup"><span data-stu-id="0ce72-145">More complex</span></span>

<span data-ttu-id="0ce72-146">Более сложная модель классифицирует финансовые транзакции по категориям, используя текстовые описания транзакций.</span><span class="sxs-lookup"><span data-stu-id="0ce72-146">A more complex model classifies financial transactions into categories using the transaction text description.</span></span>

<span data-ttu-id="0ce72-147">Описание транзакции разбивается на набор компонентов — для этого удаляются избыточные слова и символы и подсчитывается количество слов и комбинаций символов.</span><span class="sxs-lookup"><span data-stu-id="0ce72-147">Each transaction description is broken down into a set of features by removing redundant words and characters, and counting word and character combinations.</span></span> <span data-ttu-id="0ce72-148">Набор компонентов используется для обучения линейной модели на основе набора категорий в обучающих данных.</span><span class="sxs-lookup"><span data-stu-id="0ce72-148">The feature set is used to train a linear model based on the set of categories in the training data.</span></span> <span data-ttu-id="0ce72-149">Чем больше новые описания похожи на те, что уже присутствуют в наборе обучающих данных, тем выше вероятность того, что соответствующим транзакциям будет присвоена та же категория.</span><span class="sxs-lookup"><span data-stu-id="0ce72-149">The more similar a new description is to the ones in the training set, the more likely it will be assigned to the same category.</span></span> 

![Модель классификации текста](./media/text-classification-model.svg)

<span data-ttu-id="0ce72-151">И модель прогнозирования цен на дома, и модель классификации текста являются **линейными**.</span><span class="sxs-lookup"><span data-stu-id="0ce72-151">Both the house price model and the text classification model are **linear** models.</span></span> <span data-ttu-id="0ce72-152">В зависимости от характера ваших данных и решаемой задачи можно также использовать модели **дерева принятия решений**, **обобщенные аддитивные** модели и т. д.</span><span class="sxs-lookup"><span data-stu-id="0ce72-152">Depending on the nature of your data and the problem you are solving, you can also use **decision tree** models, **generalized additive** models, and others.</span></span> <span data-ttu-id="0ce72-153">Дополнительные сведения о моделях см. в статье [Задачи](./resources/tasks.md).</span><span class="sxs-lookup"><span data-stu-id="0ce72-153">You can find out more about the models in [Tasks](./resources/tasks.md).</span></span>

## <a name="data-preparation"></a><span data-ttu-id="0ce72-154">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="0ce72-154">Data preparation</span></span>

<span data-ttu-id="0ce72-155">В большинстве случаев доступные данные не подходят для обучения модели машинного обучения в их исходном виде.</span><span class="sxs-lookup"><span data-stu-id="0ce72-155">In most cases, the data that you have available isn't suitable to be used directly to train a machine learning model.</span></span> <span data-ttu-id="0ce72-156">Необработанные данные необходимо подготовить (подвергнуть предварительной обработке), прежде чем их можно будет использовать для поиска параметров вашей модели.</span><span class="sxs-lookup"><span data-stu-id="0ce72-156">The raw data needs to be prepared, or pre-processed before it can be used to find the parameters of your model.</span></span> <span data-ttu-id="0ce72-157">Возможно, данные придется преобразовать из строковых значений в числовые,</span><span class="sxs-lookup"><span data-stu-id="0ce72-157">Your data may need to be converted from string values to a numerical representation.</span></span> <span data-ttu-id="0ce72-158">освободить от избыточной информации,</span><span class="sxs-lookup"><span data-stu-id="0ce72-158">You might have redundant information in your input data.</span></span> <span data-ttu-id="0ce72-159">уменьшить или увеличить их размер,</span><span class="sxs-lookup"><span data-stu-id="0ce72-159">You may need to reduce or expand the dimensions of your input data.</span></span> <span data-ttu-id="0ce72-160">масштабировать или нормализовать.</span><span class="sxs-lookup"><span data-stu-id="0ce72-160">Your data might need to be normalized or scaled.</span></span>

<span data-ttu-id="0ce72-161">В [учебниках ML.NET](./tutorials/index.md) рассказывается о различных конвейерах обработки данных для текстов, изображений, числовых данных и временных рядов, которые используются для выполнения задач машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="0ce72-161">The [ML.NET tutorials](./tutorials/index.md) teach you about different data processing pipelines for text, image, numerical, and time-series data used for specific machine learning tasks.</span></span>

<span data-ttu-id="0ce72-162">В статье [Подготовка данных](./how-to-guides/prepare-data-ml-net.md) вы найдете более общую информацию о подготовке данных.</span><span class="sxs-lookup"><span data-stu-id="0ce72-162">[How to prepare your data](./how-to-guides/prepare-data-ml-net.md) shows you how to applied data preparation more generally.</span></span>

<span data-ttu-id="0ce72-163">Информацию обо всех [доступных преобразованиях](./resources/transforms.md) вы найдете в разделе ресурсов.</span><span class="sxs-lookup"><span data-stu-id="0ce72-163">You can find an appendix of all of the [available transformations](./resources/transforms.md) in the resources section.</span></span>

## <a name="model-evaluation"></a><span data-ttu-id="0ce72-164">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="0ce72-164">Model evaluation</span></span>

<span data-ttu-id="0ce72-165">Как узнать, насколько точные прогнозы будет давать обученная вами модель?</span><span class="sxs-lookup"><span data-stu-id="0ce72-165">Once you have trained your model, how do you know how well it will make future predictions?</span></span> <span data-ttu-id="0ce72-166">ML.NET позволяет оценить модель по новым тестовым данным.</span><span class="sxs-lookup"><span data-stu-id="0ce72-166">With ML.NET, you can evaluate your model against some new test data.</span></span> 

<span data-ttu-id="0ce72-167">У каждого типа задач машинного обучения имеются метрики, по которым можно оценить точность и аккуратность модели, применив ее к тестовому набору данных.</span><span class="sxs-lookup"><span data-stu-id="0ce72-167">Each type of machine learning task has metrics used to evaluate the accuracy and precision of the model against the test data set.</span></span>

<span data-ttu-id="0ce72-168">В примере с ценами на дома мы использовали задачу **Регрессия**.</span><span class="sxs-lookup"><span data-stu-id="0ce72-168">For our house price example, we used the **Regression** task.</span></span> <span data-ttu-id="0ce72-169">Чтобы оценить модель, добавьте к исходному образцу следующий код:</span><span class="sxs-lookup"><span data-stu-id="0ce72-169">To evaluate the model, add the following code to the original sample.</span></span>

```csharp
        HouseData[] testHouseData =
        {
            new HouseData() { Size = 1.1F, Price = 0.98F },
            new HouseData() { Size = 1.9F, Price = 2.1F },
            new HouseData() { Size = 2.8F, Price = 2.9F },
            new HouseData() { Size = 3.4F, Price = 3.6F }
        };

        var testHouseDataView = mlContext.Data.LoadFromEnumerable(testHouseData);
        var testPriceDataView = model.Transform(testHouseDataView);
                
        var metrics = mlContext.Regression.Evaluate(testPriceDataView, labelColumnName: "Price");

        Console.WriteLine($"R^2: {metrics.RSquared:0.##}");
        Console.WriteLine($"RMS error: {metrics.RootMeanSquaredError:0.##}");

        // R^2: 0.96
        // RMS error: 0.19
```

<span data-ttu-id="0ce72-170">Метрики оценки покажут, что ошибки незначительны, а корреляция между прогнозируемыми результатами и выходными данными теста высока.</span><span class="sxs-lookup"><span data-stu-id="0ce72-170">The evaluation metrics tell you that the error is low-ish, and that correlation between the predicted output and the test output is high.</span></span> <span data-ttu-id="0ce72-171">Это было просто.</span><span class="sxs-lookup"><span data-stu-id="0ce72-171">That was easy!</span></span> <span data-ttu-id="0ce72-172">На практике для получения хороших метрик модели требуется гораздо более тщательная настройка.</span><span class="sxs-lookup"><span data-stu-id="0ce72-172">In real examples, it takes more tuning to achieve good model metrics.</span></span>

## <a name="mlnet-architecture"></a><span data-ttu-id="0ce72-173">Архитектура ML.NET</span><span class="sxs-lookup"><span data-stu-id="0ce72-173">ML.NET architecture</span></span>

<span data-ttu-id="0ce72-174">В этом разделе мы рассмотрим архитектурные шаблоны ML.NET.</span><span class="sxs-lookup"><span data-stu-id="0ce72-174">In this section, we go through the architectural patterns of ML.NET.</span></span> <span data-ttu-id="0ce72-175">Если вы опытный разработчик .NET, какие-то из этих шаблонов будут вам знакомы больше, а какие-то меньше.</span><span class="sxs-lookup"><span data-stu-id="0ce72-175">If you are an experienced .NET developer, some of these patterns will be familiar to you, and some will be less familiar.</span></span> <span data-ttu-id="0ce72-176">Держитесь крепче, начинаем погружение!</span><span class="sxs-lookup"><span data-stu-id="0ce72-176">Hold tight, while we dive in!</span></span>

<span data-ttu-id="0ce72-177">Приложение ML.NET начинается с объекта <xref:Microsoft.ML.MLContext>.</span><span class="sxs-lookup"><span data-stu-id="0ce72-177">An ML.NET application starts with an <xref:Microsoft.ML.MLContext> object.</span></span> <span data-ttu-id="0ce72-178">Этот одноэлементный объект содержит **каталоги**.</span><span class="sxs-lookup"><span data-stu-id="0ce72-178">This singleton object contains **catalogs**.</span></span> <span data-ttu-id="0ce72-179">Каталог — это фабрика загрузки и сохранения данных, преобразований, инструкторов и компонентов операций модели.</span><span class="sxs-lookup"><span data-stu-id="0ce72-179">A catalog is a factory for data loading and saving, transforms, trainers, and model operation components.</span></span> <span data-ttu-id="0ce72-180">Каждый объект каталога имеет методы для создания различных типов компонентов:</span><span class="sxs-lookup"><span data-stu-id="0ce72-180">Each catalog object has methods to create the different types of components:</span></span>

|||||
|-|-|-|-|
|<span data-ttu-id="0ce72-181">Загрузка и сохранение данных</span><span class="sxs-lookup"><span data-stu-id="0ce72-181">Data loading and saving</span></span>||<xref:Microsoft.ML.DataOperationsCatalog>||
|<span data-ttu-id="0ce72-182">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="0ce72-182">Data preparation</span></span>||<xref:Microsoft.ML.TransformsCatalog>||
|<span data-ttu-id="0ce72-183">Алгоритмы обучения</span><span class="sxs-lookup"><span data-stu-id="0ce72-183">Training algorithms</span></span>|<span data-ttu-id="0ce72-184">Двоичная классификация</span><span class="sxs-lookup"><span data-stu-id="0ce72-184">Binary classification</span></span>|<xref:Microsoft.ML.BinaryClassificationCatalog>||
||<span data-ttu-id="0ce72-185">Многоклассовая классификация</span><span class="sxs-lookup"><span data-stu-id="0ce72-185">Multiclass classification</span></span>|<xref:Microsoft.ML.MulticlassClassificationCatalog>||
||<span data-ttu-id="0ce72-186">Обнаружение аномалий</span><span class="sxs-lookup"><span data-stu-id="0ce72-186">Anomaly detection</span></span>|<xref:Microsoft.ML.AnomalyDetectionCatalog>||
||<span data-ttu-id="0ce72-187">Кластеризация</span><span class="sxs-lookup"><span data-stu-id="0ce72-187">Clustering</span></span>|<xref:Microsoft.ML.ClusteringCatalog>||
||<span data-ttu-id="0ce72-188">Прогнозирование</span><span class="sxs-lookup"><span data-stu-id="0ce72-188">Forecasting</span></span>|<xref:Microsoft.ML.ForecastingCatalog>||
||<span data-ttu-id="0ce72-189">Ранжирование</span><span class="sxs-lookup"><span data-stu-id="0ce72-189">Ranking</span></span>|<xref:Microsoft.ML.RankingCatalog>||
||<span data-ttu-id="0ce72-190">Регрессия</span><span class="sxs-lookup"><span data-stu-id="0ce72-190">Regression</span></span>|<xref:Microsoft.ML.RegressionCatalog>||
||<span data-ttu-id="0ce72-191">Рекомендация</span><span class="sxs-lookup"><span data-stu-id="0ce72-191">Recommendation</span></span>|<xref:Microsoft.ML.RecommendationCatalog>|<span data-ttu-id="0ce72-192">Добавление пакета NuGet `Microsoft.ML.Recommender`</span><span class="sxs-lookup"><span data-stu-id="0ce72-192">add the `Microsoft.ML.Recommender` NuGet package</span></span>|
||<span data-ttu-id="0ce72-193">TimeSeries</span><span class="sxs-lookup"><span data-stu-id="0ce72-193">TimeSeries</span></span>|<xref:Microsoft.ML.TimeSeriesCatalog>|<span data-ttu-id="0ce72-194">Добавление пакета NuGet `Microsoft.ML.TimeSeries`</span><span class="sxs-lookup"><span data-stu-id="0ce72-194">add the `Microsoft.ML.TimeSeries` NuGet package</span></span>|
|<span data-ttu-id="0ce72-195">Использование модели</span><span class="sxs-lookup"><span data-stu-id="0ce72-195">Model usage</span></span> ||<xref:Microsoft.ML.ModelOperationsCatalog>||

<span data-ttu-id="0ce72-196">Через каждую из указанных выше категорий можно перейти к соответствующим методам создания.</span><span class="sxs-lookup"><span data-stu-id="0ce72-196">You can navigate to the creation methods in each of the above categories.</span></span> <span data-ttu-id="0ce72-197">В Visual Studio каталоги отображаются с помощью IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="0ce72-197">Using Visual Studio, the catalogs show up via IntelliSense.</span></span>

   ![IntelliSense для инструкторов регрессии](./media/catalog-intellisense.png)

### <a name="build-the-pipeline"></a><span data-ttu-id="0ce72-199">Сборка конвейера</span><span class="sxs-lookup"><span data-stu-id="0ce72-199">Build the pipeline</span></span>

<span data-ttu-id="0ce72-200">В каждом каталоге есть набор методов расширения.</span><span class="sxs-lookup"><span data-stu-id="0ce72-200">Inside each catalog is a set of extension methods.</span></span> <span data-ttu-id="0ce72-201">Посмотрим, как методы расширения используются при создании конвейера обучения.</span><span class="sxs-lookup"><span data-stu-id="0ce72-201">Let's look at how extension methods are used to create a training pipeline.</span></span>

```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
        .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));
```

<span data-ttu-id="0ce72-202">В представленном ниже фрагменте кода `Concatenate` и `Sdca` — это методы из каталога.</span><span class="sxs-lookup"><span data-stu-id="0ce72-202">In the snippet, `Concatenate` and `Sdca` are both methods in the catalog.</span></span> <span data-ttu-id="0ce72-203">Каждый из них создает объект [IEstimator](xref:Microsoft.ML.IEstimator%601), который добавляется в конвейер.</span><span class="sxs-lookup"><span data-stu-id="0ce72-203">They each create an [IEstimator](xref:Microsoft.ML.IEstimator%601) object that is appended to the pipeline.</span></span>

<span data-ttu-id="0ce72-204">Этот этап включает только создание объектов.</span><span class="sxs-lookup"><span data-stu-id="0ce72-204">At this point, the objects are created only.</span></span> <span data-ttu-id="0ce72-205">Выполнение не происходит.</span><span class="sxs-lookup"><span data-stu-id="0ce72-205">No execution has happened.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="0ce72-206">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="0ce72-206">Train the model</span></span>

<span data-ttu-id="0ce72-207">После создания объектов в конвейере данные можно использовать для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="0ce72-207">Once the objects in the pipeline have been created, data can be used to train the model.</span></span>

```csharp
    var model = pipeline.Fit(trainingData);
```

<span data-ttu-id="0ce72-208">Вызов функции `Fit()` задействует входные обучающие данные для оценки параметров модели.</span><span class="sxs-lookup"><span data-stu-id="0ce72-208">Calling `Fit()` uses the input training data to estimate the parameters of the model.</span></span> <span data-ttu-id="0ce72-209">Это называется обучение модели.</span><span class="sxs-lookup"><span data-stu-id="0ce72-209">This is known as training the model.</span></span> <span data-ttu-id="0ce72-210">Напомним, что представленная выше модель линейной регрессии включала два параметра модели: **смещение** и **вес**.</span><span class="sxs-lookup"><span data-stu-id="0ce72-210">Remember, the linear regression model above had two model parameters: **bias** and **weight**.</span></span> <span data-ttu-id="0ce72-211">После вызова функции `Fit()` значения этих параметров становятся известны.</span><span class="sxs-lookup"><span data-stu-id="0ce72-211">After the `Fit()` call, the values of the parameters are known.</span></span> <span data-ttu-id="0ce72-212">В большинстве моделей параметров будет намного больше.</span><span class="sxs-lookup"><span data-stu-id="0ce72-212">Most models will have many more parameters than this.</span></span>

<span data-ttu-id="0ce72-213">Дополнительные сведения об обучении моделей см. в статье [Обучение модели](./how-to-guides/train-machine-learning-model-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="0ce72-213">You can learn more about model training in [How to train your model](./how-to-guides/train-machine-learning-model-ml-net.md)</span></span>

<span data-ttu-id="0ce72-214">Полученный объект модели реализует интерфейс <xref:Microsoft.ML.ITransformer>.</span><span class="sxs-lookup"><span data-stu-id="0ce72-214">The resulting model object implements the <xref:Microsoft.ML.ITransformer> interface.</span></span> <span data-ttu-id="0ce72-215">Это значит, что модель преобразует входные данные в прогнозы.</span><span class="sxs-lookup"><span data-stu-id="0ce72-215">That is, the model transforms input data into predictions.</span></span>

```csharp
   IDataView predictions = model.Transform(inputData);
```

### <a name="use-the-model"></a><span data-ttu-id="0ce72-216">Использование модели</span><span class="sxs-lookup"><span data-stu-id="0ce72-216">Use the model</span></span>

<span data-ttu-id="0ce72-217">Входные данные можно преобразовывать в прогнозы все сразу или по очереди.</span><span class="sxs-lookup"><span data-stu-id="0ce72-217">You can transform input data into predictions in bulk, or one input at a time.</span></span> <span data-ttu-id="0ce72-218">В примере с ценами на дома мы использовали оба варианта: все сразу для оценки модели и поочередно для создания нового прогноза.</span><span class="sxs-lookup"><span data-stu-id="0ce72-218">In the house price example, we did both: in bulk for the purpose of evaluating the model, and one at a time to make a new prediction.</span></span> <span data-ttu-id="0ce72-219">Рассмотрим получение одиночных прогнозов.</span><span class="sxs-lookup"><span data-stu-id="0ce72-219">Let's look at making single predictions.</span></span>

```csharp
    var size = new HouseData() { Size = 2.5F };
    var predEngine = mlContext.CreatePredictionEngine<HouseData, Prediction>(model);
    var price = predEngine.Predict(size);
```
 
<span data-ttu-id="0ce72-220">Метод `CreatePredictionEngine()` принимает входной и выходной класс данных.</span><span class="sxs-lookup"><span data-stu-id="0ce72-220">The `CreatePredictionEngine()` method takes an input class and an output class.</span></span> <span data-ttu-id="0ce72-221">Имена полей и/или атрибуты кода определяют имена столбцов данных, которые используются при обучении модели и прогнозировании.</span><span class="sxs-lookup"><span data-stu-id="0ce72-221">The field names and/or code attributes determine the names of the data columns used during model training and prediction.</span></span> <span data-ttu-id="0ce72-222">Прочтите, [как создать одиночный прогноз](./how-to-guides/single-predict-model-ml-net.md), в разделе инструкций.</span><span class="sxs-lookup"><span data-stu-id="0ce72-222">You can read about  [How to make a single prediction](./how-to-guides/single-predict-model-ml-net.md) in the How-to section.</span></span>

### <a name="data-models-and-schema"></a><span data-ttu-id="0ce72-223">Модели и схема данных</span><span class="sxs-lookup"><span data-stu-id="0ce72-223">Data models and schema</span></span>

<span data-ttu-id="0ce72-224">В основе конвейера машинного обучения ML.NET лежат объекты [DataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="0ce72-224">At the core of an ML.NET machine learning pipeline are [DataView](xref:Microsoft.ML.IDataView) objects.</span></span>

<span data-ttu-id="0ce72-225">Каждое преобразование в конвейере имеет входную схему (имена, типы и размеры данных, которые должны присутствовать во входных данных) и схему вывода (имена, типы и размеры данных, которые создаются после преобразования).</span><span class="sxs-lookup"><span data-stu-id="0ce72-225">Each transformation in the pipeline has an input schema (data names, types, and sizes that the transform expects to see on its input); and an output schema (data names, types, and sizes that the transform produces after the transformation).</span></span> 

<span data-ttu-id="0ce72-226">Если схема вывода из одного преобразования в конвейере не соответствует входной схеме, ML.NET выдает исключение.</span><span class="sxs-lookup"><span data-stu-id="0ce72-226">If the output schema from one transform in the pipeline doesn't match the input schema of the next transform, ML.NET will throw an exception.</span></span>

<span data-ttu-id="0ce72-227">Объект представления данных содержит столбцы и строки.</span><span class="sxs-lookup"><span data-stu-id="0ce72-227">A data view object has columns and rows.</span></span> <span data-ttu-id="0ce72-228">Каждый столбец содержит имя, тип и длину.</span><span class="sxs-lookup"><span data-stu-id="0ce72-228">Each column has a name and a type and a length.</span></span> <span data-ttu-id="0ce72-229">Например, столбцы входных данных в примере с ценами на дома — это **размер** и **цена**.</span><span class="sxs-lookup"><span data-stu-id="0ce72-229">For example: the input columns in the house price example are **Size** and **Price**.</span></span> <span data-ttu-id="0ce72-230">Оба имеют тип и являются скорее скалярными, а не векторными величинами.</span><span class="sxs-lookup"><span data-stu-id="0ce72-230">They are both type  and they are scalar quantities rather than vector ones.</span></span>

   ![Пример представления данных ML.NET с данными прогнозов по ценам на дома](./media/ml-net-dataview.png)

<span data-ttu-id="0ce72-232">Все алгоритмы ML.NET ищут векторный столбец входных данных.</span><span class="sxs-lookup"><span data-stu-id="0ce72-232">All ML.NET algorithms look for an input column that is a vector.</span></span> <span data-ttu-id="0ce72-233">По умолчанию этот столбец вектора называется **Компоненты**.</span><span class="sxs-lookup"><span data-stu-id="0ce72-233">By default this vector column is called **Features**.</span></span> <span data-ttu-id="0ce72-234">Именно поэтому в примере с ценами на дома мы включили столбец **Размер** в новый столбец **Компоненты**.</span><span class="sxs-lookup"><span data-stu-id="0ce72-234">This is why we concatenated the **Size** column into a new column called **Features** in our house price example.</span></span>

 ```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
 ```

<span data-ttu-id="0ce72-235">Кроме того, после выполнения прогноза все алгоритмы создают новые столбцы.</span><span class="sxs-lookup"><span data-stu-id="0ce72-235">All algorithms also create new columns after they have performed a prediction.</span></span> <span data-ttu-id="0ce72-236">Фиксированные имена этих новых столбцов зависят от типа алгоритма машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="0ce72-236">The fixed names of these new columns depend on the type of machine learning algorithm.</span></span> <span data-ttu-id="0ce72-237">В задаче регрессии один из новых столбцов называется **Оценка**.</span><span class="sxs-lookup"><span data-stu-id="0ce72-237">For the regression task, one of the new columns is called **Score**.</span></span> <span data-ttu-id="0ce72-238">Вот почему мы назвали точно так же наши данные цен.</span><span class="sxs-lookup"><span data-stu-id="0ce72-238">This is why we attributed our price data with this name.</span></span>

```csharp
    public class Prediction
    {
        [ColumnName("Score")]
        public float Price { get; set; }
    }
```    

<span data-ttu-id="0ce72-239">Дополнительные сведения о выходных столбцах различных задач машинного обучения см в руководстве [Задачи машинного обучения](resources/tasks.md).</span><span class="sxs-lookup"><span data-stu-id="0ce72-239">You can find out more about output columns of different machine learning tasks in the [Machine Learning Tasks](resources/tasks.md) guide.</span></span>

<span data-ttu-id="0ce72-240">Важным свойством объектов DataView является то, что они вычисляются **неактивно**.</span><span class="sxs-lookup"><span data-stu-id="0ce72-240">An important property of DataView objects is that they are evaluated **lazily**.</span></span> <span data-ttu-id="0ce72-241">Представления данных загружаются и используются только во время обучения и оценки модели и при прогнозировании данных.</span><span class="sxs-lookup"><span data-stu-id="0ce72-241">Data views are only loaded and operated on during model training and evaluation, and data prediction.</span></span> <span data-ttu-id="0ce72-242">В процессе написания и тестирования приложения ML.NET можно использовать отладчик Visual Studio, чтобы посмотреть на любой объект представления данных, вызвав метод [предварительного просмотра](xref:Microsoft.ML.DebuggerExtensions.Preview*).</span><span class="sxs-lookup"><span data-stu-id="0ce72-242">While you are writing and testing your ML.NET application, you can use the Visual Studio debugger to take a peek at any data view object by calling the [Preview](xref:Microsoft.ML.DebuggerExtensions.Preview*) method.</span></span>

```csharp
    var debug = testPriceDataView.Preview();
```

<span data-ttu-id="0ce72-243">Вы можете проверить переменную `debug` в отладчике и изучить ее содержимое.</span><span class="sxs-lookup"><span data-stu-id="0ce72-243">You can watch the `debug` variable in the debugger and examine its contents.</span></span> <span data-ttu-id="0ce72-244">Не используйте метод предварительного просмотра в рабочем коде, поскольку он сильно снижает производительность.</span><span class="sxs-lookup"><span data-stu-id="0ce72-244">Do not use the Preview method in production code, as it significantly degrades performance.</span></span>

### <a name="model-deployment"></a><span data-ttu-id="0ce72-245">Развертывание модели</span><span class="sxs-lookup"><span data-stu-id="0ce72-245">Model Deployment</span></span>

<span data-ttu-id="0ce72-246">В реальных приложениях обучение и оценка модели будут отделены от прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="0ce72-246">In real-life applications, your model training and evaluation code will be separate from your prediction.</span></span> <span data-ttu-id="0ce72-247">На практике эти действия часто выполняют разные группы разработчиков.</span><span class="sxs-lookup"><span data-stu-id="0ce72-247">In fact, these two activities are often performed by separate teams.</span></span> <span data-ttu-id="0ce72-248">Ваша команда разработчиков модели может сохранить модель для использования в приложении прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="0ce72-248">Your model development team can save the model for use in the prediction application.</span></span>

```csharp   
   mlContext.Model.Save(model, trainingData.Schema,"model.zip");
```

## <a name="where-to-now"></a><span data-ttu-id="0ce72-249">Что дальше</span><span class="sxs-lookup"><span data-stu-id="0ce72-249">Where to now?</span></span>

<span data-ttu-id="0ce72-250">Узнайте, как создавать приложения, используя другие задачи машинного обучения и более реалистичные наборы данных, из [руководств](./tutorials/index.md).</span><span class="sxs-lookup"><span data-stu-id="0ce72-250">You can learn how to build applications using different machine learning tasks with more realistic data sets in the [tutorials](./tutorials/index.md).</span></span>

<span data-ttu-id="0ce72-251">Или изучите подробнее отдельные темы в [практических руководствах](./how-to-guides/index.md).</span><span class="sxs-lookup"><span data-stu-id="0ce72-251">Or you can learn about specific topics in more depth in the [How To Guides](./how-to-guides/index.md).</span></span>

<span data-ttu-id="0ce72-252">А если вы полны энтузиазма, то [справочная документация по API](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet) всегда к вашим услугам!</span><span class="sxs-lookup"><span data-stu-id="0ce72-252">And if you're super keen, you can dive straight into the [API Reference documentation](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet)!</span></span>
