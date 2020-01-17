---
title: Начало работы с .NET Core
description: Ресурсы, посвященные созданию приложений .NET Core в Windows, Linux и macOS.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 0968d9db1dbfbdc8c586328ee8e02315f17950b9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714395"
---
# <a name="get-started-with-net-core"></a><span data-ttu-id="8eddd-103">Начало работы с .NET Core</span><span class="sxs-lookup"><span data-stu-id="8eddd-103">Get started with .NET Core</span></span>

<span data-ttu-id="8eddd-104">В этой статье представлены сведения по началу работы с .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8eddd-104">This article provides information on getting started with .NET Core.</span></span> <span data-ttu-id="8eddd-105">.NET Core можно установить в Windows, Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="8eddd-105">.NET Core can be installed on Windows, Linux, and macOS.</span></span> <span data-ttu-id="8eddd-106">Вы можете писать код в любом текстовом редакторе, а также создавать кроссплатформенные библиотеки и приложения.</span><span class="sxs-lookup"><span data-stu-id="8eddd-106">You can code in your favorite text editor and produce cross-platform libraries and applications.</span></span>

<span data-ttu-id="8eddd-107">Если вы не знаете, что такое .NET Core и как это связано с другими технологиями .NET, начните с обзора [Что такое .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet).</span><span class="sxs-lookup"><span data-stu-id="8eddd-107">If you're unsure what .NET Core is, or how it relates to other .NET technologies, start with the [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) overview.</span></span> <span data-ttu-id="8eddd-108">Простыми словами, .NET Core — это кроссплатформенная реализация .NET с открытым исходным кодом.</span><span class="sxs-lookup"><span data-stu-id="8eddd-108">Put simply, .NET Core is an open-source, cross-platform implementation of .NET.</span></span>

## <a name="create-an-application"></a><span data-ttu-id="8eddd-109">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="8eddd-109">Create an application</span></span>

<span data-ttu-id="8eddd-110">Сначала скачайте и установите [пакет SDK для .NET Core](https://dotnet.microsoft.com/download) на компьютер.</span><span class="sxs-lookup"><span data-stu-id="8eddd-110">First, download and install the [.NET Core SDK](https://dotnet.microsoft.com/download) on your computer.</span></span>

<span data-ttu-id="8eddd-111">Затем откройте окно терминала, например **PowerShell**, **командную строку** или **bash**.</span><span class="sxs-lookup"><span data-stu-id="8eddd-111">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="8eddd-112">Для создания и запуска приложения C# введите следующие команды `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="8eddd-112">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="8eddd-113">Должны выводиться следующие данные:</span><span class="sxs-lookup"><span data-stu-id="8eddd-113">You should see the following output:</span></span>

```console
Hello World!
```

<span data-ttu-id="8eddd-114">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="8eddd-114">Congratulations!</span></span> <span data-ttu-id="8eddd-115">Вы создали простое приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8eddd-115">You've created a simple .NET Core application.</span></span> <span data-ttu-id="8eddd-116">Вы также можете использовать [Visual Studio Code](./tutorials/with-visual-studio-code.md), [Visual Studio](./tutorials/with-visual-studio.md) (только для Windows) или [Visual Studio для Mac](./tutorials/using-on-mac-vs.md) (только для macOS), чтобы создать приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8eddd-116">You can also use [Visual Studio Code](./tutorials/with-visual-studio-code.md), [Visual Studio](./tutorials/with-visual-studio.md) (Windows only), or [Visual Studio for Mac](./tutorials/using-on-mac-vs.md) (macOS only), to create a .NET Core application.</span></span>

## <a name="tutorials"></a><span data-ttu-id="8eddd-117">Учебники</span><span class="sxs-lookup"><span data-stu-id="8eddd-117">Tutorials</span></span>

<span data-ttu-id="8eddd-118">Начало работы с разработкой приложений .NET Core, используя следующие пошаговые руководства.</span><span class="sxs-lookup"><span data-stu-id="8eddd-118">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[<span data-ttu-id="8eddd-119">Windows</span><span class="sxs-lookup"><span data-stu-id="8eddd-119">Windows</span></span>](#tab/windows)

- [<span data-ttu-id="8eddd-120">Создание первого консольного приложения .NET Core в Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="8eddd-120">Create your first .NET Core console application in Visual Studio 2019</span></span>](./tutorials/with-visual-studio.md)
- [<span data-ttu-id="8eddd-121">Создание библиотеки классов с помощью .NET Standard в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8eddd-121">Build a class library with .NET Standard in Visual Studio</span></span>](./tutorials/library-with-visual-studio.md)
- [<span data-ttu-id="8eddd-122">Начало работы с .NET Core с использованием .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="8eddd-122">Get started with .NET Core using the .NET Core CLI</span></span>](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| <span data-ttu-id="8eddd-123">![значок камеры для видеоролика](./media/video-icon.png "Посмотрите видео")</span><span class="sxs-lookup"><span data-stu-id="8eddd-123">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="8eddd-124">Посмотрите видео о том, [как установить и использовать Visual Studio Code и .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/) на канале Channel 9.</span><span class="sxs-lookup"><span data-stu-id="8eddd-124">Watch the [how to install and use Visual Studio Code and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/) video on Channel 9.</span></span> |
| <span data-ttu-id="8eddd-125">![значок камеры для видеоролика](./media/video-icon.png "Посмотрите видео")</span><span class="sxs-lookup"><span data-stu-id="8eddd-125">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="8eddd-126">Просмотрите видео о [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) на YouTube.</span><span class="sxs-lookup"><span data-stu-id="8eddd-126">Watch the [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) videos on YouTube.</span></span> |

<span data-ttu-id="8eddd-127">Список поддерживаемых версий Windows см. в статье [Зависимости и требования для .NET Core](install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="8eddd-127">See the [.NET Core dependencies and requirements](install/dependencies.md?pivots=os-windows) article for a list of the supported Windows versions.</span></span>

# <a name="linuxtablinux"></a>[<span data-ttu-id="8eddd-128">Linux</span><span class="sxs-lookup"><span data-stu-id="8eddd-128">Linux</span></span>](#tab/linux)

<span data-ttu-id="8eddd-129">Начало работы с разработкой приложений .NET Core, используя следующие пошаговые руководства.</span><span class="sxs-lookup"><span data-stu-id="8eddd-129">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

- [<span data-ttu-id="8eddd-130">Начало работы с .NET Core с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="8eddd-130">Get started with .NET Core using the command line</span></span>](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| <span data-ttu-id="8eddd-131">![значок камеры для видеоролика](./media/video-icon.png "Посмотрите видео")</span><span class="sxs-lookup"><span data-stu-id="8eddd-131">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="8eddd-132">Посмотрите видео о [начале работы с Visual Studio Code с использованием C# и .NET Core в Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span><span class="sxs-lookup"><span data-stu-id="8eddd-132">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span> |

<span data-ttu-id="8eddd-133">Список поддерживаемых дистрибутивов и версий Linux см. в статье [Зависимости и требования для .NET Core](install/dependencies.md?pivots=os-linux).</span><span class="sxs-lookup"><span data-stu-id="8eddd-133">See the [.NET Core dependencies and requirements](install/dependencies.md?pivots=os-linux) article for a list of the supported Linux distros and versions.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="8eddd-134">macOS</span><span class="sxs-lookup"><span data-stu-id="8eddd-134">macOS</span></span>](#tab/macos)

<span data-ttu-id="8eddd-135">Начало работы с разработкой приложений .NET Core, используя следующие пошаговые руководства.</span><span class="sxs-lookup"><span data-stu-id="8eddd-135">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

- [<span data-ttu-id="8eddd-136">Начало работы с .NET Core в macOS с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8eddd-136">Get started with .NET Core on macOS using Visual Studio Code</span></span>](./tutorials/using-on-macos.md)
- [<span data-ttu-id="8eddd-137">Начало работы с .NET Core с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="8eddd-137">Get started with .NET Core using the command-line</span></span>](./tutorials/cli-create-console-app.md)
- [<span data-ttu-id="8eddd-138">Начало работы с .NET Core в macOS с помощью Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="8eddd-138">Get started with .NET Core on macOS using Visual Studio for Mac</span></span>](./tutorials/using-on-mac-vs.md)
- [<span data-ttu-id="8eddd-139">Создание полноценного решения .NET Core на базе macOS с помощью Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="8eddd-139">Build a complete .NET Core solution on macOS using Visual Studio for Mac</span></span>](./tutorials/using-on-mac-vs-full-solution.md)

|   |   |
|---|---|
| <span data-ttu-id="8eddd-140">![значок камеры для видеоролика](media/video-icon.png "Посмотрите видео")</span><span class="sxs-lookup"><span data-stu-id="8eddd-140">![movie camera icon for video](media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="8eddd-141">Посмотрите видео о [начале работы с Visual Studio Code с использованием C# и .NET Core в macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span><span class="sxs-lookup"><span data-stu-id="8eddd-141">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span></span> |

<span data-ttu-id="8eddd-142">Список поддерживаемых версий OS X и macOS см. в статье [Зависимости и требования для .NET Core](install/dependencies.md?pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="8eddd-142">See the [.NET Core dependencies and requirements](install/dependencies.md?pivots=os-macos) article for a list of the supported OS X / macOS versions.</span></span>

---
