---
title: 'Начало работы с F # с помощью средства командной строки'
description: 'Узнайте, как создать простое решение для нескольких проектов F # с помощью интерфейса командной строки .NET Core в любой операционной системе (Windows, macOs или Linux).'
ms.date: 03/26/2018
ms.openlocfilehash: 8a82970f33c8bbe1b8cdd8fb6499b59b16d3cbf3
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "45673913"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>Начало работы с F # с помощью интерфейса командной строки .NET Core

В этой статье рассматриваются, как вы можете начать работу с F # в любой операционной системе (Windows, macOS или Linux) с помощью интерфейса командной строки .NET Core. Проходит построение многопроектное решение с использованием библиотеки классов, которая вызывается коллекцией консольное приложение.

## <a name="prerequisites"></a>Предварительные требования

Чтобы начать, необходимо установить последнюю версию [пакет SDK для .NET Core](https://www.microsoft.com/net/download/).

В этой статье предполагается, что вы знаете, как использовать командную строку и предпочитаемый текстовый редактор. Если вы еще не используете, [Visual Studio Code](get-started-vscode.md) это отличный вариант как текстовый редактор для F #.

## <a name="build-a-simple-multi-project-solution"></a>Создайте простое решения нескольких проектов

Откройте окно командной строки или терминала и использовать [команды dotnet new](../../core/tools/dotnet-new.md) команду, чтобы создать новый файл решения с именем `FSNetCore`:

```console
dotnet new sln -o FSNetCore
```

После выполнения предыдущей команды создается следующая структура каталогов:

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>Написать библиотеку классов

Перейдите в каталог *FSNetCore*.

Используйте `dotnet new` команды, создайте проект библиотеки классов в **src** папку с именем библиотеки.

```console
dotnet new classlib -lang F# -o src/Library
```

После выполнения предыдущей команды создается следующая структура каталогов:

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

Замените содержимое файла `Library.fs` следующим кодом:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

Добавьте пакет Newtonsoft.Json NuGet в проект библиотеки.

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Добавить `Library` проект `FSNetCore` решения с помощью [добавьте dotnet sln](../../core/tools/dotnet-sln.md) команды:

```console
dotnet sln add src/Library/Library.fsproj
```

Запустите `dotnet build` для сборки проекта. Неразрешенные зависимости будут восстановлены при построении.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>Консольное приложение, использующее библиотеку классов

Используйте `dotnet new` команды, создайте консольное приложение на **src** папку с именем приложения.

```console
dotnet new console -lang F# -o src/App
```

После выполнения предыдущей команды создается следующая структура каталогов:

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

Замените содержимое файла `Program.fs` файла следующим кодом:

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

Добавьте ссылку на `Library` проекта с помощью [dotnet добавьте ссылку на](../../core/tools/dotnet-add-reference.md).

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Добавить `App` проект `FSNetCore` решения с помощью `dotnet sln add` команды:

```console
dotnet sln add src/App/App.fsproj
```

Восстановление зависимостей NuGet, `dotnet restore` ([см. Примечание](#dotnet-restore-note)) и запустите `dotnet build` для сборки проекта.

Перейдите в каталог `src/App` консоли проекта и запустить проект передачи `Hello World` как аргументы:

```console
cd src/App
dotnet run Hello World
```

Вы должны увидеть следующие результаты:

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a>Следующие шаги

Затем ознакомьтесь [обзор языка F #](../tour.md) Дополнительные сведения о различных функциях, F #.
