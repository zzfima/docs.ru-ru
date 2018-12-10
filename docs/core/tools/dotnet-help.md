---
title: Команда dotnet help — CLI .NET Core
description: Команда dotnet help выводит более подробную документацию из Интернета для указанной команды.
ms.date: 12/04/2018
ms.openlocfilehash: 60d1cc706ca5c78fa3be877bd679888181213e88
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152179"
---
# <a name="dotnet-help-reference"></a>Справочник по команде dotnet help

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a>name

`dotnet help` — выводит более подробную документацию из Интернета для указанной команды.

## <a name="synopsis"></a>Краткий обзор

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a>Описание

Команда `dotnet help` открывает страницу сайта docs.microsoft.com с подробной справочной информацией об указанной команде.

## <a name="arguments"></a>Аргументы

* **`COMMAND_NAME`**

  Имя команды интерфейса командной строки .NET Core. Список допустимых команд интерфейса командной строки см. в разделе [Команды CLI](index.md#cli-commands).

## <a name="options"></a>Параметры

* **`-h|--help`**

  Выводит краткую справку по команде.

## <a name="examples"></a>Примеры

* Открывает страницу документации по команде[dotnet new](dotnet-new.md):

  ```console
  dotnet help new
  ```