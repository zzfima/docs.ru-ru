---
title: "Команда dotnet-migrate | Microsoft Docs"
description: "Команда dotnet-migrate переносит проект и все его зависимости."
keywords: "dotnet-migrate, интерфейс командной строки, команда CLI .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 0da07253-5ae1-42e9-9455-bffee9950952
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: b7da4df5319e7c17900b9c093347e8a17045a6a3
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-migrate"></a>dotnet-migrate

## <a name="name"></a>Имя 
dotnet-migrate — перемещает проект .NET Core предварительной версии 2 в проект пакета SDK для .NET Core 1.0.

## <a name="synopsis"></a>Краткий обзор

```
dotnet migrate [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file] [-s|--skip-project-references] [-r|--report-file] [--format-report-file-json] [--skip-backup] [<arguments>]
dotnet migrate [-h|--help]
```

## <a name="description"></a>Описание

Команда `dotnet migrate` перенесет действительный проект предварительной версии 2 на основе *project.json* в действительный проект *CSPROJ* пакета SDK для .NET Core 1.0. 

По умолчанию команда перенесет корневой проект и все ссылки, которые он содержит. Это поведение можно отключить в среде выполнения с помощью параметра `--skip-project-references`. 

Миграция может выполняться несколькими способами.

* Переносится один проект посредством указания нужного файла *project.json*.
* Переносятся все каталоги, указанные в файле *global.json*, посредством передачи пути в файл *global.json*.
* Переносятся рекурсивно все подкаталоги в этом каталоге. 

Команда migrate будет хранить перенесенный файл *project.json* в каталоге `backup`(будет создан, если не существует). Это поведение можно изменить с помощью параметра `--skip-backup`. 

По умолчанию операция миграции будет выводить состояние процесса миграции в стандартный вывод (STDOUT). Если вы используете параметр `--report-file`, в выходных данных также будет сохранен указанный вами файл. 

Команда `dotnet migrate` поддерживает только допустимые файлы предварительной версии 2 *project.json*. Это означает, что эту команду нельзя использовать для переноса старых файлов DNX или файлов *project.json* предварительной версии 1 непосредственно в CSPROJ. Нужно сначала перенести их в файлы project.json предварительной версии 2, а затем в файлы CSPROJ. В будущем мы добавим поддержку проектов предварительной версии 1. 

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.  

`-t|--template-file <TEMPLATE_FILE>`

Файл CSPROJ шаблона для переноса. По умолчанию будет использоваться тот же шаблон, что и проигнорированный в `dotnet new console`. 

`-v|--sdk-package-version <VERSION>`

Версия пакета SDK, на которую будут ссылаться перенесенные приложения. По умолчанию используется версия пакета SDK новой платформы DotNet.

`-x|--xproj-file <FILE>`

Путь к файлу XPROJ, который будет использоваться. Требуется, если в каталоге проекта несколько файлов XPROJ.

`-s|--skip-project-references [Debug|Release]`

Пропуск ссылок проекта для миграции. По умолчанию ссылки проекта переносятся рекурсивно.

`-r|--report-file <REPORT_FILE>`

Вывод отчета о миграции в файл наряду с выводом в консоль.

`--format-report-file-json <REPORT_FILE>`

Вывод отчета о миграции в файл JSON вместо отправки сообщений пользователю.

`--skip-backup`

Пропуск перемещения project.json, global.json, и \*.xproj в каталог `backup` после успешной миграции.

## <a name="examples"></a>Примеры

Перенос проекта в текущем каталоге и всех взаимных зависимостей проектов.

`dotnet migrate`

Перенос всех проектов, на которые указывает файл *global.json*:

`dotnet migrate path/to/global.json`

Перенос только текущего проекта без взаимных зависимостей проектов и использование конкретной версии пакета SDK.

`dotnet migrate -s -v 1.0.0-preview4`
