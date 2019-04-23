---
title: Развертывание модели ML.NET в Функциях Azure
description: Использование модели машинного обучения ML.NET для анализа тональности и прогнозирования через Интернет с помощью Функций Azure
ms.date: 03/08/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 4681b37da64097dd8e537b4c956917277ecff96b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59330640"
---
# <a name="how-to-use-mlnet-model-in-azure-functions"></a>Руководство. Использование модели ML.NET в Функциях Azure

В этом руководстве показано, как можно выполнить отдельные прогнозы с помощью предварительно созданных моделей машинного обучения ML.NET через Интернет в бессерверной среде, например, Функциях Azure.

> [!NOTE]
> В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен. Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Сейчас в этих инструкциях и примере используется **ML.NET версии 0.10**. Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

## <a name="prerequisites"></a>Предварительные требования

- [Visual Studio 2017 версии 15.6 и выше](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core" и "Разработка в Azure". 
- [Средства Функций Azure](/azure/azure-functions/functions-develop-vs#check-your-tools-version).
- PowerShell.
- Предварительно обученная модель. 
    - Используйте [руководство по анализу тональности ML.NET](../tutorials/sentiment-analysis.md), чтобы создать собственную модель.
    - Скачайте эту [предварительно обученную модель машинного обучения для анализа тональности](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip).

## <a name="create-azure-functions-project"></a>Создание проекта в Функциях Azure

1. Откройте Visual Studio 2017. Выберите **Файл** > **Создать** > **Проект** в меню. В диалоговом окне **Новый проект** щелкните узел **Visual C#**, а затем — **Облако**. Выберите шаблон проекта **Функции Azure**. В текстовое поле **Имя** введите SentimentAnalysisFunctionsApp и нажмите кнопку **ОК**.
1. В диалоговом окне **Новый проект** откройте раскрывающийся список над разделом с параметрами проекта и выберите **Функции Azure v2 (.NET Core)**. Затем щелкните проект **Триггер HTTP** и нажмите кнопку **OK**.
1. Создайте каталог с именем *MLModels* в папке проекта, чтобы сохранить модель:

    В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**. Введите MLModels и нажмите клавишу ВВОД.

1. Установите **пакет NuGet для Microsoft.ML**:

    В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**. Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**. Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.

## <a name="add-pre-built-model-to-project"></a>Добавление предварительно созданной модели в проект

1. Скопируйте предварительно созданную модель в папку *MLModels*.
1. В обозревателе решений щелкните правой кнопкой мыши файл предварительно созданной модели и выберите **Свойства**. В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.

## <a name="create-function-to-analyze-sentiment"></a>Создание функции для анализа тональности

Создайте класс для прогнозирования тональности. Добавьте в проект новый класс:

1. В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.

1. В диалоговом окне **Добавление нового элемента** выберите **Функция Azure** и измените значение поля **Имя** на *AnalyzeSentiment.cs*. Теперь нажмите кнопку **Добавить**.

1. В диалоговом окне **Новая функция Azure** щелкните **Триггер HTTP**. Затем нажмите кнопку **OK**.

    В редакторе кода откроется файл *AnalyzeSentiment.cs*. Добавьте следующий оператор `using` в начало файла *GitHubIssueData.cs*:

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

### <a name="create-data-models"></a>Создание моделей данных

Вам потребуется создать несколько классов для входных данных и прогнозов. Добавьте в проект новый класс:

1. Создайте каталог с именем *DataModels* в папке проекта, чтобы сохранить в нем модели данных: В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Добавить > Новая папка**. Введите DataModels и нажмите клавишу ВВОД.
2. В обозревателе решений щелкните правой кнопкой мыши папку *DataModels* и выберите **Добавить > Новый элемент**.
3. В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentData.cs*. Теперь нажмите кнопку **Добавить**. Файл *SentimentData.cs* откроется в редакторе кода. Добавьте в начало файла *SentimentData.cs* следующий оператор using:

```csharp
using Microsoft.ML.Data;
```

Удалите из файла SentimentData.cs существующее определение класса и добавьте следующий код:

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
5. В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *SentimentPrediction.cs*. Теперь нажмите кнопку **Добавить**. В редакторе кода откроется файл *SentimentPrediction.cs*. Добавьте в начало файла *SentimentPrediction.cs* следующий оператор using:

```csharp
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

### <a name="add-prediction-logic"></a>Добавление логики прогнозирования

Замените существующую реализацию метода *запуска* в классе *AnalyzeSentiment* следующим кодом:

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

## <a name="test-locally"></a>Локальное тестирование

Завершив настройку параметров, протестируйте приложение:

1. Запуск приложения
1. Откройте PowerShell и введите код в командной строке, где PORT — это порт, через который работает приложение. Как правило, используется порт 7071. 

```powershell
Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

В случае успешного выполнения результат должен выглядеть, как показано ниже:

```powershell
Toxic
```

Поздравляем! Вы успешно использовали модель для прогнозирования через Интернет с помощью Функций Azure.

## <a name="next-steps"></a>Следующие шаги

- [Развертывание в Azure](/azure/azure-functions/functions-develop-vs#publish-to-azure)