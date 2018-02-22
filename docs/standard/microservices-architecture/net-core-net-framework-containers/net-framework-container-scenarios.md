---
title: "Выбор .NET Framework для контейнеров Docker"
description: "Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Выбор .NET Framework для контейнеров Docker"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: fcfb78bf521107b14d7796235f52c836f48f41fe
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2018
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a>Выбор .NET Framework для контейнеров Docker

Хотя среда .NET Core предоставляет значительные преимущества для новых приложений и шаблонов приложений, мы рекомендуем использовать среду .NET Framework для большинства имеющихся сценариев.

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a>Перенос существующих приложений непосредственно в контейнер Windows Server

Даже если вы не создаете микрослужбы, контейнеры Docker можно использовать для упрощения развертывания. Например, вы хотите улучшить функционирование рабочего процесса DevOps с помощью Docker. Использование контейнеров позволит вам получить хорошо изолированную тестовую среду и устранить проблемы с развертыванием, вызванные отсутствием зависимостей при перемещении в рабочую среду. В таких случаях даже при развертывании монолитных приложений имеет смысл использовать Docker и контейнеры Windows для текущего приложения .NET Framework.

В большинстве случаев при таком сценарии перенос существующих приложений на .NET Core не требуется. Можно использовать контейнеры Docker, в которые включена традиционная платформа .NET Framework. Тем не менее для расширения готовых приложений, например для разработки новой службы в ASP.NET Core рекомендуется использовать .NET Core.

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a>Использование сторонних библиотек .NET и пакетов NuGet, недоступных для .NET Core

Сторонние библиотеки [.NET Standard](https://docs.microsoft.com/dotnet/standard/net-standard) позволяют совместно использовать код в различных средах выполнения .NET, в том числе в .NET Core. Использование библиотеки Standard .NET 2.0 и API позволяет существенно улучшить совместимость различных платформ. В .NET Core 2.0 приложения могут напрямую обращаться к существующим библиотекам .NET Framework (см. [Модификатор совместимости](https://github.com/dotnet/standard/blob/master/docs/faq.md#how-does-net-standard-versioning-work)).

Несмотря на значительный прогресс, достигнутый после выхода .NET Standard 2.0 и .NET Core 2.0, могут возникнуть ситуации, когда для запуска определенных пакетов NuGet требуется Windows и эти пакеты могут не поддерживать .NET Core. Если эти пакеты имеют важное значение для вашего приложения, необходимо использовать .NET Framework в контейнерах Windows.

## <a name="using-net-technologies-not-available-for-net-core"></a>Использование технологий .NET, недоступных для .NET Core 

Некоторые технологии .NET Framework отсутствуют в текущей версии .NET Core (версии 2.0 на момент написания этой статьи). Поддержка некоторых из них будет добавлена в последующих выпусках .NET Core (.NET Core 2.x), однако остальные технологии не применяются к новым шаблонам приложений, используемым в среде .NET Core, и будут недоступными всегда.

В следующем списке указано большинство технологий, недоступных в .NET Core 2.0.

-   Веб-формы ASP.NET. Эта технология доступна только в .NET Framework. В настоящее время добавление веб-форм ASP.NET в среду .NET Core не планируется.

-   Службы WCF. Даже после того, как [библиотека WCF-Client](https://github.com/dotnet/wcf) стала доступна для использования служб WCF из .NET Core, начиная с середины 2017 г., реализация сервера WCF остается доступной только для .NET Framework. Этот сценарий, возможно, будет учтен в следующих выпусках .NET Core.

-   Службы, связанные с рабочим процессом. Службы Windows Workflow Foundation (WF), Workflow Services (WCF и WF в одной службе) и WCF Data Services (известные как службы данных ADO.NET) доступны только в среде .NET Framework. В настоящий момент не планируется их перенос в .NET Core.

В дополнение к технологиям, перечисленным в официальном [плане по .NET Core](https://github.com/aspnet/Home/wiki/Roadmap), в платформу .NET Core могут быть перенесены и другие функции. Все такие компоненты помечены на сайте CoreFX GitHub отметкой [перенос в ядро](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core). Однако следует иметь в виду, что наличие этих компонентов в списке не означает, что корпорация Майкрософт намеревается добавлять их в среду .NET Core. Компоненты, присутствующие в списке, лишь отражают запросы от пользователей сообщества. Если вас заинтересовал какой-либо из перечисленных выше компонентов, примите участие в обсуждениях на сайте GitHub и выразите свое мнение. Если вы думаете, что чего-то не хватает, [отправьте новый вопрос в репозиторий CoreFX](https://github.com/dotnet/corefx/issues/new).

## <a name="using-a-platform-or-api-that-does-not-support-net-core"></a>Использование платформы или API, не поддерживающей .NET Core

Некоторые платформы Майкрософт и платформы сторонних разработчиков не поддерживают среду .NET Core. Например, некоторые другие службы Azure предоставляют пакеты SDK, которые пока невозможно использовать в среде .NET Core. Эта ситуация временная. Все службы Azure в конечном итоге будут использовать .NET Core. Например, [Пакет SDK Azure DocumentDB для .NET Core](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core/1.2.1) был выпущен в виде предварительной версии 16 ноября 2016 г. В настоящее время имеется его общедоступная стабильная версия.

В течение этого переходного периода, если окажется, что какая-либо платформа или служба в Azure пока еще не поддерживает .NET Core с ее клиентским API, вы можете использовать аналогичный интерфейс REST API службы Azure или пакет SDK для клиента в платформе .NET Framework.

### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Руководство по .NET core**
    [*https://docs.microsoft.com/dotnet/core/index*](https://docs.microsoft.com/dotnet/core/index)

-   **Перенос кода в .NET Core из .NET Framework**
    [*https://docs.microsoft.com/dotnet/core/porting/index*](https://docs.microsoft.com/dotnet/core/porting/index)

-   **Руководство по Docker в .NET Framework**
    [*https://docs.microsoft.com/dotnet/framework/docker/*](https://docs.microsoft.com/dotnet/framework/docker/)

-   **Общие сведения о компонентах .NET**
    [*https://docs.microsoft.com/dotnet/standard/components*](https://docs.microsoft.com/dotnet/standard/components)




>[!div class="step-by-step"]
[Предыдущий] (net-core-container-scenarios.md) [Следующий] (container-framework-choice-factors.md)
