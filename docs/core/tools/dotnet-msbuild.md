---
title: "Команда dotnet-msbuild — CLI .NET Core"
description: "Команда dotnet-msbuild обеспечивает доступ к командной строке MSBuild."
keywords: "dotnet-msbuild, CLI, команда CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 05/24/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: ffdc40ba-ef33-463e-aa35-b0af1fe615a2
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1f02dcd779b9ed249ebd2fedb973383b1dcd8963
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-msbuild"></a>dotnet-msbuild

## <a name="name"></a>Имя

`dotnet-msbuild` — собирает проект и все его зависимости.

## <a name="synopsis"></a>Краткий обзор

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a>Описание

Команда `dotnet msbuild` предоставляет доступ к полнофункциональной системе MSBuild.

Команда имеет точно такие же возможности, как и существующий клиент с интерфейсом командной строки MSBuild. Все параметры одинаковы. Для получения сведений о различных параметрах см. раздел [Справочник по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference). 

## <a name="examples"></a>Примеры

Сборка проекта и его зависимостей:

`dotnet msbuild`

Сборка проекта и его зависимостей с помощью конфигурации Release:

`dotnet msbuild /p:Configuration=Release`

Запустите цель публикации и публикацию для RID `osx.10.11-x64`:

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

Весь проект со всеми целевыми объектами, включенными в пакет SDK:

`dotnet msbuild /pp`

