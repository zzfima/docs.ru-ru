---
title: Выбор .NET Framework для контейнеров Docker
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Выбор .NET Framework для контейнеров Docker
ms.date: 01/07/2019
ms.openlocfilehash: 9e5b18e8e3482eb86c0d9dea5de56fb12f9d6256
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966894"
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a>Выбор .NET Framework для контейнеров Docker

Хотя среда .NET Core предоставляет значительные преимущества для новых приложений и шаблонов приложений, мы рекомендуем использовать среду .NET Framework для большинства имеющихся сценариев.

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a>Перенос существующих приложений непосредственно в контейнер Windows Server

Даже если вы не создаете микрослужбы, контейнеры Docker можно использовать для упрощения развертывания. Например, вы хотите улучшить функционирование рабочего процесса DevOps с помощью Docker. Использование контейнеров позволит вам получить хорошо изолированную тестовую среду и устранить проблемы с развертыванием, вызванные отсутствием зависимостей при перемещении в рабочую среду. В таких случаях даже при развертывании монолитных приложений имеет смысл использовать Docker и контейнеры Windows для текущего приложения .NET Framework.

В большинстве случаев при таком сценарии перенос существующих приложений на .NET Core не требуется. Можно использовать контейнеры Docker, в которые включена традиционная платформа .NET Framework. Тем не менее для расширения готовых приложений, например для разработки новой службы в ASP.NET Core рекомендуется использовать .NET Core.

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a>Использование сторонних библиотек .NET и пакетов NuGet, недоступных для .NET Core

Сторонние библиотеки [.NET Standard](../../../standard/net-standard.md) позволяют совместно использовать код в различных средах выполнения .NET, в том числе в .NET Core. Использование библиотеки .NET Standard 2.0 (и более поздних версий) и API позволяет существенно улучшить совместимость различных платформ. В .NET Core 2.x приложения могут напрямую обращаться к существующим библиотекам .NET Framework (см. раздел о [.NET Framework 4.6.1 с поддержкой .NET Standard 2.0](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#net-framework-461-supporting-net-standard-20)).

Кроме того, выпущенный в ноябре 2017 г. [пакет обеспечения совместимости Windows](../../../core/porting/windows-compat-pack.md) расширяет доступную для .NET Standard 2.0 область API-интерфейсов в Windows. Этот пакет позволяет почти без изменений перекомпилировать существующий код под платформу .NET Standard версии 2.x, чтобы выполнять его в Windows.

Несмотря на значительный прогресс, достигнутый после выхода .NET Standard 2.0 и .NET Core 2.1, некоторые пакеты NuGet пока запускаются только в ОС Windows и не поддерживают .NET Core. Если эти пакеты имеют важное значение для вашего приложения, необходимо использовать .NET Framework в контейнерах Windows.

## <a name="using-net-technologies-not-available-for-net-core"></a>Использование технологий .NET, недоступных для .NET Core

Некоторые технологии .NET Framework отсутствуют в текущей версии .NET Core (версии 2.2 на момент написания этой статьи). Поддержка некоторых из них будет добавлена в последующих выпусках .NET Core (.NET Core 2.x), однако остальные технологии не применяются к новым шаблонам приложений, используемым в среде .NET Core, и будут недоступными всегда.

В следующем списке перечислены почти все технологии, недоступные в .NET Core 2.x.

- Веб-формы ASP.NET. Эта технология доступна только в .NET Framework. В настоящее время добавление веб-форм ASP.NET в среду .NET Core не планируется.

- Службы WCF. Даже с [клиентской библиотекой WCF](https://github.com/dotnet/wcf), которая позволяет использовать службы WCF из среды .NET Core, по состоянию на середину 2017 г. реализация сервера WCF доступна только для .NET Framework. Возможно, эта ситуация будет исправлена в следующих выпусках .NET Core. Рассматривается даже возможность включить некоторые API-интерфейсы в [пакет обеспечения совместимости Windows](../../../core/porting/windows-compat-pack.md).

- Службы, связанные с рабочим процессом. Службы Windows Workflow Foundation (WF), Workflow Services (WCF и WF в одной службе) и WCF Data Services (известные как службы данных ADO.NET) доступны только в среде .NET Framework. В настоящий момент не планируется их перенос в .NET Core.

В дополнение к технологиям, перечисленным в официальном [плане по .NET Core](https://github.com/aspnet/Home/wiki/Roadmap), в платформу .NET Core могут быть перенесены и другие функции. Все такие компоненты помечены на сайте CoreFX GitHub отметкой [перенос в ядро](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core). Однако следует иметь в виду, что наличие этих компонентов в списке не означает, что корпорация Майкрософт намеревается добавлять их в среду .NET Core. Компоненты, присутствующие в списке, лишь отражают запросы от пользователей сообщества. Если вас заинтересовал какой-либо из перечисленных выше компонентов, примите участие в обсуждениях на сайте GitHub и выразите свое мнение. Если вы думаете, что чего-то не хватает, [отправьте новый вопрос в репозиторий CoreFX](https://github.com/dotnet/corefx/issues/new).

Несмотря на то, что выпуск .NET Core 3 (который находится в стадии разработки на момент написания этой статьи) будет поддерживать многие существующие API-интерфейсы для .NET Framework, они рассчитаны на работу на настольных компьютерах и неприменимы в контейнерных средах.

## <a name="using-a-platform-or-api-that-does-not-support-net-core"></a>Использование платформы или API, не поддерживающей .NET Core

Некоторые платформы Майкрософт и платформы сторонних разработчиков не поддерживают среду .NET Core. Например, некоторые другие службы Azure предоставляют пакеты SDK, которые пока невозможно использовать в среде .NET Core. Эта ситуация временная. Все службы Azure в конечном итоге будут использовать .NET Core. Например, [Пакет SDK Azure DocumentDB для .NET Core](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core) был выпущен в виде предварительной версии 16 ноября 2016 г. В настоящее время имеется его общедоступная стабильная версия.

В течение этого переходного периода, если окажется, что какая-либо платформа или служба в Azure пока еще не поддерживает среду .NET Core с ее клиентским API, вы можете использовать аналогичный интерфейс REST API службы Azure или пакет SDK для клиента на платформе .NET Framework.

### <a name="additional-resources"></a>Дополнительные ресурсы

- **Руководство по .NET Core** \
  [https://docs.microsoft.com/dotnet/core/index](../../../core/index.md)

- **Перенос кода в .NET Core из .NET Framework** \
  [https://docs.microsoft.com/dotnet/core/porting/index](../../../core/porting/index.md)

- **Руководство по Docker в .NET Core** \
  [https://docs.microsoft.com/dotnet/core/docker/introduction](../../../core/docker/introduction.md)

- **Общие сведения о компонентах .NET** \
  [https://docs.microsoft.com/dotnet/standard/components](../../../standard/components.md)

>[!div class="step-by-step"]
>[Назад](net-core-container-scenarios.md)
>[Вперед](container-framework-choice-factors.md)
