---
title: Учебник. Классификация цветов ириса — кластеризация k-средних
description: Сведения об использовании ML.NET при кластеризации
author: pkulikov
ms.date: 11/15/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0516
ms.openlocfilehash: cc3a1ae984289eb01ad8fdee9741f3f9788196c7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716237"
---
# <a name="tutorial-categorize-iris-flowers-using-k-means-clustering-with-mlnet"></a><span data-ttu-id="88d51-103">Учебник. Категоризация цветов ириса с использованием кластеризации k-средних в ML.NET</span><span class="sxs-lookup"><span data-stu-id="88d51-103">Tutorial: Categorize iris flowers using k-means clustering with ML.NET</span></span>

<span data-ttu-id="88d51-104">В этом руководстве описано, как с помощью ML.NET создать [модель кластеризации](../resources/tasks.md#clustering) для [набора данных ирисов](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span><span class="sxs-lookup"><span data-stu-id="88d51-104">This tutorial illustrates how to use ML.NET to build a [clustering model](../resources/tasks.md#clustering) for the [iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span></span>

<span data-ttu-id="88d51-105">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="88d51-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="88d51-106">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="88d51-106">Understand the problem</span></span>
> - <span data-ttu-id="88d51-107">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="88d51-107">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="88d51-108">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="88d51-108">Prepare the data</span></span>
> - <span data-ttu-id="88d51-109">Загрузка и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="88d51-109">Load and transform the data</span></span>
> - <span data-ttu-id="88d51-110">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="88d51-110">Choose a learning algorithm</span></span>
> - <span data-ttu-id="88d51-111">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="88d51-111">Train the model</span></span>
> - <span data-ttu-id="88d51-112">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="88d51-112">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="88d51-113">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="88d51-113">Prerequisites</span></span>

- <span data-ttu-id="88d51-114">[Visual Studio 2017 версии 15.6 или более поздней](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="88d51-114">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="88d51-115">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="88d51-115">Understand the problem</span></span>

<span data-ttu-id="88d51-116">Задача — разделить ирисы на группы в зависимости от признаков цветка.</span><span class="sxs-lookup"><span data-stu-id="88d51-116">This problem is about dividing the set of iris flowers in different groups based on the flower features.</span></span> <span data-ttu-id="88d51-117">Эти признаки — длина и ширина чашелистика и длина и ширина лепестка.</span><span class="sxs-lookup"><span data-stu-id="88d51-117">Those features are the length and width of a sepal and the length and width of a petal.</span></span> <span data-ttu-id="88d51-118">В этом руководстве предполагается, что тип каждого цветка неизвестен.</span><span class="sxs-lookup"><span data-stu-id="88d51-118">For this tutorial, assume that the type of each flower is unknown.</span></span> <span data-ttu-id="88d51-119">Вы научитесь структурировать набор данных по признакам и предсказывать, как экземпляр данных будет вписываться в эту структуру.</span><span class="sxs-lookup"><span data-stu-id="88d51-119">You want to learn the structure of a data set from the features and predict how a data instance fits this structure.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="88d51-120">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="88d51-120">Select the appropriate machine learning task</span></span>

<span data-ttu-id="88d51-121">Поскольку вы не знаете, к какой группе принадлежит каждый цветок, вы выбираете задачу [неконтролируемого машинного обучения](../resources/glossary.md#unsupervised-machine-learning).</span><span class="sxs-lookup"><span data-stu-id="88d51-121">As you don't know to which group each flower belongs to, you choose the [unsupervised machine learning](../resources/glossary.md#unsupervised-machine-learning) task.</span></span> <span data-ttu-id="88d51-122">Чтобы разделить набор данных на группы таким образом, чтобы элементы одной группы больше походили друг на друга, чем на элементы из других групп, используйте задачу машинного обучения по [кластеризации](../resources/tasks.md#clustering).</span><span class="sxs-lookup"><span data-stu-id="88d51-122">To divide a data set in groups in such a way that elements in the same group are more similar to each other than to those in other groups, use a [clustering](../resources/tasks.md#clustering) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="88d51-123">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="88d51-123">Create a console application</span></span>

1. <span data-ttu-id="88d51-124">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="88d51-124">Open Visual Studio.</span></span> <span data-ttu-id="88d51-125">Выберите **Файл** > **Создать** > **Проект** в меню.</span><span class="sxs-lookup"><span data-stu-id="88d51-125">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="88d51-126">В диалоговом окне **Новый проект** выберите узел **Visual C#** , а затем — узел **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="88d51-126">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="88d51-127">Выберите шаблон проекта **Консольное приложение (.NET Core)** .</span><span class="sxs-lookup"><span data-stu-id="88d51-127">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="88d51-128">В текстовом поле **Имя** введите "IrisFlowerClustering", а затем нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="88d51-128">In the **Name** text box, type "IrisFlowerClustering" and then select the **OK** button.</span></span>

1. <span data-ttu-id="88d51-129">Создайте каталог с именем *Data* в папке проекта, чтобы хранить в нем наборы данных и файлы модели:</span><span class="sxs-lookup"><span data-stu-id="88d51-129">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="88d51-130">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="88d51-130">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="88d51-131">Введите имя папки Data и нажмите клавишу "ВВОД".</span><span class="sxs-lookup"><span data-stu-id="88d51-131">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="88d51-132">Установите пакет NuGet для **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="88d51-132">Install the **Microsoft.ML** NuGet package:</span></span>

    <span data-ttu-id="88d51-133">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="88d51-133">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="88d51-134">Выберите nuget.org в качестве источника пакета, откройте вкладку **Обзор**, выполните поиск по запросу **Microsoft.ML** и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="88d51-134">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML** and select the **Install** button.</span></span> <span data-ttu-id="88d51-135">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="88d51-135">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="88d51-136">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="88d51-136">Prepare the data</span></span>

1. <span data-ttu-id="88d51-137">Скачайте набор данных [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) и сохраните его в папке *Data*, созданной на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="88d51-137">Download the [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) data set and save it to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="88d51-138">Дополнительные сведения о наборе данных ирисов см. на странице Википедии [Ирисы Фишера](https://en.wikipedia.org/wiki/Iris_flower_data_set) и на странице [Набор данных ирисов](https://archive.ics.uci.edu/ml/datasets/Iris), который является источником набора данных.</span><span class="sxs-lookup"><span data-stu-id="88d51-138">For more information about the iris data set, see the [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia page and the [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris) page, which is the source of the data set.</span></span>

1. <span data-ttu-id="88d51-139">В **Обозревателе решений** щелкните правой кнопкой мыши файл *iris.data* и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="88d51-139">In **Solution Explorer**, right-click the *iris.data* file and select **Properties**.</span></span> <span data-ttu-id="88d51-140">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="88d51-140">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="88d51-141">Файл *Iris.data* содержит пять столбцов со следующими данными:</span><span class="sxs-lookup"><span data-stu-id="88d51-141">The *iris.data* file contains five columns that represent:</span></span>

- <span data-ttu-id="88d51-142">длина чашелистика в см;</span><span class="sxs-lookup"><span data-stu-id="88d51-142">sepal length in centimetres</span></span>
- <span data-ttu-id="88d51-143">ширина чашелистика в см;</span><span class="sxs-lookup"><span data-stu-id="88d51-143">sepal width in centimetres</span></span>
- <span data-ttu-id="88d51-144">длина лепестка в см;</span><span class="sxs-lookup"><span data-stu-id="88d51-144">petal length in centimetres</span></span>
- <span data-ttu-id="88d51-145">ширина лепестка в см;</span><span class="sxs-lookup"><span data-stu-id="88d51-145">petal width in centimetres</span></span>
- <span data-ttu-id="88d51-146">тип ириса.</span><span class="sxs-lookup"><span data-stu-id="88d51-146">type of iris flower</span></span>

<span data-ttu-id="88d51-147">В этом примере кластеризации мы не будем учитывать последний столбец.</span><span class="sxs-lookup"><span data-stu-id="88d51-147">For the sake of the clustering example, this tutorial ignores the last column.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="88d51-148">Создание классов данных</span><span class="sxs-lookup"><span data-stu-id="88d51-148">Create data classes</span></span>

<span data-ttu-id="88d51-149">Создайте классы для входных данных и прогнозов:</span><span class="sxs-lookup"><span data-stu-id="88d51-149">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="88d51-150">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="88d51-150">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="88d51-151">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *IrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="88d51-151">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *IrisData.cs*.</span></span> <span data-ttu-id="88d51-152">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="88d51-152">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="88d51-153">Добавьте следующую директиву `using` в новый файл:</span><span class="sxs-lookup"><span data-stu-id="88d51-153">Add the following `using` directive to the new file:</span></span>

   [!code-csharp[Add necessary usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#Usings)]

<span data-ttu-id="88d51-154">Удалите из файла *IrisData.cs* существующее определение класса и добавьте следующий код, который определяет классы `IrisData` и `ClusterPrediction`:</span><span class="sxs-lookup"><span data-stu-id="88d51-154">Remove the existing class definition and add the following code, which defines the classes `IrisData` and `ClusterPrediction`, to the *IrisData.cs* file:</span></span>

[!code-csharp[Define data classes](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#ClassDefinitions)]

<span data-ttu-id="88d51-155">Класс `IrisData` содержит входные данные и определения для каждого признака в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="88d51-155">`IrisData` is the input data class and has definitions for each feature from the data set.</span></span> <span data-ttu-id="88d51-156">Используйте атрибут [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute), чтобы указать индексы исходных столбцов в файле набора данных.</span><span class="sxs-lookup"><span data-stu-id="88d51-156">Use the [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute to specify the indices of the source columns in the data set file.</span></span>

<span data-ttu-id="88d51-157">Класс `ClusterPrediction` представляет выходные данные модели кластеризации, примененные к экземпляру `IrisData`.</span><span class="sxs-lookup"><span data-stu-id="88d51-157">The `ClusterPrediction` class represents the output of the clustering model applied to an `IrisData` instance.</span></span> <span data-ttu-id="88d51-158">Используйте атрибут [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute), чтобы привязать поля `PredictedClusterId` и `Distances` к столбцам **PredictedLabel** и **Score** соответственно.</span><span class="sxs-lookup"><span data-stu-id="88d51-158">Use the [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute to bind the `PredictedClusterId` and `Distances` fields to the **PredictedLabel** and **Score** columns respectively.</span></span> <span data-ttu-id="88d51-159">В случае задачи кластеризации эти столбцы означают следующее:</span><span class="sxs-lookup"><span data-stu-id="88d51-159">In case of the clustering task those columns have the following meaning:</span></span>

- <span data-ttu-id="88d51-160">Столбец **PredictedLabel** содержит идентификатор прогнозируемого кластера.</span><span class="sxs-lookup"><span data-stu-id="88d51-160">**PredictedLabel** column contains the ID of the predicted cluster.</span></span>
- <span data-ttu-id="88d51-161">Столбец **Score** содержит массив с квадратом Евклидовых расстояний до центроидов кластера.</span><span class="sxs-lookup"><span data-stu-id="88d51-161">**Score** column contains an array with squared Euclidean distances to the cluster centroids.</span></span> <span data-ttu-id="88d51-162">Длина массива равна числу кластеров.</span><span class="sxs-lookup"><span data-stu-id="88d51-162">The array length is equal to the number of clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="88d51-163">Используйте тип `float` для представления значений с плавающей запятой в классах данных ввода и прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="88d51-163">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="88d51-164">Определение путей к данным и модели</span><span class="sxs-lookup"><span data-stu-id="88d51-164">Define data and model paths</span></span>

<span data-ttu-id="88d51-165">Вернитесь к файлу *Program.cs* и добавьте два поля, которые будут содержать пути к файлу с наборами данных и к файлу для сохранения модели.</span><span class="sxs-lookup"><span data-stu-id="88d51-165">Go back to the *Program.cs* file and add two fields to hold the paths to the data set file and to the file to save the model:</span></span>

- <span data-ttu-id="88d51-166">`_dataPath` содержит путь к файлу с набором данных, используемым для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="88d51-166">`_dataPath` contains the path to the file with the data set used to train the model.</span></span>
- <span data-ttu-id="88d51-167">`_modelPath` содержит путь к файлу для сохранения обучаемой модели.</span><span class="sxs-lookup"><span data-stu-id="88d51-167">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="88d51-168">Добавьте прямо перед методом `Main` следующий код, чтобы указать эти пути.</span><span class="sxs-lookup"><span data-stu-id="88d51-168">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Initialize paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Paths)]

<span data-ttu-id="88d51-169">Чтобы этот код компилировался, добавьте следующие директивы `using` вверху файла *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="88d51-169">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add usings for paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#UsingsForPaths)]

## <a name="create-ml-context"></a><span data-ttu-id="88d51-170">Создание контекста машинного обучения ML</span><span class="sxs-lookup"><span data-stu-id="88d51-170">Create ML context</span></span>

<span data-ttu-id="88d51-171">Добавьте дополнительные директивы `using` в начало файла *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="88d51-171">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[Add Microsoft.ML usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#MLUsings)]

<span data-ttu-id="88d51-172">В методе `Main` замените строку `Console.WriteLine("Hello World!");` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="88d51-172">In the `Main` method, replace the `Console.WriteLine("Hello World!");` line with the following code:</span></span>

[!code-csharp[Create ML context](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateContext)]

<span data-ttu-id="88d51-173">Класс <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> представляет среду машинного обучения и предоставляет механизмы для ведения журнала и точек входа для загрузки данных, обучения модели, прогнозирования и других задач.</span><span class="sxs-lookup"><span data-stu-id="88d51-173">The <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> class represents the machine learning environment and provides mechanisms for logging and entry points for data loading, model training, prediction, and other tasks.</span></span> <span data-ttu-id="88d51-174">Концептуально это сопоставимо с использованием `DbContext` в Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="88d51-174">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span>

## <a name="set-up-data-loading"></a><span data-ttu-id="88d51-175">Настройка загрузки данных</span><span class="sxs-lookup"><span data-stu-id="88d51-175">Set up data loading</span></span>

<span data-ttu-id="88d51-176">Добавьте следующий код к методу `Main`, чтобы настроить способ загрузки данных:</span><span class="sxs-lookup"><span data-stu-id="88d51-176">Add the following code to the `Main` method to set up the way to load data:</span></span>

[!code-csharp[Create text loader](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateDataView)]

<span data-ttu-id="88d51-177">Универсальный [метод расширения `MLContext.Data.LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) выводит схему набора данных на основе предоставленного типа `IrisData` и возвращает интерфейс <xref:Microsoft.ML.IDataView>, который можно использовать в качестве входных данных для преобразования.</span><span class="sxs-lookup"><span data-stu-id="88d51-177">The generic [`MLContext.Data.LoadFromTextFile` extension method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) infers the data set schema from the provided `IrisData` type and returns <xref:Microsoft.ML.IDataView> which can be used as input for transformers.</span></span>

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="88d51-178">Создание конвейера обучения</span><span class="sxs-lookup"><span data-stu-id="88d51-178">Create a learning pipeline</span></span>

<span data-ttu-id="88d51-179">В этом руководстве настройка конвейера обучения задач кластеризации состоит из следующих двух шагов:</span><span class="sxs-lookup"><span data-stu-id="88d51-179">For this tutorial, the learning pipeline of the clustering task comprises two following steps:</span></span>

- <span data-ttu-id="88d51-180">объедините загруженные столбцы в один столбец **Функции**, который используется тренером кластеризации;</span><span class="sxs-lookup"><span data-stu-id="88d51-180">concatenate loaded columns into one **Features** column, which is used by a clustering trainer;</span></span>
- <span data-ttu-id="88d51-181">используйте тренер <xref:Microsoft.ML.Trainers.KMeansTrainer> для обучения модели с помощью алгоритма кластеризации k-means++.</span><span class="sxs-lookup"><span data-stu-id="88d51-181">use a <xref:Microsoft.ML.Trainers.KMeansTrainer> trainer to train the model using the k-means++ clustering algorithm.</span></span>

<span data-ttu-id="88d51-182">Добавьте следующий код в метод `Main`:</span><span class="sxs-lookup"><span data-stu-id="88d51-182">Add the following code to the `Main` method:</span></span>

[!code-csharp[Create pipeline](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreatePipeline)]

<span data-ttu-id="88d51-183">В этом коде указано, что набор данных нужно разделить на три кластера.</span><span class="sxs-lookup"><span data-stu-id="88d51-183">The code specifies that the data set should be split in three clusters.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="88d51-184">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="88d51-184">Train the model</span></span>

<span data-ttu-id="88d51-185">Выполнив действия в предыдущих разделах, вы подготовили конвейер для обучения, но пока ничего не было сделано.</span><span class="sxs-lookup"><span data-stu-id="88d51-185">The steps added in the preceding sections prepared the pipeline for training, however, none have been executed.</span></span> <span data-ttu-id="88d51-186">Добавьте следующую строку к методу `Main`, чтобы выполнить загрузку данных и обучение модели:</span><span class="sxs-lookup"><span data-stu-id="88d51-186">Add the following line to the `Main` method to perform data loading and model training:</span></span>

[!code-csharp[Train the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#TrainModel)]

### <a name="save-the-model"></a><span data-ttu-id="88d51-187">Сохранение модели</span><span class="sxs-lookup"><span data-stu-id="88d51-187">Save the model</span></span>

<span data-ttu-id="88d51-188">На этом этапе у вас есть модель, которую можно интегрировать с любыми существующими или новыми приложениями .NET.</span><span class="sxs-lookup"><span data-stu-id="88d51-188">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="88d51-189">Чтобы сохранить модель в ZIP-файл, добавьте к методу `Main` следующий код:</span><span class="sxs-lookup"><span data-stu-id="88d51-189">To save your model to a .zip file, add the following code to the `Main` method:</span></span>

[!code-csharp[Save the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SaveModel)]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="88d51-190">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="88d51-190">Use the model for predictions</span></span>

<span data-ttu-id="88d51-191">Чтобы получить прогноз, используйте класс <xref:Microsoft.ML.PredictionEngine%602>, который принимает экземпляры входного типа через конвейер преобразователя и создает экземпляры выходного типа.</span><span class="sxs-lookup"><span data-stu-id="88d51-191">To make predictions, use the <xref:Microsoft.ML.PredictionEngine%602> class that takes instances of the input type through the transformer pipeline and produces instances of the output type.</span></span> <span data-ttu-id="88d51-192">Добавьте следующую строку к методу `Main` для создания экземпляра этого класса:</span><span class="sxs-lookup"><span data-stu-id="88d51-192">Add the following line to the `Main` method to create an instance of that class:</span></span>

[!code-csharp[Create predictor](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Predictor)]

<span data-ttu-id="88d51-193">Класс [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) представляет собой удобный API, позволяющий осуществить прогнозирование на основе единственного экземпляра данных.</span><span class="sxs-lookup"><span data-stu-id="88d51-193">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="88d51-194">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) не является потокобезопасным.</span><span class="sxs-lookup"><span data-stu-id="88d51-194">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="88d51-195">Допустимо использовать в средах прототипов или средах с одним потоком.</span><span class="sxs-lookup"><span data-stu-id="88d51-195">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="88d51-196">Для улучшенной производительности и потокобезопасности в рабочей среде используйте службу `PredictionEnginePool`, которая создает [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) объектов [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) для использования во всем приложении.</span><span class="sxs-lookup"><span data-stu-id="88d51-196">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="88d51-197">См. руководство по [использованию `PredictionEnginePool` в веб-API ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span><span class="sxs-lookup"><span data-stu-id="88d51-197">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

> [!NOTE]
> <span data-ttu-id="88d51-198">Расширение службы `PredictionEnginePool` сейчас доступно в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="88d51-198">`PredictionEnginePool` service extension is currently in preview.</span></span>

<span data-ttu-id="88d51-199">Создание класса `TestIrisData` для размещения тестовых экземпляров данных:</span><span class="sxs-lookup"><span data-stu-id="88d51-199">Create the `TestIrisData` class to house test data instances:</span></span>

1. <span data-ttu-id="88d51-200">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="88d51-200">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="88d51-201">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *TestIrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="88d51-201">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestIrisData.cs*.</span></span> <span data-ttu-id="88d51-202">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="88d51-202">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="88d51-203">Измените класс, чтобы он был статическим, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="88d51-203">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[Make class static](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#Static)]

<span data-ttu-id="88d51-204">В этом руководстве представлен один экземпляр данных ирисов в этом классе.</span><span class="sxs-lookup"><span data-stu-id="88d51-204">This tutorial introduces one iris data instance within this class.</span></span> <span data-ttu-id="88d51-205">Вы можете добавить другие сценарии и поэкспериментировать с этой моделью.</span><span class="sxs-lookup"><span data-stu-id="88d51-205">You can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="88d51-206">Добавьте в класс `TestIrisData` следующий код:</span><span class="sxs-lookup"><span data-stu-id="88d51-206">Add the following code into the `TestIrisData` class:</span></span>

[!code-csharp[Test data](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#TestData)]

<span data-ttu-id="88d51-207">Чтобы узнать, к какому кластеру принадлежит указанный элемент, вернитесь к файлу *Program.cs* и добавьте следующий код в метод `Main`:</span><span class="sxs-lookup"><span data-stu-id="88d51-207">To find out the cluster to which the specified item belongs to, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict and output results](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#PredictionExample)]

<span data-ttu-id="88d51-208">Запустите программу, чтобы узнать, какой кластер содержит указанный экземпляр данных и квадрат расстояния от этого экземпляра до центроидов кластера.</span><span class="sxs-lookup"><span data-stu-id="88d51-208">Run the program to see which cluster contains the specified data instance and squared distances from that instance to the cluster centroids.</span></span> <span data-ttu-id="88d51-209">Результаты выполнения должны выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="88d51-209">Your results should be similar to the following:</span></span>

```text
Cluster: 2
Distances: 11.69127 0.02159119 25.59896
```

<span data-ttu-id="88d51-210">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="88d51-210">Congratulations!</span></span> <span data-ttu-id="88d51-211">Вы успешно создали модель машинного обучения для кластеризации ирисов и использовали ее для прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="88d51-211">You've now successfully built a machine learning model for iris clustering and used it to make predictions.</span></span> <span data-ttu-id="88d51-212">Исходный код для этого руководства можно найти в репозитории GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering).</span><span class="sxs-lookup"><span data-stu-id="88d51-212">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="88d51-213">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="88d51-213">Next steps</span></span>

<span data-ttu-id="88d51-214">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="88d51-214">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="88d51-215">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="88d51-215">Understand the problem</span></span>
> - <span data-ttu-id="88d51-216">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="88d51-216">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="88d51-217">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="88d51-217">Prepare the data</span></span>
> - <span data-ttu-id="88d51-218">Загрузка и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="88d51-218">Load and transform the data</span></span>
> - <span data-ttu-id="88d51-219">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="88d51-219">Choose a learning algorithm</span></span>
> - <span data-ttu-id="88d51-220">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="88d51-220">Train the model</span></span>
> - <span data-ttu-id="88d51-221">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="88d51-221">Use the model for predictions</span></span>

<span data-ttu-id="88d51-222">Извлеките наш репозиторий GitHub, чтобы продолжить обучение и получить дополнительные примеры.</span><span class="sxs-lookup"><span data-stu-id="88d51-222">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="88d51-223">Репозиторий GitHub dotnet/machinelearning</span><span class="sxs-lookup"><span data-stu-id="88d51-223">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
