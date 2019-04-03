---
title: При копировании значения ByRef параметра <parametername> обратно в соответствующий аргумент тип <typename1> сужается в тип <typename2>
ms.date: 07/20/2015
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
ms.openlocfilehash: fa8607bf72dfb344048ec82514182dcb6810274d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817166"
---
# <a name="copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument-narrows-from-type-typename1-to-type-typename2"></a>При копировании значения параметра «ByRef» "\<имя_параметра >" обратно в соответствующий аргумент сводит тип "\<Имя_типа1 >" к типу "\<имя_типа2 >"
Процедура вызывается с аргументом, который расширяется до соответствующего типа параметра, а сужающие преобразования аргумент из параметра.  
  
 При определении класса или структуры можно определить один или несколько операторов преобразования для преобразования типа класса или структуры в другие типы. Можно также определить операторы обратного преобразования для преобразования других типов обратно в тип класса или структуры. При использовании типов класса или структуры в вызове процедуры Visual Basic можно использовать эти операторы преобразования для преобразования типа аргумента в тип соответствующего параметра.  
  
 Если передается аргумент [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic иногда копирует его значение в локальную переменную в процедуре вместо передачи ссылки. В этом случае когда процедура возвращает результат, Visual Basic должен скопировать значение локальной переменной обратно в аргументе в вызывающем коде.  
  
 Если значение аргумента `ByRef` копируется в процедуру, а аргумент и параметр имеют один и тот же тип, то преобразование не требуется. Но если типы различны, Visual Basic необходимо преобразовать в обоих направлениях. Если один из типов является типом соответствующего класса или структуры, Visual Basic необходимо преобразовать в и от другого типа. Если один из этих преобразований является расширяющим, обратное преобразование может быть сужающим.  
  
 **Идентификатор ошибки:** BC32053  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   По возможности используйте аргумент вызова того же типа, что и параметр процедуры, поэтому Visual Basic не нужно выполнять никаких преобразований.  
  
-   Если необходимо вызвать процедуру с аргументом, тип которого отличается от типа параметра, но не требуется возвращать значение в аргумент вызова, то определите параметр как [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) , а не `ByRef`.  
  
-   Если требуется возвращать значение в аргумент вызова, определите оператор обратного преобразования как [Widening](../../../visual-basic/language-reference/modifiers/widening.md), если это возможно.  
  
## <a name="see-also"></a>См. также

- [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Параметры и аргументы процедуры](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Передача аргументов по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Практическое руководство. Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Преобразование типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
