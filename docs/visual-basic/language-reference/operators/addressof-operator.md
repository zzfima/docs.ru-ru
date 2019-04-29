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
ms.openlocfilehash: 9d8515b6d5b0caf3552ed05a7e0cd4a271efaf54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608350"
---
# <a name="addressof-operator-visual-basic"></a>Оператор AddressOf (Visual Basic)
Создает экземпляр делегата процедуры, который ссылается на конкретную процедуру.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Части  
 `procedurename`  
 Обязательный. Указывает процедуру, на которые ссылается созданный делегат процедуры.  
  
## <a name="remarks"></a>Примечания  
 `AddressOf` Оператор создает делегат функции, который указывает на функцию, указанную аргументом `procedurename`. Если указанная процедура является методом экземпляра, то делегат функции ссылается на экземпляр и метод. Затем при вызове делегата функция вызывает указанный метод указанного экземпляра.  
  
 `AddressOf` Оператор может использоваться в качестве операнда конструктора делегата, или он может использоваться в контексте, в котором тип делегата может определяться компилятором.  
  
## <a name="example"></a>Пример  
 В этом примере используется `AddressOf` оператор, чтобы назначить делегата для обработки `Click` события кнопки.  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется `AddressOf` оператор, чтобы назначить функцию запуска для потока.  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>См. также

- [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md)
