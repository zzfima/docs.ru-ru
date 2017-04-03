---
title: "Команда dotnet-remove package — CLI .NET Core | Документы Майкрософт"
description: "Команду dotnet-remove package удобно использовать для удаления ссылки на пакет NuGet в проекте."
keywords: "dotnet-remove, CLI, команда CLI, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 2fcc8d37-16b3-4581-8038-832160e72d36
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: a321610540534a63bd12a8f878950b75e882c3d4
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-remove-package"></a>dotnet-remove package

## <a name="name"></a>Имя

`dotnet-remove package` — удаляет ссылку на пакет из файла проекта.

## <a name="synopsis"></a>Краткий обзор

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a>Описание

Команду `dotnet remove package` удобно использовать для удаления ссылки на пакет NuGet из проекта.

## <a name="arguments"></a>Аргументы

`PROJECT`

Указывает файл проекта. Если он не указан, команда будет искать текущий каталог для него.

`PACKAGE_NAME`

Удаляемая ссылка на пакет.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.

## <a name="examples"></a>Примеры

Удаляет пакет NuGet `Newtonsoft.Json` из проекта в текущем каталоге:

`dotnet remove package Newtonsoft.Json`
