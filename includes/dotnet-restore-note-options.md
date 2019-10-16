---
ms.openlocfilehash: 47811d3fab2e4fa531d383dfe818e3cac5613eb3
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2019
ms.locfileid: "72179980"
---
> [!NOTE]
> <span data-ttu-id="b3657-101">Начиная с .NET Core 2.0 нет необходимости выполнять команду [`dotnet restore`](~/docs/core/tools/dotnet-restore.md), так как она выполняется неявно всеми командами, которые требуют восстановления, например `dotnet build` и `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="b3657-101">Starting with .NET Core 2.0, you don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands that require a restore to occur, such as `dotnet build` and `dotnet run`.</span></span> <span data-ttu-id="b3657-102">Эту команду по-прежнему можно использовать в некоторых сценариях, где необходимо явное восстановление, например в [сборках с использованием непрерывной интеграции в Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) или системах сборки, где требуется явно контролировать время восстановления.</span><span class="sxs-lookup"><span data-stu-id="b3657-102">It's still a valid command in certain scenarios where doing an explicit restore makes sense, such as [continuous integration builds in Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control the time at which the restore occurs.</span></span>
>
> <span data-ttu-id="b3657-103">Эта команда также поддерживает параметры `dotnet restore` при передаче в длинной форме (например, `--source`).</span><span class="sxs-lookup"><span data-stu-id="b3657-103">This command also supports the `dotnet restore` options when passed in the long form (for example, `--source`).</span></span> <span data-ttu-id="b3657-104">Параметры в краткой форме, например `-s`, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="b3657-104">Short form options, such as `-s`, are not supported.</span></span>
