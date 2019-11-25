---
title: Команда dotnet add reference
description: Команду dotnet add reference удобно использовать для добавления ссылок между проектами.
ms.date: 06/26/2019
ms.openlocfilehash: c97975e11410cfaad18ca68832957d75a4a2fd09
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73100817"
---
# <a name="dotnet-add-reference"></a>dotnet add reference

**Эта статья относится к ✓** SDK для .NET Core 1.x и более поздних версий

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

`dotnet add reference` — добавляет перекрестные ссылки между проектами (P2P).

## <a name="synopsis"></a>Краткий обзор

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help] [--interactive]`

## <a name="description"></a>Описание:

Команду `dotnet add reference` удобно использовать для добавления ссылок на проекты в проект. После запуска этой команды в файл проекта добавляются элементы `<ProjectReference>`.

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>Аргументы

- **`PROJECT`**

  Указывает файл проекта. Если он не указан, команда ищет текущий каталог для него.

- **`PROJECT_REFERENCES`**

  Добавляемые перекрестные ссылки между проектами (P2P). Укажите один или несколько проектов. [Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в системах на основе Unix или Linux.

## <a name="options"></a>Параметры

- **`-h|--help`**

  Выводит краткую справку по команде.

- **`-f|--framework <FRAMEWORK>`**

  Добавляет ссылки на проекты только при ориентации на конкретную [платформу](../../standard/frameworks.md).

- **`--interactive`**

  Позволяет остановить команду и дождаться, пока пользователь введет данные или выполнит действие (например, завершит проверку подлинности). Доступно, начиная с пакета SDK для .NET Core 3.0.

## <a name="examples"></a>Примеры

- Добавление ссылки на проект:

  ```dotnetcli
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

- Добавление нескольких ссылок на проекты в проект в текущем каталоге:

  ```dotnetcli
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- Добавление нескольких ссылок на проект с помощью стандартной маски в Linux/Unix:

  ```dotnetcli
  dotnet add app/app.csproj reference **/*.csproj
  ```
