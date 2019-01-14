---
title: Кластеризация цветков ириса с помощью задачи машинного обучения по кластеризации — ML.NET
description: Сведения об использовании ML.NET при кластеризации
author: pkulikov
ms.author: johalex
ms.date: 01/11/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: ab888a2cd9469d5ce0131ba2b17f7c134cf2855c
ms.sourcegitcommit: 81bd16c7435a8c9183d2a7e878a2a5eff7d04584
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2019
ms.locfileid: "54249077"
---
# <a name="tutorial-cluster-iris-flowers-using-a-clustering-learner-with-mlnet"></a><span data-ttu-id="acfce-103">Учебник. Кластеризация цветков ириса с помощью задачи машинного обучения по кластеризации в ML.NET</span><span class="sxs-lookup"><span data-stu-id="acfce-103">Tutorial: Cluster iris flowers using a clustering learner with ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="acfce-104">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="acfce-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="acfce-105">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="acfce-105">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="acfce-106">В этом руководстве описано, как с помощью ML.NET создать [модель кластеризации](../resources/tasks.md#clustering) для [набора данных ирисов](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span><span class="sxs-lookup"><span data-stu-id="acfce-106">This tutorial illustrates how to use ML.NET to build a [clustering model](../resources/tasks.md#clustering) for the [iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span></span>

<span data-ttu-id="acfce-107">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="acfce-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="acfce-108">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="acfce-108">Understand the problem</span></span>
> - <span data-ttu-id="acfce-109">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="acfce-109">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="acfce-110">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="acfce-110">Prepare the data</span></span>
> - <span data-ttu-id="acfce-111">Загрузка и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="acfce-111">Load and transform the data</span></span>
> - <span data-ttu-id="acfce-112">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="acfce-112">Choose a learning algorithm</span></span>
> - <span data-ttu-id="acfce-113">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="acfce-113">Train the model</span></span>
> - <span data-ttu-id="acfce-114">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="acfce-114">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="acfce-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="acfce-115">Prerequisites</span></span>

- <span data-ttu-id="acfce-116">[Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="acfce-116">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="acfce-117">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="acfce-117">Understand the problem</span></span>

<span data-ttu-id="acfce-118">Задача — разделить ирисы на группы в зависимости от признаков цветка.</span><span class="sxs-lookup"><span data-stu-id="acfce-118">This problem is about dividing the set of iris flowers in different groups based on the flower features.</span></span> <span data-ttu-id="acfce-119">Эти признаки — длина и ширина чашелистика и длина и ширина лепестка.</span><span class="sxs-lookup"><span data-stu-id="acfce-119">Those features are the length and width of a sepal and the length and width of a petal.</span></span> <span data-ttu-id="acfce-120">В этом руководстве предполагается, что тип каждого цветка неизвестен.</span><span class="sxs-lookup"><span data-stu-id="acfce-120">For this tutorial, assume that the type of each flower is unknown.</span></span> <span data-ttu-id="acfce-121">Вы научитесь структурировать набор данных по признакам и предсказывать, как экземпляр данных будет вписываться в эту структуру.</span><span class="sxs-lookup"><span data-stu-id="acfce-121">You want to learn the structure of a data set from the features and predict how a data instance fits this structure.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="acfce-122">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="acfce-122">Select the appropriate machine learning task</span></span>

<span data-ttu-id="acfce-123">Поскольку вы не знаете, к какой группе принадлежит каждый цветок, вы выбираете задачу [неконтролируемого машинного обучения](../resources/glossary.md#unsupervised-machine-learning).</span><span class="sxs-lookup"><span data-stu-id="acfce-123">As you don't know to which group each flower belongs to, you choose the [unsupervised machine learning](../resources/glossary.md#unsupervised-machine-learning) task.</span></span> <span data-ttu-id="acfce-124">Чтобы разделить набор данных на группы таким образом, чтобы элементы одной группы больше походили друг на друга, чем на элементы из других групп, используйте задачу машинного обучения по [кластеризации](../resources/tasks.md#clustering).</span><span class="sxs-lookup"><span data-stu-id="acfce-124">To divide a data set in groups in such a way that elements in the same group are more similar to each other than to those in other groups, use a [clustering](../resources/tasks.md#clustering) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="acfce-125">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="acfce-125">Create a console application</span></span>

1. <span data-ttu-id="acfce-126">Откройте Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="acfce-126">Open Visual Studio 2017.</span></span> <span data-ttu-id="acfce-127">Выберите **Файл** > **Создать** > **Проект** в меню.</span><span class="sxs-lookup"><span data-stu-id="acfce-127">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="acfce-128">В диалоговом окне **Новый проект** выберите узел **Visual C#**, а затем — узел **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="acfce-128">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="acfce-129">Выберите шаблон проекта **Консольное приложение (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="acfce-129">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="acfce-130">В текстовом поле **Имя** введите "IrisFlowerClustering", а затем нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="acfce-130">In the **Name** text box, type "IrisFlowerClustering" and then select the **OK** button.</span></span>

1. <span data-ttu-id="acfce-131">Создайте каталог с именем *Data* в папке проекта, чтобы хранить в нем наборы данных и файлы модели:</span><span class="sxs-lookup"><span data-stu-id="acfce-131">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="acfce-132">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="acfce-132">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="acfce-133">Введите имя папки Data и нажмите клавишу "ВВОД".</span><span class="sxs-lookup"><span data-stu-id="acfce-133">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="acfce-134">Установите пакет NuGet для **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="acfce-134">Install the **Microsoft.ML** NuGet package:</span></span>

    <span data-ttu-id="acfce-135">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="acfce-135">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="acfce-136">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку **Обзор**, выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="acfce-136">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="acfce-137">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="acfce-137">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="acfce-138">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="acfce-138">Prepare the data</span></span>

1. <span data-ttu-id="acfce-139">Скачайте набор данных [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) и сохраните его в папке *Data*, созданной на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="acfce-139">Download the [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) data set and save it to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="acfce-140">Дополнительные сведения о наборе данных ирисов см. на странице Википедии [Ирисы Фишера](https://en.wikipedia.org/wiki/Iris_flower_data_set) и на странице [Набор данных ирисов](https://archive.ics.uci.edu/ml/datasets/Iris), который является источником набора данных.</span><span class="sxs-lookup"><span data-stu-id="acfce-140">For more information about the iris data set, see the [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia page and the [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris) page, which is the source of the data set.</span></span>

1. <span data-ttu-id="acfce-141">В **Обозревателе решений** щелкните правой кнопкой мыши файл *iris.data* и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="acfce-141">In **Solution Explorer**, right-click the *iris.data* file and select **Properties**.</span></span> <span data-ttu-id="acfce-142">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="acfce-142">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="acfce-143">Файл *Iris.data* содержит пять столбцов со следующими данными:</span><span class="sxs-lookup"><span data-stu-id="acfce-143">The *iris.data* file contains five columns that represent:</span></span>

- <span data-ttu-id="acfce-144">длина чашелистика в см;</span><span class="sxs-lookup"><span data-stu-id="acfce-144">sepal length in centimetres</span></span>
- <span data-ttu-id="acfce-145">ширина чашелистика в см;</span><span class="sxs-lookup"><span data-stu-id="acfce-145">sepal width in centimetres</span></span>
- <span data-ttu-id="acfce-146">длина лепестка в см;</span><span class="sxs-lookup"><span data-stu-id="acfce-146">petal length in centimetres</span></span>
- <span data-ttu-id="acfce-147">ширина лепестка в см;</span><span class="sxs-lookup"><span data-stu-id="acfce-147">petal width in centimetres</span></span>
- <span data-ttu-id="acfce-148">тип ириса.</span><span class="sxs-lookup"><span data-stu-id="acfce-148">type of iris flower</span></span>

<span data-ttu-id="acfce-149">В этом примере кластеризации мы не будем учитывать последний столбец.</span><span class="sxs-lookup"><span data-stu-id="acfce-149">For the sake of the clustering example, this tutorial ignores the last column.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="acfce-150">Создание классов данных</span><span class="sxs-lookup"><span data-stu-id="acfce-150">Create data classes</span></span>

<span data-ttu-id="acfce-151">Создайте классы для входных данных и прогнозов:</span><span class="sxs-lookup"><span data-stu-id="acfce-151">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="acfce-152">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="acfce-152">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="acfce-153">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *IrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="acfce-153">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *IrisData.cs*.</span></span> <span data-ttu-id="acfce-154">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="acfce-154">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="acfce-155">Добавьте следующую директиву `using` в новый файл:</span><span class="sxs-lookup"><span data-stu-id="acfce-155">Add the following `using` directive to the new file:</span></span>

   [!code-csharp[Add necessary usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#Usings)]

<span data-ttu-id="acfce-156">Удалите из файла *IrisData.cs* существующее определение класса и добавьте следующий код, который определяет классы `IrisData` и `ClusterPrediction`:</span><span class="sxs-lookup"><span data-stu-id="acfce-156">Remove the existing class definition and add the following code, which defines the classes `IrisData` and `ClusterPrediction`, to the *IrisData.cs* file:</span></span>

[!code-csharp[Define data classes](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#ClassDefinitions)]

<span data-ttu-id="acfce-157">Класс `IrisData` содержит входные данные и определения для каждого признака в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="acfce-157">`IrisData` is the input data class and has definitions for each feature from the data set.</span></span> <span data-ttu-id="acfce-158">Используйте атрибут [Column](xref:Microsoft.ML.Data.ColumnAttribute), чтобы указать индексы исходных столбцов в файле набора данных.</span><span class="sxs-lookup"><span data-stu-id="acfce-158">Use the [Column](xref:Microsoft.ML.Data.ColumnAttribute) attribute to specify the indices of the source columns in the data set file.</span></span>

<span data-ttu-id="acfce-159">Класс `ClusterPrediction` представляет выходные данные модели кластеризации, примененные к экземпляру `IrisData`.</span><span class="sxs-lookup"><span data-stu-id="acfce-159">The `ClusterPrediction` class represents the output of the clustering model applied to an `IrisData` instance.</span></span> <span data-ttu-id="acfce-160">Используйте атрибут [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute), чтобы привязать поля `PredictedClusterId` и `Distances` к столбцам **PredictedLabel** и **Score** соответственно.</span><span class="sxs-lookup"><span data-stu-id="acfce-160">Use the [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute to bind the `PredictedClusterId` and `Distances` fields to the **PredictedLabel** and **Score** columns respectively.</span></span> <span data-ttu-id="acfce-161">В случае задачи кластеризации эти столбцы означают следующее:</span><span class="sxs-lookup"><span data-stu-id="acfce-161">In case of the clustering task those columns have the following meaning:</span></span>

- <span data-ttu-id="acfce-162">Столбец **PredictedLabel** содержит идентификатор прогнозируемого кластера.</span><span class="sxs-lookup"><span data-stu-id="acfce-162">**PredictedLabel** column contains the ID of the predicted cluster.</span></span>
- <span data-ttu-id="acfce-163">Столбец **Score** содержит массив с квадратом Евклидовых расстояний до центроидов кластера.</span><span class="sxs-lookup"><span data-stu-id="acfce-163">**Score** column contains an array with squared Euclidean distances to the cluster centroids.</span></span> <span data-ttu-id="acfce-164">Длина массива равна числу кластеров.</span><span class="sxs-lookup"><span data-stu-id="acfce-164">The array length is equal to the number of clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="acfce-165">Используйте тип `float` для представления значений с плавающей запятой в классах данных ввода и прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="acfce-165">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="acfce-166">Определение путей к данным и модели</span><span class="sxs-lookup"><span data-stu-id="acfce-166">Define data and model paths</span></span>

<span data-ttu-id="acfce-167">Вернитесь к файлу *Program.cs* и добавьте два поля, которые будут содержать пути к файлу с наборами данных и к файлу для сохранения модели.</span><span class="sxs-lookup"><span data-stu-id="acfce-167">Go back to the *Program.cs* file and add two fields to hold the paths to the data set file and to the file to save the model:</span></span>

- <span data-ttu-id="acfce-168">`_dataPath` содержит путь к файлу с набором данных, используемым для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="acfce-168">`_dataPath` contains the path to the file with the data set used to train the model.</span></span>
- <span data-ttu-id="acfce-169">`_modelPath` содержит путь к файлу для сохранения обучаемой модели.</span><span class="sxs-lookup"><span data-stu-id="acfce-169">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="acfce-170">Добавьте прямо перед методом `Main` следующий код, чтобы указать эти пути.</span><span class="sxs-lookup"><span data-stu-id="acfce-170">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Initialize paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Paths)]

<span data-ttu-id="acfce-171">Чтобы этот код компилировался, добавьте следующие директивы `using` вверху файла *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="acfce-171">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add usings for paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#UsingsForPaths)]

## <a name="create-ml-context"></a><span data-ttu-id="acfce-172">Создание контекста машинного обучения ML</span><span class="sxs-lookup"><span data-stu-id="acfce-172">Create ML context</span></span>

<span data-ttu-id="acfce-173">Добавьте дополнительные директивы `using` в начало файла *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="acfce-173">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[Add Microsoft.ML usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#MLUsings)]

<span data-ttu-id="acfce-174">В методе `Main` замените строку `Console.WriteLine("Hello World!");` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="acfce-174">In the `Main` method, replace the `Console.WriteLine("Hello World!");` line with the following code:</span></span>

[!code-csharp[Create ML context](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateContext)]

<span data-ttu-id="acfce-175">Класс <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> представляет среду машинного обучения и предоставляет механизмы для ведения журнала и точек входа для загрузки данных, обучения модели, прогнозирования и других задач.</span><span class="sxs-lookup"><span data-stu-id="acfce-175">The <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> class represents the machine learning environment and provides mechanisms for logging and entry points for data loading, model training, prediction, and other tasks.</span></span> <span data-ttu-id="acfce-176">Концептуально это сопоставимо с использованием `DbContext` в Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="acfce-176">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span>

## <a name="setup-data-loading"></a><span data-ttu-id="acfce-177">Настройка загрузки данных</span><span class="sxs-lookup"><span data-stu-id="acfce-177">Setup data loading</span></span>

<span data-ttu-id="acfce-178">Добавьте следующий код к методу `Main` для настройки способа загрузки данных:</span><span class="sxs-lookup"><span data-stu-id="acfce-178">Add the following code to the `Main` method to setup the way to load data:</span></span>

[!code-csharp[Create text loader](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SetupTextLoader)]

<span data-ttu-id="acfce-179">Обратите внимание, что имена столбцов и индексы соответствуют схеме, определяемой классом `IrisData`.</span><span class="sxs-lookup"><span data-stu-id="acfce-179">Note that the column names and indices match the schema defined by the `IrisData` class.</span></span> <span data-ttu-id="acfce-180">Значение <xref:Microsoft.ML.Data.DataKind.R4?displayProperty=nameWithType> задает тип `float`.</span><span class="sxs-lookup"><span data-stu-id="acfce-180">The <xref:Microsoft.ML.Data.DataKind.R4?displayProperty=nameWithType> value specifies the `float` type.</span></span>

<span data-ttu-id="acfce-181">Используйте созданный экземпляр <xref:Microsoft.ML.Data.TextLoader>, чтобы создать экземпляр <xref:Microsoft.ML.Data.IDataView>, который представляет источник данных для набора данных для обучения:</span><span class="sxs-lookup"><span data-stu-id="acfce-181">Use instantiated <xref:Microsoft.ML.Data.TextLoader> instance to create an <xref:Microsoft.ML.Data.IDataView> instance, which represents the data source for the training data set:</span></span>

[!code-csharp[Create IDataView](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateDataView)]

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="acfce-182">Создание конвейера обучения</span><span class="sxs-lookup"><span data-stu-id="acfce-182">Create a learning pipeline</span></span>

<span data-ttu-id="acfce-183">В этом руководстве настройка конвейера обучения задач кластеризации состоит из следующих двух шагов:</span><span class="sxs-lookup"><span data-stu-id="acfce-183">For this tutorial, the learning pipeline of the clustering task comprises two following steps:</span></span>

- <span data-ttu-id="acfce-184">объедините загруженные столбцы в один столбец **Функции**, который используется тренером кластеризации;</span><span class="sxs-lookup"><span data-stu-id="acfce-184">concatenate loaded columns into one **Features** column, which is used by a clustering trainer;</span></span>
- <span data-ttu-id="acfce-185">используйте тренер <xref:Microsoft.ML.Trainers.KMeans.KMeansPlusPlusTrainer> для обучения модели с помощью алгоритма кластеризации k-means++.</span><span class="sxs-lookup"><span data-stu-id="acfce-185">use a <xref:Microsoft.ML.Trainers.KMeans.KMeansPlusPlusTrainer> trainer to train the model using the k-means++ clustering algorithm.</span></span>

<span data-ttu-id="acfce-186">Добавьте следующий код в метод `Main`:</span><span class="sxs-lookup"><span data-stu-id="acfce-186">Add the following code to the `Main` method:</span></span>

[!code-csharp[Create pipeline](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreatePipeline)]

<span data-ttu-id="acfce-187">В этом коде указано, что набор данных нужно разделить на три кластера.</span><span class="sxs-lookup"><span data-stu-id="acfce-187">The code specifies that the data set should be split in three clusters.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="acfce-188">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="acfce-188">Train the model</span></span>

<span data-ttu-id="acfce-189">Выполнив действия в предыдущих разделах, вы подготовили конвейер для обучения, но пока ничего не было сделано.</span><span class="sxs-lookup"><span data-stu-id="acfce-189">The steps added in the preceding sections prepared the pipeline for training, however, none have been executed.</span></span> <span data-ttu-id="acfce-190">Добавьте следующую строку к методу `Main`, чтобы выполнить загрузку данных и обучение модели:</span><span class="sxs-lookup"><span data-stu-id="acfce-190">Add the following line to the `Main` method to perform data loading and model training:</span></span>

[!code-csharp[Train the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#TrainModel)]

### <a name="save-the-model"></a><span data-ttu-id="acfce-191">Сохранение модели</span><span class="sxs-lookup"><span data-stu-id="acfce-191">Save the model</span></span>

<span data-ttu-id="acfce-192">На этом этапе у вас есть модель, которую можно интегрировать с любыми существующими или новыми приложениями .NET.</span><span class="sxs-lookup"><span data-stu-id="acfce-192">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="acfce-193">Чтобы сохранить модель в ZIP-файл, добавьте к методу `Main` следующий код:</span><span class="sxs-lookup"><span data-stu-id="acfce-193">To save your model to a .zip file, add the following code to the `Main` method:</span></span>

[!code-csharp[Save the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SaveModel)]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="acfce-194">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="acfce-194">Use the model for predictions</span></span>

<span data-ttu-id="acfce-195">Чтобы получить прогноз, используйте класс <xref:Microsoft.ML.PredictionEngine%602>, который принимает экземпляры входного типа через конвейер преобразователя и создает экземпляры выходного типа.</span><span class="sxs-lookup"><span data-stu-id="acfce-195">To make predictions, use the <xref:Microsoft.ML.PredictionEngine%602> class that takes instances of the input type through the transformer pipeline and produces instances of the output type.</span></span> <span data-ttu-id="acfce-196">Добавьте следующую строку к методу `Main` для создания экземпляра этого класса:</span><span class="sxs-lookup"><span data-stu-id="acfce-196">Add the following line to the `Main` method to create an instance of that class:</span></span>

[!code-csharp[Create predictor](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Predictor)]

<span data-ttu-id="acfce-197">Создание класса `TestIrisData` для размещения тестовых экземпляров данных:</span><span class="sxs-lookup"><span data-stu-id="acfce-197">Create the `TestIrisData` class to house test data instances:</span></span>

1. <span data-ttu-id="acfce-198">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="acfce-198">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="acfce-199">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *TestIrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="acfce-199">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestIrisData.cs*.</span></span> <span data-ttu-id="acfce-200">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="acfce-200">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="acfce-201">Измените класс, чтобы он был статическим, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="acfce-201">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[Make class static](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#Static)]

<span data-ttu-id="acfce-202">В этом руководстве представлен один экземпляр данных ирисов в этом классе.</span><span class="sxs-lookup"><span data-stu-id="acfce-202">This tutorial introduces one iris data instance within this class.</span></span> <span data-ttu-id="acfce-203">Вы можете добавить другие сценарии и поэкспериментировать с этой моделью.</span><span class="sxs-lookup"><span data-stu-id="acfce-203">You can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="acfce-204">Добавьте в класс `TestIrisData` следующий код:</span><span class="sxs-lookup"><span data-stu-id="acfce-204">Add the following code into the `TestIrisData` class:</span></span>

[!code-csharp[Test data](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#TestData)]

<span data-ttu-id="acfce-205">Чтобы узнать, к какому кластеру принадлежит указанный элемент, вернитесь к файлу *Program.cs* и добавьте следующий код в метод `Main`:</span><span class="sxs-lookup"><span data-stu-id="acfce-205">To find out the cluster to which the specified item belongs to, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict and output results](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#PredictionExample)]

<span data-ttu-id="acfce-206">Запустите программу, чтобы узнать, какой кластер содержит указанный экземпляр данных и квадрат расстояния от этого экземпляра до центроидов кластера.</span><span class="sxs-lookup"><span data-stu-id="acfce-206">Run the program to see which cluster contains the specified data instance and squared distances from that instance to the cluster centroids.</span></span> <span data-ttu-id="acfce-207">Результаты выполнения должны выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="acfce-207">Your results should be similar to the following:</span></span>

```text
Cluster: 2
Distances: 11.69127 0.02159119 25.59896
```

<span data-ttu-id="acfce-208">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="acfce-208">Congratulations!</span></span> <span data-ttu-id="acfce-209">Вы успешно создали модель машинного обучения для кластеризации ирисов и использовали ее для прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="acfce-209">You've now successfully built a machine learning model for iris clustering and used it to make predictions.</span></span> <span data-ttu-id="acfce-210">Исходный код для этого руководства можно найти в репозитории GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering).</span><span class="sxs-lookup"><span data-stu-id="acfce-210">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="acfce-211">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="acfce-211">Next steps</span></span>

<span data-ttu-id="acfce-212">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="acfce-212">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="acfce-213">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="acfce-213">Understand the problem</span></span>
> - <span data-ttu-id="acfce-214">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="acfce-214">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="acfce-215">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="acfce-215">Prepare the data</span></span>
> - <span data-ttu-id="acfce-216">Загрузка и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="acfce-216">Load and transform the data</span></span>
> - <span data-ttu-id="acfce-217">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="acfce-217">Choose a learning algorithm</span></span>
> - <span data-ttu-id="acfce-218">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="acfce-218">Train the model</span></span>
> - <span data-ttu-id="acfce-219">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="acfce-219">Use the model for predictions</span></span>

<span data-ttu-id="acfce-220">Извлеките наш репозиторий GitHub, чтобы продолжить обучение и получить дополнительные примеры.</span><span class="sxs-lookup"><span data-stu-id="acfce-220">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="acfce-221">Репозиторий GitHub dotnet/machinelearning</span><span class="sxs-lookup"><span data-stu-id="acfce-221">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
