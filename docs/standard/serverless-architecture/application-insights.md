---
title: Application Insights — Бессерверных приложений
description: Application Insights — это платформа диагностики без сервера, которая позволяет разработчикам обнаруживать, рассматривать и диагностировать проблемы в веб-приложений, мобильных приложений, классических приложений и микрослужб.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: b4884d483de07c1c2077f7280b6b77c6059572c0
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154266"
---
# <a name="telemetry-with-application-insights"></a><span data-ttu-id="6e613-103">Данные телеметрии с Application Insights</span><span class="sxs-lookup"><span data-stu-id="6e613-103">Telemetry with Application Insights</span></span>

<span data-ttu-id="6e613-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) — это платформа диагностики без сервера, которая позволяет разработчикам обнаруживать, рассматривать и диагностировать проблемы в веб-приложений, мобильных приложений, классических приложений и микрослужб.</span><span class="sxs-lookup"><span data-stu-id="6e613-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) is a serverless diagnostics platform that enables developers to detect, triage, and diagnose issues in web apps, mobile apps, desktop apps, and microservices.</span></span> <span data-ttu-id="6e613-105">Можно включить Application Insights для приложений-функций, выключатели на портале.</span><span class="sxs-lookup"><span data-stu-id="6e613-105">You can turn on Application Insights for function apps simply by flipping a switch in the portal.</span></span> <span data-ttu-id="6e613-106">Application Insights предоставляет все эти возможности без необходимости настройки сервера или настроить собственную базу данных.</span><span class="sxs-lookup"><span data-stu-id="6e613-106">Application Insights provides all of these capabilities without you having to configure a server or set up your own database.</span></span> <span data-ttu-id="6e613-107">Все возможности Application Insights предоставляются как служба, которая автоматически интегрируется с приложениями.</span><span class="sxs-lookup"><span data-stu-id="6e613-107">All of Application Insights' capabilities are provided as a service that automatically integrates with your apps.</span></span>

![Эмблема Application Insights](./media/application-insights-logo.png)

<span data-ttu-id="6e613-109">Добавление Application Insights в существующие приложения так же просто, как добавить ключ инструментирования параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="6e613-109">Adding Application Insights to existing apps is as easy as adding an instrumentation key to your application's settings.</span></span> <span data-ttu-id="6e613-110">С помощью Application Insights можно:</span><span class="sxs-lookup"><span data-stu-id="6e613-110">With Application Insights you can:</span></span>

* <span data-ttu-id="6e613-111">Создание пользовательских диаграмм и оповещения на основе метрик, таких как количество вызовов функции, время, необходимое для выполнения функции и исключения</span><span class="sxs-lookup"><span data-stu-id="6e613-111">Create custom charts and alerts based on metrics such as number of function invocations, the time it takes to run a function, and exceptions</span></span>
* <span data-ttu-id="6e613-112">Анализ ошибок и исключений сервера</span><span class="sxs-lookup"><span data-stu-id="6e613-112">Analyze failures and server exceptions</span></span>
* <span data-ttu-id="6e613-113">Узнать сведения о производительности операции и измерить время, необходимое для вызова сторонних зависимостей</span><span class="sxs-lookup"><span data-stu-id="6e613-113">Drill into performance by operation and measure the time it takes to call third-party dependencies</span></span>
* <span data-ttu-id="6e613-114">Мониторинг использования ЦП, памяти и тарифы на всех серверах, на которых размещены приложения-функции</span><span class="sxs-lookup"><span data-stu-id="6e613-114">Monitor CPU usage, memory, and rates across all servers that host your function apps</span></span>
* <span data-ttu-id="6e613-115">Просмотреть динамический поток метрик, включая число запросов и задержки для приложения-функции</span><span class="sxs-lookup"><span data-stu-id="6e613-115">View a live stream of metrics including request count and latency for your function apps</span></span>
* <span data-ttu-id="6e613-116">Используйте [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) для поиска, запросов и создавать настраиваемые диаграммы по данным функции</span><span class="sxs-lookup"><span data-stu-id="6e613-116">Use [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) to search, query, and create custom charts over your function data</span></span>

![Обозреватель метрик](./media/metrics-explorer.png)

<span data-ttu-id="6e613-118">Помимо встроенных данных телеметрии это также можно создать пользовательские данные телеметрии.</span><span class="sxs-lookup"><span data-stu-id="6e613-118">In addition to built-in telemetry, it's also possible to generate custom telemetry.</span></span> <span data-ttu-id="6e613-119">В следующем фрагменте кода создается клиент пользовательские данные телеметрии с помощью ключа инструментирования для приложения-функции:</span><span class="sxs-lookup"><span data-stu-id="6e613-119">The following code snippet creates a custom telemetry client using the instrumentation key set for the function app:</span></span>

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

<span data-ttu-id="6e613-120">Следующий код измеряет время, необходимое для вставки новой строки в [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) экземпляр:</span><span class="sxs-lookup"><span data-stu-id="6e613-120">The following code measures how long it takes to insert a new row into an [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) instance:</span></span>

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

<span data-ttu-id="6e613-121">Показан полученный граф производительности:</span><span class="sxs-lookup"><span data-stu-id="6e613-121">The resulting performance graph is shown:</span></span>

![Пользовательские данные телеметрии](./media/custom-telemetry.png)

<span data-ttu-id="6e613-123">Пользовательские данные телеметрии показал, что среднее время, чтобы вставить новую строку — 32.6 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="6e613-123">The custom telemetry reveals the average time to insert a new row is 32.6 milliseconds.</span></span>

<span data-ttu-id="6e613-124">Application Insights предоставляет мощный и удобный способ входа подробные данные телеметрии о бессерверных приложений.</span><span class="sxs-lookup"><span data-stu-id="6e613-124">Application Insights provides a powerful, convenient way to log detailed telemetry about your serverless applications.</span></span> <span data-ttu-id="6e613-125">У вас есть полный контроль над уровень трассировки и ведения журнала, который предоставляется.</span><span class="sxs-lookup"><span data-stu-id="6e613-125">You have full control over the level of tracing and logging that is provided.</span></span> <span data-ttu-id="6e613-126">Вы можете отслеживать пользовательские статистику, например события, зависимости и просмотра страницы.</span><span class="sxs-lookup"><span data-stu-id="6e613-126">You can track custom statistics such as events, dependencies, and page view.</span></span> <span data-ttu-id="6e613-127">Наконец мощные средства аналитики позволяют писать запросы, которые важные вопросы и создавать диаграммы и расширенной аналитики.</span><span class="sxs-lookup"><span data-stu-id="6e613-127">Finally, the powerful analytics enable you to write queries that ask important questions and generate charts and advanced insights.</span></span>

<span data-ttu-id="6e613-128">Дополнительные сведения см. в разделе [мониторинг функций Azure](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span><span class="sxs-lookup"><span data-stu-id="6e613-128">For more information, see [Monitor Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6e613-129">[Назад](azure-functions.md)
>[Вперед](logic-apps.md)</span><span class="sxs-lookup"><span data-stu-id="6e613-129">[Previous](azure-functions.md)
[Next](logic-apps.md)</span></span>