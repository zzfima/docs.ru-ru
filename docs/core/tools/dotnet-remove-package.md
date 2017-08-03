---
title: "Команда dotnet-remove package — CLI .NET Core"
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a3fef846d5850e2c2a158ccd1f30a84e8f23f793
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

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

