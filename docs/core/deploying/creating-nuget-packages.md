---
title: Создание пакета NuGet с помощью .NET Core CLI
description: Узнайте, как создать пакет NuGet с помощью команды dotnet pack.
author: cartermp
ms.date: 06/20/2016
ms.technology: dotnet-cli
ms.openlocfilehash: 3f8e75a501cfc48e1c416f71e91290cab1a4ffae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920922"
---
# <a name="how-to-create-a-nuget-package-with-the-net-core-cli"></a>Создание пакета NuGet с помощью .NET Core CLI

> [!NOTE]
> Ниже приведены примеры команд командной строки для Unix. Показанная здесь команда `dotnet pack` точно так же работает в Windows.

Библиотеки .NET Standard и .NET Core должны распространяться в виде пакетов NuGet. Именно так распространяются и используются все библиотеки .NET Standard. Проще всего это делать с помощью команды `dotnet pack`.

Представим, что вы только что создали полезную библиотеку, которую хотите распространить через NuGet. Для этого можно создать пакет NuGet с помощью кроссплатформенных средств. В приведенном ниже примере используется библиотека **SuperAwesomeLibrary**, предназначенная для `netstandard1.0`.

Если у вас есть транзитивные зависимости, то есть проекты, которые зависят от других пакетов, необходимо обязательно восстановить пакеты для всего решения с помощью команды `dotnet restore`, прежде чем создавать пакет NuGet. Если не сделать этого, команда `dotnet pack` будет работать неправильно.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Восстановив пакеты, можно перейти в каталог, где находится библиотека:

```console
cd src/SuperAwesomeLibrary
```

Затем нужно выполнить всего лишь одну команду в командной строке:

```dotnetcli
dotnet pack
```

Папка */bin/Debug* теперь будет выглядеть так:

```console
$ ls bin/Debug
netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

Обратите внимание на то, что при этом создается пакет, который можно отлаживать. Если вы хотите создать пакет NuGet с двоичными файлами выпуска, вам нужно просто добавить параметр `--configuration` (или `-c`) и использовать `release` в качестве аргумента.

```dotnetcli
dotnet pack --configuration release
```

В папке */bin* теперь будет папка *release*, содержащая пакет NuGet с двоичными файлами выпуска:

```console
$ ls bin/release
netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

теперь у вас есть все необходимые файлы для публикации пакета NuGet.

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a>Не путайте команду `dotnet pack` с командой `dotnet publish`.

Важно заметить, что команда `dotnet publish` в этом процессе не применяется. Команда `dotnet publish` предназначена для развертывания приложений со всеми зависимостями в одном пакете, а не для создания пакета NuGet, который будет распространяться и использоваться посредством NuGet.

## <a name="see-also"></a>См. также раздел

- [Краткое руководство. Создание и публикация пакета](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)
