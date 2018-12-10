---
title: Команда dotnet build-server — .NET Core CLI
description: Команда dotnet build-server взаимодействует с серверами, запущенными сборкой.
ms.date: 12/04/2018
ms.openlocfilehash: 2746ade12cc819089258483e84a8c0f02a64c755
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53125682"
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

* **`shutdown`**

  Завершает работу серверов сборки, запущенных командой dotnet. По умолчанию все серверы завершают работу.

## <a name="options"></a>Параметры

* **`-h|--help`**

  Выводит краткую справку по команде.

* **`--msbuild`**

  Завершает работу сервера сборки MSBuild.

* **`--razor`**

  Завершает работу сервера сборки Razor.

* **`--vbcscompiler`**

  Завершает работу сервера сборки компилятора VB/C#.