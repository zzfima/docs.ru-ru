---
title: Среда разработки приложений Docker
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c164b94572a8fde58124acaa14d47da574a19383
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="development-environment-for-docker-apps"></a>Среда разработки приложений Docker

## <a name="development-tools-choices-ide-or-editor"></a>Выбор средства разработки: IDE или редактор

Независимо от при желании полные и мощные IDE или редактора упрощенных и гибкой, корпорация Майкрософт вас когда речь заходит о разработке приложений Docker.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code и Docker CLI (кросс платформенных инструменты для Mac, Linux и Windows)

Если вы предпочитаете упрощенный, кросс платформенных редактора, поддержка любой язык разработки, можно использовать кода Visual Studio и Docker CLI. Эти продукты обеспечивают простой и надежной работы, которая необходима для оптимизации разработчика рабочего процесса. Установив «Docker для Mac» или «Docker для Windows» (среда разработки), Docker позволяют разработчикам один Docker CLI для создания приложений для Windows или Linux (среда выполнения). Кроме того, код Visual Studio поддерживает расширения для Docker с поддержкой технологии IntelliSense для файлов Dockerfile и ярлык задачи для выполнения команд Docker из редактора.

> [!NOTE]
> Чтобы загрузить кода Visual Studio, перейдите на <https://code.visualstudio.com/download>.

Чтобы загрузить Docker для Mac и Windows, перейдите к <http://www.docker.com/products/docker>.

### <a name="visual-studio-with-docker-tools"></a>Visual Studio с помощью средств Docker

Если вы используете Visual Studio 2015 можно установить дополнительные средства «Docker средства для Visual Studio». Для Visual Studio 2017 г., Docker средства, предоставляемые встроенной уже. В обоих случаях можно разрабатывать, запуска и проверки приложения непосредственно в выбранной среде Docker. F5 приложения (один контейнер или несколько контейнеров) непосредственно в Docker разместить с отладкой, либо нажмите клавиши Ctrl + F5, чтобы изменить и обновить приложение без необходимости перестроения контейнера. Это простой и расширенные возможности для разработчиков Windows, создание контейнеров Docker для Windows или Linux.

> [!NOTE]
> Чтобы загрузить набор средств Docker для Visual Studio, перейдите на <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.

## <a name="language-and-framework-choices"></a>Выбор языка и платформы

Можно разрабатывать приложения Docker и средства Microsoft с наиболее современные языки. Ниже приведен исходный список, но вы не ограничены его:

-   .NET core и ASP.NET Core

-   Node.js

-   Golang

-   Java

-   Ruby

-   Python

По сути можно использовать любой современный язык, поддерживаемый Docker в Windows или Linux.


>[!div class="step-by-step"]
[Предыдущие] (координировать высокой масштабируемость availability.md) [Далее] (docker приложения внутреннее loop-workflow.md)
