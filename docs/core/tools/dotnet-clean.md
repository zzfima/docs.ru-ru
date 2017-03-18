---
title: "Команда dotnet-clean | Документы Майкрософт"
description: "Команда dotnet-clean очищает текущий каталог."
keywords: "dotnet-clean, CLI, CLI command, команда интерфейса командной строки, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: eff65fa1-bab4-4421-8260-d0a284b690b2
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 3c00f4616932318b5dc5d77cbdf6c645696a4226
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-clean"></a>dotnet-clean

## <a name="name"></a>Имя

`dotnet-clean` — очищает выходные данные проекта. 

## <a name="synopsis"></a>Краткий обзор

```
dotnet clean [project] [-o|--output] [-f|--framework] [-c|--configuration] [-v|--verbosity]
dotnet clean [--help] 
```

## <a name="description"></a>Описание

Команда `dotnet clean` очистит выходные данные предыдущей сборки. Она реализуется как целевой объект MSBuild, поэтому проект получит оценку. Будут очищены только выходные данные, созданные во время сборки. Очищаются папки с промежуточными (`obj`) и окончательными выходными данными (`bin`). 

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.  

`-o|--output <OUTPUT_DIRECTORY>`

Каталог, в который помещены двоичные значения сборки. При указании этого параметра также необходимо определить `--framework`. Если вы не задали это свойство во время сборки, его не нужно указывать для очистки.

`-f|--framework <FRAMEWORK>`

Платформа, указанная во время сборки. Если вы не задали это свойство во время сборки, его не нужно указывать для очистки. Платформа должна быть определена в [файле проекта](csproj.md).

`-c|--configuration [Debug|Release]`

Определяет конфигурация, с которой была запущена сборка.  Если значение не указано, по умолчанию используется значение `Debug`. Если вы не задали это свойство во время сборки, его не нужно указывать для очистки.

`-v|--verbosity <Quiet|Minimal|Normal|Diag>`

Определяет уровень детализации для вызова команды `dotnet clean`. Уровни детализации являются стандартными [уровнями детализации MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference). 

## <a name="examples"></a>Примеры

Очистите сборку проекта по умолчанию:

`dotnet clean`

Очистите сборку проекта с помощью конфигурации выпуска:

`dotnet clean --configuration Release`

