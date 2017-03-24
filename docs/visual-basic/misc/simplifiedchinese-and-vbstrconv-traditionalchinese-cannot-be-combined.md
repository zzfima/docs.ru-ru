---
title: "Китайский упрощенный и VbStrConv.TraditionalChinese нельзя объединять | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrArgument_StrConvSCandTC
ms.assetid: d8e6a11b-f549-43b5-8337-0594340e1325
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 57ab14cdcb3e4b27e821097dcfca4d97e1633035
ms.lasthandoff: 03/13/2017

---
# <a name="simplifiedchinese-and-vbstrconvtraditionalchinese-cannot-be-combined"></a>VbStrConv.SimplifiedChinese и VbStrConv.TraditionalChinese не могут использоваться вместе
Приложение пытается объединить взаимоисключающие элементы `VbStrConv` и `SimplifiedChinese` , являющиеся членами перечисления `TraditionalChinese`.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите `VbStrConv.SimplifiedChinese` или `VbStrConv.TraditionalChinese`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Globalization>   
 [Перечисления VbStrConv NOTINBUILD](http://msdn.microsoft.com/en-us/59f83dd9-6361-47df-a836-02ba9d4cb936)   
 [Знакомство с международными приложениями на платформе .NET Framework](https://docs.microsoft.com/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
