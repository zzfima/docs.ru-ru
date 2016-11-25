---
title: "Команда dotnet-migrate | Пакет SDK для .NET"
description: "Команда dotnet-migrate переносит проект и все его зависимости."
keywords: "dotnet-migrate, интерфейс командной строки, команда CLI .NET Core"
author: mairaw
manager: wpickett
ms.date: 11/13/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 70285a83-4103-4617-be8b-d0e1e9a4a91d
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: 150d70e3f0a80f7f6e733abee3691a0fe420919f

---

#<a name="dotnet-migrate"></a>dotnet-migrate

## <a name="name"></a>Имя 
dotnet-migrate — переносит проект .NET Core предварительной версии 2 в проект .NET Core предварительной версии 3.

## <a name="synopsis"></a>Краткий обзор

`dotnet migrate [--help] [--template-file]  
    [--sdk-package-version] [--xproj-file]  
    [--skip-project-references]  [--report-file] [--format-report-file-json]
    [--skip-backup]
    [<arguments>]`

## <a name="description"></a>Описание
Команда `dotnet migrate` перенесет действительный проект `project.json` предварительной версии 2 в действительный проект `csproj` предварительной версии 3. По умолчанию команда перенесет корневой проект и все ссылки, которые он содержит. Это поведение можно отключить в среде выполнения с помощью параметра `--skip-project-references`. 

Миграция может выполняться несколькими способами.

* Переносится один проект, в котором указан файл `project.json` для миграции.
* Переносятся все каталоги, указанные в файле `global.json`, с использованием передачи в путь к файлу `global.json`.
* Переносятся рекурсивно все подкаталоги в этом каталоге. 

Команда migrate будет хранить перенесенный файл `project.json` в каталоге `backup` (будет создан, если не существует). Это поведение можно изменить с помощью параметра `--skip-backup`. 

По умолчанию операция миграции будет выводить состояние процесса миграции в стандартный вывод (STDOUT). Если вы используете параметр `--report-file`, в выходных данных также будет сохранен указанный вами файл. 

Начиная с предварительной версии 3 команда `dotnet migrate` поддерживает только допустимые файлы `project.json` предварительной версии 2. Это означает, что эту команду нельзя использовать для переноса старых файлов DNX или предварительной версии 1 `project.json` непосредственно в CSPROJ. Необходимо сначала перенести их в файлы project.json предварительной версии 2, а затем в файлы CSPROJ. В будущем мы добавим поддержку проектов предварительной версии 1. 

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

`dotnet migrate -s -v 1.0.0-preview3`




<!--HONumber=Nov16_HO3-->


