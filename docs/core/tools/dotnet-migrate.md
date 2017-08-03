---
title: "Команда dotnet-migrate — CLI .NET Core"
description: "Команда dotnet-migrate переносит проект и все его зависимости."
keywords: "dotnet-migrate, интерфейс командной строки, команда CLI .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 0da07253-5ae1-42e9-9455-bffee9950952
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e8491d69b2e0df7b3bd2741e34abdb9631777019
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-migrate"></a>dotnet-migrate

## <a name="name"></a>Имя

`dotnet-migrate` — перемещает проект .NET Core предварительной версии 2 в проект пакета SDK для .NET Core 1.0.

## <a name="synopsis"></a>Краткий обзор

`dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file] [-s|--skip-project-references] [-r|--report-file] [--format-report-file-json] [--skip-backup] [-h|--help]`

## <a name="description"></a>Описание

Команда `dotnet migrate` переносит действительный проект предварительной версии 2 на основе *project.json* в действительный проект *CSPROJ* пакета SDK для .NET Core 1.0. 

По умолчанию команда переносит корневой проект и все ссылки, которые он содержит. Это поведение можно отключить в среде выполнения с помощью параметра `--skip-project-references`. 

Миграция выполняется для следующих объектов:

* Отдельный проект посредством указания нужного файла *project.json*.
* Все каталоги, указанные в файле *global.json*, посредством передачи пути в файл *global.json*.
* Файл *solution.sln*, куда переносятся проекты, на которые ссылается решение.
* Рекурсивно все подкаталоги в этом каталоге.

Команда `dotnet migrate` сохраняет перенесенный файл *project.json* в каталоге `backup` (создается, если не существует). Это поведение можно переопределить с помощью параметра `--skip-backup`. 

По умолчанию операция миграции выводит состояние процесса миграции в стандартный вывод (STDOUT). Если вы используете параметр `--report-file <REPORT_FILE>`, выходные данные сохраняются в указанном файле. 

Команда `dotnet migrate` поддерживает только допустимые проекты предварительной версии 2 на основе *project.json*. Это означает, что она не позволяет перенести проекты DNX или проекты предварительной версии 1 на базе *project.json* непосредственно в проекты MSBuild/CSPROJ. Сначала нужно вручную перенести проект в проект версии 2 на основе *project.json*, а затем воспользоваться командой `dotnet migrate` для переноса проекта.

## <a name="arguments"></a>Аргументы

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

Путь к одному из следующих объектов:

* переносимый файл *project.json*;
* файл *global.json*, куда переносятся папки, указанные в *global.json*;
* файл *solution.sln*, куда переносятся проекты, на которые ссылается решение;
* каталог для миграции, где выполняется рекурсивный поиск переносимых файлов *project.json*.

Если значение не задано, по умолчанию используется текущий каталог.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.  

`-t|--template-file <TEMPLATE_FILE>`

Файл CSPROJ шаблона для переноса. По умолчанию используется тот же шаблон, что и проигнорированный в `dotnet new console`. 

`-v|--sdk-package-version <VERSION>`

Версия пакета SDK, на которую ссылается перенесенное приложение. По умолчанию используется версия пакета SDK в `dotnet new`.

`-x|--xproj-file <FILE>`

Путь к файлу XPROJ, который будет использоваться. Требуется, если в каталоге проекта несколько файлов XPROJ.

`-s|--skip-project-references [Debug|Release]`

Пропуск ссылок проекта для миграции. По умолчанию ссылки проекта переносятся рекурсивно.

`-r|--report-file <REPORT_FILE>`

Вывод отчета о миграции в файл наряду с выводом в консоль.

`--format-report-file-json <REPORT_FILE>`

Вывод отчета о миграции в файл JSON вместо отправки сообщений пользователю.

`--skip-backup`

Пропуск перемещения *project.json*, *global.json* и *\*.xproj* в каталог `backup` после успешной миграции.

## <a name="examples"></a>Примеры

Перенос проекта в текущем каталоге и всех взаимных зависимостей проектов.

`dotnet migrate`

Перенос всех проектов, включенных в файл *global.json*:

`dotnet migrate path/to/global.json`

Перенос только текущего проекта без взаимных зависимостей проектов. Кроме того, используется определенная версия пакета SDK:

`dotnet migrate -s -v 1.0.0-preview4`

