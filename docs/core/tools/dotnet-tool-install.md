---
title: Команда dotnet tool install
description: Команда dotnet tool install устанавливает указанное средство .NET Core на компьютер.
ms.date: 02/14/2020
ms.openlocfilehash: 1e142773d1f981a8dc3b552d5a23d2864cdd82c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146467"
---
# <a name="dotnet-tool-install"></a>dotnet tool install

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий

## <a name="name"></a>name

`dotnet tool install` устанавливает указанное [средство .NET Core](global-tools.md) на компьютер.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet tool install <PACKAGE_NAME> <-g|--global>
    [--add-source] [--configfile] [--framework]
    [-v|--verbosity] [--version]

dotnet tool install <PACKAGE_NAME> <--tool-path>
    [--add-source] [--configfile] [--framework]
    [-v|--verbosity] [--version]

dotnet tool install <PACKAGE_NAME>
    [--add-source] [--configfile] [--framework]
    [-v|--verbosity] [--version]

dotnet tool install <-h|--help>
```

## <a name="description"></a>Описание

Команда `dotnet tool install` предоставляет способ установки средств .NET Core на компьютере. Чтобы использовать команду, укажите один из следующих параметров установки:

* Чтобы установить глобальный инструмент в расположение по умолчанию, используйте параметр `--global`.
* Чтобы установить глобальный инструмент в расположение, указанное пользователем, используйте параметр `--tool-path`.
* Чтобы установить локальный инструмент, пропустите параметры `--global` и `--tool-path`.

**Локальные средства доступны в пакете SDK для .NET Core, начиная с версии 3.0.**

Глобальные средства устанавливаются в следующие каталоги по умолчанию при выборе параметра `-g` или `--global`:

| Операционная система          | Path                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

Локальные средства добавляются в файл *tool-manifest.json* в каталоге *. config* в текущем каталоге. Если файл манифеста еще не существует, создайте его, выполнив следующую команду:

```dotnetcli
dotnet new tool-manifest
```

Дополнительные сведения см. в разделе [Установка глобального средства](global-tools.md#install-a-local-tool).

## <a name="arguments"></a>Аргументы

- **`PACKAGE_NAME`**

  Имя или идентификатор пакета NuGet, который содержит устанавливаемое средство .NET Core.

## <a name="options"></a>Параметры

- **`add-source <SOURCE>`**

  Добавляет дополнительный источник пакета NuGet для использования во время установки.

- **`configfile <FILE>`**

  Файл конфигурации NuGet (*nuget.config*), который будет использоваться.

- **`framework <FRAMEWORK>`**

  Указывает [требуемую версию .NET Framework](../../standard/frameworks.md) для установки средства. По умолчанию пакет SDK для .NET Core пытается выбрать наиболее подходящую версию .NET Framework.

- **`-g|--global`**

  Указывает, что установка происходит на уровне пользователя. Не может использоваться вместе с параметром `--tool-path`. Пропуск параметров `--global` и `--tool-path` задает установку локального средства.

- **`-h|--help`**

  Выводит краткую справку по команде.

- **`tool-path <PATH>`**

  Указывает место установки глобального средства. Путь может быть абсолютным или относительным. Если путь не существует, команда пытается создать его. Пропуск параметров `--global` и `--tool-path` задает установку локального средства.

- **`-v|--verbosity <LEVEL>`**

  Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

- **`--version <VERSION_NUMBER>`**

  Версия средства для установки. По умолчанию устанавливается последняя стабильная версия пакета. Используйте этот параметр для установки предварительной версии или предыдущей версии средства.

## <a name="examples"></a>Примеры

- **`dotnet tool install -g dotnetsay`**

  Устанавливает глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) в расположении по умолчанию.

- **`dotnet tool install dotnetsay --tool-path c:\global-tools`**

  Устанавливает [dotnetsay](https://www.nuget.org/packages/dotnetsay/) в качестве глобального инструмента в определенном каталоге Windows.

- **`dotnet tool install dotnetsay --tool-path ~/bin`**

  Устанавливает [dotnetsay](https://www.nuget.org/packages/dotnetsay/) в качестве глобального инструмента в определенном каталоге Linux/macOS.

- **`dotnet tool install -g dotnetsay --version 2.0.0`**

  Устанавливает версию 2.0.0 в качестве глобального средства [dotnetsay](https://www.nuget.org/packages/dotnetsay/):

- **`dotnet tool install dotnetsay`**

  Устанавливает [dotnetsay](https://www.nuget.org/packages/dotnetsay/) в качестве локального средства для текущего каталога.

## <a name="see-also"></a>См. также

- [Средства .NET Core](global-tools.md)
- [Учебник. Установка и использование глобального средства .NET Core с помощью интерфейса командной строки .NET Core](global-tools-how-to-use.md)
- [Учебник. Установка и использование локального средства .NET Core с помощью интерфейса командной строки .NET Core](local-tools-how-to-use.md)
