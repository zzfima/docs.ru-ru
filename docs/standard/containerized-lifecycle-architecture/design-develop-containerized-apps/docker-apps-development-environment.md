---
title: Среда разработки приложений Docker
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 471b52fd577e5560bd93e6da50f2032d63eb2e6f
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152420"
---
# <a name="development-environment-for-docker-apps"></a>Среда разработки приложений Docker

## <a name="development-tools-choices-ide-or-editor"></a>Выбор средства разработки: Интегрированная среда разработки или редактор

Независимо от того, если вы предпочитаете полнофункциональную среду IDE или упрощенный редактор, корпорация Майкрософт предлагает вам рассматриваются, когда дело доходит до разработки приложений Docker.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code и CLI Docker (кросс платформенные средства для Mac, Linux и Windows)

Если вам нужен упрощенный, кросс платформенных редактор, поддерживающий любой язык программирования, можно использовать Visual Studio Code и Docker CLI. Эти решения обеспечивают простой и надежной, что очень важно для оптимизации рабочий процесс разработки. Установив «Docker для Mac» или «Docker для Windows» (среда разработки), разработчики Docker можно использовать единый интерфейс CLI Docker для создания приложений для Windows или Linux (среду выполнения). Кроме того, Visual Studio Code поддерживает расширения для Docker с поддержкой технологии IntelliSense для файлов Dockerfile и ярлыками задач для выполнения команд Docker из редактора.

> [!NOTE]
> Чтобы скачать Visual Studio Code, перейдите к <https://code.visualstudio.com/download>.

Чтобы скачать Docker для Mac и Windows, перейдите к <https://www.docker.com/products/docker>.

### <a name="visual-studio-with-docker-tools"></a>Visual Studio с помощью средств Docker

При использовании Visual Studio 2015 можно установить дополнительные средства «Docker Tools for Visual Studio». Для Visual Studio 2017 средства Docker предоставляются вместе с используемыми в уже. В обоих случаях, которые можно разрабатывать запускать и проверять приложения непосредственно в выбранной среде Docker. F5 приложения (контейнера одного или нескольких) непосредственно в Docker разместить с отладкой, или нажмите клавиши Ctrl + F5, чтобы изменить и обновить приложение без повторной сборки контейнера. Это самый простой и эффективный Выбор для разработчиков Windows, создание контейнеров Docker для Windows или Linux.

> [!NOTE]
> Чтобы скачать средства Docker для Visual Studio, перейдите к <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.

## <a name="language-and-framework-choices"></a>Выбор языка и платформы

Вы можете разрабатывать приложения Docker и средства Microsoft с наиболее современные языки. Ниже приведен исходный список, но вы не ограничены его:

-   .NET Core и ASP.NET Core
-   Node.js
-   Golang
-   Java
-   Ruby
-   Python

По сути можно использовать любой современный язык, поддерживаемых в Docker в Linux или Windows.

>[!div class="step-by-step"]
>[Назад](orchestrate-high-scalability-availability.md)
>[Вперед](docker-apps-inner-loop-workflow.md)