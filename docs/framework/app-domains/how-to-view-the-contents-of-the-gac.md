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
ms.openlocfilehash: b4cc4b1a3e68d6d39e13a56b2a519d15b72bd3a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="33568-102">Практическое руководство. Просмотр содержимого глобального кэша сборок</span><span class="sxs-lookup"><span data-stu-id="33568-102">How to: View the Contents of the Global Assembly Cache</span></span>
<span data-ttu-id="33568-103">Используйте [средство глобального кэша сборок (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) для просмотра содержимого глобального кэша сборок.</span><span class="sxs-lookup"><span data-stu-id="33568-103">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache.</span></span>  
  
### <a name="to-view-a-list-of-the-assemblies-in-the-global-assembly-cache"></a><span data-ttu-id="33568-104">Просмотр списка сборок в глобальном кэше сборок</span><span class="sxs-lookup"><span data-stu-id="33568-104">To view a list of the assemblies in the global assembly cache</span></span>  
  
1.  <span data-ttu-id="33568-105">В [командной строке Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md) введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="33568-105">At the [Visual Studio command prompt](../../../docs/framework/tools/developer-command-prompt-for-vs.md), type the following command:</span></span>  
  
     <span data-ttu-id="33568-106">**gacutil -l** </span><span class="sxs-lookup"><span data-stu-id="33568-106">**gacutil -l** </span></span>  
     <span data-ttu-id="33568-107">- или -</span><span class="sxs-lookup"><span data-stu-id="33568-107">-or-</span></span>  
    <span data-ttu-id="33568-108">**gacutil /l**</span><span class="sxs-lookup"><span data-stu-id="33568-108">**gacutil /l**</span></span>  
  
 <span data-ttu-id="33568-109">В предыдущих версиях .NET Framework с помощью расширения оболочки Windows [Shfusion.dll](http://msdn.microsoft.com/en-us/0d9464cf-ddba-4ca9-bbec-f678fb58f380) можно было просматривать глобальный кэш сборок в проводнике.</span><span class="sxs-lookup"><span data-stu-id="33568-109">In earlier versions of the .NET Framework, the [Shfusion.dll](http://msdn.microsoft.com/en-us/0d9464cf-ddba-4ca9-bbec-f678fb58f380) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="33568-110">Начиная с версии [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], расширение оболочки Shfusion.dll является устаревшим.</span><span class="sxs-lookup"><span data-stu-id="33568-110">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll is obsolete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33568-111">См. также</span><span class="sxs-lookup"><span data-stu-id="33568-111">See Also</span></span>  
 [<span data-ttu-id="33568-112">Работа со сборками и глобальным кэшем сборок</span><span class="sxs-lookup"><span data-stu-id="33568-112">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="33568-113">Gacutil.exe (программа глобального кэша сборок)</span><span class="sxs-lookup"><span data-stu-id="33568-113">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
