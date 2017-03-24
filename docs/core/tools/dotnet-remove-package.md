---
title: "Команда dotnet-remove package | Документы Майкрософт"
description: "Команду dotnet-remove package удобно использовать для удаления ссылки на пакет NuGet в проекте."
keywords: "dotnet-remove, CLI, команда CLI, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 2fcc8d37-16b3-4581-8038-832160e72d36
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 87c80ad193df9cc3e0feabc41bb58f1d8dda23cd
ms.lasthandoff: 03/07/2017

---
# <a name="dotnet-remove-package"></a>dotnet-remove package

## <a name="name"></a>Имя

`dotnet-remove package` — удаляет ссылку на пакет из файла проекта.

## <a name="synopsis"></a>Краткий обзор

```
dotnet remove [project] package <package_name>
dotnet remove package [-h|--help]
```

## <a name="description"></a>Описание

Команду `dotnet remove package` удобно использовать для удаления ссылки на пакет NuGet из проекта.

## <a name="arguments"></a>Аргументы

`project`

Целевой файл проекта. Если он не указан, команда будет искать текущий каталог для него.

`package_name`

Удаляемая ссылка на пакет.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.

## <a name="examples"></a>Примеры

Удаляет пакет NuGet `Newtonsoft.Json` из проекта в текущем каталоге:

`dotnet remove package Newtonsoft.Json`
