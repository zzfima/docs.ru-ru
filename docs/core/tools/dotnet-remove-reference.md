---
title: Команда dotnet remove reference — CLI .NET Core
description: Команду dotnet remove reference удобно использовать для удаления ссылок между проектами.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: b281b255be7f49a99a6b4928c340cd4fb085f085
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696235"
---
# <a name="dotnet-remove-reference"></a>dotnet remove reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet remove reference` — удаляет перекрестные ссылки между проектами.

## <a name="synopsis"></a>Краткий обзор

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>Описание:

Команду `dotnet remove reference` удобно использовать для удаления ссылок на проекты из проекта.

## <a name="arguments"></a>Аргументы

`PROJECT`

Файл целевого проекта. Если он не указан, команда ищет текущий каталог для него.

`PROJECT_REFERENCES`

Удаляемые перекрестные ссылки между проектами (P2P). Вы можете указать один или несколько проектов. [Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в терминалах на основе Unix или Linux.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.

`-f|--framework <FRAMEWORK>`

Удаляет ссылку только при ориентации на конкретную [платформу](../../standard/frameworks.md).

## <a name="examples"></a>Примеры

Удаление ссылки на проект из указанного проекта:

`dotnet remove app/app.csproj reference lib/lib.csproj`

Удаление нескольких ссылок на проекты из проекта в текущем каталоге:

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

Удаление нескольких ссылок на проект с помощью стандартной маски в Unix или Linux:

`dotnet remove app/app.csproj reference **/*.csproj`
