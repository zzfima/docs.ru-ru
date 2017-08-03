---
title: "Команда dotnet — CLI .NET Core"
description: "Сведения о команде dotnet (универсальном драйвере для средств CLI .NET Core) и ее использовании."
keywords: "dotnet, CLI, команды CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/20/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 256e468e-eaaa-4715-b5fb-8cbddcf80e69
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1f377ea55278ae382f56a0dc0cbcf1bb99f49eca
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-command"></a>Команда dotnet

## <a name="name"></a>Имя

`dotnet` — универсальный драйвер для выполнения команд командной строки.

## <a name="synopsis"></a>Краткий обзор

`dotnet [command] [arguments] [--version] [--info] [-d|--diagnostics] [-v|--verbose] [--fx-version] [--additionalprobingpath] [-h|--help]`

## <a name="description"></a>Описание

`dotnet` — это универсальный драйвер для цепочки инструментов интерфейса командной строки (CLI). Если вызвать его без указания команды, выводятся краткие инструкции по использованию.

Каждая отдельная функция реализуется в виде команды. Для использования функции необходимо указать команду после `dotnet`, например [`dotnet build`](dotnet-build.md). Все аргументы после команды относятся именно к ней.

Единственный случай, когда `dotnet` используется в качестве команды самостоятельно, — это запуск [платформозависимых приложений](../deploying/index.md). Просто укажите библиотеку DLL приложения после команды `dotnet`, чтобы выполнить приложение (Например, `dotnet myapp.dll`).

## <a name="options"></a>Параметры

`-v|--verbose`

Включает подробные выходные данные.

`-d|--diagnostics`

Включает вывод диагностических данных.

`--fx-version <VERSION>`

Версия установленной общей платформы, используемая для запуска приложения.

`--additionalprobingpath <PATH>`

Путь, содержащий политику проверки и проверяемые сборки.

`--version`

Выводит версию средств CLI.

`--info`

Выводит подробные сведения о средствах CLI и окружении, например текущую операционную систему, фиксацию SHA для версии и т. д.

`-h|--help`

Выводит краткую справку по команде. При использовании с `dotnet` также выводится список доступных команд.

## <a name="dotnet-commands"></a>Команды dotnet

### <a name="general"></a>Общие

Команда | Функция
--- | ---
[dotnet-build](dotnet-build.md) | Выполняет сборку приложения .NET Core.
[dotnet-clean](dotnet-clean.md) | Очистка выходных данных сборки.
[dotnet-migrate](dotnet-migrate.md) | Переносит допустимый проект предварительной версии 2 в проект пакета SDK .NET Core 1.0.
[dotnet-msbuild](dotnet-msbuild.md) | Обеспечивает доступ к командной строке MSBuild.
[dotnet-new](dotnet-new.md) | Инициализирует проект C# или F# для заданного шаблона.
[dotnet-pack](dotnet-pack.md) | Создает пакет NuGet с кодом.
[dotnet-publish](dotnet-publish.md) | Публикует платформозависимое или автономное приложение .NET.
[dotnet-restore](dotnet-restore.md) | Восстанавливает зависимости для данного приложения.
[dotnet-run](dotnet-run.md) | Запускает приложение из источника.
[dotnet-sln](dotnet-sln.md) | Параметры для добавления, удаления и перечисления проектов в файле решения.
[dotnet-test](dotnet-test.md) | Выполняет тесты с помощью средства запуска тестов.

### <a name="project-references"></a>Ссылки на проекты

Команда | Функция
--- | ---
[dotnet-add reference](dotnet-add-reference.md) | Добавление ссылки на проект.
[dotnet-list reference](dotnet-list-reference.md) | Перечисление ссылок на проект.
[dotnet-remove reference](dotnet-remove-reference.md) | Удаление ссылки на проект.

### <a name="nuget-packages"></a>Пакеты NuGet

Команда | Функция
--- | ---
[dotnet-add package](dotnet-add-package.md) | Добавление пакета NuGet.
[dotnet-remove package](dotnet-remove-package.md) | Удаление пакета NuGet.

### <a name="nuget-commands"></a>Команды NuGet

Команда | Функция
--- | ---
[dotnet-nuget delete](dotnet-nuget-delete.md) | Удаляет пакет с сервера или из списка.
[dotnet-nuget locals](dotnet-nuget-locals.md) | Очищает или перечисляет локальные ресурсы NuGet в кэше HTTP-запросов, временном кэше или папке пакетов, используемой на уровне компьютера.
[dotnet-nuget push](dotnet-nuget-push.md) | Отправляет пакет на сервер и публикует его.

## <a name="examples"></a>Примеры

Инициализация образца консольного приложения .NET Core, которое можно скомпилировать и запустить:

`dotnet new console`

Восстановление зависимостей для данного приложения:

`dotnet restore`

Сборка проекта и его зависимостей в указанном каталоге:

`dotnet build`

Запуск платформозависимого приложения `myapp.dll`:

`dotnet myapp.dll`

## <a name="environment-variables"></a>Переменные среды

`DOTNET_PACKAGES`

Основной кэш пакетов. Если значение не задано, то по умолчанию в Unix используется `$HOME/.nuget/packages`, а в Windows — `%HOME%\NuGet\Packages`.

`DOTNET_SERVICING`

Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт. Задайте значение `true`, чтобы отказаться от функции телеметрии (принимаются значения `true`, `1` или `yes`), в противном случае задайте значение `false`, чтобы согласиться на функции телеметрии (принимаются значения `false`, `0` или `no`). Если значение не задано, то по умолчанию используется `false` и функция телеметрии включена.

