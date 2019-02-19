---
title: Основные понятия для обучения модели в ML.NET
description: В этой статье разъясняются основные понятия в сценариях *обучения моделей* в ML.NET. Не все понятия относятся к самому простому сценарию *прогнозирования с помощью существующей модели*.
ms.date: 02/13/2019
ms.topic: overview
ms.custom: mvc
ms.openlocfilehash: c47d5832527dca1416abfc55756dca48f1daf493
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303664"
---
# <a name="basic-concepts-for-model-training-in-mlnet"></a><span data-ttu-id="27590-104">Основные понятия для обучения модели в ML.NET</span><span class="sxs-lookup"><span data-stu-id="27590-104">Basic concepts for model training in ML.NET</span></span>

<span data-ttu-id="27590-105">В этой статье разъясняются основные понятия в сценариях *обучения моделей* в ML.NET.</span><span class="sxs-lookup"><span data-stu-id="27590-105">This article explains the basic concepts covering *model training* scenarios in ML.NET.</span></span> <span data-ttu-id="27590-106">Не все понятия относятся к самому простому сценарию *прогнозирования с помощью существующей модели*.</span><span class="sxs-lookup"><span data-stu-id="27590-106">Not all concepts are relevant to the more simple scenario of *prediction with an existing model*.</span></span>

## <a name="model-training-concepts"></a><span data-ttu-id="27590-107">Понятия, связанные с обучением моделей</span><span class="sxs-lookup"><span data-stu-id="27590-107">Model training concepts</span></span>

<span data-ttu-id="27590-108">В этом документе рассматриваются следующие понятия, связанные с обучением модели в ML.NET:</span><span class="sxs-lookup"><span data-stu-id="27590-108">This document covers the following concepts related to model training in ML.NET:</span></span>

- <span data-ttu-id="27590-109">[*Данные*](#data) представлены в виде интерфейса `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="27590-109">[*Data*](#data) represented as an `IDataView` interface.</span></span>
  - <span data-ttu-id="27590-110">В ML.NET данные аналогичны представлению SQL: Это отложенно-вычисляемый, неизменяемый, поддерживающий курсоры, неоднородный и схематизированный набор данных.</span><span class="sxs-lookup"><span data-stu-id="27590-110">In ML.NET, data is similar to a SQL view: It's a lazily evaluated, immutable, cursorable, heterogenous, schematized dataset.</span></span> 
  - <span data-ttu-id="27590-111">Полезный документ об интерфейсе данных — [Принципы проектирования IDataView](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md).</span><span class="sxs-lookup"><span data-stu-id="27590-111">An excellent document about the data interface is [IDataView Design Principles](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md).</span></span>
- <span data-ttu-id="27590-112">[*Преобразователь*](#transformer) представлен в виде интерфейса `ITransformer`.</span><span class="sxs-lookup"><span data-stu-id="27590-112">[*Transformer*](#transformer) represented as `ITransformer` interface.</span></span>
  - <span data-ttu-id="27590-113">Преобразователь — это компонент, который принимает данные, выполняет с ними определенные действия и возвращает новые преобразованные данные.</span><span class="sxs-lookup"><span data-stu-id="27590-113">A transformer is a component that takes data, does some work on it, and returns new transformed data.</span></span>
  - <span data-ttu-id="27590-114">Например, модель машинного обучения можно считать преобразователем, который принимает функции и возвращает прогнозы.</span><span class="sxs-lookup"><span data-stu-id="27590-114">For example, you can think of a machine learning model as a transformer that takes features and returns predictions.</span></span>
  - <span data-ttu-id="27590-115">Еще один пример: создатель маркеров текста принимает отдельные текстовые столбцы и выводит векторный столбец с отдельными словами, извлеченными из текста.</span><span class="sxs-lookup"><span data-stu-id="27590-115">Another example, text tokenizer takes a single text column and outputs a vector column with individual words extracted out of the texts.</span></span>
- <span data-ttu-id="27590-116">[*Модуль чтения данных*](#data-reader) представлен в виде интерфейса `IDataReader<T>`.</span><span class="sxs-lookup"><span data-stu-id="27590-116">[*Data reader*](#data-reader) represented as an `IDataReader<T>` interface.</span></span>
  - <span data-ttu-id="27590-117">Модуль чтения данных — это компонент ML.NET для создания данных.</span><span class="sxs-lookup"><span data-stu-id="27590-117">The data reader is ML.NET component to create data.</span></span> <span data-ttu-id="27590-118">Он принимает экземпляр `T` и возвращает данные из него.</span><span class="sxs-lookup"><span data-stu-id="27590-118">It takes an instance of `T` and returns data out of it.</span></span> 
  - <span data-ttu-id="27590-119">Например, *TextLoader* — это `IDataReader<IMultiStreamSource>`.</span><span class="sxs-lookup"><span data-stu-id="27590-119">For example, a *TextLoader* is an `IDataReader<IMultiStreamSource>`.</span></span> <span data-ttu-id="27590-120">Он принимает источник и создает данные.</span><span class="sxs-lookup"><span data-stu-id="27590-120">It takes the source and produces data.</span></span> 
- <span data-ttu-id="27590-121">[*Средство оценки*](#estimator) представлено в виде интерфейса `IEstimator<T>`.</span><span class="sxs-lookup"><span data-stu-id="27590-121">[*Estimator*](#estimator) represented as an `IEstimator<T>` interface.</span></span>
  - <span data-ttu-id="27590-122">Это объект, который учится на основе данных.</span><span class="sxs-lookup"><span data-stu-id="27590-122">This is an object that learns from data.</span></span> <span data-ttu-id="27590-123">Результатом обучения является *преобразователь*.</span><span class="sxs-lookup"><span data-stu-id="27590-123">The result of the learning is a *transformer*.</span></span>
  - <span data-ttu-id="27590-124">Можно представить *алгоритм* машинного обучения как средство оценки, которое учится на основе данных и создает *модель* машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="27590-124">You can think of a machine learning *algorithm* as an estimator that learns on data and produces a machine learning *model*.</span></span>
- <span data-ttu-id="27590-125">[*Прогнозирующая функция*](#prediction-function) представлена в виде класса `PredictionEngine<TSrc, TDst>`.</span><span class="sxs-lookup"><span data-stu-id="27590-125">[*Prediction function*](#prediction-function) represented as a `PredictionEngine<TSrc, TDst>` class.</span></span>
  - <span data-ttu-id="27590-126">Прогнозирующую функцию можно рассматривать как машину, которая применяет преобразователь к одной строке, например во время прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="27590-126">The prediction function can be seen as a machine that applies a transformer to one row, such as at prediction time.</span></span>

## <a name="data"></a><span data-ttu-id="27590-127">Данные</span><span class="sxs-lookup"><span data-stu-id="27590-127">Data</span></span>

<span data-ttu-id="27590-128">В ML.NET данные аналогичны представлению SQL: Это отложенно-вычисляемый, поддерживающий курсоры, неоднородный и схематизированный набор данных.</span><span class="sxs-lookup"><span data-stu-id="27590-128">In ML.NET, data is similar to a SQL view: It's a lazily evaluated, cursorable, heterogenous, schematized dataset.</span></span>

- <span data-ttu-id="27590-129">Он имеет *схему* (экземпляр интерфейса `ISchema`), содержащую сведения о столбцах представления данных.</span><span class="sxs-lookup"><span data-stu-id="27590-129">It has *Schema* (an instance of an `ISchema` interface) that contains the information about the data view's columns.</span></span>
  - <span data-ttu-id="27590-130">У каждого столбца есть *имя*, *тип* и произвольный набор *метаданных*, связанных с ним.</span><span class="sxs-lookup"><span data-stu-id="27590-130">Each column has a *Name*, a *Type*, and an arbitrary set of *metadata* associated with it.</span></span>
  - <span data-ttu-id="27590-131">*Метаданные* столбца содержат такие сведения, как имена слота векторного столбца.</span><span class="sxs-lookup"><span data-stu-id="27590-131">The column's *metadata* contains information like slot names of a vector column and the like.</span></span> <span data-ttu-id="27590-132">Сами метаданные представлены в виде других однострочных *данных*, которые являются уникальными для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="27590-132">The metadata itself is represented as another one-row *data* that is unique to each column.</span></span>
  - <span data-ttu-id="27590-133">Представление данных является источником *курсоров*.</span><span class="sxs-lookup"><span data-stu-id="27590-133">The data view is a source of *cursors*.</span></span> <span data-ttu-id="27590-134">Курсоры SQL: Курсор — это объект, который выполняет итерацию по данным по одной строке за раз и представляет доступные данные.</span><span class="sxs-lookup"><span data-stu-id="27590-134">Think SQL cursors: A cursor is an object that iterates through the data, one row at a time, and presents the available data.</span></span>
  - <span data-ttu-id="27590-135">Естественно, данные поддерживают любое количество активных курсоров при необходимости.</span><span class="sxs-lookup"><span data-stu-id="27590-135">Naturally, data can have as many active cursors over it as needed.</span></span> <span data-ttu-id="27590-136">Так как сами данные являются неизменяемыми, курсоры по-настоящему независимы.</span><span class="sxs-lookup"><span data-stu-id="27590-136">Since data itself is immutable, cursors are truly independent.</span></span>
  - <span data-ttu-id="27590-137">Курсоры обычно обращаются только к подмножеству столбцов: Для повышения эффективности ML.NET вычисляет только значения столбцов, которые необходимы курсору.</span><span class="sxs-lookup"><span data-stu-id="27590-137">Cursors typically access only a subset of columns: For efficiency, ML.NET computes only the values of columns that are needed by the cursor.</span></span>

## <a name="transformer"></a><span data-ttu-id="27590-138">Преобразователь</span><span class="sxs-lookup"><span data-stu-id="27590-138">Transformer</span></span>

<span data-ttu-id="27590-139">Преобразователь — это компонент, который принимает данные, выполняет с ними определенные действия и возвращает новые преобразованные данные.</span><span class="sxs-lookup"><span data-stu-id="27590-139">A transformer is a component that takes data, does some work on it, and returns new transformed data.</span></span>

<span data-ttu-id="27590-140">Большинство преобразователей в ML.NET, как правило, работают с *входными столбцами* по одному и создают *выходной столбец*.</span><span class="sxs-lookup"><span data-stu-id="27590-140">Most transformers in ML.NET tend to operate on one *input column* at a time, and produce the *output column*.</span></span> <span data-ttu-id="27590-141">Например, `new HashTransformer("bar", "foo")` принимает значения из столбца "foo", хэширует их и объединяет в столбец "bar".</span><span class="sxs-lookup"><span data-stu-id="27590-141">For example, a `new HashTransformer("bar", "foo")` takes the values from column "foo", hashes them, and puts them into column "bar".</span></span> 

<span data-ttu-id="27590-142">Имена входных и выходных столбцов часто совпадают.</span><span class="sxs-lookup"><span data-stu-id="27590-142">It's also common that the input and output column names are the same.</span></span> <span data-ttu-id="27590-143">В этом случае старый столбец заменяется новым.</span><span class="sxs-lookup"><span data-stu-id="27590-143">In this case, the old column is replaced with the new one.</span></span> <span data-ttu-id="27590-144">Например, `new HashTransformer("foo")` принимает значения из столбца "foo", хэширует их и помещает обратно в столбец "foo".</span><span class="sxs-lookup"><span data-stu-id="27590-144">For example, a `new HashTransformer("foo")` takes the values from column "foo", hashes them, and puts them back into "foo".</span></span> 

<span data-ttu-id="27590-145">Любой преобразователь создает новое представление данных при вызове `Transform`.</span><span class="sxs-lookup"><span data-stu-id="27590-145">Any transformer, produces a new data view when `Transform` is called.</span></span> <span data-ttu-id="27590-146">Помните, что представления данных являются неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="27590-146">Remember, data views are immutable.</span></span>

<span data-ttu-id="27590-147">Еще один важный момент — поскольку данные вычисляются отложенно, *преобразователи также работают отложенно*.</span><span class="sxs-lookup"><span data-stu-id="27590-147">Another important consideration is that, because data is lazily evaluated, *transformers are lazy too*.</span></span> <span data-ttu-id="27590-148">По сути, после вызова</span><span class="sxs-lookup"><span data-stu-id="27590-148">Essentially, after you call</span></span>

```csharp
var newData = transformer.Transform(oldData)
```

<span data-ttu-id="27590-149">никаких вычислений не происходит.</span><span class="sxs-lookup"><span data-stu-id="27590-149">no actual computation happens.</span></span> <span data-ttu-id="27590-150">Только после того, как вы получите курсор из `newData` и начнете использовать значение, `newData` вызывает логику преобразования `transformer` (и даже в этом случае, только если `transformer` необходим для создания запрошенных столбцов).</span><span class="sxs-lookup"><span data-stu-id="27590-150">Only after you get a cursor from `newData` and start consuming the value does `newData` invoke the `transformer` transformation logic (and even then, it only happens if the `transformer` in question is needed to produce the requested columns).</span></span>

### <a name="transformer-chains"></a><span data-ttu-id="27590-151">Цепочки преобразователей</span><span class="sxs-lookup"><span data-stu-id="27590-151">Transformer chains</span></span>

<span data-ttu-id="27590-152">Полезное свойство преобразователя в том, что *вы можете создать последовательное применение преобразователей как еще один преобразователь*:</span><span class="sxs-lookup"><span data-stu-id="27590-152">A useful property of a transformer is that *you can build a sequential application of transformers as yet another transformer*:</span></span>

```csharp
var fullTransformer = transformer1.Append(transformer2).Append(transformer3);
```

<span data-ttu-id="27590-153">Это свойство часто используется в ML.NET: как правило, обученная модель ML.NET представляет собой цепочку преобразователей, которая по сути является *преобразователем*.</span><span class="sxs-lookup"><span data-stu-id="27590-153">This property is commonly used in ML.NET: typically, the trained ML.NET model is a chain of transformers, which is, for all intents and purposes, a *transformer*.</span></span>

## <a name="data-reader"></a><span data-ttu-id="27590-154">Модуль чтения данных</span><span class="sxs-lookup"><span data-stu-id="27590-154">Data reader</span></span>

<span data-ttu-id="27590-155">Модуль чтения данных является компонентом ML.NET для создания данных: он принимает экземпляр `T` и возвращает данные из него.</span><span class="sxs-lookup"><span data-stu-id="27590-155">The data reader is an ML.NET component to 'create' data: it takes an instance of `T` and returns data out of it.</span></span>

<span data-ttu-id="27590-156">Интересно отметить, что вы можете создать модуль чтения данных, присоединив преобразователь к существующему модулю чтения данных.</span><span class="sxs-lookup"><span data-stu-id="27590-156">An interesting property to note is that you can create a data reader by attaching a transformer to an existing data reader.</span></span> <span data-ttu-id="27590-157">Таким образом вы можете использовать модуль чтения с поведением преобразования:</span><span class="sxs-lookup"><span data-stu-id="27590-157">This way you can have a reader with transformation behavior baked in:</span></span>

```csharp
var newReader = reader.Append(transformer1).Append(transformer2)
```

<span data-ttu-id="27590-158">Еще одно сходство с преобразователями заключается в том, что из-за отложенного вычисления данных *модули чтения также являются отложенными*: фактическое чтение не происходит (или почти не происходит) при вызове `reader.Read()` — только при запросе курсора на полученные данные модуль чтения начинает работу.</span><span class="sxs-lookup"><span data-stu-id="27590-158">Another similarity to transformers is that, since data is lazily evaluated, *readers are lazy*: no (or minimal) actual 'reading' happens when you call `reader.Read()`: only when a cursor is requested on the resulting data does the reader begin to work.</span></span>

## <a name="estimator"></a><span data-ttu-id="27590-159">Средство оценки</span><span class="sxs-lookup"><span data-stu-id="27590-159">Estimator</span></span>

<span data-ttu-id="27590-160">*Средство оценки* — это объект, который учится на основе данных.</span><span class="sxs-lookup"><span data-stu-id="27590-160">The *estimator* is an object that learns from data.</span></span> <span data-ttu-id="27590-161">Результатом обучения является *преобразователь*.</span><span class="sxs-lookup"><span data-stu-id="27590-161">The result of the learning is a *transformer*.</span></span>

<span data-ttu-id="27590-162">В ML.NET это свойство используется для создания конвейеров обучения, которые связывают различные средства оценки:</span><span class="sxs-lookup"><span data-stu-id="27590-162">In ML.NET, use this property to create learning pipelines that chain together different estimators:</span></span>

```csharp
MLContext mlContext = new MLContext(seed: 0);

var pipeline = mlContext.Transforms.CopyColumns("Label","FareAmount")
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("VendorId"))
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("RateCode"))
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("PaymentType"))
    .Append(mlContext.Transforms.Concatenate("Features","VendorId","RateCode","PassengerCount","TripTime","TripDistance","PaymentType"))
    .Append(mlContext.Regression.Trainers.FastTree("Label","Features"));

var model = pipeline.Fit(dataView);
```

<span data-ttu-id="27590-163">Важное свойство средств оценки заключается в том, *что они работают активно, а не отложенно*: при каждом вызове `Fit` происходит обучение, а на это может требоваться время.</span><span class="sxs-lookup"><span data-stu-id="27590-163">One important property of estimators is that *estimators are eager, not lazy*: every call to `Fit` is causing learning to happen, which is potentially a time-consuming operation.</span></span>

## <a name="prediction-function"></a><span data-ttu-id="27590-164">Прогнозирующая функция</span><span class="sxs-lookup"><span data-stu-id="27590-164">Prediction function</span></span>

<span data-ttu-id="27590-165">Прогнозирующую функцию можно рассматривать как компонент, который применяет преобразователь к одной строке.</span><span class="sxs-lookup"><span data-stu-id="27590-165">The prediction function can be seen as a component that applies a transformer to one row.</span></span>

<span data-ttu-id="27590-166">Когда у вас будет модель (*преобразователь*, обученный с помощью `Fit()` или загруженный из другого места), ее можно использовать для создания прогнозов с помощью обычных вызовов к `model.Transform(data)`.</span><span class="sxs-lookup"><span data-stu-id="27590-166">Once you get the model (a *transformer* either trained via `Fit()`, or loaded from somewhere), you can use it to make predictions using the normal calls to `model.Transform(data)`.</span></span> <span data-ttu-id="27590-167">Но при использовании этой модели в реальных сценариях часто у вас не бывает много примеров для прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="27590-167">However, when you use this model in a real-life scenario, you often don't have many examples to predict on.</span></span> <span data-ttu-id="27590-168">У вас есть по примеру за раз, и вам сразу нужны своевременные прогнозы.</span><span class="sxs-lookup"><span data-stu-id="27590-168">Instead, you have one example at a time, and you need to make timely predictions on them immediately.</span></span>

<span data-ttu-id="27590-169">Конечно, можно свести это к пакетному прогнозированию:</span><span class="sxs-lookup"><span data-stu-id="27590-169">Of course, you can reduce this to the batch prediction:</span></span>

- <span data-ttu-id="27590-170">Создайте представление данных с одной строкой.</span><span class="sxs-lookup"><span data-stu-id="27590-170">Create a data view with exactly one row.</span></span>
- <span data-ttu-id="27590-171">Вызовите `model.Transform(data)` для получения спрогнозированного представления данных.</span><span class="sxs-lookup"><span data-stu-id="27590-171">Call `model.Transform(data)` to get the predicted data view.</span></span>
- <span data-ttu-id="27590-172">Поставьте курсор на полученных данных.</span><span class="sxs-lookup"><span data-stu-id="27590-172">Get a cursor over the resulting data.</span></span>
- <span data-ttu-id="27590-173">Переместите курсор на один шаг, чтобы перейти к первой (и единственной) строке.</span><span class="sxs-lookup"><span data-stu-id="27590-173">Advance the cursor one step to get to the first (and only) row.</span></span>
- <span data-ttu-id="27590-174">Извлеките из нее прогнозируемые значения.</span><span class="sxs-lookup"><span data-stu-id="27590-174">Extract the predicted values out of it.</span></span>

<span data-ttu-id="27590-175">Предыдущий алгоритм может осуществляться с помощью [понимания схемы](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md) с двумя объектами, определяемыми пользователем, `InputExample` и `OutputPrediction`, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="27590-175">The preceding algorithm can be implemented using the [schema comprehension](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md), with two user-defined objects `InputExample` and `OutputPrediction` as follows:</span></span>

```csharp
var inputData = mlContext.Data.ReadFromEnumerable(new InputExample[] { example });
var outputData = model.Transform(inputData);
var output = mlContext.CreateEnumerable<OutputPrediction>(outputData,reuseRowObject:false).First();
```

<span data-ttu-id="27590-176">Но это неудобно и влечет за собой снижение производительности.</span><span class="sxs-lookup"><span data-stu-id="27590-176">But this is cumbersome and incurs performance costs.</span></span> <span data-ttu-id="27590-177">Вместо этого объект прогнозирующей функции выполняет ту же работу, но быстрее и удобнее, с помощью метода расширения `CreatePredictionEngine`:</span><span class="sxs-lookup"><span data-stu-id="27590-177">Instead, a prediction function object performs the same work, but faster and more convenient, via an extension method `CreatePredictionEngine`:</span></span>

```csharp
var predictionEngine = model.CreatePredictionEngine<InputExample,OutputPrediction>(mlContext);
var prediction = predictionEngine.Predict(example);
```

<span data-ttu-id="27590-178">Прогнозирующая функция является *нереентерабельной и потокобезопасной*.</span><span class="sxs-lookup"><span data-stu-id="27590-178">The prediction function is *not re-entrant / thread-safe*.</span></span> <span data-ttu-id="27590-179">Если вы хотите осуществлять прогнозирование с несколькими потоками, вам нужна прогнозирующая функция для каждого потока.</span><span class="sxs-lookup"><span data-stu-id="27590-179">If you want to conduct predictions simultaneously with multiple threads, you need to have a prediction function per thread.</span></span>
