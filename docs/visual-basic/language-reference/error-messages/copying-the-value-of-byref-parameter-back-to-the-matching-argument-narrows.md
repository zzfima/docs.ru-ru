---
title: "При копировании значения параметра «ByRef» &quot;&lt;parametername&gt;«обратно в соответствующий аргумент сводит тип»&lt;typename1&gt;«к типу»&lt;typename2&gt;&quot; | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32053
- vbc32053
dev_langs:
- VB
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: 8
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 84574006b2e2ccc669fdd83ebfb6eec06b00f041
ms.lasthandoff: 03/13/2017

---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a>При копировании значения параметра «ByRef» "&lt;parametername&gt;«обратно в соответствующий аргумент сводит тип»&lt;typename1&gt;«к типу»&lt;typename2&gt;"
Процедура вызывается с аргументом, который может быть расширен до соответствующего типа параметра и сужающее преобразование параметра к аргументу.  
  
 При определении класса или структуры можно определить один или несколько операторов преобразования для преобразования типа класса или структуры в другие типы. Можно также определить операторы обратного преобразования для преобразования других типов обратно в тип класса или структуры. При использовании типов класса или структуры в вызове процедуры [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] можно использовать эти операторы преобразования для преобразования типа аргумента в тип соответствующего параметра.  
  
 При передаче аргумента [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] иногда копирует его значение в локальную переменную в процедуре вместо передачи ссылки. В случае, когда процедура возвращает результат [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] должен скопировать значение локальной переменной обратно в аргумент в вызывающем коде.  
  
 Если значение аргумента `ByRef` копируется в процедуру, а аргумент и параметр имеют один и тот же тип, то преобразование не требуется. Но если типы различны, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] необходимо преобразовать в обоих направлениях. Если один из типов является типом соответствующего класса или структуры, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] необходимо преобразовать его в и из другого типа. Если один из этих преобразований является расширяющим, обратное преобразование может быть сужающим.  
  
 **Идентификатор ошибки:** BC32053  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   По возможности используйте аргумент вызова того же типа, что и параметр процедуры так [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не нужно выполнять никаких преобразований.  
  
-   Если необходимо вызвать процедуру с аргументом, тип которого отличается от типа параметра, но не требуется возвращать значение в аргумент вызова, то определите параметр для [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) вместо `ByRef`.  
  
-   Если требуется возвращать значение в аргументе, определите оператор обратного преобразования как [Widening](../../../visual-basic/language-reference/modifiers/widening.md), если это возможно.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Параметры и аргументы процедуры](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Передача аргументов по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Практическое руководство: определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [Практическое руководство: определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Преобразования типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
