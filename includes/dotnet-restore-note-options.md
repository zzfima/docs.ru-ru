---
ms.openlocfilehash: 497ac09e5c9a10470d3ae1932d7e3dc114d121dd
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632018"
---
> [!NOTE]
> Начиная с .NET Core 2.0 нет необходимости выполнять команду [`dotnet restore`](~/docs/core/tools/dotnet-restore.md), так как она выполняется неявно всеми командами, которые требуют восстановления, например `dotnet build` и `dotnet run`. Эту команду по-прежнему можно использовать в некоторых сценариях, где необходимо явное восстановление, например в [сборках с использованием непрерывной интеграции в Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) или системах сборки, где требуется явно контролировать время восстановления.
>
> Эта команда также поддерживает параметры `dotnet restore` при передаче в длинной форме (например, `--source`). Параметры в краткой форме, например `-s`, не поддерживаются.
