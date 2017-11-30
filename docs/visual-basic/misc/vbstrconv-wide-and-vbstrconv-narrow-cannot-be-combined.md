---
title: "VbStrConv.Wide и VbStrConv.Narrow не могут использоваться вместе"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrArgument_IllegalWideNarrow
ms.assetid: a53b4e6a-36b1-4e36-b2c5-8196313ec599
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cb42ffd72a7e1f9bceabc8e8b67310b4ca2ab716
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="vbstrconvwide-and-vbstrconvnarrow-cannot-be-combined"></a>VbStrConv.Wide и VbStrConv.Narrow не могут использоваться вместе
Приложение пытается объединить взаимоисключающие элементы `VbStrConv` и `Wide` перечисления `Narrow`.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Удалите `VbStrConv.Wide` или `VbStrConv.Narrow`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Globalization>  
 [НЕ В СБОРКЕ. Перечисление VbStrConv](http://msdn.microsoft.com/en-us/59f83dd9-6361-47df-a836-02ba9d4cb936)  
 [Знакомство с международными приложениями на платформе .NET Framework](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
