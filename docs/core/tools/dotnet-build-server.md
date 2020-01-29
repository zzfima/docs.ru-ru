---
title: Команда dotnet build-server
description: Команда dotnet build-server взаимодействует с серверами, запущенными сборкой.
ms.date: 04/24/2019
ms.openlocfilehash: e77a4d9f49f555ac847bb13380380599eef881b1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734374"
---
# <a name="dotnet-build-server"></a>dotnet build-server

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a>name

`dotnet build-server` — взаимодействует с серверами, запущенными сборкой.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a>Команды

- **`shutdown`**

  Завершает работу серверов сборки, запущенных командой dotnet. По умолчанию все серверы завершают работу.

## <a name="options"></a>Параметры

- **`-h|--help`**

  Выводит краткую справку по команде.

- **`--msbuild`**

  Завершает работу сервера сборки MSBuild.

- **`--razor`**

  Завершает работу сервера сборки Razor.

- **`--vbcscompiler`**

  Завершает работу сервера сборки компилятора VB/C#.
