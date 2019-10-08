---
title: Оператор Continue (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 9ee5fb19db6eafeb7e4bed12935d0b950d6368d6
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005103"
---
# <a name="continue-statement-visual-basic"></a>Оператор Continue (Visual Basic)
Немедленно передает управление следующей итерации цикла.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>Примечания  
 Можно переносить из цикла `Do`, `For` или `While` к следующей итерации этого цикла. Управление немедленно передается в условие цикла, что эквивалентно передаче в инструкцию `For` или `While` либо на инструкцию `Do` или `Loop`, которая содержит предложение `Until` или `While`.  
  
 Можно использовать `Continue` в любом месте цикла, который допускает передачу данных. Правила, допускающие перемещение элементов управления, аналогичны [инструкциям оператора goto](../../../visual-basic/language-reference/statements/goto-statement.md).  
  
 Например, если цикл полностью содержится в блоке `Try`, блоке `Catch` или блоке `Finally`, можно использовать `Continue` для выхода из цикла. Если, с другой стороны, структура `Try`... `End Try` содержится в цикле, нельзя использовать `Continue` для передачи управления из блока `Finally`. его можно использовать для передачи из блока `Try` или `Catch`, только если вы полностью передаете @no_ Структура _T-6... `End Try`.  
  
 Если у вас есть вложенные циклы одного типа, например цикл `Do` в рамках другого цикла `Do`, оператор @no__t 2 переходит к следующей итерации внутреннего цикла `Do`, который его содержит. Нельзя использовать `Continue` для перехода к следующей итерации содержащего цикла того же типа.  
  
 Если у вас есть вложенные циклы разных типов, например цикл `Do` в цикле `For`, можно перейти к следующей итерации любого цикла, используя либо `Continue Do`, либо `Continue For`.  
  
## <a name="example"></a>Пример  
 В следующем примере кода инструкция `Continue While` используется для перехода к следующему столбцу массива, если делитель равен нулю. @No__t-0 находится внутри цикла `For`. Он передает в оператор `While col < lastcol`, который является следующей итерацией внутреннего цикла `While`, который содержит цикл `For`.  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>См. также

- [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
