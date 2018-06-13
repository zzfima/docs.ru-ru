---
title: Оператор IsFalse (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: e84b2162eb0763725f05bc52d5c4223d7c430b81
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600051"
---
# <a name="isfalse-operator-visual-basic"></a>Оператор IsFalse (Visual Basic)
Определяет, является ли выражение `False`.  
  
 Не удается вызвать `IsFalse` явно в коде, но в Visual Basic компилятор может использовать его для создания кода из `AndAlso` предложения. Если вы задаете класса или структуры, а затем используется переменная этого типа в `AndAlso` предложение, необходимо определить `IsFalse` для этого класса или структуры.  
  
 Компилятор считает, что `IsFalse` и `IsTrue` операторы, как *соответствующие пары*. Это означает, что если определить один из них, необходимо также определить другой.  
  
> [!NOTE]
>  `IsFalse` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если его операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода определяется контур структуры, содержащей определения для `IsFalse` и `IsTrue` операторы.  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isfalse-operator_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md)
