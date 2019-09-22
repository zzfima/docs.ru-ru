---
title: Команда dotnet tool list
description: Команда dotnet tool list показывает указанное глобальное средство .NET Core на вашем компьютере.
ms.date: 05/29/2018
ms.openlocfilehash: 6d35b1dce0c6d57edb0c6dd5f9711f093bc804aa
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117566"
---
# <a name="dotnet-tool-list"></a>dotnet tool list

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>name

`dotnet tool list` — выводит все [глобальные средства .NET Core](global-tools.md), установленные в каталоге по умолчанию на вашем компьютере или по указанному пути.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list <-h|--help>
```

## <a name="description"></a>ОПИСАНИЕ

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

- [Глобальные средства .NET Core](global-tools.md)
