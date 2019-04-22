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
ms.openlocfilehash: 680084c39b90d4f664f48559fa21388ce192d999
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58837745"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>Практическое руководство. Разбиение и объединение инструкций в коде (Visual Basic)
При написании кода, в некоторых случаях может создать длинный оператор, требующий горизонтальной прокрутки в редакторе кода. Несмотря на то, что это не повлияет на способ ваш код, он усложняет задачу вы или кто-то еще чтение кода, как оно отображается на мониторе. В таких случаях следует обдумать разбиение одной инструкции long в несколько строк.  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a>Чтобы разбить на несколько строк одной инструкции  
  
-   Использовать символ продолжения строки — символ подчеркивания (`_`), в момент, в которое нужно разбиения строки. Непосредственно перед знаком подчеркивания должен стоять пробел, а сразу за ним должен быть признак конца строки (возврат каретки).  
  
    > [!NOTE]
    >  В некоторых случаях если не указан символ продолжения строки, компилятор Visual Basic неявно продолжит инструкцию на следующей строке кода. Список элементов синтаксиса, для которых можно опустить символ продолжения строки, см. в разделе «Неявное продолжение строки» в [инструкций](../../../visual-basic/programming-guide/language-features/statements.md).  
  
     В следующем примере инструкция разбивается на четыре строки завершает символы продолжения строки, но последняя строка.  
  
     [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]  
  
     С помощью этой последовательности делает код более удобным для чтения, так и печати.  
  
     Символ продолжения строки должен быть последним символом в строке. Он не может следовать с другими компонентами в той же строке.  
  
     Существуют ограничения на где можно использовать символ продолжения строки; например его нельзя использовать середине имя аргумента. Вы можете прервать список аргументов с символом продолжения строки, но имена отдельных аргументов должны оставаться без изменений.  
  
     Не удается продолжить комментарий с помощью символа продолжения строки. Компилятор не изучите символы в комментарии для специального значения. Для многострочных комментариев, повторите символ комментария (`'`) в каждой строке.  
  
 Несмотря на то, что рекомендуется размещать каждый оператор в отдельной строке, Visual Basic также позволяет объединять несколько операторов в той же строке.  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a>Чтобы разместить несколько операторов в одной строке  
  
-   Разместите операторов с запятой (`:`), как показано в следующем примере.  
  
     [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]  
  
## <a name="see-also"></a>См. также

- [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
