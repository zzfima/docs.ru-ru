---
title: Установка F#
description: Узнайте, как устанавливать F# различными способами.
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346563"
---
# <a name="install-f"></a>Установка F\#

В зависимости от F# среды можно установить несколькими способами.

## <a name="install-f-with-visual-studio"></a>Установка F# с помощью Visual Studio

1. Если вы скачиваете [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) впервые, сначала будет установлена Visual Studio Installer. Установите соответствующий выпуск Visual Studio из установщика.

   Если вы уже установили Visual Studio, выберите **изменить** рядом с выпуском, который необходимо F# добавить.

2. На странице рабочие нагрузки выберите рабочую нагрузку **ASP.NET and Web Development** , включающую F# и поддержку .net Core для проектов ASP.NET Core.

3. Выберите **изменить** в правом нижнем углу, чтобы установить все, что вы выбрали.

   Затем можно открыть Visual Studio с F# помощью команды **запустить** в Visual Studio Installer.

## <a name="install-f-with-visual-studio-code"></a>Установка F# с помощью Visual Studio Code

1. Убедитесь, что на вашем пути установлен и доступен [Git](https://git-scm.com/download) . Чтобы проверить правильность установки, введите `git --version` в командной строке и нажмите клавишу **Ввод**.

2. Установите [пакет SDK для .NET Core](https://dotnet.microsoft.com/download) и [Visual Studio Code](https://code.visualstudio.com).

3. Щелкните значок расширения и выполните поиск по запросу "Ionide":

   Единственным подключаемым модулем F# , необходимым для поддержки в Visual Studio Code, является [Ionide-FSharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp). Однако можно также установить [Ionide-ПОДдельные](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) , чтобы получить [поддельную](https://fake.build/) поддержку и [Ionide-пакет](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) , чтобы получить поддержку [пакет](https://fsprojects.github.io/Paket/) . Поддельные и пакет — F# это дополнительные инструменты сообщества для создания проектов и управления зависимостями соответственно.

## <a name="install-f-with-visual-studio-for-mac"></a>Установка F# с помощью Visual Studio для Mac

F#устанавливается по умолчанию в [Visual Studio для Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), независимо от выбранной конфигурации.

После завершения установки нажмите кнопку **запустить Visual Studio**. Вы также можете открыть Visual Studio с помощью Finder в macOS.

## <a name="install-f-on-a-build-server"></a>Установка F# на сервере сборки

Если вы используете .NET Core или .NET Framework с помощью пакета SDK для .NET, необходимо просто установить пакет SDK для .NET на сервере сборки. Он содержит все необходимое.

Если вы используете .NET Framework и вы **не** используете пакет SDK для .NET, необходимо установить [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) на сервере Windows Server. В установщике выберите **.NET Desktop Build Tools**, а затем выберите компонент  **F# компилятора** в правой части меню установщика.
