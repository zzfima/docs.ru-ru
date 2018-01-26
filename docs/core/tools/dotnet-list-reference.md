---
title: "Команда dotnet list reference — CLI .NET Core"
description: "Команду dotnet list reference удобно использовать для перечисления ссылок между проектами."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: a4ceadb6d070d7997e75b472624bbe2c1650396d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-list-reference"></a>dotnet list reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet list reference` — перечисляет перекрестные ссылки между проектами.

## <a name="synopsis"></a>Краткий обзор

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a>Описание:

Команду `dotnet list reference` удобно использовать для перечисления ссылок на проекты для заданного проекта.

## <a name="arguments"></a>Аргументы

`PROJECT`

Указывает файл проекта, используемый для перечисления ссылок. Если он не указан, команда ищет текущий каталог для него.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.

## <a name="examples"></a>Примеры

Перечисление ссылок на проекты для указанного проекта:

`dotnet list app/app.csproj reference`

Перечисление ссылок на проекты для проекта в текущем каталоге:

`dotnet list reference`
