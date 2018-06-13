---
title: Структуры решений (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: 1ede40d196b470a351aca4c60b33f074df14b86a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648201"
---
# <a name="decision-structures-visual-basic"></a>Структуры решений (Visual Basic)
Visual Basic позволяет проверять условия и выполнять различные операции в зависимости от результатов этой проверки. Можно проверить условие true или false, для различных значений выражений или исключений, выдаваемых при выполнении ряд инструкций.  
  
 На следующем рисунке структуру выбора, который проверяет условие и выполняет различные действия в зависимости от того, является ли значение true или false.  
  
 ![Блок-схема If... Затем... Else построения](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")  
Выполняет различные действия, если условие имеет значение true, а если он имеет значение false  
  
## <a name="ifthenelse-construction"></a>If... Затем... Else построения  
 `If...Then...Else` позволяют проверить одно или несколько условий и выполнить один или несколько операторов для каждого условия. Можно проверить условия и выполнения действий одним из следующих способов:  
  
-   Запустить один или несколько операторов, если условие равно `True`  
  
-   Запустить один или несколько операторов, если условие равно `False`  
  
-   Выполнить некоторые операторы, если условие равно `True` и другие — если `False`  
  
-   Проверить дополнительное условие, если предыдущее условие `False`  
  
 Управляющая структура, обеспечивающая все эти возможности — [Если... Затем... Оператор Else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md). Можно использовать простую версию при наличии только одного условия и одного оператора для выполнения. Если имеется более сложный набор условий и действий, можно использовать версию несколько строк.  
  
## <a name="selectcase-construction"></a>Выберите... Case построения  
 `Select...Case` Позволяет вычислить выражение один раз и выполнить различные наборы операторов на основе различных значений. Дополнительные сведения см. в разделе [выберите... Оператор выбора](../../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="trycatchfinally-construction"></a>Конструкция TRY... CATCH... Конструкции finally  
 `Try...Catch...Finally` позволяют выполнять набор инструкций в среде, которая сохраняет управление, если какой-либо из операторов вызовет исключение. Можно выполнять различные действия для различных исключений. При необходимости можно указать блок кода, который выполняется перед выходом из всей `Try...Catch...Finally` конструкция, независимо от того, что происходит. Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
>  Для многих управляющих структур при щелчке ключевого слова, все ключевые слова в структуре, выделяются. Например, при нажатии кнопки `If` в `If...Then...Else` конструкции, все экземпляры `If`, `Then`, `ElseIf`, `Else`, и `End If` выделяются при построении. Чтобы переместить выделенный следующей или предыдущей ключевое слово, нажмите клавиши CTRL + SHIFT + СТРЕЛКА ВНИЗ или CTRL + SHIFT + Стрелка вверх.  
  
## <a name="see-also"></a>См. также  
 [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [Вложенные структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Оператор If](../../../../visual-basic/language-reference/operators/if-operator.md)
