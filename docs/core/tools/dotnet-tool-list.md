---
title: Команда dotnet tool list — .NET Core CLI
description: Команда dotnet tool list показывает указанное глобальное средство .NET Core на вашем компьютере.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: e2bea974207d3098ed67b69ed16a72a03c44cd8b
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2018
ms.locfileid: "48841246"
---
# <a name="dotnet-tool-list"></a>dotnet tool list

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>name

`dotnet tool list` — выводит все [глобальные средства .NET Core](global-tools.md), установленные в каталоге по умолчанию на вашем компьютере или по указанному пути.

## <a name="synopsis"></a>Краткий обзор

```console
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list <-h|--help>
```

## <a name="description"></a>Описание:

Команда `dotnet tool list` позволяет просмотреть все глобальные средства .NET Core, установленные на уровне пользователя на компьютере (для текущего профиля пользователя) или по указанному пути. Эта команда выводит имя пакета, установленную версию и команду глобального средства. Чтобы использовать эту команду, укажите вывод средств на уровне пользователя с помощью параметра `--global` или укажите другой путь с помощью параметра `--tool-path`.

## <a name="options"></a>Параметры

`-g|--global`

Выводит глобальные средства на уровне пользователя. Не может использоваться вместе с параметром `--tool-path`. Если вы не укажете этот параметр, укажите параметр `--tool-path`.

`-h|--help`

Выводит краткую справку по команде.

`--tool-path <PATH>`

Задает пользовательское расположение для глобальных средств. Путь может быть абсолютным или относительным. Не может использоваться вместе с параметром `--global`. Если вы не укажете этот параметр, укажите параметр `--global`.

## <a name="examples"></a>Примеры

Выводит все глобальные средства, установленные на уровне пользователя на вашем компьютере (для текущего профиля пользователя):

`dotnet tool list -g`

Выводит глобальные средства в определенной папке Windows:

`dotnet tool list --tool-path c:\global-tools`

Выводит глобальные средства в определенной папке Linux/macOS:

`dotnet tool list --tool-path ~/bin`

## <a name="see-also"></a>См. также

* [Глобальные средства .NET Core](global-tools.md)