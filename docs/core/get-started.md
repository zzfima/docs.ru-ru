---
title: Начало работы с .NET Core
description: Ресурсы, посвященные созданию приложений .NET Core в Windows, Linux и Mac OS.
author: thraka
ms.author: adegeo
ms.date: 09/19/2019
ms.openlocfilehash: 89db6d79336c01315983133d9041904d88cba301
ms.sourcegitcommit: 68a4b28242da50e1d25aab597c632767713a6f81
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/06/2019
ms.locfileid: "74884258"
---
# <a name="get-started-with-net-core"></a>Начало работы с .NET Core

В этой статье представлены сведения по началу работы с .NET Core. .NET Core можно установить в Windows, Linux и macOS. Вы можете писать код в любом текстовом редакторе, а также создавать кроссплатформенные библиотеки и приложения. 

Если вы не знаете, что такое .NET Core и как это связано с другими технологиями .NET, начните с обзора [Что такое .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet). Простыми словами, .NET Core — это кроссплатформенная реализация .NET с открытым исходным кодом.

## <a name="create-an-application"></a>Создание приложения

Сначала скачайте и установите [пакет SDK для .NET Core](https://dotnet.microsoft.com/download) на компьютер.

Затем откройте окно терминала, например **PowerShell**, **командную строку** или **bash**. Для создания и запуска приложения C# введите следующие команды `dotnet`:

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

Должны выводиться следующие данные:

```console
Hello World!
```

Поздравляем! Вы создали простое приложение .NET Core. Вы также можете использовать [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio](tutorials/with-visual-studio.md) (только для Windows) или [Visual Studio для Mac](tutorials/using-on-mac-vs.md) (только для macOS), чтобы создать приложение .NET Core.

## <a name="tutorials"></a>Учебники

Чтобы приступить к разработке приложений .NET Core, воспользуйтесь следующими пошаговыми руководствами.

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[Windows](#tab/windows)

- [Создание приложения Hello World на C# с помощью .NET Core в Visual Studio 2017.](./tutorials/with-visual-studio.md)
- [Создание библиотеки классов C# с помощью .NET Core в Visual Studio 2017.](./tutorials/library-with-visual-studio.md)
- [Создание приложения Hello World на Visual Basic с помощью .NET Core в Visual Studio 2017.](./tutorials/vb-with-visual-studio.md)
- [Создание библиотеки классов с помощью Visual Basic и .NET Core в Visual Studio 2017.](./tutorials/vb-library-with-visual-studio.md)  
- Посмотрите видео о том, [как установить и использовать Visual Studio Code и .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/).
- Посмотрите видео о том, [как установить и использовать Visual Studio 2017 и .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/).
- [Начало работы с .NET Core с помощью командной строки.](tutorials/cli-create-console-app.md)

Список поддерживаемых версий Windows см. в статье [Зависимости и требования для .NET Core](install/dependencies.md?tabs=netcore30&pivots=os-windows).

# <a name="linuxtablinux"></a>[Linux](#tab/linux)

Чтобы приступить к разработке приложения .NET Core, воспользуйтесь следующими пошаговыми руководствами:

- [Начало работы с .NET Core с помощью командной строки.](tutorials/cli-create-console-app.md)
- Посмотрите видео о [начале работы с Visual Studio Code с использованием C# и .NET Core в Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).

Список поддерживаемых дистрибутивов и версий Linux см. в статье [Зависимости и требования для .NET Core](install/dependencies.md?tabs=netcore30&pivots=os-linux).

# <a name="macostabmacos"></a>[macOS](#tab/macos)

Чтобы приступить к разработке приложения .NET Core, воспользуйтесь следующими пошаговыми руководствами:

- Посмотрите видео о [начале работы с Visual Studio Code с использованием C# и .NET Core в macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).
- [Начало работы с .NET Core в macOS с помощью Visual Studio Code.](tutorials/using-on-macos.md)
- [Начало работы с .NET Core с помощью командной строки.](tutorials/cli-create-console-app.md)
- [Начало работы с .NET Core в macOS с помощью Visual Studio для Mac.](tutorials/using-on-mac-vs.md)
- [Создание полноценного решения .NET Core на базе macOS с помощью Visual Studio для Mac.](tutorials/using-on-mac-vs-full-solution.md)

Список поддерживаемых версий OS X и macOS см. в статье [Зависимости и требования для .NET Core](install/dependencies.md?tabs=netcore30&pivots=os-macos).

---
