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
# <a name="telemetry-with-application-insights"></a>Данные телеметрии с Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights) — это бессерверная платформа диагностики, которая позволяет разработчикам обнаруживать, рассматривать и диагностировать проблемы в веб-приложениях, мобильных приложениях, настольных приложениях и микрослужбах. Вы можете включить Application Insights для приложений-функций простым путем отражения коммутатора на портале. Application Insights предоставляет все эти возможности без необходимости настройки сервера или настройки собственной базы данных. Все возможности Application Insights "предоставляются как служба, которая автоматически интегрируется с вашими приложениями.

![Эмблема Application Insights](./media/application-insights-logo.png)

Добавление Application Insights в существующие приложения упрощает добавление ключа инструментирования в параметры приложения. С Application Insights можно:

- Создание пользовательских диаграмм и оповещений на основе метрик, таких как число вызовов функций, время, затрачиваемое на выполнение функции, и исключения
- Анализ ошибок и исключений сервера
- Детализация производительности по операциям и измерение времени, затрачиваемого на вызов сторонних зависимостей
- Мониторинг использования ЦП, памяти и ставок на всех серверах, на которых размещены приложения для работы с функциями
- Просмотр активного потока метрик, включая количество запросов и задержку для приложений-функций
- Использование [аналитики](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) для поиска, запроса и создания пользовательских диаграмм на основе данных функции

![Обозреватель метрик](./media/metrics-explorer.png)

Помимо встроенных данных телеметрии, можно создать пользовательскую телеметрию. Следующий фрагмент кода создает пользовательский клиент телеметрии, используя набор ключей инструментирования для приложения-функции:

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

Следующий код измеряет, сколько времени требуется для вставки новой строки в экземпляр [хранилища таблиц Azure](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) :

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

Итоговый граф производительности показан ниже.

![Пользовательская телеметрии](./media/custom-telemetry.png)

Пользовательская телеметрия показывает среднее время вставки новой строки 32,6 миллисекунд.

Application Insights предоставляет мощный и удобный способ ведения журнала подробных данных телеметрии о бессерверных приложениях. Вы имеете полный контроль над уровнем трассировки и ведения журнала, который предоставляется. Можно отслеживанию пользовательской статистики, например событий, зависимостей и просмотра страниц. Наконец, мощная аналитика позволяет создавать запросы, которые запрашивают важные вопросы и создают диаграммы и расширенные аналитические сведения.

Дополнительные сведения см. в статье [мониторинг функций Azure](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).

>[!div class="step-by-step"]
>[Назад](azure-functions.md)
>[Вперед](logic-apps.md)
