---
title: Application Insights — Бессерверных приложений
description: Application Insights — это платформа диагностики без сервера, которая позволяет разработчикам обнаруживать, рассматривать и диагностировать проблемы в веб-приложений, мобильных приложений, классических приложений и микрослужб.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 1f5b99fba448c2c1c12139524ffdcd3708b3c956
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65643361"
---
# <a name="telemetry-with-application-insights"></a>Данные телеметрии с Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights) — это платформа диагностики без сервера, которая позволяет разработчикам обнаруживать, рассматривать и диагностировать проблемы в веб-приложений, мобильных приложений, классических приложений и микрослужб. Можно включить Application Insights для приложений-функций, выключатели на портале. Application Insights предоставляет все эти возможности без необходимости настройки сервера или настроить собственную базу данных. Все возможности Application Insights предоставляются как служба, которая автоматически интегрируется с приложениями.

![Эмблема Application Insights](./media/application-insights-logo.png)

Добавление Application Insights в существующие приложения так же просто, как добавить ключ инструментирования параметры приложения. С помощью Application Insights можно:

* Создание пользовательских диаграмм и оповещения на основе метрик, таких как количество вызовов функции, время, необходимое для выполнения функции и исключения
* Анализ ошибок и исключений сервера
* Узнать сведения о производительности операции и измерить время, необходимое для вызова сторонних зависимостей
* Мониторинг использования ЦП, памяти и тарифы на всех серверах, на которых размещены приложения-функции
* Просмотреть динамический поток метрик, включая число запросов и задержки для приложения-функции
* Используйте [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) для поиска, запросов и создавать настраиваемые диаграммы по данным функции

![Обозреватель метрик](./media/metrics-explorer.png)

Помимо встроенных данных телеметрии это также можно создать пользовательские данные телеметрии. В следующем фрагменте кода создается клиент пользовательские данные телеметрии с помощью ключа инструментирования для приложения-функции:

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

Следующий код измеряет время, необходимое для вставки новой строки в [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) экземпляр:

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

Показан полученный граф производительности:

![Пользовательские данные телеметрии](./media/custom-telemetry.png)

Пользовательские данные телеметрии показал, что среднее время, чтобы вставить новую строку — 32.6 миллисекунд.

Application Insights предоставляет мощный и удобный способ входа подробные данные телеметрии о бессерверных приложений. У вас есть полный контроль над уровень трассировки и ведения журнала, который предоставляется. Вы можете отслеживать пользовательские статистику, например события, зависимости и просмотра страницы. Наконец мощные средства аналитики позволяют писать запросы, которые важные вопросы и создавать диаграммы и расширенной аналитики.

Дополнительные сведения см. в разделе [мониторинг функций Azure](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).

>[!div class="step-by-step"]
>[Назад](azure-functions.md)
>[Вперед](logic-apps.md)
