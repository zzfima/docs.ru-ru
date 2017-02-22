---
title: "Команда dotnet-migrate | Microsoft Docs"
description: "Команда dotnet-migrate переносит проект и все его зависимости."
keywords: "dotnet-migrate, интерфейс командной строки, команда CLI .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 11/13/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 0da07253-5ae1-42e9-9455-bffee9950952
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 57ae01419c6f7a75970816e1245094c38c5247fa

---

#<a name="dotnet-migrate"></a>dotnet-migrate

[!INCLUDE[preview-warning](../../../includes/warning.md)]

## <a name="name"></a>Имя 
dotnet-migrate — перемещает проект .NET Core предварительной версии 2 в проект .NET Core версии-кандидата 4

## <a name="synopsis"></a>Краткий обзор

`dotnet migrate [--help] [--template-file]  
    [--sdk-package-version] [--xproj-file]  
    [--skip-project-references]  [--report-file] [--format-report-file-json]
    [--skip-backup]
    [<arguments>]`

## <a name="description"></a>Описание
Команда `dotnet migrate` переместит действительный проект предварительной версии 2 `project.json` в действительный проект версии-кандидата 4 `csproj`. По умолчанию команда перенесет корневой проект и все ссылки, которые он содержит. Это поведение можно отключить в среде выполнения с помощью параметра `--skip-project-references`. 

Миграция может выполняться несколькими способами.

* Переносится один проект, в котором указан файл `project.json` для миграции.
* Переносятся все каталоги, указанные в файле `global.json`, с использованием передачи в путь к файлу `global.json`.
* Переносятся рекурсивно все подкаталоги в этом каталоге. 

Команда migrate будет хранить перенесенный файл `project.json` в каталоге `backup` (будет создан, если не существует). Это поведение можно изменить с помощью параметра `--skip-backup`. 

По умолчанию операция миграции будет выводить состояние процесса миграции в стандартный вывод (STDOUT). Если вы используете параметр `--report-file`, в выходных данных также будет сохранен указанный вами файл. 

Начиная с версии-кандидата 4, команда `dotnet migrate` поддерживает только допустимые файлы предварительной версии 2 `project.json`. Это означает, что эту команду нельзя использовать для переноса старых файлов DNX или предварительной версии 1 `project.json` непосредственно в CSPROJ. Необходимо сначала перенести их в файлы project.json предварительной версии 2, а затем в файлы CSPROJ. В будущем мы добавим поддержку проектов предварительной версии 1. 

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.  

`-t|--template-file <TEMPLATE_FILE>`

Файл CSPROJ шаблона для переноса. По умолчанию будет использоваться тот же шаблон, что и проигнорированный в `dotnet new`. 

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

Перенос всех проектов, на которые указывает файл `global.json`.

`dotnet migrate path/to/global.json`

Перенос только текущего проекта без взаимных зависимостей проектов и использование конкретной версии пакета SDK.

`dotnet migrate -s -v 1.0.0-preview4`


<!--HONumber=Feb17_HO2-->


