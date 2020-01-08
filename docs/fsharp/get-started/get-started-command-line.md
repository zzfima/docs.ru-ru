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
# <a name="get-started-with-f-with-the-net-core-cli"></a>Начало работы F# с .NET Core CLI

В этой статье описывается, как можно приступить F# к работе в любой операционной системе (Windows, MacOS или Linux) с .NET Core CLI. Он проходит через создание многопроектного решения с библиотекой классов, которая вызывается консольным приложением.

## <a name="prerequisites"></a>Prerequisites

Для начала необходимо установить последнюю [пакет SDK для .NET Core](https://dotnet.microsoft.com/download).

В этой статье предполагается, что вы умеете использовать командную строку и предпочитаемый текстовый редактор. Если вы еще не используете его, [Visual Studio Code](get-started-vscode.md) является отличным вариантом текстового редактора для F#.

## <a name="build-a-simple-multi-project-solution"></a>Создание простого решения с несколькими проектами

Откройте командную строку или терминал и используйте команду [DotNet New](../../core/tools/dotnet-new.md) , чтобы создать новый файл решения с именем `FSNetCore`:

```dotnetcli
dotnet new sln -o FSNetCore
```

Следующая структура каталогов создается после выполнения предыдущей команды:

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>Написание библиотеки классов

Перейдите в каталог *фснеткоре*.

Используйте команду `dotnet new`, создайте проект библиотеки классов в папке **src** с именем Library.

```dotnetcli
dotnet new classlib -lang "F#" -o src/Library
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

```dotnetcli
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Добавьте `Library` проект в решение `FSNetCore` с помощью команды [DotNet SLN Add](../../core/tools/dotnet-sln.md) :

```dotnetcli
dotnet sln add src/Library/Library.fsproj
```

Запустите `dotnet build`, чтобы выполнить сборку проекта. При сборке будут восстановлены неразрешенные зависимости.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>Написание консольного приложения, использующего библиотеку классов

С помощью команды `dotnet new` Создайте консольное приложение в папке **src** с именем App.

```dotnetcli
dotnet new console -lang "F#" -o src/App
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

Замените содержимое файла `Program.fs` приведенным ниже кодом.

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

Добавьте ссылку на проект `Library` с помощью [DotNet Add Reference](../../core/tools/dotnet-add-reference.md).

```dotnetcli
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Добавьте `App` проект в решение `FSNetCore` с помощью команды `dotnet sln add`:

```dotnetcli
dotnet sln add src/App/App.fsproj
```

Чтобы выполнить сборку проекта, восстановите зависимости NuGet `dotnet restore` и запустите `dotnet build`.

Перейдите в каталог `src/App` проект консоли и запустите проект, передав `Hello World` в качестве аргументов:

```console
cd src/App
dotnet run Hello World
```

Вы увидите следующие результаты:

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a>Следующие шаги

Далее ознакомьтесь с [обзором F# ](../tour.md) , чтобы получить дополнительные сведения о различных F# функциях.
