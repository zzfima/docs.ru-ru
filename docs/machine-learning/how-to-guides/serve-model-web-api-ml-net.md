---
title: Использование модели машинного обучения в веб-API ASP.NET Core
description: Использование модели машинного обучения ML.NET для анализа тональности через Интернет с помощью веб-API ASP.NET Core
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 07b751caff8ef0ca9a23bed68ddf88feb7b5ae4f
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57856710"
---
# <a name="how-to-serve-machine-learning-model-through-aspnet-core-web-api"></a><span data-ttu-id="2c557-103">Руководство. Использование модели машинного обучения с помощью веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2c557-103">How-To: Serve Machine Learning Model Through ASP.NET Core Web API</span></span>

<span data-ttu-id="2c557-104">В этом руководстве показано, как использовать предварительно созданную модель машинного обучения ML.NET через интернет с помощью веб-API ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2c557-104">This how-to shows how to serve a pre-built ML.NET machine learning model to the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="2c557-105">Таким образом, пользователи смогут получать доступ к API для прогнозирования с помощью стандартных методов HTTP.</span><span class="sxs-lookup"><span data-stu-id="2c557-105">By doing so it allows for users to access the API for prediction purposes via standard HTTP methods.</span></span>

> [!NOTE]
> <span data-ttu-id="2c557-106">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="2c557-106">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="2c557-107">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="2c557-107">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="2c557-108">Сейчас в этих инструкциях и примере используется **ML.NET версии 0.10**.</span><span class="sxs-lookup"><span data-stu-id="2c557-108">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="2c557-109">Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="2c557-109">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2c557-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2c557-110">Prerequisites</span></span>

- <span data-ttu-id="2c557-111">[Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="2c557-111">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="2c557-112">PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c557-112">Powershell.</span></span>
- <span data-ttu-id="2c557-113">Предварительно обученная модель.</span><span class="sxs-lookup"><span data-stu-id="2c557-113">Pre-trained model.</span></span>
    - <span data-ttu-id="2c557-114">Используйте [руководство по анализу тональности ML.NET](../tutorials/sentiment-analysis.md), чтобы создать собственную модель.</span><span class="sxs-lookup"><span data-stu-id="2c557-114">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model.</span></span>
    - <span data-ttu-id="2c557-115">Скачайте эту [предварительно обученную модель машинного обучения для анализа тональности](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip).</span><span class="sxs-lookup"><span data-stu-id="2c557-115">Download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="2c557-116">Создание проекта веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2c557-116">Create ASP.NET Core Web API Project</span></span>

1. <span data-ttu-id="2c557-117">Откройте Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="2c557-117">Open Visual Studio 2017.</span></span> <span data-ttu-id="2c557-118">В меню выберите **Файл > Новый > Проект**.</span><span class="sxs-lookup"><span data-stu-id="2c557-118">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="2c557-119">В диалоговом окне "Новый проект" щелкните узел **Visual C#**, а затем — **Веб**.</span><span class="sxs-lookup"><span data-stu-id="2c557-119">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="2c557-120">Затем, выберите шаблон проекта **Веб-приложение ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="2c557-120">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="2c557-121">В текстовое поле **Имя** введите SentimentAnalysisWebAPI и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2c557-121">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>
1. <span data-ttu-id="2c557-122">В окне с разными типами проектов ASP.NET Core выберите **API** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2c557-122">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>
1. <span data-ttu-id="2c557-123">Создайте каталог с именем *MLModels* в папке проекта, чтобы сохранить предварительно созданные файлы модели машинного обучения:</span><span class="sxs-lookup"><span data-stu-id="2c557-123">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="2c557-124">В обозревателе решений щелкните проект правой кнопкой мыши и выберите "Добавить" > "Новая папка".</span><span class="sxs-lookup"><span data-stu-id="2c557-124">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="2c557-125">Введите MLModels и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="2c557-125">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="2c557-126">Установите **пакет NuGet для Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="2c557-126">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="2c557-127">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="2c557-127">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="2c557-128">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку "Установить".</span><span class="sxs-lookup"><span data-stu-id="2c557-128">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="2c557-129">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**. Затем нажмите кнопку **Принимаю** в диалоговом окне "Принятие условий лицензионного соглашения", если вы согласны с условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="2c557-129">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="2c557-130">Добавление модели в проект веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2c557-130">Add Model to ASP.NET Core Web API Project</span></span>

1. <span data-ttu-id="2c557-131">Скопируйте предварительно созданную модель в каталог *MLModels*.</span><span class="sxs-lookup"><span data-stu-id="2c557-131">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="2c557-132">В обозревателе решений щелкните правой кнопкой мыши ZIP-файл модели и выберите пункт "Свойства".</span><span class="sxs-lookup"><span data-stu-id="2c557-132">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="2c557-133">В разделе "Дополнительно" для параметра "Копировать в выходной каталог" установите значение "Копировать более позднюю версию".</span><span class="sxs-lookup"><span data-stu-id="2c557-133">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="build-data-models"></a><span data-ttu-id="2c557-134">Создание моделей данных</span><span class="sxs-lookup"><span data-stu-id="2c557-134">Build Data Models</span></span>

<span data-ttu-id="2c557-135">Вам потребуется создать несколько классов для входных данных и прогнозов.</span><span class="sxs-lookup"><span data-stu-id="2c557-135">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="2c557-136">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="2c557-136">Add a new class to your project:</span></span>

1. <span data-ttu-id="2c557-137">Создайте каталог с именем *DataModels* в папке проекта, чтобы сохранить в нем модели данных:</span><span class="sxs-lookup"><span data-stu-id="2c557-137">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="2c557-138">В обозревателе решений щелкните проект правой кнопкой мыши и выберите "Добавить" > "Новая папка".</span><span class="sxs-lookup"><span data-stu-id="2c557-138">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="2c557-139">Введите DataModels и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="2c557-139">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="2c557-140">В обозревателе решений щелкните правой кнопкой мыши папку *DataModels* и выберите "Добавить" > "Новый элемент".</span><span class="sxs-lookup"><span data-stu-id="2c557-140">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="2c557-141">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="2c557-141">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="2c557-142">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2c557-142">Then, select the **Add** button.</span></span> <span data-ttu-id="2c557-143">Файл *SentimentData.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="2c557-143">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="2c557-144">Добавьте в начало файла *SentimentData.cs* следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="2c557-144">Add the following using statement to the top of *SentimentData.cs*:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

<span data-ttu-id="2c557-145">Удалите из файла **SentimentData.cs** существующее определение класса и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="2c557-145">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }   
}
```

4. <span data-ttu-id="2c557-146">В обозревателе решений щелкните правой кнопкой мыши папку *DataModels* и выберите **Добавить > Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="2c557-146">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="2c557-147">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="2c557-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="2c557-148">Теперь нажмите кнопку "Добавить".</span><span class="sxs-lookup"><span data-stu-id="2c557-148">Then, select the Add button.</span></span> <span data-ttu-id="2c557-149">В редакторе кода откроется файл *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="2c557-149">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="2c557-150">Добавьте в начало файла *SentimentPrediction.cs* следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="2c557-150">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

<span data-ttu-id="2c557-151">Удалите из файла *SentimentPrediction.cs* существующее определение класса и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="2c557-151">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

## <a name="create-prediction-service"></a><span data-ttu-id="2c557-152">Создание службы прогнозирования</span><span class="sxs-lookup"><span data-stu-id="2c557-152">Create Prediction Service</span></span>

<span data-ttu-id="2c557-153">Создайте службу прогнозирования для организации и повторного использования логики прогнозирования во всем приложении.</span><span class="sxs-lookup"><span data-stu-id="2c557-153">To organize and re-use the prediction logic throughout the entire application, create a prediction service.</span></span>

1. <span data-ttu-id="2c557-154">Создайте папку с названием *Службы* в проекте, чтобы добавить службы, используемые приложением:</span><span class="sxs-lookup"><span data-stu-id="2c557-154">Create a directory named *Services* in your project to hold services to be used by the application:</span></span>

    <span data-ttu-id="2c557-155">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Добавить > Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="2c557-155">In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="2c557-156">Введите "Службы" и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="2c557-156">Type "Services" and hit **Enter**.</span></span>

1. <span data-ttu-id="2c557-157">В обозревателе решений щелкните правой кнопкой мыши папку *Службы* и выберите **Добавить > Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="2c557-157">In Solution Explorer, right-click the *Services* directory, and then select **Add > New Item**.</span></span>
1. <span data-ttu-id="2c557-158">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *PredictionService.cs*.</span><span class="sxs-lookup"><span data-stu-id="2c557-158">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *PredictionService.cs*.</span></span> <span data-ttu-id="2c557-159">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2c557-159">Then, select the **Add** button.</span></span> <span data-ttu-id="2c557-160">В редакторе кода откроется файл *PredictionService.cs*.</span><span class="sxs-lookup"><span data-stu-id="2c557-160">The *PredictionService.cs* file opens in the code editor.</span></span> <span data-ttu-id="2c557-161">Добавьте в начало файла *PredictionService.cs* следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="2c557-161">Add the following using statement to the top of *PredictionService.cs*:</span></span>

```csharp
using System;
using System.IO;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using SentimentAnalysisWebAPI.DataModels;
```

<span data-ttu-id="2c557-162">Удалите из файла *PredictionService.cs* существующее определение класса и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="2c557-162">Remove the existing class definition and add the following code to the *PredictionService.cs* file:</span></span>

```csharp
public class PredictionService
{
    private readonly PredictionEngine<SentimentData, SentimentPrediction> _predictionEngine;
    public PredictionService(PredictionEngine<SentimentData,SentimentPrediction> predictionEngine)
    {
        _predictionEngine = predictionEngine;
    }

    public string Predict(SentimentData input)
    {
        // Make a prediction
        SentimentPrediction prediction = _predictionEngine.Predict(input);

        //If prediction is true then it is toxic. If it is false, the it is not.
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        return isToxic;

    }
}
```

## <a name="register-predictions-service-for-use-in-application"></a><span data-ttu-id="2c557-163">Регистрация службы прогнозирования для использования в приложении</span><span class="sxs-lookup"><span data-stu-id="2c557-163">Register Predictions Service for Use in Application</span></span>

<span data-ttu-id="2c557-164">Чтобы использовать службу прогнозирования в приложении, вам нужно будет создавать ее каждый раз, когда это необходимо.</span><span class="sxs-lookup"><span data-stu-id="2c557-164">To use the prediction service in your application you will have to create it every time it is needed.</span></span> <span data-ttu-id="2c557-165">В этом случае рекомендуется внедрить зависимости ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2c557-165">In that case, a best practice to consider is ASP.NET Core dependency injection.</span></span>

<span data-ttu-id="2c557-166">См. дополнительные сведения о [внедрении зависимостей в ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span><span class="sxs-lookup"><span data-stu-id="2c557-166">The following link provides more information if you want to learn about [dependency injection](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="2c557-167">Откройте класс *Startup.cs* и добавьте в начало файла следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="2c557-167">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

```csharp
using System.IO;
using Microsoft.AspNetCore.Builder;
using Microsoft.AspNetCore.Hosting;
using Microsoft.AspNetCore.Mvc;
using Microsoft.Extensions.Configuration;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using SentimentAnalysisWebAPI.DataModels;
using SentimentAnalysisWebAPI.Services;
```

1. <span data-ttu-id="2c557-168">Добавьте в метод *ConfigureServices* следующие строки кода:</span><span class="sxs-lookup"><span data-stu-id="2c557-168">Add the following lines of code to the *ConfigureServices* method:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);

    services.AddSingleton<MLContext>();
    services.AddSingleton<PredictionEngine<SentimentData, SentimentPrediction>>((ctx) =>
    {
        MLContext mlContext = ctx.GetRequiredService<MLContext>();
        string modelFilePathName = "MLModels/sentiment_model.zip";

        //Load model from file
        ITransformer model;
        using (var stream = File.OpenRead(modelFilePathName))
        {
            model = mlContext.Model.Load(stream);
        }

        // Return prediction engine
        return model.CreatePredictionEngine<SentimentData, SentimentPrediction>(mlContext);
    });
    services.AddSingleton<PredictionService>();
}
```

<span data-ttu-id="2c557-169">Вкратце, этот код инициализирует объекты и службы автоматически по запросу приложения, вместо того, чтобы вы делали это вручную.</span><span class="sxs-lookup"><span data-stu-id="2c557-169">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

## <a name="create-predict-controller"></a><span data-ttu-id="2c557-170">Создание контроллера прогнозирования</span><span class="sxs-lookup"><span data-stu-id="2c557-170">Create Predict Controller</span></span>

<span data-ttu-id="2c557-171">Для обработки входящих HTTP-запросов необходимо создать контроллер.</span><span class="sxs-lookup"><span data-stu-id="2c557-171">To process your incoming HTTP requests, you need to create a controller.</span></span>

1. <span data-ttu-id="2c557-172">В обозревателе решений щелкните правой кнопкой мыши папку *Контроллеры* и выберите **Добавить > Контроллер**.</span><span class="sxs-lookup"><span data-stu-id="2c557-172">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="2c557-173">В диалоговом окне **Добавление нового элемента** щелкните **Пустой контроллер API** и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2c557-173">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="2c557-174">В запросе измените поле **Имя контроллера** на *PredictController.cs*.</span><span class="sxs-lookup"><span data-stu-id="2c557-174">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="2c557-175">Теперь нажмите кнопку "Добавить".</span><span class="sxs-lookup"><span data-stu-id="2c557-175">Then, select the Add button.</span></span> <span data-ttu-id="2c557-176">Файл *PredictController.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="2c557-176">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="2c557-177">Добавьте в начало файла *PredictController.cs* следующий оператор using.</span><span class="sxs-lookup"><span data-stu-id="2c557-177">Add the following using statement to the top of *PredictController.cs*:</span></span>

```csharp
using Microsoft.AspNetCore.Mvc;
using SentimentAnalysisWebAPI.DataModels;
using SentimentAnalysisWebAPI.Services;
```

<span data-ttu-id="2c557-178">Удалите из файла *PredictController.cs* существующее определение класса и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="2c557-178">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>

```csharp
public class PredictController : ControllerBase
{

    private readonly PredictionService _predictionService;

    public PredictController(PredictionService predictionService)
    {
        _predictionService = predictionService; //Define prediction service
    }

    [HttpPost]
    public ActionResult<string> Post([FromBody]SentimentData input)
    {
        if(!ModelState.IsValid)
        {
            return BadRequest();
        }
        return Ok(_predictionService.Predict(input));
    }

}
```

<span data-ttu-id="2c557-179">Так мы назначим службу прогнозирования, передав ее в конструктор контроллера, который можно получить путем внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="2c557-179">This is assigning the Prediction service by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="2c557-180">Затем в методе POST этого контроллера служба прогнозирования используется для создания прогнозов. Она возвращает результаты пользователю при успешном выполнении запроса.</span><span class="sxs-lookup"><span data-stu-id="2c557-180">Then, in the POST method of this controller the Prediction service is being used to make predictions and return the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="2c557-181">Тестирование веб-API на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="2c557-181">Test Web API Locally</span></span>

<span data-ttu-id="2c557-182">Завершив настройку параметров, протестируйте приложение:</span><span class="sxs-lookup"><span data-stu-id="2c557-182">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="2c557-183">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="2c557-183">Run the application.</span></span>
1. <span data-ttu-id="2c557-184">Откройте PowerShell и введите следующий код, где PORT — это порт, через который приложение ожидает передачи денных.</span><span class="sxs-lookup"><span data-stu-id="2c557-184">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

```powershell
Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

<span data-ttu-id="2c557-185">В случае успешного выполнения результат должен выглядеть, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="2c557-185">If successful, the output should look similar to the text below:</span></span>

```powershell
Toxic
```

<span data-ttu-id="2c557-186">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="2c557-186">Congratulations!</span></span> <span data-ttu-id="2c557-187">Вы успешно использовали модель для прогнозирования через Интернет с помощью API ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2c557-187">You have successfully served your model to make predictions over the internet using an ASP.NET Core API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2c557-188">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="2c557-188">Next Steps</span></span>

- [<span data-ttu-id="2c557-189">Развертывание в Azure</span><span class="sxs-lookup"><span data-stu-id="2c557-189">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)