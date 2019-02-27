---
title: Среда разработки приложений Docker
description: Узнайте о наиболее важные параметры средства разработки, которые поддерживают жизненного цикла разработки Docker.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 09d15d4221d948b654912a8890df66052e68f6eb
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2019
ms.locfileid: "56836179"
---
# <a name="development-environment-for-docker-apps"></a>Среда разработки приложений Docker

## <a name="development-tools-choices-ide-or-editor"></a>Выбор средств разработки: интегрированная среда разработки или редактор

Независимо от того, если вы предпочитаете полнофункциональную среду IDE или упрощенный редактор, корпорация Майкрософт предлагает вам рассматриваются, когда дело доходит до разработки приложений Docker.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code и CLI Docker (кросс платформенные средства для Mac, Linux и Windows)

Если вам нужен упрощенный, кросс платформенных редактор, поддерживающий любой язык программирования, можно использовать Visual Studio Code и Docker CLI. Эти решения обеспечивают простой и надежной, что очень важно для оптимизации рабочий процесс разработки. Установив «Docker для Mac» или «Docker для Windows» (среда разработки), разработчики Docker можно использовать единый интерфейс CLI Docker для создания приложений для Windows или Linux (среду выполнения). Кроме того, Visual Studio Code поддерживает расширения для Docker с поддержкой технологии IntelliSense для файлов Dockerfile и ярлыками задач для выполнения команд Docker из редактора.

> [!NOTE]
>
> Чтобы скачать Visual Studio Code, перейдите к <https://code.visualstudio.com/download>.
>
> Чтобы скачать Docker для Mac и Windows, перейдите к <https://www.docker.com/products/docker>.

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a>Visual Studio с помощью инструментов Docker (на компьютере разработки Windows)

Мы рекомендуем использовать Visual Studio 2017 (или более поздней версии) с помощью встроенных инструментов Docker включена. С помощью Visual Studio можно разрабатывать, запускать и проверять приложения непосредственно в выбранной среде Docker. Нажмите клавишу F5 для отладки приложения (контейнера одного или нескольких) непосредственно в узле Docker или нажмите сочетание клавиш Ctrl + F5, чтобы изменить и обновить приложение без повторной сборки контейнера. Это самый простой и эффективный способ для разработчиков Windows для создания контейнеров Docker для Windows или Linux.

### <a name="visual-studio-for-mac-mac-development-machine"></a>Visual Studio для Mac (компьютер разработки Mac)

Можно использовать [Visual Studio для Mac](https://visualstudio.microsoft.com/vs/mac/) при разработке приложений на основе Docker. Visual Studio для Mac предлагает более широкие интегрированной среды разработки, по сравнению с Visual Studio Code для Mac.

## <a name="language-and-framework-choices"></a>Выбор языка и платформы

Можно разрабатывать приложения Docker с помощью средств Microsoft с наиболее современные языки. Ниже приведен исходный список, но вы не ограничены его:

- .NET Core и ASP.NET Core
- Node.js
- Go
- Java
- Ruby
- Python

По сути можно использовать любой современный язык, поддерживаемых в Docker в Linux или Windows.

>[!div class="step-by-step"]
>[Назад](deploy-azure-kubernetes-service.md)
>[Вперед](docker-apps-inner-loop-workflow.md)
