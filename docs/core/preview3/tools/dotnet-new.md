---
title: "Команда dotnet-new | Microsoft Docs"
description: "Команда dotnet-new создает проекты .NET Core в текущем каталоге."
keywords: "dotnet-new, CLI, команда CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 02/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fcc3ed2e-9265-4d50-b59e-dc2e5c190b34
translationtype: Human Translation
ms.sourcegitcommit: 96fd8ea3e55ea33e0bdd0bf3c50a10d0de6db1a1
ms.openlocfilehash: f0c62647c5817db2057c60a7a95a62f08f7889a5

---
#<a name="dotnet-new-net-core-tools-rc4"></a>dotnet-new (версия-кандидат 4 средств .NET Core)

> [!WARNING]
> Эта статья применима к версии-кандидату 4 средств .NET Core. Версия этой статьи об инструментах .NET Core (предварительная версия 2): [dotnet-new](../../tools/dotnet-new.md).

## <a name="name"></a>Имя
dotnet-new — создает проект .NET Core в текущем каталоге

## <a name="synopsis"></a>Краткий обзор
```
dotnet new [template] [-lang|--language] [-n|--name] [-o|--output] [-h|--help]
dotnet new [template] [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

## <a name="description"></a>Описание
Команда `dotnet new` предоставляет удобный способ инициализации проекта .NET Core, а также образец исходного кода, который позволяет испытать в работе набор средств интерфейса командной строки. 

Эта команда вызывается в контексте каталога. При вызове команда сформирует шаблоны ресурсов и файлов в соответствии с шаблоном и параметрами, переданными в команду. 

После этого проект готов к дальнейшей компиляции и изменению. 

## <a name="arguments"></a>Аргументы
template — шаблон, создающий экземпляры при вызове команды.

Команда содержит список шаблонов по умолчанию. Используйте `dotnet new --help`. 

## <a name="options"></a>Параметры

`-l|--list`         

Перечисляет шаблоны с указанным именем.

`-lang|--language`  

Задает язык создаваемого шаблона

`-n|--name`         

Имя создаваемых выходных данных. Если имя не указано, используется имя текущего каталога.

`-o|--output`       

Расположение, в котором размещаются созданные выходные данные.

`-all|--show-all`   

Показывает все шаблоны определенного типа проекта.

`-h|--help`

Распечатывает справку для команды.

## <a name="template-options"></a>Параметры шаблона
Каждый шаблон проекта может содержать дополнительные доступные параметры. Основные шаблоны, например, содержат следующее.

**console, xunit, mstest**

`-f|--framework` — указывает целевую платформу. Значения: netcoreapp1.0 или netcoreapp1.1 (по умолчанию: netcoreapp1.0)

**web, webapi**

`-f|--framework` — указывает целевую платформу. Значения: netcoreapp1.0 или netcoreapp1.1 (по умолчанию: netcoreapp1.0)
 
**mvc**

`-f|--framework` — указывает целевую платформу. Значения: netcoreapp1.0 или netcoreapp1.1 (по умолчанию: netcoreapp1.0)

`-au|--authentication` — тип проверки подлинности. Значения: None или Individual (по умолчанию: None)

`-uld|--use-local-db` — следует ли использовать LocalDB вместо SQLite. Значения: True или False (по умолчанию: False)

**classlib**

`-f|--framework` — указывает целевую платформу. Значения: netcoreapp1.0, netcoreapp1.1 и netstandard1.0–1.6 (по умолчанию: netstandard1.4).

## <a name="examples"></a>Примеры

Создайте проект консольного приложения F# в текущем каталоге:

`dotnet new console -lang f#` 
   
Создайте проект приложения ASP.NET Core C# MVC в текущем каталоге без проверки подлинности для .NET Core 1.0:  

`dotnet new mvc -au None -f netcoreapp1.0`
 
Создайте приложение XUnit, предназначенное для .NET Core 1.1:

`dotnet new xunit --Framework netcoreapp1.1`

Перечислите все шаблоны, доступные для MVC:

`dotnet new mvc -l`


<!--HONumber=Feb17_HO3-->


