---
title: Команда dotnet nuget disable source
description: Команда dotnet nuget disable source отключает существующий источник в файлах конфигурации NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: 5aa16c842bcddeead180fdeec3d9dcdda33f7ed9
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148480"
---
# <a name="dotnet-nuget-disable-source"></a>dotnet nuget disable source

**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.1.200 и более поздних версий

## <a name="name"></a>name

`dotnet nuget disable source` — отключение источника NuGet.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet nuget disable source <NAME> [--configfile]
dotnet nuget disable source [-h|--help]
```

## <a name="description"></a>Описание

Команда `dotnet nuget disable source` отключает существующий источник в файлах конфигурации NuGet.

## <a name="arguments"></a>Аргументы

- **`NAME`**

  Имя источника.

## <a name="options"></a>Параметры

- **`--configfile`**

  Файл конфигурации NuGet. Если этот параметр указан, будут использоваться только параметры из этого файла. Если не указано, будет использоваться иерархия файлов конфигурации из текущего каталога. Дополнительные сведения см. в статье [Распространенные конфигурации NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

## <a name="examples"></a>Примеры

- Отключите источник с именем `mySource`:

  ```dotnetcli
  dotnet nuget disable source mySource
  ```

## <a name="see-also"></a>См. также

- [Разделы источников пакетов в файлах NuGet.config](/nuget/reference/nuget-config-file#package-source-sections)

- [Команда sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
