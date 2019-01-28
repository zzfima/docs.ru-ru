---
title: Команда dotnet tool uninstall
description: Команда dotnet tool uninstall удаляет указанное глобальное средство .NET Core с компьютера.
ms.date: 05/29/2018
ms.openlocfilehash: 4d53d305131e3399ab5d9c19f9319f3ba3544c19
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680927"
---
# <a name="dotnet-tool-uninstall"></a>dotnet tool uninstall

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>name

`dotnet tool uninstall` — удаляет указанное [глобальное средство .NET Core](global-tools.md) с компьютера.

## <a name="synopsis"></a>Краткий обзор

```console
dotnet tool uninstall <PACKAGE_NAME> <-g|--global>
dotnet tool uninstall <PACKAGE_NAME> <--tool-path>
dotnet tool uninstall <-h|--help>
```

## <a name="description"></a>Описание

Команда `dotnet tool uninstall` позволяет удалить глобальные средства .NET Core с компьютера. Чтобы использовать эту команду, укажите, что хотите удалить средство на уровне пользователя, с помощью параметра `--global`, или укажите путь к расположению средства с помощью параметра `--tool-path`.

## <a name="arguments"></a>Аргументы

`PACKAGE_NAME`

Имя или идентификатор пакета NuGet, который содержит глобальное средство .NET Core, которое вы хотите удалить. Найти имя пакета можно с помощью команды [dotnet tool list](dotnet-tool-list.md).

## <a name="options"></a>Параметры

`-g|--global`

Указывает, что средство будет удалено из установки на уровне пользователя. Не может использоваться вместе с параметром `--tool-path`. Если вы не укажете этот параметр, укажите параметр `--tool-path`.

`-h|--help`

Выводит краткую справку по команде.

`--tool-path <PATH>`

Указывает место, откуда будет удалено глобальное средство. Путь может быть абсолютным или относительным. Не может использоваться вместе с параметром `--global`. Если вы не укажете этот параметр, укажите параметр `--global`.

## <a name="examples"></a>Примеры

Удаляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/):

`dotnet tool uninstall -g dotnetsay`

Удаляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) из определенной папки Windows:

`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`

Удаляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) из определенной папки Linux/macOS:

`dotnet tool uninstall dotnetsay --tool-path ~/bin`

## <a name="see-also"></a>См. также

- [Глобальные средства .NET Core](global-tools.md)
