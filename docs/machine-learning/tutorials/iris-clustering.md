---
title: Использование ML.NET для кластеризации ирисов
description: Сведения об использовании ML.NET при кластеризации
author: pkulikov
ms.author: johalex
ms.date: 07/02/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: bb41fd317507c14b46aea94e1ce576e390932a65
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2018
ms.locfileid: "49453194"
---
# <a name="tutorial-use-mlnet-to-cluster-iris-flowers-clustering"></a><span data-ttu-id="7ff79-103">Руководство. Использование ML.NET для кластеризации ирисов</span><span class="sxs-lookup"><span data-stu-id="7ff79-103">Tutorial: Use ML.NET to cluster iris flowers (clustering)</span></span>

> [!NOTE]
> <span data-ttu-id="7ff79-104">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="7ff79-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="7ff79-105">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="7ff79-105">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="7ff79-106">В этом руководстве описано, как с помощью ML.NET создать [модель кластеризации](../resources/tasks.md#clustering) для [набора данных ирисов](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span><span class="sxs-lookup"><span data-stu-id="7ff79-106">This tutorial illustrates how to use ML.NET to build a [clustering model](../resources/tasks.md#clustering) for the [iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span></span>

<span data-ttu-id="7ff79-107">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="7ff79-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="7ff79-108">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="7ff79-108">Understand the problem</span></span>
> - <span data-ttu-id="7ff79-109">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="7ff79-109">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="7ff79-110">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="7ff79-110">Prepare the data</span></span>
> - <span data-ttu-id="7ff79-111">Загрузка и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="7ff79-111">Load and transform the data</span></span>
> - <span data-ttu-id="7ff79-112">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="7ff79-112">Choose a learning algorithm</span></span>
> - <span data-ttu-id="7ff79-113">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="7ff79-113">Train the model</span></span>
> - <span data-ttu-id="7ff79-114">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="7ff79-114">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7ff79-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="7ff79-115">Prerequisites</span></span>

- <span data-ttu-id="7ff79-116">[Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="7ff79-116">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="7ff79-117">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="7ff79-117">Understand the problem</span></span>

<span data-ttu-id="7ff79-118">Задача — разделить ирисы на группы в зависимости от признаков цветка.</span><span class="sxs-lookup"><span data-stu-id="7ff79-118">This problem is about dividing the set of iris flowers in different groups based on the flower features.</span></span> <span data-ttu-id="7ff79-119">Эти признаки — длина и ширина чашелистика и длина и ширина лепестка.</span><span class="sxs-lookup"><span data-stu-id="7ff79-119">Those features are the length and width of a sepal and the length and width of a petal.</span></span> <span data-ttu-id="7ff79-120">В этом руководстве предполагается, что тип каждого цветка неизвестен.</span><span class="sxs-lookup"><span data-stu-id="7ff79-120">For this tutorial, assume that the type of each flower is unknown.</span></span> <span data-ttu-id="7ff79-121">Вы научитесь структурировать набор данных по признакам и предсказывать, как экземпляр данных будет вписываться в эту структуру.</span><span class="sxs-lookup"><span data-stu-id="7ff79-121">You want to learn the structure of a data set from the features and predict how a data instance fits this structure.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="7ff79-122">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="7ff79-122">Select the appropriate machine learning task</span></span>

<span data-ttu-id="7ff79-123">Поскольку вы не знаете, к какой группе принадлежит каждый цветок, вы выбираете задачу [неконтролируемого машинного обучения](../resources/glossary.md#unsupervised-machine-learning).</span><span class="sxs-lookup"><span data-stu-id="7ff79-123">As you don't know to which group each flower belongs to, you choose the [unsupervised machine learning](../resources/glossary.md#unsupervised-machine-learning) task.</span></span> <span data-ttu-id="7ff79-124">Чтобы разделить набор данных на группы таким образом, чтобы элементы одной группы больше походили друг на друга, чем на элементы из других групп, используйте задачу машинного обучения по [кластеризации](../resources/tasks.md#clustering).</span><span class="sxs-lookup"><span data-stu-id="7ff79-124">To divide a data set in groups in such a way that elements in the same group are more similar to each other than to those in other groups, use a [clustering](../resources/tasks.md#clustering) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="7ff79-125">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="7ff79-125">Create a console application</span></span>

1. <span data-ttu-id="7ff79-126">Откройте Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="7ff79-126">Open Visual Studio 2017.</span></span> <span data-ttu-id="7ff79-127">Выберите **Файл** > **Создать** > **Проект** в меню.</span><span class="sxs-lookup"><span data-stu-id="7ff79-127">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="7ff79-128">В диалоговом окне **Новый проект** выберите узел **Visual C#**, а затем — узел **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="7ff79-128">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="7ff79-129">Выберите шаблон проекта **Консольное приложение (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="7ff79-129">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="7ff79-130">В текстовом поле **Имя** введите "IrisClustering", а затем нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="7ff79-130">In the **Name** text box, type "IrisClustering" and then select the **OK** button.</span></span>

1. <span data-ttu-id="7ff79-131">Создайте каталог с именем *Data* в папке проекта, чтобы хранить в нем наборы данных и файлы модели:</span><span class="sxs-lookup"><span data-stu-id="7ff79-131">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="7ff79-132">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="7ff79-132">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="7ff79-133">Введите имя папки Data и нажмите клавишу "ВВОД".</span><span class="sxs-lookup"><span data-stu-id="7ff79-133">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="7ff79-134">Установите пакет NuGet для **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="7ff79-134">Install the **Microsoft.ML** NuGet package:</span></span>

    <span data-ttu-id="7ff79-135">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="7ff79-135">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="7ff79-136">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку **Обзор**, выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="7ff79-136">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="7ff79-137">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="7ff79-137">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="7ff79-138">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="7ff79-138">Prepare the data</span></span>

1. <span data-ttu-id="7ff79-139">Скачайте набор данных [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) и сохраните его в папке *Data*, созданной на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="7ff79-139">Download the [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) data set and save it to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="7ff79-140">Дополнительные сведения о наборе данных ирисов см. на странице Википедии [Ирисы Фишера](https://en.wikipedia.org/wiki/Iris_flower_data_set) и на странице [Набор данных ирисов](http://archive.ics.uci.edu/ml/datasets/Iris), который является источником набора данных.</span><span class="sxs-lookup"><span data-stu-id="7ff79-140">For more information about the iris data set, see the [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia page and the [Iris Data Set](http://archive.ics.uci.edu/ml/datasets/Iris) page, which is the source of the data set.</span></span>

1. <span data-ttu-id="7ff79-141">В **Обозревателе решений** щелкните правой кнопкой мыши файл *iris.data* и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7ff79-141">In **Solution Explorer**, right-click the *iris.data* file and select **Properties**.</span></span> <span data-ttu-id="7ff79-142">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="7ff79-142">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="7ff79-143">Файл *Iris.data* содержит пять столбцов со следующими данными:</span><span class="sxs-lookup"><span data-stu-id="7ff79-143">The *iris.data* file contains five columns that represent:</span></span>

- <span data-ttu-id="7ff79-144">длина чашелистика в см;</span><span class="sxs-lookup"><span data-stu-id="7ff79-144">sepal length in centimetres</span></span>
- <span data-ttu-id="7ff79-145">ширина чашелистика в см;</span><span class="sxs-lookup"><span data-stu-id="7ff79-145">sepal width in centimetres</span></span>
- <span data-ttu-id="7ff79-146">длина лепестка в см;</span><span class="sxs-lookup"><span data-stu-id="7ff79-146">petal length in centimetres</span></span>
- <span data-ttu-id="7ff79-147">ширина лепестка в см;</span><span class="sxs-lookup"><span data-stu-id="7ff79-147">petal width in centimetres</span></span>
- <span data-ttu-id="7ff79-148">тип ириса.</span><span class="sxs-lookup"><span data-stu-id="7ff79-148">type of iris flower</span></span>

<span data-ttu-id="7ff79-149">В этом примере кластеризации мы не будем учитывать последний столбец.</span><span class="sxs-lookup"><span data-stu-id="7ff79-149">For the sake of the clustering example, this tutorial ignores the last column.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="7ff79-150">Создание классов данных</span><span class="sxs-lookup"><span data-stu-id="7ff79-150">Create data classes</span></span>

<span data-ttu-id="7ff79-151">Создайте классы для входных данных и прогнозов:</span><span class="sxs-lookup"><span data-stu-id="7ff79-151">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="7ff79-152">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="7ff79-152">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="7ff79-153">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *IrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="7ff79-153">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *IrisData.cs*.</span></span> <span data-ttu-id="7ff79-154">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7ff79-154">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="7ff79-155">Добавьте следующую директиву `using` в новый файл:</span><span class="sxs-lookup"><span data-stu-id="7ff79-155">Add the following `using` directive to the new file:</span></span>

   [!code-csharp[Add necessary usings](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#1)]

<span data-ttu-id="7ff79-156">Удалите из файла *IrisData.cs* существующее определение класса и добавьте следующий код, который определяет классы `IrisData` и `ClusterPrediction`:</span><span class="sxs-lookup"><span data-stu-id="7ff79-156">Remove the existing class definition and add the following code, which defines the classes `IrisData` and `ClusterPrediction`, to the *IrisData.cs* file:</span></span>

[!code-csharp[Define data classes](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#2)]

<span data-ttu-id="7ff79-157">Класс `IrisData` содержит входные данные и определения для каждого признака в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="7ff79-157">`IrisData` is the input data class and has definitions for each feature from the data set.</span></span> <span data-ttu-id="7ff79-158">Используйте атрибут [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute), чтобы указать индексы исходных столбцов в файле набора данных.</span><span class="sxs-lookup"><span data-stu-id="7ff79-158">Use the [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) attribute to specify the indices of the source columns in the data set file.</span></span>

<span data-ttu-id="7ff79-159">Класс `ClusterPrediction` представляет выходные данные модели кластеризации, примененные к экземпляру `IrisData`.</span><span class="sxs-lookup"><span data-stu-id="7ff79-159">The `ClusterPrediction` class represents the output of the clustering model applied to an `IrisData` instance.</span></span> <span data-ttu-id="7ff79-160">Используйте атрибут [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute), чтобы привязать поля `PredictedClusterId` и `Distances` к столбцам **PredictedLabel** и **Score** соответственно.</span><span class="sxs-lookup"><span data-stu-id="7ff79-160">Use the [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) attribute to bind the `PredictedClusterId` and `Distances` fields to the **PredictedLabel** and **Score** columns respectively.</span></span> <span data-ttu-id="7ff79-161">В случае задачи кластеризации эти столбцы означают следующее:</span><span class="sxs-lookup"><span data-stu-id="7ff79-161">In case of the clustering task those columns have the following meaning:</span></span>

- <span data-ttu-id="7ff79-162">Столбец **PredictedLabel** содержит идентификатор прогнозируемого кластера.</span><span class="sxs-lookup"><span data-stu-id="7ff79-162">**PredictedLabel** column contains the ID of the predicted cluster.</span></span>
- <span data-ttu-id="7ff79-163">Столбец **Score** содержит массив с квадратом Евклидовых расстояний до центроидов кластера.</span><span class="sxs-lookup"><span data-stu-id="7ff79-163">**Score** column contains an array with squared Euclidean distances to the cluster centroids.</span></span> <span data-ttu-id="7ff79-164">Длина массива равна числу кластеров.</span><span class="sxs-lookup"><span data-stu-id="7ff79-164">The array length is equal to the number of clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="7ff79-165">Используйте тип `float` для представления значений с плавающей запятой в классах данных ввода и прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="7ff79-165">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="7ff79-166">Определение путей к данным и модели</span><span class="sxs-lookup"><span data-stu-id="7ff79-166">Define data and model paths</span></span>

<span data-ttu-id="7ff79-167">Вернитесь к файлу *Program.cs* и добавьте два поля, которые будут содержать пути к файлу с наборами данных и к файлу для сохранения модели.</span><span class="sxs-lookup"><span data-stu-id="7ff79-167">Go back to the *Program.cs* file and add two fields to hold the paths to the data set file and to the file to save the model:</span></span>

- <span data-ttu-id="7ff79-168">`_dataPath` содержит путь к файлу с набором данных, используемым для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="7ff79-168">`_dataPath` contains the path to the file with the data set used to train the model.</span></span>
- <span data-ttu-id="7ff79-169">`_modelPath` содержит путь к файлу для сохранения обучаемой модели.</span><span class="sxs-lookup"><span data-stu-id="7ff79-169">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="7ff79-170">Добавьте прямо перед методом `Main` следующий код, чтобы указать эти пути.</span><span class="sxs-lookup"><span data-stu-id="7ff79-170">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Initialize paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#1)]

<span data-ttu-id="7ff79-171">Чтобы этот код компилировался, добавьте следующие директивы `using` вверху файла *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="7ff79-171">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add usings for paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#2)]

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="7ff79-172">Создание конвейера обучения</span><span class="sxs-lookup"><span data-stu-id="7ff79-172">Create a learning pipeline</span></span>

<span data-ttu-id="7ff79-173">Добавьте дополнительные директивы `using` в начало файла *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="7ff79-173">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[Add Microsoft.ML usings](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#3)]

<span data-ttu-id="7ff79-174">В методе `Main` замените `Console.WriteLine("Hello World!")` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="7ff79-174">In the `Main` method, replace the `Console.WriteLine("Hello World!")` with the following code:</span></span>

[!code-csharp[Call the Train method](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#4)]

<span data-ttu-id="7ff79-175">Метод `Train` обучает модель.</span><span class="sxs-lookup"><span data-stu-id="7ff79-175">The `Train` method trains the model.</span></span> <span data-ttu-id="7ff79-176">Создайте этот метод сразу под методом `Main`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="7ff79-176">Create that method just below the `Main` method, using the following code:</span></span>

```csharp
private static PredictionModel<IrisData, ClusterPrediction> Train()
{

}
```

<span data-ttu-id="7ff79-177">Конвейер обучения загружает все данные и алгоритмы, необходимые для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="7ff79-177">The learning pipeline loads all of the data and algorithms necessary to train the model.</span></span> <span data-ttu-id="7ff79-178">Добавьте в метод `Train` следующий код:</span><span class="sxs-lookup"><span data-stu-id="7ff79-178">Add the following code into the `Train` method:</span></span>

[!code-csharp[Initialize pipeline](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#5)]

## <a name="load-and-transform-data"></a><span data-ttu-id="7ff79-179">Загрузка и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="7ff79-179">Load and transform data</span></span>

<span data-ttu-id="7ff79-180">Сначала нужно загрузить набор данных для обучения.</span><span class="sxs-lookup"><span data-stu-id="7ff79-180">The first step to perform is to load the training data set.</span></span> <span data-ttu-id="7ff79-181">В нашем случае набор данных для обучения хранится в текстовом файле, путь к которому задан в поле `_dataPath`.</span><span class="sxs-lookup"><span data-stu-id="7ff79-181">In our case, the training data set is stored in the text file with a path defined by the `_dataPath` field.</span></span> <span data-ttu-id="7ff79-182">Для разделения столбцов в этом файле используется запятая (",").</span><span class="sxs-lookup"><span data-stu-id="7ff79-182">Columns in the file are separated by the comma (",").</span></span> <span data-ttu-id="7ff79-183">Добавьте в метод `Train` следующий код:</span><span class="sxs-lookup"><span data-stu-id="7ff79-183">Add the following code into the `Train` method:</span></span>

[!code-csharp[Add step to load data](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#6)]

<span data-ttu-id="7ff79-184">Следующий шаг — объединить все столбцы признаков в столбце **Features** с помощью класса преобразования <xref:Microsoft.ML.Legacy.Transforms.ColumnConcatenator>.</span><span class="sxs-lookup"><span data-stu-id="7ff79-184">The next step is to combine all of the feature columns into the **Features** column using the <xref:Microsoft.ML.Legacy.Transforms.ColumnConcatenator> transformation class.</span></span> <span data-ttu-id="7ff79-185">По умолчанию алгоритм обучения обрабатывает только признаки, представленные в столбце **Features**.</span><span class="sxs-lookup"><span data-stu-id="7ff79-185">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="7ff79-186">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="7ff79-186">Add the following code:</span></span>

[!code-csharp[Add step to concatenate columns](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#7)]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="7ff79-187">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="7ff79-187">Choose a learning algorithm</span></span>

<span data-ttu-id="7ff79-188">После добавления данных в конвейер и их преобразования в правильный входной формат выберите алгоритм обучения (**средство обучения**).</span><span class="sxs-lookup"><span data-stu-id="7ff79-188">After adding the data to the pipeline and transforming it into the correct input format, you select a learning algorithm (**learner**).</span></span> <span data-ttu-id="7ff79-189">Алгоритм обучения осуществляет обучение модели.</span><span class="sxs-lookup"><span data-stu-id="7ff79-189">The learner trains the model.</span></span> <span data-ttu-id="7ff79-190">ML.NET предоставляет средство обучения <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer>, которое реализует [алгоритм k-средних](https://en.wikipedia.org/wiki/K-means_clustering) с улучшенным методом для выбора начальных центроидов кластера.</span><span class="sxs-lookup"><span data-stu-id="7ff79-190">ML.NET provides a <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer> learner that implements [k-means algorithm](https://en.wikipedia.org/wiki/K-means_clustering) with an improved method for choosing the initial cluster centroids.</span></span>

<span data-ttu-id="7ff79-191">Добавьте следующий код в метод `Train` после кода обработки данных, который вы добавили на предыдущем шаге:</span><span class="sxs-lookup"><span data-stu-id="7ff79-191">Add the following code into the `Train` method following the data processing code added in the previous step:</span></span>

[!code-csharp[Add a learner step](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#8)]

<span data-ttu-id="7ff79-192">Используйте свойство <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer.K?displayProperty=nameWithType>, чтобы указать число кластеров.</span><span class="sxs-lookup"><span data-stu-id="7ff79-192">Use the <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer.K?displayProperty=nameWithType> property to specify number of clusters.</span></span> <span data-ttu-id="7ff79-193">В приведенном выше коде указано, что набор данных нужно разделить на три кластера.</span><span class="sxs-lookup"><span data-stu-id="7ff79-193">The code above specifies that the data set should be split in three clusters.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="7ff79-194">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="7ff79-194">Train the model</span></span>

<span data-ttu-id="7ff79-195">Выполнив действия в предыдущих разделах, вы подготовили конвейер для обучения, но пока ничего не было сделано.</span><span class="sxs-lookup"><span data-stu-id="7ff79-195">The steps added in the preceding sections prepared the pipeline for training, however, none have been executed.</span></span> <span data-ttu-id="7ff79-196">Метод `pipeline.Train<TInput, TOutput>` создает модель, которая принимает экземпляр типа `TInput` и возвращает экземпляр типа `TOutput`.</span><span class="sxs-lookup"><span data-stu-id="7ff79-196">The `pipeline.Train<TInput, TOutput>` method produces the model that takes in an instance of the `TInput` type and outputs an instance of the `TOutput` type.</span></span> <span data-ttu-id="7ff79-197">Добавьте в метод `Train` следующий код:</span><span class="sxs-lookup"><span data-stu-id="7ff79-197">Add the following code into the `Train` method:</span></span>

[!code-csharp[Train the model and return](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#9)]

### <a name="save-the-model"></a><span data-ttu-id="7ff79-198">Сохранение модели</span><span class="sxs-lookup"><span data-stu-id="7ff79-198">Save the model</span></span>

<span data-ttu-id="7ff79-199">На этом этапе у вас есть модель, которую можно интегрировать с любыми существующими или новыми приложениями .NET.</span><span class="sxs-lookup"><span data-stu-id="7ff79-199">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="7ff79-200">Чтобы сохранить модель в ZIP-файл, добавьте следующий код в метод `Main` под вызовом метода `Train`:</span><span class="sxs-lookup"><span data-stu-id="7ff79-200">To save your model to a .zip file, add the following code to the `Main` method below the call to the `Train` method:</span></span>

[!code-csharp[Save the model](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#10)]

<span data-ttu-id="7ff79-201">Использование `await` в методе `Main` означает, что метод `Main` должен включать модификатор `async` и возвращать `Task`:</span><span class="sxs-lookup"><span data-stu-id="7ff79-201">Using `await` in the `Main` method means the `Main` method must have the `async` modifier and return a `Task`:</span></span>

[!code-csharp[Make the Main method async](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#11)]

<span data-ttu-id="7ff79-202">Также добавьте следующую директиву `using` в самое начало файла *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="7ff79-202">You also need to add the following `using` directive at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add System.Threading.Tasks using](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#12)]

<span data-ttu-id="7ff79-203">Так как метод `async Main` реализован только в C# версии 7.1, а для этого проекта по умолчанию устанавливается версия языка C# 7.0, необходимо изменить версию до C# 7.1 или выше.</span><span class="sxs-lookup"><span data-stu-id="7ff79-203">Because the `async Main` method is the feature added in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span> <span data-ttu-id="7ff79-204">Для этого в **обозревателе решений** щелкните узел проекта правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7ff79-204">To do that, right-click the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="7ff79-205">Откройте вкладку **Сборка** и нажмите на кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="7ff79-205">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="7ff79-206">В раскрывающемся списке выберите **C# 7.1** (или более позднюю версию).</span><span class="sxs-lookup"><span data-stu-id="7ff79-206">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="7ff79-207">Нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="7ff79-207">Select the **OK** button.</span></span>

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="7ff79-208">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="7ff79-208">Use the model for predictions</span></span>

<span data-ttu-id="7ff79-209">Создание класса `TestIrisData` для размещения тестовых экземпляров данных:</span><span class="sxs-lookup"><span data-stu-id="7ff79-209">Create the `TestIrisData` class to house test data instances:</span></span>

1. <span data-ttu-id="7ff79-210">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="7ff79-210">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="7ff79-211">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *TestIrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="7ff79-211">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestIrisData.cs*.</span></span> <span data-ttu-id="7ff79-212">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7ff79-212">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="7ff79-213">Измените класс, чтобы он был статическим, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="7ff79-213">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[Make class static](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#1)]

<span data-ttu-id="7ff79-214">В этом руководстве представлен один экземпляр данных ирисов в этом классе.</span><span class="sxs-lookup"><span data-stu-id="7ff79-214">This tutorial introduces one iris data instance within this class.</span></span> <span data-ttu-id="7ff79-215">Вы можете добавить другие сценарии и поэкспериментировать с этой моделью.</span><span class="sxs-lookup"><span data-stu-id="7ff79-215">You can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="7ff79-216">Добавьте в класс `TestIrisData` следующий код:</span><span class="sxs-lookup"><span data-stu-id="7ff79-216">Add the following code into the `TestIrisData` class:</span></span>

[!code-csharp[Test data](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#2)]

<span data-ttu-id="7ff79-217">Чтобы узнать, к какому кластеру принадлежит указанный элемент, вернитесь к файлу *Program.cs* и добавьте следующий код в метод `Main`:</span><span class="sxs-lookup"><span data-stu-id="7ff79-217">To find out the cluster to which the specified item belongs to, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict and output results](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#13)]

<span data-ttu-id="7ff79-218">Запустите программу, чтобы узнать, какой кластер содержит указанный экземпляр данных и квадрат расстояния от этого экземпляра до центроидов кластера.</span><span class="sxs-lookup"><span data-stu-id="7ff79-218">Run the program to see which cluster contains the specified data instance and squared distances from that instance to the cluster centroids.</span></span> <span data-ttu-id="7ff79-219">Результаты выполнения должны выглядеть примерно так, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="7ff79-219">Your results should be similar to the following.</span></span> <span data-ttu-id="7ff79-220">Во время обработки конвейер может вывести предупреждения или сообщения об обработке.</span><span class="sxs-lookup"><span data-stu-id="7ff79-220">As the pipeline processes, it might display warnings or processing messages.</span></span> <span data-ttu-id="7ff79-221">Для удобства они удалены из следующих выходных данных.</span><span class="sxs-lookup"><span data-stu-id="7ff79-221">These have been removed from the following output for clarity.</span></span>

```text
Cluster: 2
Distances: 0.4192338 0.0008847713 0.9660053
```

<span data-ttu-id="7ff79-222">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="7ff79-222">Congratulations!</span></span> <span data-ttu-id="7ff79-223">Вы успешно создали модель машинного обучения для кластеризации ирисов и использовали ее для прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="7ff79-223">You've now successfully built a machine learning model for iris clustering and used it to make predictions.</span></span> <span data-ttu-id="7ff79-224">Исходный код для этого руководства можно найти в репозитории GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisClustering).</span><span class="sxs-lookup"><span data-stu-id="7ff79-224">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisClustering) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7ff79-225">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="7ff79-225">Next steps</span></span>

<span data-ttu-id="7ff79-226">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="7ff79-226">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="7ff79-227">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="7ff79-227">Understand the problem</span></span>
> - <span data-ttu-id="7ff79-228">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="7ff79-228">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="7ff79-229">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="7ff79-229">Prepare the data</span></span>
> - <span data-ttu-id="7ff79-230">Загрузка и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="7ff79-230">Load and transform the data</span></span>
> - <span data-ttu-id="7ff79-231">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="7ff79-231">Choose a learning algorithm</span></span>
> - <span data-ttu-id="7ff79-232">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="7ff79-232">Train the model</span></span>
> - <span data-ttu-id="7ff79-233">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="7ff79-233">Use the model for predictions</span></span>

<span data-ttu-id="7ff79-234">Извлеките наш репозиторий GitHub, чтобы продолжить обучение и получить дополнительные примеры.</span><span class="sxs-lookup"><span data-stu-id="7ff79-234">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="7ff79-235">Репозиторий GitHub dotnet/machinelearning</span><span class="sxs-lookup"><span data-stu-id="7ff79-235">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
