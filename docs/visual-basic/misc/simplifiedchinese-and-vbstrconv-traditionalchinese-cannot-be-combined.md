---
title: "VbStrConv.SimplifiedChinese и VbStrConv.TraditionalChinese не могут использоваться вместе"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrArgument_StrConvSCandTC
ms.assetid: d8e6a11b-f549-43b5-8337-0594340e1325
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 602f375eece2d79eb2f839b220b7774ebc3a847e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="simplifiedchinese-and-vbstrconvtraditionalchinese-cannot-be-combined"></a>VbStrConv.SimplifiedChinese и VbStrConv.TraditionalChinese не могут использоваться вместе
Приложение пытается объединить взаимоисключающие элементы `VbStrConv` и `SimplifiedChinese` , являющиеся членами перечисления `TraditionalChinese`.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите `VbStrConv.SimplifiedChinese` или `VbStrConv.TraditionalChinese`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Globalization>  
 [НЕ В СБОРКЕ. Перечисление VbStrConv](http://msdn.microsoft.com/en-us/59f83dd9-6361-47df-a836-02ba9d4cb936)  
 [Знакомство с международными приложениями на платформе .NET Framework](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
