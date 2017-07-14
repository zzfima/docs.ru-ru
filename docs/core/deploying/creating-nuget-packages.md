---
title: "Создание пакета NuGet с помощью кроссплатформенных средств | Документация Майкрософт"
description: "Создание пакета NuGet с помощью кроссплатформенных средств"
keywords: .NET, .NET Core, NuGet
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 2f0415c1-110b-433d-87c1-ae3d543a8844
ms.translationtype: Human Translation
ms.sourcegitcommit: 4437ce5d344cf06d30e31911def6287999fc6ffc
ms.openlocfilehash: 2b2081bce1725fb4a019881521604e4171b85028
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017

---

# Создание пакета NuGet с помощью кроссплатформенных средств
<a id="how-to-create-a-nuget-package-with-cross-platform-tools" class="xliff"></a>

> [!NOTE]
> Ниже приведены примеры команд командной строки для Unix.  Показанная здесь команда `dotnet pack` точно так же работает в Windows.

Для .NET Core 1.0 библиотеки должны распространяться в виде пакетов NuGet.  Именно так распространяются и используются все библиотеки .NET Standard.  Проще всего это делать с помощью команды `dotnet pack`.

Представим, что вы только что создали полезную библиотеку, которую хотите распространить через NuGet.  Для этого можно создать пакет NuGet с помощью кроссплатформенных средств.  В приведенном ниже примере используется библиотека **SuperAwesomeLibrary**, предназначенная для `netstandard1.0`.

Если у вас есть транзитивные зависимости, то есть проекты, которые зависят от других проектов, необходимо обязательно восстановить пакеты для всего решения с помощью команды `dotnet restore`, прежде чем создавать пакет NuGet.  Если не сделать этого, команда `dotnet pack` будет работать неправильно.

Восстановив пакеты, можно перейти в каталог, где находится библиотека:

`$ cd src/SuperAwesomeLibrary`

Затем нужно выполнить всего лишь одну команду в командной строке:
    
`$ dotnet pack`

Папка `/bin/Debug` теперь будет выглядеть так:

```
$ ls bin/Debug

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

Обратите внимание на то, что при этом создается пакет, который можно отлаживать.  Если вы хотите создать пакет NuGet с двоичными файлами выпуска, вам нужно просто добавить параметр `-c`/`--configuration` и использовать `release` в качестве аргумента.

`$ dotnet pack --configuration release`

В папке `/bin` теперь будет папка `release`, содержащая пакет NuGet с двоичными файлами выпуска:

```
$ ls bin/release

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

теперь у вас есть все необходимые файлы для публикации пакета NuGet.

## Не путайте команду `dotnet pack` с командой `dotnet publish`.
<a id="dont-confuse-dotnet-pack-with-dotnet-publish" class="xliff"></a>

Важно заметить, что команда `dotnet publish` в этом процессе не применяется.  Команда `dotnet publish` предназначена для развертывания приложений со всеми зависимостями в одном пакете, а не для создания пакета NuGet, который будет распространяться и использоваться посредством NuGet.

