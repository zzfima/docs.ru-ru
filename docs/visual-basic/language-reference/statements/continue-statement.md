---
title: Оператор Continue
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 20140cafb68c7e5518bf3d5fa80e56ca1c1de2c6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354112"
---
# <a name="continue-statement-visual-basic"></a>Оператор Continue (Visual Basic)
Немедленно передает управление следующей итерации цикла.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>Примечания  
 Можно переносить из цикла `Do`, `For`или `While` в следующую итерацию этого цикла. Управление немедленно передается в условие цикла, что эквивалентно передаче в оператор `For` или `While` либо на `Do` или `Loop` инструкцию, содержащую `Until` или `While`.  
  
 `Continue` можно использовать в любом расположении в цикле, допускающем передачу данных. Правила, допускающие перемещение элементов управления, аналогичны [инструкциям оператора goto](../../../visual-basic/language-reference/statements/goto-statement.md).  
  
 Например, если цикл полностью содержится в блоке `Try`, блоке `Catch` или блоке `Finally`, можно использовать `Continue` для перемещения из цикла. С другой стороны, если структура `Try`...`End Try` содержится в цикле, нельзя использовать `Continue` для передачи управления из блока `Finally`, и его можно использовать для передачи из `Try` или `Catch` блока только в том случае, если вы полностью передаете структуру `Try`...`End Try`.  
  
 Если у вас есть вложенные циклы одного типа, например цикл `Do` в рамках другого цикла `Do`, то оператор `Continue Do` переходит к следующей итерации самого внутреннего цикла `Do`, который его содержит. Нельзя использовать `Continue` для перехода к следующей итерации содержащего цикла того же типа.  
  
 Если у вас есть вложенные циклы разных типов, например цикл `Do` в цикле `For`, можно перейти к следующей итерации любого цикла, используя либо `Continue Do`, либо `Continue For`.  
  
## <a name="example"></a>Пример  
 В следующем примере кода инструкция `Continue While` используется для перехода к следующему столбцу массива, если делитель равен нулю. `Continue While` находится внутри цикла `For`. Он передает оператору `While col < lastcol`, который является следующей итерацией самого внутреннего цикла `While`, содержащего цикл `For`.  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>См. также

- [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
