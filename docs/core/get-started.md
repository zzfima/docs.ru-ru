---
title: Начало работы с .NET Core
description: Ресурсы, посвященные созданию приложений .NET Core в Windows, Linux и Mac OS.
author: thraka
ms.author: adegeo
ms.date: 06/27/2018
ms.openlocfilehash: 2ec7f57250db8779552305b2ee69cbcf1db55d0c
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977182"
---
# <a name="get-started-with-net-core"></a>Начало работы с .NET Core

В этой статье представлены сведения по началу работы с .NET Core. .NET Core можно установить в Windows, Linux и macOS. Вы можете писать код в любом текстовом редакторе, а также создавать кроссплатформенные библиотеки и приложения. 

Если вы не знаете, что такое .NET Core и как это связано с другими технологиями .NET, начните с обзора [Что такое .NET](https://www.microsoft.com/net/learn/dotnet/what-is-dotnet). Простыми словами, .NET Core — это кроссплатформенная реализация .NET с открытым исходным кодом.

## <a name="create-an-application"></a>Создание приложения

Сначала скачайте и установите [пакет SDK для .NET Core](https://www.microsoft.com/net/download/) на компьютер.

Затем откройте окно терминала, например **PowerShell**, **командную строку** или **bash**. Для создания и запуска приложения C# введите следующие команды `dotnet`.

```console
dotnet new console --output sample1
dotnet run --project sample1
```

Должны выводиться следующие данные:

```console
Hello World!
```

Поздравляем! Вы создали простое приложение .NET Core. Вы также можете использовать [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio 2017](tutorials/with-visual-studio.md) (только для Windows) или [Visual Studio для Mac](tutorials/using-on-mac-vs.md) (только для macOS), чтобы создать приложение .NET Core.

## <a name="tutorials"></a>Учебники

Чтобы приступить к разработке приложений .NET Core, воспользуйтесь следующими пошаговыми руководствами.

# <a name="windowstabwindows"></a>[Windows](#tab/windows)

* [Создание приложения Hello World на C# с помощью .NET Core в Visual Studio 2017.](./tutorials/with-visual-studio.md)

* [Создание библиотеки классов C# с помощью .NET Core в Visual Studio 2017.](./tutorials/library-with-visual-studio.md)

* [Создание приложения Hello World на Visual Basic с помощью .NET Core в Visual Studio 2017.](./tutorials/vb-with-visual-studio.md)

* [Создание библиотеки классов с помощью Visual Basic и .NET Core в Visual Studio 2017.](./tutorials/vb-library-with-visual-studio.md)  

* Посмотрите видео о том, [как установить и использовать Visual Studio Code и .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/).

* Посмотрите видео о том, [как установить и использовать Visual Studio 2017 и .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/).

* [Начало работы с .NET Core с помощью командной строки.](tutorials/using-with-xplat-cli.md)

Список поддерживаемых версий Windows см. в статье [Предварительные требования для разработки в Windows](windows-prerequisites.md).

# <a name="linuxtablinux"></a>[Linux](#tab/linux)

Чтобы приступить к разработке приложения .NET Core, воспользуйтесь следующими пошаговыми руководствами.

* [Начало работы с .NET Core с помощью командной строки.](tutorials/using-with-xplat-cli.md)

* Посмотрите видео о [начале работы с Visual Studio Code с использованием C# и .NET Core в Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).

Список поддерживаемых версий и дистрибутивов Linux см. в статье [Необходимые компоненты для .NET Core в Linux](linux-prerequisites.md).

# <a name="macostabmacos"></a>[macOS](#tab/macos)

Чтобы приступить к разработке приложения .NET Core, воспользуйтесь следующими пошаговыми руководствами.

* Посмотрите видео о [начале работы с Visual Studio Code с использованием C# и .NET Core в macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).

* [Начало работы с .NET Core в macOS с помощью Visual Studio Code.](tutorials/using-on-macos.md)

* [Начало работы с .NET Core с помощью командной строки.](tutorials/using-with-xplat-cli.md)

* [Начало работы с .NET Core в macOS с помощью Visual Studio для Mac.](tutorials/using-on-mac-vs.md)

* [Создание полноценного решения .NET Core на базе macOS с помощью Visual Studio для Mac.](tutorials/using-on-mac-vs-full-solution.md)

Список поддерживаемых версий OS X и macOS см. в статье [Предварительные требования для разработки в macOS](macos-prerequisites.md).

---
