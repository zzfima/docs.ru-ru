---
title: Команда dotnet clean
description: Команда dotnet clean очищает текущий каталог.
ms.date: 04/14/2019
ms.openlocfilehash: 3e735c02c9be9b6f51a8cdf048c18eff34f838cb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754121"
---
# <a name="dotnet-clean"></a>dotnet clean

**Этот раздел относится к: ✓** пакету SDK для .NET Core 1.x и более поздних версий

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

`dotnet clean` — очищает выходные данные проекта.

## <a name="synopsis"></a>Краткий обзор

```
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--interactive] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a>Описание

Команда `dotnet clean` очищает выходные данные предыдущей сборки. Она реализуется как [целевой объект MSBuild](/visualstudio/msbuild/msbuild-targets), поэтому при выполнении команды проект получает оценку. Очищаются только выходные данные, созданные во время сборки. Очищаются папки с промежуточными (*obj*) и окончательными выходными данными (*bin*).

## <a name="arguments"></a>Аргументы

`PROJECT | SOLUTION`

Проект или решение MSBuild, которые нужно удалить. Если файл проекта или решения не указан, MSBuild ищет в текущем рабочем каталоге файл с расширением, заканчивающимся на *PROJ* или *SLN*, и использует его.

## <a name="options"></a>Параметры

* **`-c|--configuration {Debug|Release}`**

  Определяет конфигурацию сборки. Значение по умолчанию — `Debug`. Этот параметр требуется при очистке только в том случае, если вы указали его во время сборки.

* **`-f|--framework <FRAMEWORK>`**

  [Платформа](../../standard/frameworks.md), указанная во время сборки. Платформа должна быть определена в [файле проекта](csproj.md). Если вы указали платформу во время сборки, нужно указать ее эту платформу при очистке.

* **`-h|--help`**

  Выводит краткую справку по команде.

* **`--interactive`**

  Позволяет команде остановиться и дождаться, пока пользователь выполнит действие или введет данные. Например, чтобы завершить проверку подлинности. Доступно, начиная с пакета SDK для .NET Core 3.0.

* **`-o|--output <OUTPUT_DIRECTORY>`**

  Каталог, содержащий артефакты сборки, которые нужно удалить. Укажите параметр `-f|--framework <FRAMEWORK>` с параметром выходного каталога, если задали платформу при сборке проекта.

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Очищает выходную папку указанной среды выполнения. Используется, если было создано [автономное развертывание](../deploying/index.md#self-contained-deployments-scd). Параметр доступен, начиная с пакета SDK для .NET Core 2.0.

* **`-v|--verbosity <LEVEL>`**

  Задает уровень детализации MSBuild. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`. Значение по умолчанию — `normal`.

## <a name="examples"></a>Примеры

* Очистите сборку проекта по умолчанию:

  ```console
  dotnet clean
  ```

* Очистите сборку проекта с помощью конфигурации выпуска:

  ```console
  dotnet clean --configuration Release
  ```