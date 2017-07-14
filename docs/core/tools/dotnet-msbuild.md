---
title: "Команда dotnet-msbuild — CLI .NET Core | Документы Майкрософт"
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
ms.translationtype: Human Translation
ms.sourcegitcommit: df4b2ddd322e4bd2ebaf444439107e88a983f988
ms.openlocfilehash: 2267ef0b5785959456ea443405b6708a423d00ba
ms.contentlocale: ru-ru
ms.lasthandoff: 05/30/2017

---

# dotnet-msbuild
<a id="dotnet-msbuild" class="xliff"></a>

## Имя
<a id="name" class="xliff"></a>

`dotnet-msbuild` — собирает проект и все его зависимости.

## Краткий обзор
<a id="synopsis" class="xliff"></a>

`dotnet msbuild <msbuild_arguments> [-h]`

## Описание
<a id="description" class="xliff"></a>

Команда `dotnet msbuild` предоставляет доступ к полнофункциональной системе MSBuild.

Команда имеет точно такие же возможности, как и существующий клиент с интерфейсом командной строки MSBuild. Все параметры одинаковы. Для получения сведений о различных параметрах см. раздел [Справочник по командной строке MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference). 

## Примеры
<a id="examples" class="xliff"></a>

Сборка проекта и его зависимостей:

`dotnet msbuild`

Сборка проекта и его зависимостей с помощью конфигурации Release:

`dotnet msbuild /p:Configuration=Release`

Запустите цель публикации и публикацию для RID `osx.10.11-x64`:

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

Весь проект со всеми целевыми объектами, включенными в пакет SDK:

`dotnet msbuild /pp`
