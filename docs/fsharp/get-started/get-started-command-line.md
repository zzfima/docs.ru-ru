---
title: 'Начало работы с F # с помощью средства командной строки'
description: 'Узнайте, как создать простое решение для нескольких проектов F # с помощью интерфейса командной строки .NET Core в любой операционной системе (Windows, macOs или Linux).'
ms.date: 03/26/2018
ms.openlocfilehash: 8a82970f33c8bbe1b8cdd8fb6499b59b16d3cbf3
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44134809"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="449e9-103">Начало работы с F # с помощью интерфейса командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="449e9-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="449e9-104">В этой статье рассматриваются, как вы можете начать работу с F # в любой операционной системе (Windows, macOS или Linux) с помощью интерфейса командной строки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="449e9-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="449e9-105">Проходит построение многопроектное решение с использованием библиотеки классов, которая вызывается коллекцией консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="449e9-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="449e9-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="449e9-106">Prerequisites</span></span>

<span data-ttu-id="449e9-107">Чтобы начать, необходимо установить последнюю версию [пакет SDK для .NET Core](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="449e9-107">To begin, you must install the latest [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

<span data-ttu-id="449e9-108">В этой статье предполагается, что вы знаете, как использовать командную строку и предпочитаемый текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="449e9-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="449e9-109">Если вы еще не используете, [Visual Studio Code](get-started-vscode.md) это отличный вариант как текстовый редактор для F #.</span><span class="sxs-lookup"><span data-stu-id="449e9-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="449e9-110">Создайте простое решения нескольких проектов</span><span class="sxs-lookup"><span data-stu-id="449e9-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="449e9-111">Откройте окно командной строки или терминала и использовать [команды dotnet new](../../core/tools/dotnet-new.md) команду, чтобы создать новый файл решения с именем `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="449e9-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```console
dotnet new sln -o FSNetCore
```

<span data-ttu-id="449e9-112">После выполнения предыдущей команды создается следующая структура каталогов:</span><span class="sxs-lookup"><span data-stu-id="449e9-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="449e9-113">Написать библиотеку классов</span><span class="sxs-lookup"><span data-stu-id="449e9-113">Write a class library</span></span>

<span data-ttu-id="449e9-114">Перейдите в каталог *FSNetCore*.</span><span class="sxs-lookup"><span data-stu-id="449e9-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="449e9-115">Используйте `dotnet new` команды, создайте проект библиотеки классов в **src** папку с именем библиотеки.</span><span class="sxs-lookup"><span data-stu-id="449e9-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```console
dotnet new classlib -lang F# -o src/Library
```

<span data-ttu-id="449e9-116">После выполнения предыдущей команды создается следующая структура каталогов:</span><span class="sxs-lookup"><span data-stu-id="449e9-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="449e9-117">Замените содержимое файла `Library.fs` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="449e9-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="449e9-118">Добавьте пакет Newtonsoft.Json NuGet в проект библиотеки.</span><span class="sxs-lookup"><span data-stu-id="449e9-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="449e9-119">Добавить `Library` проект `FSNetCore` решения с помощью [добавьте dotnet sln](../../core/tools/dotnet-sln.md) команды:</span><span class="sxs-lookup"><span data-stu-id="449e9-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```console
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="449e9-120">Запустите `dotnet build` для сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="449e9-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="449e9-121">Неразрешенные зависимости будут восстановлены при построении.</span><span class="sxs-lookup"><span data-stu-id="449e9-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="449e9-122">Консольное приложение, использующее библиотеку классов</span><span class="sxs-lookup"><span data-stu-id="449e9-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="449e9-123">Используйте `dotnet new` команды, создайте консольное приложение на **src** папку с именем приложения.</span><span class="sxs-lookup"><span data-stu-id="449e9-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```console
dotnet new console -lang F# -o src/App
```

<span data-ttu-id="449e9-124">После выполнения предыдущей команды создается следующая структура каталогов:</span><span class="sxs-lookup"><span data-stu-id="449e9-124">The following directory structure is produced after running the previous command:</span></span>

```console
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

<span data-ttu-id="449e9-125">Замените содержимое файла `Program.fs` файла следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="449e9-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="449e9-126">Добавьте ссылку на `Library` проекта с помощью [dotnet добавьте ссылку на](../../core/tools/dotnet-add-reference.md).</span><span class="sxs-lookup"><span data-stu-id="449e9-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="449e9-127">Добавить `App` проект `FSNetCore` решения с помощью `dotnet sln add` команды:</span><span class="sxs-lookup"><span data-stu-id="449e9-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```console
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="449e9-128">Восстановление зависимостей NuGet, `dotnet restore` ([см. Примечание](#dotnet-restore-note)) и запустите `dotnet build` для сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="449e9-128">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="449e9-129">Перейдите в каталог `src/App` консоли проекта и запустить проект передачи `Hello World` как аргументы:</span><span class="sxs-lookup"><span data-stu-id="449e9-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```console
cd src/App
dotnet run Hello World
```

<span data-ttu-id="449e9-130">Вы должны увидеть следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="449e9-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="449e9-131">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="449e9-131">Next steps</span></span>

<span data-ttu-id="449e9-132">Затем ознакомьтесь [обзор языка F #](../tour.md) Дополнительные сведения о различных функциях, F #.</span><span class="sxs-lookup"><span data-stu-id="449e9-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>
