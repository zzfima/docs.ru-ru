---
title: Бессерверные приложения Application Insights
description: Application Insights — это бессерверная платформа диагностики, которая позволяет разработчикам обнаруживать, рассматривать и диагностировать проблемы в веб-приложениях, мобильных приложениях, классических приложениях и микрослужбах.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7c1013ac029645a2da44aaf1c3b6ba74ca3f3dde
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522745"
---
# <a name="telemetry-with-application-insights"></a><span data-ttu-id="b0ed5-103">Телеметрия в Application Insights</span><span class="sxs-lookup"><span data-stu-id="b0ed5-103">Telemetry with Application Insights</span></span>

<span data-ttu-id="b0ed5-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) — это бессерверная платформа диагностики, которая позволяет разработчикам обнаруживать, рассматривать и диагностировать проблемы в веб-приложениях, мобильных приложениях, классических приложениях и микрослужбах.</span><span class="sxs-lookup"><span data-stu-id="b0ed5-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) is a serverless diagnostics platform that enables developers to detect, triage, and diagnose issues in web apps, mobile apps, desktop apps, and microservices.</span></span> <span data-ttu-id="b0ed5-105">Вы можете включить Application Insights для приложений-функций, изменив положение переключателя на портале.</span><span class="sxs-lookup"><span data-stu-id="b0ed5-105">You can turn on Application Insights for function apps simply by flipping a switch in the portal.</span></span> <span data-ttu-id="b0ed5-106">Application Insights предоставляет все эти возможности без необходимости настройки сервера или собственной базы данных.</span><span class="sxs-lookup"><span data-stu-id="b0ed5-106">Application Insights provides all of these capabilities without you having to configure a server or set up your own database.</span></span> <span data-ttu-id="b0ed5-107">Все возможности Application Insights предоставляются как служба, которая автоматически интегрируется с вашими приложениями.</span><span class="sxs-lookup"><span data-stu-id="b0ed5-107">All of Application Insights' capabilities are provided as a service that automatically integrates with your apps.</span></span>

![Логотип Application Insights](./media/application-insights-logo.png)

<span data-ttu-id="b0ed5-109">Добавить службу Application Insights к существующим приложениям так же просто, как добавить ключ инструментирования в параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="b0ed5-109">Adding Application Insights to existing apps is as easy as adding an instrumentation key to your application's settings.</span></span> <span data-ttu-id="b0ed5-110">С Application Insights вы можете выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="b0ed5-110">With Application Insights you can:</span></span>

- <span data-ttu-id="b0ed5-111">Создание пользовательских диаграмм и оповещений на основе метрик, таких как число вызовов функций, время, затрачиваемое на выполнение функции, и исключения.</span><span class="sxs-lookup"><span data-stu-id="b0ed5-111">Create custom charts and alerts based on metrics such as number of function invocations, the time it takes to run a function, and exceptions</span></span>
- <span data-ttu-id="b0ed5-112">Анализ ошибок и исключений сервера.</span><span class="sxs-lookup"><span data-stu-id="b0ed5-112">Analyze failures and server exceptions</span></span>
- <span data-ttu-id="b0ed5-113">Детализация сведений о производительности по операциям и измерение времени, затрачиваемого на вызов сторонних зависимостей.</span><span class="sxs-lookup"><span data-stu-id="b0ed5-113">Drill into performance by operation and measure the time it takes to call third-party dependencies</span></span>
- <span data-ttu-id="b0ed5-114">Мониторинг использования ЦП, памяти и скорости обработки на всех серверах, на которых размещены приложения-функции.</span><span class="sxs-lookup"><span data-stu-id="b0ed5-114">Monitor CPU usage, memory, and rates across all servers that host your function apps</span></span>
- <span data-ttu-id="b0ed5-115">Просмотр прямой трансляции метрик, включая количество запросов и задержку для приложений-функций.</span><span class="sxs-lookup"><span data-stu-id="b0ed5-115">View a live stream of metrics including request count and latency for your function apps</span></span>
- <span data-ttu-id="b0ed5-116">Использование службы [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) для поиска, запроса и создания пользовательских диаграмм по данным функции.</span><span class="sxs-lookup"><span data-stu-id="b0ed5-116">Use [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) to search, query, and create custom charts over your function data</span></span>

![Обозреватель метрик](./media/metrics-explorer.png)

<span data-ttu-id="b0ed5-118">Помимо встроенной телеметрии, можно также создать пользовательскую телеметрию.</span><span class="sxs-lookup"><span data-stu-id="b0ed5-118">In addition to built-in telemetry, it's also possible to generate custom telemetry.</span></span> <span data-ttu-id="b0ed5-119">Следующий фрагмент кода создает клиент пользовательской телеметрии, используя ключ инструментирования, заданный для приложения-функции:</span><span class="sxs-lookup"><span data-stu-id="b0ed5-119">The following code snippet creates a custom telemetry client using the instrumentation key set for the function app:</span></span>

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

<span data-ttu-id="b0ed5-120">Следующий код измеряет, сколько времени требуется для вставки новой строки в экземпляр [Хранилища таблиц Azure](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview):</span><span class="sxs-lookup"><span data-stu-id="b0ed5-120">The following code measures how long it takes to insert a new row into an [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) instance:</span></span>

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

<span data-ttu-id="b0ed5-121">Ниже показан итоговый график производительности.</span><span class="sxs-lookup"><span data-stu-id="b0ed5-121">The resulting performance graph is shown:</span></span>

![Пользовательская телеметрия](./media/custom-telemetry.png)

<span data-ttu-id="b0ed5-123">Пользовательская телеметрия показывает, что среднее время вставки новой строки — 32,6 мс.</span><span class="sxs-lookup"><span data-stu-id="b0ed5-123">The custom telemetry reveals the average time to insert a new row is 32.6 milliseconds.</span></span>

<span data-ttu-id="b0ed5-124">Application Insights предоставляет эффективный и удобный способ ведения журнала подробных данных телеметрии бессерверных приложений.</span><span class="sxs-lookup"><span data-stu-id="b0ed5-124">Application Insights provides a powerful, convenient way to log detailed telemetry about your serverless applications.</span></span> <span data-ttu-id="b0ed5-125">Вы имеете полный контроль над уровнем трассировки и ведением журнала, который предоставляется.</span><span class="sxs-lookup"><span data-stu-id="b0ed5-125">You have full control over the level of tracing and logging that is provided.</span></span> <span data-ttu-id="b0ed5-126">Вы также можете отслеживать пользовательскую статистику, например, событий, зависимостей и просмотра страниц.</span><span class="sxs-lookup"><span data-stu-id="b0ed5-126">You can track custom statistics such as events, dependencies, and page view.</span></span> <span data-ttu-id="b0ed5-127">Наконец, эффективная аналитика позволяет создавать запросы, которые ставят важные вопросы, создавать диаграммы и генерировать расширенные аналитические сведения.</span><span class="sxs-lookup"><span data-stu-id="b0ed5-127">Finally, the powerful analytics enable you to write queries that ask important questions and generate charts and advanced insights.</span></span>

<span data-ttu-id="b0ed5-128">Дополнительные сведения см. в разделе [Мониторинг функций Azure](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span><span class="sxs-lookup"><span data-stu-id="b0ed5-128">For more information, see [Monitor Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b0ed5-129">[Назад](azure-functions.md)
>[Вперед](logic-apps.md)</span><span class="sxs-lookup"><span data-stu-id="b0ed5-129">[Previous](azure-functions.md)
[Next](logic-apps.md)</span></span>
