---
title: Создание пакета NuGet с помощью кроссплатформенных средств
description: Узнайте, как создать пакет NuGet с помощью команды dotnet pack.
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: b85f6d53787cb513ae4c1e8147a066188b0e56c6
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-create-a-nuget-package-with-cross-platform-tools"></a><span data-ttu-id="90281-103">Создание пакета NuGet с помощью кроссплатформенных средств</span><span class="sxs-lookup"><span data-stu-id="90281-103">How to Create a NuGet Package with Cross Platform Tools</span></span>

> [!NOTE]
> <span data-ttu-id="90281-104">Ниже приведены примеры команд командной строки для Unix.</span><span class="sxs-lookup"><span data-stu-id="90281-104">The following shows command-line samples using Unix.</span></span>  <span data-ttu-id="90281-105">Показанная здесь команда `dotnet pack` точно так же работает в Windows.</span><span class="sxs-lookup"><span data-stu-id="90281-105">The `dotnet pack` command as shown here works the same way on Windows.</span></span>

<span data-ttu-id="90281-106">Для .NET Core 1.0 библиотеки должны распространяться в виде пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="90281-106">For .NET Core 1.0, libraries are expected to be distributed as NuGet packages.</span></span>  <span data-ttu-id="90281-107">Именно так распространяются и используются все библиотеки .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="90281-107">This is in fact how all of the .NET Standard libraries are distributed and consumed.</span></span>  <span data-ttu-id="90281-108">Проще всего это делать с помощью команды `dotnet pack`.</span><span class="sxs-lookup"><span data-stu-id="90281-108">This is most easily done with the `dotnet pack` command.</span></span>

<span data-ttu-id="90281-109">Представим, что вы только что создали полезную библиотеку, которую хотите распространить через NuGet.</span><span class="sxs-lookup"><span data-stu-id="90281-109">Imagine that you just wrote an awesome new library that you would like to distribute over NuGet.</span></span>  <span data-ttu-id="90281-110">Для этого можно создать пакет NuGet с помощью кроссплатформенных средств.</span><span class="sxs-lookup"><span data-stu-id="90281-110">You can create a NuGet package with cross platform tools to do exactly that!</span></span>  <span data-ttu-id="90281-111">В приведенном ниже примере используется библиотека **SuperAwesomeLibrary**, предназначенная для `netstandard1.0`.</span><span class="sxs-lookup"><span data-stu-id="90281-111">The following example assumes a library called **SuperAwesomeLibrary** which targets `netstandard1.0`.</span></span>

<span data-ttu-id="90281-112">Если у вас есть транзитивные зависимости, то есть проекты, которые зависят от других проектов, необходимо обязательно восстановить пакеты для всего решения с помощью команды `dotnet restore`, прежде чем создавать пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="90281-112">If you have transitive dependencies; that is, a project which depends on another project, you'll need to make sure to restore packages for your entire solution with the `dotnet restore` command before creating a NuGet package.</span></span>  <span data-ttu-id="90281-113">Если не сделать этого, команда `dotnet pack` будет работать неправильно.</span><span class="sxs-lookup"><span data-stu-id="90281-113">Failing to do so will result in the `dotnet pack` command to not work properly.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]


<span data-ttu-id="90281-114">Восстановив пакеты, можно перейти в каталог, где находится библиотека:</span><span class="sxs-lookup"><span data-stu-id="90281-114">After ensuring packages are restored, you can navigate to the directory where a library lives:</span></span>

`$ cd src/SuperAwesomeLibrary`

<span data-ttu-id="90281-115">Затем нужно выполнить всего лишь одну команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="90281-115">Then it's just a single command from the command line:</span></span>
    
`$ dotnet pack`

<span data-ttu-id="90281-116">Папка `/bin/Debug` теперь будет выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="90281-116">Your `/bin/Debug` folder will now look like this:</span></span>

```
$ ls bin/Debug

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="90281-117">Обратите внимание на то, что при этом создается пакет, который можно отлаживать.</span><span class="sxs-lookup"><span data-stu-id="90281-117">Note that this will produce a package which is capable of being debugged.</span></span>  <span data-ttu-id="90281-118">Если вы хотите создать пакет NuGet с двоичными файлами выпуска, вам нужно просто добавить параметр `-c`/`--configuration` и использовать `release` в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="90281-118">If you want to build a NuGet package with release binaries, all you need to do is add the `-c`/`--configuration` switch and use `release` as the argument.</span></span>

`$ dotnet pack --configuration release`

<span data-ttu-id="90281-119">В папке `/bin` теперь будет папка `release`, содержащая пакет NuGet с двоичными файлами выпуска:</span><span class="sxs-lookup"><span data-stu-id="90281-119">Your `/bin` folder will now have a `release` folder containing your NuGet package with release binaries:</span></span>

```
$ ls bin/release

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="90281-120">теперь у вас есть все необходимые файлы для публикации пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="90281-120">And now you have the necessary files to publish a NuGet package!</span></span>

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a><span data-ttu-id="90281-121">Не путайте команду `dotnet pack` с командой `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="90281-121">Don't confuse `dotnet pack` with `dotnet publish`</span></span>

<span data-ttu-id="90281-122">Важно заметить, что команда `dotnet publish` в этом процессе не применяется.</span><span class="sxs-lookup"><span data-stu-id="90281-122">It is important to note that at no point is the `dotnet publish` command involved.</span></span>  <span data-ttu-id="90281-123">Команда `dotnet publish` предназначена для развертывания приложений со всеми зависимостями в одном пакете, а не для создания пакета NuGet, который будет распространяться и использоваться посредством NuGet.</span><span class="sxs-lookup"><span data-stu-id="90281-123">The `dotnet publish` command is for deploying applications with all of their dependencies in the same bundle -  not for generating a NuGet package to be distributed and consumed via NuGet.</span></span>
