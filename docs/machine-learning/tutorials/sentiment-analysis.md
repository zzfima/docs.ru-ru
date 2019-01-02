---
title: Использование ML.NET для анализа тональности методом двоичной классификации
description: На примере двоичной классификации с использованием ML.NET вы сможете узнать, как использовать прогнозирование тональности для выбора соответствующих действий.
ms.date: 12/20/2018
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 90f3b79226b16ac1ea4cbbe49ce07d95a138323b
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2018
ms.locfileid: "53779144"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a><span data-ttu-id="f4842-103">Учебник. Использование ML.NET для анализа тональности методом двоичной классификации</span><span class="sxs-lookup"><span data-stu-id="f4842-103">Tutorial: Use ML.NET in a sentiment analysis binary classification scenario</span></span>

> [!NOTE]
> <span data-ttu-id="f4842-104">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="f4842-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="f4842-105">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="f4842-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="f4842-106">В этом практическом руководстве демонстрируется создание классификатора тональности на основе ML.NET в консольном приложении .NET Core на языке C# с помощью Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="f4842-106">This sample tutorial illustrates using ML.NET to create a sentiment classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="f4842-107">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="f4842-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="f4842-108">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="f4842-108">Understand the problem</span></span>
> * <span data-ttu-id="f4842-109">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="f4842-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="f4842-110">подготавливать данные;</span><span class="sxs-lookup"><span data-stu-id="f4842-110">Prepare your data</span></span>
> * <span data-ttu-id="f4842-111">создавать конвейеры обучения;</span><span class="sxs-lookup"><span data-stu-id="f4842-111">Create the learning pipeline</span></span>
> * <span data-ttu-id="f4842-112">загружать классификатор;</span><span class="sxs-lookup"><span data-stu-id="f4842-112">Load a classifier</span></span>
> * <span data-ttu-id="f4842-113">обучить модель;</span><span class="sxs-lookup"><span data-stu-id="f4842-113">Train the model</span></span>
> * <span data-ttu-id="f4842-114">проводить оценку модели по другому набору данных;</span><span class="sxs-lookup"><span data-stu-id="f4842-114">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="f4842-115">прогнозировать единый экземпляр результатов тестовых данных с помощью модели;</span><span class="sxs-lookup"><span data-stu-id="f4842-115">Predict a single instance of test data outcome with the model</span></span>
> * <span data-ttu-id="f4842-116">прогнозировать результаты для тестовых данных с помощью загруженной модели.</span><span class="sxs-lookup"><span data-stu-id="f4842-116">Predict the test data outcomes with a loaded model</span></span>

## <a name="sentiment-analysis-sample-overview"></a><span data-ttu-id="f4842-117">Обзор примера для анализа тональности</span><span class="sxs-lookup"><span data-stu-id="f4842-117">Sentiment analysis sample overview</span></span>

<span data-ttu-id="f4842-118">В качестве примера мы используем консольное приложение, которое использует ML.NET для обучения модели, которая классифицирует и прогнозирует тональность по двоичному признаку: положительная или отрицательная.</span><span class="sxs-lookup"><span data-stu-id="f4842-118">The sample is a console app that uses ML.NET to train a model that classifies and predicts sentiment as either positive or negative.</span></span> <span data-ttu-id="f4842-119">Также оно оценивает качество модели по второму набору данных.</span><span class="sxs-lookup"><span data-stu-id="f4842-119">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="f4842-120">Наборы данных для анализа тональности взяты из проекта WikiDetox.</span><span class="sxs-lookup"><span data-stu-id="f4842-120">The sentiment datasets are from the WikiDetox project.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f4842-121">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f4842-121">Prerequisites</span></span>

* <span data-ttu-id="f4842-122">[Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="f4842-122">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="f4842-123">[Файл с рабочими данными в формате строк, разделенных знаками табуляции из Wikipedia detox (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span><span class="sxs-lookup"><span data-stu-id="f4842-123">The [Wikipedia detox line data tab separated file (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span>
* <span data-ttu-id="f4842-124">[Файл с тестовыми данными в формате строк, разделенных знаками табуляции из Wikipedia detox (wikiPedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span><span class="sxs-lookup"><span data-stu-id="f4842-124">The [Wikipedia detox line test tab separated file (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="f4842-125">Рабочий процесс машинного обучения</span><span class="sxs-lookup"><span data-stu-id="f4842-125">Machine learning workflow</span></span>

<span data-ttu-id="f4842-126">В этом руководстве используется рабочий процесс машинного обучения, который определяет порядок выполнения действий в процессе.</span><span class="sxs-lookup"><span data-stu-id="f4842-126">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="f4842-127">Вот основные этапы этого рабочего процесса:</span><span class="sxs-lookup"><span data-stu-id="f4842-127">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="f4842-128">**определение проблемы**;</span><span class="sxs-lookup"><span data-stu-id="f4842-128">**Understand the problem**</span></span>
2. <span data-ttu-id="f4842-129">**Подготовка данных**.</span><span class="sxs-lookup"><span data-stu-id="f4842-129">**Prepare your data**</span></span>
   * <span data-ttu-id="f4842-130">**Загрузка данных**.</span><span class="sxs-lookup"><span data-stu-id="f4842-130">**Load the data**</span></span>
   * <span data-ttu-id="f4842-131">**Извлечение компонентов (преобразование данных)**.</span><span class="sxs-lookup"><span data-stu-id="f4842-131">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="f4842-132">**Сборка и обучение**.</span><span class="sxs-lookup"><span data-stu-id="f4842-132">**Build and train**</span></span> 
   * <span data-ttu-id="f4842-133">**Обучение модели**.</span><span class="sxs-lookup"><span data-stu-id="f4842-133">**Train the model**</span></span>
   * <span data-ttu-id="f4842-134">**оценка модели**;</span><span class="sxs-lookup"><span data-stu-id="f4842-134">**Evaluate the model**</span></span>
4. <span data-ttu-id="f4842-135">**Выполнить**</span><span class="sxs-lookup"><span data-stu-id="f4842-135">**Run**</span></span>
   * <span data-ttu-id="f4842-136">**Потребление модели**.</span><span class="sxs-lookup"><span data-stu-id="f4842-136">**Model consumption**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="f4842-137">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="f4842-137">Understand the problem</span></span>

<span data-ttu-id="f4842-138">Прежде всего необходимо понять суть проблемы, что позволит разбить ее на отдельные фрагменты для построения и обучения модели.</span><span class="sxs-lookup"><span data-stu-id="f4842-138">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="f4842-139">Разделение проблемы позволяет прогнозировать и оценивать результаты.</span><span class="sxs-lookup"><span data-stu-id="f4842-139">Breaking the problem down allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="f4842-140">В этом руководстве ставится следующая задача: определение тональности поступившего на веб-сайт комментария, чтобы выполнить для него соответствующее действие.</span><span class="sxs-lookup"><span data-stu-id="f4842-140">The problem for this tutorial is to understand incoming website comment sentiment to take the appropriate action.</span></span>

<span data-ttu-id="f4842-141">Эта проблему можно разбить на следующие элементы: текст и значение тональности для данных, по которым вы будете обучать модель, и прогнозируемое значение тональности, которое вы будете оценивать и затем использовать в работе.</span><span class="sxs-lookup"><span data-stu-id="f4842-141">You can break down the problem to the sentiment text and sentiment value for the data you want to train the model with, and a predicted sentiment value that you can evaluate and then use operationally.</span></span>

<span data-ttu-id="f4842-142">После этого нужно дать **определение** тональности, которое поможет выбрать задачу машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="f4842-142">You then need to **determine** the sentiment, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="f4842-143">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="f4842-143">Select the appropriate machine learning task</span></span>

<span data-ttu-id="f4842-144">Для этой проблемы вам известны следующие факты.</span><span class="sxs-lookup"><span data-stu-id="f4842-144">With this problem, you know the following facts:</span></span>

<span data-ttu-id="f4842-145">Данные для обучения: комментарии на веб-сайте могут быть токсичными (1) и нетоксичными (0) (**тональность**).</span><span class="sxs-lookup"><span data-stu-id="f4842-145">Training data: website comments can be toxic (1) or not toxic (0) (**sentiment**).</span></span>
<span data-ttu-id="f4842-146">Определите **тональность** для новых комментариев на веб-сайте (токсичные или нетоксичные), например, для следующих примеров:</span><span class="sxs-lookup"><span data-stu-id="f4842-146">Predict the **sentiment** of a new website comment, either toxic or not toxic, such as in the following examples:</span></span>

* <span data-ttu-id="f4842-147">Воздержитесь от добавления ерунды в Википедию.</span><span class="sxs-lookup"><span data-stu-id="f4842-147">Please refrain from adding nonsense to Wikipedia.</span></span>
* <span data-ttu-id="f4842-148">Он просто лучший, и в статье надо об этом сказать.</span><span class="sxs-lookup"><span data-stu-id="f4842-148">He is the best, and the article should say that.</span></span>

<span data-ttu-id="f4842-149">Для этого сценария лучше всего подходит задача классификации в машинном обучении.</span><span class="sxs-lookup"><span data-stu-id="f4842-149">The classification machine learning task is best suited for this scenario.</span></span>

### <a name="about-the-classification-task"></a><span data-ttu-id="f4842-150">Сведения о задаче классификации</span><span class="sxs-lookup"><span data-stu-id="f4842-150">About the classification task</span></span>

<span data-ttu-id="f4842-151">Классификацией называют задачу машинного обучения, которая использует данные для **определения** категории, типа или класса для некоторого элемента или ряда данных.</span><span class="sxs-lookup"><span data-stu-id="f4842-151">Classification is a machine learning task that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="f4842-152">Например, классификацию можно использовать для следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f4842-152">For example, you can use classification to:</span></span>

* <span data-ttu-id="f4842-153">определение положительной или отрицательной тональности;</span><span class="sxs-lookup"><span data-stu-id="f4842-153">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="f4842-154">сортировка сообщений электронной почты на спам, нежелательную почту и нужные сообщения;</span><span class="sxs-lookup"><span data-stu-id="f4842-154">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="f4842-155">диагностика раковых заболеваний по лабораторным пробам, взятых у пациентов;</span><span class="sxs-lookup"><span data-stu-id="f4842-155">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="f4842-156">распределение клиентов по категориям с разной готовностью реагировать на рекламную акцию.</span><span class="sxs-lookup"><span data-stu-id="f4842-156">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="f4842-157">Задачи классификации обычно относятся к одному из следующих типов.</span><span class="sxs-lookup"><span data-stu-id="f4842-157">Classification tasks are frequently one of the following types:</span></span>

* <span data-ttu-id="f4842-158">Двоичная: A или B.</span><span class="sxs-lookup"><span data-stu-id="f4842-158">Binary: either A or B.</span></span>
* <span data-ttu-id="f4842-159">Многоклассовая: несколько категорий, которые прогнозируются по одной модели.</span><span class="sxs-lookup"><span data-stu-id="f4842-159">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="f4842-160">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="f4842-160">Create a console application</span></span>

1. <span data-ttu-id="f4842-161">Откройте Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="f4842-161">Open Visual Studio 2017.</span></span> <span data-ttu-id="f4842-162">Выберите **Файл** > **Создать** > **Проект** в меню.</span><span class="sxs-lookup"><span data-stu-id="f4842-162">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="f4842-163">В диалоговом окне **Новый проект** выберите узел **Visual C#**, а затем — узел **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="f4842-163">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="f4842-164">Выберите шаблон проекта **Консольное приложение (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="f4842-164">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="f4842-165">В текстовом поле **Имя** введите "Анализ тональности" и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f4842-165">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="f4842-166">Создайте каталог с именем *Data* в папке проекта, чтобы сохранить в нем файлы с наборами данных:</span><span class="sxs-lookup"><span data-stu-id="f4842-166">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="f4842-167">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="f4842-167">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="f4842-168">Введите имя папки Data и нажмите клавишу "ВВОД".</span><span class="sxs-lookup"><span data-stu-id="f4842-168">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="f4842-169">Установите **пакет NuGet для Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="f4842-169">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="f4842-170">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="f4842-170">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="f4842-171">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="f4842-171">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="f4842-172">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="f4842-172">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="f4842-173">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="f4842-173">Prepare your data</span></span>

1. <span data-ttu-id="f4842-174">Скачайте файлы [WikiPedia-detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) и [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) с наборами данных и сохраните их в ранее созданную папку *Data*.</span><span class="sxs-lookup"><span data-stu-id="f4842-174">Download the [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) and the [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="f4842-175">Первый из этих наборов данных обучает модель машинного обучения, а второй позволяет оценить точность полученной модели.</span><span class="sxs-lookup"><span data-stu-id="f4842-175">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="f4842-176">В обозревателе решений щелкните правой кнопкой мыши каждый из файлов \*.tsv и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f4842-176">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="f4842-177">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="f4842-177">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="f4842-178">Создание классов и определение путей</span><span class="sxs-lookup"><span data-stu-id="f4842-178">Create classes and define paths</span></span>

<span data-ttu-id="f4842-179">Добавьте следующие новые операторы `using` в начало файла *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="f4842-179">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="f4842-180">Нужно создать три глобальных поля для хранения путей к недавно скачанным файлам и глобальную переменную для `TextLoader`:</span><span class="sxs-lookup"><span data-stu-id="f4842-180">You need to create three global fields to hold the paths to the recently downloaded files, and a global variable for the `TextLoader`:</span></span>

* <span data-ttu-id="f4842-181">`_trainDataPath` содержит путь к набору данных, используемому для обучения модели;</span><span class="sxs-lookup"><span data-stu-id="f4842-181">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="f4842-182">`_testDataPath` содержит путь к набору данных, используемому для оценки модели;</span><span class="sxs-lookup"><span data-stu-id="f4842-182">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="f4842-183">`_modelPath` содержит путь, по которому сохраняется обученная модель.</span><span class="sxs-lookup"><span data-stu-id="f4842-183">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="f4842-184">`_textLoader` представляет собой <xref:Microsoft.ML.Runtime.Data.TextLoader>, используемый для загрузки и преобразования наборов данных.</span><span class="sxs-lookup"><span data-stu-id="f4842-184">`_textLoader` is the <xref:Microsoft.ML.Runtime.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="f4842-185">Добавьте следующий код в строку прямо перед методом `Main`, чтобы указать эти пути и переменную `_textLoader`:</span><span class="sxs-lookup"><span data-stu-id="f4842-185">Add the following code to the line right above the `Main` method to specify those paths and the `_textLoader` variable:</span></span>

[!code-csharp[Declare global variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare global variables")]

<span data-ttu-id="f4842-186">Вам потребуется создать несколько классов для входных данных и прогнозов.</span><span class="sxs-lookup"><span data-stu-id="f4842-186">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="f4842-187">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="f4842-187">Add a new class to your project:</span></span>

1. <span data-ttu-id="f4842-188">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="f4842-188">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="f4842-189">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="f4842-189">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="f4842-190">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="f4842-190">Then, select the **Add** button.</span></span>

    <span data-ttu-id="f4842-191">Файл *SentimentData.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="f4842-191">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="f4842-192">Добавьте следующий оператор `using` в начало файла *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="f4842-192">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

<span data-ttu-id="f4842-193">Удалите из файла *SentimentData.cs* существующее определение класса и добавьте следующий код с двумя классами `SentimentData` и `SentimentPrediction`:</span><span class="sxs-lookup"><span data-stu-id="f4842-193">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

<span data-ttu-id="f4842-194">Класс `SentimentData` содержит входной набор данных. У него есть `float` (`Sentiment`) для значения тональности (положительная или отрицательное) и строковый параметр (`SentimentText`) для текста комментария.</span><span class="sxs-lookup"><span data-stu-id="f4842-194">`SentimentData` is the input dataset class and has a `float` (`Sentiment`) that has a value for sentiment of either positive or negative, and a string for the comment (`SentimentText`).</span></span> <span data-ttu-id="f4842-195">Для обоих полей указаны атрибуты `Column`.</span><span class="sxs-lookup"><span data-stu-id="f4842-195">Both fields have `Column` attributes attached to them.</span></span> <span data-ttu-id="f4842-196">Этот атрибут позволяет описать порядок полей в файле данных и указывает, какое поле является `Label`.</span><span class="sxs-lookup"><span data-stu-id="f4842-196">This attribute describes the order of each field in the data file, and which is the `Label` field.</span></span> <span data-ttu-id="f4842-197">Класс `SentimentPrediction` используется для прогнозирования после обучения модели.</span><span class="sxs-lookup"><span data-stu-id="f4842-197">`SentimentPrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="f4842-198">Он имеет один параметр типа boolean (`Sentiment`) и атрибут `PredictedLabel` `ColumnName`.</span><span class="sxs-lookup"><span data-stu-id="f4842-198">It has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="f4842-199">`Label` используется для создания и обучения модели, а также для оценки модели по второму набору данных.</span><span class="sxs-lookup"><span data-stu-id="f4842-199">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="f4842-200">`PredictedLabel` используется для прогнозирования и оценки.</span><span class="sxs-lookup"><span data-stu-id="f4842-200">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="f4842-201">Для оценки применяются входные обучающие данные, прогнозируемые значения и модель.</span><span class="sxs-lookup"><span data-stu-id="f4842-201">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="f4842-202">При создании модели с использованием ML.NET сначала необходимо создать `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="f4842-202">When building a model with ML.NET you start by creating an `MLContext`.</span></span> <span data-ttu-id="f4842-203">Концептуально это сопоставимо с использованием `DbContext` в Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="f4842-203">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="f4842-204">Среда предоставляет контекст для вашего задания Машинного обучения, который можно использовать для отслеживания исключений и ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="f4842-204">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="f4842-205">Инициализация переменных в методе Main</span><span class="sxs-lookup"><span data-stu-id="f4842-205">Initialize variables in Main</span></span>

<span data-ttu-id="f4842-206">Создайте переменную с именем `mlContext` и инициализируйте ее с новым экземпляром `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="f4842-206">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="f4842-207">Замените строку `Console.WriteLine("Hello World!")` в методе `Main` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="f4842-207">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Create the ML Context")]

<span data-ttu-id="f4842-208">Затем, чтобы настроить загрузку данных, инициализируйте глобальную переменную `_textLoader` для повторного использования.</span><span class="sxs-lookup"><span data-stu-id="f4842-208">Next, to setup for data loading initialize the `_textLoader` global variable in order to reuse it.</span></span>  <span data-ttu-id="f4842-209">Обратите внимание, что вы используете `TextReader`.</span><span class="sxs-lookup"><span data-stu-id="f4842-209">Notice that you're using a `TextReader`.</span></span> <span data-ttu-id="f4842-210">При создании `TextLoader` с использованием `TextReader` вы передаете необходимый контекст и класс <xref:Microsoft.ML.Runtime.Data.TextLoader.Arguments>, который включает настройку.</span><span class="sxs-lookup"><span data-stu-id="f4842-210">When you create a `TextLoader` using a `TextReader`, you pass in the context needed and the <xref:Microsoft.ML.Runtime.Data.TextLoader.Arguments> class which enables customization.</span></span>

 <span data-ttu-id="f4842-211">Укажите схему данных, передав в загрузчик массив объектов <xref:Microsoft.ML.Runtime.Data.TextLoader.Column>, содержащий имена всех столбцов и их типы.</span><span class="sxs-lookup"><span data-stu-id="f4842-211">Specify the data schema by passing an array of <xref:Microsoft.ML.Runtime.Data.TextLoader.Column> objects to the loader containing all the column names and their types.</span></span> <span data-ttu-id="f4842-212">Вы определили схему данных ранее при создании класса `SentimentData`.</span><span class="sxs-lookup"><span data-stu-id="f4842-212">You defined the data schema previously when you created our `SentimentData` class.</span></span> <span data-ttu-id="f4842-213">Для нашей схемы первый столбец (метка) — это <xref:System.Boolean> (прогноз), а второй столбец (SentimentText) — это функция текстового или строкового типа, используемая для прогнозирования тональности.</span><span class="sxs-lookup"><span data-stu-id="f4842-213">For our schema, the first column (Label) is a <xref:System.Boolean> (the prediction) and the second column (SentimentText) is the feature of type text/string used for predicting the sentiment.</span></span>
<span data-ttu-id="f4842-214">Класс `TextReader` возвращает полностью инициализированный <xref:Microsoft.ML.Runtime.Data.TextLoader>.</span><span class="sxs-lookup"><span data-stu-id="f4842-214">The `TextReader` class returns a fully initialized <xref:Microsoft.ML.Runtime.Data.TextLoader></span></span>  

<span data-ttu-id="f4842-215">Чтобы инициализировать глобальную переменную `_textLoader` и повторно использовать ее для необходимых наборов данных, добавьте следующий код после инициализации `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="f4842-215">To initialize the `_textLoader` global variable in order to reuse it for the needed datasets, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[initTextReader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#4 "Initialize the TextReader")]

<span data-ttu-id="f4842-216">Добавьте в следующую строку метода `Main` приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="f4842-216">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Train your model")]

<span data-ttu-id="f4842-217">Метод `Train` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="f4842-217">The `Train` method executes the following tasks:</span></span>

* <span data-ttu-id="f4842-218">загрузка данных;</span><span class="sxs-lookup"><span data-stu-id="f4842-218">Loads the data.</span></span>
* <span data-ttu-id="f4842-219">извлечение и преобразование данных;</span><span class="sxs-lookup"><span data-stu-id="f4842-219">Extracts and transforms the data.</span></span>
* <span data-ttu-id="f4842-220">обучение модели;</span><span class="sxs-lookup"><span data-stu-id="f4842-220">Trains the model.</span></span>
* <span data-ttu-id="f4842-221">прогноз тональности на основе тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="f4842-221">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="f4842-222">возвращение модели.</span><span class="sxs-lookup"><span data-stu-id="f4842-222">Returns the model.</span></span>

<span data-ttu-id="f4842-223">Создайте метод `Train` сразу после метода `Main`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="f4842-223">Create the `Train` method, just after the `Main` method, using the following code:</span></span>

```csharp
 public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

<span data-ttu-id="f4842-224">Обратите внимание, что в метод Train передаются два параметра: `MLContext` для контекста (`mlContext`) и <xref:System.String> для пути к набору данных (`dataPath`).</span><span class="sxs-lookup"><span data-stu-id="f4842-224">Notice that two parameters are passed into the Train method; a `MLContext` for the context (`mlContext`), and a <xref:System.String> for the dataset path (`dataPath`).</span></span> <span data-ttu-id="f4842-225">Вы будете использовать этот метод несколько раз для обучения и тестирования.</span><span class="sxs-lookup"><span data-stu-id="f4842-225">You're going to use this method more than once for training and testing.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="f4842-226">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="f4842-226">Load the data</span></span>

<span data-ttu-id="f4842-227">Вы загрузите данные с использованием глобальной переменной `_textLoader` с параметром `dataPath`.</span><span class="sxs-lookup"><span data-stu-id="f4842-227">You'll load the data using the `_textLoader` global variable with the `dataPath` parameter.</span></span> <span data-ttu-id="f4842-228">В результате возвратится <xref:Microsoft.ML.Runtime.Data.IDataView>.</span><span class="sxs-lookup"><span data-stu-id="f4842-228">It returns a <xref:Microsoft.ML.Runtime.Data.IDataView>.</span></span> <span data-ttu-id="f4842-229">Точно так же как входные и выходные данные `Transforms`, `DataView` является основным типом конвейера данных, сравнимым с `IEnumerable` для `LINQ`.</span><span class="sxs-lookup"><span data-stu-id="f4842-229">As the input and output of `Transforms`, a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="f4842-230">В ML.NET данные аналогичны представлению SQL.</span><span class="sxs-lookup"><span data-stu-id="f4842-230">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="f4842-231">Они схематизированы, неоднородны, и к ним применено отложенное вычисление.</span><span class="sxs-lookup"><span data-stu-id="f4842-231">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="f4842-232">Объект является первой частью конвейера. Он загружает данные.</span><span class="sxs-lookup"><span data-stu-id="f4842-232">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="f4842-233">Для этого руководства он загружает набор данных с комментариями и соответствующей токсичной или нетоксичной тональностью.</span><span class="sxs-lookup"><span data-stu-id="f4842-233">For this tutorial, it loads a dataset with comments and corresponding toxic or non toxic sentiment.</span></span> <span data-ttu-id="f4842-234">Это позволяет создать и обучить модель.</span><span class="sxs-lookup"><span data-stu-id="f4842-234">This is used to create the model, and train it.</span></span>

 <span data-ttu-id="f4842-235">Добавьте следующий код в первую строку метода `Train`:</span><span class="sxs-lookup"><span data-stu-id="f4842-235">Add the following code as the first line of the `Train` method:</span></span>

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "loading training dataset")]

## <a name="extract-and-transform-the-data"></a><span data-ttu-id="f4842-236">Извлечение и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="f4842-236">Extract and transform the data</span></span>

<span data-ttu-id="f4842-237">Предварительная обработка и очистка данных — это очень важные задачи, которые нужно выполнить перед использованием набора данных для машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="f4842-237">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="f4842-238">Необработанные данные часто содержат много шума, недостаточно надежны и в них могут быть пропуски.</span><span class="sxs-lookup"><span data-stu-id="f4842-238">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="f4842-239">Использование данных напрямую без этих задач моделирования может дать неправильные результаты.</span><span class="sxs-lookup"><span data-stu-id="f4842-239">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="f4842-240">Конвейеры преобразования ML.NET создают пользовательский набор преобразований, которые применяются к данным перед началом обучения или проверки.</span><span class="sxs-lookup"><span data-stu-id="f4842-240">ML.NET's transform pipelines compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="f4842-241">Основной целью преобразования является [присвоение признаков](../resources/glossary.md#feature-engineering).</span><span class="sxs-lookup"><span data-stu-id="f4842-241">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="f4842-242">Алгоритмы Машинного обучения определяют данные с [присвоенными признаками](../resources/glossary.md#feature), поэтому следующим шагом является преобразование текстовых данных в формат, который распознают наши алгоритмы Машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="f4842-242">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="f4842-243">Этот формат — [числовой вектор](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="f4842-243">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="f4842-244">Далее вызовите `mlContext.Transforms.Text.FeaturizeText`, который преобразовывает текстовый столбец (`SentimentText`) в числовой вектор под названием `Features`, используемый в алгоритмах Машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="f4842-244">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text column (`SentimentText`) column into a numeric vector called `Features` used by the machine learning algorithm.</span></span> <span data-ttu-id="f4842-245">Это вызов программы-оболочки, возвращающий <xref:Microsoft.ML.Runtime.Data.EstimatorChain%601>, который фактически будет конвейером.</span><span class="sxs-lookup"><span data-stu-id="f4842-245">This is a wrapper call that returns an <xref:Microsoft.ML.Runtime.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="f4842-246">Присвойте ему имя `pipeline`, так как затем вы добавите обучающую систему в `EstimatorChain`.</span><span class="sxs-lookup"><span data-stu-id="f4842-246">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="f4842-247">Добавьте следующую строку кода:</span><span class="sxs-lookup"><span data-stu-id="f4842-247">Add this as the next line of code:</span></span>

[!code-csharp[TextFeaturizingEstimator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizingEstimator")]

<span data-ttu-id="f4842-248">Это этап предварительной обработки и присвоения признаков.</span><span class="sxs-lookup"><span data-stu-id="f4842-248">This is the preprocessing/featurization step.</span></span> <span data-ttu-id="f4842-249">Дополнительные компоненты из ML.NET могут дать более точные результаты для вашей модели.</span><span class="sxs-lookup"><span data-stu-id="f4842-249">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="f4842-250">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="f4842-250">Choose a learning algorithm</span></span>

<span data-ttu-id="f4842-251">Чтобы добавить обучающую систему, вызовите метод программы-оболочки `mlContext.Transforms.Text.FeaturizeText`, возвращающий объект <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer>.</span><span class="sxs-lookup"><span data-stu-id="f4842-251">To add the trainer, call the `mlContext.Transforms.Text.FeaturizeText` wrapper method which returns a <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer> object.</span></span> <span data-ttu-id="f4842-252">Это средство обучения по дереву принятия решений, которое мы применим для нашего конвейера.</span><span class="sxs-lookup"><span data-stu-id="f4842-252">This is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="f4842-253">`FastTreeBinaryClassificationTrainer` добавляется в `pipeline` и принимает `SentimentText` с присвоенными признаками (`Features`) и входные параметры `Label`, чтобы пройти обучение по историческим данным.</span><span class="sxs-lookup"><span data-stu-id="f4842-253">The `FastTreeBinaryClassificationTrainer` is appended to the `pipeline` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

<span data-ttu-id="f4842-254">Добавьте следующий код в метод `Train`:</span><span class="sxs-lookup"><span data-stu-id="f4842-254">Add the following code to the `Train` method:</span></span>

[!code-csharp[FastTreeBinaryClassificationTrainer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="f4842-255">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="f4842-255">Train the model</span></span>

<span data-ttu-id="f4842-256">Обучения модели <xref:Microsoft.ML.Data.TransformerChain%601> выполняется по набору данных, который вы ранее скачали и преобразовали.</span><span class="sxs-lookup"><span data-stu-id="f4842-256">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="f4842-257">После определения средства оценки вы обучите модель с помощью <xref:Microsoft.ML.Runtime.Data.EstimatorChain%601.Fit%2A>, предоставляя уже загруженные данные для обучения.</span><span class="sxs-lookup"><span data-stu-id="f4842-257">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Runtime.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="f4842-258">В результате возвращается модель, необходимая для выполнения прогнозов.</span><span class="sxs-lookup"><span data-stu-id="f4842-258">This returns a model to use for predictions.</span></span> <span data-ttu-id="f4842-259">`pipeline.Fit()` обучает конвейер и возвращает `Transformer` на основе переданного типа `DataView`.</span><span class="sxs-lookup"><span data-stu-id="f4842-259">`pipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="f4842-260">Эксперимент не выполняется, пока этот процесс не закончится.</span><span class="sxs-lookup"><span data-stu-id="f4842-260">The experiment is not executed until this happens.</span></span>

<span data-ttu-id="f4842-261">Добавьте следующий код в метод `Train`:</span><span class="sxs-lookup"><span data-stu-id="f4842-261">Add the following code to the `Train` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="f4842-262">Сохранение и возврат обученной модели для оценки</span><span class="sxs-lookup"><span data-stu-id="f4842-262">Save and Return the model trained to use for evaluation</span></span>

<span data-ttu-id="f4842-263">На этом этапе у вас есть модель типа <xref:Microsoft.ML.Data.TransformerChain%601>, которую можно интегрировать с любыми имеющимися или новыми приложениями .NET.</span><span class="sxs-lookup"><span data-stu-id="f4842-263">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="f4842-264">Выполните возврат модели в конце метода `Train`.</span><span class="sxs-lookup"><span data-stu-id="f4842-264">Return the model at the end of the `Train` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="f4842-265">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="f4842-265">Evaluate the model</span></span>

<span data-ttu-id="f4842-266">Итак, вы завершили создание и обучение модели, и теперь ее можно оценить по другому набору данных, чтобы проверить ее точность и качество прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="f4842-266">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="f4842-267">В методе `Evaluate` передается для оценки модель, созданная в `Train`.</span><span class="sxs-lookup"><span data-stu-id="f4842-267">In the `Evaluate` method, the model created in `Train` is passed in to be evaluated.</span></span> <span data-ttu-id="f4842-268">Создайте метод `Evaluate` сразу после метода `Train` как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="f4842-268">Create the `Evaluate` method, just after `Train`, as in the following code:</span></span>

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="f4842-269">Метод `Evaluate` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="f4842-269">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="f4842-270">загрузка тестового набора данных;</span><span class="sxs-lookup"><span data-stu-id="f4842-270">Loads the test dataset.</span></span>
* <span data-ttu-id="f4842-271">создание средства двоичной оценки;</span><span class="sxs-lookup"><span data-stu-id="f4842-271">Creates the binary evaluator.</span></span>
* <span data-ttu-id="f4842-272">оценка модели и создание метрик;</span><span class="sxs-lookup"><span data-stu-id="f4842-272">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="f4842-273">отображение метрик.</span><span class="sxs-lookup"><span data-stu-id="f4842-273">Displays the metrics.</span></span>

<span data-ttu-id="f4842-274">Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `Train`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="f4842-274">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Call the Evaluate method")]

<span data-ttu-id="f4842-275">Вы загрузите тестовый набор данных с использованием ранее инициализированной глобальной переменной `_textLoader` с глобальным полем `_testDataPath`.</span><span class="sxs-lookup"><span data-stu-id="f4842-275">You'll load the test dataset using the previously initialized  `_textLoader` global variable with the `_testDataPath` global field.</span></span> <span data-ttu-id="f4842-276">С помощью этого набора данных вы можете оценить модели для проверки ее качества.</span><span class="sxs-lookup"><span data-stu-id="f4842-276">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="f4842-277">Добавьте следующий код в метод `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="f4842-277">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Load the test dataset")]

<span data-ttu-id="f4842-278">Далее вы будете использовать параметр машинного обучения `model` (преобразователь) для ввода признаков и возврата прогнозов.</span><span class="sxs-lookup"><span data-stu-id="f4842-278">Next, you'll use the machine learning `model` parameter (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="f4842-279">В качестве следующей строки в методе `Evaluate` добавьте приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="f4842-279">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Predict using the Transformer")]

<span data-ttu-id="f4842-280">Метод `BinaryClassificationContext.Evaluate` вычисляет метрики качества для `PredictionModel` на основе указанного набора данных.</span><span class="sxs-lookup"><span data-stu-id="f4842-280">The `BinaryClassificationContext.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="f4842-281">Он возвращает объект `BinaryClassificationEvaluator.CalibratedResult`, содержащий общие метрики, вычисляемые с помощью средств оценки двоичной классификации.</span><span class="sxs-lookup"><span data-stu-id="f4842-281">It returns a `BinaryClassificationEvaluator.CalibratedResult` object contains the overall metrics computed by binary classification evaluators.</span></span> <span data-ttu-id="f4842-282">Чтобы отобразить их для оценки качества модели, сначала метрики необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="f4842-282">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="f4842-283">Добавьте в следующую строку метода `Evaluate` приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="f4842-283">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="f4842-284">Отображение метрик для проверки модели</span><span class="sxs-lookup"><span data-stu-id="f4842-284">Displaying the metrics for model validation</span></span>

<span data-ttu-id="f4842-285">Используйте следующий код для отображения метрик, передачи результатов и выполнения действий по ним:</span><span class="sxs-lookup"><span data-stu-id="f4842-285">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Display selected metrics")]

<span data-ttu-id="f4842-286">Чтобы сохранить модель в ZIP-файл, для вызова метода `SaveModelAsFile` добавьте в качестве следующей строки в `TrainFinalModel` приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="f4842-286">To save your model to a .zip file before returning, add the following code to call the `SaveModelAsFile` method as the next line in `TrainFinalModel`:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#23 "Save the model")]

## <a name="save-the-model-as-azip-file"></a><span data-ttu-id="f4842-287">Сохранение модели в качестве ZIP-файла</span><span class="sxs-lookup"><span data-stu-id="f4842-287">Save the model as a.zip file</span></span>

<span data-ttu-id="f4842-288">Создайте метод `SaveModelAsFile` сразу после метода `Evaluate`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="f4842-288">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="f4842-289">Метод `SaveModelAsFile` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="f4842-289">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="f4842-290">сохранение модели в качестве ZIP-файла.</span><span class="sxs-lookup"><span data-stu-id="f4842-290">Saves the model as a .zip file.</span></span>

<span data-ttu-id="f4842-291">Далее создайте метод для сохранения модели, чтобы ее можно было использовать повторно, а также применять в других приложениях.</span><span class="sxs-lookup"><span data-stu-id="f4842-291">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="f4842-292">`ITransformer` содержит метод <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.Runtime.IHostEnvironment,System.IO.Stream)>, который принимает глобальное поле `_modelPath`, и <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="f4842-292">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.Runtime.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="f4842-293">Чтобы сохранить модель в качестве ZIP-файла, мы создадим `FileStream` непосредственно перед вызовом метода `SaveTo`.</span><span class="sxs-lookup"><span data-stu-id="f4842-293">To save this as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="f4842-294">В качестве следующей строки в методе `SaveModelAsFile` добавьте приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="f4842-294">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#24 "Add the SaveTo Method")]

<span data-ttu-id="f4842-295">Вы также можете просмотреть, куда был записан файл, написав консольное сообщение с `_modelPath`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="f4842-295">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-model-and-a-single-comment"></a><span data-ttu-id="f4842-296">Прогнозирование результатов тестовых данных с помощью модели и одного комментария</span><span class="sxs-lookup"><span data-stu-id="f4842-296">Predict the test data outcome with the model and a single comment</span></span>

<span data-ttu-id="f4842-297">Создайте метод `Predict` сразу после метода `Evaluate`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="f4842-297">Create the `Predict` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void Predict(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="f4842-298">Метод `Predict` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="f4842-298">The `Predict` method executes the following tasks:</span></span>

* <span data-ttu-id="f4842-299">создание отдельного комментария тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="f4842-299">Creates a single comment of test data.</span></span>
* <span data-ttu-id="f4842-300">прогноз тональности на основе тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="f4842-300">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="f4842-301">объединение тестовых данных и прогнозов для создания отчетов;</span><span class="sxs-lookup"><span data-stu-id="f4842-301">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="f4842-302">отображение результатов прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="f4842-302">Displays the predicted results.</span></span>

<span data-ttu-id="f4842-303">Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `Evaluate`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="f4842-303">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Call the Predict method")]

<span data-ttu-id="f4842-304">Несмотря на то что `model` представляет собой `transformer`, который обрабатывает многочисленные строки данных, достаточно распространенным сценарием рабочей среды является прогнозирование на основе отдельных примеров.</span><span class="sxs-lookup"><span data-stu-id="f4842-304">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="f4842-305"><xref:Microsoft.ML.Runtime.Data.PredictionFunction%602> — это программа-оболочка, возвращаемая из метода `MakePredictionFunction`.</span><span class="sxs-lookup"><span data-stu-id="f4842-305">The <xref:Microsoft.ML.Runtime.Data.PredictionFunction%602> is a wrapper that is returned from the `MakePredictionFunction` method.</span></span> <span data-ttu-id="f4842-306">Давайте добавим следующий код в качестве первой строки в методе `Predict` для создания PredictionFunction:</span><span class="sxs-lookup"><span data-stu-id="f4842-306">Let's add the following code to create the PredictionFunction as the first line in the `Predict` Method:</span></span>

[!code-csharp[MakePredictionFunction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Create the PredictionFunction")]
  
<span data-ttu-id="f4842-307">Добавьте комментарий для проверки прогнозирования обученной модели в методе `Predict`, создав экземпляр `SentimentData`:</span><span class="sxs-lookup"><span data-stu-id="f4842-307">Add a comment to test the trained model's prediction in the `Predict` method by creating an instance of `SentimentData`:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for single prediction")]


 <span data-ttu-id="f4842-308">Это можно использовать для прогнозирования токсичной или нетоксичной тональности одного экземпляра данных комментария.</span><span class="sxs-lookup"><span data-stu-id="f4842-308">You can use that to predict the Toxic or Non Toxic sentiment of a single instance of the comment data.</span></span> <span data-ttu-id="f4842-309">Чтобы получить прогноз, примените <xref:Microsoft.ML.Runtime.Data.PredictionFunction%602.Predict(%600)> для данных.</span><span class="sxs-lookup"><span data-stu-id="f4842-309">To get a prediction, use <xref:Microsoft.ML.Runtime.Data.PredictionFunction%602.Predict(%600)> on the data.</span></span> <span data-ttu-id="f4842-310">Обратите внимание, что входные данные имеют строковый формат, а модель выполняет присвоение признаков.</span><span class="sxs-lookup"><span data-stu-id="f4842-310">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="f4842-311">Конвейер синхронизируется во время обучения и прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="f4842-311">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="f4842-312">Вам не нужно писать для прогнозирования отдельный код предварительной обработки и присвоения признаков. Кроме того, этот API выполняет как пакетное, так и разовое прогнозирование.</span><span class="sxs-lookup"><span data-stu-id="f4842-312">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create a prediction of sentiment")]

### <a name="model-operationalization-prediction"></a><span data-ttu-id="f4842-313">Ввод модели в эксплуатацию: прогнозирование</span><span class="sxs-lookup"><span data-stu-id="f4842-313">Model operationalization: prediction</span></span>

<span data-ttu-id="f4842-314">Отобразите `SentimentText` и соответствующие прогнозы тональности, чтобы поделиться результатами и выполнить соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="f4842-314">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="f4842-315">Этот этап называется вводом в эксплуатацию, после которого возвращаемые данные можно включить в операционные политики.</span><span class="sxs-lookup"><span data-stu-id="f4842-315">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="f4842-316">Создайте отображение для результатов с помощью следующего кода <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="f4842-316">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction output")]

## <a name="predict-the-test-data-outcomes-with-the-saved-model"></a><span data-ttu-id="f4842-317">Прогнозирование результатов для тестовых данных с помощью сохраненной модели</span><span class="sxs-lookup"><span data-stu-id="f4842-317">Predict the test data outcomes with the saved model</span></span>

<span data-ttu-id="f4842-318">Создайте метод `PredictWithModelLoadedFromFile` непосредственно перед методом `SaveModelAsFile`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="f4842-318">Create the `PredictWithModelLoadedFromFile` method, just before the `SaveModelAsFile` method, using the following code:</span></span>

```csharp
public static void PredictWithModelLoadedFromFile(MLContext mlContext)
{

}
```

<span data-ttu-id="f4842-319">Метод `PredictWithModelLoadedFromFile` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="f4842-319">The `PredictWithModelLoadedFromFile` method executes the following tasks:</span></span>

* <span data-ttu-id="f4842-320">создание пакетных тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="f4842-320">Creates batch test data.</span></span>
* <span data-ttu-id="f4842-321">прогноз тональности на основе тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="f4842-321">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="f4842-322">объединение тестовых данных и прогнозов для создания отчетов;</span><span class="sxs-lookup"><span data-stu-id="f4842-322">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="f4842-323">отображение результатов прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="f4842-323">Displays the predicted results.</span></span>

<span data-ttu-id="f4842-324">Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `Predict`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="f4842-324">Add a call to the new method from the `Main` method, right under the `Predict` method call, using the following code:</span></span>

[!code-csharp[CallPredictModelLoaded](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#25 "Call the PredictWithModelLoadedFromFile method")]

<span data-ttu-id="f4842-325">Добавьте новые комментарии, чтобы проверить прогнозы обученной модели, в метод `PredictWithModelLoadedFromFile`:</span><span class="sxs-lookup"><span data-stu-id="f4842-325">Add some comments to test the trained model's predictions in the `PredictWithModelLoadedFromFile` method:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#26 "Create test data for predictions")]

<span data-ttu-id="f4842-326">Загрузите модель [!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#27 "Load the model")].</span><span class="sxs-lookup"><span data-stu-id="f4842-326">Load the model [!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#27 "Load the model")]</span></span>

<span data-ttu-id="f4842-327">Теперь у вас есть готовая модель, и ее можно использовать для прогнозирования токсичной или нетоксичной тональности по данным комментариев с помощью метода <xref:Microsoft.ML.Core.Data.ITransformer.Transform(Microsoft.ML.Runtime.Data.IDataView)>.</span><span class="sxs-lookup"><span data-stu-id="f4842-327">Now that you have a model, you can use that to predict the Toxic or Non Toxic sentiment of the comment data using the <xref:Microsoft.ML.Core.Data.ITransformer.Transform(Microsoft.ML.Runtime.Data.IDataView)> method.</span></span> <span data-ttu-id="f4842-328">Чтобы получить прогноз, примените `Predict` для новых данных.</span><span class="sxs-lookup"><span data-stu-id="f4842-328">To get a prediction, use `Predict` on new data.</span></span> <span data-ttu-id="f4842-329">Обратите внимание, что входные данные имеют строковый формат, а модель выполняет присвоение признаков.</span><span class="sxs-lookup"><span data-stu-id="f4842-329">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="f4842-330">Конвейер синхронизируется во время обучения и прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="f4842-330">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="f4842-331">Вам не нужно писать для прогнозирования отдельный код предварительной обработки и присвоения признаков. Кроме того, этот API выполняет как пакетное, так и разовое прогнозирование.</span><span class="sxs-lookup"><span data-stu-id="f4842-331">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="f4842-332">Добавьте в метод `PredictWithModelLoadedFromFile` приведенный ниже код для прогнозирования:</span><span class="sxs-lookup"><span data-stu-id="f4842-332">Add the following code to the `PredictWithModelLoadedFromFile` method for the predictions:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#28 "Create predictions of sentiments")]

### <a name="model-operationalization-prediction"></a><span data-ttu-id="f4842-333">Ввод модели в эксплуатацию: прогнозирование</span><span class="sxs-lookup"><span data-stu-id="f4842-333">Model operationalization: prediction</span></span>

<span data-ttu-id="f4842-334">Отобразите `SentimentText` и соответствующие прогнозы тональности, чтобы поделиться результатами и выполнить соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="f4842-334">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="f4842-335">Этот этап называется вводом в эксплуатацию, после которого возвращаемые данные можно включить в операционные политики.</span><span class="sxs-lookup"><span data-stu-id="f4842-335">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="f4842-336">Создайте заголовок для результатов с помощью следующего кода <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="f4842-336">Create a header for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#29 "Display prediction outputs")]

<span data-ttu-id="f4842-337">Перед отображением результатов прогнозирования объедините данные о тональности с прогнозами, чтобы просмотреть исходные комментарии и прогнозы тональности.</span><span class="sxs-lookup"><span data-stu-id="f4842-337">Before displaying the predicted results, combine the sentiment and prediction together to see the original comment with its predicted sentiment.</span></span> <span data-ttu-id="f4842-338">В следующем коде для этого используется метод <xref:System.Linq.Enumerable.Zip%2A>, а после него нужно добавить следующий код:</span><span class="sxs-lookup"><span data-stu-id="f4842-338">The following code uses the <xref:System.Linq.Enumerable.Zip%2A> method to make that happen, so add that code next:</span></span>

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#30 "Build the pairs of sentiment data and predictions")]

<span data-ttu-id="f4842-339">Теперь, когда вы объединили в один класс `SentimentText` и `Sentiment`, можно отобразить результаты с помощью метода <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="f4842-339">Now that you've combined the `SentimentText` and `Sentiment` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#31 "Display the predictions")]

<span data-ttu-id="f4842-340">Так как выводимые имена элементов кортежа появились только в C# версии 7.1, а для этого проекта по умолчанию устанавливается версия языка C# 7.0, необходимо изменить это значение до C# 7.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="f4842-340">Because inferred tuple element names are a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="f4842-341">Для этого в **обозревателе решений** щелкните узел проекта правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f4842-341">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="f4842-342">Откройте вкладку **Сборка** и нажмите на кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="f4842-342">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="f4842-343">В раскрывающемся списке выберите **C# 7.1** (или более позднюю версию).</span><span class="sxs-lookup"><span data-stu-id="f4842-343">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="f4842-344">Нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4842-344">Select the **OK** button.</span></span>

## <a name="results"></a><span data-ttu-id="f4842-345">Результаты</span><span class="sxs-lookup"><span data-stu-id="f4842-345">Results</span></span>

<span data-ttu-id="f4842-346">Результаты выполнения должны выглядеть примерно так, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="f4842-346">Your results should be similar to the following.</span></span> <span data-ttu-id="f4842-347">В процессе работы конвейер выводит сообщения.</span><span class="sxs-lookup"><span data-stu-id="f4842-347">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="f4842-348">Вы можете видеть предупреждения или обработанные сообщения.</span><span class="sxs-lookup"><span data-stu-id="f4842-348">You may see warnings, or processing messages.</span></span> <span data-ttu-id="f4842-349">Для удобства они удалены из следующих результатов.</span><span class="sxs-lookup"><span data-stu-id="f4842-349">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 94.44%
Auc: 98.77%
F1Score: 94.74%
=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.5297049
=============== End of Predictions ===============

=============== New iteration of Model ===============
=============== Create and Train the Model ===============
=============== End of training ===============


The model is saved to: C:\Tutorial\SentimentAnalysis\bin\Debug\netcoreapp2.0\Data\Model.zip

=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.4585565
Sentiment: He is the best, and the article should say that. | Prediction: Not Toxic | Probability: 0.9924279

```

<span data-ttu-id="f4842-350">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="f4842-350">Congratulations!</span></span> <span data-ttu-id="f4842-351">Вы успешно создали модель машинного обучения для классификации и прогнозирования тональности сообщений.</span><span class="sxs-lookup"><span data-stu-id="f4842-351">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span> <span data-ttu-id="f4842-352">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="f4842-352">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f4842-353">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="f4842-353">Next steps</span></span>

<span data-ttu-id="f4842-354">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="f4842-354">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="f4842-355">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="f4842-355">Understand the problem</span></span>
> * <span data-ttu-id="f4842-356">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="f4842-356">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="f4842-357">подготавливать данные;</span><span class="sxs-lookup"><span data-stu-id="f4842-357">Prepare your data</span></span>
> * <span data-ttu-id="f4842-358">создавать конвейеры обучения;</span><span class="sxs-lookup"><span data-stu-id="f4842-358">Create the learning pipeline</span></span>
> * <span data-ttu-id="f4842-359">загружать классификатор;</span><span class="sxs-lookup"><span data-stu-id="f4842-359">Load a classifier</span></span>
> * <span data-ttu-id="f4842-360">обучить модель;</span><span class="sxs-lookup"><span data-stu-id="f4842-360">Train the model</span></span>
> * <span data-ttu-id="f4842-361">проводить оценку модели по другому набору данных;</span><span class="sxs-lookup"><span data-stu-id="f4842-361">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="f4842-362">прогнозировать результаты для тестовых данных с помощью модели.</span><span class="sxs-lookup"><span data-stu-id="f4842-362">Predict the test data outcomes with the model</span></span>

<span data-ttu-id="f4842-363">Переходите к следующему руководству:</span><span class="sxs-lookup"><span data-stu-id="f4842-363">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="f4842-364">Прогнозирование платы за такси</span><span class="sxs-lookup"><span data-stu-id="f4842-364">Taxi Fare Predictor</span></span>](taxi-fare.md)
