---
title: "Команда dotnet-clean — CLI .NET Core | Документы Майкрософт"
description: "Команда dotnet-clean очищает текущий каталог."
keywords: "dotnet-clean, CLI, CLI command, команда интерфейса командной строки, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: eff65fa1-bab4-4421-8260-d0a284b690b2
ms.translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: 0bdd8b9ab133ca92e414618412d95d8136d6234a
ms.contentlocale: ru-ru
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-clean"></a>dotnet-clean

## <a name="name"></a>Имя

`dotnet-clean` — очищает выходные данные проекта. 

## <a name="synopsis"></a>Краткий обзор

`dotnet clean [<PROJECT>] [-o|--output] [-f|--framework] [-c|--configuration] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>Описание

Команда `dotnet clean` очищает выходные данные предыдущей сборки. Она реализуется как [целевой объект MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-targets), поэтому при выполнении команды проект получает оценку. Очищаются только выходные данные, созданные во время сборки. Очищаются папки с промежуточными (*obj*) и окончательными выходными данными (*bin*).

## <a name="arguments"></a>Аргументы

`PROJECT`

Очищаемый проект MSBuild. Если файл проекта не указан, MSBuild ищет в текущем рабочем каталоге файл с расширением, заканчивающимся на *PROJ*, и использует его.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.

`-o|--output <OUTPUT_DIRECTORY>`

Каталог, куда помещаются выходные данные сборки. Укажите параметр `-f|--framework <FRAMEWORK>` с параметром выходного каталога, если задали платформу при сборке проекта.

`-f|--framework <FRAMEWORK>`

[Платформа](../../standard/frameworks.md), указанная во время сборки. Платформа должна быть определена в [файле проекта](csproj.md). Если вы указали платформу во время сборки, нужно указать ее эту платформу при очистке.

`-c|--configuration <CONFIGURATION>`

Определяет конфигурацию. Если значение не указано, по умолчанию используется значение `Debug`. Это свойство требуется при очистке только в том случае, если вы указали его во время сборки.

`-v|--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые уровни: q[uiet], m[inimal], n[ormal], d[etailed] и diag[nostic].

## <a name="examples"></a>Примеры

Очистите сборку проекта по умолчанию:

`dotnet clean`

Очистите сборку проекта с помощью конфигурации выпуска:

`dotnet clean --configuration Release`

