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
# <a name="get-started-with-f-with-the-net-core-cli"></a>Начало работы с F # с .NET Core CLI

В этой статье рассказывается, как вы можете начать работу с помощью F # на основе .NET Core. Оно будет выполнено построение многопроектное решение с библиотекой класса, вызываемого консольного приложения.

## <a name="prerequisites"></a>Предварительные требования

Чтобы начать, необходимо установить [.NET Core SDK 1.0 или более поздней версии](https://dot.net/core). Нет необходимости удалить предыдущую версию пакета SDK для .NET Core, как он поддерживает side-by-side установок.

В этой статье предполагается, что вы знаете, как использовать командную строку и предпочтительный текстовый редактор. Если вы уже не используете ее, [кода Visual Studio](https://code.visualstudio.com) отличная возможность как текстовый редактор для F #. Чтобы получить замечательных функций, таких как IntelliSense, лучше выделение синтаксиса и другие, можно загрузить [Ionide расширение](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).

## <a name="building-a-simple-multi-project-solution"></a>Создание простого решения для нескольких проектов

Откройте командную строку и терминалов и используйте `dotnet new` команду, чтобы создать новый файл решения с именем `FSNetCore`:

```
dotnet new sln -o FSNetCore
```

Структура каталогов следующих создается в результате выполнения команды.

```
FSNetCore
    ├── FSNetCore.sln
```

Перейдите к *FSNetCore* и начните добавлять проекты в папке решения.
 
### <a name="writing-a-class-library"></a>Создание библиотеки классов

Используйте `dotnet new` команду, создайте проект библиотеки классов в **src** папку с именем библиотеки. 

```bash
dotnet new lib -lang F# -o src/Library 
```

В результате выполнения команды создается следующая структура каталогов:

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

Замените содержимое `Library.fs` со следующим:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value = 
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value  (JsonConvert.SerializeObject(value))
```

Добавьте пакет Newtonsoft.Json NuGet на проект библиотеки.

```bash
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Добавить `Library` проекта `FSNetCore` решении с помощью `dotnet sln add` команды:

```bash
dotnet sln add src/Library/Library.fsproj
```

Восстановление зависимости NuGet `dotnet restore` ([см. Примечание](#dotnet-restore-note)) и запустите `dotnet build` для сборки проекта.

### <a name="writing-a-console-application-which-consumes-the-class-library"></a>Создание консольного приложения, которому требуется библиотека классов

Используйте `dotnet new` команду, создайте консольное приложение в **src** папку с именем приложения. 

```bash
dotnet new console -lang F# -o src/App 
```

В результате выполнения команды создается следующая структура каталогов:

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

Изменение `Program.fs` для:

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

Добавьте ссылку на `Library` проекта с помощью `dotnet add reference`.

```bash
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Добавить `App` проекта `FSNetCore` решении с помощью `dotnet sln add` команды:

```bash
dotnet sln add src/App/App.fsproj
```

Восстановление зависимости NuGet `dotnet restore` ([см. Примечание](#dotnet-restore-note)) и запустите `dotnet build` для сборки проекта.

Перейдите в каталог `src/App` консоли проекта и запустите проект передача `Hello World` как аргументы.

```bash
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