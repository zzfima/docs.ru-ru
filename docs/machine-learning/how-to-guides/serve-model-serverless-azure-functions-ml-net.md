---
title: Развертывание модели в Функциях Azure
description: Использование модели машинного обучения ML.NET для анализа тональности и прогнозирования через Интернет с помощью Функций Azure
ms.date: 06/11/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 7df7a6f9fcc5a4702171e1aac4b6b67e0c343748
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025975"
---
# <a name="deploy-a-model-to-azure-functions"></a><span data-ttu-id="28a3f-103">Развертывание модели в Функциях Azure</span><span class="sxs-lookup"><span data-stu-id="28a3f-103">Deploy a model to Azure Functions</span></span>

<span data-ttu-id="28a3f-104">Сведения о развертывании предварительно обученной модели машинного обучения ML.NET для создания прогнозов по протоколу HTTP через бессерверную среду Функций Azure.</span><span class="sxs-lookup"><span data-stu-id="28a3f-104">Learn how to deploy a pre-trained ML.NET machine learning model for predictions over HTTP through an Azure Functions serverless environment.</span></span>

> [!NOTE]
> <span data-ttu-id="28a3f-105">Расширение службы `PredictionEnginePool` сейчас доступно в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="28a3f-105">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="28a3f-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="28a3f-106">Prerequisites</span></span>

- <span data-ttu-id="28a3f-107">[Visual Studio 2017 версии 15.6 и выше](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core" и "Разработка в Azure".</span><span class="sxs-lookup"><span data-stu-id="28a3f-107">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span>
- <span data-ttu-id="28a3f-108">Пакет NuGet Microsoft.NET.Sdk.Functions версии 1.0.28 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="28a3f-108">Microsoft.NET.Sdk.Functions NuGet Package version 1.0.28+.</span></span>
- <span data-ttu-id="28a3f-109">[Средства Функций Azure](/azure/azure-functions/functions-develop-vs#check-your-tools-version).</span><span class="sxs-lookup"><span data-stu-id="28a3f-109">[Azure Functions Tools](/azure/azure-functions/functions-develop-vs#check-your-tools-version)</span></span>
- <span data-ttu-id="28a3f-110">PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28a3f-110">Powershell</span></span>
- <span data-ttu-id="28a3f-111">Предварительно обученная модель.</span><span class="sxs-lookup"><span data-stu-id="28a3f-111">Pre-trained model.</span></span> <span data-ttu-id="28a3f-112">Используйте [учебник по анализу тональности ML.NET](../tutorials/sentiment-analysis.md), чтобы создать собственную модель, или скачайте эту [предварительно обученную модель машинного обучения для анализа тональности](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span><span class="sxs-lookup"><span data-stu-id="28a3f-112">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="28a3f-113">Создание проекта в Функциях Azure</span><span class="sxs-lookup"><span data-stu-id="28a3f-113">Create Azure Functions project</span></span>

1. <span data-ttu-id="28a3f-114">Откройте Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="28a3f-114">Open Visual Studio 2017.</span></span> <span data-ttu-id="28a3f-115">Выберите **Файл** > **Создать** > **Проект** в меню.</span><span class="sxs-lookup"><span data-stu-id="28a3f-115">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="28a3f-116">В диалоговом окне **Новый проект** щелкните узел **Visual C#** , а затем — **Облако**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-116">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="28a3f-117">Выберите шаблон проекта **Функции Azure**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-117">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="28a3f-118">В текстовое поле **Имя** введите SentimentAnalysisFunctionsApp и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-118">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="28a3f-119">В диалоговом окне **Новый проект** откройте раскрывающийся список над разделом с параметрами проекта и выберите **Функции Azure v2 (.NET Core)** .</span><span class="sxs-lookup"><span data-stu-id="28a3f-119">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="28a3f-120">Затем щелкните проект **Триггер HTTP** и нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-120">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="28a3f-121">Создайте каталог с именем *MLModels* в папке проекта, чтобы сохранить модель:</span><span class="sxs-lookup"><span data-stu-id="28a3f-121">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="28a3f-122">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-122">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="28a3f-123">Введите MLModels и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="28a3f-123">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="28a3f-124">Установите **пакет NuGet для Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="28a3f-124">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="28a3f-125">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-125">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="28a3f-126">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-126">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="28a3f-127">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="28a3f-127">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="28a3f-128">Установите **пакет NuGet Microsoft.Azure.Functions.Extensions**:</span><span class="sxs-lookup"><span data-stu-id="28a3f-128">Install the **Microsoft.Azure.Functions.Extensions NuGet Package**:</span></span>

    <span data-ttu-id="28a3f-129">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-129">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="28a3f-130">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.Azure.Functions.Extensions**, выберите из списка этот пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-130">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Azure.Functions.Extensions**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="28a3f-131">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="28a3f-131">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="28a3f-132">Установите **пакет NuGet для Microsoft.Extensions.ML**:</span><span class="sxs-lookup"><span data-stu-id="28a3f-132">Install the **Microsoft.Extensions.ML NuGet Package**:</span></span>

    <span data-ttu-id="28a3f-133">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-133">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="28a3f-134">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.Extensions.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-134">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="28a3f-135">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="28a3f-135">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="28a3f-136">Обновите **пакет NuGet Microsoft.NET.Sdk.Functions** до версии 1.0.28:</span><span class="sxs-lookup"><span data-stu-id="28a3f-136">Update the **Microsoft.NET.Sdk.Functions NuGet Package** to version 1.0.28:</span></span>

    <span data-ttu-id="28a3f-137">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-137">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="28a3f-138">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Установленные", выполните поиск по фразе **Microsoft.NET.Sdk.Functions**, выберите из списка этот пакет, выберите версию 1.0.28 или более позднюю в раскрывающемся списке "Версия" и нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-138">Choose "nuget.org" as the Package source, select the Installed tab, search for **Microsoft.NET.Sdk.Functions**, select that package in the list, select 1.0.28 or later from the Version dropdown, and select the **Update** button.</span></span> <span data-ttu-id="28a3f-139">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="28a3f-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-trained-model-to-project"></a><span data-ttu-id="28a3f-140">Добавление предварительно обученной модели в проект</span><span class="sxs-lookup"><span data-stu-id="28a3f-140">Add pre-trained model to project</span></span>

1. <span data-ttu-id="28a3f-141">Скопируйте предварительно созданную модель в папку *MLModels*.</span><span class="sxs-lookup"><span data-stu-id="28a3f-141">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="28a3f-142">В обозревателе решений щелкните правой кнопкой мыши файл предварительно созданной модели и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-142">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="28a3f-143">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-143">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-azure-function-to-analyze-sentiment"></a><span data-ttu-id="28a3f-144">Создание функции Azure для анализа тональности</span><span class="sxs-lookup"><span data-stu-id="28a3f-144">Create Azure Function to analyze sentiment</span></span>

<span data-ttu-id="28a3f-145">Создайте класс для прогнозирования тональности.</span><span class="sxs-lookup"><span data-stu-id="28a3f-145">Create a class to predict sentiment.</span></span> <span data-ttu-id="28a3f-146">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="28a3f-146">Add a new class to your project:</span></span>

1. <span data-ttu-id="28a3f-147">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-147">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="28a3f-148">В диалоговом окне **Добавление нового элемента** выберите **Функция Azure** и измените значение поля **Имя** на *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="28a3f-148">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="28a3f-149">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-149">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="28a3f-150">В диалоговом окне **Новая функция Azure** щелкните **Триггер HTTP**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-150">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="28a3f-151">Затем нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-151">Then, select the **OK** button.</span></span>

    <span data-ttu-id="28a3f-152">В редакторе кода откроется файл *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="28a3f-152">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="28a3f-153">Добавьте следующий оператор `using` в начало файла *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="28a3f-153">Add the following `using` statement to the top of *AnalyzeSentiment.cs*:</span></span>

    ```csharp
    using System;
    using System.IO;
    using System.Threading.Tasks;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Extensions.Http;
    using Microsoft.AspNetCore.Http;
    using Microsoft.Extensions.Logging;
    using Newtonsoft.Json;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="28a3f-154">По умолчанию класс `AnalyzeSentiment` — `static`.</span><span class="sxs-lookup"><span data-stu-id="28a3f-154">By default, the `AnalyzeSentiment` class is `static`.</span></span> <span data-ttu-id="28a3f-155">Удалите ключевое слово `static` из объявления класса.</span><span class="sxs-lookup"><span data-stu-id="28a3f-155">Make sure to remove the `static` keyword from the class definition.</span></span>

    ```csharp
    public class AnalyzeSentiment
    {
    
    }
    ```

## <a name="create-data-models"></a><span data-ttu-id="28a3f-156">Создание моделей данных</span><span class="sxs-lookup"><span data-stu-id="28a3f-156">Create data models</span></span>

<span data-ttu-id="28a3f-157">Вам потребуется создать несколько классов для входных данных и прогнозов.</span><span class="sxs-lookup"><span data-stu-id="28a3f-157">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="28a3f-158">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="28a3f-158">Add a new class to your project:</span></span>

1. <span data-ttu-id="28a3f-159">Создайте каталог с именем *DataModels* в папке проекта, чтобы сохранить в нем модели данных: В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Добавить > Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-159">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="28a3f-160">Введите DataModels и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="28a3f-160">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="28a3f-161">В обозревателе решений щелкните правой кнопкой мыши папку *DataModels* и выберите **Добавить > Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-161">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="28a3f-162">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="28a3f-162">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="28a3f-163">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-163">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="28a3f-164">Файл *SentimentData.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="28a3f-164">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="28a3f-165">Добавьте в начало файла *SentimentData.cs* следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="28a3f-165">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="28a3f-166">Удалите из файла *SentimentData.cs* существующее определение класса и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="28a3f-166">Remove the existing class definition and add the following code to the *SentimentData.cs* file:</span></span>
    
    ```csharp
    public class SentimentData
    {
        [LoadColumn(0)]
        public string SentimentText;

        [LoadColumn(1)]
        [ColumnName("Label")]
        public bool Sentiment;
    }
    ```

4. <span data-ttu-id="28a3f-167">В обозревателе решений щелкните правой кнопкой мыши папку *DataModels* и выберите **Добавить > Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-167">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="28a3f-168">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="28a3f-168">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="28a3f-169">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-169">Then, select the **Add** button.</span></span> <span data-ttu-id="28a3f-170">В редакторе кода откроется файл *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="28a3f-170">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="28a3f-171">Добавьте в начало файла *SentimentPrediction.cs* следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="28a3f-171">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="28a3f-172">Удалите из файла *SentimentPrediction.cs* существующее определение класса и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="28a3f-172">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="28a3f-173">`SentimentPrediction` наследует от `SentimentData`, который обеспечивает доступ к исходным данным в свойстве `SentimentText`, а также выходным данным модели.</span><span class="sxs-lookup"><span data-stu-id="28a3f-173">`SentimentPrediction` inherits from `SentimentData` which provides access to the original data in the `SentimentText` property as well as the output generated by the model.</span></span>

## <a name="register-predictionenginepool-service"></a><span data-ttu-id="28a3f-174">Регистрация службы PredictionEnginePool</span><span class="sxs-lookup"><span data-stu-id="28a3f-174">Register PredictionEnginePool service</span></span>

<span data-ttu-id="28a3f-175">Чтобы сделать один прогноз, можно использовать [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="28a3f-175">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="28a3f-176">Чтобы использовать [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) в приложении, следует создать его при необходимости.</span><span class="sxs-lookup"><span data-stu-id="28a3f-176">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application you must create it when it's needed.</span></span> <span data-ttu-id="28a3f-177">В этом случае рекомендуется внедрить зависимости.</span><span class="sxs-lookup"><span data-stu-id="28a3f-177">In that case, a best practice to consider is dependency injection.</span></span>

<span data-ttu-id="28a3f-178">См. дополнительные сведения о [внедрении зависимостей в ASP.NET Core](https://en.wikipedia.org/wiki/Dependency_injection).</span><span class="sxs-lookup"><span data-stu-id="28a3f-178">The following link provides more information if you want to learn about [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection).</span></span>

1. <span data-ttu-id="28a3f-179">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-179">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="28a3f-180">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *Startup.cs*.</span><span class="sxs-lookup"><span data-stu-id="28a3f-180">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *Startup.cs*.</span></span> <span data-ttu-id="28a3f-181">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="28a3f-181">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="28a3f-182">В редакторе кода откроется файл *Startup.cs*.</span><span class="sxs-lookup"><span data-stu-id="28a3f-182">The *Startup.cs* file opens in the code editor.</span></span> <span data-ttu-id="28a3f-183">Добавьте в начало файла *Startup.cs* следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="28a3f-183">Add the following using statement to the top of *Startup.cs*:</span></span>

    ```csharp
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Hosting;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="28a3f-184">Удалите существующий код ниже инструкций using и добавьте следующий код в файле *Startup.cs*:</span><span class="sxs-lookup"><span data-stu-id="28a3f-184">Remove the existing code below the using statements and add the following code to the *Startup.cs* file:</span></span>

    ```csharp
    [assembly: WebJobsStartup(typeof(Startup))]
    namespace SentimentAnalysisFunctionsApp
    {
        class Startup : IWebJobsStartup
        {
            public void Configure(IWebJobsBuilder builder)
            {
                builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
                    .FromFile("MLModels/sentiment_model.zip");
            }
        }
    }
    ```

<span data-ttu-id="28a3f-185">Вкратце, этот код инициализирует объекты и службы автоматически по запросу приложения, вместо того, чтобы вы делали это вручную.</span><span class="sxs-lookup"><span data-stu-id="28a3f-185">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

> [!WARNING]
> <span data-ttu-id="28a3f-186">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) не является потокобезопасным.</span><span class="sxs-lookup"><span data-stu-id="28a3f-186">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="28a3f-187">Для повышения производительности и безопасности потока используйте службу `PredictionEnginePool`, которая создает [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) из объектов `PredictionEngine` для использования приложений.</span><span class="sxs-lookup"><span data-stu-id="28a3f-187">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> 

## <a name="load-the-model-into-the-function"></a><span data-ttu-id="28a3f-188">Загрузка модели в функцию</span><span class="sxs-lookup"><span data-stu-id="28a3f-188">Load the model into the function</span></span>

<span data-ttu-id="28a3f-189">Вставьте следующий код внутри класса *AnalyzeSentiment*:</span><span class="sxs-lookup"><span data-stu-id="28a3f-189">Insert the following code inside the *AnalyzeSentiment* class:</span></span>

```csharp
private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

// AnalyzeSentiment class constructor
public AnalyzeSentiment(PredictionEnginePool<SentimentData, SentimentPrediction> predictionEnginePool)
{
    _predictionEnginePool = predictionEnginePool;
}
```

<span data-ttu-id="28a3f-190">Этот код назначает `PredictionEnginePool`, передав его в конструктор функции, который можно получить путем внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="28a3f-190">This code assigns the `PredictionEnginePool` by passing it to the function's constructor which you get via dependency injection.</span></span>

## <a name="use-the-model-to-make-predictions"></a><span data-ttu-id="28a3f-191">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="28a3f-191">Use the model to make predictions</span></span>

<span data-ttu-id="28a3f-192">Замените существующую реализацию метода *запуска* в классе *AnalyzeSentiment* следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="28a3f-192">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

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
    SentimentPrediction prediction = _predictionEnginePool.Predict(data);

    //Convert prediction to string
    string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

    //Return Prediction
    return (ActionResult)new OkObjectResult(sentiment);
}
```

<span data-ttu-id="28a3f-193">Когда метод `Run` выполняется, входящие данные из HTTP-запроса десериализуются и используются в качестве входных данных для `PredictionEnginePool`.</span><span class="sxs-lookup"><span data-stu-id="28a3f-193">When the `Run` method executes, the incoming data from the HTTP request is deserialized and used as input for the `PredictionEnginePool`.</span></span> <span data-ttu-id="28a3f-194">Затем вызывается метод `Predict` для создания прогноза и возврата результата пользователю.</span><span class="sxs-lookup"><span data-stu-id="28a3f-194">The `Predict` method is then called to generate a prediction and return the result to the user.</span></span> 

## <a name="test-locally"></a><span data-ttu-id="28a3f-195">Локальное тестирование</span><span class="sxs-lookup"><span data-stu-id="28a3f-195">Test locally</span></span>

<span data-ttu-id="28a3f-196">Завершив настройку параметров, протестируйте приложение:</span><span class="sxs-lookup"><span data-stu-id="28a3f-196">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="28a3f-197">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="28a3f-197">Run the application</span></span>
1. <span data-ttu-id="28a3f-198">Откройте PowerShell и введите код в командной строке, где PORT — это порт, через который работает приложение.</span><span class="sxs-lookup"><span data-stu-id="28a3f-198">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="28a3f-199">Как правило, используется порт 7071.</span><span class="sxs-lookup"><span data-stu-id="28a3f-199">Typically the port is 7071.</span></span>

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="28a3f-200">В случае успешного выполнения результат должен выглядеть, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="28a3f-200">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="28a3f-201">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="28a3f-201">Congratulations!</span></span> <span data-ttu-id="28a3f-202">Вы успешно использовали модель для прогнозирования через Интернет с помощью Функций Azure.</span><span class="sxs-lookup"><span data-stu-id="28a3f-202">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="28a3f-203">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="28a3f-203">Next Steps</span></span>

- [<span data-ttu-id="28a3f-204">Развертывание в Azure</span><span class="sxs-lookup"><span data-stu-id="28a3f-204">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)
