---
title: Оператор IsTrue (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 1152f4b512a85ae183f8fc8d476b69685e2926ef
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966916"
---
# <a name="istrue-operator-visual-basic"></a>Оператор IsTrue (Visual Basic)
Определяет, является `True`ли выражение.  
  
 В коде нельзя `IsTrue` вызывать явным образом, но компилятор Visual Basic может использовать его для создания кода из `OrElse` предложений. Если вы определяете класс или структуру, а затем используете переменную этого типа в `OrElse` предложении, необходимо определить `IsTrue` для этого класса или структуры.  
  
 Компилятор рассматривает `IsTrue` операторы и `IsFalse` как парную *пару*. Это означает, что при определении одного из них необходимо также определить другой.  
  
## <a name="compiler-use-of-istrue"></a>Использование IsTrue компилятором  
 После определения класса или структуры можно `For`использовать переменную этого типа в операторе `Else If`, `If`, или `While` , или в `When` предложении. В этом случае компилятору требуется оператор, который преобразует тип в `Boolean` значение, чтобы можно было проверить условие. Он выполняет поиск подходящего оператора в следующем порядке:  
  
1. Оператор расширяющего преобразования из класса или структуры в `Boolean`.  
  
2. Оператор расширяющего преобразования из класса или структуры в `Boolean?`.  
  
3. `IsTrue` Оператор для класса или структуры.  
  
4. Суженное преобразование в `Boolean?` , не охватывающее преобразование из `Boolean` в `Boolean?`.  
  
5. Оператор сужения преобразования из класса или структуры в `Boolean`.  
  
 Если не было определено преобразование в `Boolean` `IsTrue` оператор или, компилятор сообщает об ошибке.  
  
> [!NOTE]
> Оператор можно перегрузить, что означает, что класс или структура может переопределить свое поведение, если его операнд имеет тип этого класса или структуры. `IsTrue` Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода определяется структура структуры, включающей определения для `IsFalse` операторов и. `IsTrue`  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>См. также

- [Оператор IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md)
