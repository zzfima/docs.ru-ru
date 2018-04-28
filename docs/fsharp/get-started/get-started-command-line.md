---
title: 'Начало работы с F # с помощью средства командной строки'
description: 'Сведения о создании простого многопроектное решение на F # с помощью .NET Core CLI в любой операционной системе (Windows, macOs или Linux).'
author: cartermp
ms.author: phcart
ms.date: 03/26/2018
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 767385be605d863644db563a2e86a41ca80527c4
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="8c18a-103">Начало работы с F # с .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="8c18a-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="8c18a-104">В этой статье рассказывается, как вы можете начать работу с F # в любой операционной системе (Windows, macOS или Linux) с .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="8c18a-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="8c18a-105">Он проходит построение многопроектное решение с библиотекой класса, вызываемого консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="8c18a-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8c18a-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="8c18a-106">Prerequisites</span></span>

<span data-ttu-id="8c18a-107">Чтобы начать, необходимо установить [.NET Core SDK 1.0 или более поздней версии](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="8c18a-107">To begin, you must install the [.NET Core SDK 1.0 or later](https://www.microsoft.com/net/download/).</span></span> <span data-ttu-id="8c18a-108">Нет необходимости удалить предыдущую версию пакета SDK для .NET Core, как он поддерживает side-by-side установок.</span><span class="sxs-lookup"><span data-stu-id="8c18a-108">There is no need to uninstall a previous version of the .NET Core SDK, as it supports side-by-side installations.</span></span>

<span data-ttu-id="8c18a-109">В этой статье предполагается, что вы знаете, как использовать командную строку и предпочтительный текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="8c18a-109">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="8c18a-110">Если вы уже не используете ее, [кода Visual Studio](https://code.visualstudio.com) отличная возможность как текстовый редактор для F #.</span><span class="sxs-lookup"><span data-stu-id="8c18a-110">If you don't already use it, [Visual Studio Code](https://code.visualstudio.com) is a great option as a text editor for F#.</span></span> <span data-ttu-id="8c18a-111">Чтобы получить замечательных функций, таких как IntelliSense, лучше выделение синтаксиса и другие, можно загрузить [Ionide расширение](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="8c18a-111">To get awesome features like IntelliSense, better syntax highlighting, and more, you can download the [Ionide Extension](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="8c18a-112">Построение простого решения для нескольких проектов</span><span class="sxs-lookup"><span data-stu-id="8c18a-112">Build a simple multi-project solution</span></span>

<span data-ttu-id="8c18a-113">Откройте командную строку и терминалов и используйте [dotnet новый](../../core/tools/dotnet-new.md) команду, чтобы создать новый файл решения с именем `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="8c18a-113">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```
dotnet new sln -o FSNetCore
```

<span data-ttu-id="8c18a-114">После выполнения предыдущей команды создается следующая структура каталогов:</span><span class="sxs-lookup"><span data-stu-id="8c18a-114">The following directory structure is produced after running the previous command:</span></span>

```
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="8c18a-115">Запись библиотеки классов</span><span class="sxs-lookup"><span data-stu-id="8c18a-115">Write a class library</span></span>

<span data-ttu-id="8c18a-116">Перейдите к *FSNetCore*.</span><span class="sxs-lookup"><span data-stu-id="8c18a-116">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="8c18a-117">Используйте `dotnet new` команду, создайте проект библиотеки классов в **src** папку с именем библиотеки.</span><span class="sxs-lookup"><span data-stu-id="8c18a-117">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```
dotnet new lib -lang F# -o src/Library
```

<span data-ttu-id="8c18a-118">После выполнения предыдущей команды создается следующая структура каталогов:</span><span class="sxs-lookup"><span data-stu-id="8c18a-118">The following directory structure is produced after running the previous command:</span></span>

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="8c18a-119">Замените содержимое `Library.fs` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="8c18a-119">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="8c18a-120">Добавьте пакет Newtonsoft.Json NuGet на проект библиотеки.</span><span class="sxs-lookup"><span data-stu-id="8c18a-120">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="8c18a-121">Добавить `Library` проекта `FSNetCore` решении с помощью [добавьте dotnet sln](../../core/tools/dotnet-sln.md) команды:</span><span class="sxs-lookup"><span data-stu-id="8c18a-121">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="8c18a-122">Восстановление с помощью зависимостей NuGet `dotnet restore` команда ([см. Примечание](#dotnet-restore-note)) и запустите `dotnet build` для сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="8c18a-122">Restore the NuGet dependencies using the `dotnet restore` command ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="8c18a-123">Запись консольное приложение, использующее библиотеку классов</span><span class="sxs-lookup"><span data-stu-id="8c18a-123">Write a console application that consumes the class library</span></span>

<span data-ttu-id="8c18a-124">Используйте `dotnet new` команду, создайте консольное приложение в **src** папку с именем приложения.</span><span class="sxs-lookup"><span data-stu-id="8c18a-124">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```
dotnet new console -lang F# -o src/App
```

<span data-ttu-id="8c18a-125">После выполнения предыдущей команды создается следующая структура каталогов:</span><span class="sxs-lookup"><span data-stu-id="8c18a-125">The following directory structure is produced after running the previous command:</span></span>

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        ├── App
        │   ├── App.fsproj
        │   ├── Program.fs
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="8c18a-126">Замените содержимое `Program.fs` файла следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="8c18a-126">Replace the contents of the `Program.fs` file with the following code:</span></span>

```fsharp
open System
open Library

[<EntryPoint>]
let main argv =
    printfn "Nice command-line arguments! Here's what JSON.NET has to say about them:"

    argv
    |> Array.map getJsonNetJson
    |> Array.iter (printfn "%s")

    0 // return an integer exit code
```

<span data-ttu-id="8c18a-127">Добавьте ссылку на `Library` проекта с помощью [dotnet добавить ссылку](../../core/tools/dotnet-add-reference.md).</span><span class="sxs-lookup"><span data-stu-id="8c18a-127">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="8c18a-128">Добавить `App` проекта `FSNetCore` решении с помощью `dotnet sln add` команды:</span><span class="sxs-lookup"><span data-stu-id="8c18a-128">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="8c18a-129">Восстановление зависимости NuGet `dotnet restore` ([см. Примечание](#dotnet-restore-note)) и запустите `dotnet build` для сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="8c18a-129">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="8c18a-130">Перейдите в каталог `src/App` консоли проекта и запустите проект передача `Hello World` как аргументы:</span><span class="sxs-lookup"><span data-stu-id="8c18a-130">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```
cd src/App
dotnet run Hello World
```

<span data-ttu-id="8c18a-131">Вы увидите следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="8c18a-131">You should see the following results:</span></span>

```
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]