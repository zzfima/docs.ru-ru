---
title: "Команда dotnet-publish — CLI .NET Core"
description: "Команда dotnet-publish публикует проект .NET Core в каталоге."
keywords: "dotnet-publish, CLI, команда CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f2ef275a-7c5e-430a-8c30-65f52af62771
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a8a37b1eacab13682d4f4a2bea2f9ea248cdd9eb
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-publish"></a>dotnet-publish

## <a name="name"></a>Имя

`dotnet-publish` — упаковывает приложение и его зависимости в папку для развертывания на размещающей системе.

## <a name="synopsis"></a>Краткий обзор

`dotnet publish [<PROJECT>] [-f|--framework] [-r|--runtime] [-o|--output] [-c|--configuration] [--version-suffix] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>Описание

`dotnet publish` компилирует приложение, считывает его зависимости, указанные в файле проекта, и публикует итоговый набор файлов в каталоге. Выходные данные будут содержать следующее.

* Код на промежуточном языке (IL) в сборке с расширением `*.dll`.
* Файл *\*.deps.json*, содержащий все зависимости проекта.
* Файл *\*.runtime.config.json*, указывающий общую среду выполнения, которую ожидает приложение, а также другие параметры конфигурации для среды выполнения (например, тип сборки мусора).
* Зависимости приложения. Они копируются из кэша NuGet в выходную папку.

Выходных данных команды `dotnet publish` готовы к развертыванию на размещающей системе (например, на сервере, компьютере, ноутбуке Mac) для выполнения и являются единственным официально поддерживаемым способом подготовить приложение к развертыванию. В зависимости от указанного в проекте типа развертывания размещающая система может как иметь, так и не иметь общую среду выполнения .NET Core. Дополнительные сведения см. в разделе [Развертывание приложений .NET Core](../deploying/index.md). Структуру каталогов опубликованного приложения см. в разделе [Структура каталогов](/aspnet/core/hosting/directory-structure).

## <a name="arguments"></a>Аргументы

`PROJECT` 

Публикуемый проект. Если параметр не задан, по умолчанию используется текущий каталог. 

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.  

`-f|--framework <FRAMEWORK>`

Публикует приложение для указанной [целевой платформы](../../standard/frameworks.md). Вам нужно указать целевую платформу в файле проекта.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Публикует приложение для данной среды выполнения. Используется при создании [автономного развертывания](../deploying/index.md#self-contained-deployments-scd). Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md). По умолчанию публикуется [платформозависимое приложение](../deploying/index.md#framework-dependent-deployments-fdd).

`-o|--output <OUTPUT_DIRECTORY>`

Задает путь для выходного каталога. Если значение не задано, по умолчанию используется путь *./bin/[configuration]/[framework]/* для платформозависимого развертывания или *./bin/[configuration]/[framework]/[runtime]* для автономного.

`-c|--configuration <CONFIGURATION>`

Конфигурация, используемая при сборке проекта. Значение по умолчанию — `Debug`.

`--version-suffix <VERSION_SUFFIX>`

Определяет суффикс версии для замены звездочки (`*`) в поле версия файла проекта.

`-v|--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

## <a name="examples"></a>Примеры

Публикация проекта в текущем каталоге:

`dotnet publish`

Публикация приложения с использованием указанного файла проекта:

`dotnet publish ~/projects/app1/app1.csproj`
    
Публикация проекта в текущем каталоге с использованием платформы `netcoreapp1.1`:

`dotnet publish --framework netcoreapp1.1`
    
Публикация текущего приложения с использованием платформы `netcoreapp1.1` и среды выполнения для `OS X 10.10` (вам нужно указать этот идентификатор RID в файле проекта).

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

## <a name="see-also"></a>См. также

* [Целевые платформы](../../standard/frameworks.md)
* [Каталог идентификаторов сред выполнения (RID)](../rid-catalog.md)

