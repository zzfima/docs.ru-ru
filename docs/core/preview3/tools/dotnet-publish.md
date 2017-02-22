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
ms.assetid: f2ef275a-7c5e-430a-8c30-65f52af62771
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 0d222382640fc239760f8f51c69f1f306674d7ca

---

#<a name="dotnet-publish-net-core-tools-rc4"></a>dotnet-publish (версия-кандидат 4 средств .NETCore)

> [!WARNING]
> Эта статья применима к версии-кандидату 4 средств .NET Core. Версия этой статьи об инструментах .NET Core (предварительная версия 2): [dotnet-publish](../../tools/dotnet-publish.md).

## <a name="name"></a>Имя

`dotnet-publish` — упаковывает приложение и все его зависимости в папку, подготавливая их к публикации.

## <a name="synopsis"></a>Краткий обзор

`dotnet publish [project] 
    [--help] [--framework]  
    [--runtime] [--output]  
    [--version-suffix] [--configuration]`

## <a name="description"></a>Описание

`dotnet publish` компилирует приложение, считывает его зависимости, указанные в файле проекта, и публикует итоговый набор файлов в каталоге. 

В зависимости от типа переносимого приложения итоговый каталог будет содержать следующие компоненты:

1. *Зависимое от платформы развертывание* — код приложения на промежуточном языке (IL) и все управляемые зависимости приложения.
2. *Автономное развертывание* — то же, что и выше, а также вся среда выполнения для целевой платформы.

Дополнительные сведения см. в разделе [Развертывание приложений .NET Core](../deploying/index.md).

## <a name="options"></a>Параметры

`[project]` 

Публикуемый проект. Если параметр `[project]` не задан, по умолчанию используется текущий каталог. 

`-h|--help`

Выводит краткую справку по команде.  

`-f|--framework <FRAMEWORK>`

Публикует приложение для указанного идентификатора платформы (FID). 

`-r|--runtime <RUNTIME_IDENTIFIER>`

Публикует приложение для данной среды выполнения. Список идентификаторов сред выполнения (RID), которые можно использовать, см. в [каталоге RID](../../rid-catalog.md).

`-o|--output <OUTPUT_PATH>`

Укажите путь размещения каталога. Если значение не задано, по умолчанию используется путь *_./bin/[configuration]/[framework]/_* для переносимых приложений или *_./bin/[configuration]/[framework]/[runtime]_* для автономных развертываний.

`--version-suffix [VERSION_SUFFIX]`

Определяет, чем следует заменить звездочку (`*`) в поле версии в файле проекта.

`-c|--configuration [Debug|Release]`

Конфигурация, используемая при публикации. Значение по умолчанию — `Debug`.

## <a name="examples"></a>Примеры

Публикация приложения.

`dotnet publish`

Публикация приложения с использованием указанного файла проекта

`dotnet publish ~/projects/app1/app1.csproj`
    
Публикация текущего приложения с помощью платформы `netcoreapp1.0`:

`dotnet publish --framework netcoreapp1.0`
    
Публикация текущего приложения с использованием платформы `netcoreapp1.0` и среды выполнения для `OS X 10.10` (этот идентификатор RID должен присутствовать в файле проекта).

`dotnet publish --framework netcoreapp1.0 --runtime osx.10.11-x64`

## <a name="see-also"></a>См. также
* [Платформы](../../../standard/frameworks.md)
* [Каталог идентификаторов сред выполнения (RID)](../../rid-catalog.md)



<!--HONumber=Feb17_HO2-->


