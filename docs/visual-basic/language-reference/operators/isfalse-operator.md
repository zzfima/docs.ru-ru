---
title: Оператор IsFalse
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 51b7bfb2cf5301a39818e6566b408ee0677689f2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349518"
---
# <a name="isfalse-operator-visual-basic"></a>Оператор IsFalse (Visual Basic)
Определяет, является ли выражение `False`.  
  
 Нельзя явно вызывать `IsFalse` в коде, но компилятор Visual Basic может использовать его для создания кода на основе `AndAlso`ных предложений. Если вы определяете класс или структуру, а затем используете переменную этого типа в предложении `AndAlso`, необходимо определить `IsFalse` для этого класса или структуры.  
  
 Компилятор рассматривает операторы `IsFalse` и `IsTrue` как *парную пару*. Это означает, что при определении одного из них необходимо также определить другой.  
  
> [!NOTE]
> Оператор `IsFalse` может быть *перегружен*, а это означает, что класс или структура могут переопределять свое поведение, когда его операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода определяется структура структуры, включающей определения для операторов `IsFalse` и `IsTrue`.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>См. также

- [Оператор IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md)
