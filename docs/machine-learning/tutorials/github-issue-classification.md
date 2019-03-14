---
title: Использование ML.NET для сценариев многоклассовой классификации задач GitHub
description: Узнайте, как использовать ML.NET для сценариев многоклассовой классификации, чтобы назначать задачи GitHub определенным областям.
ms.date: 02/20/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 4f6a95fbd470c688c977b406d1813d6a453e8a79
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471493"
---
# <a name="tutorial-use-mlnet-in-a-multiclass-classification-scenario-to-classify-github-issues"></a><span data-ttu-id="2fa77-103">Учебник. Использование ML.NET для сценариев многоклассовой классификации задач GitHub</span><span class="sxs-lookup"><span data-stu-id="2fa77-103">Tutorial: Use ML.NET in a multiclass classification scenario to classify GitHub issues</span></span>

<span data-ttu-id="2fa77-104">В этом практическом руководстве демонстрируется создание классификатора задач GitHub с помощью ML.NET в консольном приложении .NET Core на языке C# в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="2fa77-104">This sample tutorial illustrates using ML.NET to create a GitHub issue classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="2fa77-105">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="2fa77-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="2fa77-106">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="2fa77-106">Understand the problem</span></span>
> * <span data-ttu-id="2fa77-107">Выбор подходящего алгоритма машинного обучения</span><span class="sxs-lookup"><span data-stu-id="2fa77-107">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="2fa77-108">подготавливать данные;</span><span class="sxs-lookup"><span data-stu-id="2fa77-108">Prepare your data</span></span>
> * <span data-ttu-id="2fa77-109">Преобразование данных</span><span class="sxs-lookup"><span data-stu-id="2fa77-109">Transform the data</span></span>
> * <span data-ttu-id="2fa77-110">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="2fa77-110">Train the model</span></span>
> * <span data-ttu-id="2fa77-111">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="2fa77-111">Evaluate the model</span></span>
> * <span data-ttu-id="2fa77-112">Прогнозирование с помощью обученной модели</span><span class="sxs-lookup"><span data-stu-id="2fa77-112">Predict with the trained model</span></span>
> * <span data-ttu-id="2fa77-113">Развертывание и прогнозирование с помощью загруженной модели</span><span class="sxs-lookup"><span data-stu-id="2fa77-113">Deploy and Predict with a loaded model</span></span>

> [!NOTE]
> <span data-ttu-id="2fa77-114">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="2fa77-114">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="2fa77-115">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="2fa77-115">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="2fa77-116">Сейчас в этом руководстве и соответствующем примере используется **ML.NET версии 0.10**.</span><span class="sxs-lookup"><span data-stu-id="2fa77-116">This tutorial and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="2fa77-117">Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="2fa77-117">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="github-issue-sample-overview"></a><span data-ttu-id="2fa77-118">Обзор примера задачи GitHub</span><span class="sxs-lookup"><span data-stu-id="2fa77-118">GitHub issue sample overview</span></span>

<span data-ttu-id="2fa77-119">Пример представляет собой консольное приложение, использующее ML.NET для обучения модели, которая классифицирует и прогнозирует метку области для задачи GitHub.</span><span class="sxs-lookup"><span data-stu-id="2fa77-119">The sample is a console app that uses ML.NET to train a model that classifies and predicts the Area label for a GitHub issue.</span></span> <span data-ttu-id="2fa77-120">Также оно оценивает качество модели по второму набору данных.</span><span class="sxs-lookup"><span data-stu-id="2fa77-120">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="2fa77-121">Наборы данных для задачи взяты из GitHub-репозитория dotnet/corefx.</span><span class="sxs-lookup"><span data-stu-id="2fa77-121">The issue datasets are from the dotnet/corefx GitHub repo.</span></span>

<span data-ttu-id="2fa77-122">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="2fa77-122">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2fa77-123">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2fa77-123">Prerequisites</span></span>

* <span data-ttu-id="2fa77-124">[Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="2fa77-124">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="2fa77-125">[Файл задач GitHub с разделением знаками табуляции (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span><span class="sxs-lookup"><span data-stu-id="2fa77-125">The [Github issues tab separated file (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span></span>
* <span data-ttu-id="2fa77-126">[Файл с тестовыми данными задач GitHub с разделением знаками табуляции (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span><span class="sxs-lookup"><span data-stu-id="2fa77-126">The [Github issues test tab separated file (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="2fa77-127">Рабочий процесс машинного обучения</span><span class="sxs-lookup"><span data-stu-id="2fa77-127">Machine learning workflow</span></span>

<span data-ttu-id="2fa77-128">В этом руководстве используется рабочий процесс машинного обучения, который определяет порядок выполнения действий в процессе.</span><span class="sxs-lookup"><span data-stu-id="2fa77-128">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="2fa77-129">Вот основные этапы этого рабочего процесса:</span><span class="sxs-lookup"><span data-stu-id="2fa77-129">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="2fa77-130">**определение проблемы**;</span><span class="sxs-lookup"><span data-stu-id="2fa77-130">**Understand the problem**</span></span>
2. <span data-ttu-id="2fa77-131">**Подготовка данных**.</span><span class="sxs-lookup"><span data-stu-id="2fa77-131">**Prepare your data**</span></span>
   * <span data-ttu-id="2fa77-132">**Загрузка данных**.</span><span class="sxs-lookup"><span data-stu-id="2fa77-132">**Load the data**</span></span>
   * <span data-ttu-id="2fa77-133">**Извлечение компонентов (преобразование данных)**.</span><span class="sxs-lookup"><span data-stu-id="2fa77-133">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="2fa77-134">**Сборка и обучение**.</span><span class="sxs-lookup"><span data-stu-id="2fa77-134">**Build and train**</span></span> 
   * <span data-ttu-id="2fa77-135">**Обучение модели**.</span><span class="sxs-lookup"><span data-stu-id="2fa77-135">**Train the model**</span></span>
   * <span data-ttu-id="2fa77-136">**оценка модели**;</span><span class="sxs-lookup"><span data-stu-id="2fa77-136">**Evaluate the model**</span></span>
4. <span data-ttu-id="2fa77-137">**Развертывание модели**</span><span class="sxs-lookup"><span data-stu-id="2fa77-137">**Deploy Model**</span></span>
   * <span data-ttu-id="2fa77-138">**Использование модели для прогнозирования**</span><span class="sxs-lookup"><span data-stu-id="2fa77-138">**Use the Model to predict**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="2fa77-139">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="2fa77-139">Understand the problem</span></span>

<span data-ttu-id="2fa77-140">Прежде всего необходимо понять суть проблемы, что позволит разбить ее на отдельные фрагменты для построения и обучения модели.</span><span class="sxs-lookup"><span data-stu-id="2fa77-140">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="2fa77-141">Разделение проблемы на составляющие позволяет прогнозировать и оценивать результаты.</span><span class="sxs-lookup"><span data-stu-id="2fa77-141">Breaking  down the problem allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="2fa77-142">Рассматриваемая в этом руководстве проблема: определить, к какой области относятся входящие задачи GitHub, чтобы корректно помечать их для дальнейшей приоритизации и планирования.</span><span class="sxs-lookup"><span data-stu-id="2fa77-142">The problem for this tutorial is to understand what area incoming GitHub issues belong to in order to label them correctly for prioritization and scheduling.</span></span>

<span data-ttu-id="2fa77-143">Проблему можно разделить на следующие части:</span><span class="sxs-lookup"><span data-stu-id="2fa77-143">You can break down the problem to the following parts:</span></span>

* <span data-ttu-id="2fa77-144">текст названия задачи;</span><span class="sxs-lookup"><span data-stu-id="2fa77-144">the issue title text</span></span>
* <span data-ttu-id="2fa77-145">текст описания задачи;</span><span class="sxs-lookup"><span data-stu-id="2fa77-145">the issue description text</span></span>
* <span data-ttu-id="2fa77-146">значение области для обучающих данных модели;</span><span class="sxs-lookup"><span data-stu-id="2fa77-146">an area value for the model training data</span></span>
* <span data-ttu-id="2fa77-147">прогнозируемое значение области, которое можно оценить и затем использовать на практике.</span><span class="sxs-lookup"><span data-stu-id="2fa77-147">a predicted area value that you can evaluate and then use operationally</span></span>

<span data-ttu-id="2fa77-148">После этого нужно **определить** область, что поможет выбрать задачу машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="2fa77-148">You then need to **determine** the area, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="2fa77-149">Выбор подходящего алгоритма машинного обучения</span><span class="sxs-lookup"><span data-stu-id="2fa77-149">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="2fa77-150">Для этой проблемы вам известны следующие факты.</span><span class="sxs-lookup"><span data-stu-id="2fa77-150">With this problem, you know the following facts:</span></span>

<span data-ttu-id="2fa77-151">Обучающие данные</span><span class="sxs-lookup"><span data-stu-id="2fa77-151">Training data:</span></span>

<span data-ttu-id="2fa77-152">Задачам GitHub можно присваивать метки в нескольких областях (**Area**), как в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="2fa77-152">GitHub issues can be labeled in several areas (**Area**) as in the following examples:</span></span>

* <span data-ttu-id="2fa77-153">area-System.Numerics</span><span class="sxs-lookup"><span data-stu-id="2fa77-153">area-System.Numerics</span></span>
* <span data-ttu-id="2fa77-154">area-System.Xml</span><span class="sxs-lookup"><span data-stu-id="2fa77-154">area-System.Xml</span></span>
* <span data-ttu-id="2fa77-155">area-Infrastructure</span><span class="sxs-lookup"><span data-stu-id="2fa77-155">area-Infrastructure</span></span>
* <span data-ttu-id="2fa77-156">area-System.Linq</span><span class="sxs-lookup"><span data-stu-id="2fa77-156">area-System.Linq</span></span>
* <span data-ttu-id="2fa77-157">area-System.IO</span><span class="sxs-lookup"><span data-stu-id="2fa77-157">area-System.IO</span></span>

<span data-ttu-id="2fa77-158">Вы можете спрогнозировать **область** новой задачи GitHub, как в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="2fa77-158">Predict the **Area** of a new GitHub Issue such as in the following examples:</span></span>

* <span data-ttu-id="2fa77-159">Contract.Assert и Debug.Assert</span><span class="sxs-lookup"><span data-stu-id="2fa77-159">Contract.Assert vs Debug.Assert</span></span>
* <span data-ttu-id="2fa77-160">Защита полей от записи в System.Xml</span><span class="sxs-lookup"><span data-stu-id="2fa77-160">Make fields readonly in System.Xml</span></span>

<span data-ttu-id="2fa77-161">Для этого сценария лучше всего подходит алгоритм классификации в машинном обучении.</span><span class="sxs-lookup"><span data-stu-id="2fa77-161">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-learning-algorithm"></a><span data-ttu-id="2fa77-162">Об алгоритме обучения классификации</span><span class="sxs-lookup"><span data-stu-id="2fa77-162">About the classification learning algorithm</span></span>

<span data-ttu-id="2fa77-163">Классификацией называют алгоритм машинного обучения, который использует данные для **определения** категории, типа или класса для некоторого элемента или ряда данных.</span><span class="sxs-lookup"><span data-stu-id="2fa77-163">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="2fa77-164">Например, классификацию можно использовать для следующих действий:</span><span class="sxs-lookup"><span data-stu-id="2fa77-164">For example, you can use classification to:</span></span>

* <span data-ttu-id="2fa77-165">определение положительной или отрицательной тональности;</span><span class="sxs-lookup"><span data-stu-id="2fa77-165">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="2fa77-166">сортировка сообщений электронной почты на спам, нежелательную почту и нужные сообщения;</span><span class="sxs-lookup"><span data-stu-id="2fa77-166">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="2fa77-167">диагностика раковых заболеваний по лабораторным пробам, взятых у пациентов;</span><span class="sxs-lookup"><span data-stu-id="2fa77-167">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="2fa77-168">распределение клиентов по категориям с разной готовностью реагировать на рекламную акцию.</span><span class="sxs-lookup"><span data-stu-id="2fa77-168">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="2fa77-169">Варианты использования обучающих алгоритмов классификации обычно относятся к одному из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="2fa77-169">Classification learning algorithm use cases are frequently one of the following types:</span></span>

* <span data-ttu-id="2fa77-170">Двоичная: A или B.</span><span class="sxs-lookup"><span data-stu-id="2fa77-170">Binary: either A or B.</span></span>
* <span data-ttu-id="2fa77-171">Многоклассовая: несколько категорий, которые прогнозируются по одной модели.</span><span class="sxs-lookup"><span data-stu-id="2fa77-171">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="2fa77-172">Для таких проблем используйте обучающий алгоритм многоклассовой классификации, поскольку прогноз категории проблемы может относиться к нескольким категориям (многоклассовая), а не только к двум (двоичная).</span><span class="sxs-lookup"><span data-stu-id="2fa77-172">For this type of problem, use a Multiclass classification learning algorithm, since your issue category prediction can be one of multiple categories (multiclass) rather than just two (binary).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="2fa77-173">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="2fa77-173">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="2fa77-174">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="2fa77-174">Create a project</span></span>

1. <span data-ttu-id="2fa77-175">Откройте Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="2fa77-175">Open Visual Studio 2017.</span></span> <span data-ttu-id="2fa77-176">Выберите **Файл** > **Создать** > **Проект** в меню.</span><span class="sxs-lookup"><span data-stu-id="2fa77-176">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="2fa77-177">В диалоговом окне **Новый проект** выберите узел **Visual C#**, а затем — узел **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="2fa77-177">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="2fa77-178">Выберите шаблон проекта **Консольное приложение (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="2fa77-178">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="2fa77-179">В текстовое поле **Имя** введите GitHubIssueClassification, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2fa77-179">In the **Name** text box, type "GitHubIssueClassification" and then select the **OK** button.</span></span>

2. <span data-ttu-id="2fa77-180">Создайте каталог с именем *Data* в папке проекта, чтобы сохранить в нем файлы с наборами данных:</span><span class="sxs-lookup"><span data-stu-id="2fa77-180">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="2fa77-181">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="2fa77-181">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="2fa77-182">Введите имя папки Data и нажмите клавишу "ВВОД".</span><span class="sxs-lookup"><span data-stu-id="2fa77-182">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="2fa77-183">Создайте каталог с именем *Models* в папке проекта, чтобы сохранить модель:</span><span class="sxs-lookup"><span data-stu-id="2fa77-183">Create a directory named *Models* in your project to save your model:</span></span>

    <span data-ttu-id="2fa77-184">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="2fa77-184">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="2fa77-185">Введите "Models" и нажмите ВВОД.</span><span class="sxs-lookup"><span data-stu-id="2fa77-185">Type "Models" and hit Enter.</span></span>

4. <span data-ttu-id="2fa77-186">Установите **пакет NuGet для Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="2fa77-186">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="2fa77-187">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="2fa77-187">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="2fa77-188">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="2fa77-188">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="2fa77-189">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="2fa77-189">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="2fa77-190">подготавливать данные;</span><span class="sxs-lookup"><span data-stu-id="2fa77-190">Prepare your data</span></span>

1. <span data-ttu-id="2fa77-191">Скачайте наборы данных [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) и [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) и сохраните их в ранее созданную папку *Data*.</span><span class="sxs-lookup"><span data-stu-id="2fa77-191">Download the [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) and the [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="2fa77-192">Первый из этих наборов данных обучает модель машинного обучения, а второй позволяет оценить точность полученной модели.</span><span class="sxs-lookup"><span data-stu-id="2fa77-192">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="2fa77-193">В обозревателе решений щелкните правой кнопкой мыши каждый из файлов \*.tsv и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="2fa77-193">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="2fa77-194">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="2fa77-194">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="2fa77-195">Создание классов и определение путей</span><span class="sxs-lookup"><span data-stu-id="2fa77-195">Create classes and define paths</span></span>

<span data-ttu-id="2fa77-196">Добавьте следующие новые операторы `using` в начало файла *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="2fa77-196">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddUsings)]

<span data-ttu-id="2fa77-197">Создайте три глобальных поля для хранения путей к недавно скачанным файлам и глобальные переменные для `MLContext`, `DataView`, `PredictionEngine` и `TextLoader`:</span><span class="sxs-lookup"><span data-stu-id="2fa77-197">Create three global fields to hold the paths to the recently downloaded files, and global variables for the `MLContext`,`DataView`, `PredictionEngine`, and `TextLoader`:</span></span>

* <span data-ttu-id="2fa77-198">`_trainDataPath` содержит путь к набору данных, используемому для обучения модели;</span><span class="sxs-lookup"><span data-stu-id="2fa77-198">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="2fa77-199">`_testDataPath` содержит путь к набору данных, используемому для оценки модели;</span><span class="sxs-lookup"><span data-stu-id="2fa77-199">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="2fa77-200">`_modelPath` содержит путь, по которому сохраняется обученная модель.</span><span class="sxs-lookup"><span data-stu-id="2fa77-200">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="2fa77-201">`_mlContext` соответствует классу <xref:Microsoft.ML.MLContext>, предоставляющему контекст для обработки;</span><span class="sxs-lookup"><span data-stu-id="2fa77-201">`_mlContext` is the <xref:Microsoft.ML.MLContext> that provides processing context.</span></span>
* <span data-ttu-id="2fa77-202">`_trainingDataView` представляет собой интерфейс <xref:Microsoft.Data.DataView.IDataView>, используемый для обработки обучающего набора данных;</span><span class="sxs-lookup"><span data-stu-id="2fa77-202">`_trainingDataView` is the <xref:Microsoft.Data.DataView.IDataView> used to process the training dataset.</span></span>
* <span data-ttu-id="2fa77-203">`_predEngine` соответствует классу <xref:Microsoft.ML.PredictionEngine%602>, используемому для одиночных прогнозов;</span><span class="sxs-lookup"><span data-stu-id="2fa77-203">`_predEngine` is the <xref:Microsoft.ML.PredictionEngine%602> used for single predictions.</span></span>
* <span data-ttu-id="2fa77-204">`_reader` представляет собой <xref:Microsoft.ML.Data.TextLoader>, используемый для загрузки и преобразования наборов данных.</span><span class="sxs-lookup"><span data-stu-id="2fa77-204">`_reader` is the <xref:Microsoft.ML.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="2fa77-205">Добавьте следующий код в строку непосредственно над методом `Main`, чтобы указать эти пути и другие переменные:</span><span class="sxs-lookup"><span data-stu-id="2fa77-205">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="2fa77-206">Создайте несколько классов для входных данных и прогнозов.</span><span class="sxs-lookup"><span data-stu-id="2fa77-206">Create some classes for your input data and predictions.</span></span> <span data-ttu-id="2fa77-207">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="2fa77-207">Add a new class to your project:</span></span>

1. <span data-ttu-id="2fa77-208">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="2fa77-208">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="2fa77-209">В диалоговом окне **Добавление нового элемента** выберите **Класс** и в поле **Имя** укажите *GitHubIssueData.cs*.</span><span class="sxs-lookup"><span data-stu-id="2fa77-209">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *GitHubIssueData.cs*.</span></span> <span data-ttu-id="2fa77-210">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2fa77-210">Then, select the **Add** button.</span></span>

    <span data-ttu-id="2fa77-211">Файл *GitHubIssueData.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="2fa77-211">The *GitHubIssueData.cs* file opens in the code editor.</span></span> <span data-ttu-id="2fa77-212">Добавьте следующий оператор `using` в начало файла *GitHubIssueData.cs*:</span><span class="sxs-lookup"><span data-stu-id="2fa77-212">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#AddUsings)]

<span data-ttu-id="2fa77-213">Удалите из файла *GitHubIssueData.cs* существующее определение класса и добавьте следующий код с двумя классами `GitHubIssue` и `IssuePrediction`:</span><span class="sxs-lookup"><span data-stu-id="2fa77-213">Remove the existing class definition and add the following code, which has two classes `GitHubIssue` and `IssuePrediction`, to the *GitHubIssueData.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#DeclareTypes)]

<span data-ttu-id="2fa77-214">`GitHubIssue` является классом входного набора данных и имеет следующие поля <xref:System.String>:</span><span class="sxs-lookup"><span data-stu-id="2fa77-214">`GitHubIssue` is the input dataset class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="2fa77-215">`ID` содержит значение идентификатора задачи GitHub.</span><span class="sxs-lookup"><span data-stu-id="2fa77-215">`ID` contains a value for the GitHub issue ID</span></span>
* <span data-ttu-id="2fa77-216">`Area` содержит значение метки `Area`.</span><span class="sxs-lookup"><span data-stu-id="2fa77-216">`Area` contains a value for the `Area` label</span></span>
* <span data-ttu-id="2fa77-217">`Title` содержит название задачи GitHub.</span><span class="sxs-lookup"><span data-stu-id="2fa77-217">`Title` contains the GitHub issue title</span></span>
* <span data-ttu-id="2fa77-218">`Description` содержит описание задачи GitHub.</span><span class="sxs-lookup"><span data-stu-id="2fa77-218">`Description` contains the GitHub issue description</span></span>

<span data-ttu-id="2fa77-219">Класс `IssuePrediction` используется для прогнозирования после обучения модели.</span><span class="sxs-lookup"><span data-stu-id="2fa77-219">`IssuePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="2fa77-220">Он имеет один параметр типа `string` (`Area`) и атрибут `PredictedLabel` `ColumnName`.</span><span class="sxs-lookup"><span data-stu-id="2fa77-220">It has a single `string` (`Area`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="2fa77-221">`Label` используется для создания и обучения модели, а также для оценки модели по второму набору данных.</span><span class="sxs-lookup"><span data-stu-id="2fa77-221">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="2fa77-222">`PredictedLabel` используется для прогнозирования и оценки.</span><span class="sxs-lookup"><span data-stu-id="2fa77-222">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="2fa77-223">Для оценки применяются входные обучающие данные, прогнозируемые значения и модель.</span><span class="sxs-lookup"><span data-stu-id="2fa77-223">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="2fa77-224">При создании модели с использованием ML.NET сначала необходимо создать <xref:Microsoft.ML.MLContext>.</span><span class="sxs-lookup"><span data-stu-id="2fa77-224">When building a model with ML.NET, you start by creating an <xref:Microsoft.ML.MLContext>.</span></span> <span data-ttu-id="2fa77-225">Концептуально `MLContext` сопоставимо с использованием `DbContext` в Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="2fa77-225">`MLContext` is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="2fa77-226">Среда предоставляет контекст для вашего задания Машинного обучения, который можно использовать для отслеживания исключений и ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="2fa77-226">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="2fa77-227">Инициализация переменных в методе Main</span><span class="sxs-lookup"><span data-stu-id="2fa77-227">Initialize variables in Main</span></span>

<span data-ttu-id="2fa77-228">Инициализируйте глобальную переменную `_mlContext` в новом экземпляре `MLContext` со случайным начальным значением (`seed: 0`) для получения воспроизводимых и детерминированных результатов при множестве циклов обучения.</span><span class="sxs-lookup"><span data-stu-id="2fa77-228">Initialize the `_mlContext` global variable  with a new instance of `MLContext` with a random seed (`seed: 0`) for repeatable/deterministic results across multiple trainings.</span></span>  <span data-ttu-id="2fa77-229">Замените строку `Console.WriteLine("Hello World!")` в методе `Main` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="2fa77-229">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a><span data-ttu-id="2fa77-230">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="2fa77-230">Load the data</span></span>

<span data-ttu-id="2fa77-231">Затем инициализируйте глобальную переменную `_trainingDataView` <xref:Microsoft.Data.DataView.IDataView> и загрузите данные с параметром `_trainDataPath`.</span><span class="sxs-lookup"><span data-stu-id="2fa77-231">Next, initialize the `_trainingDataView` <xref:Microsoft.Data.DataView.IDataView> global variable and load the data with the `_trainDataPath` parameter.</span></span>

 <span data-ttu-id="2fa77-232">Точно так же как входные и выходные данные [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer), `DataView` является основным типом конвейера данных, сравнимым с `IEnumerable` для `LINQ`.</span><span class="sxs-lookup"><span data-stu-id="2fa77-232">As the input and output of [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer), a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="2fa77-233">В ML.NET данные аналогичны `SQL view`.</span><span class="sxs-lookup"><span data-stu-id="2fa77-233">In ML.NET, data is similar to a `SQL view`.</span></span> <span data-ttu-id="2fa77-234">Они схематизированы, неоднородны, и к ним применено отложенное вычисление.</span><span class="sxs-lookup"><span data-stu-id="2fa77-234">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="2fa77-235">Объект является первой частью конвейера. Он загружает данные.</span><span class="sxs-lookup"><span data-stu-id="2fa77-235">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="2fa77-236">В этом руководстве он загружает набор данных с названиями и описаниями задач, а также с соответствующей меткой области GitHub.</span><span class="sxs-lookup"><span data-stu-id="2fa77-236">For this tutorial, it loads a dataset with issue titles, descriptions, and corresponding area GitHub label.</span></span> <span data-ttu-id="2fa77-237">`DataView` используется для создания и обучения модели.</span><span class="sxs-lookup"><span data-stu-id="2fa77-237">The `DataView` is used to create and train the model.</span></span>

<span data-ttu-id="2fa77-238">Так как созданный ранее тип модели данных `GitHubIssue` соответствует схеме набора данных, вы можете объединить инициализацию, сопоставление и загрузку набора данных в одной строке кода.</span><span class="sxs-lookup"><span data-stu-id="2fa77-238">Since your previously created `GitHubIssue` data model type matches the dataset schema, you can combine the initialization, mapping, and dataset loading into one line of code.</span></span>

<span data-ttu-id="2fa77-239">Первая часть строки (`CreateTextLoader<GitHubIssue>(hasHeader: true)`) создает <xref:Microsoft.ML.Data.TextLoader>, выводя схему набора данных из типа модели данных `GitHubIssue` и используя заголовок набора данных.</span><span class="sxs-lookup"><span data-stu-id="2fa77-239">The first part of the line (`CreateTextLoader<GitHubIssue>(hasHeader: true)`) creates a <xref:Microsoft.ML.Data.TextLoader> by inferring the dataset schema from the `GitHubIssue` data model type and using the dataset header.</span></span>

<span data-ttu-id="2fa77-240">Вы определили схему данных ранее при создании класса `GitHubIssue`.</span><span class="sxs-lookup"><span data-stu-id="2fa77-240">You defined the data schema previously when you created the `GitHubIssue` class.</span></span> <span data-ttu-id="2fa77-241">Для схемы:</span><span class="sxs-lookup"><span data-stu-id="2fa77-241">For your schema:</span></span>

* <span data-ttu-id="2fa77-242">Первый столбец `ID` (идентификатор задачи GitHub).</span><span class="sxs-lookup"><span data-stu-id="2fa77-242">the first column `ID` (GitHub Issue ID)</span></span>
* <span data-ttu-id="2fa77-243">Второй столбец `Area` (прогноз для обучения).</span><span class="sxs-lookup"><span data-stu-id="2fa77-243">the second column `Area` (the prediction for training)</span></span>
* <span data-ttu-id="2fa77-244">Третий столбец `Title` (название задачи GitHub) является первым [признаком](../resources/glossary.md##feature), используемым для прогнозирования `Area`.</span><span class="sxs-lookup"><span data-stu-id="2fa77-244">the third column `Title` (GitHub issue title) is the first [feature](../resources/glossary.md##feature)  used for predicting the `Area`</span></span>
* <span data-ttu-id="2fa77-245">Четвертый столбец `Description` является вторым признаком, используемым для прогнозирования `Area`.</span><span class="sxs-lookup"><span data-stu-id="2fa77-245">the fourth column  `Description` is the second feature used for predicting the `Area`</span></span>

<span data-ttu-id="2fa77-246">Вторая часть строки (`.Read(_trainDataPath)`) использует метод <xref:Microsoft.ML.Data.TextLoader.Read%2A> для загрузки обучающего текстового файла с помощью `_trainDataPath` в глобальную переменную `IDataView` (`_trainingDataView`).</span><span class="sxs-lookup"><span data-stu-id="2fa77-246">The second part of the line  (`.Read(_trainDataPath)`) uses <xref:Microsoft.ML.Data.TextLoader.Read%2A> method to load the training text file using `_trainDataPath` into the `IDataView` (`_trainingDataView`) global variable.</span></span>  

<span data-ttu-id="2fa77-247">Чтобы инициализировать и загрузить глобальную переменную `_trainingDataView` для ее использования в конвейере, добавьте после инициализации `mlContext` следующий код:</span><span class="sxs-lookup"><span data-stu-id="2fa77-247">To initialize and load the `_trainingDataView` global variable in order to use it for the pipeline, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTrainData)]


<span data-ttu-id="2fa77-248">Добавьте в следующую строку метода `Main` приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="2fa77-248">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallProcessData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallProcessData)]

<span data-ttu-id="2fa77-249">Метод `ProcessData` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="2fa77-249">The `ProcessData` method executes the following tasks:</span></span>

* <span data-ttu-id="2fa77-250">извлечение и преобразование данных;</span><span class="sxs-lookup"><span data-stu-id="2fa77-250">Extracts and transforms the data.</span></span>
* <span data-ttu-id="2fa77-251">возвращение конвейера обработки.</span><span class="sxs-lookup"><span data-stu-id="2fa77-251">Returns the processing pipeline.</span></span>

<span data-ttu-id="2fa77-252">Создайте метод `ProcessData` сразу после метода `Main`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="2fa77-252">Create the `ProcessData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static EstimatorChain<ITransformer> ProcessData()
{

}
```

## <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="2fa77-253">Извлечение компонентов и преобразование данных</span><span class="sxs-lookup"><span data-stu-id="2fa77-253">Extract Features and transform the data</span></span>

<span data-ttu-id="2fa77-254">Предварительная обработка и очистка данных — это очень важные задачи, которые нужно выполнить перед использованием набора данных для машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="2fa77-254">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="2fa77-255">Необработанные данные часто содержат много шума, недостаточно надежны и в них могут быть пропуски.</span><span class="sxs-lookup"><span data-stu-id="2fa77-255">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="2fa77-256">Использование данных напрямую без этих задач моделирования может дать неправильные результаты.</span><span class="sxs-lookup"><span data-stu-id="2fa77-256">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="2fa77-257">Конвейеры преобразования ML.NET создают пользовательский набор `transforms`, который применяется к данным перед началом обучения или проверки.</span><span class="sxs-lookup"><span data-stu-id="2fa77-257">ML.NET's transform pipelines compose a custom `transforms`set that is applied to your data before training or testing.</span></span> <span data-ttu-id="2fa77-258">Основной целью преобразования является [присвоение признаков](../resources/glossary.md#feature-engineering).</span><span class="sxs-lookup"><span data-stu-id="2fa77-258">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="2fa77-259">Алгоритмы Машинного обучения определяют данные с [присвоенными признаками](../resources/glossary.md#feature), поэтому следующим шагом является преобразование текстовых данных в формат, который распознают наши алгоритмы Машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="2fa77-259">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="2fa77-260">Этот формат — [числовой вектор](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="2fa77-260">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="2fa77-261">При выполнении следующих шагов мы будем называть столбцы по именам, определенным в классе `GitHubIssue`.</span><span class="sxs-lookup"><span data-stu-id="2fa77-261">In the next steps, we refer to the columns by the names defined in the `GitHubIssue` class.</span></span>

<span data-ttu-id="2fa77-262">При обучении и оценке модели значения в столбце **Label** по умолчанию рассматриваются как правильные значения для прогноза.</span><span class="sxs-lookup"><span data-stu-id="2fa77-262">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="2fa77-263">Поскольку нам необходимо спрогнозировать метку области GitHub для `GitHubIssue`, скопируйте столбец `Area` в столбец **Label**.</span><span class="sxs-lookup"><span data-stu-id="2fa77-263">As we want to predict the Area GitHub label for a `GitHubIssue`, copy the `Area` column into the **Label** column.</span></span> <span data-ttu-id="2fa77-264">Для этого используйте `MLContext.Transforms.Conversion.MapValueToKey`, что является оболочкой для класса преобразования <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="2fa77-264">To do that, use the `MLContext.Transforms.Conversion.MapValueToKey`, which is a wrapper for the <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> transformation class.</span></span>  <span data-ttu-id="2fa77-265">`MapValueToKey` возвращает <xref:Microsoft.ML.Data.EstimatorChain%601>, что фактически станет конвейером.</span><span class="sxs-lookup"><span data-stu-id="2fa77-265">The `MapValueToKey` returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="2fa77-266">Присвойте ему имя `pipeline`, так как затем вы добавите обучающую систему в `EstimatorChain`.</span><span class="sxs-lookup"><span data-stu-id="2fa77-266">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="2fa77-267">Добавьте следующую строку кода:</span><span class="sxs-lookup"><span data-stu-id="2fa77-267">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#MapValueToKey)]

 <span data-ttu-id="2fa77-268">Такое присвоение задает значения ключа различным значениям в каждом из столбцов, и оно используется в алгоритме машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="2fa77-268">Featurizing assigns different numeric key values to the different values in each of the columns and is used by the machine learning algorithm.</span></span> <span data-ttu-id="2fa77-269">Затем вызовите `mlContext.Transforms.Text.FeaturizeText`, который присваивает столбцы текста (`Title` и `Description`) числовому вектору `TitleFeaturized` и `DescriptionFeaturized` соответственно.</span><span class="sxs-lookup"><span data-stu-id="2fa77-269">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text (`Title` and `Description`) columns into a numeric vector for each called `TitleFeaturized` and `DescriptionFeaturized`.</span></span> <span data-ttu-id="2fa77-270">Добавьте присвоение признаков для обоих столбцов в конвейере, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="2fa77-270">Append the featurization for both columns to the pipeline with the following code:</span></span>

[!code-csharp[FeaturizeText](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#FeaturizeText)]

>[!WARNING]
> <span data-ttu-id="2fa77-271">В ML.NET версии 0.10 изменился порядок параметров преобразования.</span><span class="sxs-lookup"><span data-stu-id="2fa77-271">ML.NET Version 0.10 has changed the order of the Transform parameters.</span></span> <span data-ttu-id="2fa77-272">Ошибка не возникнет до момента сборки.</span><span class="sxs-lookup"><span data-stu-id="2fa77-272">This will not error out until you build.</span></span> <span data-ttu-id="2fa77-273">Используйте имена параметров для преобразования, как показано в предыдущем фрагменте кода.</span><span class="sxs-lookup"><span data-stu-id="2fa77-273">Use the parameter names for Transforms as illustrated in the previous code snippet.</span></span>

<span data-ttu-id="2fa77-274">Последний шаг на этапе подготовки данных заключается в объединении всех столбцов признаков в столбце **Features** с помощью класса преобразования `Concatenate`.</span><span class="sxs-lookup"><span data-stu-id="2fa77-274">The last step in data preparation combines all of the feature columns into the **Features** column using the `Concatenate` transformation class.</span></span> <span data-ttu-id="2fa77-275">По умолчанию алгоритм обучения обрабатывает только признаки, представленные в столбце **Features**.</span><span class="sxs-lookup"><span data-stu-id="2fa77-275">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="2fa77-276">Добавьте это преобразование в конвейер, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="2fa77-276">Append this transformation to the pipeline with the following code:</span></span>

[!code-csharp[Concatenate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Concatenate)]

 <span data-ttu-id="2fa77-277">Затем добавьте <xref:Microsoft.ML.Data.EstimatorChain`1.AppendCacheCheckpoint%2A> для кэширования DataView, которое может ускорить обучение при многократных итерациях по данным, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="2fa77-277">Next, append a <xref:Microsoft.ML.Data.EstimatorChain`1.AppendCacheCheckpoint%2A> to cache the DataView so when you iterate over the data multiple times using the cache might get better performance, as with the following code:</span></span>

[!code-csharp[AppendCache](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AppendCache)]

> [!WARNING]
> <span data-ttu-id="2fa77-278">Используйте AppendCacheCheckpoint для небольших и средних наборов данных для ускорения обучения.</span><span class="sxs-lookup"><span data-stu-id="2fa77-278">Use AppendCacheCheckpoint for small/medium datasets to lower training time.</span></span> <span data-ttu-id="2fa77-279">НЕ используйте AppendCacheCheckpoint (удалите .AppendCacheCheckpoint()) при обработке очень больших наборов данных.</span><span class="sxs-lookup"><span data-stu-id="2fa77-279">Do NOT use it (remove .AppendCacheCheckpoint()) when handling very large datasets.</span></span>

<span data-ttu-id="2fa77-280">Выполните возврат конвейера в конце метода `ProcessData`.</span><span class="sxs-lookup"><span data-stu-id="2fa77-280">Return the pipeline at the end of the `ProcessData` method.</span></span>

[!code-csharp[ReturnPipeline](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnPipeline)]

<span data-ttu-id="2fa77-281">На этом этапе выполняется предварительная обработка и присвоение признаков.</span><span class="sxs-lookup"><span data-stu-id="2fa77-281">This step handles preprocessing/featurization.</span></span> <span data-ttu-id="2fa77-282">Дополнительные компоненты из ML.NET могут дать более точные результаты для вашей модели.</span><span class="sxs-lookup"><span data-stu-id="2fa77-282">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="build-and-train-the-model"></a><span data-ttu-id="2fa77-283">Сборка и обучение модели</span><span class="sxs-lookup"><span data-stu-id="2fa77-283">Build and train the model</span></span>

<span data-ttu-id="2fa77-284">В следующей строке кода в методе `Main` добавьте приведенный ниже вызов метода `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="2fa77-284">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="2fa77-285">Метод `BuildAndTrainModel` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="2fa77-285">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="2fa77-286">создание класса алгоритма обучения;</span><span class="sxs-lookup"><span data-stu-id="2fa77-286">Creates the training algorithm class.</span></span>
* <span data-ttu-id="2fa77-287">обучение модели;</span><span class="sxs-lookup"><span data-stu-id="2fa77-287">Trains the model.</span></span>
* <span data-ttu-id="2fa77-288">прогнозирование области на основе обучающих данных;</span><span class="sxs-lookup"><span data-stu-id="2fa77-288">Predicts area based on training data.</span></span>
* <span data-ttu-id="2fa77-289">сохранение модели в файл `.zip`;</span><span class="sxs-lookup"><span data-stu-id="2fa77-289">Saves the model to a `.zip` file.</span></span>
* <span data-ttu-id="2fa77-290">возвращение модели.</span><span class="sxs-lookup"><span data-stu-id="2fa77-290">Returns the model.</span></span>

<span data-ttu-id="2fa77-291">Создайте метод `BuildAndTrainModel` сразу после метода `Main`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="2fa77-291">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static EstimatorChain<KeyToValueMappingTransformer> BuildAndTrainModel(IDataView trainingDataView, EstimatorChain<ITransformer> pipeline)
{

}
```

<span data-ttu-id="2fa77-292">Обратите внимание, что в метод BuildAndTrainModel передаются два параметра — `IDataView` для обучающего набора данных (`trainingDataView`) и <xref:Microsoft.ML.Data.EstimatorChain%601> для конвейера обработки, созданного в ProcessData (`pipeline`).</span><span class="sxs-lookup"><span data-stu-id="2fa77-292">Notice that two parameters are passed into the BuildAndTrainModel method; an `IDataView` for the training dataset (`trainingDataView`), and a <xref:Microsoft.ML.Data.EstimatorChain%601> for the processing pipeline created in ProcessData (`pipeline`).</span></span>

 <span data-ttu-id="2fa77-293">Добавьте следующий код в первую строку метода `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="2fa77-293">Add the following code as the first line of the `BuildAndTrainModel` method:</span></span>

### <a name="choose-a-learning-algorithm"></a><span data-ttu-id="2fa77-294">Выбор алгоритма обучения</span><span class="sxs-lookup"><span data-stu-id="2fa77-294">Choose a learning algorithm</span></span>

<span data-ttu-id="2fa77-295">Чтобы добавить алгоритм обучения, вызовите метод оболочки `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent`, возвращающий объект <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer>.</span><span class="sxs-lookup"><span data-stu-id="2fa77-295">To add the learning algorithm, call the `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent` wrapper method which returns a <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer> object.</span></span>  <span data-ttu-id="2fa77-296">`SdcaMultiClassTrainer` добавляется в `pipeline` и принимает в качестве входных параметров `Title` и `Description` (`Features`) с присвоенными признаками, а также `Label` для обучения по историческим данным.</span><span class="sxs-lookup"><span data-stu-id="2fa77-296">The `SdcaMultiClassTrainer` is appended to the `pipeline` and accepts the featurized `Title` and `Description` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span> <span data-ttu-id="2fa77-297">Для возврата в исходное доступное для чтения состояние необходимо также сопоставить метку со значением.</span><span class="sxs-lookup"><span data-stu-id="2fa77-297">You also need to map the label to the value to return to its original readable state.</span></span> <span data-ttu-id="2fa77-298">Выполните оба эти действия, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="2fa77-298">Do both of those actions with the following code:</span></span>

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTrainer)]

### <a name="train-the-model"></a><span data-ttu-id="2fa77-299">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="2fa77-299">Train the model</span></span>

<span data-ttu-id="2fa77-300">Обучения модели <xref:Microsoft.ML.Data.TransformerChain%601> выполняется по набору данных, который вы ранее скачали и преобразовали.</span><span class="sxs-lookup"><span data-stu-id="2fa77-300">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="2fa77-301">После определения средства оценки вы обучите модель с помощью <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A>, предоставляя уже загруженные данные для обучения.</span><span class="sxs-lookup"><span data-stu-id="2fa77-301">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="2fa77-302">Этот метод возвращает модель, необходимую для прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="2fa77-302">This  method returns a model to use for predictions.</span></span> <span data-ttu-id="2fa77-303">`trainingPipeline.Fit()` обучает конвейер и возвращает `Transformer` на основе переданного типа `DataView`.</span><span class="sxs-lookup"><span data-stu-id="2fa77-303">`trainingPipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="2fa77-304">Эксперимент не выполняется, пока метод `.Fit()` не запустится.</span><span class="sxs-lookup"><span data-stu-id="2fa77-304">The experiment is not executed until the `.Fit()` method runs.</span></span>

<span data-ttu-id="2fa77-305">Добавьте следующий код в метод `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="2fa77-305">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#TrainModel)]

<span data-ttu-id="2fa77-306">Несмотря на то, что `model` представляет собой `transformer`, который обрабатывает многочисленные строки данных, достаточно распространенным сценарием рабочей среды является прогнозирование на основе отдельных примеров.</span><span class="sxs-lookup"><span data-stu-id="2fa77-306">While the `model` is a `transformer` that operates on many rows of data, a need for predictions on individual examples is a common production scenario.</span></span> <span data-ttu-id="2fa77-307"><xref:Microsoft.ML.PredictionEngine%602> — это программа-оболочка, возвращаемая из метода `CreatePredictionEngine`.</span><span class="sxs-lookup"><span data-stu-id="2fa77-307">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="2fa77-308">Давайте добавим в следующей строке метода `BuildAndTrainModel` указанный ниже код для создания `PredictionEngine`:</span><span class="sxs-lookup"><span data-stu-id="2fa77-308">Let's add the following code to create the `PredictionEngine` as the next line in the `BuildAndTrainModel` Method:</span></span>

[!code-csharp[CreatePredictionEngine1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine1)]

### <a name="predict-with-the-trained-model"></a><span data-ttu-id="2fa77-309">Прогнозирование с помощью обученной модели</span><span class="sxs-lookup"><span data-stu-id="2fa77-309">Predict with the trained model</span></span>

<span data-ttu-id="2fa77-310">Добавьте задачу GitHub для тестирования прогноза обученной модели в методе `Predict`, создав экземпляр `GitHubIssue`:</span><span class="sxs-lookup"><span data-stu-id="2fa77-310">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[CreateTestIssue1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateTestIssue1)]

<span data-ttu-id="2fa77-311">Его можно использовать для прогнозирования метки `Area` в одном экземпляре данных задачи.</span><span class="sxs-lookup"><span data-stu-id="2fa77-311">You can use that to predict the `Area` label of a single instance of the issue data.</span></span> <span data-ttu-id="2fa77-312">Чтобы получить прогноз, примените <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> для данных.</span><span class="sxs-lookup"><span data-stu-id="2fa77-312">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="2fa77-313">Входные данные имеют строковый формат, а модель выполняет присвоение признаков.</span><span class="sxs-lookup"><span data-stu-id="2fa77-313">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="2fa77-314">Конвейер синхронизируется во время обучения и прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="2fa77-314">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="2fa77-315">Вам не нужно писать для прогнозирования отдельный код предварительной обработки и присвоения признаков. Кроме того, этот API выполняет как пакетное, так и разовое прогнозирование.</span><span class="sxs-lookup"><span data-stu-id="2fa77-315">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Predict)]

### <a name="using-the-model-prediction-results"></a><span data-ttu-id="2fa77-316">Использование модели: результаты прогнозирования</span><span class="sxs-lookup"><span data-stu-id="2fa77-316">Using the model: prediction results</span></span>

<span data-ttu-id="2fa77-317">Отобразите `GitHubIssue` и соответствующий прогноз метки `Area`, чтобы поделиться результатами и обработать их должным образом.</span><span class="sxs-lookup"><span data-stu-id="2fa77-317">Display `GitHubIssue` and corresponding `Area` label prediction in order to share the results and act on them accordingly.</span></span>  <span data-ttu-id="2fa77-318">Создайте отображение для результатов с помощью следующего кода <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="2fa77-318">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="2fa77-319">Возврат обученной модели для оценки</span><span class="sxs-lookup"><span data-stu-id="2fa77-319">Return the model trained to use for evaluation</span></span>

<span data-ttu-id="2fa77-320">Выполните возврат модели в конце метода `BuildAndTrainModel`.</span><span class="sxs-lookup"><span data-stu-id="2fa77-320">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a><span data-ttu-id="2fa77-321">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="2fa77-321">Evaluate the model</span></span>

<span data-ttu-id="2fa77-322">Итак, вы завершили создание и обучение модели, и теперь ее можно оценить по другому набору данных, чтобы проверить ее точность и качество прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="2fa77-322">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="2fa77-323">В методе `Evaluate` передается для оценки модель, созданная в `BuildAndTrainModel`.</span><span class="sxs-lookup"><span data-stu-id="2fa77-323">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="2fa77-324">Создайте метод `Evaluate` сразу после метода `BuildAndTrainModel` как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="2fa77-324">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate()
{

}
```

<span data-ttu-id="2fa77-325">Метод `Evaluate` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="2fa77-325">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="2fa77-326">загрузка тестового набора данных;</span><span class="sxs-lookup"><span data-stu-id="2fa77-326">Loads the test dataset.</span></span>
* <span data-ttu-id="2fa77-327">создание средства оценки многоклассовой классификации;</span><span class="sxs-lookup"><span data-stu-id="2fa77-327">Creates the multiclass evaluator.</span></span>
* <span data-ttu-id="2fa77-328">оценка модели и создание метрик;</span><span class="sxs-lookup"><span data-stu-id="2fa77-328">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="2fa77-329">отображение метрик.</span><span class="sxs-lookup"><span data-stu-id="2fa77-329">Displays the metrics.</span></span>

<span data-ttu-id="2fa77-330">Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `BuildAndTrainModel`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="2fa77-330">Add a call to the new method from the `Main` method, right under the `BuildAndTrainModel` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallEvaluate)]

<span data-ttu-id="2fa77-331">Как и для обучающего набора данных ранее, вы можете объединить инициализацию, сопоставление и загрузку тестового набора данных в одной строке кода.</span><span class="sxs-lookup"><span data-stu-id="2fa77-331">As you did previously with the training dataset, you can combine the initialization, mapping, and test dataset loading into one line of code.</span></span> <span data-ttu-id="2fa77-332">С помощью этого набора данных вы можете оценить модели для проверки ее качества.</span><span class="sxs-lookup"><span data-stu-id="2fa77-332">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="2fa77-333">Добавьте следующий код в метод `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="2fa77-333">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTestDataset)]

<span data-ttu-id="2fa77-334">`MulticlassClassificationContext.Evaluate` является оболочкой для метода <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A>, который вычисляет метрики качества для модели по указанному набору данных.</span><span class="sxs-lookup"><span data-stu-id="2fa77-334">The `MulticlassClassificationContext.Evaluate` is a wrapper for the <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A> method that computes the quality metrics for the model using the specified dataset.</span></span> <span data-ttu-id="2fa77-335">Он возвращает объект <xref:Microsoft.ML.Data.MultiClassClassifierMetrics>, содержащий общие метрики, вычисляемые средствами оценки многоклассовой классификации.</span><span class="sxs-lookup"><span data-stu-id="2fa77-335">It returns a <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> object that contains the overall metrics computed by multiclass classification evaluators.</span></span>
<span data-ttu-id="2fa77-336">Чтобы отобразить метрики для оценки качества модели, сначала их необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="2fa77-336">To display the metrics to determine the quality of the model, you need to get them first.</span></span>
<span data-ttu-id="2fa77-337">Используйте метод `Transform` (преобразователь) для глобальной переменной `_trainedModel` машинного обучения для ввода признаков и возврата прогнозов.</span><span class="sxs-lookup"><span data-stu-id="2fa77-337">Notice the use of the `Transform` method of the machine learning `_trainedModel` global variable (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="2fa77-338">В качестве следующей строки в методе `Evaluate` добавьте приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="2fa77-338">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Evaluate)]

<span data-ttu-id="2fa77-339">Для многоклассовой классификации выполняется оценка следующих метрик:</span><span class="sxs-lookup"><span data-stu-id="2fa77-339">The following metrics are evaluated for multiclass classification:</span></span>

* <span data-ttu-id="2fa77-340">Микроточность — на метрику точности в равной степени влияет каждая пара "пример-класс".</span><span class="sxs-lookup"><span data-stu-id="2fa77-340">Micro Accuracy - Every sample-class pair contributes equally to the accuracy metric.</span></span>  <span data-ttu-id="2fa77-341">Значение микроточности должно быть максимально близко к 1.</span><span class="sxs-lookup"><span data-stu-id="2fa77-341">You want Micro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="2fa77-342">Макроточность — на метрику точности в равной степени влияет каждый класс.</span><span class="sxs-lookup"><span data-stu-id="2fa77-342">Macro Accuracy - Every class contributes equally to the accuracy metric.</span></span> <span data-ttu-id="2fa77-343">Миноритарным классам назначается тот же вес, что и более крупным.</span><span class="sxs-lookup"><span data-stu-id="2fa77-343">Minority classes are given equal weight as the larger classes.</span></span> <span data-ttu-id="2fa77-344">Значение макроточности должно быть максимально близко к 1.</span><span class="sxs-lookup"><span data-stu-id="2fa77-344">You want Macro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="2fa77-345">Логарифмические потери — см. термин [логарифмические потери](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="2fa77-345">Log-loss - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="2fa77-346">Значение логарифмических потерь должно быть максимально близко к нулю.</span><span class="sxs-lookup"><span data-stu-id="2fa77-346">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="2fa77-347">Минимизация логарифмических потерь — находится в диапазоне [-inf, 100], где 100 — идеальный прогноз, а 0 — среднее прогнозное значение.</span><span class="sxs-lookup"><span data-stu-id="2fa77-347">Log-loss reduction - Ranges from [-inf, 100], where 100 is perfect predictions and 0 indicates mean predictions.</span></span> <span data-ttu-id="2fa77-348">Значение минимизации логарифмических потерь должно быть максимально близко к нулю.</span><span class="sxs-lookup"><span data-stu-id="2fa77-348">You want Log-loss reduction to be as close to zero as possible.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="2fa77-349">Отображение метрик для проверки модели</span><span class="sxs-lookup"><span data-stu-id="2fa77-349">Displaying the metrics for model validation</span></span>

<span data-ttu-id="2fa77-350">Используйте следующий код для отображения метрик, передачи результатов и выполнения действий по ним:</span><span class="sxs-lookup"><span data-stu-id="2fa77-350">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayMetrics)]

### <a name="save-the-trained-and-evaluated-model"></a><span data-ttu-id="2fa77-351">Сохранение обученной и вычисленной модели</span><span class="sxs-lookup"><span data-stu-id="2fa77-351">Save the trained and evaluated model</span></span>

<span data-ttu-id="2fa77-352">На этом этапе у вас есть модель типа <xref:Microsoft.ML.Data.TransformerChain%601>, которую можно интегрировать с любыми имеющимися или новыми приложениями .NET.</span><span class="sxs-lookup"><span data-stu-id="2fa77-352">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="2fa77-353">Чтобы сохранить обученную модель в ZIP-файл, добавьте приведенный ниже код вызова метода `SaveModelAsFile` в качестве следующей строки в `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="2fa77-353">To save your trained model to a .zip file, add the following code to call the `SaveModelAsFile` method as the next line in `BuildAndTrainModel`:</span></span>

[!code-csharp[CallSaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallSaveModel)]

## <a name="save-the-model-as-a-zip-file"></a><span data-ttu-id="2fa77-354">Сохранение модели в качестве ZIP-файла</span><span class="sxs-lookup"><span data-stu-id="2fa77-354">Save the model as a .zip file</span></span>

<span data-ttu-id="2fa77-355">Создайте метод `SaveModelAsFile` сразу после метода `Evaluate`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="2fa77-355">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="2fa77-356">Метод `SaveModelAsFile` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="2fa77-356">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="2fa77-357">сохранение модели в качестве ZIP-файла.</span><span class="sxs-lookup"><span data-stu-id="2fa77-357">Saves the model as a .zip file.</span></span>

<span data-ttu-id="2fa77-358">Далее создайте метод для сохранения модели, чтобы ее можно было использовать повторно, а также применять в других приложениях.</span><span class="sxs-lookup"><span data-stu-id="2fa77-358">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="2fa77-359">`ITransformer` содержит метод <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)>, который принимает глобальное поле `_modelPath`, и <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="2fa77-359">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="2fa77-360">Чтобы сохранить модель в качестве ZIP-файла, мы создадим `FileStream` непосредственно перед вызовом метода `SaveTo`.</span><span class="sxs-lookup"><span data-stu-id="2fa77-360">To save the model as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="2fa77-361">В качестве следующей строки в методе `SaveModelAsFile` добавьте приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="2fa77-361">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SaveModel)]

<span data-ttu-id="2fa77-362">Вы также можете просмотреть, куда был записан файл, написав консольное сообщение с `_modelPath`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="2fa77-362">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="2fa77-363">Развертывание и прогнозирование с помощью загруженной модели</span><span class="sxs-lookup"><span data-stu-id="2fa77-363">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="2fa77-364">Добавьте вызов нового метода из метода `Main`, сразу после вызова метода `Evaluate`, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="2fa77-364">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallPredictIssue)]

<span data-ttu-id="2fa77-365">Создайте метод `PredictIssue` сразу после метода `Evaluate` (и непосредственно перед методом `SaveModelAsFile`), вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="2fa77-365">Create the `PredictIssue` method, just after the `Evaluate` method (and just before the `SaveModelAsFile` method), using the following code:</span></span>

```csharp
private static void PredictIssue()
{

}
```

<span data-ttu-id="2fa77-366">Метод `PredictIssue` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="2fa77-366">The `PredictIssue` method executes the following tasks:</span></span>

* <span data-ttu-id="2fa77-367">создание одной задачи с тестовыми данными;</span><span class="sxs-lookup"><span data-stu-id="2fa77-367">Creates a single issue of test data.</span></span>
* <span data-ttu-id="2fa77-368">прогнозирование области на основе тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="2fa77-368">Predicts Area based on test data.</span></span>
* <span data-ttu-id="2fa77-369">объединение тестовых данных и прогнозов для создания отчетов;</span><span class="sxs-lookup"><span data-stu-id="2fa77-369">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="2fa77-370">отображение результатов прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="2fa77-370">Displays the predicted results.</span></span>

<span data-ttu-id="2fa77-371">Сначала загрузите сохраненную ранее модель, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="2fa77-371">First, load the model that you saved previously with the following code:</span></span>

[!code-csharp[LoadModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadModel)]

<span data-ttu-id="2fa77-372">Добавьте задачу GitHub для тестирования прогноза обученной модели в методе `Predict`, создав экземпляр `GitHubIssue`:</span><span class="sxs-lookup"><span data-stu-id="2fa77-372">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[AddTestIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTestIssue)]

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]
  
<span data-ttu-id="2fa77-373">Теперь, когда у вас есть модель, ее можно использовать для прогнозирования метки области GitHub у одного экземпляра данных задачи GitHub.</span><span class="sxs-lookup"><span data-stu-id="2fa77-373">Now that you have a model, you can use that to predict the Area GitHub label of a single instance of the GitHub issue data.</span></span> <span data-ttu-id="2fa77-374">Чтобы получить прогноз, примените <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> для данных.</span><span class="sxs-lookup"><span data-stu-id="2fa77-374">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="2fa77-375">Входные данные имеют строковый формат, а модель выполняет присвоение признаков.</span><span class="sxs-lookup"><span data-stu-id="2fa77-375">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="2fa77-376">Конвейер синхронизируется во время обучения и прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="2fa77-376">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="2fa77-377">Вам не нужно писать для прогнозирования отдельный код предварительной обработки и присвоения признаков. Кроме того, этот API выполняет как пакетное, так и разовое прогнозирование.</span><span class="sxs-lookup"><span data-stu-id="2fa77-377">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="2fa77-378">Добавьте в метод `PredictIssue` приведенный ниже код для прогнозирования:</span><span class="sxs-lookup"><span data-stu-id="2fa77-378">Add the following code to the `PredictIssue` method for the predictions:</span></span>

[!code-csharp[PredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a><span data-ttu-id="2fa77-379">Использование загружаемой модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="2fa77-379">Using the loaded model for prediction</span></span>

<span data-ttu-id="2fa77-380">Отобразите `Area`, чтобы категоризировать задачу и обработать ее должным образом.</span><span class="sxs-lookup"><span data-stu-id="2fa77-380">Display `Area` in order to categorize the issue and act on it accordingly.</span></span> <span data-ttu-id="2fa77-381">Создайте отображение для результатов с помощью следующего кода <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="2fa77-381">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayResults](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayResults)]

## <a name="results"></a><span data-ttu-id="2fa77-382">Результаты</span><span class="sxs-lookup"><span data-stu-id="2fa77-382">Results</span></span>

<span data-ttu-id="2fa77-383">Результаты выполнения должны выглядеть примерно так, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="2fa77-383">Your results should be similar to the following.</span></span> <span data-ttu-id="2fa77-384">В процессе работы конвейер выводит сообщения.</span><span class="sxs-lookup"><span data-stu-id="2fa77-384">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="2fa77-385">Вы можете видеть предупреждения или обработанные сообщения.</span><span class="sxs-lookup"><span data-stu-id="2fa77-385">You may see warnings, or processing messages.</span></span> <span data-ttu-id="2fa77-386">Для удобства эти сообщения удалены из следующих результатов.</span><span class="sxs-lookup"><span data-stu-id="2fa77-386">These messages have been removed from the following results for clarity.</span></span>

```console
=============== Single Prediction just-trained-model - Result: area-System.Net ===============
The model is saved to C:\Users\johalex\dotnet-samples\samples\machine-learning\tutorials\GitHubIssueClassification\bin\Debug\netcoreapp2.0\..\..\..\Models\model.zip
*************************************************************************************************************
*       Metrics for Multi-class Classification model - Test Data
*------------------------------------------------------------------------------------------------------------
*       MicroAccuracy:    0.74
*       MacroAccuracy:    0.687
*       LogLoss:          .932
*       LogLossReduction: 63.852
*************************************************************************************************************
=============== Single Prediction - Result: area-System.Data ===============
```

<span data-ttu-id="2fa77-387">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="2fa77-387">Congratulations!</span></span> <span data-ttu-id="2fa77-388">Вы успешно создали модель машинного обучения для классификации и прогнозирования метки области у задачи GitHub.</span><span class="sxs-lookup"><span data-stu-id="2fa77-388">You've now successfully built a machine learning model for classifying and predicting an Area label for a GitHub issue.</span></span> <span data-ttu-id="2fa77-389">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="2fa77-389">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2fa77-390">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="2fa77-390">Next steps</span></span>

<span data-ttu-id="2fa77-391">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="2fa77-391">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="2fa77-392">Определение проблемы</span><span class="sxs-lookup"><span data-stu-id="2fa77-392">Understand the problem</span></span>
> * <span data-ttu-id="2fa77-393">Выбор подходящего алгоритма машинного обучения</span><span class="sxs-lookup"><span data-stu-id="2fa77-393">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="2fa77-394">подготавливать данные;</span><span class="sxs-lookup"><span data-stu-id="2fa77-394">Prepare your data</span></span>
> * <span data-ttu-id="2fa77-395">Преобразование данных</span><span class="sxs-lookup"><span data-stu-id="2fa77-395">Transform the data</span></span>
> * <span data-ttu-id="2fa77-396">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="2fa77-396">Train the model</span></span>
> * <span data-ttu-id="2fa77-397">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="2fa77-397">Evaluate the model</span></span>
> * <span data-ttu-id="2fa77-398">Прогнозирование с помощью обученной модели</span><span class="sxs-lookup"><span data-stu-id="2fa77-398">Predict with the trained model</span></span>
> * <span data-ttu-id="2fa77-399">Развертывание и прогнозирование с помощью загруженной модели</span><span class="sxs-lookup"><span data-stu-id="2fa77-399">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="2fa77-400">Переходите к следующему руководству:</span><span class="sxs-lookup"><span data-stu-id="2fa77-400">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="2fa77-401">Прогнозирование платы за такси</span><span class="sxs-lookup"><span data-stu-id="2fa77-401">Taxi Fare Predictor</span></span>](taxi-fare.md)
