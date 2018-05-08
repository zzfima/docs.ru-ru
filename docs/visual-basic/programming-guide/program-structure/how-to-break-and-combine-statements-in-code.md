---
title: Практическое руководство. Разбиение и объединение инструкций в коде (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb._
helpviewer_keywords:
- colons (:)
- line continuation
- _ line-continuation character
- ': line separator character'
- Visual Basic code, line breaks in
- Visual Basic code, line breaks
- Visual Basic code, line continuation
- long lines of code
- line terminator
- line-continuation sequence
- underscores [Visual Basic], in code
- statements [Visual Basic], line continuation in
- line breaks [Visual Basic], in code
- line-continuation character [Visual Basic]
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
ms.openlocfilehash: 6bca3d62cb3e886ee08b9169d63d4c3a38247f3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>Практическое руководство. Разбиение и объединение инструкций в коде (Visual Basic)
При написании кода, в некоторых случаях может создать длинный оператор, требующий горизонтальной прокрутки в окне редактора кода. Несмотря на то, что это не влияет на внешний код выполняется, он создает сложности при или кто-то еще чтение кода, как он отображается на мониторе. В таких случаях следует разбивает один длинный оператор на несколько строк.  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a>Чтобы разбить один оператор на несколько строк  
  
-   Использовать символ продолжения строки — символ подчеркивания (`_`), в точке, в которой необходимо разбиения строки. Непосредственно перед знаком подчеркивания должен стоять пробел, а сразу за ним должен быть признак конца строки (возврат каретки).  
  
    > [!NOTE]
    >  В некоторых случаях если не указан знак продолжения строки, компилятор Visual Basic неявно продолжит инструкцию на следующей строке кода. Список элементов синтаксиса, для которых можно опустить знак продолжения строки см. в разделе «Неявное продолжение строки» в [инструкции](../../../visual-basic/programming-guide/language-features/statements.md).  
  
     В следующем примере оператор разбивается на четыре строки завершается, все символы продолжения строки, но последней строки.  
  
     [!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]  
  
     Использование этой последовательности делает код более удобным для чтения, так и при печати.  
  
     Знак продолжения строки должен быть последним символом в строке. Вы не выполните с других символов в той же строке.  
  
     Существуют некоторые ограничения на где можно использовать символ продолжения строки; например его нельзя использовать в середине имени аргумента. Может быть разбит на список аргументов с символом продолжения строки, но отдельные имена аргументов должны оставаться без изменений.  
  
     Не удается продолжить комментарий с помощью символ продолжения строки. Компилятор не изучите символов в комментарии для особое значение. Для многострочных комментариев, символа начала комментария (`'`) в каждой строке.  
  
 Хотя в общем случае рекомендуется размещать каждый оператор в отдельной строке, Visual Basic также позволяет объединять несколько операторов в той же строке.  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a>Чтобы разместить несколько операторов в одной строке  
  
-   Операторы разделяются точкой с запятой (`:`), как показано в следующем примере.  
  
     [!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
