---
title: Установка F#
description: Узнайте, как установить F-образное установить F-образное время различными способами.
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401097"
---
# <a name="install-f"></a>Установка F\#

Вы можете установить F-образное, в зависимости от среды.

## <a name="install-f-with-visual-studio"></a>Установка ФЗ с помощью визуальной студии

1. Если вы загружаете [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) в первый раз, он сначала установит Visual Studio Installer. Установите соответствующее издание Visual Studio от установки.

   Если у вас уже установлена Visual Studio, выберите **Modify** рядом с изданием, к который вы хотите добавить F-образное.

2. На странице «Рабочие нагрузки» выберите рабочую нагрузку **ASP.NET и веб-разработки,** которая включает в себя поддержку F и .NET Core для ASP.NET основных проектов.

3. Выберите **изменение** в правом нижнем углу, чтобы установить все, что вы выбрали.

   Затем вы можете открыть Visual Studio с F, выбрав **Launch** in Visual Studio Installer.

## <a name="install-f-with-visual-studio-code"></a>Установка F с визуальным кодом студии

1. Убедитесь, что у вас есть [git](https://git-scm.com/download) установлен и доступен на вашем PATH. Вы можете убедиться, что он `git --version` установлен правильно, введя в команде запрос и нажатие **Enter.**

2. Установите [код .NET Core SDK](https://dotnet.microsoft.com/download) и [Visual Studio.](https://code.visualstudio.com)

3. Выберите значок расширения и ищите "Ionide":

   Единственным плагином, необходимым для поддержки F-студии в Visual Studio Code, является [Ionide-fsharp.](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) Тем не менее, вы также можете установить [Ionide-FAKE,](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) чтобы получить поддержку [FAKE](https://fake.build/) и [Ionide-Paket,](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) чтобы получить поддержку [Paket.](https://fsprojects.github.io/Paket/) FAKE и Paket являются дополнительными инструментами сообщества F е для создания проектов и управления зависимостями, соответственно.

## <a name="install-f-with-visual-studio-for-mac"></a>Установка F с Visual Studio для Mac

Фз устанавливается по умолчанию в [Visual Studio для Mac,](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)независимо от того, какую конфигурацию вы выберете.

После завершения установки выберите **Start Visual Studio.** Вы также можете открыть Visual Studio через Finder на macOS.

## <a name="install-f-on-a-build-server"></a>Установка F-сервера на сервере сборки

Если вы используете систему .NET Core или .NET через .NET SDK, вам просто необходимо установить .NET SDK на сервер сборки. В нем есть все, что вам нужно.

Если вы используете систему .NET и **не** используете SDK .NET, то вам нужно установить [SKU Visual Studio Build Tools](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) на ваш Windows Server. В установке выберите **инструменты сборки настольных компьютеров .NET,** а затем выберите компонент **компилятора F's** на правой стороне меню установки.
