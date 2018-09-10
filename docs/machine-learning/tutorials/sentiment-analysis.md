---
title: Использование ML.NET для анализа тональности методом двоичной классификации
description: На примере двоичной классификации с использованием ML.NET вы сможете узнать, как использовать прогнозирование тональности для выбора соответствующих действий.
ms.date: 06/04/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: dec44bf114472e19fdac131e0af6c13854957fe3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864778"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a><span data-ttu-id="93862-103">Руководство. Использование ML.NET для анализа тональности методом двоичной классификации</span><span class="sxs-lookup"><span data-stu-id="93862-103">Tutorial: Use ML.NET in a sentiment analysis binary classification scenario</span></span>

> [!NOTE]
> <span data-ttu-id="93862-104">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="93862-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="93862-105">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="93862-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="93862-106">В этом практическом руководстве демонстрируется создание классификатора тональности на основе ML.NET в консольном приложении .NET Core на языке C# с помощью Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="93862-106">This sample tutorial illustrates using ML.NET to create a sentiment classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="93862-107">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="93862-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="93862-108">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="93862-108">Understand the problem</span></span>
> * <span data-ttu-id="93862-109">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="93862-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="93862-110">подготавливать данные;</span><span class="sxs-lookup"><span data-stu-id="93862-110">Prepare your data</span></span>
> * <span data-ttu-id="93862-111">создавать конвейеры обучения;</span><span class="sxs-lookup"><span data-stu-id="93862-111">Create the learning pipeline</span></span>
> * <span data-ttu-id="93862-112">загружать классификатор;</span><span class="sxs-lookup"><span data-stu-id="93862-112">Load a classifier</span></span>
> * <span data-ttu-id="93862-113">обучить модель;</span><span class="sxs-lookup"><span data-stu-id="93862-113">Train the model</span></span>
> * <span data-ttu-id="93862-114">проводить оценку модели по другому набору данных;</span><span class="sxs-lookup"><span data-stu-id="93862-114">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="93862-115">прогнозировать результаты для тестовых данных с помощью модели.</span><span class="sxs-lookup"><span data-stu-id="93862-115">Predict the test data outcomes with the model</span></span>

## <a name="sentiment-analysis-sample-overview"></a><span data-ttu-id="93862-116">Обзор примера для анализа тональности</span><span class="sxs-lookup"><span data-stu-id="93862-116">Sentiment analysis sample overview</span></span>

<span data-ttu-id="93862-117">В качестве примера мы используем консольное приложение, которое использует ML.NET для обучения модели, которая классифицирует и прогнозирует тональность по двоичному признаку: положительная или отрицательная.</span><span class="sxs-lookup"><span data-stu-id="93862-117">The sample is a console app that uses ML.NET to train a model that classifies and predicts sentiment as either positive or negative.</span></span> <span data-ttu-id="93862-118">Также оно оценивает качество модели по второму набору данных.</span><span class="sxs-lookup"><span data-stu-id="93862-118">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="93862-119">Наборы данных для анализа тональности взяты из проекта WikiDetox.</span><span class="sxs-lookup"><span data-stu-id="93862-119">The sentiment datasets are from the WikiDetox project.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="93862-120">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="93862-120">Prerequisites</span></span>

* <span data-ttu-id="93862-121">[Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="93862-121">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="93862-122">[Файл с рабочими данными в формате строк, разделенных знаками табуляции из Wikipedia detox (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span><span class="sxs-lookup"><span data-stu-id="93862-122">The [Wikipedia detox line data tab separated file (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span>
* <span data-ttu-id="93862-123">[Файл с тестовыми данными в формате строк, разделенных знаками табуляции из Wikipedia detox (wikiPedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span><span class="sxs-lookup"><span data-stu-id="93862-123">The [Wikipedia detox line test tab separated file (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="93862-124">Рабочий процесс машинного обучения</span><span class="sxs-lookup"><span data-stu-id="93862-124">Machine learning workflow</span></span>

<span data-ttu-id="93862-125">В этом руководстве используется рабочий процесс машинного обучения, который определяет порядок выполнения действий в процессе.</span><span class="sxs-lookup"><span data-stu-id="93862-125">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="93862-126">Вот основные этапы этого рабочего процесса:</span><span class="sxs-lookup"><span data-stu-id="93862-126">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="93862-127">**определение проблемы**;</span><span class="sxs-lookup"><span data-stu-id="93862-127">**Understand the problem**</span></span>
2. <span data-ttu-id="93862-128">**прием данных**;</span><span class="sxs-lookup"><span data-stu-id="93862-128">**Ingest the data**</span></span>
3. <span data-ttu-id="93862-129">**предварительная обработка данных и проектирование признаков**;</span><span class="sxs-lookup"><span data-stu-id="93862-129">**Data preprocess and feature engineering**</span></span>
4. <span data-ttu-id="93862-130">**обучение модели и прогнозирование**;</span><span class="sxs-lookup"><span data-stu-id="93862-130">**Train and predict the model**</span></span>
5. <span data-ttu-id="93862-131">**оценка модели**;</span><span class="sxs-lookup"><span data-stu-id="93862-131">**Evaluate the model**</span></span>
6. <span data-ttu-id="93862-132">**ввод модели в эксплуатацию**.</span><span class="sxs-lookup"><span data-stu-id="93862-132">**Model operationalization**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="93862-133">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="93862-133">Understand the problem</span></span>

<span data-ttu-id="93862-134">Прежде всего необходимо понять суть проблемы, что позволит разбить ее на отдельные фрагменты для построения и обучения модели.</span><span class="sxs-lookup"><span data-stu-id="93862-134">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="93862-135">Разделение проблемы позволяет прогнозировать и оценивать результаты.</span><span class="sxs-lookup"><span data-stu-id="93862-135">Breaking the problem down you to predict and evaluate the results.</span></span>

<span data-ttu-id="93862-136">В этом руководстве ставится следующая задача: определение тональности поступившего на веб-сайт комментария, чтобы выполнить для него соответствующее действие.</span><span class="sxs-lookup"><span data-stu-id="93862-136">The problem for this tutorial is to understand incoming website comment sentiment to take the appropriate action.</span></span>

<span data-ttu-id="93862-137">Эта проблему можно разбить на следующие элементы: текст и значение тональности для данных, по которым вы будете обучать модель, и прогнозируемое значение тональности, которое вы будете оценивать и затем использовать в работе.</span><span class="sxs-lookup"><span data-stu-id="93862-137">You can break down the problem to the sentiment text and sentiment value for the data you want to train the model with, and a predicted sentiment value that you can evaluate and then use operationally.</span></span>

<span data-ttu-id="93862-138">После этого нужно дать **определение** тональности, которое поможет выбрать задачу машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="93862-138">You then need to **determine** the sentiment, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="93862-139">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="93862-139">Select the appropriate machine learning task</span></span>

<span data-ttu-id="93862-140">Для этой проблемы вам известны следующие факты.</span><span class="sxs-lookup"><span data-stu-id="93862-140">With this problem, you know the following facts:</span></span>

<span data-ttu-id="93862-141">Обучающие данные: комментарии на веб-сайте могут быть положительными или отрицательными (**тональность**).</span><span class="sxs-lookup"><span data-stu-id="93862-141">Training data: website comments can be positive or negative (**sentiment**).</span></span>
<span data-ttu-id="93862-142">Определите **тональность** для новых комментариев на веб-сайте, например для следующих примеров:</span><span class="sxs-lookup"><span data-stu-id="93862-142">Predict the **sentiment** of a new website comment, either positive or negative, such as in the following examples:</span></span>

* <span data-ttu-id="93862-143">Воздержитесь от добавления ерунды в Википедию.</span><span class="sxs-lookup"><span data-stu-id="93862-143">Please refrain from adding nonsense to Wikipedia.</span></span>
* <span data-ttu-id="93862-144">Он просто лучший, и в статье надо об этом сказать.</span><span class="sxs-lookup"><span data-stu-id="93862-144">He is the best, and the article should say that.</span></span>

<span data-ttu-id="93862-145">Для этого сценария лучше всего подходит задача классификации в машинном обучении.</span><span class="sxs-lookup"><span data-stu-id="93862-145">The classification machine learning task is best suited for this scenario.</span></span>

### <a name="about-the-classification-task"></a><span data-ttu-id="93862-146">Сведения о задаче классификации</span><span class="sxs-lookup"><span data-stu-id="93862-146">About the classification task</span></span>

<span data-ttu-id="93862-147">Классификацией называют задачу машинного обучения, которая использует данные для **определения** категории, типа или класса для некоторого элемента или ряда данных.</span><span class="sxs-lookup"><span data-stu-id="93862-147">Classification is a machine learning task that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="93862-148">Например, классификацию можно использовать для следующих действий:</span><span class="sxs-lookup"><span data-stu-id="93862-148">For example, you can use classification to:</span></span>

* <span data-ttu-id="93862-149">определение положительной или отрицательной тональности;</span><span class="sxs-lookup"><span data-stu-id="93862-149">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="93862-150">сортировка сообщений электронной почты на спам, нежелательную почту и нужные сообщения;</span><span class="sxs-lookup"><span data-stu-id="93862-150">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="93862-151">диагностика раковых заболеваний по лабораторным пробам, взятых у пациентов;</span><span class="sxs-lookup"><span data-stu-id="93862-151">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="93862-152">распределение клиентов по категориям с разной готовностью реагировать на рекламную акцию.</span><span class="sxs-lookup"><span data-stu-id="93862-152">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="93862-153">Задачи классификации обычно относятся к одному из следующих типов.</span><span class="sxs-lookup"><span data-stu-id="93862-153">Classification tasks are frequently one of the following types:</span></span>

* <span data-ttu-id="93862-154">Двоичная: A или B.</span><span class="sxs-lookup"><span data-stu-id="93862-154">Binary: either A or B.</span></span>
* <span data-ttu-id="93862-155">Многоклассовая: несколько категорий, которые прогнозируются по одной модели.</span><span class="sxs-lookup"><span data-stu-id="93862-155">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="93862-156">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="93862-156">Create a console application</span></span>

1. <span data-ttu-id="93862-157">Откройте Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="93862-157">Open Visual Studio 2017.</span></span> <span data-ttu-id="93862-158">Выберите **Файл** > **Создать** > **Проект** в меню.</span><span class="sxs-lookup"><span data-stu-id="93862-158">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="93862-159">В диалоговом окне **Новый проект** выберите узел **Visual C#**, а затем — узел **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="93862-159">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="93862-160">Выберите шаблон проекта **Консольное приложение (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="93862-160">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="93862-161">В текстовом поле **Имя** введите "Анализ тональности" и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="93862-161">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="93862-162">Создайте каталог с именем *Data* в папке проекта, чтобы сохранить в нем файлы с наборами данных:</span><span class="sxs-lookup"><span data-stu-id="93862-162">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="93862-163">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="93862-163">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="93862-164">Введите имя папки Data и нажмите клавишу "ВВОД".</span><span class="sxs-lookup"><span data-stu-id="93862-164">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="93862-165">Установите **пакет NuGet для Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="93862-165">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="93862-166">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="93862-166">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="93862-167">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="93862-167">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="93862-168">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="93862-168">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="93862-169">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="93862-169">Prepare your data</span></span>

1. <span data-ttu-id="93862-170">Скачайте файлы [WikiPedia-detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) и [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) с наборами данных и сохраните их в ранее созданную папку *Data*.</span><span class="sxs-lookup"><span data-stu-id="93862-170">Download the [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) and the [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="93862-171">Первый из этих наборов данных обучает модель машинного обучения, а второй позволяет оценить точность полученной модели.</span><span class="sxs-lookup"><span data-stu-id="93862-171">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="93862-172">В обозревателе решений щелкните правой кнопкой мыши каждый из файлов \*.tsv и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="93862-172">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="93862-173">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="93862-173">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="93862-174">Создание классов и определение путей</span><span class="sxs-lookup"><span data-stu-id="93862-174">Create classes and define paths</span></span>

<span data-ttu-id="93862-175">Добавьте следующие новые операторы `using` в начало файла *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="93862-175">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="93862-176">Также нужно создать три глобальных поля для хранения путей к недавно скачанным файлам:</span><span class="sxs-lookup"><span data-stu-id="93862-176">You need to create three global fields to hold the paths to the recently downloaded files:</span></span>

* <span data-ttu-id="93862-177">`_dataPath` содержит путь к набору данных, используемому для обучения модели;</span><span class="sxs-lookup"><span data-stu-id="93862-177">`_dataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="93862-178">`_testDataPath` содержит путь к набору данных, используемому для оценки модели;</span><span class="sxs-lookup"><span data-stu-id="93862-178">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="93862-179">`_modelPath` содержит путь, по которому сохраняется обученная модель.</span><span class="sxs-lookup"><span data-stu-id="93862-179">`_modelPath` has the path where the trained model is saved.</span></span>

<span data-ttu-id="93862-180">Добавьте следующий код в строку прямо перед методом `Main`, чтобы указать эти пути:</span><span class="sxs-lookup"><span data-stu-id="93862-180">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Declare file variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare variables to store data files")]

<span data-ttu-id="93862-181">Вам потребуется создать несколько классов для входных данных и прогнозов.</span><span class="sxs-lookup"><span data-stu-id="93862-181">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="93862-182">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="93862-182">Add a new class to your project:</span></span>

1. <span data-ttu-id="93862-183">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="93862-183">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="93862-184">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="93862-184">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="93862-185">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="93862-185">Then, select the **Add** button.</span></span>

    <span data-ttu-id="93862-186">Файл *SentimentData.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="93862-186">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="93862-187">Добавьте следующий оператор `using` в начало файла *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="93862-187">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

<span data-ttu-id="93862-188">Удалите из файла *SentimentData.cs* существующее определение класса и добавьте следующий код с двумя классами `SentimentData` и `SentimentPrediction`:</span><span class="sxs-lookup"><span data-stu-id="93862-188">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

<span data-ttu-id="93862-189">Класс `SentimentData` содержит входной набор данных. У него есть `float` (`Sentiment`) для значения тональности (положительная или отрицательное) и строковый параметр (`SentimentText`) для текста комментария.</span><span class="sxs-lookup"><span data-stu-id="93862-189">`SentimentData` is the input dataset class and has a `float` (`Sentiment`) that has a value for sentiment of either positive or negative, and a string for the comment (`SentimentText`).</span></span> <span data-ttu-id="93862-190">Для обоих полей указаны атрибуты `Column`.</span><span class="sxs-lookup"><span data-stu-id="93862-190">Both fields have `Column` attributes attached to them.</span></span> <span data-ttu-id="93862-191">Этот атрибут позволяет описать порядок полей в файле данных и указывает, какое поле является `Label`.</span><span class="sxs-lookup"><span data-stu-id="93862-191">This attribute describes the order of each field in the data file, and which is the `Label` field.</span></span> <span data-ttu-id="93862-192">Класс `SentimentPrediction` используется для прогнозирования после обучения модели.</span><span class="sxs-lookup"><span data-stu-id="93862-192">`SentimentPrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="93862-193">Он имеет один параметр типа boolean (`Sentiment`) и атрибут `PredictedLabel` `ColumnName`.</span><span class="sxs-lookup"><span data-stu-id="93862-193">It has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="93862-194">`Label` используется для создания и обучения модели, а также для оценки модели по второму набору данных.</span><span class="sxs-lookup"><span data-stu-id="93862-194">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="93862-195">`PredictedLabel` используется для прогнозирования и оценки.</span><span class="sxs-lookup"><span data-stu-id="93862-195">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="93862-196">Для оценки применяются входные обучающие данные, прогнозируемые значения и модель.</span><span class="sxs-lookup"><span data-stu-id="93862-196">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="93862-197">В файле *Program.cs* измените сигнатуру метода `Main`, заменив `void` значением `async Task`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="93862-197">In the *Program.cs* file, change the `Main` method signature by replacing `void` with `async Task`, as in the following example:</span></span>

```csharp
static async Task Main(string[] args) 
{

}
```

<span data-ttu-id="93862-198">Добавьте `async` в `Main` с типом возвращаемого значения <xref:System.Threading.Tasks.Task>, так как позднее модель сохраняется в ZIP-файл и программе необходимо дождаться завершения внешней задачи.</span><span class="sxs-lookup"><span data-stu-id="93862-198">You add `async` to `Main` with a <xref:System.Threading.Tasks.Task> return type because you're saving the model to a zip file later, and the program needs to wait until that external task completes.</span></span>

> [!NOTE]
> <span data-ttu-id="93862-199">Метод *async main* позволяет использовать `await` в методе `Main`.</span><span class="sxs-lookup"><span data-stu-id="93862-199">An *async main* method enables you to use `await` in your `Main` method.</span></span> <span data-ttu-id="93862-200">Дополнительные сведения см. в статье о методе [async main](../../../docs/csharp/programming-guide/main-and-command-args/index.md) в руководстве по программированию на C#.</span><span class="sxs-lookup"><span data-stu-id="93862-200">For more information, see the [async main](../../../docs/csharp/programming-guide/main-and-command-args/index.md) topic in the C# programming guide.</span></span>

<span data-ttu-id="93862-201">Замените строку `Console.WriteLine("Hello World!")` в методе `Main` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="93862-201">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Train your model")]

<span data-ttu-id="93862-202">Метод `Train` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="93862-202">The `Train` method executes the following tasks:</span></span>

* <span data-ttu-id="93862-203">загрузка или прием данных;</span><span class="sxs-lookup"><span data-stu-id="93862-203">Loads or ingests the data.</span></span>
* <span data-ttu-id="93862-204">предварительная обработка данных и присвоение признаков;</span><span class="sxs-lookup"><span data-stu-id="93862-204">Preprocesses and featurizes the data.</span></span>
* <span data-ttu-id="93862-205">обучение модели;</span><span class="sxs-lookup"><span data-stu-id="93862-205">Trains the model.</span></span>
* <span data-ttu-id="93862-206">прогноз тональности на основе тестовых данных.</span><span class="sxs-lookup"><span data-stu-id="93862-206">Predicts sentiment based on test data.</span></span>

<span data-ttu-id="93862-207">Создайте метод `Train` сразу после метода `Main`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="93862-207">Create the `Train` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static async Task<PredictionModel<SentimentData, SentimentPrediction>> Train()
{

}
```

## <a name="ingest-the-data"></a><span data-ttu-id="93862-208">Прием данных</span><span class="sxs-lookup"><span data-stu-id="93862-208">Ingest the data</span></span>

<span data-ttu-id="93862-209">Инициализируйте новый экземпляр <xref:Microsoft.ML.LearningPipeline>, который будет содержать процедуры загрузки, обработки данных, присвоения признаков и саму модель.</span><span class="sxs-lookup"><span data-stu-id="93862-209">Initialize a new instance of <xref:Microsoft.ML.LearningPipeline> that will include the data loading, data processing/featurization, and model.</span></span> <span data-ttu-id="93862-210">Добавьте следующий код в первую строку метода `Train`:</span><span class="sxs-lookup"><span data-stu-id="93862-210">Add the following code as the first line of the `Train` method:</span></span>

[!code-csharp[LearningPipeline](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Create a learning pipeline")]

<span data-ttu-id="93862-211">Объект <xref:Microsoft.ML.Data.TextLoader> является первой частью конвейера. Этот объект загружает файл с обучающими данными.</span><span class="sxs-lookup"><span data-stu-id="93862-211">The <xref:Microsoft.ML.Data.TextLoader> object is the first part of the pipeline, and loads the training file data.</span></span>

[!code-csharp[TextLoader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "Add a text loader to the pipeline")]

## <a name="data-preprocess-and-feature-engineering"></a><span data-ttu-id="93862-212">Предварительная обработка данных и проектирование признаков</span><span class="sxs-lookup"><span data-stu-id="93862-212">Data preprocess and feature engineering</span></span>

<span data-ttu-id="93862-213">Предварительная обработка и очистка данных — это очень важные задачи, которые нужно выполнить перед использованием набора данных для машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="93862-213">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="93862-214">Необработанные данные часто содержат много шума, недостаточно надежны и в них могут быть пропуски.</span><span class="sxs-lookup"><span data-stu-id="93862-214">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="93862-215">Использование данных напрямую без этих задач моделирования может дать неправильные результаты.</span><span class="sxs-lookup"><span data-stu-id="93862-215">Using data without these modeling tasks can produce misleading results.</span></span> <span data-ttu-id="93862-216">Конвейеры преобразования ML.NET позволяют создать пользовательский набор преобразований и применить их к данным перед началом обучения или проверки.</span><span class="sxs-lookup"><span data-stu-id="93862-216">ML.NET's transform pipelines allow you to compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="93862-217">Основной целью преобразования является присвоение признаков.</span><span class="sxs-lookup"><span data-stu-id="93862-217">The transforms' primary purpose is for data featurization.</span></span> <span data-ttu-id="93862-218">Конвейер преобразования хорош тем, что вам достаточно лишь преобразовать определение конвейера и сохранить его, чтобы автоматически применить к тестовым данным.</span><span class="sxs-lookup"><span data-stu-id="93862-218">A transform pipeline's advantage is that after transform pipeline definition, save the pipeline to apply it to test data.</span></span>

<span data-ttu-id="93862-219">Примените <xref:Microsoft.ML.Transforms.TextFeaturizer>, чтобы преобразовать столбец `SentimentText` в [числовой вектор](../resources/glossary.md#numerical-feature-vector), который называется `Features` в алгоритмах машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="93862-219">Apply a <xref:Microsoft.ML.Transforms.TextFeaturizer> to convert the `SentimentText` column into a [numeric vector](../resources/glossary.md#numerical-feature-vector) called `Features` used by the machine learning algorithm.</span></span> <span data-ttu-id="93862-220">Это этап предварительной обработки и присвоения признаков.</span><span class="sxs-lookup"><span data-stu-id="93862-220">This is the preprocessing/featurization step.</span></span> <span data-ttu-id="93862-221">Дополнительные компоненты из ML.NET могут дать более точные результаты для вашей модели.</span><span class="sxs-lookup"><span data-stu-id="93862-221">Using additional components available in ML.NET can enable better results with your model.</span></span> <span data-ttu-id="93862-222">Добавьте `TextFeaturizer` в конвейер на следующей строке кода:</span><span class="sxs-lookup"><span data-stu-id="93862-222">Add `TextFeaturizer` to the pipeline as the next line of code:</span></span>

[!code-csharp[TextFeaturizer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizer to the pipeline")]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="93862-223">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="93862-223">Choose a learning algorithm</span></span>

<span data-ttu-id="93862-224">Объект <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier> представляет собой средство обучения по дереву принятия решений, которое мы применим для нашего конвейера.</span><span class="sxs-lookup"><span data-stu-id="93862-224">The <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier> object is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="93862-225">Как и на шаге присвоения признаков, разные средства обучения из ML.NET и разные параметры для них позволяют получить разные результаты.</span><span class="sxs-lookup"><span data-stu-id="93862-225">Similar to the featurization step, trying out different learners available in ML.NET and changing their parameters leads to different results.</span></span> <span data-ttu-id="93862-226">Для настройки результатов можно установить [гиперпараметры](../resources/glossary.md#hyperparameter), например <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumTrees>, <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumLeaves> или <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.MinDocumentsInLeafs>.</span><span class="sxs-lookup"><span data-stu-id="93862-226">For tuning, you can set [hyperparameters](../resources/glossary.md#hyperparameter) like <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumTrees>, <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumLeaves>, and <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.MinDocumentsInLeafs>.</span></span> <span data-ttu-id="93862-227">Гиперпараметры устанавливаются до того, как на модель повлияет что-то другое, и различаются для разных моделей.</span><span class="sxs-lookup"><span data-stu-id="93862-227">These hyperparameters are set before anything affects the model and are model-specific.</span></span> <span data-ttu-id="93862-228">Они позволяют настроить дерево принятия решений, но большие значения могут отрицательно повлиять на производительность.</span><span class="sxs-lookup"><span data-stu-id="93862-228">They're used to tune the decision tree for performance, so larger values can negatively impact performance.</span></span>

<span data-ttu-id="93862-229">Добавьте следующий код в метод `Train`:</span><span class="sxs-lookup"><span data-stu-id="93862-229">Add the following code to the `Train` method:</span></span>

[!code-csharp[BinaryClassifier](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a fast binary tree classifier")]

## <a name="train-the-model"></a><span data-ttu-id="93862-230">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="93862-230">Train the model</span></span>

<span data-ttu-id="93862-231">Обучения модели <xref:Microsoft.ML.PredictionModel%602> выполняется по набору данных, который вы ранее скачали и преобразовали.</span><span class="sxs-lookup"><span data-stu-id="93862-231">You train the model, <xref:Microsoft.ML.PredictionModel%602>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="93862-232">`pipeline.Train<SentimentData, SentimentPrediction>()` обучает конвейер (загружает данные, обучает средство присвоения признаков и средство обучения).</span><span class="sxs-lookup"><span data-stu-id="93862-232">`pipeline.Train<SentimentData, SentimentPrediction>()` trains the pipeline (loads the data, trains the featurizer and learner).</span></span> <span data-ttu-id="93862-233">Эксперимент не выполняется, пока этот процесс не закончится.</span><span class="sxs-lookup"><span data-stu-id="93862-233">The experiment is not executed until this happens.</span></span>

<span data-ttu-id="93862-234">Добавьте следующий код в метод `Train`:</span><span class="sxs-lookup"><span data-stu-id="93862-234">Add the following code to the `Train` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="93862-235">Сохранение и возврат обученной модели для оценки</span><span class="sxs-lookup"><span data-stu-id="93862-235">Save and Return the model trained to use for evaluation</span></span>

<span data-ttu-id="93862-236">На этом этапе у вас есть модель, которую можно интегрировать с любыми существующими или новыми приложениями .NET.</span><span class="sxs-lookup"><span data-stu-id="93862-236">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="93862-237">Чтобы сохранить модель в ZIP-файл, добавьте следующий код в следующую строку в `Train`:</span><span class="sxs-lookup"><span data-stu-id="93862-237">To save your model to a .zip file before returning, add the following code to the next line in `Train`:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Save the model")]

<span data-ttu-id="93862-238">Выполните возврат модели в конце метода `Train`.</span><span class="sxs-lookup"><span data-stu-id="93862-238">Return the model at the end of the `Train` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="93862-239">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="93862-239">Evaluate the model</span></span>

<span data-ttu-id="93862-240">Итак, вы завершили создание и обучение модели, и теперь ее можно оценить по другому набору данных, чтобы проверить ее точность и качество прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="93862-240">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="93862-241">В методе `Evaluate` передается для оценки модель, созданная в `Train`.</span><span class="sxs-lookup"><span data-stu-id="93862-241">In the `Evaluate` method, the model created in `Train` is passed in to be evaluated.</span></span> <span data-ttu-id="93862-242">Создайте метод `Evaluate` сразу после метода `Train` как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="93862-242">Create the `Evaluate` method, just after `Train`, as in the following code:</span></span>

```csharp
public static void Evaluate(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

<span data-ttu-id="93862-243">Метод `Evaluate` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="93862-243">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="93862-244">загрузка тестового набора данных;</span><span class="sxs-lookup"><span data-stu-id="93862-244">Loads the test dataset.</span></span>
* <span data-ttu-id="93862-245">создание средства двоичной оценки;</span><span class="sxs-lookup"><span data-stu-id="93862-245">Creates the binary evaluator.</span></span>
* <span data-ttu-id="93862-246">оценка модели и создание метрик;</span><span class="sxs-lookup"><span data-stu-id="93862-246">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="93862-247">отображение метрик.</span><span class="sxs-lookup"><span data-stu-id="93862-247">Displays the metrics.</span></span>

<span data-ttu-id="93862-248">Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `Train`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="93862-248">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Call the Evaluate method")]

<span data-ttu-id="93862-249">Класс <xref:Microsoft.ML.Data.TextLoader> загружает новый тестовый набор данных с той же схемой.</span><span class="sxs-lookup"><span data-stu-id="93862-249">The <xref:Microsoft.ML.Data.TextLoader> class loads the new test dataset with the same schema.</span></span> <span data-ttu-id="93862-250">С помощью этого набора данных вы можете оценить модели для проверки ее качества.</span><span class="sxs-lookup"><span data-stu-id="93862-250">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="93862-251">Добавьте следующий код в метод `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="93862-251">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadText](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Load the test dataset")]

<span data-ttu-id="93862-252">Объект <xref:Microsoft.ML.Models.BinaryClassificationEvaluator> вычисляет метрики качества для `PredictionModel` на основе указанного набора данных.</span><span class="sxs-lookup"><span data-stu-id="93862-252">The <xref:Microsoft.ML.Models.BinaryClassificationEvaluator> object computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="93862-253">Чтобы просмотреть эти метрики, добавьте средство оценки в следующей строке метода `Evaluate`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="93862-253">To see those metrics, add the evaluator as the next line in the `Evaluate` method, with the following code:</span></span>

[!code-csharp[BinaryEvaluator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Create the binary evaluator")]

<span data-ttu-id="93862-254"><xref:Microsoft.ML.Models.BinaryClassificationMetrics> содержит общие метрики, вычисляемые с помощью средств оценки двоичной классификации.</span><span class="sxs-lookup"><span data-stu-id="93862-254">The <xref:Microsoft.ML.Models.BinaryClassificationMetrics> contains the overall metrics computed by binary classification evaluators.</span></span> <span data-ttu-id="93862-255">Чтобы отобразить их для оценки качества модели, сначала метрики необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="93862-255">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="93862-256">Добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="93862-256">Add the following code:</span></span>

[!code-csharp[CreateMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Evaluate the model and create metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="93862-257">Отображение метрик для проверки модели</span><span class="sxs-lookup"><span data-stu-id="93862-257">Displaying the metrics for model validation</span></span>

<span data-ttu-id="93862-258">Используйте следующий код для отображения метрик, передачи результатов и выполнения действий по ним:</span><span class="sxs-lookup"><span data-stu-id="93862-258">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Display selected metrics")]

## <a name="predict-the-test-data-outcomes-with-the-model"></a><span data-ttu-id="93862-259">Прогнозирование результатов для тестовых данных с помощью модели</span><span class="sxs-lookup"><span data-stu-id="93862-259">Predict the test data outcomes with the model</span></span>

<span data-ttu-id="93862-260">Создайте метод `Predict` сразу после метода `Evaluate`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="93862-260">Create the `Predict` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
public static void Predict(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

<span data-ttu-id="93862-261">Метод `Predict` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="93862-261">The `Predict` method executes the following tasks:</span></span>

* <span data-ttu-id="93862-262">создание тестовых данные;</span><span class="sxs-lookup"><span data-stu-id="93862-262">Creates test data.</span></span>
* <span data-ttu-id="93862-263">прогноз тональности на основе тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="93862-263">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="93862-264">объединение тестовых данных и прогнозов для создания отчетов;</span><span class="sxs-lookup"><span data-stu-id="93862-264">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="93862-265">отображение результатов прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="93862-265">Displays the predicted results.</span></span>

<span data-ttu-id="93862-266">Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `Evaluate`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="93862-266">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Call the Predict method")]

<span data-ttu-id="93862-267">Добавьте новые комментарии, чтобы проверить прогнозы обученной модели, в метод `Predict`:</span><span class="sxs-lookup"><span data-stu-id="93862-267">Add some comments to test the trained model's predictions in the `Predict` method:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for predictions")]

<span data-ttu-id="93862-268">Теперь у вас есть готовая модель, и ее можно использовать для прогнозирования положительной или отрицательной тональности по данным комментариев с помощью метода <xref:Microsoft.ML.PredictionModel.Predict%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="93862-268">Now that you have a model, you can use that to predict the positive or negative sentiment of the comment data using the <xref:Microsoft.ML.PredictionModel.Predict%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="93862-269">Чтобы получить прогноз, примените `Predict` для новых данных.</span><span class="sxs-lookup"><span data-stu-id="93862-269">To get a prediction, use `Predict` on new data.</span></span> <span data-ttu-id="93862-270">Обратите внимание, что входные данные имеют строковый формат, а модель выполняет присвоение признаков.</span><span class="sxs-lookup"><span data-stu-id="93862-270">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="93862-271">Конвейер синхронизируется во время обучения и прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="93862-271">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="93862-272">Вам не нужно писать для прогнозирования отдельный код предварительной обработки и присвоения признаков. Кроме того, этот API выполняет как пакетное, так и разовое прогнозирование.</span><span class="sxs-lookup"><span data-stu-id="93862-272">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create predictions of sentiments")]

### <a name="model-operationalization-prediction"></a><span data-ttu-id="93862-273">Ввод модели в эксплуатацию: прогнозирование</span><span class="sxs-lookup"><span data-stu-id="93862-273">Model operationalization: prediction</span></span>

<span data-ttu-id="93862-274">Отобразите `SentimentText` и соответствующие прогнозы тональности, чтобы поделиться результатами и выполнить соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="93862-274">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="93862-275">Этот этап называется вводом в эксплуатацию, после которого возвращаемые данные можно включить в операционные политики.</span><span class="sxs-lookup"><span data-stu-id="93862-275">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="93862-276">Создайте заголовок для результатов с помощью следующего кода <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="93862-276">Create a header for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction outputs")]

<span data-ttu-id="93862-277">Перед отображением результатов прогнозирования объедините данные о тональности с прогнозами, чтобы просмотреть исходные комментарии и прогнозы тональности.</span><span class="sxs-lookup"><span data-stu-id="93862-277">Before displaying the predicted results, combine the sentiment and prediction together to see the original comment with its predicted sentiment.</span></span> <span data-ttu-id="93862-278">В следующем коде для этого используется метод <xref:System.Linq.Enumerable.Zip%2A>, а после него нужно добавить следующий код:</span><span class="sxs-lookup"><span data-stu-id="93862-278">The following code uses the <xref:System.Linq.Enumerable.Zip%2A> method to make that happen, so add that code next:</span></span>

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#21 "Build the pairs of sentiment data and predictions")]

<span data-ttu-id="93862-279">Теперь, когда вы объединили в один класс `SentimentText` и `Sentiment`, можно отобразить результаты с помощью метода <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="93862-279">Now that you've combined the `SentimentText` and `Sentiment` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#22 "Display the predictions")]

<span data-ttu-id="93862-280">Так как выводимые имена элементов кортежа появились только в C# версии 7.1, а для этого проекта по умолчанию устанавливается версия языка C# 7.0, необходимо изменить это значение до C# 7.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="93862-280">Because inferred tuple element names are a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="93862-281">Для этого в **обозревателе решений** щелкните узел проекта правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="93862-281">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="93862-282">Откройте вкладку **Сборка** и нажмите на кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="93862-282">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="93862-283">В раскрывающемся списке выберите **C# 7.1** (или более позднюю версию).</span><span class="sxs-lookup"><span data-stu-id="93862-283">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="93862-284">Нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="93862-284">Select the **OK** button.</span></span>

## <a name="results"></a><span data-ttu-id="93862-285">Результаты</span><span class="sxs-lookup"><span data-stu-id="93862-285">Results</span></span>

<span data-ttu-id="93862-286">Результаты выполнения должны выглядеть примерно так, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="93862-286">Your results should be similar to the following.</span></span> <span data-ttu-id="93862-287">В процессе работы конвейер выводит сообщения.</span><span class="sxs-lookup"><span data-stu-id="93862-287">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="93862-288">Вы можете видеть предупреждения или обработанные сообщения.</span><span class="sxs-lookup"><span data-stu-id="93862-288">You may see warnings, or processing messages.</span></span> <span data-ttu-id="93862-289">Для удобства они удалены из следующих результатов.</span><span class="sxs-lookup"><span data-stu-id="93862-289">These have been removed from the following results for clarity.</span></span>

```

PredictionModel quality metrics evaluation
------------------------------------------
Accuracy: 66.67%
Auc: 94.44%
F1Score: 75.00%

Sentiment Predictions
---------------------
Sentiment: Please refrain from adding nonsense to Wikipedia. | Prediction: Negative
Sentiment: He is the best, and the article should say that. | Prediction: Positive

```

<span data-ttu-id="93862-290">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="93862-290">Congratulations!</span></span> <span data-ttu-id="93862-291">Вы успешно создали модель машинного обучения для классификации и прогнозирования тональности сообщений.</span><span class="sxs-lookup"><span data-stu-id="93862-291">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span> <span data-ttu-id="93862-292">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="93862-292">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="93862-293">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="93862-293">Next steps</span></span>

<span data-ttu-id="93862-294">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="93862-294">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="93862-295">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="93862-295">Understand the problem</span></span>
> * <span data-ttu-id="93862-296">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="93862-296">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="93862-297">подготавливать данные;</span><span class="sxs-lookup"><span data-stu-id="93862-297">Prepare your data</span></span>
> * <span data-ttu-id="93862-298">создавать конвейеры обучения;</span><span class="sxs-lookup"><span data-stu-id="93862-298">Create the learning pipeline</span></span>
> * <span data-ttu-id="93862-299">загружать классификатор;</span><span class="sxs-lookup"><span data-stu-id="93862-299">Load a classifier</span></span>
> * <span data-ttu-id="93862-300">обучить модель;</span><span class="sxs-lookup"><span data-stu-id="93862-300">Train the model</span></span>
> * <span data-ttu-id="93862-301">проводить оценку модели по другому набору данных;</span><span class="sxs-lookup"><span data-stu-id="93862-301">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="93862-302">прогнозировать результаты для тестовых данных с помощью модели.</span><span class="sxs-lookup"><span data-stu-id="93862-302">Predict the test data outcomes with the model</span></span>

<span data-ttu-id="93862-303">Переходите к следующему руководству:</span><span class="sxs-lookup"><span data-stu-id="93862-303">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="93862-304">Прогнозирование платы за такси</span><span class="sxs-lookup"><span data-stu-id="93862-304">Taxi Fare Predictor</span></span>](taxi-fare.md)
