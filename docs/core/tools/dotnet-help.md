---
title: Команда dotnet help
description: Команда dotnet help выводит более подробную документацию из Интернета для указанной команды.
ms.date: 02/14/2020
ms.openlocfilehash: f5d9221ae18653451a3bf97dc82fae396ae4e288
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503726"
---
# <a name="dotnet-help-reference"></a>Справочник по команде dotnet help

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.0 и более поздних версий

## <a name="name"></a>Имя

`dotnet help` — выводит более подробную документацию из Интернета для указанной команды.

## <a name="synopsis"></a>Краткий обзор

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a>Описание:

Команда `dotnet help` открывает страницу сайта docs.microsoft.com с подробной справочной информацией об указанной команде.

## <a name="arguments"></a>Аргументы

- **`COMMAND_NAME`**

  Имя команды интерфейса командной строки .NET Core. Список допустимых команд интерфейса командной строки см. в разделе [Команды CLI](index.md#cli-commands).

## <a name="options"></a>Параметры

- **`-h|--help`**

  Выводит краткую справку по команде.

## <a name="examples"></a>Примеры

- Открывает страницу документации по команде[dotnet new](dotnet-new.md):

  ```dotnetcli
  dotnet help new
  ```
