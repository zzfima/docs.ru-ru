---
title: Команда dotnet help — CLI .NET Core
description: Команда dotnet help выводит более подробную документацию из Интернета для указанной команды.
author: mairaw
ms.author: mairaw
ms.date: 08/17/2017
ms.openlocfilehash: 846ca15fa40a4cf9e1bd18c14cbcd9aef5cab97d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
