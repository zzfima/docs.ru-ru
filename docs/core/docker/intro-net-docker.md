---
title: "Общие сведения о .NET и Docker"
description: "Основные сведения о Docker и .NET Core"
keywords: .NET, .NET Core, Docker
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
manager: wpickett
ms.custom: mvc
ms.openlocfilehash: 1c9ce7a008c86d1c245ce8b7d616e05fcb3d4bbc
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="introduction-to-net-and-docker"></a>Общие сведения о .NET и Docker

 Эта статья содержит введение и концептуальную основу для работы с .NET в Docker. 

## <a name="docker-packaging-your-apps-to-deploy-and-run-anywhere"></a>Docker: Упаковка приложений для развертывания и выполнения в любом месте

[Docker](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-defined) – это открытая платформа, которая позволяет разработчикам и администраторам для построения [изображения](https://docs.docker.com/glossary/?term=image), распространять и выполнения распределенных приложений в слабо изолированной среде называется [контейнера](https://www.docker.com/what-container). Такой подход позволяет эффективно использование управления жизненным циклом разработки, контроля Качества и рабочих средах.
 
[Платформа Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) использует [подсистемы Docker](https://docs.docker.com/engine/docker-overview/#docker-engine) быстро построить и пакет приложения в качестве [Docker images](https://docs.docker.com/glossary/?term=image) создан с помощью файлов, записанных [Dockerfile ](https://docs.docker.com/glossary/?term=Dockerfile) формат, который затем развертывается и запускается [многоуровневая контейнер](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).

Можно создать собственные [многоуровневая изображения](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) файлов dockerfile или использование существующих из [реестра](https://docs.docker.com/glossary/?term=registry), таких как [Docker Hub](https://docs.docker.com/glossary/?term=Docker%20Hub).

[Связь между контейнеры Docker, изображения и реестров](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries) — это важная концепция при [архитектуры и проектирование контейнерных приложений или микрослужбами](https://docs.microsoft.com/dotnet/standard/microservices-architecture/architect-microservice-container-applications/). Такой подход значительно сокращает время между разработки и развертывания.

### <a name="further-reading-and-watching"></a>Дополнительные сведения (и просмотр)

* [Контейнеры на основе Windows: Разработка современных приложений с корпоративным уровнем управления.](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be)
* [Общие сведения о docker](https://docs.docker.com/engine/docker-overview/)
* [Dockerfile в контейнерах Windows](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [Советы и рекомендации по составлению файлов Dockerfile](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)
* [Сборка Docker Images для приложений .NET Core](../docker/building-net-docker-images.md)


### <a name="getting-net-docker-images"></a>Получение образов Docker .NET

Образы Docker официальный .NET созданы и оптимизированы корпорацией Майкрософт. Они доступны публично в репозиториях Microsoft в концентраторе Docker. Каждого репозитория может содержать несколько образов, в зависимости от версии платформы .NET и версии ОС. Большинство репозиториев изображения предоставляют широко тегов, чтобы облегчить выбор версии конкретной платформы и ОС (дистрибутив Linux или версии Windows).

## <a name="scenario-based-guidance"></a>Сценарий на основе рекомендации

Корпорации Майкрософт для .NET репозиториев призван имеют репозиториев организованную и имеющего фокус, представляющие конкретному сценарию или рабочей нагрузки.

`microsoft/aspnetcore` Изображения оптимизированы для приложений ASP.NET Core для Docker, поэтому контейнеры можно запустить быстрее.

.NET Core изображений (`microsoft/dotnet`), предназначены для приложений консоли, в зависимости от .NET Core. Например процессы пакетной обработки, веб-заданий Azure и других сценариев консоли следует использовать оптимизированные изображения .NET Core.

Наиболее очевидным горизонтальной сценария по использованию приложений Docker и .NET — для рабочего развертывания и размещения. Оказывается, что производства — всего лишь одного сценария, и остальные одинаково полезны. Эти сценарии не являются специфичными для .NET, но также применимы для большинства платформ разработки.

* **Установка низкого трения** — можно опробовать .NET без локальной установки. Просто загрузите образа Docker с помощью .NET в нем.

* **Разработка в контейнере** — можно разрабатывать в согласованной среде, выполняющего аналогичные (Предотвращение проблем, таких как глобальное состояние на компьютерах разработчиков) разработки и рабочих средах. Visual Studio Tools для Docker даже позволяют запускать контейнер непосредственно из Visual Studio.

* **Тестирование в контейнере** — можно проверить в контейнере, уменьшая сбои из-за неправильно настроенной среды или другие изменения, оставшиеся от последнего теста.

* **Сборки в контейнере** — вы можете создать код в контейнере, устраняя необходимость правильно настроить на компьютерах сборки, общего для нескольких сред, но вместо этого переместить «BYOC» (Используйте собственный контейнер) подход.

* **Развертывания в любых средах** — можно развертывать образ с помощью всех сред. Этот подход уменьшает сбои из-за различий в настройках, обычно изменения поведения изображения через внешнюю конфигурацию (например, введенный переменные).

[Общие рекомендации](https://docs.microsoft.com/dotnet/standard/microservices-architecture/net-core-net-framework-containers/general-guidance) для Выбор между .NET Core и .NET Framework для разработки контейнер Docker.

### <a name="common-docker-development-scenarios"></a>Распространенные сценарии разработки Docker

#### <a name="net-core"></a>.NET Core

**Ресурсы .NET core**

 Выберите подходящие сценарии процент образцы .NET Core. Все инструкции образец описываются способы нацеливания Windows или Linux Docker образы из Windows, Linux и macOS узлов.

Примеры использования .NET Core 2.0. Они используют Docker [построения многоэтапным](https://github.com/dotnet/announcements/issues/18) и [несколькими arch теги](https://github.com/dotnet/announcements/issues/14) в случае необходимости.

* [.NET core изображений на DockerHub](https://hub.docker.com/r/microsoft/dotnet/)

* [Dockerize приложения .NET Core](https://docs.docker.com/engine/examples/dotnetcore/)

* В этом образце .NET Core Docker показано как [использовать Docker в процессе разработки .NET Core](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev). Образец работает с контейнерами Windows и Linux.

* В этом примере .NET Core Docker демонстрируется лучше всего рекомендаций для [построения образов Docker для приложений .NET Core для рабочей среды.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod) Образец работает с контейнерами Windows и Linux.

* Это [образец .NET Core Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) показан шаблон лучший подход для создания образов Docker для [автономные приложения .NET Core](https://docs.microsoft.com/dotnet/core/deploying/). Для наименьшего контейнера рабочей среде без выгода от [базовые образы между контейнерами для управления доступом](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/). Однако нижних слоев Docker может использоваться совместно.

#### <a name="arm32--raspberry-pi"></a>ARM32 / Raspberry Pi

* [Объявление построений ARM32 среды выполнения .NET core](https://github.com/dotnet/announcements/issues/29)

* [ARM32 / images Raspberry Pi .NET Core на DockerHub](https://hub.docker.com/r/microsoft/dotnet/)

* [ARM32 / Samples малиновая Pi .NET Core Docker на GitHub](https://github.com/dotnet/dotnet-docker-samples#arm32--raspberry-pi)

#### <a name="net-framework"></a>.NET Framework

* [.NET framework изображений на DockerHub](https://hub.docker.com/r/microsoft/dotnet-framework/) этого репозитория содержит образцы, демонстрирующие различные конфигурации .NET Framework Docker. Эти образы можно использовать как основу для образов Docker.

**.NET framework 4.7**

[ [Dotnet-образец framework: 4.7](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) демонстрирует основные «hello world» использование [.NET Framework 4.7](https://docs.microsoft.com/dotnet/framework/whats-new/index#introducing-the-net-framework-47). Он показано, как построить и развернуть приложение, полагаясь на [образа docker .NET Framework 4.7](https://github.com/Microsoft/dotnet-framework-docker/blob/master/4.7/Dockerfile).

**.NET framework 4.6.2**

[Dotnet-образец framework: 4.6.2](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) демонстрирует основные «hello world» использование [.NET Framework 4.6.2](https://docs.microsoft.com/dotnet/framework/whats-new/index#whats-new-in-the-net-framework-462). Он показано, как построить и развернуть приложение, полагаясь на [образа docker .NET Framework 4.6.2](https://github.com/Microsoft/dotnet-framework-docker/tree/master/4.6.2).

**Платформа .NET framework 3.5**

 [Dotnet-образец framework: 3.5](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) демонстрирует основные «hello world» использование [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker/tree/master/3.5). Он показывает, как построить и развернуть проект на .NET Framework 3.5 в Docker.

#### <a name="aspnet-core"></a>ASP.NET Core

* [В этом примере ASP.NET Core Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) показан шаблон лучший подход для создания образов Docker для ASP.NET Core приложений для рабочей среды. Образец работает с контейнерами Windows и Linux.

* [ASP.NET Core изображений на DockerHub](https://hub.docker.com/r/microsoft/aspnetcore-build/)

* [ASP.NET Core изображения на GitHub](https://github.com/aspnet/aspnet-docker)

#### <a name="aspnet-framework"></a>Платформа ASP.NET 

* [Платформа ASP.NET изображений на DockerHub](https://hub.docker.com/r/microsoft/aspnet/)

* [Приложение веб-форм ASP.NET на примеры .NET Framework 4.6.2](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/aspnetapp)

#### <a name="windows-communication-framework-wcf"></a>Windows Communication Framework (WCF)

* [Образы Windows Communication Framework (WCF) на DockerHub](https://hub.docker.com/r/microsoft/wcf/)

* [Образы Windows Communication Framework (WCF) на сайте GitHub](https://github.com/microsoft/iis-docker)

* [Образцы Windows Communication Framework (WCF) Docker на основе .NET Full Framework 4.6.2](https://github.com/Microsoft/wcf-docker-samples)

#### <a name="internet-information-server-iis"></a>Internet Information Server (IIS)

* [Образы Internet Information Server (IIS) на DockerHub](https://hub.docker.com/r/microsoft/iis/)

* [Образы Internet Information Server (IIS) на сайте GitHub](https://github.com/microsoft/wcf-docker)

### <a name="interact-with-other-microsoft-stack-container-images"></a>Взаимодействие с другими образы контейнеров стека Microsoft

#### <a name="microsoft-sql-server"></a>Microsoft SQL Server

* [Запустите Microsoft SQL Server для Linux 2017 г образа контейнера с Docker начало работы](https://docs.microsoft.com/sql/linux/quickstart-install-connect-docker)

* [Microsoft SQL Server для образов Linux на DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [Microsoft SQL Server для контейнеров Windows изображений на DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [Microsoft SQL Server, экспресс-выпуск образов для контейнеров Windows на DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows-express/)

* [Microsoft SQL Server Developer Edition образов для контейнеров Windows на DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows-developer/)

#### <a name="visual-studio-team-services-vsts-agent"></a>Агент Visual Studio Team Services (VSTS)

* [Изображений в Visual Studio Team Services (VSTS) агента на DockerHub](https://hub.docker.com/r/microsoft/vsts-agent/)

* [Образы в Visual Studio Team Services (VSTS) агента на GitHub](https://github.com/Microsoft/vsts-agent-docker)

#### <a name="operations-management-suite-oms-linux-agent"></a>Агент Operations Management Suite (OMS) Linux

* [Общие сведения об агенте Operations Management Suite (OMS) Linux](https://github.com/Microsoft/OMS-Agent-for-Linux/blob/master/docs/Docker-Instructions.md#overview)

* [Operations Management Suite (OMS) изображений на DockerHub](https://hub.docker.com/r/microsoft/vsts-agent/) 

* [Образы Operations Management Suite (OMS) на сайте GitHub](https://github.com/Microsoft/OMS-docker)

#### <a name="microsoft-azure-command-line-interface-cli"></a>Microsoft Azure командной строки (CLI)

* [Microsoft Azure интерфейс командной строки (CLI) изображений на DockerHub](Docker image for Microsoft Azure Command Line Interface) 

* [Microsoft Azure интерфейс командной строки (CLI) изображений на GitHub](https://github.com/Microsoft/OMS-docker)

> [!Note]
> Если у вас подписка на Azure, [Зарегистрируйтесь](https://azure.microsoft.com/free/?b=16.48) для бесплатной 30-дневной учетной записи и get 200 в кредиты Azure, чтобы испытать любое сочетание служб Azure.
>

#### <a name="microsoft-azure-cosmos-db-emulator-windows-containers-only"></a>Эмулятор Microsoft Azure Cosmos DB (только для контейнеров Windows)

* [Эмулятор Microsoft Azure Cosmos DB изображений на DockerHub](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator) 

* [Использование эмулятора Azure Cosmos DB локальной разработки и тестирования](https://docs.microsoft.com/azure/cosmos-db/local-emulator#developing-with-the-emulator)

## <a name="exploring-the-rich-docker-development-ecosystem"></a>Изучение экосистеме разработки многофункциональных Docker

Теперь, когда вы изучили платформы Docker и различные изображения Docker, следующим шагом является исследование форматированного экосистеме Docker. Следующие ссылки покажут, как средства Microsoft дополняют разработки контейнера.

* [Совместное использование .NET и Docker](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/) 
* [Проектирование и разработка приложений на основе Микрослужбу и несколькими контейнера .NET](../standard/microservices-architecture/multi-container-microservice-net-applications)
* [Расширение Visual Studio код Docker](https://code.visualstudio.com/docs/languages/dockerfile) 
* [Использование Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/) 
* [Пример работы начало Service Fabric](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/)
* [Преимущества контейнеров Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/index#video-overview)
* [Работа со средствами Visual Studio Docker](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Развертывание образов Docker из реестра контейнер Azure с экземплярами Azure контейнера](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [Отладка с кодом Visual Studio](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [Получение руки по с помощью Visual Studio для Mac, контейнеры и без сервера кода в облаке](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [Начало работы с Docker и Visual Studio для Mac лаборатории](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

## <a name="next-steps"></a>Дальнейшие действия

* [Основы Docker с помощью .NET Core](../docker/docker-basics-dotnet-core.md)
* [Создание образов Docker .NET Core](../docker/building-net-docker-images)