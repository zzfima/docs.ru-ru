---
title: "Среда разработки приложений Docker"
description: "Жизненный цикл приложений контейнерного Docker с помощью платформы Майкрософт и средств"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: eedba16136ad394bda45cc871944f9b876c8ee38
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2017
---
# <a name="development-environment-for-docker-apps"></a>Среда разработки приложений Docker

## <a name="development-tools-choices-ide-or-editor"></a>Выбор средства разработки: IDE или редактора

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
