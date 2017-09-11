---
title: "Создание пакета NuGet с помощью кроссплатформенных средств"
description: "Узнайте, как создать пакет NuGet с помощью команды dotnet pack."
keywords: .NET, .NET Core, NuGet
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 2f0415c1-110b-433d-87c1-ae3d543a8844
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e5c762de0a14407c92c9752edc9619caa07d500
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="how-to-create-a-nuget-package-with-cross-platform-tools"></a><span data-ttu-id="7bdf8-104">Создание пакета NuGet с помощью кроссплатформенных средств</span><span class="sxs-lookup"><span data-stu-id="7bdf8-104">How to Create a NuGet Package with Cross Platform Tools</span></span>

> [!NOTE]
> <span data-ttu-id="7bdf8-105">Ниже приведены примеры команд командной строки для Unix.</span><span class="sxs-lookup"><span data-stu-id="7bdf8-105">The following shows command-line samples using Unix.</span></span>  <span data-ttu-id="7bdf8-106">Показанная здесь команда `dotnet pack` точно так же работает в Windows.</span><span class="sxs-lookup"><span data-stu-id="7bdf8-106">The `dotnet pack` command as shown here works the same way on Windows.</span></span>

<span data-ttu-id="7bdf8-107">Для .NET Core 1.0 библиотеки должны распространяться в виде пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="7bdf8-107">For .NET Core 1.0, libraries are expected to be distributed as NuGet packages.</span></span>  <span data-ttu-id="7bdf8-108">Именно так распространяются и используются все библиотеки .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="7bdf8-108">This is in fact how all of the .NET Standard libraries are distributed and consumed.</span></span>  <span data-ttu-id="7bdf8-109">Проще всего это делать с помощью команды `dotnet pack`.</span><span class="sxs-lookup"><span data-stu-id="7bdf8-109">This is most easily done with the `dotnet pack` command.</span></span>

<span data-ttu-id="7bdf8-110">Представим, что вы только что создали полезную библиотеку, которую хотите распространить через NuGet.</span><span class="sxs-lookup"><span data-stu-id="7bdf8-110">Imagine that you just wrote an awesome new library that you would like to distribute over NuGet.</span></span>  <span data-ttu-id="7bdf8-111">Для этого можно создать пакет NuGet с помощью кроссплатформенных средств.</span><span class="sxs-lookup"><span data-stu-id="7bdf8-111">You can create a NuGet package with cross platform tools to do exactly that!</span></span>  <span data-ttu-id="7bdf8-112">В приведенном ниже примере используется библиотека **SuperAwesomeLibrary**, предназначенная для `netstandard1.0`.</span><span class="sxs-lookup"><span data-stu-id="7bdf8-112">The following example assumes a library called **SuperAwesomeLibrary** which targets `netstandard1.0`.</span></span>

<span data-ttu-id="7bdf8-113">Если у вас есть транзитивные зависимости, то есть проекты, которые зависят от других проектов, необходимо обязательно восстановить пакеты для всего решения с помощью команды `dotnet restore`, прежде чем создавать пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="7bdf8-113">If you have transitive dependencies; that is, a project which depends on another project, you'll need to make sure to restore packages for your entire solution with the `dotnet restore` command before creating a NuGet package.</span></span>  <span data-ttu-id="7bdf8-114">Если не сделать этого, команда `dotnet pack` будет работать неправильно.</span><span class="sxs-lookup"><span data-stu-id="7bdf8-114">Failing to do so will result in the `dotnet pack` command to not work properly.</span></span>

<span data-ttu-id="7bdf8-115">Восстановив пакеты, можно перейти в каталог, где находится библиотека:</span><span class="sxs-lookup"><span data-stu-id="7bdf8-115">After ensuring packages are restored, you can navigate to the directory where a library lives:</span></span>

`$ cd src/SuperAwesomeLibrary`

<span data-ttu-id="7bdf8-116">Затем нужно выполнить всего лишь одну команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="7bdf8-116">Then it's just a single command from the command line:</span></span>
    
`$ dotnet pack`

<span data-ttu-id="7bdf8-117">Папка `/bin/Debug` теперь будет выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="7bdf8-117">Your `/bin/Debug` folder will now look like this:</span></span>

```
$ ls bin/Debug

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="7bdf8-118">Обратите внимание на то, что при этом создается пакет, который можно отлаживать.</span><span class="sxs-lookup"><span data-stu-id="7bdf8-118">Note that this will produce a package which is capable of being debugged.</span></span>  <span data-ttu-id="7bdf8-119">Если вы хотите создать пакет NuGet с двоичными файлами выпуска, вам нужно просто добавить параметр `-c`/`--configuration` и использовать `release` в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="7bdf8-119">If you want to build a NuGet package with release binaries, all you need to do is add the `-c`/`--configuration` switch and use `release` as the argument.</span></span>

`$ dotnet pack --configuration release`

<span data-ttu-id="7bdf8-120">В папке `/bin` теперь будет папка `release`, содержащая пакет NuGet с двоичными файлами выпуска:</span><span class="sxs-lookup"><span data-stu-id="7bdf8-120">Your `/bin` folder will now have a `release` folder containing your NuGet package with release binaries:</span></span>

```
$ ls bin/release

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="7bdf8-121">теперь у вас есть все необходимые файлы для публикации пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="7bdf8-121">And now you have the necessary files to publish a NuGet package!</span></span>

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a><span data-ttu-id="7bdf8-122">Не путайте команду `dotnet pack` с командой `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="7bdf8-122">Don't confuse `dotnet pack` with `dotnet publish`</span></span>

<span data-ttu-id="7bdf8-123">Важно заметить, что команда `dotnet publish` в этом процессе не применяется.</span><span class="sxs-lookup"><span data-stu-id="7bdf8-123">It is important to note that at no point is the `dotnet publish` command involved.</span></span>  <span data-ttu-id="7bdf8-124">Команда `dotnet publish` предназначена для развертывания приложений со всеми зависимостями в одном пакете, а не для создания пакета NuGet, который будет распространяться и использоваться посредством NuGet.</span><span class="sxs-lookup"><span data-stu-id="7bdf8-124">The `dotnet publish` command is for deploying applications with all of their dependencies in the same bundle -  not for generating a NuGet package to be distributed and consumed via NuGet.</span></span>

