---
title: 'Установка F #'
description: 'Сведения об установке F # об используемой среде.'
ms.date: 08/28/2018
ms.openlocfilehash: 909e1c07ff7f6d52db77a987639d1c749146fdca
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49120938"
---
# <a name="install-f"></a>Установка F # #

Вы можете установить F # несколькими способами, в зависимости от среды.

## <a name="install-f-with-visual-studio"></a>Установка F # с Visual Studio

Если происходит загрузка [Visual Studio](https://visualstudio.microsoft.com/) в первый раз, его вначале установит установщик Visual Studio. Установите соответствующие номера SKU из Visual Studio с помощью установщика. Если вы уже установили его, нажмите кнопку **изменить**.

Далее вы увидите список рабочих нагрузок. Выберите **ASP.NET и веб-разработка** которого будет устанавливаться, поддержка F # и поддержке .NET Core для проектов ASP.NET Core.

Затем щелкните **изменить** в нижнем правом углу.  Эта команда установит все, что вы выбрали. Затем можно открыть Visual Studio 2017 с поддержкой языка F #, щелкнув **запуска**.

## <a name="install-f-with-visual-studio-for-mac"></a>Установка F # с Visual Studio для Mac

F # по умолчанию устанавливается в [Visual Studio для Mac](https://visualstudio.microsoft.com/vs/mac/), независимо от того, какую конфигурацию вы выберите.

После завершения установки, выберите «Запустить Visual Studio». Его можно также запустить через Finder в macOS.

## <a name="install-f-with-visual-studio-code"></a>Установка F # с помощью Visual Studio Code

Необходимо иметь [репозиторий git](https://git-scm.com/download) и доступные в свой путь, чтобы сделать использование шаблонов проектов. Убедитесь, что он установлен правильно, введя `git --version` командной строки и нажмите клавишу **ввод**.

### <a name="macostabmacos"></a>[macOS](#tab/macos)

[Mono](http://www.mono-project.com) используется для [F # Interactive](../tutorials/fsharp-interactive/index.md) поддержки. Самый простой способ установить Mono в macOS — с помощью Homebrew. Просто введите следующую команду в окне терминала:

```console
brew install mono
```

Кроме того, установить [пакет SDK для .NET Core](https://www.microsoft.com/net/download).

### <a name="linuxtablinux"></a>[Linux](#tab/linux)

[Mono](https://www.mono-project.com) используется для [F # Interactive](../tutorials/fsharp-interactive/index.md) поддержки. Если вы в Debian и Ubuntu, можно использовать следующее:

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

Кроме того, установить [пакет SDK для .NET Core](https://www.microsoft.com/net/download).

### <a name="windowstabwindows"></a>[Windows](#tab/windows)

Установка [Visual Studio с поддержкой F #](#install-f-with-visual-studio). При этом будут установлены все необходимые компоненты для написания, компиляции и выполнения кода на F #.

Кроме того, установить [пакет SDK для .NET Core](https://www.microsoft.com/net/download/).

---

Необходимо будет [Visual Studio Code](https://code.visualstudio.com) установлен.

Затем щелкните значок расширения и выполните поиск «Ionide»:

Только подключаемый модуль, необходимый для поддержки F # в Visual Studio Code является [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp). Тем не менее, можно также установить [Ionide ИМИТАЦИИ](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) для получения [ИМИТИРОВАТЬ](https://fsharp.github.io/FAKE/) поддержки и [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) для получения [Paket](https://fsprojects.github.io/Paket/) поддержки. ПОДДЕЛКИ и Paket средства Дополнительные сообщества F # для создания проектов и управление зависимостями, соответственно.
