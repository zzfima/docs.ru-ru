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
# <a name="get-started-with-f-with-the-net-core-cli"></a>Начало работы F# с .NET Core CLI

В этой статье описывается, как можно приступить F# к работе в любой операционной системе (Windows, MacOS или Linux) с .NET Core CLI. Он проходит через создание многопроектного решения с библиотекой классов, которая вызывается консольным приложением.

## <a name="prerequisites"></a>Предварительные требования

Для начала необходимо установить последнюю [пакет SDK для .NET Core](https://dotnet.microsoft.com/download).

В этой статье предполагается, что вы умеете использовать командную строку и предпочитаемый текстовый редактор. Если вы еще не используете его, [Visual Studio Code](get-started-vscode.md) является отличным вариантом текстового редактора для F#.

## <a name="build-a-simple-multi-project-solution"></a>Создание простого решения с несколькими проектами

Откройте командную строку или терминал и выполните команду [DotNet New](../../core/tools/dotnet-new.md) , чтобы создать новый файл решения с `FSNetCore`именем:

```console
dotnet new sln -o FSNetCore
```

Следующая структура каталогов создается после выполнения предыдущей команды:

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>Написание библиотеки классов

Перейдите в каталог *фснеткоре*.

Используйте команду, чтобы создать проект библиотеки классов в папке src с именем Library. `dotnet new`

```console
dotnet new classlib -lang F# -o src/Library
```

Следующая структура каталогов создается после выполнения предыдущей команды:

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

Замените содержимое `Library.fs` следующим кодом:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

Добавьте пакет NuGet Newtonsoft. JSON в проект библиотеки.

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Добавьте проект в решение с помощью команды [DotNet SLN Add:](../../core/tools/dotnet-sln.md) `FSNetCore` `Library`

```console
dotnet sln add src/Library/Library.fsproj
```

Выполните `dotnet build` команду, чтобы выполнить сборку проекта. При сборке будут восстановлены неразрешенные зависимости.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>Написание консольного приложения, использующего библиотеку классов

Используйте команду, чтобы создать консольное приложение в папке src с именем App. `dotnet new`

```console
dotnet new console -lang F# -o src/App
```

Следующая структура каталогов создается после выполнения предыдущей команды:

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

Замените содержимое `Program.fs` файла следующим кодом:

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

Добавьте ссылку на `Library` проект с помощью команды [DotNet Add](../../core/tools/dotnet-add-reference.md).

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Добавьте проект в решение с помощью `dotnet sln add` команды: `FSNetCore` `App`

```console
dotnet sln add src/App/App.fsproj
```

Чтобы выполнить сборку проекта, `dotnet restore` восстановите зависимости NuGet и выполните команду `dotnet build` .

Перейдите в каталог `src/App` консольного проекта и запустите проект, передавая `Hello World` в качестве аргументов:

```console
cd src/App
dotnet run Hello World
```

Должны отобразиться следующие результаты.

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a>Следующие шаги

Далее ознакомьтесь с [обзором F# ](../tour.md) , чтобы получить дополнительные сведения о различных F# функциях.
