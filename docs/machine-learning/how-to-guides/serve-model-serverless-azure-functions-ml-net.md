---
title: Развертывание модели в Функциях Azure
description: Использование модели машинного обучения ML.NET для анализа тональности и прогнозирования через Интернет с помощью Функций Azure
ms.date: 09/12/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 31169116abdda7308ed216902b335a6b77fbcfc4
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321281"
---
# <a name="deploy-a-model-to-azure-functions"></a><span data-ttu-id="c3a3b-103">Развертывание модели в Функциях Azure</span><span class="sxs-lookup"><span data-stu-id="c3a3b-103">Deploy a model to Azure Functions</span></span>

<span data-ttu-id="c3a3b-104">Сведения о развертывании предварительно обученной модели машинного обучения ML.NET для создания прогнозов по протоколу HTTP через бессерверную среду Функций Azure.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-104">Learn how to deploy a pre-trained ML.NET machine learning model for predictions over HTTP through an Azure Functions serverless environment.</span></span>

> [!NOTE]
> <span data-ttu-id="c3a3b-105">Расширение службы `PredictionEnginePool` сейчас доступно в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-105">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c3a3b-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c3a3b-106">Prerequisites</span></span>

- <span data-ttu-id="c3a3b-107">[Visual Studio 2017 версии 15.6 и выше](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core" и "Разработка в Azure".</span><span class="sxs-lookup"><span data-stu-id="c3a3b-107">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span>
- <span data-ttu-id="c3a3b-108">Пакет NuGet Microsoft.NET.Sdk.Functions версии 1.0.28 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-108">Microsoft.NET.Sdk.Functions NuGet Package version 1.0.28+.</span></span>
- <span data-ttu-id="c3a3b-109">[Средства Функций Azure](/azure/azure-functions/functions-develop-vs#check-your-tools-version).</span><span class="sxs-lookup"><span data-stu-id="c3a3b-109">[Azure Functions Tools](/azure/azure-functions/functions-develop-vs#check-your-tools-version)</span></span>
- <span data-ttu-id="c3a3b-110">PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-110">Powershell</span></span>
- <span data-ttu-id="c3a3b-111">Предварительно обученная модель.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-111">Pre-trained model.</span></span> <span data-ttu-id="c3a3b-112">Используйте [учебник по анализу тональности ML.NET](../tutorials/sentiment-analysis.md), чтобы создать собственную модель, или скачайте эту [предварительно обученную модель машинного обучения для анализа тональности](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span><span class="sxs-lookup"><span data-stu-id="c3a3b-112">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="c3a3b-113">Создание проекта в Функциях Azure</span><span class="sxs-lookup"><span data-stu-id="c3a3b-113">Create Azure Functions project</span></span>

1. <span data-ttu-id="c3a3b-114">Откройте Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-114">Open Visual Studio 2017.</span></span> <span data-ttu-id="c3a3b-115">Выберите **Файл** > **Создать** > **Проект** в меню.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-115">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="c3a3b-116">В диалоговом окне **Новый проект** щелкните узел **Visual C#** , а затем — **Облако**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-116">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="c3a3b-117">Выберите шаблон проекта **Функции Azure**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-117">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="c3a3b-118">В текстовое поле **Имя** введите SentimentAnalysisFunctionsApp и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-118">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="c3a3b-119">В диалоговом окне **Новый проект** откройте раскрывающийся список над разделом с параметрами проекта и выберите **Функции Azure v2 (.NET Core)** .</span><span class="sxs-lookup"><span data-stu-id="c3a3b-119">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="c3a3b-120">Затем щелкните проект **Триггер HTTP** и нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-120">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="c3a3b-121">Создайте каталог с именем *MLModels* в папке проекта, чтобы сохранить модель:</span><span class="sxs-lookup"><span data-stu-id="c3a3b-121">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="c3a3b-122">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-122">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="c3a3b-123">Введите MLModels и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-123">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="c3a3b-124">Установите **пакет NuGet для Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="c3a3b-124">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="c3a3b-125">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-125">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="c3a3b-126">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-126">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="c3a3b-127">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-127">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="c3a3b-128">Установите **пакет NuGet Microsoft.Azure.Functions.Extensions**:</span><span class="sxs-lookup"><span data-stu-id="c3a3b-128">Install the **Microsoft.Azure.Functions.Extensions NuGet Package**:</span></span>

    <span data-ttu-id="c3a3b-129">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-129">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="c3a3b-130">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.Azure.Functions.Extensions**, выберите из списка этот пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-130">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Azure.Functions.Extensions**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="c3a3b-131">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-131">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="c3a3b-132">Установите **пакет NuGet для Microsoft.Extensions.ML**:</span><span class="sxs-lookup"><span data-stu-id="c3a3b-132">Install the **Microsoft.Extensions.ML NuGet Package**:</span></span>

    <span data-ttu-id="c3a3b-133">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-133">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="c3a3b-134">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.Extensions.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-134">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="c3a3b-135">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-135">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="c3a3b-136">Обновите **пакет NuGet Microsoft.NET.Sdk.Functions** до версии 1.0.28 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-136">Update the **Microsoft.NET.Sdk.Functions NuGet Package** to version 1.0.28+:</span></span>

    <span data-ttu-id="c3a3b-137">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-137">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="c3a3b-138">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Установленные", выполните поиск по фразе **Microsoft.NET.Sdk.Functions**, выберите из списка этот пакет, выберите версию 1.0.28 или более позднюю в раскрывающемся списке "Версия" и нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-138">Choose "nuget.org" as the Package source, select the Installed tab, search for **Microsoft.NET.Sdk.Functions**, select that package in the list, select 1.0.28 or later from the Version dropdown, and select the **Update** button.</span></span> <span data-ttu-id="c3a3b-139">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-trained-model-to-project"></a><span data-ttu-id="c3a3b-140">Добавление предварительно обученной модели в проект</span><span class="sxs-lookup"><span data-stu-id="c3a3b-140">Add pre-trained model to project</span></span>

1. <span data-ttu-id="c3a3b-141">Скопируйте предварительно созданную модель в папку *MLModels*.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-141">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="c3a3b-142">В обозревателе решений щелкните правой кнопкой мыши файл предварительно созданной модели и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-142">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="c3a3b-143">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-143">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-azure-function-to-analyze-sentiment"></a><span data-ttu-id="c3a3b-144">Создание функции Azure для анализа тональности</span><span class="sxs-lookup"><span data-stu-id="c3a3b-144">Create Azure Function to analyze sentiment</span></span>

<span data-ttu-id="c3a3b-145">Создайте класс для прогнозирования тональности.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-145">Create a class to predict sentiment.</span></span> <span data-ttu-id="c3a3b-146">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="c3a3b-146">Add a new class to your project:</span></span>

1. <span data-ttu-id="c3a3b-147">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-147">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="c3a3b-148">В диалоговом окне **Добавление нового элемента** выберите **Функция Azure** и измените значение поля **Имя** на *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-148">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="c3a3b-149">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-149">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="c3a3b-150">В диалоговом окне **Новая функция Azure** щелкните **Триггер HTTP**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-150">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="c3a3b-151">Затем нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-151">Then, select the **OK** button.</span></span>

    <span data-ttu-id="c3a3b-152">В редакторе кода откроется файл *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-152">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="c3a3b-153">Добавьте следующий оператор `using` в начало файла *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-153">Add the following `using` statement to the top of *AnalyzeSentiment.cs*:</span></span>

    [!code-csharp [AnalyzeUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/AnalyzeSentiment.cs#L1-L11)]

    <span data-ttu-id="c3a3b-154">По умолчанию класс `AnalyzeSentiment` — `static`.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-154">By default, the `AnalyzeSentiment` class is `static`.</span></span> <span data-ttu-id="c3a3b-155">Удалите ключевое слово `static` из объявления класса.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-155">Make sure to remove the `static` keyword from the class definition.</span></span>

    ```csharp
    public class AnalyzeSentiment
    {

    }
    ```

## <a name="create-data-models"></a><span data-ttu-id="c3a3b-156">Создание моделей данных</span><span class="sxs-lookup"><span data-stu-id="c3a3b-156">Create data models</span></span>

<span data-ttu-id="c3a3b-157">Вам потребуется создать несколько классов для входных данных и прогнозов.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-157">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="c3a3b-158">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="c3a3b-158">Add a new class to your project:</span></span>

1. <span data-ttu-id="c3a3b-159">Создайте каталог с именем *DataModels* в папке проекта, чтобы сохранить в нем модели данных: В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Добавить > Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-159">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="c3a3b-160">Введите DataModels и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-160">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="c3a3b-161">В обозревателе решений щелкните правой кнопкой мыши папку *DataModels* и выберите **Добавить > Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-161">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="c3a3b-162">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-162">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="c3a3b-163">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-163">Then, select the **Add** button.</span></span>

    <span data-ttu-id="c3a3b-164">Файл *SentimentData.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-164">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="c3a3b-165">Добавьте в начало файла *SentimentData.cs* следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="c3a3b-165">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    [!code-csharp [SentimentDataUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentData.cs#L1)]

    <span data-ttu-id="c3a3b-166">Удалите из файла *SentimentData.cs* существующее определение класса и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="c3a3b-166">Remove the existing class definition and add the following code to the *SentimentData.cs* file:</span></span>

    [!code-csharp [SentimentData](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentData.cs#L5-L13)]

4. <span data-ttu-id="c3a3b-167">В обозревателе решений щелкните правой кнопкой мыши папку *DataModels* и выберите **Добавить > Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-167">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="c3a3b-168">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-168">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="c3a3b-169">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-169">Then, select the **Add** button.</span></span> <span data-ttu-id="c3a3b-170">В редакторе кода откроется файл *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-170">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="c3a3b-171">Добавьте в начало файла *SentimentPrediction.cs* следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="c3a3b-171">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    [!code-csharp [SentimentPredictionUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentPrediction.cs#L1)]

    <span data-ttu-id="c3a3b-172">Удалите из файла *SentimentPrediction.cs* существующее определение класса и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="c3a3b-172">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    [!code-csharp [SentimentPrediction](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentPrediction.cs#L5-L14)]

    <span data-ttu-id="c3a3b-173">`SentimentPrediction` наследует от `SentimentData`, который обеспечивает доступ к исходным данным в свойстве `SentimentText`, а также выходным данным модели.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-173">`SentimentPrediction` inherits from `SentimentData` which provides access to the original data in the `SentimentText` property as well as the output generated by the model.</span></span>

## <a name="register-predictionenginepool-service"></a><span data-ttu-id="c3a3b-174">Регистрация службы PredictionEnginePool</span><span class="sxs-lookup"><span data-stu-id="c3a3b-174">Register PredictionEnginePool service</span></span>

<span data-ttu-id="c3a3b-175">Для формирования одного прогноза необходимо создать [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="c3a3b-175">To make a single prediction, you have to create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="c3a3b-176">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) не является потокобезопасным.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-176">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="c3a3b-177">Кроме того, необходимо создать его экземпляр везде, где он понадобится в вашем приложении.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-177">Additionally, you have to create an instance of it everywhere it is needed within your application.</span></span> <span data-ttu-id="c3a3b-178">По мере увеличения размера приложения этот процесс может стать неуправляемым.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-178">As your application grows, this process can become unmanageable.</span></span> <span data-ttu-id="c3a3b-179">Для улучшенной производительности и потокобезопасности используйте сочетание внедрения зависимостей и службы `PredictionEnginePool`, которое создает [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) объектов [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) для использования во всем приложении.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-179">For improved performance and thread safety, use a combination of dependency injection and the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span>

<span data-ttu-id="c3a3b-180">См. дополнительные сведения о [внедрении зависимостей](https://en.wikipedia.org/wiki/Dependency_injection) по следующей ссылке.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-180">The following link provides more information if you want to learn more about [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection).</span></span>

1. <span data-ttu-id="c3a3b-181">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-181">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="c3a3b-182">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *Startup.cs*.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-182">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *Startup.cs*.</span></span> <span data-ttu-id="c3a3b-183">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-183">Then, select the **Add** button.</span></span>

    <span data-ttu-id="c3a3b-184">В редакторе кода откроется файл *Startup.cs*.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-184">The *Startup.cs* file opens in the code editor.</span></span> <span data-ttu-id="c3a3b-185">Добавьте в начало файла *Startup.cs* следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="c3a3b-185">Add the following using statement to the top of *Startup.cs*:</span></span>

    ```csharp
    using Microsoft.Azure.Functions.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="c3a3b-186">Удалите существующий код ниже инструкций using и добавьте следующий код в файле *Startup.cs*:</span><span class="sxs-lookup"><span data-stu-id="c3a3b-186">Remove the existing code below the using statements and add the following code to the *Startup.cs* file:</span></span>

    ```csharp
    [assembly: FunctionsStartup(typeof(Startup))]
    namespace SentimentAnalysisFunctionsApp
    {
        public class Startup : FunctionsStartup
        {
            public override void Configure(IFunctionsHostBuilder builder)
            {
                builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
                    .FromFile(modelName: "SentimentAnalysisModel", filePath:"MLModels/sentiment_model.zip", watchForChanges: true);
            }
        }
    }
    ```

<span data-ttu-id="c3a3b-187">Вкратце, этот код инициализирует объекты и службы автоматически для использования в дальнейшем по запросу приложения, вместо того чтобы вы делали это вручную.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-187">At a high level, this code initializes the objects and services automatically for later use when requested by the application instead of having to manually do it.</span></span>

<span data-ttu-id="c3a3b-188">Модели машинного обучения не являются статическими.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-188">Machine learning models are not static.</span></span> <span data-ttu-id="c3a3b-189">По мере появления новых данных для обучения модель переобучается и развертывается повторно.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-189">As new training data becomes available, the model is retrained and redeployed.</span></span> <span data-ttu-id="c3a3b-190">Одним из способов получения последней версии модели в приложении является повторное развертывание всего приложения.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-190">One way to get the latest version of the model into your application is to redeploy the entire application.</span></span> <span data-ttu-id="c3a3b-191">Однако это приводит к простою приложения.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-191">However, this introduces application downtime.</span></span> <span data-ttu-id="c3a3b-192">Служба `PredictionEnginePool` предоставляет механизм перезагрузки обновленной модели без отключения приложения.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-192">The `PredictionEnginePool` service provides a mechanism to reload an updated model without taking your application down.</span></span>

<span data-ttu-id="c3a3b-193">Задайте для параметра `watchForChanges` значение `true`. В таком случае `PredictionEnginePool` запустит объект [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher), который прослушивает уведомления об изменениях файловой системы и вызывает события при изменении файла.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-193">Set the `watchForChanges` parameter to `true`, and the `PredictionEnginePool` starts a [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) that listens to the file system change notifications and raises events when there is a change to the file.</span></span> <span data-ttu-id="c3a3b-194">При наличии изменений `PredictionEnginePool` автоматически перезагружает модель.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-194">This prompts the `PredictionEnginePool` to automatically reload the model.</span></span>

<span data-ttu-id="c3a3b-195">Модель определяется параметром `modelName`, поэтому при изменении может быть перезагружено несколько моделей на одно приложение.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-195">The model is identified by the `modelName` parameter so that more than one model per application can be reloaded upon change.</span></span>

> [!TIP]
> <span data-ttu-id="c3a3b-196">Кроме того, можно использовать метод `FromUri` при работе с моделями, сохраненными удаленно.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-196">Alternatively, you can use the `FromUri` method when working with models stored remotely.</span></span> <span data-ttu-id="c3a3b-197">Вместо наблюдения за событиями изменения файлов `FromUri` опрашивает удаленное расположение на предмет изменений.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-197">Rather than watching for file changed events, `FromUri` polls the remote location for changes.</span></span> <span data-ttu-id="c3a3b-198">Интервал опроса по умолчанию равен 5 минутам.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-198">The polling interval defaults to 5 minutes.</span></span> <span data-ttu-id="c3a3b-199">Вы можете увеличить или уменьшить интервал опроса в зависимости от требований вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-199">You can increase or decrease the polling interval based on your application's requirements.</span></span> <span data-ttu-id="c3a3b-200">В приведенном ниже примере кода `PredictionEnginePool` опрашивает модель, сохраненную по указанному универсальному коду ресурса (URI), каждую минуту.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-200">In the code sample below, the `PredictionEnginePool` polls the model stored at the specified URI every minute.</span></span>
>    
>```csharp
>builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
>   .FromUri(
>       modelName: "SentimentAnalysisModel", 
>       uri:"https://github.com/dotnet/samples/raw/master/machine-learning/models/sentimentanalysis/sentiment_model.zip", 
>       period: TimeSpan.FromMinutes(1));
>```

## <a name="load-the-model-into-the-function"></a><span data-ttu-id="c3a3b-201">Загрузка модели в функцию</span><span class="sxs-lookup"><span data-stu-id="c3a3b-201">Load the model into the function</span></span>

<span data-ttu-id="c3a3b-202">Вставьте следующий код внутри класса *AnalyzeSentiment*:</span><span class="sxs-lookup"><span data-stu-id="c3a3b-202">Insert the following code inside the *AnalyzeSentiment* class:</span></span>

[!code-csharp [AnalyzeCtor](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/AnalyzeSentiment.cs#L18-L24)]

<span data-ttu-id="c3a3b-203">Этот код назначает `PredictionEnginePool`, передав его в конструктор функции, который можно получить путем внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-203">This code assigns the `PredictionEnginePool` by passing it to the function's constructor which you get via dependency injection.</span></span>

## <a name="use-the-model-to-make-predictions"></a><span data-ttu-id="c3a3b-204">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="c3a3b-204">Use the model to make predictions</span></span>

<span data-ttu-id="c3a3b-205">Замените существующую реализацию метода *запуска* в классе *AnalyzeSentiment* следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="c3a3b-205">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

```csharp
[FunctionName("AnalyzeSentiment")]
public async Task<IActionResult> Run(
[HttpTrigger(AuthorizationLevel.Function, "post", Route = null)] HttpRequest req,
ILogger log)
{
    log.LogInformation("C# HTTP trigger function processed a request.");

    //Parse HTTP Request Body
    string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
    SentimentData data = JsonConvert.DeserializeObject<SentimentData>(requestBody);

    //Make Prediction
    SentimentPrediction prediction = _predictionEnginePool.Predict(modelName: "SentimentAnalysisModel", example: data);

    //Convert prediction to string
    string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

    //Return Prediction
    return (ActionResult)new OkObjectResult(sentiment);
}
```

<span data-ttu-id="c3a3b-206">Когда метод `Run` выполняется, входящие данные из HTTP-запроса десериализуются и используются в качестве входных данных для `PredictionEnginePool`.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-206">When the `Run` method executes, the incoming data from the HTTP request is deserialized and used as input for the `PredictionEnginePool`.</span></span> <span data-ttu-id="c3a3b-207">Затем метод `Predict` вызывается для формирования прогнозов с использованием модели `SentimentAnalysisModel`, зарегистрированной в классе `Startup`, и возвращает результаты пользователю в случае успеха.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-207">The `Predict` method is then called to make predictions using the `SentimentAnalysisModel` registered in the `Startup` class and returns the results back to the user if successful.</span></span>

## <a name="test-locally"></a><span data-ttu-id="c3a3b-208">Локальное тестирование</span><span class="sxs-lookup"><span data-stu-id="c3a3b-208">Test locally</span></span>

<span data-ttu-id="c3a3b-209">Завершив настройку параметров, протестируйте приложение:</span><span class="sxs-lookup"><span data-stu-id="c3a3b-209">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="c3a3b-210">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="c3a3b-210">Run the application</span></span>
1. <span data-ttu-id="c3a3b-211">Откройте PowerShell и введите код в командной строке, где PORT — это порт, через который работает приложение.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-211">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="c3a3b-212">Как правило, используется порт 7071.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-212">Typically the port is 7071.</span></span>

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="c3a3b-213">В случае успешного выполнения результат должен выглядеть, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="c3a3b-213">If successful, the output should look similar to the text below:</span></span>

    ```powershell
    Negative
    ```

<span data-ttu-id="c3a3b-214">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="c3a3b-214">Congratulations!</span></span> <span data-ttu-id="c3a3b-215">Вы успешно использовали модель для прогнозирования через Интернет с помощью Функций Azure.</span><span class="sxs-lookup"><span data-stu-id="c3a3b-215">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c3a3b-216">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="c3a3b-216">Next Steps</span></span>

- [<span data-ttu-id="c3a3b-217">Развертывание в Azure</span><span class="sxs-lookup"><span data-stu-id="c3a3b-217">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)
