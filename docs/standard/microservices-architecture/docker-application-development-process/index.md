---
title: "Процесс разработки для приложений на основе Docker"
description: "Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Процесс разработки для приложений на основе Docker"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.translationtype: HT
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: f4c241f463ff1270037c7d66ba39409ca5d9e728
ms.contentlocale: ru-ru
ms.lasthandoff: 09/05/2017

---
# <a name="development-process-for-docker-based-applications"></a>Процесс разработки для приложений на основе Docker

*Вы можете разрабатывать контейнерные приложения .NET так, как вам нравится: либо с помощью интегрированной среды разработки (IDE) Visual Studio и Средств Visual Studio для Docker, либо с помощью интерфейса командной строки (CLI) и редактора — CLI Docker и Visual Studio Code.*

## <a name="development-environment-for-docker-apps"></a>Среда разработки приложений Docker

### <a name="development-tool-choices-ide-or-editor"></a>Выбор средства разработки: IDE или редактор

Предпочитаете ли вы использовать полнофункциональную среду IDE или упрощенный редактор, корпорация Майкрософт предлагает средства, с помощью которых можно разрабатывать приложения Docker.

**Visual Studio со средствами для Docker**. Если вы используете Visual Studio 2015, то можете установить надстройку [Средства Visual Studio для Docker](https://marketplace.visualstudio.com/items?itemName=MicrosoftCloudExplorer.VisualStudioToolsforDocker-Preview). Если вы используете среду Visual Studio 2017, средства для Docker уже встроены в нее. В любом случае средства для Docker позволяют разрабатывать, запускать и проверять приложения непосредственно в целевой среде Docker. Нажмите клавишу F5 для запуска и отладки приложения (на основе одного контейнера или нескольких) непосредственно в узле Docker или нажмите клавиши CTRL+F5 для редактирования и обновления приложения без повторной сборки контейнера. Это самый простой и эффективный способ разработки приложений, предназначенных для контейнеров Docker в Linux или Windows.

**Visual Studio Code и CLI Docker**. Если вам нужен упрощенный кроссплатформенный редактор, поддерживающий любой язык программирования, то вы можете использовать Microsoft Visual Studio Code (VS Code) и CLI Docker. Таким образом реализуется кроссплатформенный подход к разработке приложений для Mac OS, Linux и Windows.

Эти решения обеспечивают простой, но в то же время эффективный рабочий процесс разработки. Установив средства [Docker Community Edition (CE)](https://www.docker.com/community-edition), вы можете использовать единый интерфейс CLI Docker, чтобы создавать приложения как для Windows, так и для Linux. Кроме того, Visual Studio Code поддерживает расширения для Docker, такие как IntelliSense для Dockerfile, и ярлыки для выполнения команд Docker из редактора.

### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Средства Visual Studio для Docker**
    [*https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4*](https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4)

-   **Visual Studio Code**. Официальный сайт
    [*https://code.visualstudio.com/download*](https://code.visualstudio.com/download)

-   **Docker Community Edition (CE) для Mac и Windows**
    [*https://www.docker.com/community-editions*](https://www.docker.com/community-edition)

## <a name="net-languages-and-frameworks-for-docker-containers"></a>Языки и платформы .NET для контейнеров Docker

Как уже упоминалось в предыдущих разделах этого руководства, при разработке приложений .NET, помещенных в контейнеры Docker, можно использовать .NET Framework, .NET Core или проект Mono с открытым кодом. При разработке приложений на основе контейнеров Linux или Windows можно использовать язык C\#, F\# или Visual Basic в зависимости от применяемой платформы .NET. Дополнительные сведения о языках .NET см. в записи блога [Стратегия .NET в отношении языков](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/).


>[!div class="step-by-step"]
[Назад] (../architect-microservice-container-applications/using-azure-service-fabric.md) [Далее] (docker-app-development-workflow.md)

