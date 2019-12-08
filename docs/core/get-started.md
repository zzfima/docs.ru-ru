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
# <a name="get-started-with-net-core"></a><span data-ttu-id="46081-103">Начало работы с .NET Core</span><span class="sxs-lookup"><span data-stu-id="46081-103">Get started with .NET Core</span></span>

<span data-ttu-id="46081-104">В этой статье представлены сведения по началу работы с .NET Core.</span><span class="sxs-lookup"><span data-stu-id="46081-104">This article provides information on getting started with .NET Core.</span></span> <span data-ttu-id="46081-105">.NET Core можно установить в Windows, Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="46081-105">.NET Core can be installed on Windows, Linux, and macOS.</span></span> <span data-ttu-id="46081-106">Вы можете писать код в любом текстовом редакторе, а также создавать кроссплатформенные библиотеки и приложения.</span><span class="sxs-lookup"><span data-stu-id="46081-106">You can code in your favorite text editor and produce cross-platform libraries and applications.</span></span> 

<span data-ttu-id="46081-107">Если вы не знаете, что такое .NET Core и как это связано с другими технологиями .NET, начните с обзора [Что такое .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet).</span><span class="sxs-lookup"><span data-stu-id="46081-107">If you're unsure what .NET Core is, or how it relates to other .NET technologies, start with the [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) overview.</span></span> <span data-ttu-id="46081-108">Простыми словами, .NET Core — это кроссплатформенная реализация .NET с открытым исходным кодом.</span><span class="sxs-lookup"><span data-stu-id="46081-108">Put simply, .NET Core is an open-source, cross-platform implementation of .NET.</span></span>

## <a name="create-an-application"></a><span data-ttu-id="46081-109">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="46081-109">Create an application</span></span>

<span data-ttu-id="46081-110">Сначала скачайте и установите [пакет SDK для .NET Core](https://dotnet.microsoft.com/download) на компьютер.</span><span class="sxs-lookup"><span data-stu-id="46081-110">First, download and install the [.NET Core SDK](https://dotnet.microsoft.com/download) on your computer.</span></span>

<span data-ttu-id="46081-111">Затем откройте окно терминала, например **PowerShell**, **командную строку** или **bash**.</span><span class="sxs-lookup"><span data-stu-id="46081-111">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="46081-112">Для создания и запуска приложения C# введите следующие команды `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="46081-112">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="46081-113">Должны выводиться следующие данные:</span><span class="sxs-lookup"><span data-stu-id="46081-113">You should see the following output:</span></span>

```console
Hello World!
```

<span data-ttu-id="46081-114">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="46081-114">Congratulations!</span></span> <span data-ttu-id="46081-115">Вы создали простое приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="46081-115">You've created a simple .NET Core application.</span></span> <span data-ttu-id="46081-116">Вы также можете использовать [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio](tutorials/with-visual-studio.md) (только для Windows) или [Visual Studio для Mac](tutorials/using-on-mac-vs.md) (только для macOS), чтобы создать приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="46081-116">You can also use [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio](tutorials/with-visual-studio.md) (Windows only), or [Visual Studio for Mac](tutorials/using-on-mac-vs.md) (macOS only), to create a .NET Core application.</span></span>

## <a name="tutorials"></a><span data-ttu-id="46081-117">Учебники</span><span class="sxs-lookup"><span data-stu-id="46081-117">Tutorials</span></span>

<span data-ttu-id="46081-118">Чтобы приступить к разработке приложений .NET Core, воспользуйтесь следующими пошаговыми руководствами.</span><span class="sxs-lookup"><span data-stu-id="46081-118">You can get started developing .NET Core applications by following these step-by-step tutorials.</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[<span data-ttu-id="46081-119">Windows</span><span class="sxs-lookup"><span data-stu-id="46081-119">Windows</span></span>](#tab/windows)

- [<span data-ttu-id="46081-120">Создание приложения Hello World на C# с помощью .NET Core в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="46081-120">Build a C# "Hello World" Application with .NET Core in Visual Studio 2017.</span></span>](./tutorials/with-visual-studio.md)
- [<span data-ttu-id="46081-121">Создание библиотеки классов C# с помощью .NET Core в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="46081-121">Build a C# class library with .NET Core in Visual Studio 2017.</span></span>](./tutorials/library-with-visual-studio.md)
- [<span data-ttu-id="46081-122">Создание приложения Hello World на Visual Basic с помощью .NET Core в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="46081-122">Build a Visual Basic "Hello World" application with .NET Core in Visual Studio 2017.</span></span>](./tutorials/vb-with-visual-studio.md)
- [<span data-ttu-id="46081-123">Создание библиотеки классов с помощью Visual Basic и .NET Core в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="46081-123">Build a class library with Visual Basic and .NET Core in Visual Studio 2017.</span></span>](./tutorials/vb-library-with-visual-studio.md)  
- <span data-ttu-id="46081-124">Посмотрите видео о том, [как установить и использовать Visual Studio Code и .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/).</span><span class="sxs-lookup"><span data-stu-id="46081-124">Watch a video on [how to install and use Visual Studio Code and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/).</span></span>
- <span data-ttu-id="46081-125">Посмотрите видео о том, [как установить и использовать Visual Studio 2017 и .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/).</span><span class="sxs-lookup"><span data-stu-id="46081-125">Watch a video on [how to install and use Visual Studio 2017 and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/).</span></span>
- [<span data-ttu-id="46081-126">Начало работы с .NET Core с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="46081-126">Getting started with .NET Core using the command-line.</span></span>](tutorials/cli-create-console-app.md)

<span data-ttu-id="46081-127">Список поддерживаемых версий Windows см. в статье [Зависимости и требования для .NET Core](install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="46081-127">See the [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-windows) article for a list of the supported Windows versions.</span></span>

# <a name="linuxtablinux"></a>[<span data-ttu-id="46081-128">Linux</span><span class="sxs-lookup"><span data-stu-id="46081-128">Linux</span></span>](#tab/linux)

<span data-ttu-id="46081-129">Чтобы приступить к разработке приложения .NET Core, воспользуйтесь следующими пошаговыми руководствами:</span><span class="sxs-lookup"><span data-stu-id="46081-129">You can get started developing .NET Core application by following these step-by-step tutorials:</span></span>

- [<span data-ttu-id="46081-130">Начало работы с .NET Core с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="46081-130">Getting started with .NET Core using the command-line.</span></span>](tutorials/cli-create-console-app.md)
- <span data-ttu-id="46081-131">Посмотрите видео о [начале работы с Visual Studio Code с использованием C# и .NET Core в Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span><span class="sxs-lookup"><span data-stu-id="46081-131">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

<span data-ttu-id="46081-132">Список поддерживаемых дистрибутивов и версий Linux см. в статье [Зависимости и требования для .NET Core](install/dependencies.md?tabs=netcore30&pivots=os-linux).</span><span class="sxs-lookup"><span data-stu-id="46081-132">See the [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-linux) article for a list of the supported Linux distros and versions.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="46081-133">macOS</span><span class="sxs-lookup"><span data-stu-id="46081-133">macOS</span></span>](#tab/macos)

<span data-ttu-id="46081-134">Чтобы приступить к разработке приложения .NET Core, воспользуйтесь следующими пошаговыми руководствами:</span><span class="sxs-lookup"><span data-stu-id="46081-134">You can get started developing .NET Core application by following these step-by-step tutorials:</span></span>

- <span data-ttu-id="46081-135">Посмотрите видео о [начале работы с Visual Studio Code с использованием C# и .NET Core в macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span><span class="sxs-lookup"><span data-stu-id="46081-135">Watch a video on [Getting started with Visual Studio Code using C# and .NET Core on macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span></span>
- [<span data-ttu-id="46081-136">Начало работы с .NET Core в macOS с помощью Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="46081-136">Getting started with .NET Core on macOS, using Visual Studio Code.</span></span>](tutorials/using-on-macos.md)
- [<span data-ttu-id="46081-137">Начало работы с .NET Core с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="46081-137">Getting started with .NET Core using the command-line.</span></span>](tutorials/cli-create-console-app.md)
- [<span data-ttu-id="46081-138">Начало работы с .NET Core в macOS с помощью Visual Studio для Mac.</span><span class="sxs-lookup"><span data-stu-id="46081-138">Getting started with .NET Core on macOS using Visual Studio for Mac.</span></span>](tutorials/using-on-mac-vs.md)
- [<span data-ttu-id="46081-139">Создание полноценного решения .NET Core на базе macOS с помощью Visual Studio для Mac.</span><span class="sxs-lookup"><span data-stu-id="46081-139">Build a complete .NET Core solution on macOS using Visual Studio for Mac.</span></span>](tutorials/using-on-mac-vs-full-solution.md)

<span data-ttu-id="46081-140">Список поддерживаемых версий OS X и macOS см. в статье [Зависимости и требования для .NET Core](install/dependencies.md?tabs=netcore30&pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="46081-140">See the [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-macos) article for a list of the supported OS X / macOS versions.</span></span>

---
