---
title: Команда dotnet build-server — .NET Core CLI
description: Команда dotnet build-server взаимодействует с серверами, запущенными сборкой.
author: mairaw
ms.author: mairaw
ms.date: 07/02/2018
ms.openlocfilehash: 1c59c85f246b79c7e2552f704db5b4f076f9b502
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404337"
---
# <a name="dotnet-build-server"></a>dotnet build-server

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>name

`dotnet build-server` — взаимодействует с серверами, запущенными сборкой.

## <a name="synopsis"></a>Краткий обзор

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a>Команды

`shutdown`

Завершает работу серверов сборки, запущенных командой dotnet. По умолчанию все серверы завершают работу.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.

`--msbuild`

Завершает работу сервера сборки MSBuild.

`--razor`

Завершает работу сервера сборки Razor.

`--vbcscompiler`

Завершает работу сервера сборки компилятора VB/C#.
