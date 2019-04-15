---
title: Развертывание модели ML.NET в Функциях Azure
description: Использование модели машинного обучения ML.NET для анализа тональности и прогнозирования через Интернет с помощью Функций Azure
ms.date: 03/08/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 4681b37da64097dd8e537b4c956917277ecff96b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59330640"
---
# <a name="how-to-use-mlnet-model-in-azure-functions"></a><span data-ttu-id="e0ecf-103">Руководство. Использование модели ML.NET в Функциях Azure</span><span class="sxs-lookup"><span data-stu-id="e0ecf-103">How-To: Use ML.NET Model in Azure Functions</span></span>

<span data-ttu-id="e0ecf-104">В этом руководстве показано, как можно выполнить отдельные прогнозы с помощью предварительно созданных моделей машинного обучения ML.NET через Интернет в бессерверной среде, например, Функциях Azure.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-104">This how-to shows how individual predictions can be made using a pre-built ML.NET machine learning model through the internet in a serverless environment such as Azure Functions.</span></span>

> [!NOTE]
> <span data-ttu-id="e0ecf-105">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-105">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="e0ecf-106">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="e0ecf-106">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="e0ecf-107">Сейчас в этих инструкциях и примере используется **ML.NET версии 0.10**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-107">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="e0ecf-108">Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="e0ecf-108">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e0ecf-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="e0ecf-109">Prerequisites</span></span>

- <span data-ttu-id="e0ecf-110">[Visual Studio 2017 версии 15.6 и выше](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core" и "Разработка в Azure".</span><span class="sxs-lookup"><span data-stu-id="e0ecf-110">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span> 
- [<span data-ttu-id="e0ecf-111">Средства функций Azure</span><span class="sxs-lookup"><span data-stu-id="e0ecf-111">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="e0ecf-112">PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-112">Powershell</span></span>
- <span data-ttu-id="e0ecf-113">Предварительно обученная модель.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-113">Pre-trained model.</span></span> 
    - <span data-ttu-id="e0ecf-114">Используйте [руководство по анализу тональности ML.NET](../tutorials/sentiment-analysis.md), чтобы создать собственную модель.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-114">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model.</span></span>
    - <span data-ttu-id="e0ecf-115">Скачайте эту [предварительно обученную модель машинного обучения для анализа тональности](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip).</span><span class="sxs-lookup"><span data-stu-id="e0ecf-115">Download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="e0ecf-116">Создание проекта в Функциях Azure</span><span class="sxs-lookup"><span data-stu-id="e0ecf-116">Create Azure Functions Project</span></span>

1. <span data-ttu-id="e0ecf-117">Откройте Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-117">Open Visual Studio 2017.</span></span> <span data-ttu-id="e0ecf-118">Выберите **Файл** > **Создать** > **Проект** в меню.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-118">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="e0ecf-119">В диалоговом окне **Новый проект** щелкните узел **Visual C#**, а затем — **Облако**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-119">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="e0ecf-120">Выберите шаблон проекта **Функции Azure**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-120">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="e0ecf-121">В текстовое поле **Имя** введите SentimentAnalysisFunctionsApp и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-121">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="e0ecf-122">В диалоговом окне **Новый проект** откройте раскрывающийся список над разделом с параметрами проекта и выберите **Функции Azure v2 (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-122">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="e0ecf-123">Затем щелкните проект **Триггер HTTP** и нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-123">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="e0ecf-124">Создайте каталог с именем *MLModels* в папке проекта, чтобы сохранить модель:</span><span class="sxs-lookup"><span data-stu-id="e0ecf-124">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="e0ecf-125">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-125">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="e0ecf-126">Введите MLModels и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-126">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="e0ecf-127">Установите **пакет NuGet для Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="e0ecf-127">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="e0ecf-128">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-128">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="e0ecf-129">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-129">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="e0ecf-130">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-130">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-built-model-to-project"></a><span data-ttu-id="e0ecf-131">Добавление предварительно созданной модели в проект</span><span class="sxs-lookup"><span data-stu-id="e0ecf-131">Add Pre-built Model To Project</span></span>

1. <span data-ttu-id="e0ecf-132">Скопируйте предварительно созданную модель в папку *MLModels*.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-132">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="e0ecf-133">В обозревателе решений щелкните правой кнопкой мыши файл предварительно созданной модели и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-133">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="e0ecf-134">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-134">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-function-to-analyze-sentiment"></a><span data-ttu-id="e0ecf-135">Создание функции для анализа тональности</span><span class="sxs-lookup"><span data-stu-id="e0ecf-135">Create Function to Analyze Sentiment</span></span>

<span data-ttu-id="e0ecf-136">Создайте класс для прогнозирования тональности.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-136">Create a class to predict sentiment.</span></span> <span data-ttu-id="e0ecf-137">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="e0ecf-137">Add a new class to your project:</span></span>

1. <span data-ttu-id="e0ecf-138">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-138">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="e0ecf-139">В диалоговом окне **Добавление нового элемента** выберите **Функция Azure** и измените значение поля **Имя** на *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-139">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="e0ecf-140">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-140">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="e0ecf-141">В диалоговом окне **Новая функция Azure** щелкните **Триггер HTTP**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-141">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="e0ecf-142">Затем нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-142">Then, select the **OK** button.</span></span>

    <span data-ttu-id="e0ecf-143">В редакторе кода откроется файл *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-143">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="e0ecf-144">Добавьте следующий оператор `using` в начало файла *GitHubIssueData.cs*:</span><span class="sxs-lookup"><span data-stu-id="e0ecf-144">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

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
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using Microsoft.ML.Data;
using MLNETServerless.DataModels;
```

### <a name="create-data-models"></a><span data-ttu-id="e0ecf-145">Создание моделей данных</span><span class="sxs-lookup"><span data-stu-id="e0ecf-145">Create Data Models</span></span>

<span data-ttu-id="e0ecf-146">Вам потребуется создать несколько классов для входных данных и прогнозов.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-146">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="e0ecf-147">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="e0ecf-147">Add a new class to your project:</span></span>

1. <span data-ttu-id="e0ecf-148">Создайте каталог с именем *DataModels* в папке проекта, чтобы сохранить в нем модели данных: В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Добавить > Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-148">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="e0ecf-149">Введите DataModels и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-149">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="e0ecf-150">В обозревателе решений щелкните правой кнопкой мыши папку *DataModels* и выберите **Добавить > Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-150">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="e0ecf-151">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-151">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="e0ecf-152">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-152">Then, select the **Add** button.</span></span> <span data-ttu-id="e0ecf-153">Файл *SentimentData.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-153">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="e0ecf-154">Добавьте в начало файла *SentimentData.cs* следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="e0ecf-154">Add the following using statement to the top of *SentimentData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="e0ecf-155">Удалите из файла SentimentData.cs существующее определение класса и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="e0ecf-155">Remove the existing class definition and add the following code to the SentimentData.cs file:</span></span>

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }
}
```

4. <span data-ttu-id="e0ecf-156">В обозревателе решений щелкните правой кнопкой мыши папку *DataModels* и выберите **Добавить > Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-156">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="e0ecf-157">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-157">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="e0ecf-158">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-158">Then, select the **Add** button.</span></span> <span data-ttu-id="e0ecf-159">В редакторе кода откроется файл *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-159">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="e0ecf-160">Добавьте в начало файла *SentimentPrediction.cs* следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="e0ecf-160">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="e0ecf-161">Удалите из файла *SentimentPrediction.cs* существующее определение класса и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="e0ecf-161">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

### <a name="add-prediction-logic"></a><span data-ttu-id="e0ecf-162">Добавление логики прогнозирования</span><span class="sxs-lookup"><span data-stu-id="e0ecf-162">Add Prediction Logic</span></span>

<span data-ttu-id="e0ecf-163">Замените существующую реализацию метода *запуска* в классе *AnalyzeSentiment* следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="e0ecf-163">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

```csharp
    public static async Task<IActionResult> Run(
        [HttpTrigger(AuthorizationLevel.Function,"post", Route = null)] HttpRequest req,
        ILogger log)
    {
        log.LogInformation("C# HTTP trigger function processed a request.");

        //Create Context
        MLContext mlContext = new MLContext();

        //Load Model
        using (var fs = File.OpenRead("MLModels/sentiment_model.zip"))
        {
            model = mlContext.Model.Load(fs);
        }

        //Parse HTTP Request Body
        string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
        SentimentData data = JsonConvert.DeserializeObject<SentimentData>(requestBody);

        //Create Prediction Engine
        PredictionEngine<SentimentData, SentimentPrediction> predictionEngine = model.CreatePredictionEngine<SentimentData, SentimentPrediction>(mlContext);

        //Make Prediction
        SentimentPrediction prediction = predictionEngine.Predict(data);

        //Convert prediction to string
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        //Return Prediction
        return (ActionResult)new OkObjectResult(isToxic);
    }
}
```

## <a name="test-locally"></a><span data-ttu-id="e0ecf-164">Локальное тестирование</span><span class="sxs-lookup"><span data-stu-id="e0ecf-164">Test Locally</span></span>

<span data-ttu-id="e0ecf-165">Завершив настройку параметров, протестируйте приложение:</span><span class="sxs-lookup"><span data-stu-id="e0ecf-165">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="e0ecf-166">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="e0ecf-166">Run the application</span></span>
1. <span data-ttu-id="e0ecf-167">Откройте PowerShell и введите код в командной строке, где PORT — это порт, через который работает приложение.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-167">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="e0ecf-168">Как правило, используется порт 7071.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-168">Typically the port is 7071.</span></span> 

```powershell
Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

<span data-ttu-id="e0ecf-169">В случае успешного выполнения результат должен выглядеть, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="e0ecf-169">If successful, the output should look similar to the text below:</span></span>

```powershell
Toxic
```

<span data-ttu-id="e0ecf-170">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="e0ecf-170">Congratulations!</span></span> <span data-ttu-id="e0ecf-171">Вы успешно использовали модель для прогнозирования через Интернет с помощью Функций Azure.</span><span class="sxs-lookup"><span data-stu-id="e0ecf-171">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e0ecf-172">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="e0ecf-172">Next Steps</span></span>

- [<span data-ttu-id="e0ecf-173">Развертывание в Azure</span><span class="sxs-lookup"><span data-stu-id="e0ecf-173">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)