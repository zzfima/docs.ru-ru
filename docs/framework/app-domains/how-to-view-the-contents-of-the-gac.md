---
title: "Практическое руководство. Просмотр содержимого глобального кэша сборок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e50292d1cbb5f2906f053ffd6e21ca21174e2914
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="f316a-102">Практическое руководство. Просмотр содержимого глобального кэша сборок</span><span class="sxs-lookup"><span data-stu-id="f316a-102">How to: View the Contents of the Global Assembly Cache</span></span>
<span data-ttu-id="f316a-103">Используйте [средство глобального кэша сборок (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) для просмотра содержимого глобального кэша сборок.</span><span class="sxs-lookup"><span data-stu-id="f316a-103">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache.</span></span>  
  
### <a name="to-view-a-list-of-the-assemblies-in-the-global-assembly-cache"></a><span data-ttu-id="f316a-104">Просмотр списка сборок в глобальном кэше сборок</span><span class="sxs-lookup"><span data-stu-id="f316a-104">To view a list of the assemblies in the global assembly cache</span></span>  
  
1.  <span data-ttu-id="f316a-105">В [командной строке Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md) введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f316a-105">At the [Visual Studio command prompt](../../../docs/framework/tools/developer-command-prompt-for-vs.md), type the following command:</span></span>  
  
     <span data-ttu-id="f316a-106">**gacutil -l** </span><span class="sxs-lookup"><span data-stu-id="f316a-106">**gacutil -l** </span></span>  
     <span data-ttu-id="f316a-107">- или -</span><span class="sxs-lookup"><span data-stu-id="f316a-107">-or-</span></span>  
    <span data-ttu-id="f316a-108">**gacutil /l**</span><span class="sxs-lookup"><span data-stu-id="f316a-108">**gacutil /l**</span></span>  
  
 <span data-ttu-id="f316a-109">В предыдущих версиях .NET Framework с помощью расширения оболочки Windows [Shfusion.dll](http://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) можно было просматривать глобальный кэш сборок в проводнике.</span><span class="sxs-lookup"><span data-stu-id="f316a-109">In earlier versions of the .NET Framework, the [Shfusion.dll](http://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="f316a-110">Начиная с версии [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], расширение оболочки Shfusion.dll является устаревшим.</span><span class="sxs-lookup"><span data-stu-id="f316a-110">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll is obsolete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f316a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f316a-111">See Also</span></span>  
 [<span data-ttu-id="f316a-112">Работа со сборками и глобальным кэшем сборок</span><span class="sxs-lookup"><span data-stu-id="f316a-112">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="f316a-113">Gacutil.exe (программа глобального кэша сборок)</span><span class="sxs-lookup"><span data-stu-id="f316a-113">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
