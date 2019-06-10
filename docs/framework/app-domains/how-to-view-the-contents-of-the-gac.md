---
title: Практическое руководство. Просмотр содержимого глобального кэша сборок
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, viewing contents
- viewing assemblies in global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- GAC (global assembly cache), viewing contents
- list of assemblies in global assembly cache
- Global Assembly Cache tool
ms.assetid: c5f786a0-969b-4f14-9f02-e77c3384d9af
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c319c5f7c9bb808b2ce7ee10178722287e456339
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486425"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="72793-102">Практическое руководство. Просмотр содержимого глобального кэша сборок</span><span class="sxs-lookup"><span data-stu-id="72793-102">How to: View the contents of the global assembly cache</span></span>

<span data-ttu-id="72793-103">Используйте [средство глобального кэша сборок (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) для просмотра содержимого глобального кэша сборок (GAC).</span><span class="sxs-lookup"><span data-stu-id="72793-103">Use the [global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache (GAC).</span></span>

## <a name="view-the-assemblies-in-the-gac"></a><span data-ttu-id="72793-104">Просмотр сборок в GAC</span><span class="sxs-lookup"><span data-stu-id="72793-104">View the assemblies in the GAC</span></span>

<span data-ttu-id="72793-105">Чтобы просмотреть список сборок в GAC, откройте [командную строку разработчика для Visual Studio](../tools/developer-command-prompt-for-vs.md), а затем введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="72793-105">To view a list of the assemblies in the global assembly cache, open [Developer Command Prompt for Visual Studio](../tools/developer-command-prompt-for-vs.md), and then enter the following command:</span></span>

```shell
gacutil -l
```

<span data-ttu-id="72793-106">- или -</span><span class="sxs-lookup"><span data-stu-id="72793-106">-or-</span></span>

```shell
gacutil /l
```

> [!NOTE]
> <span data-ttu-id="72793-107">В предыдущих версиях .NET Framework с помощью расширения оболочки Windows [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) можно было просматривать глобальный кэш сборок в проводнике.</span><span class="sxs-lookup"><span data-stu-id="72793-107">In earlier versions of the .NET Framework, the [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="72793-108">Начиная с версии .NET Framework 4, расширение оболочки Shfusion.dll является устаревшим.</span><span class="sxs-lookup"><span data-stu-id="72793-108">Beginning with the .NET Framework 4, Shfusion.dll is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="72793-109">См. также</span><span class="sxs-lookup"><span data-stu-id="72793-109">See also</span></span>

- [<span data-ttu-id="72793-110">Работа со сборками и глобальным кэшем сборок</span><span class="sxs-lookup"><span data-stu-id="72793-110">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="72793-111">Gacutil.exe (программа глобального кэша сборок)</span><span class="sxs-lookup"><span data-stu-id="72793-111">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
