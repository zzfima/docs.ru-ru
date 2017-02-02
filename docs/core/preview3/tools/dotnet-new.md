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
ms.assetid: fcc3ed2e-9265-4d50-b59e-dc2e5c190b34
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: d4ca76f3de38b5d05868292d5c4bb8e3b0c7fdf2

---

#<a name="dotnet-new-tooling-preview-4"></a>dotnet-new (предварительная версия 4 инструментов)

> [!WARNING]
> Эта статья применима к инструментам .NET Core (предварительная версия 4) для версии-кандидата Visual Studio 2017. Версия этой статьи об инструментах .NET Core (предварительная версия 2): [dotnet-new](../../tools/dotnet-new.md).

## <a name="name"></a>Имя
dotnet-new — создает проект на .NET Core в текущем каталоге.

## <a name="synopsis"></a>Краткий обзор
`dotnet new [--help] [--type] [--lang]`

## <a name="description"></a>Описание
Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core, а также образец исходного кода, который позволяет испытать в работе набор средств интерфейса командной строки (CLI). 

Эта команда вызывается в контексте каталога. Вызов команды приводит к записи двух основных объектов в текущем каталоге: 

1. файла `Program.cs` (или `Program.fs`), содержащего образец программы Hello World;
2. Допустимый файл проекта csproj.

После этого проект готов к дальнейшей компиляции и изменению. 

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.  

`-l|--lang C#`

Язык проекта. По умолчанию — `C#`. Другие допустимые значения: `csharp` и `cs`.

`-t|--type`

Тип проекта. Допустимые значения для C#: `console`, `web`, `lib` и `xunittest`; для F# допустимо только значение `console`. 

## <a name="examples"></a>Примеры

Создание проекта консольного приложения C# в текущем каталоге:

`dotnet new` или `dotnet new --lang c#` 
   
Создание проекта приложения ASP.NET Core C# в текущем каталоге:

`dotnet new -t web`


<!--HONumber=Jan17_HO3-->


