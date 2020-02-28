---
title: Команда dotnet sln
description: Команда dotnet-sln предоставляет удобный способ добавлять проекты в файл решений, удалять или перечислять их.
ms.date: 02/14/2020
ms.openlocfilehash: b2455c04a46b2a10b8142d8ddc2d8129f2154b27
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543486"
---
# <a name="dotnet-sln"></a>dotnet sln

**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий

## <a name="name"></a>name

`dotnet sln` — перечисляет или изменяет проекты в файле решения .NET Core.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a>Описание

Команда `dotnet sln` предоставляет удобный способ перечислять и изменять проекты в файле решений.

Для использования команды `dotnet sln` файл решения должен уже существовать. Если необходимо создать его, используйте команду [dotnet new](dotnet-new.md), как в следующем примере:

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a>Аргументы

- **`SOLUTION_FILE`**

  Используемый файл решений. Если этот аргумент упущен, команда ищет текущий каталог для него. Если файл решения или несколько файлов решения не найдены, команда завершается ошибкой.

## <a name="options"></a>Параметры

- **`-h|--help`**

  Выводит описание использования команды.

## <a name="commands"></a>Команды

### `list`

Перечисляет все проекты в файле решения.

#### <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a>Аргументы

- **`SOLUTION_FILE`**

  Используемый файл решений. Если этот аргумент упущен, команда ищет текущий каталог для него. Если файл решения или несколько файлов решения не найдены, команда завершается ошибкой.

#### <a name="options"></a>Параметры

- **`-h|--help`**

  Выводит описание использования команды.
  
### `add`

Добавление проектов в файл решения.

#### <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a>Аргументы

- **`SOLUTION_FILE`**

  Используемый файл решений. Если он не указан, команда ищет его в текущем каталоге и завершается ошибкой, если имеется несколько файлов решения.

- **`PROJECT_PATH`**

  Путь к проекту или проектам, который необходимо добавить в решение. Расширения [стандартной маски](https://en.wikipedia.org/wiki/Glob_(programming)) оболочки Unix/Linux правильно обрабатываются командой `dotnet sln`.

#### <a name="options"></a>Параметры

- **`-h|--help`**

  Выводит описание использования команды.

- **`--in-root`**

  Поместите проекты в корень решения, и вам не нужно будет создавать папку решения. Доступно, начиная с пакета SDK для .NET Core 3.0.

- **`-s|--solution-folder`**

  Путь к папке назначения решения, в которую будут добавлены проекты. Доступно, начиная с пакета SDK для .NET Core 3.0.

### `remove`

Удаляет один или несколько проектов из файла решений.

#### <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a>Аргументы

- **`SOLUTION_FILE`**

  Используемый файл решений. Если он не указан, команда ищет его в текущем каталоге и завершается ошибкой, если имеется несколько файлов решения.

- **`PROJECT_PATH`**

  Путь к проекту или проектам, который необходимо добавить в решение. Расширения [стандартной маски](https://en.wikipedia.org/wiki/Glob_(programming)) оболочки Unix/Linux правильно обрабатываются командой `dotnet sln`.

#### <a name="options"></a>Параметры

- **`-h|--help`**

  Выводит описание использования команды.

## <a name="examples"></a>Примеры

- Перечисление проектов в решении:

  ```dotnetcli
  dotnet sln todo.sln list
  ```

- Добавление проекта C# в решение:

  ```dotnetcli
  dotnet sln add todo-app/todo-app.csproj
  ```

- Удаление проекта C# из решения:

  ```dotnetcli
  dotnet sln remove todo-app/todo-app.csproj
  ```

- Добавление нескольких проектов C# в корень решения:

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj --in-root
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
