---
title: "Команда dotnet nuget locals — CLI .NET Core"
description: "Команда dotnet nuget locals очищает или перечисляет локальные ресурсы NuGet, например кэш HTTP-запросов, временный кэш или папку глобальных пакетов, используемую на уровне компьютера."
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 2b66198ac3e33c640abda0c96fb05944f5ea91df
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-nuget-locals"></a>dotnet nuget locals

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Имя

`dotnet nuget locals` — очищает или перечисляет локальные ресурсы NuGet.

## <a name="synopsis"></a>Краткий обзор

`dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output] [-h|--help]`

## <a name="description"></a>Описание

Команда `dotnet nuget locals` очищает или перечисляет локальные ресурсы NuGet в кэше HTTP-запросов, временном кэше или папке пакетов, используемой на уровне компьютера.

## <a name="arguments"></a>Аргументы

`CACHE_LOCATION`

Одно из следующих значений:

* `all` — указывает, что определенная операция применяется ко всем типам кэша, то есть к кэшу HTTP-запросов, глобальному кэшу пакетов и временному кэшу.
* `http-cache` — указывает, что определенная операция применяется только к кэшу HTTP-запросов. Другие расположения кэша не затрагиваются.
* `global-packages` — указывает, что определенная операция применяется только к глобальному кэшу пакетов. Другие расположения кэша не затрагиваются.
* `temp` — указывает, что определенная операция применяется только к временному кэшу. Другие расположения кэша не затрагиваются.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.

`-c|--clear`

Параметр clear очищает кэш указанного типа. Содержимое каталогов кэша удаляется рекурсивно. Пользователь или группа, совершающие выполнение, должны иметь разрешение на доступ к файлам в каталогах кэша. Если доступа нет, отображается ошибка, в которой указаны неочищенные файлы и папки.

`-l|--list`

Параметр list используется для отображения расположения кэша указанного типа. 

`--force-english-output`

Принудительно отображает выходные данные командной строки на английском языке.

## <a name="examples"></a>Примеры

Отображает пути ко всем локальным каталогам кэша (т. е. к каталогам кэша HTTP-запросов, кэша глобальных пакетов и временного кэша):

`dotnet nuget locals –l all`

Отображает путь к локальному каталогу кэша HTTP-запросов.

`dotnet nuget locals --list http-cache`

Очищает все файлы изо всех локальных каталогов кэша (т. е. каталогов кэша HTTP-запросов, кэша глобальных пакетов и временного кэша):

`dotnet nuget locals --clear all`

Очищает все файлы в локальном каталоге кэша глобальных пакетов:

`dotnet nuget locals -c global-packages`

Очищает все файлы в локальном каталоге временного кэша:

`dotnet nuget locals -c temp`

## <a name="troubleshooting"></a>Устранение неполадок

Сведения о распространенных проблемах и ошибках при использовании команды `dotnet nuget locals` см. в статье об [управлении кэшем NuGet](/nuget/consume-packages/managing-the-nuget-cache).