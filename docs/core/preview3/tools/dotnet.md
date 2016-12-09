---
title: "Команда dotnet | Пакет SDK для .NET Core"
description: "Сведения о команде dotnet (универсальном драйвере для средств CLI .NET Core) и ее использовании."
keywords: "dotnet, CLI, команды CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 93015521-2127-4fe9-8fce-ca79bcc4ff49
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: bbc13c8cca82e660f0f8ccf7d88c0340d9c06e68

---

#<a name="dotnet-command"></a>Команда dotnet

## <a name="name"></a>Имя

dotnet — универсальный драйвер для выполнения команд командной строки

## <a name="synopsis"></a>Краткий обзор

`dotnet [--version] [--verbose] [--info] [command] [arguments] [--help]`

## <a name="description"></a>Описание
`dotnet` — это универсальный драйвер для цепочки инструментов интерфейса командной строки (CLI). Если вызвать его без указания команды, будут выведены краткие инструкции по использованию. 

Каждая отдельная функция реализуется в виде команды. Для использования функции необходимо указать команду после `dotnet`, например [`dotnet build`](dotnet-build.md). Все аргументы после команды относятся именно к ней. 

Единственный случай, когда `dotnet` используется в качестве команды самостоятельно, — это запуск переносимых приложений. Просто укажите библиотеку DLL переносимого приложения после команды `dotnet`, чтобы выполнить приложение.    

## <a name="options"></a>Параметры

`-v|--verbose`

Включает подробные выходные данные.

`--version`

Выводит версию средств CLI.

`--info`

Выводит более подробные сведения о средствах CLI, например текущую операционную систему, фиксацию SHA для версии и т. д. 

`-h|--help`

Выводит краткую справку по команде. При использовании только с `dotnet` также выводится список доступных команд.  

## <a name="dotnet-commands"></a>Команды dotnet

Для dotnet имеются следующие команды:

* [dotnet-new](dotnet-new.md)
   * Инициализирует проект консольного приложения C# или F#.
* [dotnet-restore](dotnet-restore.md)
  * Восстанавливает зависимости для данного приложения. 
* [dotnet-build](dotnet-build.md)
  * Выполняет сборку приложения .NET Core.
* [dotnet-publish](dotnet-publish.md)
   * Публикует переносимое или автономное приложение .NET.
* [dotnet-run](dotnet-run.md)
   * Запускает приложение из источника.
* [dotnet-test](dotnet-test.md)
   * Выполняет тесты с помощью средства выполнения тестов, указанного в файле project.json.
* [dotnet-pack](dotnet-pack.md)
   * Создает пакет NuGet с кодом.
* [dotnet-migrate](dotnet-migrate.md)
   * Переносит допустимый проект предварительной версии 2 в аналогичный проект версии 3
* [dotnet-msbuild](dotnet-msbuild.md)
   * Предоставляет доступ к командной строке MSBuild

## <a name="examples"></a>Примеры

Инициализация образца консольного приложения .NET Core, которое можно скомпилировать и запустить:

`dotnet new`

Восстановление зависимостей для данного приложения:

`dotnet restore`

Сборка проекта и его зависимостей в указанном каталоге: 

`dotnet build`

Запуск переносимого приложения с именем `myapp.dll`: `dotnet myapp.dll`

## <a name="environment"></a>Среда 

`DOTNET_PACKAGES`

Основной кэш пакетов. Если значение не задано, по умолчанию используется путь $HOME/.nuget/packages в Unix или %HOME%\NuGet\Packages в Windows.

`DOTNET_SERVICING`

Задает расположение служебного индекса, который будет использоваться общим узлом при загрузке среды выполнения.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Указывает, собираются ли данные по использованию средств .NET Core для отправки в корпорацию Майкрософт. `true` для отказа от использования функции телеметрии (допускаются значения true, 1 или yes); в противном случае — `false` (допускаются значения false, 0 или no). Если значение не задано, то по умолчанию используется значение `false`, то есть функция телеметрии включена.




<!--HONumber=Nov16_HO3-->


