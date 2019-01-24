---
title: Переполнение (Ошибка во время выполнения Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: c45559042231b72ef1ba892cabbead03797df8e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642520"
---
# <a name="overflow-visual-basic-run-time-error"></a>Переполнение (Ошибка во время выполнения Visual Basic)
Переполнение возникает, когда вы попытаетесь задание, которое превышает ограничения целевой объект назначения.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что результаты назначений, вычисления и тип данных преобразования не слишком велико для представления в диапазоне от переменных, допустимых для данного типа значения и присвойте значение переменной типа, который может содержать более широкий диапазон значений , если это необходимо.  
  
2.  Убедитесь, что назначения свойств соответствуют указанному диапазону свойства, к которому они были сделаны.  
  
3.  Убедитесь, что номера, используемые в вычислениях, которые затем преобразуются в целые числа не имеют результаты, размер которых превышает целых чисел.  
  
## <a name="see-also"></a>См. также
- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)
