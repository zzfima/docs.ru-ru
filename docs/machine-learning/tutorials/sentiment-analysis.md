---
title: Использование ML.NET для анализа тональности методом двоичной классификации
description: На примере двоичной классификации с использованием ML.NET вы сможете узнать, как использовать прогнозирование тональности для выбора соответствующих действий.
ms.date: 03/07/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: b0d02babd126a62ef9a87b251f525a08376069aa
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2019
ms.locfileid: "57845795"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a><span data-ttu-id="db753-103">Учебник. Использование ML.NET для анализа тональности методом двоичной классификации</span><span class="sxs-lookup"><span data-stu-id="db753-103">Tutorial: Use ML.NET in a sentiment analysis binary classification scenario</span></span>

<span data-ttu-id="db753-104">В этом практическом руководстве показано, как создать классификатор тональности для прогнозирования положительной или отрицательной тональности на основе ML.NET в консольном приложении .NET Core на языке C# с помощью Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="db753-104">This sample tutorial illustrates using ML.NET to create a sentiment classifier to predict either positive or negative sentiment via a .NET Core console application using C# in Visual Studio 2017.</span></span> <span data-ttu-id="db753-105">В сфере машинного обучения этот тип прогнозирования называется двоичной классификацией.</span><span class="sxs-lookup"><span data-stu-id="db753-105">In the world of machine learning, this type of prediction is known as binary classification.</span></span>

> [!NOTE]
> <span data-ttu-id="db753-106">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="db753-106">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="db753-107">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="db753-107">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="db753-108">Сейчас в этом руководстве и соответствующем примере используется **ML.NET версии 0.11**.</span><span class="sxs-lookup"><span data-stu-id="db753-108">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="db753-109">Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="db753-109">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)</span></span>

<span data-ttu-id="db753-110">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="db753-110">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="db753-111">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="db753-111">Understand the problem</span></span>
> * <span data-ttu-id="db753-112">Выбор подходящего алгоритма машинного обучения</span><span class="sxs-lookup"><span data-stu-id="db753-112">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="db753-113">подготавливать данные;</span><span class="sxs-lookup"><span data-stu-id="db753-113">Prepare your data</span></span>
> * <span data-ttu-id="db753-114">Преобразование данных</span><span class="sxs-lookup"><span data-stu-id="db753-114">Transform the data</span></span>
> * <span data-ttu-id="db753-115">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="db753-115">Train the model</span></span>
> * <span data-ttu-id="db753-116">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="db753-116">Evaluate the model</span></span>
> * <span data-ttu-id="db753-117">Прогнозирование с помощью обученной модели</span><span class="sxs-lookup"><span data-stu-id="db753-117">Predict with the trained model</span></span>
> * <span data-ttu-id="db753-118">Развертывание и прогнозирование с помощью загруженной модели</span><span class="sxs-lookup"><span data-stu-id="db753-118">Deploy and Predict with a loaded model</span></span>

## <a name="sentiment-analysis-sample-overview"></a><span data-ttu-id="db753-119">Обзор примера для анализа тональности</span><span class="sxs-lookup"><span data-stu-id="db753-119">Sentiment analysis sample overview</span></span>

<span data-ttu-id="db753-120">В качестве примера мы используем консольное приложение, которое использует ML.NET для обучения модели, которая классифицирует и прогнозирует тональность по двоичному признаку: положительная или отрицательная.</span><span class="sxs-lookup"><span data-stu-id="db753-120">The sample is a console app that uses ML.NET to train a model that classifies and predicts sentiment as either positive or negative.</span></span> <span data-ttu-id="db753-121">Набор данных тональности Yelp был взят из Калифорнийского Университета в Ирвайне (UCI) и делится на два набора данных — для обучения и для тестирования.</span><span class="sxs-lookup"><span data-stu-id="db753-121">The Yelp sentiment dataset is from University of California, Irvine (UCI), which is split into a train dataset and a test dataset.</span></span> <span data-ttu-id="db753-122">Для анализа качества в примере модель оценивается по набору данных для тестирования.</span><span class="sxs-lookup"><span data-stu-id="db753-122">The sample evaluates the model with the test dataset for quality analysis.</span></span> 

<span data-ttu-id="db753-123">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="db753-123">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="db753-124">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="db753-124">Prerequisites</span></span>

* <span data-ttu-id="db753-125">[Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="db753-125">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="db753-126">[ZIP-файл набора данных предложений с меткой тональности UCI](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip).</span><span class="sxs-lookup"><span data-stu-id="db753-126">[The UCI Sentiment Labeled Sentences dataset zip file](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="db753-127">Рабочий процесс машинного обучения</span><span class="sxs-lookup"><span data-stu-id="db753-127">Machine learning workflow</span></span>

<span data-ttu-id="db753-128">В этом руководстве используется рабочий процесс машинного обучения, который определяет порядок выполнения действий в процессе.</span><span class="sxs-lookup"><span data-stu-id="db753-128">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="db753-129">Вот основные этапы этого рабочего процесса:</span><span class="sxs-lookup"><span data-stu-id="db753-129">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="db753-130">**определение проблемы**;</span><span class="sxs-lookup"><span data-stu-id="db753-130">**Understand the problem**</span></span>
2. <span data-ttu-id="db753-131">**Подготовка данных**.</span><span class="sxs-lookup"><span data-stu-id="db753-131">**Prepare your data**</span></span>
   * <span data-ttu-id="db753-132">**Загрузка данных**.</span><span class="sxs-lookup"><span data-stu-id="db753-132">**Load the data**</span></span>
   * <span data-ttu-id="db753-133">**Извлечение компонентов (преобразование данных)**.</span><span class="sxs-lookup"><span data-stu-id="db753-133">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="db753-134">**Сборка и обучение**.</span><span class="sxs-lookup"><span data-stu-id="db753-134">**Build and train**</span></span> 
   * <span data-ttu-id="db753-135">**Обучение модели**.</span><span class="sxs-lookup"><span data-stu-id="db753-135">**Train the model**</span></span>
   * <span data-ttu-id="db753-136">**оценка модели**;</span><span class="sxs-lookup"><span data-stu-id="db753-136">**Evaluate the model**</span></span>
4. <span data-ttu-id="db753-137">**Развертывание модели**</span><span class="sxs-lookup"><span data-stu-id="db753-137">**Deploy Model**</span></span>
   * <span data-ttu-id="db753-138">**Использование модели для прогнозирования**</span><span class="sxs-lookup"><span data-stu-id="db753-138">**Use the Model to predict**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="db753-139">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="db753-139">Understand the problem</span></span>

<span data-ttu-id="db753-140">Прежде всего необходимо понять суть проблемы, что позволит разбить ее на отдельные фрагменты для построения и обучения модели.</span><span class="sxs-lookup"><span data-stu-id="db753-140">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="db753-141">Разделение проблемы позволяет прогнозировать и оценивать результаты.</span><span class="sxs-lookup"><span data-stu-id="db753-141">Breaking the problem down allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="db753-142">В этом руководстве ставится следующая задача: определение тональности поступившего на веб-сайт комментария, чтобы выполнить для него соответствующее действие.</span><span class="sxs-lookup"><span data-stu-id="db753-142">The problem for this tutorial is to understand incoming website comment sentiment to take the appropriate action.</span></span>

<span data-ttu-id="db753-143">Эта проблему можно разбить на следующие элементы: текст и значение тональности для данных, по которым вы будете обучать модель, и прогнозируемое значение тональности, которое вы будете оценивать и затем использовать в работе.</span><span class="sxs-lookup"><span data-stu-id="db753-143">You can break down the problem to the sentiment text and sentiment value for the data you want to train the model with, and a predicted sentiment value that you can evaluate and then use operationally.</span></span>

<span data-ttu-id="db753-144">После этого нужно дать **определение** тональности, которое поможет выбрать задачу машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="db753-144">You then need to **determine** the sentiment, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="db753-145">Выбор подходящего алгоритма машинного обучения</span><span class="sxs-lookup"><span data-stu-id="db753-145">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="db753-146">Для этой проблемы вам известны следующие факты.</span><span class="sxs-lookup"><span data-stu-id="db753-146">With this problem, you know the following facts:</span></span>

<span data-ttu-id="db753-147">Данные для обучения: комментарии на веб-сайте могут быть положительными (1) или отрицательными (0) (**тональность**).</span><span class="sxs-lookup"><span data-stu-id="db753-147">Training data: website comments can be positive (1) or negative (0) (**sentiment**).</span></span>

<span data-ttu-id="db753-148">Определите **тональность** для новых комментариев на веб-сайте, например для следующих примеров:</span><span class="sxs-lookup"><span data-stu-id="db753-148">Predict the **sentiment** of a new website comment, either positive or negative, such as in the following examples:</span></span>

* <span data-ttu-id="db753-149">Здесь отличные официанты.</span><span class="sxs-lookup"><span data-stu-id="db753-149">I love the wait staff here.</span></span> <span data-ttu-id="db753-150">Молодцы!</span><span class="sxs-lookup"><span data-stu-id="db753-150">They rock.</span></span>
* <span data-ttu-id="db753-151">В этом заведении отвратительный суп.</span><span class="sxs-lookup"><span data-stu-id="db753-151">This place has the worst soup.</span></span>

<span data-ttu-id="db753-152">Для этого сценария лучше всего подходит алгоритм классификации в машинном обучении.</span><span class="sxs-lookup"><span data-stu-id="db753-152">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-algorithm"></a><span data-ttu-id="db753-153">Алгоритм классификации</span><span class="sxs-lookup"><span data-stu-id="db753-153">About the classification algorithm</span></span>

<span data-ttu-id="db753-154">Классификацией называют алгоритм машинного обучения, который использует данные для **определения** категории, типа или класса для некоторого элемента или ряда данных.</span><span class="sxs-lookup"><span data-stu-id="db753-154">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="db753-155">Например, классификацию можно использовать для следующих действий:</span><span class="sxs-lookup"><span data-stu-id="db753-155">For example, you can use classification to:</span></span>

* <span data-ttu-id="db753-156">определение положительной или отрицательной тональности;</span><span class="sxs-lookup"><span data-stu-id="db753-156">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="db753-157">сортировка сообщений электронной почты на спам, нежелательную почту и нужные сообщения;</span><span class="sxs-lookup"><span data-stu-id="db753-157">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="db753-158">диагностика раковых заболеваний по лабораторным пробам, взятых у пациентов;</span><span class="sxs-lookup"><span data-stu-id="db753-158">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="db753-159">распределение клиентов по категориям с разной готовностью реагировать на рекламную акцию.</span><span class="sxs-lookup"><span data-stu-id="db753-159">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="db753-160">Алгоритмы классификации обычно относятся к одному из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="db753-160">Classification algorithms are frequently one of the following types:</span></span>

* <span data-ttu-id="db753-161">Двоичная: A или B.</span><span class="sxs-lookup"><span data-stu-id="db753-161">Binary: either A or B.</span></span>
* <span data-ttu-id="db753-162">Многоклассовая: несколько категорий, которые прогнозируются по одной модели.</span><span class="sxs-lookup"><span data-stu-id="db753-162">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="db753-163">Так как комментарии с сайта необходимо классифицировать как положительные или отрицательные, используется алгоритм двоичной классификации.</span><span class="sxs-lookup"><span data-stu-id="db753-163">Because the website comments need to be classified as either positive or negative, you use the Binary Classification algorithm.</span></span> 

## <a name="create-a-console-application"></a><span data-ttu-id="db753-164">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="db753-164">Create a console application</span></span>

1. <span data-ttu-id="db753-165">Откройте Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="db753-165">Open Visual Studio 2017.</span></span> <span data-ttu-id="db753-166">Выберите **Файл** > **Создать** > **Проект** в меню.</span><span class="sxs-lookup"><span data-stu-id="db753-166">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="db753-167">В диалоговом окне **Новый проект** выберите узел **Visual C#**, а затем — узел **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="db753-167">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="db753-168">Выберите шаблон проекта **Консольное приложение (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="db753-168">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="db753-169">В текстовом поле **Имя** введите "Анализ тональности" и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="db753-169">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="db753-170">Создайте каталог с именем *Data* в папке проекта, чтобы сохранить в нем файлы с наборами данных:</span><span class="sxs-lookup"><span data-stu-id="db753-170">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="db753-171">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="db753-171">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="db753-172">Введите имя папки Data и нажмите клавишу "ВВОД".</span><span class="sxs-lookup"><span data-stu-id="db753-172">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="db753-173">Установите **пакет NuGet для Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="db753-173">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="db753-174">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="db753-174">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="db753-175">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="db753-175">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="db753-176">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="db753-176">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="db753-177">подготавливать данные;</span><span class="sxs-lookup"><span data-stu-id="db753-177">Prepare your data</span></span>

1. <span data-ttu-id="db753-178">Скачайте [ZIP-файл набора данных предложений с меткой тональности UCI (ссылка дана в следующем примечании)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) и распакуйте его.</span><span class="sxs-lookup"><span data-stu-id="db753-178">Download [The UCI Sentiment Labeled Sentences dataset zip file (see citations in the following note)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="db753-179">Скопируйте файл `yelp_labelled.txt` в созданный каталог *Data*.</span><span class="sxs-lookup"><span data-stu-id="db753-179">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

> [!NOTE]
> <span data-ttu-id="db753-180">Наборы данных в этом руководстве взяты из документа "From Group to Individual Labels using Deep Features" (От групповых до индивидуальных меток с использованием функций глубокого обучения), Котциас (Kotzias) и</span><span class="sxs-lookup"><span data-stu-id="db753-180">The datasets this tutorial uses are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="db753-181">др.,</span><span class="sxs-lookup"><span data-stu-id="db753-181">al,.</span></span> <span data-ttu-id="db753-182">KDD 2015, и размещены в репозитории машинного обучения UCI Д. Дуа (D. Dua) и Э. Карра Танискиду (E. Karra Taniskidou) (2017).</span><span class="sxs-lookup"><span data-stu-id="db753-182">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="db753-183">UCI Machine Learning Repository (Репозиторий машинного обучения UCI) [http://archive.ics.uci.edu/ml].</span><span class="sxs-lookup"><span data-stu-id="db753-183">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="db753-184">Ирвайн, Калифорния: Калифорнийский университет, Школа информационных технологий и компьютерных наук.</span><span class="sxs-lookup"><span data-stu-id="db753-184">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

3. <span data-ttu-id="db753-185">В обозревателе решений щелкните правой кнопкой мыши файл `yelp_labeled.txt` и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="db753-185">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="db753-186">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="db753-186">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="db753-187">Создание классов и определение путей</span><span class="sxs-lookup"><span data-stu-id="db753-187">Create classes and define paths</span></span>

<span data-ttu-id="db753-188">Добавьте следующие новые операторы `using` в начало файла *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="db753-188">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="db753-189">Создайте два глобальных поля для хранения пути к недавно скачанному файлу набора данных и файлу сохраненной модели:</span><span class="sxs-lookup"><span data-stu-id="db753-189">You need to create two global fields to hold the recently downloaded dataset file path and the saved model file path:</span></span>

* <span data-ttu-id="db753-190">`_dataPath` содержит путь к набору данных, используемому для обучения модели;</span><span class="sxs-lookup"><span data-stu-id="db753-190">`_dataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="db753-191">`_modelPath` содержит путь, по которому сохраняется обученная модель.</span><span class="sxs-lookup"><span data-stu-id="db753-191">`_modelPath` has the path where the trained model is saved.</span></span>

<span data-ttu-id="db753-192">Добавьте следующий код в строку прямо перед методом `Main`, чтобы указать эти пути:</span><span class="sxs-lookup"><span data-stu-id="db753-192">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Declare global variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DeclareGlobalVariables "Declare global variables")]

<span data-ttu-id="db753-193">Вам потребуется создать несколько классов для входных данных и прогнозов.</span><span class="sxs-lookup"><span data-stu-id="db753-193">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="db753-194">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="db753-194">Add a new class to your project:</span></span>

1. <span data-ttu-id="db753-195">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="db753-195">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="db753-196">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="db753-196">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="db753-197">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="db753-197">Then, select the **Add** button.</span></span>

    <span data-ttu-id="db753-198">Файл *SentimentData.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="db753-198">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="db753-199">Добавьте следующий оператор `using` в начало файла *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="db753-199">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="db753-200">Удалите из файла *SentimentData.cs* существующее определение класса и добавьте следующий код с двумя классами `SentimentData` и `SentimentPrediction`:</span><span class="sxs-lookup"><span data-stu-id="db753-200">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#DeclareTypes "Declare data record types")]

<span data-ttu-id="db753-201">Класс входного набора данных `SentimentData` содержит параметры `string` — для комментария (`SentimentText`) и `bool` (`Sentiment`) — для определения положительной или отрицательной тональности.</span><span class="sxs-lookup"><span data-stu-id="db753-201">The input dataset class, `SentimentData`, has a `string` for the comment (`SentimentText`) and a `bool` (`Sentiment`) that has a value for sentiment of either positive or negative.</span></span> <span data-ttu-id="db753-202">Для обоих полей указаны атрибуты <xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29>.</span><span class="sxs-lookup"><span data-stu-id="db753-202">Both fields have <xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29> attributes attached to them.</span></span> <span data-ttu-id="db753-203">Этот атрибут позволяет описать порядок полей в файле данных.</span><span class="sxs-lookup"><span data-stu-id="db753-203">This attribute describes the order of each field in the data file.</span></span>  <span data-ttu-id="db753-204">Кроме того, свойство `Sentiment` имеет атрибут <xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A>, который позволяет обозначить его как поле `Label`.</span><span class="sxs-lookup"><span data-stu-id="db753-204">In addition, the `Sentiment` property has a <xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A> to designate it as the `Label` field.</span></span> <span data-ttu-id="db753-205">Класс `SentimentPrediction` используется для прогнозирования после обучения модели.</span><span class="sxs-lookup"><span data-stu-id="db753-205">`SentimentPrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="db753-206">Он имеет один параметр типа boolean (`Sentiment`) и атрибут `PredictedLabel` `ColumnName`.</span><span class="sxs-lookup"><span data-stu-id="db753-206">It has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="db753-207">Параметр `Label` используется для создания и обучения модели, а также для оценки модели по разделенному набору данных для тестирования.</span><span class="sxs-lookup"><span data-stu-id="db753-207">The `Label` is used to create and train the model, and it's also used with the split out test dataset to evaluate the model.</span></span> <span data-ttu-id="db753-208">`PredictedLabel` используется для прогнозирования и оценки.</span><span class="sxs-lookup"><span data-stu-id="db753-208">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="db753-209">Для оценки применяются входные обучающие данные, прогнозируемые значения и модель.</span><span class="sxs-lookup"><span data-stu-id="db753-209">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="db753-210">При создании модели с использованием ML.NET сначала необходимо создать <xref:Microsoft.ML.MLContext>.</span><span class="sxs-lookup"><span data-stu-id="db753-210">When building a model with ML.NET you start by creating an <xref:Microsoft.ML.MLContext>.</span></span> <span data-ttu-id="db753-211">Концептуально `MLContext` сопоставимо с использованием `DbContext` в Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="db753-211">`MLContext` is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="db753-212">Среда предоставляет контекст для вашего задания Машинного обучения, который можно использовать для отслеживания исключений и ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="db753-212">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="db753-213">Инициализация переменных в методе Main</span><span class="sxs-lookup"><span data-stu-id="db753-213">Initialize variables in Main</span></span>

<span data-ttu-id="db753-214">Создайте переменную с именем `mlContext` и инициализируйте ее с новым экземпляром `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="db753-214">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="db753-215">Замените строку `Console.WriteLine("Hello World!")` в методе `Main` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="db753-215">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateMLContext "Create the ML Context")]

<span data-ttu-id="db753-216">Добавьте в следующую строку метода `Main` приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="db753-216">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallLoadData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallLoadData)]

<span data-ttu-id="db753-217">Метод `LoadData` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="db753-217">The `LoadData` method executes the following tasks:</span></span>

* <span data-ttu-id="db753-218">загрузка данных;</span><span class="sxs-lookup"><span data-stu-id="db753-218">Loads the data.</span></span>
* <span data-ttu-id="db753-219">Разделяет скачанный набор данных на наборы данных для обучения и тестирования.</span><span class="sxs-lookup"><span data-stu-id="db753-219">Splits the loaded dataset into train and test datasets.</span></span>
* <span data-ttu-id="db753-220">Возвращает два набора данных — для обучения и для тестирования.</span><span class="sxs-lookup"><span data-stu-id="db753-220">Returns the split train and test datasets.</span></span>

<span data-ttu-id="db753-221">Создайте метод `LoadData` сразу после метода `Main`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="db753-221">Create the `LoadData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static (IDataView trainSet, IDataView testSet) LoadData(MLContext mlContext)
{

}
```
## <a name="load-the-data"></a><span data-ttu-id="db753-222">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="db753-222">Load the data</span></span>

<span data-ttu-id="db753-223">Так как созданный ранее тип модели данных `SentimentData` соответствует схеме набора данных, вы можете объединить инициализацию, сопоставление и загрузку набора данных в одной строке кода с использованием оболочки `MLContext.Data.LoadFromTextFile` для [метода LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span><span class="sxs-lookup"><span data-stu-id="db753-223">Since your previously created `SentimentData` data model type matches the dataset schema, you can combine the initialization, mapping, and dataset loading into one line of code using the `MLContext.Data.LoadFromTextFile` wrapper for the [LoadFromTextFile method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span></span> <span data-ttu-id="db753-224">В результате возвратится <xref:Microsoft.Data.DataView.IDataView>.</span><span class="sxs-lookup"><span data-stu-id="db753-224">It returns a <xref:Microsoft.Data.DataView.IDataView>.</span></span> 

 <span data-ttu-id="db753-225">Точно так же как входные и выходные данные `Transforms`, `DataView` является основным типом конвейера данных, сравнимым с `IEnumerable` для `LINQ`.</span><span class="sxs-lookup"><span data-stu-id="db753-225">As the input and output of `Transforms`, a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="db753-226">В ML.NET данные аналогичны представлению SQL.</span><span class="sxs-lookup"><span data-stu-id="db753-226">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="db753-227">Они схематизированы, неоднородны, и к ним применено отложенное вычисление.</span><span class="sxs-lookup"><span data-stu-id="db753-227">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="db753-228">Объект является первой частью конвейера. Он загружает данные.</span><span class="sxs-lookup"><span data-stu-id="db753-228">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="db753-229">Для этого руководства он загружает набор данных с комментариями и соответствующей токсичной или нетоксичной тональностью.</span><span class="sxs-lookup"><span data-stu-id="db753-229">For this tutorial, it loads a dataset with comments and corresponding toxic or non toxic sentiment.</span></span> <span data-ttu-id="db753-230">Это позволяет создать и обучить модель.</span><span class="sxs-lookup"><span data-stu-id="db753-230">This is used to create the model, and train it.</span></span>

 <span data-ttu-id="db753-231">Добавьте следующий код в первую строку метода `LoadData`:</span><span class="sxs-lookup"><span data-stu-id="db753-231">Add the following code as the first line of the `LoadData` method:</span></span>

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadData "loading dataset")]

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="db753-232">Разделение набора данных для обучения и тестирования модели</span><span class="sxs-lookup"><span data-stu-id="db753-232">Split the dataset for model training and testing</span></span>

<span data-ttu-id="db753-233">Затем для обучения модели необходимо использовать набор данных для обучения, а для оценки модели — набор данных для тестирования.</span><span class="sxs-lookup"><span data-stu-id="db753-233">Next, you need both a training dataset to train the model and a test dataset to evaluate the model.</span></span> <span data-ttu-id="db753-234">Используйте параметр `MLContext.BinaryClassification.TrainTestSplit` который заключает в оболочку <xref:Microsoft.ML.StaticPipe.TrainingStaticExtensions.TrainTestSplit%2A>, чтобы разделить загруженный набор данных на наборы данных для обучения и тестирования и вернуть их в <xref:Microsoft.ML.TrainCatalogBase.TrainTestData>.</span><span class="sxs-lookup"><span data-stu-id="db753-234">Use the `MLContext.BinaryClassification.TrainTestSplit` which wraps <xref:Microsoft.ML.StaticPipe.TrainingStaticExtensions.TrainTestSplit%2A> to split the loaded dataset into train and test datasets and return them inside of a <xref:Microsoft.ML.TrainCatalogBase.TrainTestData>.</span></span> <span data-ttu-id="db753-235">С помощью параметра `testFraction` можно указать, какие данные необходимо добавить в набор для тестирования.</span><span class="sxs-lookup"><span data-stu-id="db753-235">You can specify the fraction of data for the test set with the `testFraction`parameter.</span></span> <span data-ttu-id="db753-236">По умолчанию параметр имеет значение 10%, но в этом примере необходимо задать 20%, чтобы использовать дополнительные данные для оценки.</span><span class="sxs-lookup"><span data-stu-id="db753-236">The default is 10% but you use 20% in this case to use more data for the evaluation.</span></span>  

<span data-ttu-id="db753-237">Чтобы разделить скачанные данные на необходимые наборы данных, добавьте код в следующей строке метода `LoadData`:</span><span class="sxs-lookup"><span data-stu-id="db753-237">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData` method:</span></span>

[!code-csharp[SplitData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SplitData "Split the Data")]

<span data-ttu-id="db753-238">Верните `splitDataView` в конце метода `LoadData`.</span><span class="sxs-lookup"><span data-stu-id="db753-238">Return the `splitDataView` at the end of the `LoadData` method:</span></span>

[!code-csharp[ReturnSplitData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="db753-239">Сборка и обучение модели</span><span class="sxs-lookup"><span data-stu-id="db753-239">Build and train the model</span></span>

<span data-ttu-id="db753-240">В следующей строке кода в методе `Main` добавьте приведенный ниже вызов метода `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="db753-240">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="db753-241">Метод `BuildAndTrainModel` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="db753-241">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="db753-242">извлечение и преобразование данных;</span><span class="sxs-lookup"><span data-stu-id="db753-242">Extracts and transforms the data.</span></span>
* <span data-ttu-id="db753-243">обучение модели;</span><span class="sxs-lookup"><span data-stu-id="db753-243">Trains the model.</span></span>
* <span data-ttu-id="db753-244">прогноз тональности на основе тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="db753-244">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="db753-245">возвращение модели.</span><span class="sxs-lookup"><span data-stu-id="db753-245">Returns the model.</span></span>

<span data-ttu-id="db753-246">Создайте метод `BuildAndTrainModel` сразу после метода `Main`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="db753-246">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
{

}
```

<span data-ttu-id="db753-247">Обратите внимание, что в метод Train передаются два параметра: `MLContext` для контекста (`mlContext`) и `IDataView` набора данных для обучения (`splitTrainSet`).</span><span class="sxs-lookup"><span data-stu-id="db753-247">Notice that two parameters are passed into the Train method; a `MLContext` for the context (`mlContext`), and an `IDataView`for the training dataset (`splitTrainSet`).</span></span> 

## <a name="extract-and-transform-the-data"></a><span data-ttu-id="db753-248">Извлечение и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="db753-248">Extract and transform the data</span></span>

<span data-ttu-id="db753-249">Предварительная обработка и очистка данных — это очень важные задачи, которые нужно выполнить перед использованием набора данных для машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="db753-249">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="db753-250">Необработанные данные часто содержат много шума, недостаточно надежны и в них могут быть пропуски.</span><span class="sxs-lookup"><span data-stu-id="db753-250">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="db753-251">Использование данных напрямую без этих задач моделирования может дать неправильные результаты.</span><span class="sxs-lookup"><span data-stu-id="db753-251">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="db753-252">Конвейеры преобразования ML.NET создают пользовательский набор преобразований, которые применяются к данным перед началом обучения или проверки.</span><span class="sxs-lookup"><span data-stu-id="db753-252">ML.NET's transform pipelines compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="db753-253">Основной целью преобразования является [присвоение признаков](../resources/glossary.md#feature-engineering).</span><span class="sxs-lookup"><span data-stu-id="db753-253">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="db753-254">Алгоритмы Машинного обучения определяют данные с [присвоенными признаками](../resources/glossary.md#feature), поэтому следующим шагом является преобразование текстовых данных в формат, который распознают наши алгоритмы Машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="db753-254">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="db753-255">Этот формат — [числовой вектор](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="db753-255">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="db753-256">Далее вызовите `mlContext.Transforms.Text.FeaturizeText`, который преобразовывает текстовый столбец (`SentimentText`) в числовой вектор под названием `Features`, используемый в алгоритмах Машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="db753-256">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text column (`SentimentText`) column into a numeric vector called `Features` used by the machine learning algorithm.</span></span> <span data-ttu-id="db753-257">Это вызов программы-оболочки, возвращающий <xref:Microsoft.ML.Data.EstimatorChain%601>, который фактически будет конвейером.</span><span class="sxs-lookup"><span data-stu-id="db753-257">This is a wrapper call that returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="db753-258">Присвойте ему имя `pipeline`, так как затем вы добавите обучающую систему в `EstimatorChain`.</span><span class="sxs-lookup"><span data-stu-id="db753-258">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="db753-259">Добавьте следующую строку кода:</span><span class="sxs-lookup"><span data-stu-id="db753-259">Add this as the next line of code:</span></span>

[!code-csharp[FeaturizeText](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#FeaturizeText "Featurize the text")]

>[!WARNING]
> <span data-ttu-id="db753-260">В ML.NET версии 0.10 изменился порядок параметров преобразования.</span><span class="sxs-lookup"><span data-stu-id="db753-260">ML.NET Version 0.10 changed the order of the Transform parameters.</span></span> <span data-ttu-id="db753-261">Процесс будет происходить без ошибок, пока вы не запустите приложение и не создадите модель.</span><span class="sxs-lookup"><span data-stu-id="db753-261">This will not error out until you run the application and build the model.</span></span> <span data-ttu-id="db753-262">Используйте имена параметров для преобразования, как показано в предыдущем фрагменте кода.</span><span class="sxs-lookup"><span data-stu-id="db753-262">Use the parameter names for Transforms as illustrated in the previous code snippet.</span></span>

<span data-ttu-id="db753-263">Это этап предварительной обработки и присвоения признаков.</span><span class="sxs-lookup"><span data-stu-id="db753-263">This is the preprocessing/featurization step.</span></span> <span data-ttu-id="db753-264">Дополнительные компоненты из ML.NET могут дать более точные результаты для вашей модели.</span><span class="sxs-lookup"><span data-stu-id="db753-264">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="db753-265">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="db753-265">Choose a learning algorithm</span></span>

<span data-ttu-id="db753-266">Чтобы добавить обучающую систему, вызовите метод программы-оболочки `mlContext.BinaryClassification.Trainers.FastTree`, возвращающий объект <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer>.</span><span class="sxs-lookup"><span data-stu-id="db753-266">To add the trainer, call the `mlContext.BinaryClassification.Trainers.FastTree` wrapper method which returns a <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer> object.</span></span> <span data-ttu-id="db753-267">Это средство обучения по дереву принятия решений, которое мы применим для нашего конвейера.</span><span class="sxs-lookup"><span data-stu-id="db753-267">This is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="db753-268">`FastTreeBinaryClassificationTrainer` добавляется в `pipeline` и принимает `SentimentText` с присвоенными признаками (`Features`) и входные параметры `Label`, чтобы пройти обучение по историческим данным.</span><span class="sxs-lookup"><span data-stu-id="db753-268">The `FastTreeBinaryClassificationTrainer` is appended to the `pipeline` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

<span data-ttu-id="db753-269">Добавьте следующий код в метод `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="db753-269">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[FastTreeBinaryClassificationTrainer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddTrainer "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="db753-270">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="db753-270">Train the model</span></span>

<span data-ttu-id="db753-271">Обучения модели <xref:Microsoft.ML.Data.TransformerChain%601> выполняется по набору данных, который вы ранее скачали и преобразовали.</span><span class="sxs-lookup"><span data-stu-id="db753-271">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="db753-272">После определения средства оценки вы обучите модель с помощью метода <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A>, предоставляя уже загруженные данные для обучения.</span><span class="sxs-lookup"><span data-stu-id="db753-272">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> method while providing the already loaded training data.</span></span> <span data-ttu-id="db753-273">В результате возвращается модель, необходимая для выполнения прогнозов.</span><span class="sxs-lookup"><span data-stu-id="db753-273">This returns a model to use for predictions.</span></span> <span data-ttu-id="db753-274">`pipeline.Fit()` обучает конвейер и возвращает `Transformer` на основе переданного типа `DataView`.</span><span class="sxs-lookup"><span data-stu-id="db753-274">`pipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="db753-275">Эксперимент не выполняется, пока метод `.Fit()` не запустится.</span><span class="sxs-lookup"><span data-stu-id="db753-275">The experiment is not executed until the `.Fit()` method runs.</span></span>

<span data-ttu-id="db753-276">Добавьте следующий код в метод `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="db753-276">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TrainModel "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="db753-277">Сохранение и возврат обученной модели для оценки</span><span class="sxs-lookup"><span data-stu-id="db753-277">Save and Return the model trained to use for evaluation</span></span>

<span data-ttu-id="db753-278">На этом этапе у вас есть модель типа <xref:Microsoft.ML.Data.TransformerChain%601>, которую можно интегрировать с любыми имеющимися или новыми приложениями .NET.</span><span class="sxs-lookup"><span data-stu-id="db753-278">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="db753-279">Выполните возврат модели в конце метода `BuildAndTrainModel`.</span><span class="sxs-lookup"><span data-stu-id="db753-279">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="db753-280">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="db753-280">Evaluate the model</span></span>

<span data-ttu-id="db753-281">Итак, вы завершили создание и обучение модели, и теперь ее можно оценить по другому набору данных, чтобы проверить ее точность и качество прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="db753-281">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="db753-282">В методе `Evaluate` передается для оценки модель, созданная в `BuildAndTrainModel`.</span><span class="sxs-lookup"><span data-stu-id="db753-282">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="db753-283">Создайте метод `Evaluate` сразу после метода `BuildAndTrainModel` как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="db753-283">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
{

}
```

<span data-ttu-id="db753-284">Метод `Evaluate` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="db753-284">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="db753-285">загрузка тестового набора данных;</span><span class="sxs-lookup"><span data-stu-id="db753-285">Loads the test dataset.</span></span>
* <span data-ttu-id="db753-286">создание средства оценки двоичной классификации;</span><span class="sxs-lookup"><span data-stu-id="db753-286">Creates the binaryclassification evaluator.</span></span>
* <span data-ttu-id="db753-287">оценка модели и создание метрик;</span><span class="sxs-lookup"><span data-stu-id="db753-287">Evaluates the model and creates metrics.</span></span>
* <span data-ttu-id="db753-288">отображение метрик.</span><span class="sxs-lookup"><span data-stu-id="db753-288">Displays the metrics.</span></span>

<span data-ttu-id="db753-289">Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `Train`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="db753-289">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallEvaluate "Call the Evaluate method")]

<span data-ttu-id="db753-290">Далее вы будете использовать параметр машинного обучения `model` (преобразователь) и параметр `splitTestSet` для ввода признаков и возврата прогнозов.</span><span class="sxs-lookup"><span data-stu-id="db753-290">Next, you'll use the machine learning `model` parameter (a transformer) and the `splitTestSet` parameter to input the features and return predictions.</span></span> <span data-ttu-id="db753-291">В качестве следующей строки в методе `Evaluate` добавьте приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="db753-291">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TransformData "Predict using the Transformer")]

<span data-ttu-id="db753-292">Метод `mlContext.BinaryClassification.Evaluate` вычисляет метрики качества для `PredictionModel` на основе указанного набора данных.</span><span class="sxs-lookup"><span data-stu-id="db753-292">The `mlContext.BinaryClassification.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="db753-293">Он возвращает объект <xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics>, содержащий общие метрики, вычисляемые с помощью средств оценки двоичной классификации.</span><span class="sxs-lookup"><span data-stu-id="db753-293">It returns a <xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics> object that contains the overall metrics computed by binary classification evaluators.</span></span> <span data-ttu-id="db753-294">Чтобы отобразить их для оценки качества модели, сначала метрики необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="db753-294">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="db753-295">Добавьте в следующую строку метода `Evaluate` приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="db753-295">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Evaluate "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="db753-296">Отображение метрик для проверки модели</span><span class="sxs-lookup"><span data-stu-id="db753-296">Displaying the metrics for model validation</span></span>

<span data-ttu-id="db753-297">Используйте следующий код для отображения метрик, передачи результатов и выполнения действий по ним:</span><span class="sxs-lookup"><span data-stu-id="db753-297">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayMetrics "Display selected metrics")]

<span data-ttu-id="db753-298">Чтобы сохранить модель в ZIP-файл, для вызова метода `SaveModelAsFile` добавьте в качестве следующей строки в `Evaluate` приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="db753-298">To save your model to a .zip file before returning, add the following code to call the `SaveModelAsFile` method as the next line in `Evaluate`:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallSaveModel "Save the model")]

## <a name="save-the-model-as-azip-file"></a><span data-ttu-id="db753-299">Сохранение модели в качестве ZIP-файла</span><span class="sxs-lookup"><span data-stu-id="db753-299">Save the model as a.zip file</span></span>

<span data-ttu-id="db753-300">Создайте метод `SaveModelAsFile` сразу после метода `Evaluate`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="db753-300">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="db753-301">Метод `SaveModelAsFile` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="db753-301">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="db753-302">сохранение модели в качестве ZIP-файла.</span><span class="sxs-lookup"><span data-stu-id="db753-302">Saves the model as a .zip file.</span></span>

<span data-ttu-id="db753-303">Далее создайте метод для сохранения модели, чтобы ее можно было использовать повторно, а также применять в других приложениях.</span><span class="sxs-lookup"><span data-stu-id="db753-303">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="db753-304">`ITransformer` содержит метод <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)>, который принимает глобальное поле `_modelPath`, и <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="db753-304">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="db753-305">Чтобы сохранить модель в качестве ZIP-файла, мы создадим `FileStream` непосредственно перед вызовом метода `SaveTo`.</span><span class="sxs-lookup"><span data-stu-id="db753-305">To save this as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="db753-306">В качестве следующей строки в методе `SaveModelAsFile` добавьте приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="db753-306">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SaveModel "Add the SaveTo Method")]

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="db753-307">Развертывание и прогнозирование с помощью загруженной модели</span><span class="sxs-lookup"><span data-stu-id="db753-307">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="db753-308">Вы также можете просмотреть, куда был записан файл, написав консольное сообщение с `_modelPath`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="db753-308">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a><span data-ttu-id="db753-309">Прогнозирование результатов для тестовых данных с помощью сохраненной модели</span><span class="sxs-lookup"><span data-stu-id="db753-309">Predict the test data outcome with the saved model</span></span>

<span data-ttu-id="db753-310">Создайте метод `UseModelWithSingleItem` сразу после метода `Evaluate`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="db753-310">Create the `UseModelWithSingleItem` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="db753-311">Метод `UseModelWithSingleItem` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="db753-311">The `UseModelWithSingleItem` method executes the following tasks:</span></span>

* <span data-ttu-id="db753-312">создание отдельного комментария тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="db753-312">Creates a single comment of test data.</span></span>
* <span data-ttu-id="db753-313">прогноз тональности на основе тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="db753-313">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="db753-314">объединение тестовых данных и прогнозов для создания отчетов;</span><span class="sxs-lookup"><span data-stu-id="db753-314">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="db753-315">отображение результатов прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="db753-315">Displays the predicted results.</span></span>

<span data-ttu-id="db753-316">Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `Evaluate`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="db753-316">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallUseModelWithSingleItem](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

<span data-ttu-id="db753-317">Несмотря на то что `model` представляет собой `transformer`, который обрабатывает многочисленные строки данных, достаточно распространенным сценарием рабочей среды является прогнозирование на основе отдельных примеров.</span><span class="sxs-lookup"><span data-stu-id="db753-317">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="db753-318"><xref:Microsoft.ML.PredictionEngine%602> — это программа-оболочка, возвращаемая из метода `CreatePredictionEngine`.</span><span class="sxs-lookup"><span data-stu-id="db753-318">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="db753-319">Давайте добавим следующий код в качестве первой строки в методе `Predict` для создания `PredictionEngine`:</span><span class="sxs-lookup"><span data-stu-id="db753-319">Let's add the following code to create the `PredictionEngine` as the first line in the `Predict` Method:</span></span>

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]
  
<span data-ttu-id="db753-320">Добавьте комментарий для проверки прогнозирования обученной модели в методе `Predict`, создав экземпляр `SentimentData`:</span><span class="sxs-lookup"><span data-stu-id="db753-320">Add a comment to test the trained model's prediction in the `Predict` method by creating an instance of `SentimentData`:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

 <span data-ttu-id="db753-321">Это можно использовать для прогнозирования положительной или отрицательной тональности одного экземпляра данных комментария.</span><span class="sxs-lookup"><span data-stu-id="db753-321">You can use that to predict the positive or negative sentiment of a single instance of the comment data.</span></span> <span data-ttu-id="db753-322">Чтобы получить прогноз, примените <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> для данных.</span><span class="sxs-lookup"><span data-stu-id="db753-322">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="db753-323">Обратите внимание, что входные данные имеют строковый формат, а модель выполняет присвоение признаков.</span><span class="sxs-lookup"><span data-stu-id="db753-323">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="db753-324">Конвейер синхронизируется во время обучения и прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="db753-324">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="db753-325">Вам не нужно писать для прогнозирования отдельный код предварительной обработки и присвоения признаков. Кроме того, этот API выполняет как пакетное, так и разовое прогнозирование.</span><span class="sxs-lookup"><span data-stu-id="db753-325">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Predict "Create a prediction of sentiment")]

### <a name="use-the-model-prediction"></a><span data-ttu-id="db753-326">Использование модели. Прогнозирование</span><span class="sxs-lookup"><span data-stu-id="db753-326">Use the model: prediction</span></span>

<span data-ttu-id="db753-327">Отобразите `SentimentText` и соответствующие прогнозы тональности, чтобы поделиться результатами и выполнить соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="db753-327">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="db753-328">Этот этап называется вводом в эксплуатацию, после которого возвращаемые данные можно включить в операционные политики.</span><span class="sxs-lookup"><span data-stu-id="db753-328">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="db753-329">Создайте отображение для результатов с помощью следующего кода <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="db753-329">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#OutputPrediction "Display prediction output")]

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="db753-330">Развертывание и прогнозирование с помощью загруженной модели</span><span class="sxs-lookup"><span data-stu-id="db753-330">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="db753-331">Создайте метод `UseLoadedModelWithBatchItems` непосредственно перед методом `SaveModelAsFile`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="db753-331">Create the `UseLoadedModelWithBatchItems` method, just before the `SaveModelAsFile` method, using the following code:</span></span>

```csharp
public static void UseLoadedModelWithBatchItems(MLContext mlContext)
{

}
```

<span data-ttu-id="db753-332">Метод `UseLoadedModelWithBatchItems` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="db753-332">The `UseLoadedModelWithBatchItems` method executes the following tasks:</span></span>

* <span data-ttu-id="db753-333">создание пакетных тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="db753-333">Creates batch test data.</span></span>
* <span data-ttu-id="db753-334">прогноз тональности на основе тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="db753-334">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="db753-335">объединение тестовых данных и прогнозов для создания отчетов;</span><span class="sxs-lookup"><span data-stu-id="db753-335">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="db753-336">отображение результатов прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="db753-336">Displays the predicted results.</span></span>

<span data-ttu-id="db753-337">Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `UseModelWithSingleItem`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="db753-337">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem` method call, using the following code:</span></span>

[!code-csharp[CallPredictModelLoaded](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseLoadedModelWithBatchItems "Call the CallUseLoadedModelWithBatchItems method")]

<span data-ttu-id="db753-338">Добавьте новые комментарии, чтобы проверить прогнозы обученной модели, в метод `UseLoadedModelWithBatchItems`:</span><span class="sxs-lookup"><span data-stu-id="db753-338">Add some comments to test the trained model's predictions in the `UseLoadedModelWithBatchItems` method:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssues "Create test data for predictions")]

<span data-ttu-id="db753-339">Загрузите модель</span><span class="sxs-lookup"><span data-stu-id="db753-339">Load the model</span></span>

[!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadModel "Load the model")]

<span data-ttu-id="db753-340">Теперь у вас есть готовая модель, и ее можно использовать для прогнозирования токсичной или нетоксичной тональности по данным комментариев с помощью метода <xref:Microsoft.ML.ITransformer.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="db753-340">Now that you have a model, you can use that to predict the Toxic or Non Toxic sentiment of the comment data using the <xref:Microsoft.ML.ITransformer.Transform%2A> method.</span></span> <span data-ttu-id="db753-341">Чтобы получить прогноз, примените `Predict` для новых данных.</span><span class="sxs-lookup"><span data-stu-id="db753-341">To get a prediction, use `Predict` on new data.</span></span> <span data-ttu-id="db753-342">Обратите внимание, что входные данные имеют строковый формат, а модель выполняет присвоение признаков.</span><span class="sxs-lookup"><span data-stu-id="db753-342">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="db753-343">Конвейер синхронизируется во время обучения и прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="db753-343">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="db753-344">Вам не нужно писать для прогнозирования отдельный код предварительной обработки и присвоения признаков. Кроме того, этот API выполняет как пакетное, так и разовое прогнозирование.</span><span class="sxs-lookup"><span data-stu-id="db753-344">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="db753-345">Добавьте в метод `UseLoadedModelWithBatchItems` приведенный ниже код для прогнозирования:</span><span class="sxs-lookup"><span data-stu-id="db753-345">Add the following code to the `UseLoadedModelWithBatchItems` method for the predictions:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="use-the-loaded-model-for-prediction"></a><span data-ttu-id="db753-346">Использование загруженной модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="db753-346">Use the loaded model for prediction</span></span>

<span data-ttu-id="db753-347">Отобразите `SentimentText` и соответствующие прогнозы тональности, чтобы поделиться результатами и выполнить соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="db753-347">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="db753-348">Этот этап называется вводом в эксплуатацию, после которого возвращаемые данные можно включить в операционные политики.</span><span class="sxs-lookup"><span data-stu-id="db753-348">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="db753-349">Создайте заголовок для результатов с помощью следующего кода <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="db753-349">Create a header for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="db753-350">Перед отображением результатов прогнозирования объедините данные о тональности с прогнозами, чтобы просмотреть исходные комментарии и прогнозы тональности.</span><span class="sxs-lookup"><span data-stu-id="db753-350">Before displaying the predicted results, combine the sentiment and prediction together to see the original comment with its predicted sentiment.</span></span> <span data-ttu-id="db753-351">В следующем коде для этого используется метод <xref:System.Linq.Enumerable.Zip%2A>, а после него нужно добавить следующий код:</span><span class="sxs-lookup"><span data-stu-id="db753-351">The following code uses the <xref:System.Linq.Enumerable.Zip%2A> method to make that happen, so add that code next:</span></span>

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#BuildSentimentPredictionPairs "Build the pairs of sentiment data and predictions")]

<span data-ttu-id="db753-352">Теперь, когда вы объединили в один класс `SentimentText` и `Sentiment`, можно отобразить результаты с помощью метода <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="db753-352">Now that you've combined the `SentimentText` and `Sentiment` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayResults "Display the predictions")]

<span data-ttu-id="db753-353">Так как выводимые имена элементов кортежа появились только в C# версии 7.1, а для этого проекта по умолчанию устанавливается версия языка C# 7.0, необходимо изменить это значение до C# 7.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="db753-353">Because inferred tuple element names are a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="db753-354">Для этого в **обозревателе решений** щелкните узел проекта правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="db753-354">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="db753-355">Откройте вкладку **Сборка** и нажмите на кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="db753-355">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="db753-356">В раскрывающемся списке выберите **C# 7.1** (или более позднюю версию).</span><span class="sxs-lookup"><span data-stu-id="db753-356">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="db753-357">Нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="db753-357">Select the **OK** button.</span></span>

## <a name="results"></a><span data-ttu-id="db753-358">Результаты</span><span class="sxs-lookup"><span data-stu-id="db753-358">Results</span></span>

<span data-ttu-id="db753-359">Результаты выполнения должны выглядеть примерно так, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="db753-359">Your results should be similar to the following.</span></span> <span data-ttu-id="db753-360">В процессе работы конвейер выводит сообщения.</span><span class="sxs-lookup"><span data-stu-id="db753-360">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="db753-361">Вы можете видеть предупреждения или обработанные сообщения.</span><span class="sxs-lookup"><span data-stu-id="db753-361">You may see warnings, or processing messages.</span></span> <span data-ttu-id="db753-362">Для удобства они удалены из следующих результатов.</span><span class="sxs-lookup"><span data-stu-id="db753-362">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 79.14%
Auc: 86.27%
F1Score: 80.60%

=============== End of model evaluation ===============
The model is saved to C:\Tutorials\SentimentAnalysis\bin\Debug\netcoreapp2.1\Data\Model.zip

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.4641322
=============== End of Predictions ===============


=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1391833
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9819039
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

<span data-ttu-id="db753-363">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="db753-363">Congratulations!</span></span> <span data-ttu-id="db753-364">Вы успешно создали модель машинного обучения для классификации и прогнозирования тональности сообщений.</span><span class="sxs-lookup"><span data-stu-id="db753-364">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span> 

<span data-ttu-id="db753-365">Построение успешных моделей — итеративный процесс.</span><span class="sxs-lookup"><span data-stu-id="db753-365">Building successful models is an iterative process.</span></span> <span data-ttu-id="db753-366">Изначально эта модель имеет низкое качество, так как в руководстве используются небольшие наборы данных для быстрого обучения.</span><span class="sxs-lookup"><span data-stu-id="db753-366">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="db753-367">Если вам требуется модель более высокого качества, можно попытаться улучшить ее, использовав более крупные наборы данных для обучения или выбрав другие алгоритмы обучения с разными гиперпараметрами для каждого алгоритма.</span><span class="sxs-lookup"><span data-stu-id="db753-367">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different hyper-parameters for each algorithm.</span></span>

<span data-ttu-id="db753-368">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="db753-368">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="db753-369">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="db753-369">Next steps</span></span>

<span data-ttu-id="db753-370">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="db753-370">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="db753-371">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="db753-371">Understand the problem</span></span>
> * <span data-ttu-id="db753-372">Выбор подходящего алгоритма машинного обучения</span><span class="sxs-lookup"><span data-stu-id="db753-372">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="db753-373">подготавливать данные;</span><span class="sxs-lookup"><span data-stu-id="db753-373">Prepare your data</span></span>
> * <span data-ttu-id="db753-374">Преобразование данных</span><span class="sxs-lookup"><span data-stu-id="db753-374">Transform the data</span></span>
> * <span data-ttu-id="db753-375">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="db753-375">Train the model</span></span>
> * <span data-ttu-id="db753-376">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="db753-376">Evaluate the model</span></span>
> * <span data-ttu-id="db753-377">Прогнозирование с помощью обученной модели</span><span class="sxs-lookup"><span data-stu-id="db753-377">Predict with the trained model</span></span>
> * <span data-ttu-id="db753-378">Развертывание и прогнозирование с помощью загруженной модели</span><span class="sxs-lookup"><span data-stu-id="db753-378">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="db753-379">Переходите к следующему руководству:</span><span class="sxs-lookup"><span data-stu-id="db753-379">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="db753-380">Классификация задач</span><span class="sxs-lookup"><span data-stu-id="db753-380">Issue Classification</span></span>](github-issue-classification.md)
