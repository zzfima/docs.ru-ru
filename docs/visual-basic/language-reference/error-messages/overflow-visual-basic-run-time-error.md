---
title: "Переполнение (Ошибка во время выполнения Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1908ad576a499e79102aff23e3e2f11d7d99d52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="overflow-visual-basic-run-time-error"></a>Переполнение (Ошибка во время выполнения Visual Basic)
Переполнение является результатом присваивания, которое нарушает ограничения присваиваемого результата.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что результаты назначений, вычислений и данных типа преобразования не слишком велико для представления в диапазоне допустимых для данного типа значения переменных, а также присвоить значение переменной типа, может содержать больший диапазон значений , если это необходимо.  
  
2.  Убедитесь, что назначения свойств соответствуют указанному диапазону свойства, к которому они были сделаны.  
  
3.  Убедитесь в том, что номера, используемые в вычислениях, которые затем преобразуются в целые числа нет результатов, превышающих целые числа.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Int32.MaxValue?displayProperty=nameWithType>  
 <xref:System.Double.MaxValue?displayProperty=nameWithType>  
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)
