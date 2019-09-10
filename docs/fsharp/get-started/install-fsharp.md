---
title: Установка F#
description: Узнайте, как установить F# на основе среды.
ms.date: 09/05/2019
ms.openlocfilehash: dffa30eac0bdb59c85a66dca6cafd62b25daa572
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855802"
---
# <a name="install-f"></a>Установка F\#

В зависимости от F# среды можно установить несколькими способами.

## <a name="install-f-with-visual-studio"></a>Установка F# с помощью Visual Studio

Если вы скачиваете [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) впервые, сначала будет установлена программа Visual Studio Installer. Установите соответствующий SKU Visual Studio из установщика. Если вы уже установили его, нажмите кнопку **изменить**.

Далее вы увидите список рабочих нагрузок. Выберите **ASP.NET и веб-разработку** , которые F# будут устанавливать поддержку и поддержку .net Core для проектов ASP.NET Core.

Затем в нижней правой части щелкните **изменить** .  Будет выполнена установка всех выбранных элементов. Затем можно открыть Visual Studio 2017 с F# поддержкой языка, нажав кнопку **запустить**.

## <a name="install-f-with-visual-studio-for-mac"></a>Установка F# с помощью Visual Studio для Mac

F#устанавливается по умолчанию в [Visual Studio для Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), независимо от выбранной конфигурации.

После завершения установки нажмите кнопку "запустить Visual Studio". Его также можно запустить с помощью средства поиска в macOS.

## <a name="install-f-with-visual-studio-code"></a>Установка F# с помощью Visual Studio Code

Необходимо установить и сделать [Git](https://git-scm.com/download) доступным на пути, чтобы использовать шаблоны проектов. Чтобы проверить правильность установки, введите `git --version` в командной строке и нажмите клавишу **Ввод**.

### <a name="macostabmacos"></a>[macOS](#tab/macos)

[Mono](https://www.mono-project.com) используется для [ F# интерактивной](../tutorials/fsharp-interactive/index.md) поддержки. Самый простой способ установить Mono на macOS — через Homebrew. Просто введите следующий текст в терминал:

```console
brew install mono
```

Также установите [пакет SDK для .NET Core](https://dotnet.microsoft.com/download).

### <a name="linuxtablinux"></a>[Linux](#tab/linux)

[Mono](https://www.mono-project.com) используется для [ F# интерактивной](../tutorials/fsharp-interactive/index.md) поддержки. Если вы используете Debian или Ubuntu, вы можете использовать следующую команду:

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

Также установите [пакет SDK для .NET Core](https://dotnet.microsoft.com/download).

### <a name="windowstabwindows"></a>[Windows](#tab/windows)

Установите [Visual Studio с F# поддержкой](#install-f-with-visual-studio). При этом устанавливаются все необходимые компоненты для записи, компиляции и выполнения F# кода.

Также установите [пакет SDK для .NET Core](https://dotnet.microsoft.com/download).

---

После этого потребуется [Visual Studio Code](https://code.visualstudio.com) установить.

Затем щелкните значок расширения и выполните поиск по запросу "Ionide":

Единственным подключаемым модулем F# , необходимым для поддержки в Visual Studio Code, является [Ionide-FSharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp). Однако можно также установить [Ionide-ПОДдельные](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) , чтобы получить [поддельную](https://fsharp.github.io/FAKE/) поддержку и [Ionide-пакет](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) , чтобы получить поддержку [пакет](https://fsprojects.github.io/Paket/) . Поддельные и пакет — F# это дополнительные инструменты сообщества для создания проектов и управления зависимостями соответственно.

## <a name="install-f-on-a-build-server"></a>Установка F# на сервере сборки

Если вы используете .NET Core или .NET Framework с помощью пакета SDK для .NET, необходимо просто установить пакет SDK для .NET на сервере сборки. Он содержит все необходимое.

Если вы используете .NET Framework и вы **не** используете пакет SDK для .NET, необходимо установить [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) на сервере Windows Server. В установщике выберите **.NET Desktop Build Tools** , а затем выберите компонент  **F# компилятора** в правой части меню установщика.
