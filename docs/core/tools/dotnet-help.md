---
title: Команда dotnet help — CLI .NET Core
description: Команда dotnet help выводит более подробную документацию из Интернета для указанной команды.
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: ed152717e32ffb294f5d5bd8e5eb74d55e33e506
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696602"
---
# <a name="dotnet-help-reference"></a>Справочник по команде dotnet help

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a>name

`dotnet help` — выводит более подробную документацию из Интернета для указанной команды.

## <a name="synopsis"></a>Краткий обзор

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a>Описание:

Команда `dotnet help` открывает страницу сайта docs.microsoft.com с подробной справочной информацией об указанной команде.

## <a name="arguments"></a>Аргументы

`COMMAND_NAME`

Имя команды интерфейса командной строки .NET Core. Список допустимых команд интерфейса командной строки см. в разделе [Команды CLI](index.md#cli-commands).

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.

## <a name="examples"></a>Примеры

Открывает страницу документации по команде[dotnet new](dotnet-new.md):

`dotnet help new`
