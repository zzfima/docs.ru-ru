---
title: Команда dotnet build-server
description: Команда dotnet build-server взаимодействует с серверами, запущенными сборкой.
ms.date: 02/14/2020
ms.openlocfilehash: a6a9cd6de66371caef66d1101b3f844dffc771ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503775"
---
# <a name="dotnet-build-server"></a>dotnet build-server

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий

## <a name="name"></a>Имя

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
