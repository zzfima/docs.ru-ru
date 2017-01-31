---
title: "Команда dotnet-nuget-locals | Microsoft Docs"
description: "Команда dotnet-nuget-locals очищает или перечисляет локальные ресурсы NuGet, например кэш HTTP-запросов, временный кэш или папку глобальных пакетов, используемую на уровне компьютера."
keywords: "dotnet-nuget-locals, CLI, команда CLI, .NET Core"
author: karann-msft
ms.author: mairaw
ms.date: 11/15/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8440229e-317e-4dc1-9463-cba5fdb12c3b
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: 5f8c3be091b515553eb0db0ccfaee6bb8c620cff

---

#<a name="dotnet-nuget-locals"></a>dotnet-nuget-locals

[!INCLUDE[preview-warning](../../../includes/warning.md)] 

## <a name="name"></a>Имя 
`dotnet-nuget-locals` — очищает или перечисляет локальные ресурсы NuGet, например кэш HTTP-запросов, временный кэш или папку глобальных пакетов, используемую на уровне компьютера. 

## <a name="synopsis"></a>Краткий обзор

`dotnet nuget locals <cache_location> [--clear|--list] [--help] [--force-english-output]`

Где `<cache_location>` может принимать одно из следующих значений: `all`, `http-cache`, `packages-cache`, `global-packages` или `temp`.

## <a name="description"></a>Описание

Команда `dotnet nuget locals` очищает или перечисляет локальные ресурсы NuGet, например кэш HTTP-запросов, временный кэш или папку пакетов, используемую на уровне компьютера.

## <a name="arguments"></a>Аргументы

`all`

Указывает, что определенная операция должна применяться ко всем типам кэша, то есть к кэшу HTTP-запросов, глобальному кэшу пакетов и временному кэшу.

`http-cache`

Указывает, что определенная операция должна применяться только к кэшу HTTP-запросов. Другие расположения кэша не затрагиваются.

`global-packages`

Указывает, что определенная операция должна применяться только к глобальному кэшу пакетов. Другие расположения кэша не затрагиваются.

`temp`

Указывает, что определенная операция должна применяться только к временному кэшу. Другие расположения кэша не затрагиваются.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.  

`-c|--clear`

Параметр clear используется для очистки кэша указанного типа. Содержимое каталогов кэша удаляется рекурсивно. Для успешного выполнения операции существующий пользователь или группа должны иметь разрешение на доступ к файлам в каталогах кэша. Если доступа нет, отобразится ошибка, в которой указаны неочищенные файлы и (или) папки.

`-l|--list`

Параметр list используется для отображения расположения кэша указанного типа. 

`--force-english-output`

Принудительно отображает выходные данные командной строки на английском языке.

## <a name="examples"></a>Примеры

Отображает пути ко всем локальным каталогам кэша, т. е. к каталогам кэша HTTP-запросов, кэша глобальных пакетов и временного кэша.

`dotnet nuget locals –l all`

Отображает путь к локальному каталогу кэша HTTP-запросов.

`dotnet nuget locals --list http-cache`

Очищает файлы во всех локальных каталогах кэша, т. е. в каталоге кэша HTTP-запросов, кэша глобальных пакетов и временного кэша.

`dotnet nuget locals --clear all`

Удаляет все файлы в локальном каталоге кэша глобальных пакетов.

`dotnet nuget locals -c global-packages`

Удаляет все файлы в локальном каталоге временного кэша.

`dotnet nuget locals -c temp`

## <a name="troubleshooting"></a>Устранение неполадок

Сведения о распространенных проблемах и ошибках при использовании команды `dotnet-nuget-locals` см. в статье об [управлении кэшем NuGet](https://docs.microsoft.com/nuget/consume-packages/managing-the-nuget-cache).



<!--HONumber=Jan17_HO3-->


