---
title: Развертывание модели в веб-API ASP.NET Core
description: Использование модели машинного обучения ML.NET для анализа тональности через Интернет с помощью веб-API ASP.NET Core
ms.date: 08/20/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: e1dcc719738a2beb3e63463245d4721c5298cf85
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666659"
---
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a><span data-ttu-id="e2305-103">Развертывание модели в веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e2305-103">Deploy a model in an ASP.NET Core Web API</span></span>

<span data-ttu-id="e2305-104">Узнайте, как использовать предварительно обученную модель машинного обучения ML.NET через интернет с помощью веб-API ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e2305-104">Learn how to serve a pre-trained ML.NET machine learning model on the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="e2305-105">Обслуживание модели через веб-API позволяет формировать прогнозы с помощью стандартных методов HTTP.</span><span class="sxs-lookup"><span data-stu-id="e2305-105">Serving a model over a web API enables predictions via standard HTTP methods.</span></span>

> [!NOTE]
> <span data-ttu-id="e2305-106">Расширение службы `PredictionEnginePool` сейчас доступно в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="e2305-106">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e2305-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="e2305-107">Prerequisites</span></span>

- <span data-ttu-id="e2305-108">[Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="e2305-108">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="e2305-109">PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2305-109">Powershell.</span></span>
- <span data-ttu-id="e2305-110">Предварительно обученная модель.</span><span class="sxs-lookup"><span data-stu-id="e2305-110">Pre-trained model.</span></span> <span data-ttu-id="e2305-111">Используйте [учебник по анализу тональности ML.NET](../tutorials/sentiment-analysis.md), чтобы создать собственную модель, или скачайте эту [предварительно обученную модель машинного обучения для анализа тональности](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span><span class="sxs-lookup"><span data-stu-id="e2305-111">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="e2305-112">Создание проекта веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e2305-112">Create ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="e2305-113">Откройте Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="e2305-113">Open Visual Studio 2017.</span></span> <span data-ttu-id="e2305-114">В меню выберите **Файл > Новый > Проект**.</span><span class="sxs-lookup"><span data-stu-id="e2305-114">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="e2305-115">В диалоговом окне "Новый проект" щелкните узел **Visual C#** , а затем — **Веб**.</span><span class="sxs-lookup"><span data-stu-id="e2305-115">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="e2305-116">Затем, выберите шаблон проекта **Веб-приложение ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="e2305-116">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="e2305-117">В текстовое поле **Имя** введите SentimentAnalysisWebAPI и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e2305-117">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>

1. <span data-ttu-id="e2305-118">В окне с разными типами проектов ASP.NET Core выберите **API** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e2305-118">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>

1. <span data-ttu-id="e2305-119">Создайте каталог с именем *MLModels* в папке проекта, чтобы сохранить предварительно созданные файлы модели машинного обучения:</span><span class="sxs-lookup"><span data-stu-id="e2305-119">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="e2305-120">В обозревателе решений щелкните проект правой кнопкой мыши и выберите "Добавить" > "Новая папка".</span><span class="sxs-lookup"><span data-stu-id="e2305-120">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="e2305-121">Введите MLModels и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="e2305-121">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="e2305-122">Установите **пакет NuGet для Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="e2305-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="e2305-123">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="e2305-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="e2305-124">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку "Установить".</span><span class="sxs-lookup"><span data-stu-id="e2305-124">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="e2305-125">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**. Затем нажмите кнопку **Принимаю** в диалоговом окне "Принятие условий лицензионного соглашения", если вы согласны с условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="e2305-125">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="e2305-126">Установите **пакет NuGet для Microsoft.Extensions.ML**:</span><span class="sxs-lookup"><span data-stu-id="e2305-126">Install the **Microsoft.Extensions.ML Nuget Package**:</span></span>

    <span data-ttu-id="e2305-127">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="e2305-127">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="e2305-128">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.Extensions.ML**, выберите из списка этот пакет и нажмите кнопку "Установить".</span><span class="sxs-lookup"><span data-stu-id="e2305-128">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="e2305-129">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**. Затем нажмите кнопку **Принимаю** в диалоговом окне "Принятие условий лицензионного соглашения", если вы согласны с условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="e2305-129">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="e2305-130">Добавление модели в проект веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e2305-130">Add model to ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="e2305-131">Скопируйте предварительно созданную модель в каталог *MLModels*.</span><span class="sxs-lookup"><span data-stu-id="e2305-131">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="e2305-132">В обозревателе решений щелкните правой кнопкой мыши ZIP-файл модели и выберите пункт "Свойства".</span><span class="sxs-lookup"><span data-stu-id="e2305-132">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="e2305-133">В разделе "Дополнительно" для параметра "Копировать в выходной каталог" установите значение "Копировать более позднюю версию".</span><span class="sxs-lookup"><span data-stu-id="e2305-133">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="create-data-models"></a><span data-ttu-id="e2305-134">Создание моделей данных</span><span class="sxs-lookup"><span data-stu-id="e2305-134">Create data models</span></span>

<span data-ttu-id="e2305-135">Вам потребуется создать несколько классов для входных данных и прогнозов.</span><span class="sxs-lookup"><span data-stu-id="e2305-135">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="e2305-136">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="e2305-136">Add a new class to your project:</span></span>

1. <span data-ttu-id="e2305-137">Создайте каталог с именем *DataModels* в папке проекта, чтобы сохранить в нем модели данных:</span><span class="sxs-lookup"><span data-stu-id="e2305-137">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="e2305-138">В обозревателе решений щелкните проект правой кнопкой мыши и выберите "Добавить" > "Новая папка".</span><span class="sxs-lookup"><span data-stu-id="e2305-138">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="e2305-139">Введите DataModels и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="e2305-139">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="e2305-140">В обозревателе решений щелкните правой кнопкой мыши папку *DataModels* и выберите "Добавить" > "Новый элемент".</span><span class="sxs-lookup"><span data-stu-id="e2305-140">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="e2305-141">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="e2305-141">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="e2305-142">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e2305-142">Then, select the **Add** button.</span></span> <span data-ttu-id="e2305-143">Файл *SentimentData.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="e2305-143">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="e2305-144">Добавьте в начало файла *SentimentData.cs* следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="e2305-144">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```
    
    <span data-ttu-id="e2305-145">Удалите из файла **SentimentData.cs** существующее определение класса и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="e2305-145">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>
    
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

4. <span data-ttu-id="e2305-146">В обозревателе решений щелкните правой кнопкой мыши папку *DataModels* и выберите **Добавить > Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="e2305-146">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="e2305-147">В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="e2305-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="e2305-148">Теперь нажмите кнопку "Добавить".</span><span class="sxs-lookup"><span data-stu-id="e2305-148">Then, select the Add button.</span></span> <span data-ttu-id="e2305-149">В редакторе кода откроется файл *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="e2305-149">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="e2305-150">Добавьте в начало файла *SentimentPrediction.cs* следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="e2305-150">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```
    
    <span data-ttu-id="e2305-151">Удалите из файла *SentimentPrediction.cs* существующее определение класса и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="e2305-151">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>
    
    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="e2305-152">Тип`SentimentPrediction` наследуется от типа `SentimentData`.</span><span class="sxs-lookup"><span data-stu-id="e2305-152">`SentimentPrediction` inherits from `SentimentData`.</span></span> <span data-ttu-id="e2305-153">Это упрощает просмотр исходных данных в свойстве `SentimentText`, а также выходных данных модели.</span><span class="sxs-lookup"><span data-stu-id="e2305-153">This makes it easier to see the original data in the `SentimentText` property along with the output generated by the model.</span></span> 

## <a name="register-predictionenginepool-for-use-in-the-application"></a><span data-ttu-id="e2305-154">Регистрация класса PredictionEnginePool для использования в приложении</span><span class="sxs-lookup"><span data-stu-id="e2305-154">Register PredictionEnginePool for use in the application</span></span>

<span data-ttu-id="e2305-155">Чтобы сделать один прогноз, можно использовать [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="e2305-155">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="e2305-156">Чтобы использовать [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) в приложении, следует создать его при необходимости.</span><span class="sxs-lookup"><span data-stu-id="e2305-156">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application you must create it when it's needed.</span></span> <span data-ttu-id="e2305-157">В этом случае рекомендуется внедрить зависимости.</span><span class="sxs-lookup"><span data-stu-id="e2305-157">In that case, a best practice to consider is dependency injection.</span></span>

<span data-ttu-id="e2305-158">См. дополнительные сведения о [внедрении зависимостей в ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span><span class="sxs-lookup"><span data-stu-id="e2305-158">The following link provides more information if you want to learn about [dependency injection in ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="e2305-159">Откройте класс *Startup.cs* и добавьте в начало файла следующий оператор using:</span><span class="sxs-lookup"><span data-stu-id="e2305-159">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. <span data-ttu-id="e2305-160">Добавьте в метод *ConfigureServices* следующий код:</span><span class="sxs-lookup"><span data-stu-id="e2305-160">Add the following code to the *ConfigureServices* method:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);
        services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
            .FromFile("MLModels/sentiment_model.zip");
    }
    ```

<span data-ttu-id="e2305-161">Вкратце, этот код инициализирует объекты и службы автоматически по запросу приложения, вместо того, чтобы вы делали это вручную.</span><span class="sxs-lookup"><span data-stu-id="e2305-161">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

> [!WARNING]
> <span data-ttu-id="e2305-162">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) не является потокобезопасным.</span><span class="sxs-lookup"><span data-stu-id="e2305-162">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="e2305-163">Для повышения производительности и безопасности потока используйте службу `PredictionEnginePool`, которая создает [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) из объектов `PredictionEngine` для использования приложений.</span><span class="sxs-lookup"><span data-stu-id="e2305-163">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> <span data-ttu-id="e2305-164">Прочтите следующую запись блога, чтобы узнать о [создании и использовании пулов объектов `PredictionEngine` в ASP.NET Core](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span><span class="sxs-lookup"><span data-stu-id="e2305-164">Read the following blog post to learn more about [creating and using `PredictionEngine` object pools in ASP.NET Core](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span></span>  

## <a name="create-predict-controller"></a><span data-ttu-id="e2305-165">Создание контроллера прогнозирования</span><span class="sxs-lookup"><span data-stu-id="e2305-165">Create Predict controller</span></span>

<span data-ttu-id="e2305-166">Для обработки входящих HTTP-запросов создайте контроллер.</span><span class="sxs-lookup"><span data-stu-id="e2305-166">To process your incoming HTTP requests, create a controller.</span></span>

1. <span data-ttu-id="e2305-167">В обозревателе решений щелкните правой кнопкой мыши папку *Контроллеры* и выберите **Добавить > Контроллер**.</span><span class="sxs-lookup"><span data-stu-id="e2305-167">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="e2305-168">В диалоговом окне **Добавление нового элемента** щелкните **Пустой контроллер API** и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e2305-168">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="e2305-169">В запросе измените поле **Имя контроллера** на *PredictController.cs*.</span><span class="sxs-lookup"><span data-stu-id="e2305-169">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="e2305-170">Теперь нажмите кнопку "Добавить".</span><span class="sxs-lookup"><span data-stu-id="e2305-170">Then, select the Add button.</span></span> <span data-ttu-id="e2305-171">Файл *PredictController.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="e2305-171">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="e2305-172">Добавьте в начало файла *PredictController.cs* следующий оператор using.</span><span class="sxs-lookup"><span data-stu-id="e2305-172">Add the following using statement to the top of *PredictController.cs*:</span></span>

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    <span data-ttu-id="e2305-173">Удалите из файла *PredictController.cs* существующее определение класса и добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="e2305-173">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>
    
    ```csharp
    public class PredictController : ControllerBase
    {
        private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

        public PredictController(PredictionEnginePool<SentimentData,SentimentPrediction> predictionEnginePool)
        {
            _predictionEnginePool = predictionEnginePool;
        }

        [HttpPost]
        public ActionResult<string> Post([FromBody] SentimentData input)
        {
            if(!ModelState.IsValid)
            {
                return BadRequest();
            }

            SentimentPrediction prediction = _predictionEnginePool.Predict(input);

            string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

            return Ok(sentiment);
        }
    }
    ```

<span data-ttu-id="e2305-174">Этот код назначает класс `PredictionEnginePool`, передав его в конструктор контроллера, который можно получить путем внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="e2305-174">This code assigns the `PredictionEnginePool` by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="e2305-175">После этого метод `Post` контроллера `Predict` использует `PredictionEnginePool` для создания прогнозов. Он возвращает результаты пользователю при успешном выполнении запроса.</span><span class="sxs-lookup"><span data-stu-id="e2305-175">Then, the `Predict` controller's `Post` method uses the `PredictionEnginePool` to make predictions and return the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="e2305-176">Тестирование веб-API на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="e2305-176">Test web API locally</span></span>

<span data-ttu-id="e2305-177">Завершив настройку параметров, протестируйте приложение:</span><span class="sxs-lookup"><span data-stu-id="e2305-177">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="e2305-178">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="e2305-178">Run the application.</span></span>
1. <span data-ttu-id="e2305-179">Откройте PowerShell и введите следующий код, где PORT — это порт, через который приложение ожидает передачи денных.</span><span class="sxs-lookup"><span data-stu-id="e2305-179">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{SentimentText="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="e2305-180">В случае успешного выполнения результат должен выглядеть, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="e2305-180">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="e2305-181">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="e2305-181">Congratulations!</span></span> <span data-ttu-id="e2305-182">Вы успешно использовали модель для прогнозирования через Интернет с помощью веб-API ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e2305-182">You have successfully served your model to make predictions over the internet using an ASP.NET Core Web API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e2305-183">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="e2305-183">Next Steps</span></span>

- [<span data-ttu-id="e2305-184">Развертывание в Azure</span><span class="sxs-lookup"><span data-stu-id="e2305-184">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)
