---
title: Оператор AddressOf (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 7c229c32a3b295b4dbfe50ca2abc60d4ad5f2145
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="addressof-operator-visual-basic"></a>Оператор AddressOf (Visual Basic)
Создает экземпляр делегата процедуры, ссылающийся на конкретную процедуру.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Части  
 `procedurename`  
 Обязательно. Указывает процедуру, на которые ссылается созданный делегат процедуры.  
  
## <a name="remarks"></a>Примечания  
 `AddressOf` Оператор создает делегат функции, который указывает функции, указанной `procedurename`. Если указанная процедура является методом экземпляра, то делегат функции ссылается на экземпляр и метод. Затем при вызове функции вызывается указанный метод указанного экземпляра.  
  
 `AddressOf` Оператор можно использовать в качестве операнда конструктора делегата, или он может использоваться в контексте, в котором тип делегата может определяться компилятором.  
  
## <a name="example"></a>Пример  
 В этом примере используется `AddressOf` оператор, чтобы назначить делегата для обработки `Click` события кнопки.  
  
 [!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется `AddressOf` оператор, чтобы назначить функцию запуска для потока.  
  
 [!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md)
