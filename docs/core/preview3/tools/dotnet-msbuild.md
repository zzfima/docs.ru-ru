---
title: "Команда dotnet-msbuild | Microsoft Docs"
description: "Команда dotnet-msbuild обеспечивает доступ к командной строке MSBuild."
keywords: "dotnet-msbuild, CLI, команда CLI, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 10/13/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: ffdc40ba-ef33-463e-aa35-b0af1fe615a2
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: 06d4210e5dff97d3e96efff8ae8e84efc27fb7d2

---

#<a name="dotnet-msbuild"></a>dotnet-msbuild

[!INCLUDE[preview-warning](../../../includes/warning.md)]

## <a name="name"></a>Имя 
dotnet-msbuild — собирает проект и все его зависимости.

## <a name="synopsis"></a>Краткий обзор

`dotnet msbuild <msbuild_arguments>`

## <a name="description"></a>Описание
Команда `dotnet msbuild` предоставляет доступ к полнофункциональной командной строке MSBuild. 

Команда имеет точно такие же возможности, как и существующий клиент с интерфейсом командной строки MSBuild. Все параметры одинаковы. Ознакомиться с параметрами можно в статье [Справочник по командной строке MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference). 

## <a name="examples"></a>Примеры

Сборка проекта и его зависимостей:

`dotnet msbuild`

Сборка проекта и его зависимостей с помощью конфигурации Release:

`dotnet msbuild /p:Configuration=Release`

Запустите цель публикации и публикацию для RID `osx.10.11-x64`:

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`



<!--HONumber=Jan17_HO3-->


