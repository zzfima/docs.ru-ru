---
title: "Когда лучше использовать .NET Framework для контейнеров Docker"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Когда лучше использовать .NET Framework для контейнеров Docker"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1bf1f055f040e7f3dc575b7a04140ebf0c599f98
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a>Когда лучше использовать .NET Framework для контейнеров Docker

Пока .NET Core имеет значительные преимущества для новых приложений и шаблоны приложений, платформа .NET Framework будет продолжать подходит для многих существующих сценариев.

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a>Перенос существующих приложений прямо к контейнеру Windows Server

Вы можете использовать контейнеры Docker только для упрощения развертывания, даже если вы не создаете микрослужбами. Например, это может потребоваться повысить рабочий процесс DevOps с помощью Docker, контейнеры, поможет вам лучше изолированной тестовых сред и можно устранить проблемы с развертыванием вызвана отсутствием зависимостей при перемещении в производственной среде. В подобных случаях даже при развертывании монолитные приложения, имеет смысл использовать Docker и контейнеры Windows для текущего приложения .NET Framework.

В большинстве случаев для этого сценария не требуется перенос существующих приложений на .NET Core; можно использовать контейнеры Docker, которые содержат традиционных .NET Framework. Тем не менее рекомендуется использовать .NET Core, как расширение существующего приложения, такие как создание новой службы в ASP.NET Core.

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a>С помощью библиотеки .NET сторонних разработчиков или пакеты NuGet недоступно для .NET Core

Сторонние библиотеки быстрого принятия [.NET Standard](https://docs.microsoft.com/dotnet/standard/net-standard), позволяющий коду, совместное использование все выпуски .NET, включая .NET Core. Библиотека Standard .NET 2.0 и более поздних рабочую область API совместимости различных платформ стала значительно больше, и в .NET Core 2.0 приложения также напрямую ссылаются существующие библиотеки .NET Framework (см. [совместимости Прокладка](https://github.com/dotnet/standard/blob/master/docs/faq.md#how-does-net-standard-versioning-work)).

Тем не менее даже при использовании этого исключительные продвижения с момента .NET Standard 2.0 и .NET Core 2.0, может быть случаев, когда требуется Windows для запуска определенных пакетов NuGet и могут не поддерживать .NET Core. Если эти пакеты являются критическими для вашего приложения, затем необходимо будет использовать .NET Framework в контейнерах Windows.

## <a name="usingnet-technologies-not-available-for-net-core"></a>Технологии Using.NET недоступно для .NET Core 

Некоторые технологии .NET Framework доступны не в текущей версии .NET Core (версии 2.0 на момент написания этой статьи). Некоторые из них будут доступны в более поздних версиях .NET Core (.NET Core 2.x), в новом приложении шаблоны мишенью .NET Core и никогда не могут быть доступны другим пользователям применения.

В следующем списке приведены большинство технологий, которые недоступны в .NET Core 2.0:

-   Веб-форм ASP.NET. Данная технология доступна только в .NET Framework. В настоящее время добавление веб-форм ASP.NET в среду .NET Core не планируется.

-   Службы WCF. Даже в том случае, когда [WCF клиентская библиотека](https://github.com/dotnet/wcf) доступна для использования служб WCF из .NET Core. начиная с mid 2017 г реализация WCF сервера доступна только для .NET Framework. Этот сценарий может считаться для будущих выпусков .NET Core.

-   Службы, связанные с рабочего процесса. Windows Workflow Foundation (WF), службы рабочего процесса (WCF + WF в одной службы) и службы данных WCF (ранее называвшиеся службами данных ADO.NET) доступны только в .NET Framework. В данный момент не планирует перевести их на .NET Core.

В дополнение к технологии, перечисленные в официальные [.NET Core стратегия](https://github.com/aspnet/Home/wiki/Roadmap), другие функции может быть перенесена в .NET Core. Полный список см. на элементов, помеченных как [порт ядро](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core) на сайте CoreFX GitHub. Обратите внимание, что этот список не является как обязательство корпорации Майкрософт для перевода этих компонентов .NET Core — элементы просто сбора запросов от сообщества. Если вас интересует любой из перечисленных выше компонентов, рассмотрите возможность участия в обсуждениях на GitHub, чтобы воспроизводится голоса. Если вы думаете, что чего-то не хватает, [отправьте новый вопрос в репозиторий CoreFX](https://github.com/dotnet/corefx/issues/new).

## <a name="using-a-platform-or-api-that-does-not-support-net-core"></a>С помощью платформы или API, который не поддерживает .NET Core

Некоторые Microsoft или сторонних разработчиков платформы не поддерживают .NET Core. Например несколько служб Azure, предоставляют пакет SDK, который еще не доступен для использования на основе .NET Core. Это является временным, так как все службы Azure будут занимать .NET Core. Например [Azure SDK DocumentDB для .NET Core](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core/1.2.1) была выпущена в предварительной версии 16 ноября 2016 г., однако теперь является общедоступной версии (GA) как стабильная версия.

В то же время если любой платформе или службы в Azure по-прежнему не поддерживает .NET Core с его API клиента, можно использовать эквивалентное API-интерфейса REST из службы Azure или пакет SDK для клиента на .NET Framework.

### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Руководство по .NET core**
    [*https://docs.microsoft.com/dotnet/core/index*](https://docs.microsoft.com/dotnet/core/index)

-   **Перенос из .NET Framework на .NET Core**
    [*https://docs.microsoft.com/dotnet/core/porting/index*](https://docs.microsoft.com/dotnet/core/porting/index)

-   **.NET framework на руководство по Docker**
    [*https://docs.microsoft.com/dotnet/framework/docker/*](https://docs.microsoft.com/dotnet/framework/docker/)

-   **Общие сведения о компонентах .NET**
    [*https://docs.microsoft.com/dotnet/standard/components*](https://docs.microsoft.com/dotnet/standard/components)




>[!div class="step-by-step"]
[Предыдущие] (net-core контейнера scenarios.md) [Далее] (контейнер framework Выбор factors.md)
