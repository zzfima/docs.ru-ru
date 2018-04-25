---
title: Введение в .NET и Docker
description: Общие сведения о Docker и .NET Core
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
ms.workload:
- dotnetcore
ms.openlocfilehash: 75c631cf0abac543889cb7387f6fc3fdb2624512
ms.sourcegitcommit: 68b60d38043e50104ccc90c76f8599b1ffe18346
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="introduction-to-net-and-docker"></a>Введение в .NET и Docker

В этой статье приводятся вводные сведения и основные понятия, касающиеся работы с .NET в Docker.

## <a name="docker-packaging-your-apps-to-deploy-and-run-anywhere"></a>Docker: упаковка приложений для развертывания и выполнения в любом месте

[Docker](../../standard/microservices-architecture/container-docker-introduction/docker-defined.md) — это открытая платформа, которая позволяет разработчикам и администраторам создавать [образы](https://docs.docker.com/glossary/?term=image), а также доставлять и запускать распределенные приложения в слабо изолированной среде, называемой [контейнером](https://www.docker.com/what-container). Такой подход позволяет эффективно управлять жизненным циклом приложений в средах разработки и контроля качества, а также в рабочей среде.
 
[Платформа Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) использует [подсистему Docker](https://docs.docker.com/engine/docker-overview/#docker-engine), чтобы обеспечить быстрое создание и упаковку приложений в виде [образов Docker](https://docs.docker.com/glossary/?term=image), созданных с помощью файлов в формате [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile), которые затем развертываются и запускаются в [многослойном контейнере](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).

Вы можете создавать собственные [многослойные образы](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) в виде файлов Dockerfile или использовать существующие образы из [реестра](https://docs.docker.com/glossary/?term=registry), например [Docker Hub](https://docs.docker.com/glossary/?term=Docker%20Hub).

[Связь между контейнерами, образами и реестрами Docker](../../standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries.md) — это важный элемент в [разработке архитектуры и создании контейнерных приложений или микрослужб](../../standard/microservices-architecture/architect-microservice-container-applications/index.md). Этой подход значительно сокращает время между разработкой и развертыванием.

### <a name="further-reading-and-watching"></a>Дополнительные ресурсы и видеоматериалы

* [Windows-based containers: Modern app development with enterprise-grade control](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be) (Контейнеры для Windows. Разработка современных приложений с управлением на уровне организации)
* [Docker overview](https://docs.docker.com/engine/docker-overview/) (Общие сведения о Docker)
* [Dockerfile в контейнерах Windows](/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [Best practices for writing Dockerfiles](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/) (Рекомендации по созданию файлов Dockerfile)
* [Создание образов Docker для приложений .NET Core](../docker/building-net-docker-images.md)


### <a name="getting-net-docker-images"></a>Получение образов Docker для .NET

Корпорация Майкрософт создает и оптимизирует официальные образы Docker для .NET. Они доступны для всех в репозиториях Майкрософт в Docker Hub. Каждый репозиторий может содержать несколько образов в зависимости от версий .NET и версий ОС. Большинство репозиториев образов предоставляют широкие возможности по использованию тегов, чтобы облегчить выбор конкретной версии платформы и ОС (дистрибутива Linux или версии Windows).

## <a name="scenario-based-guidance"></a>Рекомендации на основе сценариев

Корпорация Майкрософт стремится создавать подробные специализированные репозитории .NET, представляющие конкретный сценарий или рабочую нагрузку.

Образы `microsoft/aspnetcore` оптимизированы для приложений ASP.NET Core в Docker, что позволяет запускать контейнеры быстрее.

Образы .NET Core (`microsoft/dotnet`) предназначены для консольных приложений на базе .NET Core. Например, для процессов пакетной обработки, веб-заданий Azure и других консольных сценариев следует использовать оптимизированные образы .NET Core.

Наиболее очевидным однотипным сценарием использования приложений Docker и .NET является развертывание в рабочей среде и размещение. Как оказывается, разработка — это всего лишь один из сценариев. Остальные не менее практичны. Эти сценарии можно применять для большинства платформ разработки, а не только для .NET.

* **Установка по пути наименьшего сопротивления.** Можно опробовать .NET без локальной установки. Просто скачайте образ Docker с .NET.

* **Разработка в контейнере.** Вы можете выполнять разработку в согласованной среде, создав рабочую среду, аналогичную среде разработки (это позволяет избежать такой проблемы, как глобальное состояние на компьютерах для разработки). Средства Visual Studio для Docker даже позволяют запускать контейнеры прямо из Visual Studio.

* **Тестирование в контейнере.** Тестирование можно проводить в контейнере, благодаря чему уменьшается число сбоев из-за неправильно настроенной среды или других изменений, оставшихся после последнего тестирования.

* **Сборка в контейнере.** Вы можете выполнить сборку кода в контейнере, чтобы не настраивать общие компьютеры сборки для нескольких сред, а перейти на подход BYOC (использование собственного контейнера).

* **Развертывание во всех средах.** Вы можете развернуть образ во всех своих средах. Этот подход позволяет сократить число сбоев из-за различий в настройках. Как правило, поведение образа меняется через внешнюю конфигурацию (например, внедренные переменные среды).

[Общие рекомендации](../../standard/microservices-architecture/net-core-net-framework-containers/general-guidance.md) по выбору между .NET Core и .NET Framework для разработки контейнеров Docker.

### <a name="common-docker-development-scenarios"></a>Распространенные сценарии разработки Docker

#### <a name="net-core"></a>.NET Core

**Ресурсы .NET Core**

 Выберите примеры .NET Core, которые соответствуют вашему сценарию. Во всех инструкциях в примерах описывается, как использовать образы Docker для Windows или Linux в качестве целевых сред на узлах Windows, Linux или macOS.

В примерах используется .NET Core 2.0. В примерах при необходимости используется [многоэтапная сборка](https://github.com/dotnet/announcements/issues/18) и [теги для разных архитектур](https://github.com/dotnet/announcements/issues/14) Docker.

* [Образы для .NET Core в Docker Hub](https://hub.docker.com/r/microsoft/dotnet/)

* [Добавление приложения .NET Core в Docker](https://docs.docker.com/engine/examples/dotnetcore/)

* В этом примере Docker для .NET Core показано, как [использовать Docker в процессе разработки .NET Core](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev). Этот пример поддерживается в контейнерах Linux и Windows.

* В этом примере Docker для .NET Core демонстрируется рекомендуемый шаблон [создания образов Docker для приложений .NET Core в рабочей среде](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod). Этот пример поддерживается в контейнерах Linux и Windows.

* В этом [примере Docker для .NET Core](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) демонстрируется рекомендуемый шаблон для создания образов Docker для [автономных приложений .NET Core](../deploying/index.md). Используется для наименьшего контейнера без возможности [предоставлять контейнерам общий доступ к базовым образам](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/). Но слои Docker могут использоваться совместно.

#### <a name="arm32--raspberry-pi"></a>ARM32 или Raspberry Pi

* [Объявление о доступности сборок ARM32 для среды выполнения .NET Core](https://github.com/dotnet/announcements/issues/29)

* [Образы ARM32 и Raspberry Pi для .NET Core в Docker Hub](https://hub.docker.com/r/microsoft/dotnet/)

* [Примеры ARM32 и Raspberry Pi для .NET Core в GitHub](https://github.com/dotnet/dotnet-docker-samples#arm32--raspberry-pi)

#### <a name="net-framework"></a>.NET Framework

* [Образы .NET Framework в Docker Hub](https://hub.docker.com/r/microsoft/dotnet-framework/)

Этот репозиторий содержит примеры различных конфигураций Docker для .NET Framework. Вы можете использовать эти образы в качестве основы для своих образов Docker.

**.NET Framework 4.7**

Пример [dotnet-framework:4.7](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) демонстрирует использование базового приложения Hello World на платформе [.NET Framework 4.7](../../framework/whats-new/index.md#v47). Также в нем показано, как создать и развернуть приложение на основе [образа Docker для .NET Framework 4.7](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.7/Dockerfile).

**.NET Framework 4.6.2**

В примере [dotnet-framework:4.6.2](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) демонстрируется использование базового приложения Hello World на платформе [.NET Framework 4.6.2](../../framework/whats-new/index.md#v462). Также в нем показано, как создать и развернуть приложение на основе [образа Docker для .NET Framework 4.6.2](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.6.2/Dockerfile)

**.NET Framework 3.5**

 В примере [dotnet-framework:3.5](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) демонстрируется использование базового приложения Hello World на платформе [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-3.5/dotnetapp-3.5/Dockerfile). Также в нем показано, как создать и развернуть проект на основе .NET Framework 3.5 в Docker.

#### <a name="aspnet-core"></a>ASP.NET Core

* [В этом примере Docker для ASP.NET Core](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) демонстрируется рекомендуемый шаблон создания образов Docker для приложений ASP.NET Core в рабочей среде. Этот пример поддерживается в контейнерах Linux и Windows.

* [Образы для ASP.NET Core в Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore-build/)

* [Образы для ASP.NET Core в GitHub](https://github.com/aspnet/aspnet-docker)

#### <a name="aspnet-framework"></a>ASP.NET Framework

* [Образы для ASP.NET Framework в Docker Hub](https://hub.docker.com/r/microsoft/aspnet/)

* [Пример приложения веб-форм ASP.NET в .NET Framework 4.6.2](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/aspnetapp)

#### <a name="windows-communication-framework-wcf"></a>Windows Communication Framework (WCF)

* [Образы для WCF в Docker Hub](https://hub.docker.com/r/microsoft/wcf/)

* [Образы для WCF в GitHub](https://github.com/microsoft/wcf-docker)

* [Примеры Docker для WCF с использованием .NET Full Framework 4.6.2](https://github.com/Microsoft/wcf-docker-samples)

#### <a name="internet-information-server-iis"></a>Internet Information Server (IIS)

* [Образы для IIS в Docker Hub](https://hub.docker.com/r/microsoft/iis/)

* [Образы для IIS в GitHub](https://github.com/microsoft/iis-docker)

### <a name="interact-with-other-microsoft-stack-container-images"></a>Взаимодействие с другими образами контейнеров стека Microsoft

#### <a name="microsoft-sql-server"></a>Microsoft SQL Server

* [Краткое руководство по запуску образа контейнера Microsoft SQL Server для Linux 2017 с помощью Docker](https://docs.microsoft.com/sql/linux/quickstart-install-connect-docker)

* [Образы Microsoft SQL Server для Linux в Docker Hub](https://hub.docker.com/r/microsoft/mssql-server-linux/)

* [Образы для выпуска Microsoft SQL Server Express для контейнеров Windows в Docker Hub](https://hub.docker.com/r/microsoft/mssql-server-windows-express/)

* [Образы для выпуска Microsoft SQL Server Developer для контейнеров Windows в Docker Hub](https://hub.docker.com/r/microsoft/mssql-server-windows-developer/)

#### <a name="visual-studio-team-services-vsts-agent"></a>Агент Visual Studio Team Services (VSTS)

* [Образы для агента VSTS в Docker Hub](https://hub.docker.com/r/microsoft/vsts-agent/)

* [Образы для агента VSTS в GitHub](https://github.com/Microsoft/vsts-agent-docker)

#### <a name="operations-management-suite-oms-linux-agent"></a>Агент Operations Management Suite (OMS) для Linux

* [Обзор агента OMS для Linux](https://github.com/Microsoft/OMS-Agent-for-Linux/blob/master/docs/Docker-Instructions.md)

* [Образы для агента OMS для Linux в Docker Hub](https://hub.docker.com/r/microsoft/oms/)

* [Образы для агента OMS в GitHub](https://github.com/Microsoft/OMS-docker)

#### <a name="microsoft-azure-command-line-interface-cli"></a>Интерфейс командной строки Microsoft Azure (CLI)

* [Образы для Microsoft Azure CLI в Docker Hub](https://hub.docker.com/r/microsoft/azure-cli/) 

* [Образы для Microsoft Azure CLI в GitHub](https://github.com/Azure/azure-cli#Docker)

> [!NOTE]
> Если у вас нет подписки Azure, [зарегистрируйте сейчас](https://azure.microsoft.com/free/?b=16.48) бесплатную учетную запись на 30 дней и получите 200 долл. США на счет в Azure, чтобы опробовать любое сочетание служб Azure.

#### <a name="microsoft-azure-cosmos-db-emulator-windows-containers-only"></a>Эмулятор Microsoft Azure Cosmos DB (только для контейнеров Windows)

* [Образы для эмулятора Microsoft Azure Cosmos DB в Docker Hub](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator) 

* [Использование эмулятора Azure Cosmos DB для разработки и тестирования в локальной среде](/azure/cosmos-db/local-emulator#developing-with-the-emulator)

## <a name="exploring-the-rich-docker-development-ecosystem"></a>Изучение обширной экосистемы разработки Docker

Теперь, когда вы узнали о платформе Docker и различных образах Docker, мы перейдем к изучению обширной экосистемы Docker. Из указанных ниже ресурсов вы узнаете, как средства Майкрософт дополняют средства разработки контейнеров.

* [Using .NET and Docker Together](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/) (Совместное использование .NET и Docker)
* [Проектирование и разработка приложений .NET на основе множества контейнеров и микрослужб](../../standard/microservices-architecture/multi-container-microservice-net-applications/index.md)
* [Расширение Docker для Visual Studio Code](https://code.visualstudio.com/docs/languages/dockerfile)
* [Сведения об использовании Azure Service Fabric](/azure/service-fabric/index)
* [Service Fabric Getting Started Sample](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/) (Пример начала работы с Service Fabric)
* [Преимущества контейнеров Windows](/virtualization/windowscontainers/about/index#video-overview)
* [Работа со средствами Visual Studio для Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker)
* [Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) (Развертывание образов Docker из реестра контейнеров Azure в службе "Экземпляры контейнеров Azure")
* [Отладка с помощью Visual Studio Code](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container)
* [Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments) (Получение практических навыков по работе с Visual Studio для Mac, контейнерами и бессерверным кодом в облаке)
* [Getting started integrating with Docker containers in Visual Studio for Mac](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started) (Приступая к интеграции с контейнерами Docker в Visual Studio для Mac)

## <a name="next-steps"></a>Следующие шаги

* [Основы работы с Docker с помощью .NET Core](docker-basics-dotnet-core.md)
* [Создание образов Docker для приложений .NET Core](building-net-docker-images.md)
