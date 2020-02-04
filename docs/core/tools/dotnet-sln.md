---
title: Команда dotnet sln
description: Команда dotnet-sln предоставляет удобный способ добавлять проекты в файл решений, удалять или перечислять их.
ms.date: 10/29/2019
ms.openlocfilehash: e344deaae0867202a79a3c38df48a2be8d4d7d13
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733083"
---
# <a name="dotnet-sln"></a>dotnet sln

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 1.x и более поздних версий

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

`dotnet sln` — изменяет файл решений .NET Core.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a>Описание

Команда `dotnet sln` предоставляет удобный способ добавлять проекты в файл решений, удалять или перечислять их.

Для использования команды `dotnet sln` файл решения должен уже существовать. Если необходимо создать его, используйте команду [dotnet new](dotnet-new.md), как в следующем примере:

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a>Аргументы

- **`SOLUTION_FILE`**

  Используемый файл решений. Если он не указан, команда ищет текущий каталог для него. Если файлов решений в каталоге несколько, нужно указать один.

## <a name="options"></a>Параметры

- **`-h|--help`**

  Выводит краткую справку по команде.

## <a name="commands"></a>Команды

### `add`

Добавляет один или несколько проектов в файл решений.

#### <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH>
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a>Аргументы

- **`SOLUTION_FILE`**

  Используемый файл решений. Если он не указан, команда ищет текущий каталог для него. Если файлов решений в каталоге несколько, нужно указать один.

- **`PROJECT_PATH`**

  Путь к проекту, который необходимо добавить в решение. Добавьте несколько проектов с разделением пробелами. Расширения [стандартной маски](https://en.wikipedia.org/wiki/Glob_(programming)) оболочки UNIX/Linux правильно обрабатываются командой `dotnet sln`.

#### <a name="options"></a>Параметры

- **`-h|--help`**

  Выводит краткую справку по команде.

- **`--in-root`**

  Поместите проекты в корень решения, и вам не нужно будет создавать папку решения. Доступно, начиная с пакета SDK для .NET Core 3.0.

- **`-s|--solution-folder`**

  Путь к папке назначения решения, в которую будут добавлены проекты. Доступно, начиная с пакета SDK для .NET Core 3.0.

### `remove`

Удаляет один или несколько проектов из файла решений.

#### <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH>
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a>Аргументы

- **`SOLUTION_FILE`**

  Используемый файл решений. Если он не указан, команда ищет текущий каталог для него. Если файлов решений в каталоге несколько, нужно указать один.

- **`PROJECT_PATH`**

  Путь к проекту, который необходимо удалить из решения. Удалите несколько проектов с разделением пробелами. Расширения [стандартной маски](https://en.wikipedia.org/wiki/Glob_(programming)) оболочки Unix/Linux правильно обрабатываются командой `dotnet sln`.

#### <a name="options"></a>Параметры

- **`-h|--help`**

  Выводит краткую справку по команде.

### `list`

Перечисляет все проекты в файле решения.

#### <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a>Аргументы

- **`SOLUTION_FILE`**

  Используемый файл решений. Если он не указан, команда ищет текущий каталог для него. Если файлов решений в каталоге несколько, нужно указать один.

#### <a name="options"></a>Параметры

- **`-h|--help`**

  Выводит краткую справку по команде.

## <a name="examples"></a>Примеры

- Добавление проекта C# в решение:

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj
  ```

- Удаление проекта C# из решения:

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj
  ```

- Добавление нескольких проектов C# в решение:

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- Удаление нескольких проектов C# из решения:

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- Добавление нескольких проектов C# в решение с помощью стандартной маски (только Unix/Linux):

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- Удаление нескольких проектов C# из решения с помощью стандартной маски (только Unix/Linux):

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```
