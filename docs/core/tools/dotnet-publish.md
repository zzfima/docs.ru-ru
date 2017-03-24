---
title: "Команда dotnet-publish | Microsoft Docs"
description: "Команда dotnet-publish публикует проект .NET Core в каталоге."
keywords: "dotnet-publish, CLI, команда CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f2ef275a-7c5e-430a-8c30-65f52af62771
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 78487673d8fa07286605fb806f30083747b17386
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-publish"></a>dotnet-publish

## <a name="name"></a>Имя

`dotnet-publish` — упаковывает приложение и все его зависимости в папку, подготавливая их к публикации.

## <a name="synopsis"></a>Краткий обзор

```
dotnet publish [project] [-f|--framework] [-r|--runtime] [-o|--output] [-c|--configuration] [--version-suffix] [-v|--verbosity]
dotnet publish [-h|--help]
```

## <a name="description"></a>Описание

`dotnet publish` компилирует приложение, считывает его зависимости, указанные в файле проекта, и публикует итоговый набор файлов в каталоге. Выходные данные будут содержать следующее.

1. Код на промежуточном языке (IL) в сборке с расширением `*.dll`.
2. Файл*deps.json*, содержащий все зависимости проекта. 
3. Файл *Runtime.config.json*, указывающий общую среду выполнения, которую ожидает приложение, а также другие параметры конфигурации для среды выполнения (например, тип сборки мусора).
4. Все зависимости приложения. Они копируются из кэша NuGet в выходную папку. 

Выходных данных команды `dotnet publish` готовы к развертыванию на удаленном компьютере для выполнения и являются единственным официально поддерживаемым способом подготовить приложение к развертыванию на другом компьютере (например, сервере) для выполнения. В зависимости от указанного в проекте типа развертывания на удаленном компьютере потребуется установить общую среду выполнения .NET Core. Дополнительные сведения см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).

## <a name="arguments"></a>Аргументы

`project` 

Публикуемый проект. Если параметр `project` не задан, по умолчанию используется текущий каталог. 

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.  

`-f|--framework <FRAMEWORK>`

Публикует приложение для указанной целевой платформы. Целевая платформа должна быть указана в файле проекта.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Публикует приложение для данной среды выполнения. Используется при создании [автономного развертывания](../deploying/index.md#self-contained-deployments-scd). Список идентификаторов сред выполнения (RID), которые можно использовать, см. в [каталоге RID](../rid-catalog.md). По умолчанию публикуется [приложение, зависимое от платформы](../deploying/index.md#framework-dependent-deployments-fdd).

`-o|--output <OUTPUT_PATH>`

Укажите путь размещения каталога. Если значение не задано, по умолчанию используется путь *_./bin/[configuration]/[framework]/_* для переносимых приложений или *_./bin/[configuration]/[framework]/[runtime]_* для автономных развертываний.

`-c|--configuration {Debug|Release}`

Конфигурация, используемая при сборке проекта. Значение по умолчанию — `Debug`.

`--version-suffix <VERSION_SUFFIX>`

Определяет, чем следует заменить звездочку (`*`) в поле версии в файле проекта.

`-v|--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

## <a name="examples"></a>Примеры

Публикация проекта, найденного в текущем каталоге:

`dotnet publish`

Публикация приложения с использованием указанного файла проекта:

`dotnet publish ~/projects/app1/app1.csproj`
    
Публикация проекта, найденного в текущем каталоге, с использованием платформы `netcoreapp1.1`:

`dotnet publish --framework netcoreapp1.1`
    
Публикация текущего приложения с использованием платформы `netcoreapp1.1` и среды выполнения для `OS X 10.10` (этот идентификатор RID должен присутствовать в файле проекта).

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

## <a name="see-also"></a>См. также
* [Платформы](../../standard/frameworks.md)
* [Каталог идентификаторов сред выполнения (RID)](../rid-catalog.md)
