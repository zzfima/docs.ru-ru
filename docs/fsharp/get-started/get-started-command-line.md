---
title: Приступая к F# работе со средствами командной строки
description: Узнайте, как создать простое многопроектное решение на F# основе .NET Core CLI в любой операционной системе (Windows, MacOs или Linux).
ms.date: 03/26/2018
ms.openlocfilehash: 1376b6b5384f380c06a96cdc568ad108de8a6e5f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855822"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="34edd-103">Начало работы F# с .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="34edd-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="34edd-104">В этой статье описывается, как можно приступить F# к работе в любой операционной системе (Windows, MacOS или Linux) с .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="34edd-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="34edd-105">Он проходит через создание многопроектного решения с библиотекой классов, которая вызывается консольным приложением.</span><span class="sxs-lookup"><span data-stu-id="34edd-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="34edd-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="34edd-106">Prerequisites</span></span>

<span data-ttu-id="34edd-107">Для начала необходимо установить последнюю [пакет SDK для .NET Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="34edd-107">To begin, you must install the latest [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="34edd-108">В этой статье предполагается, что вы умеете использовать командную строку и предпочитаемый текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="34edd-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="34edd-109">Если вы еще не используете его, [Visual Studio Code](get-started-vscode.md) является отличным вариантом текстового редактора для F#.</span><span class="sxs-lookup"><span data-stu-id="34edd-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="34edd-110">Создание простого решения с несколькими проектами</span><span class="sxs-lookup"><span data-stu-id="34edd-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="34edd-111">Откройте командную строку или терминал и выполните команду [DotNet New](../../core/tools/dotnet-new.md) , чтобы создать новый файл решения с `FSNetCore`именем:</span><span class="sxs-lookup"><span data-stu-id="34edd-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```console
dotnet new sln -o FSNetCore
```

<span data-ttu-id="34edd-112">Следующая структура каталогов создается после выполнения предыдущей команды:</span><span class="sxs-lookup"><span data-stu-id="34edd-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="34edd-113">Написание библиотеки классов</span><span class="sxs-lookup"><span data-stu-id="34edd-113">Write a class library</span></span>

<span data-ttu-id="34edd-114">Перейдите в каталог *фснеткоре*.</span><span class="sxs-lookup"><span data-stu-id="34edd-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="34edd-115">Используйте команду, чтобы создать проект библиотеки классов в папке src с именем Library. `dotnet new`</span><span class="sxs-lookup"><span data-stu-id="34edd-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```console
dotnet new classlib -lang F# -o src/Library
```

<span data-ttu-id="34edd-116">Следующая структура каталогов создается после выполнения предыдущей команды:</span><span class="sxs-lookup"><span data-stu-id="34edd-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="34edd-117">Замените содержимое `Library.fs` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="34edd-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="34edd-118">Добавьте пакет NuGet Newtonsoft. JSON в проект библиотеки.</span><span class="sxs-lookup"><span data-stu-id="34edd-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="34edd-119">Добавьте проект в решение с помощью команды [DotNet SLN Add:](../../core/tools/dotnet-sln.md) `FSNetCore` `Library`</span><span class="sxs-lookup"><span data-stu-id="34edd-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```console
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="34edd-120">Выполните `dotnet build` команду, чтобы выполнить сборку проекта.</span><span class="sxs-lookup"><span data-stu-id="34edd-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="34edd-121">При сборке будут восстановлены неразрешенные зависимости.</span><span class="sxs-lookup"><span data-stu-id="34edd-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="34edd-122">Написание консольного приложения, использующего библиотеку классов</span><span class="sxs-lookup"><span data-stu-id="34edd-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="34edd-123">Используйте команду, чтобы создать консольное приложение в папке src с именем App. `dotnet new`</span><span class="sxs-lookup"><span data-stu-id="34edd-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```console
dotnet new console -lang F# -o src/App
```

<span data-ttu-id="34edd-124">Следующая структура каталогов создается после выполнения предыдущей команды:</span><span class="sxs-lookup"><span data-stu-id="34edd-124">The following directory structure is produced after running the previous command:</span></span>

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

<span data-ttu-id="34edd-125">Замените содержимое `Program.fs` файла следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="34edd-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="34edd-126">Добавьте ссылку на `Library` проект с помощью команды [DotNet Add](../../core/tools/dotnet-add-reference.md).</span><span class="sxs-lookup"><span data-stu-id="34edd-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="34edd-127">Добавьте проект в решение с помощью `dotnet sln add` команды: `FSNetCore` `App`</span><span class="sxs-lookup"><span data-stu-id="34edd-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```console
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="34edd-128">Чтобы выполнить сборку проекта, `dotnet restore` восстановите зависимости NuGet и выполните команду `dotnet build` .</span><span class="sxs-lookup"><span data-stu-id="34edd-128">Restore the NuGet dependencies, `dotnet restore` and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="34edd-129">Перейдите в каталог `src/App` консольного проекта и запустите проект, передавая `Hello World` в качестве аргументов:</span><span class="sxs-lookup"><span data-stu-id="34edd-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```console
cd src/App
dotnet run Hello World
```

<span data-ttu-id="34edd-130">Должны отобразиться следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="34edd-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="34edd-131">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="34edd-131">Next steps</span></span>

<span data-ttu-id="34edd-132">Далее ознакомьтесь с [обзором F# ](../tour.md) , чтобы получить дополнительные сведения о различных F# функциях.</span><span class="sxs-lookup"><span data-stu-id="34edd-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>
