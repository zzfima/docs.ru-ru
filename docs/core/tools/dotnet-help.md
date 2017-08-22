---
title: "Команда dotnet help — CLI .NET Core"
description: "Команда dotnet help выводит более подробную документацию из Интернета для указанной команды."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: b33d21d7578bb4c1b33c655103f720b32aaf2203
ms.contentlocale: ru-ru
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-help-reference"></a>Справочник по команде dotnet help

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a>Имя

`dotnet help` — выводит более подробную документацию из Интернета для указанной команды.

## <a name="synopsis"></a>Краткий обзор

`dotnet list <COMMAND_NAME> [-h|--help]`

## <a name="description"></a>Описание

Команда `dotnet help` открывает страницу сайта docs.microsoft.com с подробной справочной информацией об указанной команде.

## <a name="arguments"></a>Аргументы

`COMMAND_NAME`

Имя команды интерфейса командной строки .NET Core. Список допустимых команд интерфейса командной строки см. в разделе [Команды CLI](index.md#cli-commands).

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.

## <a name="examples"></a>Примеры

Перечисление ссылок на проекты для указанного проекта:

`dotnet list app/app.csproj reference`

Перечисление ссылок на проекты для проекта в текущем каталоге:

`dotnet list reference`

