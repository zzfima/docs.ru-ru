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
ms.openlocfilehash: 20b60fb425278dacb56ee5f888967554a1f76aeb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825382"
---
# <a name="decision-structures-visual-basic"></a>Структуры решений (Visual Basic)
Visual Basic позволяет проверять условия и выполнять различные операции в зависимости от результата этого теста. Можно проверить условие true или false, для различных значений выражения, или для различных исключений, сформированных при выполнении последовательности инструкций.  
  
 На следующем рисунке структуру выбора, который проверяет условие и выполняет различные действия в зависимости от того, является ли это значение true или false.  
  
 ![Блок-схема If... Затем... Else конструкции](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")  
Выполняет различные действия, если условие имеет значение true, а также если он имеет значение false  
  
## <a name="ifthenelse-construction"></a>If... Затем... Else построения  
 `If...Then...Else` позволяют проверить одно или несколько условий и запустить один или несколько операторов для каждого условия. Можно проверить условия и действий одним из следующих способов:  
  
-   Выполните один или несколько операторов, если условие равно `True`  
  
-   Выполните один или несколько операторов, если условие равно `False`  
  
-   Выполнить некоторые операторы, если условие равно `True` и другие — если `False`  
  
-   Проверить дополнительное условие, если предыдущее условие `False`  
  
 Управляющая структура, обеспечивающая все эти возможности — [Если... Затем... Оператор Else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md). Если у вас есть только один тест и один оператор для запуска, можно использовать простую версию. При наличии более сложного набора условий и действий, можно использовать несколько строк версии.  
  
## <a name="selectcase-construction"></a>Выберите... Конструкции case  
 `Select...Case` Позволяет вычислить выражение один раз и выполнить различные наборы операторов на основе различных значений. Дополнительные сведения см. в разделе [выберите... Оператор выбора](../../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="trycatchfinally-construction"></a>Try... CATCH... Наконец, создание  
 `Try...Catch...Finally` позволяют выполнять набор инструкций в среде, которая сохраняет контроль, если какой-либо инструкций вызовет исключение. Можно выполнять разные действия для различных исключений. При необходимости можно указать блок кода, который выполняется перед выходом из целого `Try...Catch...Finally` конструкции, независимо от того, что происходит. Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
>  Для многих управляющих структур при щелчке ключевого слова, все ключевые слова в структуре, выделяются. Например, при нажатии кнопки `If` в `If...Then...Else` конструкции, все экземпляры `If`, `Then`, `ElseIf`, `Else`, и `End If` выделяются при построении. Чтобы перейти к следующему или предыдущему выделенный ключевое слово, нажмите клавиши CTRL + SHIFT + СТРЕЛКА ВНИЗ или CTRL + SHIFT + Стрелка вверх.  
  
## <a name="see-also"></a>См. также

- [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [Вложенные структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Оператор If](../../../../visual-basic/language-reference/operators/if-operator.md)
