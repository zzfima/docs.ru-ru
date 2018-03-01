---
title: "VbStrConv.Wide и VbStrConv.Narrow не могут использоваться вместе"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrArgument_IllegalWideNarrow
ms.assetid: a53b4e6a-36b1-4e36-b2c5-8196313ec599
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 60921cbeb1d0d21c2881aaf7e651c59263af2c48
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="vbstrconvwide-and-vbstrconvnarrow-cannot-be-combined"></a>VbStrConv.Wide и VbStrConv.Narrow не могут использоваться вместе
Приложение пытается объединить взаимоисключающие элементы `VbStrConv` и `Wide` перечисления `Narrow`.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Удалите `VbStrConv.Wide` или `VbStrConv.Narrow`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Globalization>  
   
 [Знакомство с международными приложениями на платформе .NET Framework](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
