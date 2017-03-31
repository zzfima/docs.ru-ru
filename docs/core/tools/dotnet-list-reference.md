---
title: "Команда dotnet-list reference — CLI .NET Core | Документы Майкрософт"
description: "Команду dotnet-list reference удобно использовать для перечисления ссылок между проектами."
keywords: "dotnet-list, CLI, команда CLI, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8f954a0c-03f8-4fbc-a529-b313ab12c623
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: fdaf2a6f66801be68507ccabe7e0f2fea5433e65
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-list-reference"></a>dotnet-list reference

## <a name="name"></a>Имя

`dotnet-list reference` — перечисляет перекрестные ссылки между проектами.

## <a name="synopsis"></a>Краткий обзор

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a>Описание

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

