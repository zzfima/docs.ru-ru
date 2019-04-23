---
title: Использование модели машинного обучения в веб-API ASP.NET Core
description: Использование модели машинного обучения ML.NET для анализа тональности через Интернет с помощью веб-API ASP.NET Core
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: af51ccaac263202fc34d36e746722d2da46404f8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59321239"
---
# <a name="how-to-serve-machine-learning-model-through-aspnet-core-web-api"></a>Руководство. Использование модели машинного обучения с помощью веб-API ASP.NET Core

В этом руководстве показано, как использовать предварительно созданную модель машинного обучения ML.NET через интернет с помощью веб-API ASP.NET Core. Таким образом, пользователи смогут получать доступ к API для прогнозирования с помощью стандартных методов HTTP.

> [!NOTE]
> В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен. Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Сейчас в этих инструкциях и примере используется **ML.NET версии 0.10**. Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

## <a name="prerequisites"></a>Предварительные требования

- [Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".
- PowerShell.
- Предварительно обученная модель.
    - Используйте [руководство по анализу тональности ML.NET](../tutorials/sentiment-analysis.md), чтобы создать собственную модель.
    - Скачайте эту [предварительно обученную модель машинного обучения для анализа тональности](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip).

## <a name="create-aspnet-core-web-api-project"></a>Создание проекта веб-API ASP.NET Core

1. Откройте Visual Studio 2017. В меню выберите **Файл > Новый > Проект**. В диалоговом окне "Новый проект" щелкните узел **Visual C#**, а затем — **Веб**. Затем, выберите шаблон проекта **Веб-приложение ASP.NET Core**. В текстовое поле **Имя** введите SentimentAnalysisWebAPI и нажмите кнопку **ОК**.
1. В окне с разными типами проектов ASP.NET Core выберите **API** и нажмите кнопку **ОК**.
1. Создайте каталог с именем *MLModels* в папке проекта, чтобы сохранить предварительно созданные файлы модели машинного обучения:

    В обозревателе решений щелкните проект правой кнопкой мыши и выберите "Добавить" > "Новая папка". Введите MLModels и нажмите клавишу ВВОД.

1. Установите **пакет NuGet для Microsoft.ML**:

    В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**. Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку "Установить". Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**. Затем нажмите кнопку **Принимаю** в диалоговом окне "Принятие условий лицензионного соглашения", если вы согласны с условиями лицензионного соглашения для выбранных пакетов.

### <a name="add-model-to-aspnet-core-web-api-project"></a>Добавление модели в проект веб-API ASP.NET Core

1. Скопируйте предварительно созданную модель в каталог *MLModels*.
1. В обозревателе решений щелкните правой кнопкой мыши ZIP-файл модели и выберите пункт "Свойства". В разделе "Дополнительно" для параметра "Копировать в выходной каталог" установите значение "Копировать более позднюю версию".

## <a name="build-data-models"></a>Создание моделей данных

Вам потребуется создать несколько классов для входных данных и прогнозов. Добавьте в проект новый класс:

1. Создайте каталог с именем *DataModels* в папке проекта, чтобы сохранить в нем модели данных:

    В обозревателе решений щелкните проект правой кнопкой мыши и выберите "Добавить" > "Новая папка". Введите DataModels и нажмите клавишу **ВВОД**.

2. В обозревателе решений щелкните правой кнопкой мыши папку *DataModels* и выберите "Добавить" > "Новый элемент".
3. В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentData.cs*. Теперь нажмите кнопку **Добавить**. Файл *SentimentData.cs* откроется в редакторе кода. Добавьте в начало файла *SentimentData.cs* следующий оператор using:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

Удалите из файла **SentimentData.cs** существующее определение класса и добавьте следующий код:

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }   
}
```

4. В обозревателе решений щелкните правой кнопкой мыши папку *DataModels* и выберите **Добавить > Новый элемент**.
5. В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentPrediction.cs*. Теперь нажмите кнопку "Добавить". В редакторе кода откроется файл *SentimentPrediction.cs*. Добавьте в начало файла *SentimentPrediction.cs* следующий оператор using:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

Удалите из файла *SentimentPrediction.cs* существующее определение класса и добавьте следующий код:

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

## <a name="register-predictionengine-for-use-in-application"></a>Регистрация класса PredictionEngine для использования в приложении

Чтобы сделать один прогноз, можно использовать класс `PredictionEngine`. Для использования класса `PredictionEngine` в приложении вам нужно будет создавать его каждый раз, когда это необходимо. В этом случае рекомендуется внедрить зависимости ASP.NET Core.

См. дополнительные сведения о [внедрении зависимостей в ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).

1. Откройте класс *Startup.cs* и добавьте в начало файла следующий оператор using:

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

2. Добавьте в метод *ConfigureServices* следующие строки кода:

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
> `PredictionEngine` не является потокобезопасным. Чтобы ограничить затраты на создание объекта, можно сделать время существования службы *регулируемым*. *Регулируемые* объекты остаются неизменными в пределах одного запроса, но в разных запросах используются разные объекты. Дополнительные сведения о времени существования службы см. [здесь](/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1#service-lifetimes).

Вкратце, этот код инициализирует объекты и службы автоматически по запросу приложения, вместо того, чтобы вы делали это вручную.

## <a name="create-predict-controller"></a>Создание контроллера прогнозирования

Для обработки входящих HTTP-запросов необходимо создать контроллер.

1. В обозревателе решений щелкните правой кнопкой мыши папку *Контроллеры* и выберите **Добавить > Контроллер**.
1. В диалоговом окне **Добавление нового элемента** щелкните **Пустой контроллер API** и нажмите **Добавить**.
1. В запросе измените поле **Имя контроллера** на *PredictController.cs*. Теперь нажмите кнопку "Добавить". Файл *PredictController.cs* откроется в редакторе кода. Добавьте в начало файла *PredictController.cs* следующий оператор using.

```csharp
using System;
using Microsoft.AspNetCore.Mvc;
using SentimentAnalysisWebAPI.DataModels;
using Microsoft.ML;
```

Удалите из файла *PredictController.cs* существующее определение класса и добавьте следующий код:

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

Так мы назначим класс `PredictionEngine`, передав его в конструктор контроллера, который можно получить путем внедрения зависимостей. Затем в методе POST этого контроллера класс `PredictionEngine` используется для создания прогнозов. Он возвращает результаты пользователю при успешном выполнении запроса.

## <a name="test-web-api-locally"></a>Тестирование веб-API на локальном компьютере

Завершив настройку параметров, протестируйте приложение:

1. Запустите приложение.
1. Откройте PowerShell и введите следующий код, где PORT — это порт, через который приложение ожидает передачи денных.

```powershell
Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

В случае успешного выполнения результат должен выглядеть, как показано ниже:

```powershell
Toxic
```

Поздравляем! Вы успешно использовали модель для прогнозирования через Интернет с помощью API ASP.NET Core.

## <a name="next-steps"></a>Следующие шаги

- [Развертывание в Azure](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)