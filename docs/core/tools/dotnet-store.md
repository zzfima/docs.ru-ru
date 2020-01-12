---
title: Команда dotnet store
description: Команда dotnet store сохраняет указанные сборки в хранилище пакетов среды выполнения.
author: bleroy
ms.date: 05/29/2018
ms.openlocfilehash: 3a81e06f36ffbed68b7cc35de47aa5dca32bab6e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714201"
---
# <a name="dotnet-store"></a>dotnet store

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a>name

`dotnet store` — сохраняет указанные сборки в [хранилище пакетов среды выполнения](../deploying/runtime-store.md).

## <a name="synopsis"></a>Краткий обзор

`dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]`

## <a name="description"></a>Описание

`dotnet store` — сохраняет указанные сборки в [хранилище пакетов среды выполнения](../deploying/runtime-store.md). По умолчанию сборки оптимизируются для целевой среды выполнения и платформы. Дополнительные сведения см. в разделе, посвященном [хранилищу пакетов среды выполнения](../deploying/runtime-store.md).

## <a name="required-options"></a>Обязательные параметры

`-f|--framework <FRAMEWORK>`

Задает [целевую платформу](../../standard/frameworks.md).

`-m|--manifest <PATH_TO_MANIFEST_FILE>`

*Файл манифеста хранилища пакетов* — это XML-файл, содержащий список сохраняемых пакетов. Формат файла манифеста совместим с форматом проекта в стиле SDK. Поэтому файл проекта, ссылающийся на требуемые пакеты, можно использовать с параметром `-m|--manifest` для сохранения сборок в хранилище пакетов среды выполнения. Чтобы указать несколько файлов манифеста, добавьте параметр и путь для каждого из них. Например, `--manifest packages1.csproj --manifest packages2.csproj`.

`-r|--runtime <RUNTIME_IDENTIFIER>`

[Идентификатор целевой среды выполнения](../rid-catalog.md).

## <a name="optional-options"></a>Необязательные параметры

`--framework-version <FRAMEWORK_VERSION>`

Указывает версию пакета SDK для .NET Core. Этот параметр позволяет выбрать определенную версию платформы, отличную от версии, заданной с помощью параметра `-f|--framework`.

`-h|--help`

Выводит справочные сведения.

`-o|--output <OUTPUT_DIRECTORY>`

Определяет путь к хранилищу пакетов среды выполнения. Если значение не указано, по умолчанию используется подкаталог *store* каталога установки .NET Core в профиле пользователя.

`--skip-optimization`

Пропуск этапа оптимизации.

`--skip-symbols`

Пропуск создания символов. В настоящее время символы можно создавать только в Windows и Linux.

`-v|--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

`-w|--working-dir <INTERMEDIATE_WORKING_DIRECTORY>`

Рабочий каталог, используемый командой. Если значение не указано, используется подкаталог *obj* в текущем каталоге.

## <a name="examples"></a>Примеры

Сохранение пакетов, указанных в файле проекта *packages.csproj* для .NET Core 2.0.0:

`dotnet store --manifest packages.csproj --framework-version 2.0.0`

Сохранение пакетов, указанных в файле *packages.csproj*, без оптимизации:

`dotnet store --manifest packages.csproj --skip-optimization`

## <a name="see-also"></a>См. также

- [Хранилище пакетов среды выполнения](../deploying/runtime-store.md)
