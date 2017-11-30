---
title: "Начало работы с F # с помощью средства командной строки"
description: "Сведения об использовании языка F # с CLI кросс платформенных .NET Core."
keywords: "visual f#, f#, функциональное программирование, .NET, .NET Core"
author: cartermp
ms.author: phcart
ms.date: 06/14/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 615db1ec-6ef3-4de2-bae6-4586affa9771
ms.openlocfilehash: a23d4861ce599f20f37ecd0564a0187e7b9b739f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="37d06-104">Начало работы с F # с .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="37d06-104">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="37d06-105">В этой статье рассказывается, как вы можете начать работу с помощью F # на основе .NET Core.</span><span class="sxs-lookup"><span data-stu-id="37d06-105">This article covers how you can get started with using F# on .NET Core.</span></span> <span data-ttu-id="37d06-106">Оно будет выполнено построение многопроектное решение с библиотекой класса, вызываемого консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="37d06-106">It will go through building a multi-project solution with a Class Library that is called by a Console Application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="37d06-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="37d06-107">Prerequisites</span></span>

<span data-ttu-id="37d06-108">Чтобы начать, необходимо установить [.NET Core SDK 1.0 или более поздней версии](https://dot.net/core).</span><span class="sxs-lookup"><span data-stu-id="37d06-108">To begin, you must install the [.NET Core SDK 1.0 or later](https://dot.net/core).</span></span> <span data-ttu-id="37d06-109">Нет необходимости удалить предыдущую версию пакета SDK для .NET Core, как он поддерживает side-by-side установок.</span><span class="sxs-lookup"><span data-stu-id="37d06-109">There is no need to uninstall a previous version of the .NET Core SDK, as it supports side-by-side installations.</span></span>

<span data-ttu-id="37d06-110">В этой статье предполагается, что вы знаете, как использовать командную строку и предпочтительный текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="37d06-110">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="37d06-111">Если вы уже не используете ее, [кода Visual Studio](https://code.visualstudio.com) отличная возможность как текстовый редактор для F #.</span><span class="sxs-lookup"><span data-stu-id="37d06-111">If you don't already use it, [Visual Studio Code](https://code.visualstudio.com) is a great option as a text editor for F#.</span></span> <span data-ttu-id="37d06-112">Чтобы получить замечательных функций, таких как IntelliSense, лучше выделение синтаксиса и другие, можно загрузить [Ionide расширение](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="37d06-112">To get awesome features like IntelliSense, better syntax highlighting, and more, you can download the [Ionide Extension](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span>

## <a name="building-a-simple-multi-project-solution"></a><span data-ttu-id="37d06-113">Создание простого решения для нескольких проектов</span><span class="sxs-lookup"><span data-stu-id="37d06-113">Building a Simple Multi-project Solution</span></span>

<span data-ttu-id="37d06-114">Откройте командную строку и терминалов и используйте `dotnet new` команду, чтобы создать новый файл решения с именем `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="37d06-114">Open a command prompt/terminal and use the `dotnet new` command to create new solution file called `FSNetCore`:</span></span>

```
dotnet new sln -o FSNetCore
```

<span data-ttu-id="37d06-115">Структура каталогов следующих создается в результате выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="37d06-115">The folowing directory structure is produced as a result of the command completing:</span></span>

```
FSNetCore
    ├── FSNetCore.sln
```

<span data-ttu-id="37d06-116">Перейдите к *FSNetCore* и начните добавлять проекты в папке решения.</span><span class="sxs-lookup"><span data-stu-id="37d06-116">Change directories to *FSNetCore* and start adding projects to the solution folder.</span></span>
 
### <a name="writing-a-class-library"></a><span data-ttu-id="37d06-117">Создание библиотеки классов</span><span class="sxs-lookup"><span data-stu-id="37d06-117">Writing a Class library</span></span>

<span data-ttu-id="37d06-118">Используйте `dotnet new` команду, создайте проект библиотеки классов в **src** папку с именем библиотеки.</span><span class="sxs-lookup"><span data-stu-id="37d06-118">Use the `dotnet new` command, create a Class Library project in the **src** folder named Library.</span></span> 

```bash
dotnet new lib -lang F# -o src/Library 
```

<span data-ttu-id="37d06-119">В результате выполнения команды создается следующая структура каталогов:</span><span class="sxs-lookup"><span data-stu-id="37d06-119">The following directory structure is produced as a result of the command completing:</span></span>

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="37d06-120">Замените содержимое `Library.fs` со следующим:</span><span class="sxs-lookup"><span data-stu-id="37d06-120">Replace the contents of `Library.fs` with the following:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value = 
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value  (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="37d06-121">Добавьте пакет Newtonsoft.Json NuGet на проект библиотеки.</span><span class="sxs-lookup"><span data-stu-id="37d06-121">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```bash
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="37d06-122">Добавить `Library` проекта `FSNetCore` решении с помощью `dotnet sln add` команды:</span><span class="sxs-lookup"><span data-stu-id="37d06-122">Add the `Library` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```bash
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="37d06-123">Восстановление зависимости NuGet `dotnet restore` ([см. Примечание](#dotnet-restore-note)) и запустите `dotnet build` для сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="37d06-123">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

### <a name="writing-a-console-application-which-consumes-the-class-library"></a><span data-ttu-id="37d06-124">Создание консольного приложения, которому требуется библиотека классов</span><span class="sxs-lookup"><span data-stu-id="37d06-124">Writing a Console Application which Consumes the Class Library</span></span>

<span data-ttu-id="37d06-125">Используйте `dotnet new` команду, создайте консольное приложение в **src** папку с именем приложения.</span><span class="sxs-lookup"><span data-stu-id="37d06-125">Use the `dotnet new` command, create a Console app in the **src** folder named App.</span></span> 

```bash
dotnet new console -lang F# -o src/App 
```

<span data-ttu-id="37d06-126">В результате выполнения команды создается следующая структура каталогов:</span><span class="sxs-lookup"><span data-stu-id="37d06-126">The following directory structure is produced as a result of the command completing:</span></span>

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

<span data-ttu-id="37d06-127">Изменение `Program.fs` для:</span><span class="sxs-lookup"><span data-stu-id="37d06-127">Change `Program.fs` to:</span></span>

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

<span data-ttu-id="37d06-128">Добавьте ссылку на `Library` проекта с помощью `dotnet add reference`.</span><span class="sxs-lookup"><span data-stu-id="37d06-128">Add a reference to the `Library` project using `dotnet add reference`.</span></span>

```bash
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="37d06-129">Добавить `App` проекта `FSNetCore` решении с помощью `dotnet sln add` команды:</span><span class="sxs-lookup"><span data-stu-id="37d06-129">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```bash
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="37d06-130">Восстановление зависимости NuGet `dotnet restore` ([см. Примечание](#dotnet-restore-note)) и запустите `dotnet build` для сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="37d06-130">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="37d06-131">Перейдите в каталог `src/App` консоли проекта и запустите проект передача `Hello World` как аргументы.</span><span class="sxs-lookup"><span data-stu-id="37d06-131">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments.</span></span>

```bash
cd src/App
dotnet run Hello World
``` 

<span data-ttu-id="37d06-132">Вы увидите следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="37d06-132">You should see the following results:</span></span>

```
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```
<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]