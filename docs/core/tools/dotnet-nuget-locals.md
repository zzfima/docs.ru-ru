---
title: "Команда dotnet-nuget-locals — CLI .NET Core | Документы Майкрософт"
description: "Команда dotnet-nuget-locals очищает или перечисляет локальные ресурсы NuGet, например кэш HTTP-запросов, временный кэш или папку глобальных пакетов, используемую на уровне компьютера."
keywords: "dotnet-nuget-locals, CLI, команда CLI, .NET Core"
author: karann-msft
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8440229e-317e-4dc1-9463-cba5fdb12c3b
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: d0acfaa6ff1a11f49a0d3751b675ea94bd6ae3a3
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-nuget-locals"></a>dotnet-nuget locals

## <a name="name"></a>Имя

`dotnet-nuget locals` — очищает или перечисляет локальные ресурсы NuGet. 

## <a name="synopsis"></a>Краткий обзор

`dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output] [-h|--help]`

## <a name="description"></a>Описание

Команда `dotnet nuget locals` очищает или перечисляет локальные ресурсы NuGet в кэше HTTP-запросов, временном кэше или папке пакетов, используемой на уровне компьютера.

## <a name="arguments"></a>Аргументы

`CACHE_LOCATION`

Одно из следующих значений:

`all`

Указывает, что определенная операция применяется ко всем типам кэша, то есть к кэшу HTTP-запросов, глобальному кэшу пакетов и временному кэшу.

`http-cache`

Указывает, что определенная операция применяется только к кэшу HTTP-запросов. Другие расположения кэша не затрагиваются.

`global-packages`

Указывает, что определенная операция применяется только к глобальному кэшу пакетов. Другие расположения кэша не затрагиваются.

`temp`

Указывает, что определенная операция применяется только к временному кэшу. Другие расположения кэша не затрагиваются.

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

Сведения о распространенных проблемах и ошибках при использовании команды `dotnet nuget locals` см. в статье об [управлении кэшем NuGet](https://docs.microsoft.com/nuget/consume-packages/managing-the-nuget-cache).

