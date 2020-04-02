---
title: Команда dotnet nuget list source
description: Команда dotnet nuget list source выводит список всех существующих источников в файлах конфигурации NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: 4d7bc3dbd3ab5eb14c1ebf592044b685d28355cd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148498"
---
# <a name="dotnet-nuget-list-source"></a>dotnet nuget list source

**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.1.200 и более поздних версий

## <a name="name"></a>name

`dotnet nuget list source` — перечисляет все настроенные источники NuGet.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet nuget list source [--format] [--configfile]
dotnet nuget list source [-h|--help]
```

## <a name="description"></a>Описание

Команда `dotnet nuget list source` перечисляет все существующие источники из файлов конфигурации NuGet.

## <a name="options"></a>Параметры

- **`--configfile`**

  Файл конфигурации NuGet. Если этот параметр указан, будут использоваться только параметры из этого файла. Если не указано, будет использоваться иерархия файлов конфигурации из текущего каталога. Дополнительные сведения см. в статье [Распространенные конфигурации NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

- **`--format`**

  Формат выходных данных команды list: `Detailed` (по умолчанию) и `Short`.

## <a name="examples"></a>Примеры

- Список настроенных источников из текущего каталога:

  ```dotnetcli
  dotnet nuget list source
  ```

## <a name="see-also"></a>См. также

- [Разделы источников пакетов в файлах NuGet.config](/nuget/reference/nuget-config-file#package-source-sections)

- [Команда sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
