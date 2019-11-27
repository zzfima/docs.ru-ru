---
title: Оператор IsTrue
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 4b863eed8406a10b9a44d7139f8659ac5cb758ad
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349514"
---
# <a name="istrue-operator-visual-basic"></a>Оператор IsTrue (Visual Basic)
Определяет, является ли выражение `True`.  
  
 Нельзя явно вызывать `IsTrue` в коде, но компилятор Visual Basic может использовать его для создания кода на основе `OrElse`ных предложений. Если вы определяете класс или структуру, а затем используете переменную этого типа в предложении `OrElse`, необходимо определить `IsTrue` для этого класса или структуры.  
  
 Компилятор рассматривает операторы `IsTrue` и `IsFalse` как *парную пару*. Это означает, что при определении одного из них необходимо также определить другой.  
  
## <a name="compiler-use-of-istrue"></a>Использование IsTrue компилятором  
 Определив класс или структуру, можно использовать переменную этого типа в операторе `For`, `If`, `Else If`или `While` или в предложении `When`. В этом случае компилятору требуется оператор, преобразующий тип в `Boolean` значение, чтобы можно было проверить условие. Он выполняет поиск подходящего оператора в следующем порядке:  
  
1. Оператор расширяющего преобразования из класса или структуры для `Boolean`.  
  
2. Оператор расширяющего преобразования из класса или структуры для `Boolean?`.  
  
3. Оператор `IsTrue` в классе или структуре.  
  
4. Суженное преобразование в `Boolean?`, которое не предусматривает преобразование из `Boolean` в `Boolean?`.  
  
5. Оператор сужения преобразования из класса или структуры в `Boolean`.  
  
 Если вы не определили преобразование в `Boolean` или оператор `IsTrue`, компилятор сигнализирует об ошибке.  
  
> [!NOTE]
> Оператор `IsTrue` может быть *перегружен*, а это означает, что класс или структура могут переопределять свое поведение, когда его операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода определяется структура структуры, включающей определения для операторов `IsFalse` и `IsTrue`.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>См. также

- [Оператор IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md)
