---
title: Бессерверные приложения Application Insights
description: Application Insights — это бессерверная платформа диагностики, которая позволяет разработчикам обнаруживать, рассматривать и диагностировать проблемы в веб-приложениях, мобильных приложениях, настольных приложениях и микрослужбах.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7c1013ac029645a2da44aaf1c3b6ba74ca3f3dde
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522745"
---
# <a name="telemetry-with-application-insights"></a><span data-ttu-id="5189e-103">Данные телеметрии с Application Insights</span><span class="sxs-lookup"><span data-stu-id="5189e-103">Telemetry with Application Insights</span></span>

<span data-ttu-id="5189e-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) — это бессерверная платформа диагностики, которая позволяет разработчикам обнаруживать, рассматривать и диагностировать проблемы в веб-приложениях, мобильных приложениях, настольных приложениях и микрослужбах.</span><span class="sxs-lookup"><span data-stu-id="5189e-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) is a serverless diagnostics platform that enables developers to detect, triage, and diagnose issues in web apps, mobile apps, desktop apps, and microservices.</span></span> <span data-ttu-id="5189e-105">Вы можете включить Application Insights для приложений-функций простым путем отражения коммутатора на портале.</span><span class="sxs-lookup"><span data-stu-id="5189e-105">You can turn on Application Insights for function apps simply by flipping a switch in the portal.</span></span> <span data-ttu-id="5189e-106">Application Insights предоставляет все эти возможности без необходимости настройки сервера или настройки собственной базы данных.</span><span class="sxs-lookup"><span data-stu-id="5189e-106">Application Insights provides all of these capabilities without you having to configure a server or set up your own database.</span></span> <span data-ttu-id="5189e-107">Все возможности Application Insights "предоставляются как служба, которая автоматически интегрируется с вашими приложениями.</span><span class="sxs-lookup"><span data-stu-id="5189e-107">All of Application Insights' capabilities are provided as a service that automatically integrates with your apps.</span></span>

![Эмблема Application Insights](./media/application-insights-logo.png)

<span data-ttu-id="5189e-109">Добавление Application Insights в существующие приложения упрощает добавление ключа инструментирования в параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="5189e-109">Adding Application Insights to existing apps is as easy as adding an instrumentation key to your application's settings.</span></span> <span data-ttu-id="5189e-110">С Application Insights можно:</span><span class="sxs-lookup"><span data-stu-id="5189e-110">With Application Insights you can:</span></span>

- <span data-ttu-id="5189e-111">Создание пользовательских диаграмм и оповещений на основе метрик, таких как число вызовов функций, время, затрачиваемое на выполнение функции, и исключения</span><span class="sxs-lookup"><span data-stu-id="5189e-111">Create custom charts and alerts based on metrics such as number of function invocations, the time it takes to run a function, and exceptions</span></span>
- <span data-ttu-id="5189e-112">Анализ ошибок и исключений сервера</span><span class="sxs-lookup"><span data-stu-id="5189e-112">Analyze failures and server exceptions</span></span>
- <span data-ttu-id="5189e-113">Детализация производительности по операциям и измерение времени, затрачиваемого на вызов сторонних зависимостей</span><span class="sxs-lookup"><span data-stu-id="5189e-113">Drill into performance by operation and measure the time it takes to call third-party dependencies</span></span>
- <span data-ttu-id="5189e-114">Мониторинг использования ЦП, памяти и ставок на всех серверах, на которых размещены приложения для работы с функциями</span><span class="sxs-lookup"><span data-stu-id="5189e-114">Monitor CPU usage, memory, and rates across all servers that host your function apps</span></span>
- <span data-ttu-id="5189e-115">Просмотр активного потока метрик, включая количество запросов и задержку для приложений-функций</span><span class="sxs-lookup"><span data-stu-id="5189e-115">View a live stream of metrics including request count and latency for your function apps</span></span>
- <span data-ttu-id="5189e-116">Использование [аналитики](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) для поиска, запроса и создания пользовательских диаграмм на основе данных функции</span><span class="sxs-lookup"><span data-stu-id="5189e-116">Use [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) to search, query, and create custom charts over your function data</span></span>

![Обозреватель метрик](./media/metrics-explorer.png)

<span data-ttu-id="5189e-118">Помимо встроенных данных телеметрии, можно создать пользовательскую телеметрию.</span><span class="sxs-lookup"><span data-stu-id="5189e-118">In addition to built-in telemetry, it's also possible to generate custom telemetry.</span></span> <span data-ttu-id="5189e-119">Следующий фрагмент кода создает пользовательский клиент телеметрии, используя набор ключей инструментирования для приложения-функции:</span><span class="sxs-lookup"><span data-stu-id="5189e-119">The following code snippet creates a custom telemetry client using the instrumentation key set for the function app:</span></span>

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

<span data-ttu-id="5189e-120">Следующий код измеряет, сколько времени требуется для вставки новой строки в экземпляр [хранилища таблиц Azure](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) :</span><span class="sxs-lookup"><span data-stu-id="5189e-120">The following code measures how long it takes to insert a new row into an [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) instance:</span></span>

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

<span data-ttu-id="5189e-121">Итоговый граф производительности показан ниже.</span><span class="sxs-lookup"><span data-stu-id="5189e-121">The resulting performance graph is shown:</span></span>

![Пользовательская телеметрии](./media/custom-telemetry.png)

<span data-ttu-id="5189e-123">Пользовательская телеметрия показывает среднее время вставки новой строки 32,6 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="5189e-123">The custom telemetry reveals the average time to insert a new row is 32.6 milliseconds.</span></span>

<span data-ttu-id="5189e-124">Application Insights предоставляет мощный и удобный способ ведения журнала подробных данных телеметрии о бессерверных приложениях.</span><span class="sxs-lookup"><span data-stu-id="5189e-124">Application Insights provides a powerful, convenient way to log detailed telemetry about your serverless applications.</span></span> <span data-ttu-id="5189e-125">Вы имеете полный контроль над уровнем трассировки и ведения журнала, который предоставляется.</span><span class="sxs-lookup"><span data-stu-id="5189e-125">You have full control over the level of tracing and logging that is provided.</span></span> <span data-ttu-id="5189e-126">Можно отслеживанию пользовательской статистики, например событий, зависимостей и просмотра страниц.</span><span class="sxs-lookup"><span data-stu-id="5189e-126">You can track custom statistics such as events, dependencies, and page view.</span></span> <span data-ttu-id="5189e-127">Наконец, мощная аналитика позволяет создавать запросы, которые запрашивают важные вопросы и создают диаграммы и расширенные аналитические сведения.</span><span class="sxs-lookup"><span data-stu-id="5189e-127">Finally, the powerful analytics enable you to write queries that ask important questions and generate charts and advanced insights.</span></span>

<span data-ttu-id="5189e-128">Дополнительные сведения см. в статье [мониторинг функций Azure](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span><span class="sxs-lookup"><span data-stu-id="5189e-128">For more information, see [Monitor Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5189e-129">[Назад](azure-functions.md)
>[Вперед](logic-apps.md)</span><span class="sxs-lookup"><span data-stu-id="5189e-129">[Previous](azure-functions.md)
[Next](logic-apps.md)</span></span>
