---
title: Команда dotnet nuget locals
description: Команда dotnet nuget locals очищает или перечисляет локальные ресурсы NuGet, например кэш HTTP-запросов, временный кэш или папку глобальных пакетов, используемую на уровне компьютера.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: cb5747636aa9d04f1ef6a6ff9309ba29c0630dd6
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087409"
---
# <a name="dotnet-nuget-locals"></a>dotnet nuget locals

**Этот раздел относится к: ✓** пакету SDK для .NET Core 1.x и более поздних версий

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

`dotnet nuget locals` — очищает или перечисляет локальные ресурсы NuGet.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output]
dotnet nuget locals [-h|--help]
```

## <a name="description"></a>Описание:

Команда `dotnet nuget locals` очищает или перечисляет локальные ресурсы NuGet в кэше HTTP-запросов, временном кэше или папке пакетов, используемой на уровне компьютера.

## <a name="arguments"></a>Аргументы

* **`CACHE_LOCATION`**

  Расположение кэша для вывода или очищения. Принимает одно из следующих значений:

  * `all` — указывает, что определенная операция применяется ко всем типам кэша, то есть к кэшу HTTP-запросов, глобальному кэшу пакетов и временному кэшу.
  * `http-cache` — указывает, что определенная операция применяется только к кэшу HTTP-запросов. Другие расположения кэша не затрагиваются.
  * `global-packages` — указывает, что определенная операция применяется только к глобальному кэшу пакетов. Другие расположения кэша не затрагиваются.
  * `temp` — указывает, что определенная операция применяется только к временному кэшу. Другие расположения кэша не затрагиваются.

## <a name="options"></a>Параметры

* **`--force-english-output`**

  Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.

* **`-h|--help`**

  Выводит краткую справку по команде.

* **`-c|--clear`**

  Параметр clear очищает кэш указанного типа. Содержимое каталогов кэша удаляется рекурсивно. Пользователь или группа, совершающие выполнение, должны иметь разрешение на доступ к файлам в каталогах кэша. Если доступа нет, отображается ошибка, в которой указаны неочищенные файлы и папки.

* **`-l|--list`**

  Параметр list используется для отображения расположения кэша указанного типа.

## <a name="examples"></a>Примеры

* Отображает пути ко всем локальным каталогам кэша (т. е. к каталогам кэша HTTP-запросов, кэша глобальных пакетов и временного кэша):

  ```dotnetcli
  dotnet nuget locals all –l
  ```

* Отображает путь к локальному каталогу кэша HTTP-запросов.

  ```dotnetcli
  dotnet nuget locals http-cache --list
  ```

* Очищает все файлы изо всех локальных каталогов кэша (т. е. каталогов кэша HTTP-запросов, кэша глобальных пакетов и временного кэша):

  ```dotnetcli
  dotnet nuget locals all --clear
  ```

* Очищает все файлы в локальном каталоге кэша глобальных пакетов:

  ```dotnetcli
  dotnet nuget locals global-packages -c
  ```

* Очищает все файлы в локальном каталоге временного кэша:

  ```dotnetcli
  dotnet nuget locals temp -c
  ```

## <a name="troubleshooting"></a>Устранение неполадок

Сведения о распространенных проблемах и ошибках при использовании команды `dotnet nuget locals` см. в статье об [управлении кэшем NuGet](/nuget/consume-packages/managing-the-nuget-cache).
