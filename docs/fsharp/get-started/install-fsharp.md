---
title: Установка F#
description: Узнайте, как установить F# на основе среды.
ms.date: 09/05/2019
ms.openlocfilehash: 592a4c7763266cee68809fca84f9604d7e96b8f1
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204878"
---
# <a name="install-f"></a>Установка F\#

В зависимости от F# среды можно установить несколькими способами.

## <a name="install-f-with-visual-studio"></a>Установка F# с помощью Visual Studio

Если вы скачиваете [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) впервые, сначала будет установлена программа Visual Studio Installer. Установите соответствующий SKU Visual Studio из установщика. Если вы уже установили его, нажмите кнопку **изменить**.

Далее вы увидите список рабочих нагрузок. Выберите **ASP.NET и веб-разработку** , которые F# будут устанавливать поддержку и поддержку .net Core для проектов ASP.NET Core.

Затем в нижней правой части щелкните **изменить** .  Будет выполнена установка всех выбранных элементов. Затем можно открыть Visual Studio 2017 с F# поддержкой языка, нажав кнопку **запустить**.

## <a name="install-f-with-visual-studio-code"></a>Установка F# с помощью Visual Studio Code

Сначала убедитесь, что на вашем пути установлен и доступен [Git](https://git-scm.com/download) . Чтобы проверить правильность установки, введите `git --version` в командной строке и нажмите клавишу **Ввод**.

Затем установите [пакет SDK для .NET Core](https://dotnet.microsoft.com/download).

После этого потребуется [Visual Studio Code](https://code.visualstudio.com) установить.

Затем щелкните значок расширения и выполните поиск по запросу "Ionide":

Единственным подключаемым модулем F# , необходимым для поддержки в Visual Studio Code, является [Ionide-FSharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp). Однако можно также установить [Ionide-ПОДдельные](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) , чтобы получить [поддельную](https://fake.build/) поддержку и [Ionide-пакет](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) , чтобы получить поддержку [пакет](https://fsprojects.github.io/Paket/) . Поддельные и пакет — F# это дополнительные инструменты сообщества для создания проектов и управления зависимостями соответственно.

## <a name="install-f-with-visual-studio-for-mac"></a>Установка F# с помощью Visual Studio для Mac

F#устанавливается по умолчанию в [Visual Studio для Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), независимо от выбранной конфигурации.

После завершения установки нажмите кнопку "запустить Visual Studio". Его также можно запустить с помощью средства поиска в macOS.

## <a name="install-f-on-a-build-server"></a>Установка F# на сервере сборки

Если вы используете .NET Core или .NET Framework с помощью пакета SDK для .NET, необходимо просто установить пакет SDK для .NET на сервере сборки. Он содержит все необходимое.

Если вы используете .NET Framework и вы **не** используете пакет SDK для .NET, необходимо установить [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) на сервере Windows Server. В установщике выберите **.NET Desktop Build Tools** , а затем выберите компонент  **F# компилятора** в правой части меню установщика.
