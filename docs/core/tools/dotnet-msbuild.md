---
title: "Команда dotnet-msbuild — CLI .NET Core | Документы Майкрософт"
description: "Команда dotnet-msbuild обеспечивает доступ к командной строке MSBuild."
keywords: "dotnet-msbuild, CLI, команда CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: ffdc40ba-ef33-463e-aa35-b0af1fe615a2
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: 069909ab3890b75502602f57fc15df19bc7dd614
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-msbuild"></a>dotnet-msbuild

## <a name="name"></a>Имя

`dotnet-msbuild` — собирает проект и все его зависимости.

## <a name="synopsis"></a>Краткий обзор

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a>Описание

Команда `dotnet msbuild` предоставляет доступ к полнофункциональной системе MSBuild.

Команда имеет точно такие же возможности, как и существующий клиент с интерфейсом командной строки MSBuild. Все параметры одинаковы. Для получения сведений о различных параметрах см. раздел [Справочник по командной строке MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference). 

## <a name="examples"></a>Примеры

Сборка проекта и его зависимостей:

`dotnet msbuild`

Сборка проекта и его зависимостей с помощью конфигурации Release:

`dotnet msbuild /p:Configuration=Release`

Запустите цель публикации и публикацию для RID `osx.10.11-x64`:

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`
