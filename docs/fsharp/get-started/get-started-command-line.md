---
title: Приступая к F# работе со средствами командной строки
description: Узнайте, как создать простое многопроектное решение на F# основе .NET Core CLI в любой операционной системе (Windows, MacOS или Linux).
ms.date: 03/26/2018
ms.openlocfilehash: aa3ed84660a951eeafc11a00ea3831f587b6d876
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559491"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="05930-103">Начало работы F# с .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="05930-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="05930-104">В этой статье описывается, как можно приступить F# к работе в любой операционной системе (Windows, MacOS или Linux) с .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="05930-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="05930-105">Он проходит через создание многопроектного решения с библиотекой классов, которая вызывается консольным приложением.</span><span class="sxs-lookup"><span data-stu-id="05930-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="05930-106">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="05930-106">Prerequisites</span></span>

<span data-ttu-id="05930-107">Для начала необходимо установить последнюю [пакет SDK для .NET Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="05930-107">To begin, you must install the latest [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="05930-108">В этой статье предполагается, что вы умеете использовать командную строку и предпочитаемый текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="05930-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="05930-109">Если вы еще не используете его, [Visual Studio Code](get-started-vscode.md) является отличным вариантом текстового редактора для F#.</span><span class="sxs-lookup"><span data-stu-id="05930-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="05930-110">Создание простого решения с несколькими проектами</span><span class="sxs-lookup"><span data-stu-id="05930-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="05930-111">Откройте командную строку или терминал и используйте команду [DotNet New](../../core/tools/dotnet-new.md) , чтобы создать новый файл решения с именем `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="05930-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```dotnetcli
dotnet new sln -o FSNetCore
```

<span data-ttu-id="05930-112">Следующая структура каталогов создается после выполнения предыдущей команды:</span><span class="sxs-lookup"><span data-stu-id="05930-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="05930-113">Написание библиотеки классов</span><span class="sxs-lookup"><span data-stu-id="05930-113">Write a class library</span></span>

<span data-ttu-id="05930-114">Перейдите в каталог *фснеткоре*.</span><span class="sxs-lookup"><span data-stu-id="05930-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="05930-115">Используйте команду `dotnet new`, создайте проект библиотеки классов в папке **src** с именем Library.</span><span class="sxs-lookup"><span data-stu-id="05930-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```dotnetcli
dotnet new classlib -lang "F#" -o src/Library
```

<span data-ttu-id="05930-116">Следующая структура каталогов создается после выполнения предыдущей команды:</span><span class="sxs-lookup"><span data-stu-id="05930-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="05930-117">Замените содержимое `Library.fs` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="05930-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="05930-118">Добавьте пакет NuGet Newtonsoft. JSON в проект библиотеки.</span><span class="sxs-lookup"><span data-stu-id="05930-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```dotnetcli
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="05930-119">Добавьте `Library` проект в решение `FSNetCore` с помощью команды [DotNet SLN Add](../../core/tools/dotnet-sln.md) :</span><span class="sxs-lookup"><span data-stu-id="05930-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```dotnetcli
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="05930-120">Запустите `dotnet build`, чтобы выполнить сборку проекта.</span><span class="sxs-lookup"><span data-stu-id="05930-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="05930-121">При сборке будут восстановлены неразрешенные зависимости.</span><span class="sxs-lookup"><span data-stu-id="05930-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="05930-122">Написание консольного приложения, использующего библиотеку классов</span><span class="sxs-lookup"><span data-stu-id="05930-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="05930-123">С помощью команды `dotnet new` Создайте консольное приложение в папке **src** с именем App.</span><span class="sxs-lookup"><span data-stu-id="05930-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```dotnetcli
dotnet new console -lang "F#" -o src/App
```

<span data-ttu-id="05930-124">Следующая структура каталогов создается после выполнения предыдущей команды:</span><span class="sxs-lookup"><span data-stu-id="05930-124">The following directory structure is produced after running the previous command:</span></span>

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

<span data-ttu-id="05930-125">Замените содержимое файла `Program.fs` приведенным ниже кодом.</span><span class="sxs-lookup"><span data-stu-id="05930-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="05930-126">Добавьте ссылку на проект `Library` с помощью [DotNet Add Reference](../../core/tools/dotnet-add-reference.md).</span><span class="sxs-lookup"><span data-stu-id="05930-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```dotnetcli
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="05930-127">Добавьте `App` проект в решение `FSNetCore` с помощью команды `dotnet sln add`:</span><span class="sxs-lookup"><span data-stu-id="05930-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```dotnetcli
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="05930-128">Чтобы выполнить сборку проекта, восстановите зависимости NuGet `dotnet restore` и запустите `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="05930-128">Restore the NuGet dependencies, `dotnet restore` and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="05930-129">Перейдите в каталог `src/App` проект консоли и запустите проект, передав `Hello World` в качестве аргументов:</span><span class="sxs-lookup"><span data-stu-id="05930-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```console
cd src/App
dotnet run Hello World
```

<span data-ttu-id="05930-130">Вы увидите следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="05930-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="05930-131">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="05930-131">Next steps</span></span>

<span data-ttu-id="05930-132">Далее ознакомьтесь с [обзором F# ](../tour.md) , чтобы получить дополнительные сведения о различных F# функциях.</span><span class="sxs-lookup"><span data-stu-id="05930-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>
