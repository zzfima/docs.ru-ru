---
title: Команда dotnet msbuild — CLI .NET Core
description: Команда dotnet msbuild обеспечивает доступ к командной строке MSBuild.
ms.date: 12/03/2018
ms.openlocfilehash: 93471ded9614502ab89d5afb19dd9992f068ef80
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128051"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet msbuild` — собирает проект и все его зависимости.

## <a name="synopsis"></a>Краткий обзор

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a>Описание

Команда `dotnet msbuild` предоставляет доступ к полнофункциональной системе MSBuild.

Команда имеет точно такие же возможности, как и существующий клиент с интерфейсом командной строки MSBuild только для проекта в стиле SDK. Все параметры одинаковы. Дополнительные сведения о доступных параметрах см. в [справочнике по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).

Команда [dotnet build](dotnet-build.md) эквивалентна `dotnet msbuild -restore -target:Build`. Обычно для сборки проектов используется `dotnet build`, но `dotnet msbuild` дает больше возможностей управления. Например, если вам нужно выполнить конкретный целевой объект (без выполнения целевого объекта сборки), возможно, потребуется использовать `dotnet msbuild`.

## <a name="examples"></a>Примеры

* Сборка проекта и его зависимостей:

  ```console
  dotnet msbuild
  ```

* Сборка проекта и его зависимостей с помощью конфигурации Release:

  ```console
  dotnet msbuild -p:Configuration=Release
  ```

* Запустите цель публикации и публикацию для RID `osx.10.11-x64`:

  ```console
  dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64
  ```

* Весь проект со всеми целевыми объектами, включенными в пакет SDK:

  ```console
  dotnet msbuild -pp
  ```