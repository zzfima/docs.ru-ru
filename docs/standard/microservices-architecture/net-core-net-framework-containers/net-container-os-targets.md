---
title: "Какие ОС для нацеливания .NET контейнеров"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Какие ОС для нацеливания .NET контейнеров"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 828ccb5e7a76f9419e80793b6cb3a6ba24f358cf
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="what-os-to-target-with-net-containers"></a>Какие ОС для нацеливания .NET контейнеров

Учитывая разнообразие операционных систем, поддерживаемых Docker и различия между .NET Framework и .NET Core, должно использовать определенные ОС и определенные версии в зависимости от платформы, которую вы используете. 

Для Windows можно использовать Windows Server Core или Nano Windows Server. Эти версии Windows предоставляют разные характеристики (IIS в Windows Server Core и резидентной веб-сервера как Kestrel в Nano Server), которые могут быть необходимы, .NET Framework или .NET Core, соответственно. 

Для Linux несколько дистрибутивы доступно и поддерживается в официальный образов .NET Docker (например, Debian).

На рисунке 3-1, вы увидите возможные версии операционной системы в зависимости от .NET framework, используемой.

![](./media/image1.png)

**Рисунок 3-1.** Операционные системы для среды, в зависимости от версии платформы .NET framework

Также можно создать собственный образ Docker в случаях, где вы хотите использовать другой дистрибутив Linux или нужное изображение с версиями, не предоставляемых Майкрософт. Например можно создать образ с ASP.NET Core под управлением традиционных .NET Framework и Windows Server Core сценарии not, общие для Docker.

При добавлении имени образа в файл Dockerfile, можно выбрать операционной системы и версии в зависимости от тег, который используется, как показано в следующих примерах:

-   Microsoft и**dotnet:2.0.0-среда выполнения-детском**

        .NET Core 2.0 runtime-only on Linux

-   Microsoft и**dotnet:2.0.0-среда выполнения-nanoserver-1709** 

        .NET Core 2.0 runtime-only on Windows Nano Server (Windows Server 2016 Fall Creators Update version 1709)

-   Microsoft и**aspnetcore:2.0**
    
        .NET Core 2.0 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 





>[!div class="step-by-step"]
[Предыдущие] (контейнер framework Выбор factors.md) [Далее] (официальное net-docker-images.md)
