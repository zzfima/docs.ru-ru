---
title: Развертывание модели в веб-API ASP.NET Core
description: Использование модели машинного обучения ML.NET для анализа тональности через Интернет с помощью веб-API ASP.NET Core
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: f8b8f74f752aeb243d4a2987929bd28ddc5f7d5a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641084"
---
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a>Развертывание модели в веб-API ASP.NET Core

Узнайте, как использовать предварительно обученную модель машинного обучения ML.NET через интернет с помощью веб-API ASP.NET Core. Обслуживание модели через веб-API позволяет формировать прогнозы с помощью стандартных методов HTTP.

> [!NOTE]
> Расширение службы `PredictionEnginePool` сейчас доступно в предварительной версии.

## <a name="prerequisites"></a>Предварительные требования

- [Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".
- PowerShell.
- Предварительно обученная модель. Используйте [учебник по анализу тональности ML.NET](../tutorials/sentiment-analysis.md), чтобы создать собственную модель, или скачайте эту [предварительно обученную модель машинного обучения для анализа тональности](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)

## <a name="create-aspnet-core-web-api-project"></a>Создание проекта веб-API ASP.NET Core

1. Откройте Visual Studio 2017. В меню выберите **Файл > Новый > Проект**. В диалоговом окне "Новый проект" щелкните узел **Visual C#**, а затем — **Веб**. Затем, выберите шаблон проекта **Веб-приложение ASP.NET Core**. В текстовое поле **Имя** введите SentimentAnalysisWebAPI и нажмите кнопку **ОК**.

1. В окне с разными типами проектов ASP.NET Core выберите **API** и нажмите кнопку **ОК**.

1. Создайте каталог с именем *MLModels* в папке проекта, чтобы сохранить предварительно созданные файлы модели машинного обучения:

    В обозревателе решений щелкните проект правой кнопкой мыши и выберите "Добавить" > "Новая папка". Введите MLModels и нажмите клавишу ВВОД.

1. Установите **пакет NuGet для Microsoft.ML**:

    В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**. Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку "Установить". Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**. Затем нажмите кнопку **Принимаю** в диалоговом окне "Принятие условий лицензионного соглашения", если вы согласны с условиями лицензионного соглашения для выбранных пакетов.

1. Установите **пакет NuGet для Microsoft.Extensions.ML**:

    В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**. Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.Extensions.ML**, выберите из списка этот пакет и нажмите кнопку "Установить". Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**. Затем нажмите кнопку **Принимаю** в диалоговом окне "Принятие условий лицензионного соглашения", если вы согласны с условиями лицензионного соглашения для выбранных пакетов.

### <a name="add-model-to-aspnet-core-web-api-project"></a>Добавление модели в проект веб-API ASP.NET Core

1. Скопируйте предварительно созданную модель в каталог *MLModels*.
1. В обозревателе решений щелкните правой кнопкой мыши ZIP-файл модели и выберите пункт "Свойства". В разделе "Дополнительно" для параметра "Копировать в выходной каталог" установите значение "Копировать более позднюю версию".

## <a name="create-data-models"></a>Создание моделей данных

Вам потребуется создать несколько классов для входных данных и прогнозов. Добавьте в проект новый класс:

1. Создайте каталог с именем *DataModels* в папке проекта, чтобы сохранить в нем модели данных:

    В обозревателе решений щелкните проект правой кнопкой мыши и выберите "Добавить" > "Новая папка". Введите DataModels и нажмите клавишу **ВВОД**.

2. В обозревателе решений щелкните правой кнопкой мыши папку *DataModels* и выберите "Добавить" > "Новый элемент".
3. В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentData.cs*. Теперь нажмите кнопку **Добавить**. Файл *SentimentData.cs* откроется в редакторе кода. Добавьте в начало файла *SentimentData.cs* следующий оператор using:

    ```csharp
    using Microsoft.ML.Data;
    ```
    
    Удалите из файла **SentimentData.cs** существующее определение класса и добавьте следующий код:
    
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

4. В обозревателе решений щелкните правой кнопкой мыши папку *DataModels* и выберите **Добавить > Новый элемент**.
5. В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentPrediction.cs*. Теперь нажмите кнопку "Добавить". В редакторе кода откроется файл *SentimentPrediction.cs*. Добавьте в начало файла *SentimentPrediction.cs* следующий оператор using:

    ```csharp
    using Microsoft.ML.Data;
    ```
    
    Удалите из файла *SentimentPrediction.cs* существующее определение класса и добавьте следующий код:
    
    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    Тип`SentimentPrediction` наследуется от типа `SentimentData`. Это упрощает просмотр исходных данных в свойстве `SentimentText`, а также выходных данных модели. 

## <a name="register-predictionenginepool-for-use-in-the-application"></a>Регистрация класса PredictionEnginePool для использования в приложении

Чтобы сделать один прогноз, можно использовать [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602). Чтобы использовать [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) в приложении, следует создать его при необходимости. В этом случае рекомендуется внедрить зависимости.

См. дополнительные сведения о [внедрении зависимостей в ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).

1. Откройте класс *Startup.cs* и добавьте в начало файла следующий оператор using:

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. Добавьте в метод *ConfigureServices* следующий код:

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);
        services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
            .FromFile("MLModels/sentiment_model.zip");
    }
    ```

Вкратце, этот код инициализирует объекты и службы автоматически по запросу приложения, вместо того, чтобы вы делали это вручную.

> [!WARNING]
> [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) не является потокобезопасным. Для повышения производительности и безопасности потока используйте службу `PredictionEnginePool`, которая создает [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) из объектов `PredictionEngine` для использования приложений. Прочтите следующую запись блога, чтобы узнать о [создании и использовании пулов объектов `PredictionEngine` в ASP.NET Core](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).  

## <a name="create-predict-controller"></a>Создание контроллера прогнозирования

Для обработки входящих HTTP-запросов создайте контроллер.

1. В обозревателе решений щелкните правой кнопкой мыши папку *Контроллеры* и выберите **Добавить > Контроллер**.
1. В диалоговом окне **Добавление нового элемента** щелкните **Пустой контроллер API** и нажмите **Добавить**.
1. В запросе измените поле **Имя контроллера** на *PredictController.cs*. Теперь нажмите кнопку "Добавить". Файл *PredictController.cs* откроется в редакторе кода. Добавьте в начало файла *PredictController.cs* следующий оператор using.

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    Удалите из файла *PredictController.cs* существующее определение класса и добавьте следующий код:
    
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

Этот код назначает класс `PredictionEnginePool`, передав его в конструктор контроллера, который можно получить путем внедрения зависимостей. После этого метод `Post` контроллера `Predict` использует `PredictionEnginePool` для создания прогнозов. Он возвращает результаты пользователю при успешном выполнении запроса.

## <a name="test-web-api-locally"></a>Тестирование веб-API на локальном компьютере

Завершив настройку параметров, протестируйте приложение:

1. Запустите приложение.
1. Откройте PowerShell и введите следующий код, где PORT — это порт, через который приложение ожидает передачи денных.

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    В случае успешного выполнения результат должен выглядеть, как показано ниже:
    
    ```powershell
    Negative
    ```

Поздравляем! Вы успешно использовали модель для прогнозирования через Интернет с помощью веб-API ASP.NET Core.

## <a name="next-steps"></a>Следующие шаги

- [Развертывание в Azure](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)
