---
title: Команда dotnet remove package
description: Команду dotnet remove package удобно использовать для удаления ссылки на пакет NuGet в проекте.
ms.date: 05/29/2018
ms.openlocfilehash: 4cc8ac927b761547dc5e53be9abeba827bf1e1d9
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168732"
---
# <a name="dotnet-remove-package"></a>dotnet remove package

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet remove package` — удаляет ссылку на пакет из файла проекта.

## <a name="synopsis"></a>Краткий обзор

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a>Описание

Команду `dotnet remove package` удобно использовать для удаления ссылки на пакет NuGet из проекта.

## <a name="arguments"></a>Аргументы

`PROJECT`

Указывает файл проекта. Если он не указан, команда ищет текущий каталог для него.

`PACKAGE_NAME`

Удаляемая ссылка на пакет.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.

## <a name="examples"></a>Примеры

Удаляет пакет NuGet `Newtonsoft.Json` из проекта в текущем каталоге:

`dotnet remove package Newtonsoft.Json`