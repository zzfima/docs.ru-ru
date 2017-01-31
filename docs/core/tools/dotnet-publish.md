---
title: "Команда dotnet-publish | Microsoft Docs"
description: "Команда dotnet-publish публикует проект .NET Core в каталоге."
keywords: "dotnet-publish, CLI, команда CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8a7e1c52-5c57-4bf5-abad-727450ebeefd
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: f9fb64a90bdbd2096d4752279b1670fad8e8703f

---

#<a name="dotnet-publish"></a>dotnet-publish

> [!WARNING]
> Эта статья применима к инструментам .NET Core (предварительная версия 2). Информацию об инструментах .NET Core (предварительная версия 4) для версии-кандидата Visual Studio 2017 см. в статье [dotnet-publish (предварительная версия 4 инструментов)](../preview3/tools/dotnet-publish.md).

## <a name="name"></a>Имя

`dotnet-publish` — упаковывает приложение и все его зависимости в папку, подготавливая их к публикации.

## <a name="synopsis"></a>Краткий обзор

`dotnet publish [project] 
    [--help] [--framework]  
    [--runtime] [--build-base-path] [--output]  
    [--version-suffix] [--configuration] [--native-subdirectory] [--no-build]`

## <a name="description"></a>Описание

`dotnet publish` компилирует приложение, считывает его зависимости, указанные в файле [project.json](project-json.md), и публикует итоговый набор файлов в каталоге. 

В зависимости от типа переносимого приложения итоговый каталог будет содержать следующие компоненты:

1. *Переносимое приложение* — код приложения на промежуточном языке (IL) и все управляемые зависимости приложения.
    * *Переносимое приложение с собственными зависимостями* — то же, что и выше, с подкаталогом для поддерживаемой платформы каждой собственной зависимости. 
2. *Автономное приложение* — то же, что и выше, а также полная среда выполнения для целевой платформы.

Дополнительные сведения см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).

## <a name="options"></a>Параметры

`[project]` 

Публикуемый проект. Если параметр `[project]` не задан, по умолчанию используется текущий каталог. Значением может быть путь к файлу [project.json](project-json.md) или к каталогу проекта, содержащему файл [project.json](project-json.md). Если найти файл [project.json](project-json.md) не удалось, команда `dotnet publish` выдает ошибку. 

`-h|--help`

Выводит краткую справку по команде.  

`-f|--framework <FRAMEWORK>`

Публикует приложение для указанного идентификатора платформы (FID). Если значение не задано, идентификатор FID считывается из файла [project.json](project-json.md#frameworks). Если допустимая платформа не найдена, команда выдает ошибку. Если найдено несколько допустимых платформ, публикация выполняется для каждой из них. 

`-r|--runtime <RUNTIME_IDENTIFIER>`

Публикует приложение для данной среды выполнения. Список идентификаторов сред выполнения (RID), которые можно использовать, см. в [каталоге RID](../rid-catalog.md).

`-b|--build-base-path <OUTPUT_DIRECTORY>`

Каталог, в который будут помещаться временные выходные данные.

`-o|--output <OUTPUT_PATH>`

Укажите путь размещения каталога. Если значение не задано, по умолчанию используется путь *_./bin/[configuration]/[framework]/_* для переносимых приложений или *_./bin/[configuration]/[framework]/[runtime]_* для автономных развертываний.

`--version-suffix [VERSION_SUFFIX]`

Определяет, чем следует заменить звездочку (`*`) в поле версии в файле project.json.

`-c|--configuration [Debug|Release]`

Конфигурация, используемая при публикации. Значение по умолчанию — `Debug`.

`[--native-subdirectory]` Временный механизм для включения подкаталогов из ресурсов в машинном коде, входящих в пакеты зависимостей, в выходные данные. 

`[--no-build]` Не выполняет сборку проектов перед публикацией.

## <a name="examples"></a>Примеры

Публикация приложения с помощью платформы, указанной в файле `project.json`. Если файл `project.json` содержит узел [runtimes](project-json.md#runtimes), публикация выполняется для идентификатора RID текущей платформы.

`dotnet publish`

Публикация приложения с использованием указанного файла [project.json](project-json.md):

`dotnet publish ~/projects/app1/project.json`
    
Публикация текущего приложения с помощью платформы `netcoreapp1.0`:

`dotnet publish --framework netcoreapp1.0`
    
Публикация текущего приложения с использованием платформы `netcoreapp1.0` и среды выполнения для `OS X 10.10` (этот идентификатор RID должен присутствовать в узле [runtimes](project-json.md#runtimes) файла `project.json`):

`dotnet publish --framework netcoreapp1.0 --runtime osx.10.11-x64`

## <a name="see-also"></a>См. также
* [Платформы](../../standard/frameworks.md)
* [Каталог идентификаторов сред выполнения (RID)](../rid-catalog.md)


<!--HONumber=Jan17_HO3-->


