---
title: Команда dotnet list reference
description: Команду dotnet list reference удобно использовать для перечисления ссылок между проектами.
ms.date: 12/03/2018
ms.openlocfilehash: d22ea27f8e8f6b94d763e44a6d8644f814663797
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169837"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet list reference` — перечисляет перекрестные ссылки между проектами.

## <a name="synopsis"></a>Краткий обзор

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a>Описание

Команду `dotnet list reference` удобно использовать для перечисления ссылок на проекты для заданного проекта или решения.

## <a name="arguments"></a>Аргументы

* **`PROJECT`**

  Указывает файл проекта, используемый для перечисления ссылок. Если он не указан, команда ищет текущий каталог для него.

## <a name="options"></a>Параметры

* **`-h|--help`**

  Выводит краткую справку по команде.

## <a name="examples"></a>Примеры

* Перечисление ссылок на проекты для указанного проекта:

  ```console
  dotnet list app/app.csproj reference
  ```

* Перечисление ссылок на проекты для проекта в текущем каталоге:

  ```console
  dotnet list reference
  ```