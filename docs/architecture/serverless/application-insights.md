---
title: Бессерверные приложения Application Insights
description: Application Insights — это бессерверная платформа диагностики, которая позволяет разработчикам обнаруживать, рассматривать и диагностировать проблемы в веб-приложениях, мобильных приложениях, классических приложениях и микрослужбах.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7c1013ac029645a2da44aaf1c3b6ba74ca3f3dde
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2019
ms.locfileid: "72522745"
---
# <a name="telemetry-with-application-insights"></a>Телеметрия в Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights) — это бессерверная платформа диагностики, которая позволяет разработчикам обнаруживать, рассматривать и диагностировать проблемы в веб-приложениях, мобильных приложениях, классических приложениях и микрослужбах. Вы можете включить Application Insights для приложений-функций, изменив положение переключателя на портале. Application Insights предоставляет все эти возможности без необходимости настройки сервера или собственной базы данных. Все возможности Application Insights предоставляются как служба, которая автоматически интегрируется с вашими приложениями.

![Логотип Application Insights](./media/application-insights-logo.png)

Добавить службу Application Insights к существующим приложениям так же просто, как добавить ключ инструментирования в параметры приложения. С Application Insights вы можете выполнять следующие задачи:

- Создание пользовательских диаграмм и оповещений на основе метрик, таких как число вызовов функций, время, затрачиваемое на выполнение функции, и исключения.
- Анализ ошибок и исключений сервера.
- Детализация сведений о производительности по операциям и измерение времени, затрачиваемого на вызов сторонних зависимостей.
- Мониторинг использования ЦП, памяти и скорости обработки на всех серверах, на которых размещены приложения-функции.
- Просмотр прямой трансляции метрик, включая количество запросов и задержку для приложений-функций.
- Использование службы [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) для поиска, запроса и создания пользовательских диаграмм по данным функции.

![Обозреватель метрик](./media/metrics-explorer.png)

Помимо встроенной телеметрии, можно также создать пользовательскую телеметрию. Следующий фрагмент кода создает клиент пользовательской телеметрии, используя ключ инструментирования, заданный для приложения-функции:

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

Следующий код измеряет, сколько времени требуется для вставки новой строки в экземпляр [Хранилища таблиц Azure](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview):

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

Ниже показан итоговый график производительности.

![Пользовательская телеметрия](./media/custom-telemetry.png)

Пользовательская телеметрия показывает, что среднее время вставки новой строки — 32,6 мс.

Application Insights предоставляет эффективный и удобный способ ведения журнала подробных данных телеметрии бессерверных приложений. Вы имеете полный контроль над уровнем трассировки и ведением журнала, который предоставляется. Вы также можете отслеживать пользовательскую статистику, например, событий, зависимостей и просмотра страниц. Наконец, эффективная аналитика позволяет создавать запросы, которые ставят важные вопросы, создавать диаграммы и генерировать расширенные аналитические сведения.

Дополнительные сведения см. в разделе [Мониторинг функций Azure](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).

>[!div class="step-by-step"]
>[Назад](azure-functions.md)
>[Вперед](logic-apps.md)
