---
title: Команда dotnet-add reference — CLI .NET Core
description: Команду dotnet add reference удобно использовать для добавления ссылок между проектами.
author: mairaw
ms.author: mairaw
ms.date: 12/04/2018
ms.openlocfilehash: 33c5e532baf23cc8fe2b3a5084bff029caece842
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129549"
---
# <a name="dotnet-add-reference"></a>dotnet-add reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet add reference` — добавляет перекрестные ссылки между проектами (P2P).

## <a name="synopsis"></a>Краткий обзор

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>Описание:

Команду `dotnet add reference` удобно использовать для добавления ссылок на проекты в проект. После запуска этой команды в файл проекта добавляются элементы [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items).

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>Аргументы

* **`PROJECT`**

  Указывает файл проекта. Если он не указан, команда ищет текущий каталог для него.

* **`PROJECT_REFERENCES`**

  Добавляемые перекрестные ссылки между проектами (P2P). Укажите один или несколько проектов. [Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в системах на основе Unix или Linux.

## <a name="options"></a>Параметры

* **`-h|--help`**

  Выводит краткую справку по команде.

* **`-f|--framework <FRAMEWORK>`**

  Добавляет ссылки на проекты только при ориентации на конкретную [платформу](../../standard/frameworks.md).

## <a name="examples"></a>Примеры

* Добавление ссылки на проект:

  ```console
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

* Добавление нескольких ссылок на проекты в проект в текущем каталоге:

  ```console
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

* Добавление нескольких ссылок на проект с помощью стандартной маски в Linux/Unix:

  ```console
  dotnet add app/app.csproj reference **/*.csproj
  ```