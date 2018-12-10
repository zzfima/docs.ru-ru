---
title: Процесс разработки для приложений на основе Docker
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Процесс разработки для приложений на основе Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: 7736c1fe4cb1a2a4553ba36cecceab37e2fe90c4
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144472"
---
# <a name="development-process-for-docker-based-applications"></a>Процесс разработки для приложений на основе Docker

*Вы можете разрабатывать контейнерные приложения .NET так, как вам нравится: либо с помощью интегрированной среды разработки (IDE) Visual Studio и Средств Visual Studio для Docker, либо с помощью интерфейса командной строки (CLI) и редактора — CLI Docker и Visual Studio Code.*

## <a name="development-environment-for-docker-apps"></a>Среда разработки приложений Docker

### <a name="development-tool-choices-ide-or-editor"></a>Выбор средства разработки: IDE или редактор

Предпочитаете ли вы использовать полнофункциональную среду IDE или упрощенный редактор, корпорация Майкрософт предлагает средства, с помощью которых можно разрабатывать приложения Docker.

**Visual Studio (для Windows)**. Для разработки приложений на основе Docker используйте Visual Studio 2017 или более поздние версии, в которые уже встроены средства для Docker. Средства для Docker позволяют разрабатывать, запускать и проверять приложения непосредственно в целевой среде Docker. Нажмите клавишу F5 для запуска и отладки приложения (на основе одного контейнера или нескольких) непосредственно в узле Docker или нажмите клавиши CTRL+F5 для редактирования и обновления приложения без повторной сборки контейнера. Это самый эффективный вариант разработки приложений на основе Docker.

**Visual Studio для Mac**. Это интегрированная среда разработки, которая является эволюцией Xamarin Studio, выполняется в macOS и поддерживает разработку приложений на основе Docker. Она должна быть предпочтительным вариантом для разработчиков, работающих на компьютерах Mac и стремящихся использовать мощную интегрированную среду разработки.

**Visual Studio Code и CLI Docker**. Если вам нужен упрощенный кроссплатформенный редактор, поддерживающий любой язык программирования, то вы можете использовать Microsoft Visual Studio Code (VS Code) и CLI Docker. Таким образом реализуется кроссплатформенный подход к разработке приложений для Mac OS, Linux и Windows.

Установив средства [Docker Community Edition (CE)](https://www.docker.com/community-edition), вы можете использовать единый интерфейс CLI Docker, чтобы создавать приложения как для Windows, так и для Linux. Кроме того, Visual Studio Code поддерживает расширения для Docker, такие как IntelliSense для Dockerfile, и ярлыки для выполнения команд Docker из редактора.

### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Инструменты Visual Studio для Docker**
    [*https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker*](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)

-   **Visual Studio Code**. Официальный сайт
    [*https://code.visualstudio.com/download*](https://code.visualstudio.com/download)

-   **Docker Community Edition (CE) для Mac и Windows**
    [*https://www.docker.com/community-editions*](https://www.docker.com/community-edition)

## <a name="net-languages-and-frameworks-for-docker-containers"></a>Языки и платформы .NET для контейнеров Docker

Как уже упоминалось в предыдущих разделах этого руководства, при разработке приложений .NET, помещенных в контейнеры Docker, можно использовать .NET Framework, .NET Core или проект Mono с открытым кодом. При разработке приложений на основе контейнеров Linux или Windows можно использовать язык C\#, F\# или Visual Basic в зависимости от применяемой платформы .NET. Дополнительные сведения о языках .NET см. в записи блога [Стратегия .NET в отношении языков](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/).

>[!div class="step-by-step"]
>[Назад](../architect-microservice-container-applications/using-azure-service-fabric.md)
>[Вперед](docker-app-development-workflow.md)