---
title: Команда dotnet clean — CLI .NET Core
description: Команда dotnet clean очищает текущий каталог.
ms.date: 12/04/2018
ms.openlocfilehash: 9930d2905f234e7125f27367cda36aa85ae23b87
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144459"
---
# <a name="dotnet-clean"></a>dotnet clean

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet clean` — очищает выходные данные проекта.

## <a name="synopsis"></a>Краткий обзор

```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a>Описание:

Команда `dotnet clean` очищает выходные данные предыдущей сборки. Она реализуется как [целевой объект MSBuild](/visualstudio/msbuild/msbuild-targets), поэтому при выполнении команды проект получает оценку. Очищаются только выходные данные, созданные во время сборки. Очищаются папки с промежуточными (*obj*) и окончательными выходными данными (*bin*).

## <a name="arguments"></a>Аргументы

`PROJECT`

Очищаемый проект MSBuild. Если файл проекта не указан, MSBuild ищет в текущем рабочем каталоге файл с расширением, заканчивающимся на *PROJ*, и использует его.

## <a name="options"></a>Параметры

* **`-c|--configuration {Debug|Release}`**

  Определяет конфигурацию сборки. Значение по умолчанию — `Debug`. Этот параметр требуется при очистке только в том случае, если вы указали его во время сборки.

* **`-f|--framework <FRAMEWORK>`**

  [Платформа](../../standard/frameworks.md), указанная во время сборки. Платформа должна быть определена в [файле проекта](csproj.md). Если вы указали платформу во время сборки, нужно указать ее эту платформу при очистке.

* **`-h|--help`**

  Выводит краткую справку по команде.

* **`-o|--output <OUTPUT_DIRECTORY>`**

  Каталог, куда помещаются выходные данные сборки. Укажите параметр `-f|--framework <FRAMEWORK>` с параметром выходного каталога, если задали платформу при сборке проекта.

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Очищает выходную папку указанной среды выполнения. Используется, если было создано [автономное развертывание](../deploying/index.md#self-contained-deployments-scd). Параметр доступен, начиная с пакета SDK для .NET Core 2.0.

* **`-v|--verbosity <LEVEL>`**

  Задает уровень детализации команды. Допустимые уровни: q[uiet], m[inimal], n[ormal], d[etailed] и diag[nostic].

## <a name="examples"></a>Примеры

* Очистите сборку проекта по умолчанию:

  ```console
  dotnet clean
  ```

* Очистите сборку проекта с помощью конфигурации выпуска:

  ```console
  dotnet clean --configuration Release
  ```