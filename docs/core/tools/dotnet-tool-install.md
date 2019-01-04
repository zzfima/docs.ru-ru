---
title: Команда dotnet tool install
description: Команда dotnet tool install устанавливает указанное глобальное средство .NET Core на компьютер.
ms.date: 05/29/2018
ms.openlocfilehash: 251e7b04be96ac2340727fa03dbaa2d548110fa9
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168719"
---
# <a name="dotnet-tool-install"></a>dotnet tool install

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>name

`dotnet tool install` устанавливает указанное [глобальное средство .NET Core](global-tools.md) на компьютер.

## <a name="synopsis"></a>Краткий обзор

```console
dotnet tool install <PACKAGE_NAME> <-g|--global> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> <--tool-path> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <-h|--help>
```

## <a name="description"></a>Описание

Команда `dotnet tool install` предоставляет способ установки глобальных средств .NET Core на компьютере. Чтобы использовать эту команду, укажите установку уровня пользователя с помощью параметра `--global` или укажите путь к месту установки с помощью параметра `--tool-path`.

Глобальные средства устанавливаются в следующие каталоги по умолчанию при выборе параметра `-g` (или `--global`):

| Операционная система          | Путь                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

## <a name="arguments"></a>Аргументы

`PACKAGE_NAME`

Имя или идентификатор пакета NuGet, который содержит устанавливаемое глобальное средство .NET Core.

## <a name="options"></a>Параметры

`--add-source <SOURCE>`

Добавляет дополнительный источник пакета NuGet для использования во время установки.

`--configfile <FILE>`

Файл конфигурации NuGet (*nuget.config*), который будет использоваться.

`--framework <FRAMEWORK>`

Указывает [требуемую версию .NET Framework](../../standard/frameworks.md) для установки средства. По умолчанию пакет SDK для .NET Core пытается выбрать наиболее подходящую версию .NET Framework.

`-g|--global`

Указывает, что установка происходит на уровне пользователя. Не может использоваться вместе с параметром `--tool-path`. Если вы не укажете этот параметр, укажите параметр `--tool-path`.

`-h|--help`

Выводит краткую справку по команде.

`--tool-path <PATH>`

Указывает место установки глобального средства. Путь может быть абсолютным или относительным. Если путь не существует, команда пытается создать его. Не может использоваться вместе с параметром `--global`. Если вы не укажете этот параметр, укажите параметр `--global`.

`-v|--verbosity <LEVEL>`

Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

`--version <VERSION_NUMBER>`

Версия средства для установки. По умолчанию устанавливается последняя стабильная версия пакета. Используйте этот параметр для установки предварительной версии или предыдущей версии средства.

## <a name="examples"></a>Примеры

Устанавливает глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) в расположении по умолчанию:

`dotnet tool install -g dotnetsay`

Устанавливает глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) в определенную папку Windows:

`dotnet tool install dotnetsay --tool-path c:\global-tools`

Устанавливает глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) в определенную папку Linux/macOS:

`dotnet tool install dotnetsay --tool-path ~/bin`

Устанавливает версию 2.0.0 глобального средства [dotnetsay](https://www.nuget.org/packages/dotnetsay/):

`dotnet tool install -g dotnetsay --version 2.0.0`

## <a name="see-also"></a>См. также

* [Глобальные средства .NET Core](global-tools.md)