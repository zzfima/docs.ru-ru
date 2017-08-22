---
title: "Команда dotnet msbuild — CLI .NET Core"
description: "Команда dotnet msbuild обеспечивает доступ к командной строке MSBuild."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 96e4eac528abad2b336a979a98c9be2bee5d17ee
ms.contentlocale: ru-ru
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-msbuild"></a>dotnet msbuild

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Имя

`dotnet msbuild` — собирает проект и все его зависимости.

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

