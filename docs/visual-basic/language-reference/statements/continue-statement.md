---
title: Оператор Continue (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a47819600a6c1d58f09c2f8ed3443632e9dab68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="continue-statement-visual-basic"></a>Оператор Continue (Visual Basic)
Передает управление непосредственно следующей итерации цикла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>Примечания  
 Можно перенести из внутри `Do`, `For`, или `While` цикла следующую итерацию цикла. Управление немедленно передается проверке условия цикла, что эквивалентно передаче `For` или `While` инструкции, или к `Do` или `Loop` инструкция, содержащая `Until` или `While` предложения.  
  
 Можно использовать `Continue` в любом месте в цикл, который позволяет передачи. Правила разрешения передачи управления совпадают с [оператор GoTo](../../../visual-basic/language-reference/statements/goto-statement.md).  
  
 Например, если цикл полностью содержаться в `Try` блока `Catch` блока или `Finally` блока, можно использовать `Continue` для передачи из цикла. Если, с другой стороны, `Try`... `End Try` структура находится внутри цикла, нельзя использовать `Continue` для передачи управления из `Finally` блок и можно использовать для передачи из `Try` или `Catch` блокировать только в том случае, если передача полностью из `Try`... `End Try` структуры.  
  
 Если у вас есть вложенные циклы одного типа, например `Do` цикла в другом `Do` цикла, `Continue Do` инструкции переходит к следующей итерации самого внутреннего `Do` цикл, который его содержит. Нельзя использовать `Continue` , чтобы перейти к следующей итерации включающего цикла того же типа.  
  
 Если у вас есть вложенные циклы разных типов, например `Do` цикла в `For` цикла, можно перейти к следующей итерации цикла, либо с помощью `Continue Do` или `Continue For`.  
  
## <a name="example"></a>Пример  
 Следующий пример кода использует `Continue While` инструкцию, чтобы пропустить следующий столбец массива, если делитель равен нулю. `Continue While` Находится внутри `For` цикла. Он передает `While col < lastcol` инструкцию, которая является следующей итерации самого внутреннего `While` цикл, который содержит `For` цикла.  
  
 [!code-vb[VbVbalrStatements#14](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/continue-statement_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
