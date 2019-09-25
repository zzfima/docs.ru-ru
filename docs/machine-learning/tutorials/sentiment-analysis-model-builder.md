---
title: Учебник. Анализ тональности (двоичная классификация)
description: В этом руководстве показано, как создать консольное приложение Razor Pages, которое определяет тональность комментариев на веб-сайте, и предпринимает соответствующие действия. Двоичный классификатор тональности использует построитель моделей в Visual Studio.
ms.date: 09/13/2019
author: luisquintanilla
ms.author: luquinta
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c6184e097daf4604173db9e2a34606e68eb0fdc8
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054276"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-in-a-web-application-using-mlnet-model-builder"></a>Учебник. Анализ тональности комментариев на веб-сайте в веб-приложении с помощью построителя моделей ML.NET

Узнайте, как анализировать тональность комментариев в реальном времени в веб-приложении.

В этом руководстве показано, как создать приложение ASP.NET Razor Pages, которое определяет тональность комментариев на веб-сайте в реальном времени.

В этом руководстве вы узнаете, как:

> [!div class="checklist"]
> * Создание приложения Razor Pages ASP.NET Core
> * Подготовка и анализ данных
> * Выбор сценария
> * Загрузка данных
> * Обучение модели
> * Оценка модели
> * Использование модели для прогнозирования

> [!NOTE]
> Построитель моделей в настоящее время находится на этапе предварительной версии.

Исходный код для этого руководства можно найти в репозитории [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples).

## <a name="pre-requisites"></a>Предварительные требования

Список необходимых условий и инструкции по установке см. в [руководстве по установке построителя моделей](../how-to-guides/install-model-builder.md).

## <a name="create-a-razor-pages-application"></a>Создание приложения Razor Pages

1. Создайте **приложение ASP.NET Core Razor Pages**.

    1. Откройте Visual Studio и выберите **Файл > Создать > Проект** в строке меню. 
    1. В диалоговом окне "Новый проект" щелкните узел **Visual C#** , а затем — **Веб**. 
    1. Затем, выберите шаблон проекта **Веб-приложение ASP.NET Core**. 
    1. В текстовом поле **Имя** введите SentimentRazor.
    1. Флажок **Создать каталог для решения** должен быть установлен по умолчанию. Если это не так, установите его. 
    1. Нажмите кнопку **OK**.
    1. Выберите **Web Application** (Веб-приложение) в окне с разными типами проектов ASP.NET Core и нажмите кнопку **ОК**.

## <a name="prepare-and-understand-the-data"></a>Подготовка и анализ данных

Скачайте [набор данных Wikipedia Detox](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv). Щелкните открывшуюся веб-страницу правой кнопкой мыши, выберите **Сохранить как** и сохраните файл на компьютере. 

Каждая строка в наборе данных *wikipedia-detox-250-line-data.tsv* содержит сообщение, оставленное пользователем Википедии. Первый столбец представляет тональность текста (0 — нетоксичный, 1 — токсичный), а второй столбец включает сам комментарий, оставленный пользователем. Столбцы разделены пробелами. Данные выглядят так:

| Тональность | SentimentText |
| :---: | :---: |
1 | ==RUDE== Мужик давай не начинай, просто загрузи обратно эту картинку.
1 | ==OK! ==Я ЩАС WILD ONES WIKI ПОЛОЖУ!!!
0 | Надеюсь, это поможет.

## <a name="choose-a-scenario"></a>Выбор сценария

![](./media/sentiment-analysis-model-builder/model-builder-screen.png)

Чтобы обучить модель, нужно выбрать один из доступных сценариев машинного обучения в построителе моделей. 

1. В **обозревателе решений** щелкните правой кнопкой мыши проект *SentimentRazor* и выберите **Добавить** > **Машинное обучение**.
1. В этом примере сценарий включает анализ тональности. На шаге *Сценарий* средства построителя моделей выберите сценарий **Анализ тональности**.

## <a name="load-the-data"></a>Загрузка данных

Построитель моделей принимает данные из двух источников: базы данных SQL Server или локального файла в формате `csv` или `tsv`.

1. На этапе добавления данных выберите в раскрывающемся списке источников данных пункт **Прогнозирование цен**.
1. Нажмите кнопку рядом с текстовым полем **Выберите файл** и щелкните в проводнике файл *wikipedia-detox-250-line-data.tsv*.
1. Выберите **Тональность** в раскрывающемся списке **Метка или столбец для прогнозирования**.
1. Щелкните ссылку **Обучение**, чтобы перейти к следующему шагу в средстве построителя моделей.

## <a name="train-the-model"></a>Обучение модели

Задачей машинного обучения, используемой в этом руководстве для обучения модели прогнозирования цен, является бинарная классификация. В процессе обучения построитель моделей обучает отдельные модели с помощью различных алгоритмов и параметров бинарной классификации, определяя оптимальную модель для вашего набора данных.

Время, требуемое для обучения модели, пропорционально объему данных. Построитель моделей автоматически выбирает значение по умолчанию для параметра **Time to train (seconds)** (Время обучения в секундах) в зависимости от размера источника данных. 

1. Хотя построитель моделей задает для параметра **Время обучения (в секундах)** значение 10 секунд, увеличьте его до 30 секунд. Обучение в течение более длительного периода времени позволяет построителю моделей исследовать большее количество алгоритмов и комбинаций параметров, чтобы определить наилучшую модель.
1. Выберите **Начать обучение**.

    В процессе обучения сведения о ходе выполнения отображаются в разделе `Progress` шага обучения.

    - "Состояние" — это состояние завершения процесса обучения.
    - "Наибольшая точность" — это точность модели, которая на данный момент определена построителем моделей как лучшая. Точность зависит от того, насколько правильный прогноз был сделан моделью на основе тестовых данных.
    - "Лучший алгоритм" — это название алгоритма, который на данный момент определен построителем моделей как лучший.
    - "Последний алгоритм" — это название алгоритма, который использовался построителем моделей для обучения модели последним.

1. По завершении обучения щелкните ссылку **Оценить**, чтобы перейти к следующему шагу.

## <a name="evaluate-the-model"></a>Оценка модели

Результат обучения — одна модель с наивысшей точностью. В шаге оценки в разделе результатов будет указан алгоритм, используемый оптимальной моделью, в поле **Лучшая модель**, а также метрики в поле **Качество лучшей модели (достоверность аппроксимации)** . Кроме того, приводится сводная таблица с пятью лучшими моделями и их метриками.

Если вас не удовлетворяют метрики точности, самые простые способы повысить точность модели — увеличить длительность обучения или использовать больше данных. В противном случае щелкните ссылку **Код**, чтобы перейти к завершающему шагу в средстве построителя моделей.

## <a name="add-the-code-to-make-predictions"></a>Добавление кода для прогнозирования

В результате процесса обучения создаются два проекта.

### <a name="reference-the-trained-model"></a>Создание ссылки на обученную модель

1. На шаге **Код** в построителе моделей выберите *Добавить проекты*, чтобы добавить автоматически созданные проекты в решение.

    Теперь в **обозревателе решений** должны появиться следующие проекты:

    - *SentimentRazorML.ConsoleApp*: консольное приложение .NET Core с кодом прогнозирования и обучения модели.
    - *SentimentRazorML.Model*: библиотека классов .NET Standard с моделями данных, которые определяют схему входных и выходных данных модели, а также хранимую версию оптимальной модели.

    В этом руководстве используется только проект *SentimentRazorML.Model*, так как прогнозы будут выполняться в веб-приложении *SentimentRazor*, а не в консоли. Хотя проект *SentimentRazorML.ConsoleApp* не будет использоваться для оценки, его можно применить для переобучения модели в будущем с помощью новых данных. Вопросы, связанные с переобучением, выходят за рамки этого руководства.

1. Чтобы использовать обученную модель в приложении Razor Pages, добавьте ссылку на проект *SentimentRazorML.Model*.

    1. Щелкните проект **SentimentRazor** правой кнопкой мыши. 
    1. Выберите **Добавить > Ссылка**. 
    1. Выберите узел **Проекты > Решение**, и установите в списке флажок рядом с проектом **SentimentRazorML.Model**.
    1. Нажмите кнопку **ОК**.

### <a name="configure-the-predictionengine-pool"></a>Настройка пула PredictionEngine

Чтобы сделать один прогноз, можно использовать [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602). При необходимости создайте [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) для дальнейшего использования в приложении. В этом случае рекомендуется внедрить зависимости.

> [!WARNING]
> [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) не является потокобезопасным. Для повышения производительности и безопасности потока используйте службу `PredictionEnginePool`, которая создает [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) из объектов `PredictionEngine` для использования приложений. Прочтите следующую запись блога, чтобы узнать о [создании и использовании пулов объектов `PredictionEngine` в ASP.NET Core](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/). 

1. Установите пакет NuGet *Microsoft.Extensions.ML*:

    1. В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**. 
    1. Выберите nuget.org в качестве источника пакета. 
    1. Откройте вкладку **Обзор** и найдите **Microsoft.Extensions.ML**. 
    1. Выберите пакет в списке и нажмите кнопку **Установить**. 
    1. Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**.
    1. Нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с условиями лицензионного соглашения для указанных пакетов. 

1. Откройте файл *Startup.cs* в проекте *SentimentRazor*.
1. Добавьте следующие операторы using, ссылающиеся на пакет NuGet *Microsoft.Extensions.ML* и проект *SentimentRazorML.Model*:

    [!code-csharp [StartupUsings](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L12-L14)]        

1. Создайте глобальную переменную для хранения расположения файла обученной модели.

    [!code-csharp [ModelPath](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L20)]

1. Файл модели хранится в каталоге сборки вместе с файлами сборки приложения. Чтобы упростить доступ к нему, создайте вспомогательный метод `GetAbsolutePath`, вызываемый после метода `Configure`.

    [!code-csharp [GetAbsolutePathMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L66-L73)]

1. Используйте метод `GetAbsolutePath` в конструкторе класса `Startup`, чтобы задать `_modelPath`.

    [!code-csharp [InitModelPath](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L25)]

1. Настройте `PredictionEnginePool` для приложения в методе `ConfigureServices`:

    [!code-csharp [InitPredEnginePool](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L42)]

### <a name="create-sentiment-analysis-handler"></a>Создание обработчика анализа тональности

Прогнозы будут отображаться на главной странице приложения. Поэтому вам нужно добавить метод, который принимает входные данные пользователя и использует `PredictionEnginePool` для получения прогноза.

1. Откройте файл *Index.cshtml.cs*, расположенный в каталоге *Pages*, и добавьте следующие операторы using:

    [!code-csharp [IndexUsings](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L7-L8)]

    Чтобы использовать службу `PredictionEnginePool`, настроенную в классе `Startup`, необходимо внедрить ее в конструктор модели для дальнейшего использования. 

1. Добавьте переменную для создания ссылки на `PredictionEnginePool` в классе `IndexModel`.

    [!code-csharp [PredEnginePool](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L14)]

1. Создайте конструктор в классе `IndexModel` и вставьте в него службу `PredictionEnginePool`.

    [!code-csharp [IndexConstructor](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L16-L19)]

1. Создайте обработчик метода, который использует `PredictionEnginePool` для создания прогнозов на основе вводимых пользователем данных, полученных с веб-страницы.

    1. Добавьте новый метод `OnGetAnalyzeSentiment` под методом `OnGet`.

        ```csharp
        public IActionResult OnGetAnalyzeSentiment([FromQuery] string text)
        {

        }
        ```

    1. Внутри метода `OnGetAnalyzeSentiment` передайте тональность *Neutral* (Нейтрально), если входные данные пользователя пусты или имеют значение NULL.

        [!code-csharp [InitInput](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L28)] 
    
    1. При наличии допустимых входных данных создайте новый экземпляр `ModelInput`. 

        [!code-csharp [InitInput](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L29)] 

    1. Используйте `PredictionEnginePool` для прогнозирования тональности.

        [!code-csharp [MakePrediction](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L30)] 

    1. Преобразуйте прогнозируемое значение `bool` в токсичное или нетоксичное с помощью следующего кода.

        [!code-csharp [ConvertPrediction](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L31)]

    1. Наконец, передайте тональности обратно на веб-страницу.

        [!code-csharp [ReturnSentiment](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L32)]

### <a name="configure-the-web-page"></a>Настройка веб-страницы

Результаты, возвращаемые `OnGetAnalyzeSentiment`, будут динамически отображаться на веб-странице `Index`.

1. Откройте файл *Index.cshtml* в каталоге *Pages* и замените его содержимое следующим кодом: 

    [!code-cshtml [IndexPage](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml)]

1. Затем добавьте код CSS в конец страницы *site.css* в каталоге *wwwroot\css*:

    [!code-css [CssStyling](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/css/site.css#L61-L105)]

1. После этого добавьте код для отправки входных данных с веб-страницы в обработчик `OnGetAnalyzeSentiment`.

    1. В файле *site.js*, расположенном в каталоге *wwwroot\js*, создайте функцию `getSentiment` для создания HTTP-запроса GET с входными данными пользователя к обработчику `OnGetAnalyzeSentiment`.

        [!code-javascript [GetSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L5-L10)]

    1. Ниже добавьте еще одну функцию `updateMarker` для динамического обновления расположения маркера на веб-странице по мере прогнозирования тональности.

        [!code-javascript [UpdateMarkerMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L12-L15)]

    1. Создайте функцию обработчика событий `updateSentiment` для получения входных данных от пользователя, отправьте ее в функцию `OnGetAnalyzeSentiment` с помощью функции `getSentiment` и обновите маркер с помощью функции `updateMarker`.

        [!code-javascript [UpdateSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L17-L34)]

    1. Наконец, зарегистрируйте обработчик событий и привяжите его к элементу `textarea` с помощью атрибута `id=Message`.

        [!code-javascript [UpdateSentimentEvtHandler](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L36)]

## <a name="run-the-application"></a>Запуск приложения

Теперь запустите приложение, которое должно открыться в браузере.

Когда приложение запустится, введите *Model Builder is cool!* (Построитель моделей — это круто!) в текстовом поле. Отобразится прогнозируемая тональность — *Not Toxic* (Нетоксично).

![](./media/sentiment-analysis-model-builder/web-app.png)

В будущем вам может потребоваться создать ссылку на проекты, созданные с помощью построителя моделей, для использования в другом решении. В таком случае их можно найти в каталоге `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы узнали, как:
> [!div class="checklist"]
> * Создание приложения Razor Pages ASP.NET Core
> * Подготовка и анализ данных
> * Выбор сценария
> * Загрузка данных
> * Обучение модели
> * Оценка модели
> * Использование модели для прогнозирования

### <a name="additional-resources"></a>Дополнительные ресурсы

Дополнительные сведения см. в следующих статьях:

- [Сценарии для построителя моделей](../automate-training-with-model-builder.md#scenarios)
- [Двоичная классификация](../resources/glossary.md#binary-classification)
- [Метрики модели двоичной классификации](../resources/metrics.md#metrics-for-binary-classification)