---
title: Оператор IsTrue (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: fc01b074d9aba245b1c55b75b841a7f195f7ec04
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="istrue-operator-visual-basic"></a>Оператор IsTrue (Visual Basic)
Определяет, является ли выражение `True`.  
  
 Не удается вызвать `IsTrue` явно в коде, но в Visual Basic компилятор может использовать его для создания кода из `OrElse` предложения. Если вы задаете класса или структуры, а затем используется переменная этого типа в `OrElse` предложение, необходимо определить `IsTrue` для этого класса или структуры.  
  
 Компилятор считает, что `IsTrue` и `IsFalse` операторы, как *соответствующие пары*. Это означает, что если определить один из них, необходимо также определить другой.  
  
## <a name="compiler-use-of-istrue"></a>Использование IsTrue компилятором  
 После определения класса или структуры, можно использовать переменную этого типа в `For`, `If`, `Else``If`, или `While` инструкции, либо в `When` предложения. После этого компилятор требует оператор, который преобразует тип в `Boolean` значение, чтобы проверить условие. Он выполняет поиск подходящего оператора в следующем порядке:  
  
1.  Оператор расширяющего преобразования от класса или структуры `Boolean`.  
  
2.  Оператор расширяющего преобразования от класса или структуры `Boolean?`.  
  
3.  `IsTrue` Оператор в классе или структуре.  
  
4.  Сужающее преобразование `Boolean?` , не включает преобразование из `Boolean` для `Boolean?`.  
  
5.  Оператор сужающего преобразования от класса или структуры `Boolean`.  
  
 Если не определены никакие преобразования в `Boolean` или `IsTrue` оператор, компилятор сообщает об ошибке.  
  
> [!NOTE]
>  `IsTrue` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если его операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода определяется контур структуры, содержащей определения для `IsFalse` и `IsTrue` операторы.  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/istrue-operator_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md)
