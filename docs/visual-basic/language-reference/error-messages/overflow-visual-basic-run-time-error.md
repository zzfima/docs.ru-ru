---
title: Переполнение (Ошибка во время выполнения Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: 7546676b85465577b357b7ad0757b4db8d40dbe3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863355"
---
# <a name="overflow-visual-basic-run-time-error"></a>Переполнение (Ошибка во время выполнения Visual Basic)
Переполнение возникает, когда вы попытаетесь задание, которое превышает ограничения целевой объект назначения.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что результаты назначений, вычисления и тип данных преобразования не слишком велико для представления в диапазоне от переменных, допустимых для данного типа значения и присвойте значение переменной типа, который может содержать более широкий диапазон значений , если это необходимо.  
  
2.  Убедитесь, что назначения свойств соответствуют указанному диапазону свойства, к которому они были сделаны.  
  
3.  Убедитесь, что номера, используемые в вычислениях, которые затем преобразуются в целые числа не имеют результаты, размер которых превышает целых чисел.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Int32.MaxValue?displayProperty=nameWithType>  
 <xref:System.Double.MaxValue?displayProperty=nameWithType>  
 [Типы данных](../../../visual-basic/language-reference/data-types/index.md)  
 [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)
