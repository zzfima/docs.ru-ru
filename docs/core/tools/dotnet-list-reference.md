---
title: Команда dotnet list reference
description: Команду dotnet list reference удобно использовать для перечисления ссылок между проектами.
ms.date: 06/26/2019
ms.openlocfilehash: b4b82ca1e7aeb2b73d9f99aff1c97452b2166770
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117683"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

**Этот раздел относится к: ✓** пакету SDK для .NET Core 1.x и более поздних версий

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

`dotnet list reference` — перечисляет перекрестные ссылки между проектами.

## <a name="synopsis"></a>Краткий обзор

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a>ОПИСАНИЕ

Команду `dotnet list reference` удобно использовать для перечисления ссылок на проекты для заданного проекта или решения.

## <a name="arguments"></a>Аргументы

* **`PROJECT | SOLUTION`**

  Указывает файл проекта или решения, используемый для перечисления ссылок. Если он не указан, команда ищет текущий каталог для него.

## <a name="options"></a>Параметры

* **`-h|--help`**

  Выводит краткую справку по команде.

## <a name="examples"></a>Примеры

* Перечисление ссылок на проекты для указанного проекта:

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* Перечисление ссылок на проекты для проекта в текущем каталоге:

  ```dotnetcli
  dotnet list reference
  ```
