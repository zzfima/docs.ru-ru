---
title: Оператор IsFalse (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 85fd6b9264fa80c3636f2cb839c8fc5ed855ddc8
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965661"
---
# <a name="isfalse-operator-visual-basic"></a>Оператор IsFalse (Visual Basic)
Определяет, является ли выражение `False`.  
  
 Нельзя вызывать `IsFalse` явно в коде, но в Visual Basic компилятор может использовать его для создания кода из `AndAlso` предложения. Если вы задаете класса или структуры, а затем использовать переменную этого типа в `AndAlso` предложение, необходимо определить `IsFalse` для этого класса или структуры.  
  
 Компилятор считает, что `IsFalse` и `IsTrue` операторы как *соответствующую пару*. Это означает, что если определить один из них, необходимо также определить другой.  
  
> [!NOTE]
>  `IsFalse` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если его операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода определяется контур структуры, содержащей определения для `IsFalse` и `IsTrue` операторы.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>См. также
- [Оператор IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md)
