---
title: Практическое руководство. Разбиение и объединение операторов в коде (Visual Basic)
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
ms.openlocfilehash: 745974523bd747dd23f3cfaf7cb70bb6cd4513f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946202"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>Практическое руководство. Разбиение и объединение операторов в коде (Visual Basic)
При написании кода иногда можно создавать длинные операторы, требующие горизонтальной прокрутки в редакторе кода. Хотя это не влияет на способ выполнения кода, он затрудняет чтение кода в том виде, в котором он отображается на мониторе. В таких случаях следует рассмотреть возможность разбиения одного длинного оператора на несколько строк.  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a>Разбиение одного оператора на несколько строк  
  
- Используйте символ продолжения строки, который является подчеркиванием (`_`), в точке, в которой должна прерываться линия. Непосредственно перед знаком подчеркивания должен стоять пробел, а сразу за ним должен быть признак конца строки (возврат каретки).  
  
    > [!NOTE]
    > В некоторых случаях, если опустить символ продолжения строки, компилятор Visual Basic неявно продолжит инструкцию на следующей строке кода. Список элементов синтаксиса, для которых можно опустить символ продолжения строки, см. в разделе «неявные продолжения строки» в [инструкциях](../../../visual-basic/programming-guide/language-features/statements.md).  
  
     В следующем примере инструкция разбивается на четыре строки с символами продолжения строки, завершающими все, кроме последней строки.  
  
     [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]  
  
     Использование этой последовательности упрощает чтение кода в сети и при печати.  
  
     Символ продолжения строки должен быть последним символом в строке. Вы не можете подписаться на него другим в той же строке.  
  
     Существуют некоторые ограничения, в которых можно использовать символ продолжения строки. Например, нельзя использовать его в середине имени аргумента. Можно прервать список аргументов с помощью символа продолжения строки, но отдельные имена аргументов должны оставаться неизменными.  
  
     Комментарий нельзя продолжить с помощью символа продолжения строки. Компилятор не проверяет символы в комментарии на наличие специального значения. Для многострочного комментария повторите символ комментария (`'`) в каждой строке.  
  
 Хотя размещение каждой инструкции в отдельной строке является рекомендуемым методом, Visual Basic также позволяет размещать несколько инструкций в одной строке.  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a>Размещение нескольких инструкций на одной строке  
  
- Разделите операторы с помощью двоеточия`:`(), как показано в следующем примере.  
  
     [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]  
  
## <a name="see-also"></a>См. также

- [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
