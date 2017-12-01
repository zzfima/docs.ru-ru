---
title: "Команда dotnet publish — CLI .NET Core"
description: "Команда dotnet publish публикует проект .NET Core в каталоге."
author: mairaw
ms.author: mairaw
ms.date: 09/01/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: d59ba8cf74a63c7d4a2234989477b5778fa0148f
ms.sourcegitcommit: a19548e5167cbe7e9e58df4ffd8c3b23f17d5c7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2017
---
# <a name="dotnet-publish"></a>dotnet publish

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Имя

`dotnet publish` — упаковывает приложение и его зависимости в папку для развертывания на размещающей системе.

## <a name="synopsis"></a>Краткий обзор

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [no-dependencies] [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a>Описание

`dotnet publish` компилирует приложение, считывает его зависимости, указанные в файле проекта, и публикует итоговый набор файлов в каталоге. Выходные данные будут содержать следующее.

* Код на промежуточном языке (IL) в сборке с расширением *DLL*.
* Файл *.deps.json*, содержащий все зависимости проекта.
* Файл *.runtime.config.json*, указывающий общую среду выполнения, которую ожидает приложение, а также другие параметры конфигурации для среды выполнения (например, тип сборки мусора).
* Зависимости приложения. Они копируются из кэша NuGet в выходную папку.

Выходных данных команды `dotnet publish` готовы к развертыванию на размещающей системе (например, на сервере, компьютере, ноутбуке Mac) для выполнения и являются единственным официально поддерживаемым способом подготовить приложение к развертыванию. В зависимости от указанного в проекте типа развертывания размещающая система может как иметь, так и не иметь общую среду выполнения .NET Core. Дополнительные сведения см. в разделе [Развертывание приложений .NET Core](../deploying/index.md). Структуру каталогов опубликованного приложения см. в разделе [Структура каталогов](/aspnet/core/hosting/directory-structure).

## <a name="arguments"></a>Аргументы

`PROJECT`

Публикуемый проект. Если параметр не задан, по умолчанию используется текущий каталог.

## <a name="options"></a>Параметры

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

Определяет конфигурацию сборки. Значение по умолчанию — `Debug`.

`-f|--framework <FRAMEWORK>`

Публикует приложение для указанной [целевой платформы](../../standard/frameworks.md). Вам нужно указать целевую платформу в файле проекта.

`--force`

Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно. Равносильно удалению файла *project.assets.json*.

`-h|--help`

Выводит краткую справку по команде.

`--manifest <PATH_TO_MANIFEST_FILE>`

Определяет один или несколько [целевых манифестов](../deploying/runtime-store.md) для усечения множества пакетов, публикуемых вместе с приложением. Файл манифеста является частью выходных данных [команды `dotnet store`](dotnet-store.md). Чтобы указать несколько манифестов, добавьте параметр `--manifest` для каждого из них. Этот параметр доступен начиная с пакета SDK для .NET Core 2.0.

`--no-dependencies`

Межпроектные ссылки игнорируются, и восстанавливается только корневой проект.

`--no-restore`

Не выполняет неявное восстановление при выполнении команды.

`-o|--output <OUTPUT_DIRECTORY>`

Задает путь для выходного каталога. Если значение не задано, по умолчанию используется путь *./bin/[configuration]/[framework]/* для платформозависимого развертывания или *./bin/[configuration]/[framework]/[runtime]* для автономного.
Если указан относительный путь, созданный выходной каталог задается относительно расположения файла проекта, не в текущем рабочем каталоге.

`--self-contained`

Публикует среду выполнения .NET Core вместе с приложением, что позволяет не устанавливать ее на конечном компьютере. Если указывается идентификатор среды выполнения, его значение по умолчанию — `true`. Дополнительные сведения о типах развертывания см. в разделе [развертывание приложений .NET Core](../deploying/index.md).

`-r|--runtime <RUNTIME_IDENTIFIER>`

Публикует приложение для данной среды выполнения. Используется при создании [автономного развертывания](../deploying/index.md#self-contained-deployments-scd). Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md). По умолчанию публикуется [платформозависимое приложение](../deploying/index.md#framework-dependent-deployments-fdd).

`-v|--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Определяет суффикс версии для замены звездочки (`*`) в поле версия файла проекта.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

Определяет конфигурацию сборки. Значение по умолчанию — `Debug`.

`-f|--framework <FRAMEWORK>`

Публикует приложение для указанной [целевой платформы](../../standard/frameworks.md). Вам нужно указать целевую платформу в файле проекта.

`-h|--help`

Выводит краткую справку по команде.

`--manifest <PATH_TO_MANIFEST_FILE>`

Определяет один или несколько [целевых манифестов](../deploying/runtime-store.md) для усечения множества пакетов, публикуемых вместе с приложением. Файл манифеста является частью выходных данных [команды `dotnet store`](dotnet-store.md). Чтобы указать несколько манифестов, добавьте параметр `--manifest` для каждого из них. Этот параметр доступен начиная с пакета SDK для .NET Core 2.0.

`-o|--output <OUTPUT_DIRECTORY>`

Задает путь для выходного каталога. Если значение не задано, по умолчанию используется путь *./bin/[configuration]/[framework]/* для платформозависимого развертывания или *./bin/[configuration]/[framework]/[runtime]* для автономного.
Если указан относительный путь, созданный выходной каталог задается относительно расположения файла проекта, не в текущем рабочем каталоге.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Публикует приложение для данной среды выполнения. Используется при создании [автономного развертывания](../deploying/index.md#self-contained-deployments-scd). Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md). По умолчанию публикуется [платформозависимое приложение](../deploying/index.md#framework-dependent-deployments-fdd).

`-v|--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Определяет суффикс версии для замены звездочки (`*`) в поле версия файла проекта.

---

## <a name="examples"></a>Примеры

Публикация проекта в текущем каталоге:

`dotnet publish`

Публикация приложения с использованием указанного файла проекта:

`dotnet publish ~/projects/app1/app1.csproj`
    
Публикация проекта в текущем каталоге с использованием платформы `netcoreapp1.1`:

`dotnet publish --framework netcoreapp1.1`
    
Публикация текущего приложения с использованием платформы `netcoreapp1.1` и среды выполнения для `OS X 10.10` (вам нужно указать этот идентификатор RID в файле проекта).

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

## <a name="see-also"></a>См. также

* [Целевые платформы](../../standard/frameworks.md)
* [Каталог идентификаторов сред выполнения (RID)](../rid-catalog.md)
