---
title: Развертывание модели в Функциях Azure
description: Использование модели машинного обучения ML.NET для анализа тональности и прогнозирования через Интернет с помощью Функций Azure
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: c30c1c2e6f00020d22fe32fb3f53cefe88d8bb09
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063503"
---
# <a name="deploy-a-model-to-azure-functions"></a><span data-ttu-id="a6380-103">Развертывание модели в Функциях Azure</span><span class="sxs-lookup"><span data-stu-id="a6380-103">Deploy a model to Azure Functions</span></span>

<span data-ttu-id="a6380-104">Сведения о развертывании предварительно обученной модели машинного обучения ML.NET для создания прогнозов по протоколу HTTP через бессерверную среду Функций Azure.</span><span class="sxs-lookup"><span data-stu-id="a6380-104">Learn how to deploy a pre-trained ML.NET machine learning model for predictions over HTTP through an Azure Functions serverless environment.</span></span>

> [!NOTE]
> <span data-ttu-id="a6380-105">Расширение службы `PredictionEnginePool` сейчас доступно в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="a6380-105">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a6380-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="a6380-106">Prerequisites</span></span>

- <span data-ttu-id="a6380-107">[Visual Studio 2017 версии 15.6 и выше](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core" и "Разработка в Azure".</span><span class="sxs-lookup"><span data-stu-id="a6380-107">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span>
- <span data-ttu-id="a6380-108">[Средства Функций Azure](/azure/azure-functions/functions-develop-vs#check-your-tools-version).</span><span class="sxs-lookup"><span data-stu-id="a6380-108">[Azure Functions Tools](/azure/azure-functions/functions-develop-vs#check-your-tools-version)</span></span>
- <span data-ttu-id="a6380-109">PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6380-109">Powershell</span></span>
- <span data-ttu-id="a6380-110">Предварительно обученная модель.</span><span class="sxs-lookup"><span data-stu-id="a6380-110">Pre-trained model.</span></span> <span data-ttu-id="a6380-111">Используйте [учебник по анализу тональности ML.NET](../tutorials/sentiment-analysis.md), чтобы создать собственную модель, или скачайте эту [предварительно обученную модель машинного обучения для анализа тональности](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span><span class="sxs-lookup"><span data-stu-id="a6380-111">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="a6380-112">Создание проекта в Функциях Azure</span><span class="sxs-lookup"><span data-stu-id="a6380-112">Create Azure Functions project</span></span>

1. <span data-ttu-id="a6380-113">Откройте Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="a6380-113">Open Visual Studio 2017.</span></span> <span data-ttu-id="a6380-114">Выберите **Файл** > **Создать** > **Проект** в меню.</span><span class="sxs-lookup"><span data-stu-id="a6380-114">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="a6380-115">В диалоговом окне **Новый проект** щелкните узел **Visual C#**, а затем — **Облако**.</span><span class="sxs-lookup"><span data-stu-id="a6380-115">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="a6380-116">Выберите шаблон проекта **Функции Azure**.</span><span class="sxs-lookup"><span data-stu-id="a6380-116">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="a6380-117">В текстовое поле **Имя** введите SentimentAnalysisFunctionsApp и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a6380-117">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="a6380-118">В диалоговом окне **Новый проект** откройте раскрывающийся список над разделом с параметрами проекта и выберите **Функции Azure v2 (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="a6380-118">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="a6380-119">Затем щелкните проект **Триггер HTTP** и нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6380-119">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="a6380-120">Создайте каталог с именем *MLModels* в папке проекта, чтобы сохранить модель:</span><span class="sxs-lookup"><span data-stu-id="a6380-120">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="a6380-121">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="a6380-121">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="a6380-122">Введите MLModels и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="a6380-122">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="a6380-123">Установите **пакет NuGet для Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="a6380-123">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="a6380-124">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="a6380-124">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="a6380-125">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="a6380-125">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="a6380-126">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="a6380-126">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="a6380-127">Установите **пакет NuGet для Microsoft.Extensions.ML**:</span><span class="sxs-lookup"><span data-stu-id="a6380-127">Install the **Microsoft.Extensions.ML NuGet Package**:</span></span>

    <span data-ttu-id="a6380-128">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="a6380-128">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="a6380-129">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.Extensions.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="a6380-129">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="a6380-130">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="a6380-130">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-trained-model-to-project"></a><span data-ttu-id="a6380-131">Добавление предварительно обученной модели в проект</span><span class="sxs-lookup"><span data-stu-id="a6380-131">Add pre-trained model to project</span></span>

1. <span data-ttu-id="a6380-132">Скопируйте предварительно созданную модель в папку *MLModels*.</span><span class="sxs-lookup"><span data-stu-id="a6380-132">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="a6380-133">В обозревателе решений щелкните правой кнопкой мыши файл предварительно созданной модели и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a6380-133">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="a6380-134">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="a6380-134">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-azure-function-to-analyze-sentiment"></a><span data-ttu-id="a6380-135">Создание функции Azure для анализа тональности</span><span class="sxs-lookup"><span data-stu-id="a6380-135">Create Azure Function to analyze sentiment</span></span>

<span data-ttu-id="a6380-136">Создайте класс для прогнозирования тональности.</span><span class="sxs-lookup"><span data-stu-id="a6380-136">Create a class to predict sentiment.</span></span> <span data-ttu-id="a6380-137">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="a6380-137">Add a new class to your project:</span></span>

1. <span data-ttu-id="a6380-138">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="a6380-138">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="a6380-139">В диалоговом окне **Добавление нового элемента** выберите **Функция Azure** и измените значение поля **Имя** на *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="a6380-139">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="a6380-140">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a6380-140">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="a6380-141">В диалоговом окне **Новая функция Azure** щелкните **Триггер HTTP**.</span><span class="sxs-lookup"><span data-stu-id="a6380-141">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="a6380-142">Затем нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6380-142">Then, select the **OK** button.</span></span>

    <span data-ttu-id="a6380-143">В редакторе кода откроется файл *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="a6380-143">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="a6380-144">Добавьте следующий оператор `using` в начало файла *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="a6380-144">Add the following `using` statement to the top of *AnalyzeSentiment.cs*:</span></span>

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

    <span data-ttu-id="a6380-145">По умолчанию класс `AnalyzeSentiment` — `static`.</span><span class="sxs-lookup"><span data-stu-id="a6380-145">By default, the `AnalyzeSentiment` class is `static`.</span></span> <span data-ttu-id="a6380-146">Удалите ключевое слово `static` из объявления класса.</span><span class="sxs-lookup"><span data-stu-id="a6380-146">Make sure to remove the `static` keyword from the class definition.</span></span>

    ```csharp
    public class AnalyzeSentiment
    {
    
    }
    ```

## <a name="create-data-models"></a><span data-ttu-id="a6380-147">Создание моделей данных</span><span class="sxs-lookup"><span data-stu-id="a6380-147">Create data models</span></span>

<span data-ttu-id="a6380-148">Вам потребуется создать несколько классов для входных данных и прогнозов.</span><span class="sxs-lookup"><span data-stu-id="a6380-148">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="a6380-149">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="a6380-149">Add a new class to your project:</span></span>

1. <span data-ttu-id="a6380-150">Создайте каталог с именем *DataModels* в папке проекта, чтобы сохранить в нем модели данных: В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Добавить > Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="a6380-150">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="a6380-151">Введите DataModels и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="a6380-151">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="a6380-152">В обозревателе решений щелкните правой кнопкой мыши папку *DataModels* и выберите **Добавить > Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="a6380-152">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="a6380-153">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="a6380-153">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="a6380-154">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a6380-154">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="a6380-155">Файл *SentimentData.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="a6380-155">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="a6380-156">Добавьте в начало файла *SentimentData.cs* следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="a6380-156">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="a6380-157">Удалите из файла *SentimentData.cs* существующее определение класса и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="a6380-157">Remove the existing class definition and add the following code to the *SentimentData.cs* file:</span></span>
    
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

4. <span data-ttu-id="a6380-158">В обозревателе решений щелкните правой кнопкой мыши папку *DataModels* и выберите **Добавить > Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="a6380-158">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="a6380-159">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="a6380-159">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="a6380-160">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a6380-160">Then, select the **Add** button.</span></span> <span data-ttu-id="a6380-161">В редакторе кода откроется файл *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="a6380-161">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="a6380-162">Добавьте в начало файла *SentimentPrediction.cs* следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="a6380-162">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="a6380-163">Удалите из файла *SentimentPrediction.cs* существующее определение класса и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="a6380-163">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="a6380-164">`SentimentPrediction` наследует от `SentimentData`, который обеспечивает доступ к исходным данным в свойстве `SentimentText`, а также выходным данным модели.</span><span class="sxs-lookup"><span data-stu-id="a6380-164">`SentimentPrediction` inherits from `SentimentData` which provides access to the original data in the `SentimentText` property as well as the output generated by the model.</span></span>

## <a name="register-predictionenginepool-service"></a><span data-ttu-id="a6380-165">Регистрация службы PredictionEnginePool</span><span class="sxs-lookup"><span data-stu-id="a6380-165">Register PredictionEnginePool service</span></span>

<span data-ttu-id="a6380-166">Чтобы сделать один прогноз, можно использовать [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="a6380-166">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="a6380-167">Чтобы использовать [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) в приложении, следует создать его при необходимости.</span><span class="sxs-lookup"><span data-stu-id="a6380-167">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application you must create it when it's needed.</span></span> <span data-ttu-id="a6380-168">В этом случае рекомендуется внедрить зависимости.</span><span class="sxs-lookup"><span data-stu-id="a6380-168">In that case, a best practice to consider is dependency injection.</span></span>

<span data-ttu-id="a6380-169">См. дополнительные сведения о [внедрении зависимостей в ASP.NET Core](https://en.wikipedia.org/wiki/Dependency_injection).</span><span class="sxs-lookup"><span data-stu-id="a6380-169">The following link provides more information if you want to learn about [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection).</span></span>

1. <span data-ttu-id="a6380-170">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="a6380-170">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="a6380-171">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *Startup.cs*.</span><span class="sxs-lookup"><span data-stu-id="a6380-171">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *Startup.cs*.</span></span> <span data-ttu-id="a6380-172">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a6380-172">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="a6380-173">В редакторе кода откроется файл *Startup.cs*.</span><span class="sxs-lookup"><span data-stu-id="a6380-173">The *Startup.cs* file opens in the code editor.</span></span> <span data-ttu-id="a6380-174">Добавьте в начало файла *Startup.cs* следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="a6380-174">Add the following using statement to the top of *Startup.cs*:</span></span>

    ```csharp
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Hosting;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="a6380-175">Удалите существующий код ниже инструкций using и добавьте следующий код в файле *Startup.cs*:</span><span class="sxs-lookup"><span data-stu-id="a6380-175">Remove the existing code below the using statements and add the following code to the *Startup.cs* file:</span></span>

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

<span data-ttu-id="a6380-176">Вкратце, этот код инициализирует объекты и службы автоматически по запросу приложения, вместо того, чтобы вы делали это вручную.</span><span class="sxs-lookup"><span data-stu-id="a6380-176">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

> [!WARNING]
> <span data-ttu-id="a6380-177">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) не является потокобезопасным.</span><span class="sxs-lookup"><span data-stu-id="a6380-177">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="a6380-178">Для повышения производительности и безопасности потока используйте службу `PredictionEnginePool`, которая создает [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) из объектов `PredictionEngine` для использования приложений.</span><span class="sxs-lookup"><span data-stu-id="a6380-178">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> 

## <a name="register-startup-as-an-azure-functions-extension"></a><span data-ttu-id="a6380-179">Регистрация запуска в качестве расширения Функций Azure</span><span class="sxs-lookup"><span data-stu-id="a6380-179">Register Startup as an Azure Functions extension</span></span>

<span data-ttu-id="a6380-180">Чтобы использовать `Startup` в приложении, необходимо зарегистрировать его как расширение Функций Azure.</span><span class="sxs-lookup"><span data-stu-id="a6380-180">In order to use `Startup` in your application, you need to register it as an Azure Functions extension.</span></span> <span data-ttu-id="a6380-181">Создайте новый файл с именем *extensions.json* в проекте, если он еще не существует.</span><span class="sxs-lookup"><span data-stu-id="a6380-181">Create a new file called *extensions.json* in your project if one does not already exist.</span></span>

1. <span data-ttu-id="a6380-182">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="a6380-182">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="a6380-183">В диалоговом окне **Новый проект** щелкните узел **Visual C#**, а затем — узел **Веб**.</span><span class="sxs-lookup"><span data-stu-id="a6380-183">In the **New Item** dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="a6380-184">Затем выберите **Json-файл**.</span><span class="sxs-lookup"><span data-stu-id="a6380-184">Then select the **Json File** option.</span></span> <span data-ttu-id="a6380-185">В текстовом поле **Имя** введите "extensions.json", а затем нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6380-185">In the **Name** text box, type "extensions.json" and then select the **OK** button.</span></span>

    <span data-ttu-id="a6380-186">Файл *extensions.json* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="a6380-186">The *extensions.json* file opens in the code editor.</span></span> <span data-ttu-id="a6380-187">Добавьте в *extensions.json* следующее содержимое.</span><span class="sxs-lookup"><span data-stu-id="a6380-187">Add the following content to *extensions.json*:</span></span>
    
    ```json
    {
      "extensions": [
        {
          "name": "Startup",
          "typename": "SentimentAnalysisFunctionsApp.Startup, SentimentAnalysisFunctionsApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"
        }
      ]
    }
    ```

1. <span data-ttu-id="a6380-188">В обозревателе решений щелкните правой кнопкой мыши файл *extensions.json* и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a6380-188">In Solution Explorer, right-click your *extensions.json* file and select **Properties**.</span></span> <span data-ttu-id="a6380-189">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="a6380-189">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="load-the-model-into-the-function"></a><span data-ttu-id="a6380-190">Загрузка модели в функцию</span><span class="sxs-lookup"><span data-stu-id="a6380-190">Load the model into the function</span></span>

<span data-ttu-id="a6380-191">Вставьте следующий код внутри класса *AnalyzeSentiment*:</span><span class="sxs-lookup"><span data-stu-id="a6380-191">Insert the following code inside the *AnalyzeSentiment* class:</span></span>

```csharp
private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

// AnalyzeSentiment class constructor
public AnalyzeSentiment(PredictionEnginePool<SentimentData, SentimentPrediction> predictionEnginePool)
{
    _predictionEnginePool = predictionEnginePool;
}
```

<span data-ttu-id="a6380-192">Этот код назначает `PredictionEnginePool`, передав его в конструктор функции, который можно получить путем внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="a6380-192">This code assigns the `PredictionEnginePool` by passing it to the function's constructor which you get via dependency injection.</span></span>

## <a name="use-the-model-to-make-predictions"></a><span data-ttu-id="a6380-193">Использование модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="a6380-193">Use the model to make predictions</span></span>

<span data-ttu-id="a6380-194">Замените существующую реализацию метода *запуска* в классе *AnalyzeSentiment* следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="a6380-194">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

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

<span data-ttu-id="a6380-195">Когда метод `Run` выполняется, входящие данные из HTTP-запроса десериализуются и используются в качестве входных данных для `PredictionEnginePool`.</span><span class="sxs-lookup"><span data-stu-id="a6380-195">When the `Run` method executes, the incoming data from the HTTP request is deserialized and used as input for the `PredictionEnginePool`.</span></span> <span data-ttu-id="a6380-196">Затем вызывается метод `Predict` для создания прогноза и возврата результата пользователю.</span><span class="sxs-lookup"><span data-stu-id="a6380-196">The `Predict` method is then called to generate a prediction and return the result to the user.</span></span> 

## <a name="test-locally"></a><span data-ttu-id="a6380-197">Локальное тестирование</span><span class="sxs-lookup"><span data-stu-id="a6380-197">Test locally</span></span>

<span data-ttu-id="a6380-198">Завершив настройку параметров, протестируйте приложение:</span><span class="sxs-lookup"><span data-stu-id="a6380-198">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="a6380-199">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="a6380-199">Run the application</span></span>
1. <span data-ttu-id="a6380-200">Откройте PowerShell и введите код в командной строке, где PORT — это порт, через который работает приложение.</span><span class="sxs-lookup"><span data-stu-id="a6380-200">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="a6380-201">Как правило, используется порт 7071.</span><span class="sxs-lookup"><span data-stu-id="a6380-201">Typically the port is 7071.</span></span>

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="a6380-202">В случае успешного выполнения результат должен выглядеть, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="a6380-202">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="a6380-203">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="a6380-203">Congratulations!</span></span> <span data-ttu-id="a6380-204">Вы успешно использовали модель для прогнозирования через Интернет с помощью Функций Azure.</span><span class="sxs-lookup"><span data-stu-id="a6380-204">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a6380-205">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="a6380-205">Next Steps</span></span>

- [<span data-ttu-id="a6380-206">Развертывание в Azure</span><span class="sxs-lookup"><span data-stu-id="a6380-206">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)
