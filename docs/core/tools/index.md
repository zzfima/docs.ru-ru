---
title: "Программы с интерфейсом командной строки (CLI) .NET Core | Microsoft Docs"
description: "Обзор средств и возможностей интерфейса командной строки (CLI)."
keywords: "CLI, средства CLI, .NET, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/20/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 7c5eee9f-d873-4224-8f5f-ed83df329a59
translationtype: Human Translation
ms.sourcegitcommit: 4a1f0c88fb1ccd6694f8d4f5687431646adbe000
ms.openlocfilehash: d00277ceb7fd1c8a7186da330ab2bc4ad40c59a7
ms.lasthandoff: 04/05/2017

---

# <a name="net-core-command-line-interface-cli-tools"></a>Средства интерфейса командной строки (CLI) .NET Core

Интерфейс командной строки (CLI) .NET Core — это новая кроссплатформенная цепочка инструментов для разработки приложений .NET. Он является той основой, на которую могут опираться инструменты более высоких уровней, такие как интегрированные среды разработки (IDE), редакторы и оркестраторы сборки.

## <a name="installation"></a>Установка

Можно использовать либо собственные установщики, либо скрипты оболочки для установки:

* Собственные установщики в основном применяются на компьютерах разработчиков и используют собственные механизмы установки каждой поддерживаемой платформы, например пакеты DEB в Ubuntu или пакеты MSI в Windows. Эти установщики устанавливают и настраивают окружение для немедленного использования разработчиком, но им требуются права администратора на компьютере. Инструкции по установке см. в [руководстве по установке .NET Core](https://aka.ms/dotnetcoregs).
* Скрипты оболочки применяются в первую очередь для настройки серверов сборки или установки средств без прав администратора. Скрипты установки не устанавливают на компьютере необходимые компоненты, поэтому их следует установить вручную. Дополнительные сведения см. в [справочном разделе по скриптам установки](dotnet-install-script.md). Сведения о настройке интерфейса командной строки на сервере сборки с непрерывной интеграцией см. в разделе [Использование пакета SDK и средств .NET Core при непрерывной интеграции (CI)](using-ci-with-cli.md).

По умолчанию интерфейс выполняет установку параллельно, чтобы на одном компьютере могли сосуществовать разные версии средств CLI. Сведения о том, как определить, какая из нескольких версий используется на компьютере, см. в разделе [Драйвер](#driver).

## <a name="cli-commands"></a>Команды CLI

По умолчанию устанавливаются следующие команды:

### <a name="basic-commands"></a>Основные команды

* [new](dotnet-new.md)
* [restore](dotnet-restore.md)
* [build](dotnet-build.md)
* [publish](dotnet-publish.md)
* [run](dotnet-run.md)
* [test](dotnet-test.md)
* [vstest](dotnet-vstest.md)
* [pack](dotnet-pack.md)
* [migrate](dotnet-migrate.md)
* [clean](dotnet-clean.md)
* [sln](dotnet-sln.md)

### <a name="project-modification-commands"></a>Команды для изменения проекта

* [add package](dotnet-add-package.md)
* [add reference](dotnet-add-reference.md)
* [remove package](dotnet-remove-package.md)
* [remove reference](dotnet-remove-reference.md)
* [list reference](dotnet-list-reference.md)

### <a name="advanced-commands"></a>Расширенные команды

* [nuget delete](dotnet-nuget-delete.md)
* [nuget locals](dotnet-nuget-locals.md)
* [nuget push](dotnet-nuget-push.md)
* [msbuild](dotnet-msbuild.md)
* [dotnet install script](dotnet-install-script.md)

Интерфейс CLI использует модель расширяемости, которая позволяет указывать дополнительные средства для проектов. Дополнительные сведения см. в разделе [Модель расширяемости CLI .NET Core](extensibility.md).

## <a name="command-structure"></a>Структура команд

Структура команд CLI состоит из [драйвера ("dotnet")](#driver), [самой команды](#command-verb) и возможных [аргументов](#arguments) и [параметров](#options). Этот шаблон используется в большинстве операций интерфейса командной строки, таких как создание консольного приложения и его запуск из командной строки, как показывают следующие команды при выполнении из каталога *my_app*:

```console
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

### <a name="driver"></a>Драйвер

Драйвер называется [dotnet](dotnet.md) и имеет два вида ответственности — выполнение [платформозависимого приложения](../app-types.md) или выполнение команды. Без команды `dotnet` используется только при запуске приложения.

Для запуска платформозависимого приложения укажите его драйвера, например `dotnet /path/to/my_app.dll`. При выполнении команды из папки, где находится библиотека DLL приложения, просто выполните `dotnet my_app.dll`.

При указании команды для драйвера `dotnet.exe` запускает процесс выполнения команды CLI. Сначала драйвер определяет нужную версию средств. Если в параметрах команды эта версия не указана, драйвер использует последнюю доступную версию. Чтобы указать версию, отличную от самой последней установленной, используйте параметр `--fx-version <VERSION>` (см. описание [команды dotnet](dotnet.md)). После определения версии пакета SDK драйвер выполняет команду.

### <a name="command-verb"></a>Команда

Команда служит для выполнения действия. Например, `dotnet build` проводит сборку кода. `dotnet publish` публикует код. Команды реализуются как консольное приложение с использованием соглашения `dotnet-{verb}`. 

### <a name="arguments"></a>Аргументы

Аргументы, указываемые в командной строке, передаются непосредственно в вызываемую команду. Например, если выполнить `dotnet publish my_app.csproj`, аргумент `my_app.csproj` указывает публикуемый проект и передается в команду `publish`.

### <a name="options"></a>Параметры

Параметры, указываемые в командной строке, передаются непосредственно в вызываемую команду. Например, при выполнении `dotnet publish --output /build_output` параметр `--output` и его значение передаются в команду `publish`. 

## <a name="migration-from-projectjson"></a>Перенос из проекта project.json

Если вы использовали средства предварительной версии 2 для создания проектов на основе *project.json*, обратитесь к разделу о [dotnet migrate](dotnet-migrate.md) за информацией о переносе проекта в MSBuild/*.csproj*, чтобы его можно было использовать со средствами версии выпуска. Для проектов .NET Core, созданных до выхода средств предварительной версии 2, обновите проект вручную, выполнив указания из раздела [Переход с DNX на интерфейс CLI .NET Core (project.json)](../migration/from-dnx.md) и воспользовавшись `dotnet migrate`, либо напрямую обновите свои проекты.

## <a name="additional-resources"></a>Дополнительные ресурсы

* [Репозиторий dotnet/CLI на сайте GitHub](https://github.com/dotnet/cli/)
* [Руководство по установке .NET Core](https://aka.ms/dotnetcoregs/)

