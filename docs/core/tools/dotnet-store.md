---
title: Команда dotnet store
description: Команда dotnet store сохраняет указанные сборки в хранилище пакетов среды выполнения.
ms.date: 02/14/2020
ms.openlocfilehash: da1d132b2b873ff55ec104b5bb092d0194889bdc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503581"
---
# <a name="dotnet-store"></a>dotnet store

**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий

## <a name="name"></a>Имя

`dotnet store` — сохраняет указанные сборки в [хранилище пакетов среды выполнения](../deploying/runtime-store.md).

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]
```

## <a name="description"></a>Описание:

`dotnet store` — сохраняет указанные сборки в [хранилище пакетов среды выполнения](../deploying/runtime-store.md). По умолчанию сборки оптимизируются для целевой среды выполнения и платформы. Дополнительные сведения см. в разделе, посвященном [хранилищу пакетов среды выполнения](../deploying/runtime-store.md).

## <a name="required-options"></a>Обязательные параметры

- **`-f|--framework <FRAMEWORK>`**

  Задает [целевую платформу](../../standard/frameworks.md). Целевая платформа должна быть указана в файле проекта.

- **`-m|--manifest <PATH_TO_MANIFEST_FILE>`**

  *Файл манифеста хранилища пакетов* — это XML-файл, содержащий список сохраняемых пакетов. Формат файла манифеста совместим с форматом проекта в стиле SDK. Поэтому файл проекта, ссылающийся на требуемые пакеты, можно использовать с параметром `-m|--manifest` для сохранения сборок в хранилище пакетов среды выполнения. Чтобы указать несколько файлов манифеста, добавьте параметр и путь для каждого из них. Пример: `--manifest packages1.csproj --manifest packages2.csproj`.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  [Идентификатор целевой среды выполнения](../rid-catalog.md).

## <a name="optional-options"></a>Необязательные параметры

- **`--framework-version <FRAMEWORK_VERSION>`**

  Указывает версию пакета SDK для .NET Core. Этот параметр позволяет выбрать определенную версию платформы, отличную от версии, заданной с помощью параметра `-f|--framework`.

- **`-h|--help`**

  Выводит справочные сведения.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Определяет путь к хранилищу пакетов среды выполнения. Если значение не указано, по умолчанию используется подкаталог *store* каталога установки .NET Core в профиле пользователя.

- **`--skip-optimization`**

  Пропуск этапа оптимизации.

- **`--skip-symbols`**

  Пропуск создания символов. В настоящее время символы можно создавать только в Windows и Linux.

- **`-v|--verbosity <LEVEL>`**

  Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

- **`-w|--working-dir <WORKING_DIRECTORY>`**

  Рабочий каталог, используемый командой. Если значение не указано, используется подкаталог *obj* в текущем каталоге.

## <a name="examples"></a>Примеры

- Сохранение пакетов, указанных в файле проекта *packages.csproj* для .NET Core 2.0.0:

  ```dotnetcli
  dotnet store --manifest packages.csproj --framework-version 2.0.0
  ```

- Сохранение пакетов, указанных в файле *packages.csproj*, без оптимизации:

  ```dotnetcli
  dotnet store --manifest packages.csproj --skip-optimization
  ```

## <a name="see-also"></a>См. также раздел

- [Хранилище пакетов среды выполнения](../deploying/runtime-store.md)
