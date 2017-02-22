---
title: "Команда dotnet-new | Microsoft Docs"
description: "Команда dotnet-new создает проекты .NET Core в текущем каталоге."
keywords: "dotnet-new, CLI, команда CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 263c3d05-3a47-46a6-8023-3ca16b488410
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: a49fe94ca8f678c614fb7f58767693c73e34c737

---

#<a name="dotnet-new"></a>dotnet-new

> [!WARNING]
> Эта статья применима к инструментам .NET Core (предварительная версия 2). Сведения для версии-кандидата 4 средств .NET Core см. в разделе [dotnet-new (версия-кандидат 4 средств .NET Core)](../preview3/tools/dotnet-new.md).

## <a name="name"></a>Имя
`dotnet-new` — создает проект .NET Core в текущем каталоге.

## <a name="synopsis"></a>Краткий обзор
`dotnet new [--help] [--type] [--lang]`

## <a name="description"></a>Описание
Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core, а также образец исходного кода, который позволяет испытать в работе набор средств интерфейса командной строки (CLI). 

Эта команда вызывается в контексте каталога. Вызов команды приводит к записи двух основных объектов в текущем каталоге: 

1. файла `Program.cs` (или `Program.fs`), содержащего образец программы Hello World;
2. допустимого файла `project.json`.

После этого проект готов к дальнейшей компиляции и изменению. 

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.  

`-l|--lang <C#|F#>`

Язык проекта. По умолчанию — `C#`. Другие допустимые значения: `csharp`, `fsharp`, `cs` и `fs`.

`-t|--type`

Тип проекта. Допустимые значения для C#: `console`, `web`, `lib` и `xunittest`; для F# допустимо только значение `console`. 

## <a name="examples"></a>Примеры

Создание проекта консольного приложения C# в текущем каталоге:

`dotnet new` или `dotnet new --lang c#` 
   
Создание проекта консольного приложения F# в текущем каталоге:

`dotnet new --lang f#`
  
Создание проекта приложения ASP.NET Core C# в текущем каталоге:

`dotnet new -t web`


<!--HONumber=Feb17_HO2-->


