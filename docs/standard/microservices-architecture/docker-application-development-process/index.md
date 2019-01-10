---
title: Процесс разработки для приложений на основе Docker
description: Общий обзор возможностей для разработки приложений Docker. Использование Visual Studio для Windows, Visual Studio для Mac и Visual Studio Code для поддержки нескольких платформ (Windows, Mac и Linux).
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/27/2018
ms.openlocfilehash: eb87f9a214dbffe71dae1e1739f2563c08fac280
ms.sourcegitcommit: d09c77414e9e4fc72c79b04deee7a756a120674e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2019
ms.locfileid: "54084931"
---
# <a name="development-process-for-docker-based-applications"></a>Процесс разработки для приложений на основе Docker

*Вы можете разрабатывать контейнерные приложения .NET так, как вам нравится: либо с помощью интегрированной среды разработки (IDE) Visual Studio и Средств Visual Studio для Docker, либо с помощью интерфейса командной строки (CLI) и редактора — CLI Docker и Visual Studio Code.*

## <a name="development-environment-for-docker-apps"></a>Среда разработки приложений Docker

### <a name="development-tool-choices-ide-or-editor"></a>Выбор средства разработки: интегрированная среда разработки или редактор

Предпочитаете ли вы использовать полнофункциональную среду IDE или упрощенный редактор, корпорация Майкрософт предлагает средства, с помощью которых можно разрабатывать приложения Docker.

**Visual Studio (для Windows).** При разработке приложений Docker с помощью Visual Studio, мы рекомендуем использовать Visual Studio 2017 начиная с версии 15.7. Этот инструмент уже встроен в средства для Docker. Средства для Docker позволяют разрабатывать, запускать и проверять приложения непосредственно в целевой среде Docker. Нажмите клавишу F5 для запуска и отладки приложения (на основе одного контейнера или нескольких) непосредственно в узле Docker или нажмите клавиши CTRL+F5 для редактирования и обновления приложения без повторной сборки контейнера. Это самый эффективный вариант разработки приложений на основе Docker.

**Visual Studio для Mac.** Это интегрированная среда разработки, дальнейшее развитие Xamarin Studio, которая работает в macOS и поддерживает Docker с середины 2017 года. Она должна быть предпочтительным вариантом для разработчиков, работающих на компьютерах Mac и стремящихся использовать мощную интегрированную среду разработки.

**Visual Studio Code и CLI Docker**. Если вам нужен упрощенный кроссплатформенный редактор, поддерживающий любой язык программирования, то вы можете использовать Microsoft Visual Studio Code (VS Code) и CLI Docker. Таким образом реализуется кроссплатформенный подход к разработке приложений для Mac OS, Linux и Windows. Кроме того, Visual Studio Code поддерживает расширения для Docker, такие как IntelliSense для Dockerfile, и ярлыки для выполнения команд Docker из редактора.

Установив средства [Docker Community Edition (CE)](https://www.docker.com/community-edition), вы можете использовать единый интерфейс CLI Docker, чтобы создавать приложения как для Windows, так и для Linux.

### <a name="additional-resources"></a>Дополнительные ресурсы

- **Visual Studio**. Официальный сайт \
  [*https://visualstudio.microsoft.com/vs/*](https://visualstudio.microsoft.com/vs/)

- **Visual Studio Code**. Официальный сайт \
  [*https://code.visualstudio.com/download*](https://code.visualstudio.com/download)

- **Docker Community Edition (CE) для Mac и Windows** \.
  [*https://www.docker.com/community-editions*](https://www.docker.com/community-edition)

## <a name="net-languages-and-frameworks-for-docker-containers"></a>Языки и платформы .NET для контейнеров Docker

Как уже упоминалось в предыдущих разделах этого руководства, при разработке приложений .NET, помещенных в контейнеры Docker, можно использовать .NET Framework, .NET Core или проект Mono с открытым кодом. При разработке приложений на основе контейнеров Linux или Windows можно использовать язык C\#, F\# или Visual Basic в зависимости от применяемой платформы .NET. Дополнительные сведения о языках .NET см. в записи блога [Стратегия .NET в отношении языков](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/).

>[!div class="step-by-step"]
>[Назад](../architect-microservice-container-applications/using-azure-service-fabric.md)
>[Вперед](docker-app-development-workflow.md)