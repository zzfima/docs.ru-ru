---
title: Использование модели машинного обучения в веб-API ASP.NET Core
description: Использование модели машинного обучения ML.NET для анализа тональности через Интернет с помощью веб-API ASP.NET Core
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 0cc13ec22b3a8805ec4aa17bf10560b2564ccd63
ms.sourcegitcommit: 77854e8704b9689b73103d691db34d71c2bf1dad
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2019
ms.locfileid: "58307919"
---
# <a name="how-to-serve-machine-learning-model-through-aspnet-core-web-api"></a><span data-ttu-id="e5192-103">Руководство. Использование модели машинного обучения с помощью веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e5192-103">How-To: Serve Machine Learning Model Through ASP.NET Core Web API</span></span>

<span data-ttu-id="e5192-104">В этом руководстве показано, как использовать предварительно созданную модель машинного обучения ML.NET через интернет с помощью веб-API ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e5192-104">This how-to shows how to serve a pre-built ML.NET machine learning model to the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="e5192-105">Таким образом, пользователи смогут получать доступ к API для прогнозирования с помощью стандартных методов HTTP.</span><span class="sxs-lookup"><span data-stu-id="e5192-105">By doing so it allows for users to access the API for prediction purposes via standard HTTP methods.</span></span>

> [!NOTE]
> <span data-ttu-id="e5192-106">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="e5192-106">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="e5192-107">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="e5192-107">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="e5192-108">Сейчас в этих инструкциях и примере используется **ML.NET версии 0.10**.</span><span class="sxs-lookup"><span data-stu-id="e5192-108">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="e5192-109">Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="e5192-109">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e5192-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="e5192-110">Prerequisites</span></span>

- <span data-ttu-id="e5192-111">[Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="e5192-111">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="e5192-112">PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5192-112">Powershell.</span></span>
- <span data-ttu-id="e5192-113">Предварительно обученная модель.</span><span class="sxs-lookup"><span data-stu-id="e5192-113">Pre-trained model.</span></span>
    - <span data-ttu-id="e5192-114">Используйте [руководство по анализу тональности ML.NET](../tutorials/sentiment-analysis.md), чтобы создать собственную модель.</span><span class="sxs-lookup"><span data-stu-id="e5192-114">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model.</span></span>
    - <span data-ttu-id="e5192-115">Скачайте эту [предварительно обученную модель машинного обучения для анализа тональности](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip).</span><span class="sxs-lookup"><span data-stu-id="e5192-115">Download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="e5192-116">Создание проекта веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e5192-116">Create ASP.NET Core Web API Project</span></span>

1. <span data-ttu-id="e5192-117">Откройте Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="e5192-117">Open Visual Studio 2017.</span></span> <span data-ttu-id="e5192-118">В меню выберите **Файл > Новый > Проект**.</span><span class="sxs-lookup"><span data-stu-id="e5192-118">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="e5192-119">В диалоговом окне "Новый проект" щелкните узел **Visual C#**, а затем — **Веб**.</span><span class="sxs-lookup"><span data-stu-id="e5192-119">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="e5192-120">Затем, выберите шаблон проекта **Веб-приложение ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="e5192-120">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="e5192-121">В текстовое поле **Имя** введите SentimentAnalysisWebAPI и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e5192-121">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>
1. <span data-ttu-id="e5192-122">В окне с разными типами проектов ASP.NET Core выберите **API** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e5192-122">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>
1. <span data-ttu-id="e5192-123">Создайте каталог с именем *MLModels* в папке проекта, чтобы сохранить предварительно созданные файлы модели машинного обучения:</span><span class="sxs-lookup"><span data-stu-id="e5192-123">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="e5192-124">В обозревателе решений щелкните проект правой кнопкой мыши и выберите "Добавить" > "Новая папка".</span><span class="sxs-lookup"><span data-stu-id="e5192-124">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="e5192-125">Введите MLModels и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="e5192-125">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="e5192-126">Установите **пакет NuGet для Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="e5192-126">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="e5192-127">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="e5192-127">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="e5192-128">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку "Установить".</span><span class="sxs-lookup"><span data-stu-id="e5192-128">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="e5192-129">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**. Затем нажмите кнопку **Принимаю** в диалоговом окне "Принятие условий лицензионного соглашения", если вы согласны с условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="e5192-129">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="e5192-130">Добавление модели в проект веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e5192-130">Add Model to ASP.NET Core Web API Project</span></span>

1. <span data-ttu-id="e5192-131">Скопируйте предварительно созданную модель в каталог *MLModels*.</span><span class="sxs-lookup"><span data-stu-id="e5192-131">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="e5192-132">В обозревателе решений щелкните правой кнопкой мыши ZIP-файл модели и выберите пункт "Свойства".</span><span class="sxs-lookup"><span data-stu-id="e5192-132">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="e5192-133">В разделе "Дополнительно" для параметра "Копировать в выходной каталог" установите значение "Копировать более позднюю версию".</span><span class="sxs-lookup"><span data-stu-id="e5192-133">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="build-data-models"></a><span data-ttu-id="e5192-134">Создание моделей данных</span><span class="sxs-lookup"><span data-stu-id="e5192-134">Build Data Models</span></span>

<span data-ttu-id="e5192-135">Вам потребуется создать несколько классов для входных данных и прогнозов.</span><span class="sxs-lookup"><span data-stu-id="e5192-135">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="e5192-136">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="e5192-136">Add a new class to your project:</span></span>

1. <span data-ttu-id="e5192-137">Создайте каталог с именем *DataModels* в папке проекта, чтобы сохранить в нем модели данных:</span><span class="sxs-lookup"><span data-stu-id="e5192-137">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="e5192-138">В обозревателе решений щелкните проект правой кнопкой мыши и выберите "Добавить" > "Новая папка".</span><span class="sxs-lookup"><span data-stu-id="e5192-138">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="e5192-139">Введите DataModels и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="e5192-139">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="e5192-140">В обозревателе решений щелкните правой кнопкой мыши папку *DataModels* и выберите "Добавить" > "Новый элемент".</span><span class="sxs-lookup"><span data-stu-id="e5192-140">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="e5192-141">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="e5192-141">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="e5192-142">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e5192-142">Then, select the **Add** button.</span></span> <span data-ttu-id="e5192-143">Файл *SentimentData.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="e5192-143">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="e5192-144">Добавьте в начало файла *SentimentData.cs* следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="e5192-144">Add the following using statement to the top of *SentimentData.cs*:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

<span data-ttu-id="e5192-145">Удалите из файла **SentimentData.cs** существующее определение класса и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="e5192-145">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }   
}
```

4. <span data-ttu-id="e5192-146">В обозревателе решений щелкните правой кнопкой мыши папку *DataModels* и выберите **Добавить > Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="e5192-146">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="e5192-147">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="e5192-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="e5192-148">Теперь нажмите кнопку "Добавить".</span><span class="sxs-lookup"><span data-stu-id="e5192-148">Then, select the Add button.</span></span> <span data-ttu-id="e5192-149">В редакторе кода откроется файл *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="e5192-149">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="e5192-150">Добавьте в начало файла *SentimentPrediction.cs* следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="e5192-150">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

<span data-ttu-id="e5192-151">Удалите из файла *SentimentPrediction.cs* существующее определение класса и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="e5192-151">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

## <a name="register-predictionengine-for-use-in-application"></a><span data-ttu-id="e5192-152">Регистрация класса PredictionEngine для использования в приложении</span><span class="sxs-lookup"><span data-stu-id="e5192-152">Register PredictionEngine for Use in Application</span></span>

<span data-ttu-id="e5192-153">Чтобы сделать один прогноз, можно использовать класс `PredictionEngine`.</span><span class="sxs-lookup"><span data-stu-id="e5192-153">To make a single prediction, you can use `PredictionEngine`.</span></span> <span data-ttu-id="e5192-154">Для использования класса `PredictionEngine` в приложении вам нужно будет создавать его каждый раз, когда это необходимо.</span><span class="sxs-lookup"><span data-stu-id="e5192-154">In order to use `PredictionEngine` in your application you will have to create it every time it is needed.</span></span> <span data-ttu-id="e5192-155">В этом случае рекомендуется внедрить зависимости ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e5192-155">In that case, a best practice to consider is ASP.NET Core dependency injection.</span></span>

<span data-ttu-id="e5192-156">См. дополнительные сведения о [внедрении зависимостей в ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span><span class="sxs-lookup"><span data-stu-id="e5192-156">The following link provides more information if you want to learn about [dependency injection](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="e5192-157">Откройте класс *Startup.cs* и добавьте в начало файла следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="e5192-157">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

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
```

2. <span data-ttu-id="e5192-158">Добавьте в метод *ConfigureServices* следующие строки кода:</span><span class="sxs-lookup"><span data-stu-id="e5192-158">Add the following lines of code to the *ConfigureServices* method:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);

    services.AddScoped<MLContext>();
    services.AddScoped<PredictionEngine<SentimentData, SentimentPrediction>>((ctx) =>
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
}
```

> [!WARNING]
> <span data-ttu-id="e5192-159">`PredictionEngine` не является потокобезопасным.</span><span class="sxs-lookup"><span data-stu-id="e5192-159">`PredictionEngine` is not thread-safe.</span></span> <span data-ttu-id="e5192-160">Чтобы ограничить затраты на создание объекта, можно сделать время существования службы *регулируемым*.</span><span class="sxs-lookup"><span data-stu-id="e5192-160">A way that you can limit the cost of creating the object is by making its service lifetime *Scoped*.</span></span> <span data-ttu-id="e5192-161">*Регулируемые* объекты остаются неизменными в пределах одного запроса, но в разных запросах используются разные объекты.</span><span class="sxs-lookup"><span data-stu-id="e5192-161">*Scoped* objects are the same within a request but different across requests.</span></span> <span data-ttu-id="e5192-162">Дополнительные сведения о времени существования службы см. [здесь](/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1#service-lifetimes).</span><span class="sxs-lookup"><span data-stu-id="e5192-162">Visit the following link to learn more about [service lifetimes](/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1#service-lifetimes).</span></span>

<span data-ttu-id="e5192-163">Вкратце, этот код инициализирует объекты и службы автоматически по запросу приложения, вместо того, чтобы вы делали это вручную.</span><span class="sxs-lookup"><span data-stu-id="e5192-163">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

## <a name="create-predict-controller"></a><span data-ttu-id="e5192-164">Создание контроллера прогнозирования</span><span class="sxs-lookup"><span data-stu-id="e5192-164">Create Predict Controller</span></span>

<span data-ttu-id="e5192-165">Для обработки входящих HTTP-запросов необходимо создать контроллер.</span><span class="sxs-lookup"><span data-stu-id="e5192-165">To process your incoming HTTP requests, you need to create a controller.</span></span>

1. <span data-ttu-id="e5192-166">В обозревателе решений щелкните правой кнопкой мыши папку *Контроллеры* и выберите **Добавить > Контроллер**.</span><span class="sxs-lookup"><span data-stu-id="e5192-166">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="e5192-167">В диалоговом окне **Добавление нового элемента** щелкните **Пустой контроллер API** и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e5192-167">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="e5192-168">В запросе измените поле **Имя контроллера** на *PredictController.cs*.</span><span class="sxs-lookup"><span data-stu-id="e5192-168">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="e5192-169">Теперь нажмите кнопку "Добавить".</span><span class="sxs-lookup"><span data-stu-id="e5192-169">Then, select the Add button.</span></span> <span data-ttu-id="e5192-170">Файл *PredictController.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="e5192-170">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="e5192-171">Добавьте в начало файла *PredictController.cs* следующий оператор using.</span><span class="sxs-lookup"><span data-stu-id="e5192-171">Add the following using statement to the top of *PredictController.cs*:</span></span>

```csharp
using System;
using Microsoft.AspNetCore.Mvc;
using SentimentAnalysisWebAPI.DataModels;
using Microsoft.ML;
```

<span data-ttu-id="e5192-172">Удалите из файла *PredictController.cs* существующее определение класса и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="e5192-172">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>

```csharp
public class PredictController : ControllerBase
{
    
    private readonly PredictionEngine<SentimentData,SentimentPrediction> _predictionEngine;

    public PredictController(PredictionEngine<SentimentData, SentimentPrediction> predictionEngine)
    {
        _predictionEngine = predictionEngine; //Define prediction engine
    }

    [HttpPost]
    public ActionResult<string> Post([FromBody]SentimentData input)
    {
        if(!ModelState.IsValid)
        {
            return BadRequest();
        }

        // Make a prediction
        SentimentPrediction prediction = _predictionEngine.Predict(input);

        //If prediction is true then it is toxic. If it is false, the it is not.
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        return Ok(isToxic);
    }
    
}
```

<span data-ttu-id="e5192-173">Так мы назначим класс `PredictionEngine`, передав его в конструктор контроллера, который можно получить путем внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="e5192-173">This is assigning the `PredictionEngine` by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="e5192-174">Затем в методе POST этого контроллера класс `PredictionEngine` используется для создания прогнозов. Он возвращает результаты пользователю при успешном выполнении запроса.</span><span class="sxs-lookup"><span data-stu-id="e5192-174">Then, in the POST method of this controller the `PredictionEngine` is being used to make predictions and return the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="e5192-175">Тестирование веб-API на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="e5192-175">Test Web API Locally</span></span>

<span data-ttu-id="e5192-176">Завершив настройку параметров, протестируйте приложение:</span><span class="sxs-lookup"><span data-stu-id="e5192-176">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="e5192-177">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="e5192-177">Run the application.</span></span>
1. <span data-ttu-id="e5192-178">Откройте PowerShell и введите следующий код, где PORT — это порт, через который приложение ожидает передачи денных.</span><span class="sxs-lookup"><span data-stu-id="e5192-178">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

```powershell
Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

<span data-ttu-id="e5192-179">В случае успешного выполнения результат должен выглядеть, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="e5192-179">If successful, the output should look similar to the text below:</span></span>

```powershell
Toxic
```

<span data-ttu-id="e5192-180">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="e5192-180">Congratulations!</span></span> <span data-ttu-id="e5192-181">Вы успешно использовали модель для прогнозирования через Интернет с помощью API ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e5192-181">You have successfully served your model to make predictions over the internet using an ASP.NET Core API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e5192-182">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="e5192-182">Next Steps</span></span>

- [<span data-ttu-id="e5192-183">Развертывание в Azure</span><span class="sxs-lookup"><span data-stu-id="e5192-183">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)