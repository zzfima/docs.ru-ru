---
title: Команда dotnet msbuild
description: Команда dotnet msbuild обеспечивает доступ к командной строке MSBuild.
ms.date: 12/03/2018
ms.openlocfilehash: dae1e9f0ca355166d41c11fbafb80c7c9fb29748
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733194"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet msbuild` — собирает проект и все его зависимости.

## <a name="synopsis"></a>Краткий обзор

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a>Описание

Команда `dotnet msbuild` предоставляет доступ к полнофункциональной системе MSBuild.

Команда имеет точно такие же возможности, как и существующий клиент с интерфейсом командной строки MSBuild только для проектов в стиле SDK. Все параметры одинаковы. Дополнительные сведения о доступных параметрах см. в [справочнике по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).

Команда [dotnet build](dotnet-build.md) эквивалентна `dotnet msbuild -restore -target:Build`. Обычно для сборки проектов используется команда [dotnet build](dotnet-build.md). Так как команда `dotnet msbuild` всегда запускает целевой объект сборки, вы можете использовать ее, если не хотите выполнять сборку проекта. Например, если вам нужно запустить конкретный целевой объект, не выполняя сборку проекта, используйте `dotnet msbuild` и укажите целевой объект.

## <a name="examples"></a>Примеры

* Сборка проекта и его зависимостей:

  ```dotnetcli
  dotnet msbuild
  ```

* Сборка проекта и его зависимостей с помощью конфигурации Release:

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

* Запустите цель публикации и публикацию для RID `osx.10.11-x64`:

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

* Весь проект со всеми целевыми объектами, включенными в пакет SDK:

  ```dotnetcli
  dotnet msbuild -preprocess
  ```
