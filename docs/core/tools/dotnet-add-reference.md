---
title: Команда dotnet add reference
description: Команду dotnet add reference удобно использовать для добавления ссылок между проектами.
ms.date: 06/26/2019
ms.openlocfilehash: dc8bc01a2bff4f2cf3a8af9efb233448d7de337f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733272"
---
# <a name="dotnet-add-reference"></a>dotnet add reference

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 1.x и более поздних версий

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

`dotnet add reference` — добавляет перекрестные ссылки между проектами (P2P).

## <a name="synopsis"></a>Краткий обзор

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help] [--interactive]`

## <a name="description"></a>Описание

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
