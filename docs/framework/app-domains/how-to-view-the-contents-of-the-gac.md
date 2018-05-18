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
ms.openlocfilehash: d6e582f86eac03a51437b965f87f1bc7f29294eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a>Практическое руководство. Просмотр содержимого глобального кэша сборок
Используйте [средство глобального кэша сборок (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) для просмотра содержимого глобального кэша сборок.  
  
### <a name="to-view-a-list-of-the-assemblies-in-the-global-assembly-cache"></a>Просмотр списка сборок в глобальном кэше сборок  
  
1.  В [командной строке Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md) введите следующую команду:  
  
     **gacutil -l**   
     - или -  
    **gacutil /l**  
  
 В предыдущих версиях .NET Framework с помощью расширения оболочки Windows [Shfusion.dll](http://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) можно было просматривать глобальный кэш сборок в проводнике. Начиная с версии [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], расширение оболочки Shfusion.dll является устаревшим.  
  
## <a name="see-also"></a>См. также  
 [Работа со сборками и глобальным кэшем сборок](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [Gacutil.exe (программа глобального кэша сборок)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
