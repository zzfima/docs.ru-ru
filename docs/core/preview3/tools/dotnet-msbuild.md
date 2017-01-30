---
title: "Команда dotnet-msbuild | Пакет SDK для .NET Core"
description: "Команда dotnet-msmsbuild предоставляет доступ к командной строке MSmsbuild"
keywords: "dotnet-msbuild, CLI, команда CLI, .NET Core"
author: mairaw
manager: wpickett
ms.date: 10/13/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: ffdc40ba-ef33-463e-aa35-b0af1fe615a2
translationtype: Human Translation
ms.sourcegitcommit: cde9d9577246a9025d646ce2a6d574a18512146e
ms.openlocfilehash: 51a3afdcf591b8147790d78471c6fee63ceb7f2d

---

#<a name="dotnet-msbuild"></a>dotnet-msbuild

## <a name="name"></a>Имя 
dotnet-msbuild — выполняет сборку проекта и всех его зависимостей. 

## <a name="synopsis"></a>Краткий обзор

`dotnet msbuild <msbuild_arguments>`

## <a name="description"></a>Описание
Команда `dotnet msbuild` предоставляет доступ к полнофункциональной командной строке MSBuild. 

Команда имеет точно такие же возможности, как существующий клиент командной строки MSBuild. Все параметры одинаковы. Справочник по командам см. в [доступной документации](https://msdn.microsoft.com/en-us/library/ms164311.aspx). 

## <a name="examples"></a>Примеры

Сборка проекта и его зависимостей:

`dotnet msbuild`

Сборка проекта и его зависимостей с помощью конфигурации Release:

`dotnet msbuild /p:Configuration=Release`

Запустите цель публикации и публикацию для RID `osx.10.11-x64`:

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`



<!--HONumber=Nov16_HO3-->


