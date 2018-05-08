---
title: VbStrConv.SimplifiedChinese и VbStrConv.TraditionalChinese не могут использоваться вместе
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_StrConvSCandTC
ms.assetid: d8e6a11b-f549-43b5-8337-0594340e1325
ms.openlocfilehash: e9bee8c0e9b534704bdd2bef7d61042886f0a91a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="simplifiedchinese-and-vbstrconvtraditionalchinese-cannot-be-combined"></a>VbStrConv.SimplifiedChinese и VbStrConv.TraditionalChinese не могут использоваться вместе
Приложение пытается объединить взаимоисключающие элементы `VbStrConv` и `SimplifiedChinese` , являющиеся членами перечисления `TraditionalChinese`.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите `VbStrConv.SimplifiedChinese` или `VbStrConv.TraditionalChinese`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Globalization>  
   
 [Знакомство с международными приложениями на платформе .NET Framework](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
