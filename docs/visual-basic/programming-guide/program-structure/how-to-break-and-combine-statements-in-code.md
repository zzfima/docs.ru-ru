---
title: "Практическое руководство: разбиение и объединение инструкций в коде (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb._
dev_langs:
- VB
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
- underscores, in code
- statements [Visual Basic], line continuation in
- line breaks, in code
- line-continuation character
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
caps.latest.revision: 21
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 840036a91f430f72e0258b8be466770f2855a58f
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>Практическое руководство. Разбиение и объединение инструкций в коде (Visual Basic)
Во время написания кода может быть создан длинный оператор, требующий горизонтальной прокрутки в окне редактора кода. Несмотря на то, что это не влияет на способ выполняется код, он создает сложности вы или кто-то еще чтение кода, как он отображается на экране монитора. В таких случаях следует обдумать разбиение один длинный оператор на несколько строк.  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a>Чтобы разбить один оператор на несколько строк  
  
-   Использовать знак продолжения строки — символ подчеркивания (`_`), в том месте, в котором разбиения строки. Непосредственно перед знаком подчеркивания должен стоять пробел, а сразу за ним должен быть признак конца строки (возврат каретки).  
  
    > [!NOTE]
    >  В некоторых случаях если опустить знак продолжения строки, компилятор Visual Basic неявно продолжит инструкцию на следующей строке кода. Список элементов синтаксиса, для которых можно опустить знак продолжения строки, в разделе «Неявное продолжение строки» в [инструкции](../../../visual-basic/programming-guide/language-features/statements.md).  
  
     В следующем примере оператор разбивается на четыре строки завершает все символы продолжения строки, но последняя строка.  
  
     [!code-vb[VbVbcnConventions&20;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]  
  
     Использование этой последовательности делает код более удобными для чтения, так и при печати.  
  
     Знак продолжения строки должен быть последним символом в строке. Вы не может следовать с другими объектами в той же строке.  
  
     Существуют некоторые ограничения, о том, где можно использовать символ продолжения строки; например его нельзя использовать в середине имени аргумента. Можно разбить список аргументов знак продолжения строки, но имена отдельных аргументов должны оставаться неизменными.  
  
     Не удается продолжить комментарий с помощью символа продолжения строки. Компилятор не Проверьте символы комментария для особое значение. Для многострочных комментариев, символа начала комментария (`'`) в каждой строке.  
  
 Несмотря на то, что размещать каждый оператор в отдельной строке является рекомендуемым методом [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] также позволяет объединять несколько операторов в одной строке.  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a>Чтобы разместить несколько операторов в одной строке  
  
-   Операторы разделяются точкой с запятой (`:`), как показано в следующем примере.  
  
     [!code-vb[VbVbcnConventions&#10;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Структура программы и соглашения о коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
