---
title: Среда разработки приложений Docker
description: Ознакомьтесь с наиболее важными средствами разработки, поддерживающими жизненный цикл разработки Docker.
ms.date: 02/15/2019
ms.openlocfilehash: 35236e75f47e830d0970ca9cfd074d9a69e6f85c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "71214303"
---
# <a name="development-environment-for-docker-apps"></a>Среда разработки приложений Docker

## <a name="development-tools-choices-ide-or-editor"></a>Выбор средства разработки: IDE или редактор

Предпочитаете ли вы использовать полнофункциональную среду IDE или упрощенный редактор, корпорация Майкрософт предлагает вам удобное решение для разработки приложений Docker.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code и CLI Docker (кроссплатформенные средства для Mac, Linux и Windows)

Если вам нужен упрощенный кроссплатформенный редактор, поддерживающий любой язык программирования, вы можете использовать Visual Studio Code и CLI Docker. Эти решения обеспечивают простой, но в то же время эффективный рабочий процесс разработки. Установив Docker для Mac или Docker для Windows (среду разработки), разработчики приложений Docker могут использовать единый интерфейс CLI Docker (среду выполнения), чтобы создавать приложения как для Windows, так и для Linux. Кроме того, Visual Studio Code поддерживает расширения для Docker с IntelliSense для файлов Dockerfile и ярлыками для выполнения команд Docker из редактора.

> [!NOTE]
> Чтобы скачать Visual Studio Code, перейдите на страницу <https://code.visualstudio.com/download>.
>
> Чтобы скачать Docker для Mac и Windows, перейдите на страницу <https://www.docker.com/products/docker>.

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a>Visual Studio со средствами Docker (компьютер Windows для разработки)

Мы рекомендуем использовать Visual Studio 2017 (или более поздней версии) с включенными встроенными средствами Docker. С помощью Visual Studio вы можете разрабатывать, запускать и проверять приложения непосредственно в выбранной среде Docker. Нажмите клавишу F5 для отладки приложения (на основе одного контейнера или нескольких) непосредственно в узле Docker или клавиши CTRL+F5 для редактирования и обновления приложения без повторной сборки контейнера. Это самый простой и эффективный способ разработки в Windows контейнеров Docker для Linux или Windows.

### <a name="visual-studio-for-mac-mac-development-machine"></a>Visual Studio для Mac (компьютер Mac для разработки)

При разработке приложений на основе Docker можно использовать [Visual Studio для Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link). Visual Studio для Mac — это интегрированная среда разработки с более широкими возможностями по сравнению с Visual Studio Code для Mac.

## <a name="language-and-framework-choices"></a>Языки и платформы

С помощью средств Майкрософт вы можете разрабатывать приложения Docker на самых современных языках. Вот лишь часть их списка:

- .NET Core и ASP.NET Core
- Node.js
- Go
- Java
- Ruby
- Python

По сути, можно использовать любой современный язык, поддерживаемый Docker в Linux или Windows.

>[!div class="step-by-step"]
>[Назад](deploy-azure-kubernetes-service.md)
>[Вперед](docker-apps-inner-loop-workflow.md)
