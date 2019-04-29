---
title: Оператор Continue (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 5523be69f2901851c86f6c0263548e3577507ff9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638250"
---
# <a name="continue-statement-visual-basic"></a>Оператор Continue (Visual Basic)
Передает управление непосредственно следующей итерации цикла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>Примечания  
 Можно перенести из внутри `Do`, `For`, или `While` цикл в следующую итерацию цикла. Управление немедленно передается проверке условия цикла, что эквивалентно передаче `For` или `While` инструкции или `Do` или `Loop` инструкция, содержащая `Until` или `While` предложение.  
  
 Можно использовать `Continue` в любом расположении в цикл, который позволяет передачу. Правила разрешения передачи элемента управления совпадают с [оператор GoTo](../../../visual-basic/language-reference/statements/goto-statement.md).  
  
 Например, если цикл полностью содержится в `Try` блока, `Catch` блока или `Finally` блока, можно использовать `Continue` для передачи из цикла. Если, с другой стороны, `Try`... `End Try` структура находится внутри цикла, нельзя использовать `Continue` для передачи управления из `Finally` блок и можно использовать для передачи из `Try` или `Catch` блокируется только в том случае, если вы полностью передачи из `Try`... `End Try` структуры.  
  
 Если у вас есть вложенные циклы одного типа, например `Do` цикл в другом `Do` цикл, `Continue Do` инструкция переходит к следующей итерации самого внутреннего `Do` цикл, который его содержит. Нельзя использовать `Continue` переходите к следующей итерации цикла, содержащего того же типа.  
  
 Если у вас есть вложенные циклы разных типов, например `Do` цикл в `For` цикла, можно перейти к следующей итерации любого цикла с помощью `Continue Do` или `Continue For`.  
  
## <a name="example"></a>Пример  
 В следующем примере кода используется `Continue While` инструкцию, чтобы пропустить к следующему столбцу массива, если делитель равен нулю. `Continue While` Находится внутри `For` цикла. Он передает `While col < lastcol` инструкцию, которая является следующей итерации самого внутреннего `While` цикл, который содержит `For` цикла.  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>См. также

- [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
