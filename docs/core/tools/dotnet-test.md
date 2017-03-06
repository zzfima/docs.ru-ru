---
title: "Команда dotnet-test | Microsoft Docs"
description: "Команда `dotnet test` служит для выполнения модульных тестов в проекте."
keywords: "dotnet-test, CLI, команда CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 3a0fa917-eb0a-4d7e-9217-d06e65455675
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 871a6f736272309f6fae74b06f437c7271df2321

---

#<a name="dotnet-test"></a>dotnet-test

> [!WARNING]
> Эта статья применима к инструментам .NET Core (предварительная версия 2). Сведения для версию-кандидата 4 средств .NET Core см. в разделе [dotnet-test (версия-кандидат 4 средств .NET Core)](../preview3/tools/dotnet-test.md).

## <a name="name"></a>Имя

`dotnet-test` — выполняет модульные тесты при помощи настроенного средства запуска тестов.

## <a name="synopsis"></a>Краткий обзор

`dotnet test [project] [--help] 
    [--parentProcessId] [--port] [--configuration]   
    [--output] [--build-base-path] [--framework] [--runtime]
    [--no-build]`  

## <a name="description"></a>Описание

Команда `dotnet test` служит для выполнения модульных тестов в проекте. Модульные тесты — это проекты библиотек классов, которые имеют зависимости от среды модульного тестирования (например, NUnit или xUnit) и средства запуска тестов dotnet для этой среды. Они упаковываются в пакеты NuGet и восстанавливаются как обычные зависимости проекта.

В тестовых проектах также должно быть указано свойство средства запуска тестов в файле project.json в узле testRunner. Это значение должно содержать имя среды модульного тестирования.

В следующем примере файла project.json показаны необходимые свойства:

```json
{
  "version": "1.0.0-*",
  "buildOptions": {
    "debugType": "portable"
  },
  "dependencies": {
    "System.Runtime.Serialization.Primitives": "4.1.1",
    "xunit": "2.1.0",
    "dotnet-test-xunit": "1.0.0-rc2-192208-24"
  },
  "testRunner": "xunit",
  "frameworks": {
    "netcoreapp1.0": {
      "dependencies": {
        "Microsoft.NETCore.App": {
          "type": "platform",
          "version": "1.0.0"
        }
      },
      "imports": [
        "dotnet5.4",
        "portable-net451+win8"
      ]
    }
  }
}
```

`dotnet test` поддерживает два режима работы.

1. Консольный: в консольном режиме команда `dotnet test` просто полностью выполняет все передаваемые ей команды и выводит результаты. При каждом вызове команды `dotnet test` без указания параметра -port она выполняется в консольном режиме, что, в свою очередь, приводит к выполнению средства запуска в консольном режиме.
2. Во время разработки: используется в контексте других средств, таких как редакторы или интегрированные среды разработки (IDE). Узнать больше об этом режиме можно в документе [Протокол dotnet-test](test-protocol.md). 

## <a name="options"></a>Параметры

`[project]`
    
Указывает путь к тестовому проекту. Если значение не задано, по умолчанию используется текущий каталог.

`-?|-h|--help`

Выводит краткую справку по команде.

`--parentProcessId`

Используется средой IDE для указания ее идентификатора процесса. Тест завершается, если завершается родительский процесс.

`--port`

Используется средой IDE с целью указания номера порта для прослушивания подключения.

`-c|--configuration <Debug|Release>`

Конфигурация для сборки. Значение по умолчанию — `Release`. 

`-o|--output [OUTPUT_DIRECTORY]`

Каталог, в котором выполняется поиск двоичных файлов для выполнения.

`-b|--build-base-path <OUTPUT_DIRECTORY>`

Каталог, в который будут помещаться временные выходные данные.

`-f|--framework [FRAMEWORK]`

Поиск тестовых двоичных файлов для определенной платформы.

`-r|--runtime [RUNTIME_IDENTIFIER]`

Поиск тестовых двоичных файлов для указанной среды выполнения.

`--no-build` 

Не выполняет сборку тестового проекта перед его запуском. 

## <a name="examples"></a>Примеры

Выполнение тестов в проекте в текущем каталоге:

`dotnet test` 

Выполнение тестов в проекте test1:

`dotnet test /projects/test1/project.json` 

## <a name="see-also"></a>См. также

[Протокол связи dotnet-test](test-protocol.md)

[Платформы](../../standard/frameworks.md)

[Каталог идентификаторов сред выполнения (RID)](../rid-catalog.md)


<!--HONumber=Feb17_HO2-->


