---
title: 'Начало работы с F # с помощью средства командной строки'
description: 'Сведения о создании простого многопроектное решение на F # с помощью .NET Core CLI в любой операционной системе (Windows, macOs или Linux).'
author: cartermp
ms.author: phcart
ms.date: 03/26/2018
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.openlocfilehash: e48e1291bbe91da0d9ca2adbb08662bd106c8fb4
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2018
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>Начало работы с F # с .NET Core CLI

В этой статье рассказывается, как вы можете начать работу с F # в любой операционной системе (Windows, macOS или Linux) с .NET Core CLI. Он проходит построение многопроектное решение с библиотекой класса, вызываемого консольное приложение.

## <a name="prerequisites"></a>Предварительные требования

Чтобы начать, необходимо установить [.NET Core SDK 1.0 или более поздней версии](https://www.microsoft.com/net/download/). Нет необходимости удалить предыдущую версию пакета SDK для .NET Core, как он поддерживает side-by-side установок.

В этой статье предполагается, что вы знаете, как использовать командную строку и предпочтительный текстовый редактор. Если вы уже не используете ее, [кода Visual Studio](https://code.visualstudio.com) отличная возможность как текстовый редактор для F #. Чтобы получить замечательных функций, таких как IntelliSense, лучше выделение синтаксиса и другие, можно загрузить [Ionide расширение](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).

## <a name="build-a-simple-multi-project-solution"></a>Построение простого решения для нескольких проектов

Откройте командную строку и терминалов и используйте [dotnet новый](../../core/tools/dotnet-new.md) команду, чтобы создать новый файл решения с именем `FSNetCore`:

```
dotnet new sln -o FSNetCore
```

После выполнения предыдущей команды создается следующая структура каталогов:

```
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>Запись библиотеки классов

Перейдите к *FSNetCore*.

Используйте `dotnet new` команду, создайте проект библиотеки классов в **src** папку с именем библиотеки.

```
dotnet new lib -lang F# -o src/Library
```

После выполнения предыдущей команды создается следующая структура каталогов:

```
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

Добавьте пакет Newtonsoft.Json NuGet на проект библиотеки.

```
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Добавить `Library` проекта `FSNetCore` решении с помощью [добавьте dotnet sln](../../core/tools/dotnet-sln.md) команды:

```
dotnet sln add src/Library/Library.fsproj
```

Восстановление с помощью зависимостей NuGet `dotnet restore` команда ([см. Примечание](#dotnet-restore-note)) и запустите `dotnet build` для сборки проекта.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>Запись консольное приложение, использующее библиотеку классов

Используйте `dotnet new` команду, создайте консольное приложение в **src** папку с именем приложения.

```
dotnet new console -lang F# -o src/App
```

После выполнения предыдущей команды создается следующая структура каталогов:

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

Добавьте ссылку на `Library` проекта с помощью [dotnet добавить ссылку](../../core/tools/dotnet-add-reference.md).

```
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Добавить `App` проекта `FSNetCore` решении с помощью `dotnet sln add` команды:

```
dotnet sln add src/App/App.fsproj
```

Восстановление зависимости NuGet `dotnet restore` ([см. Примечание](#dotnet-restore-note)) и запустите `dotnet build` для сборки проекта.

Перейдите в каталог `src/App` консоли проекта и запустите проект передача `Hello World` как аргументы:

```
cd src/App
dotnet run Hello World
```

Вы увидите следующие результаты:

```
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]