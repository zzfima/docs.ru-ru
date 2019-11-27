---
title: Структуры решений
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: d0d4039ff2edc61ee8b4b732c6adcb6e420d73ea
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353965"
---
# <a name="decision-structures-visual-basic"></a>Структуры решений (Visual Basic)
Visual Basic позволяет тестировать условия и выполнять различные операции в зависимости от результатов этого теста. Можно проверить наличие условия, которое имеет значение true или false, для различных значений выражения или для различных исключений, создаваемых при выполнении последовательности инструкций.  
  
 На следующем рисунке показана структура принятия решений, которая проверяет истинность условия и принимает различные действия в зависимости от того, имеет ли оно значение true или false.  
  
 ![Блок-схема If...Then...Else.](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a>If...Then...Else, конструкция  
 `If...Then...Else`ные конструкции позволяют проверить одно или несколько условий и выполнить одну или несколько инструкций в зависимости от каждого условия. Проверить условия и выполнить действия можно следующими способами.  
  
- Выполнить одну или несколько инструкций, если условие имеет значение `True`  
  
- Выполнить одну или несколько инструкций, если условие имеет значение `False`  
  
- Выполните некоторые инструкции, если условие `True` и другие, если это `False`  
  
- Протестируйте дополнительное условие, если предыдущие условия `False`  
  
 Структура элемента управления, которая предоставляет все эти возможности, — это [If... Затем... Else, инструкция](../../../../visual-basic/language-reference/statements/if-then-else-statement.md). Можно использовать однострочную версию, если имеется только один тест и один оператор для выполнения. При наличии более сложного набора условий и действий можно использовать версию из нескольких строк.  
  
## <a name="selectcase-construction"></a>Select...Case Конструкция  
 Конструкция `Select...Case` позволяет оценивать выражение один раз и выполнять разные наборы инструкций на основе различных возможных значений. Дополнительные сведения см. в разделе [SELECT... Case, инструкция](../../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="trycatchfinally-construction"></a>Try...Catch...Finally, создание  
 `Try...Catch...Finally`ные конструкции позволяют запускать набор инструкций в среде, сохраняющей управление, если какая-либо из инструкций вызывает исключение. Для разных исключений можно выполнять различные действия. При необходимости можно указать блок кода, который будет выполняться перед выходом из всей `Try...Catch...Finally` построения, независимо от того, что происходит. Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
> Для многих структур управления при щелчке ключевого слова все ключевые слова в структуре выделяются. Например, если щелкнуть `If` в конструкции `If...Then...Else`, будут выделены все экземпляры `If`, `Then`, `ElseIf`, `Else`и `End If` в конструкции. Чтобы перейти к следующему или предыдущему выделенному ключевому слову, нажмите клавиши CTRL + SHIFT + стрелка вниз или CTRL + SHIFT + стрелка вверх.  
  
## <a name="see-also"></a>См. также

- [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [Вложенные структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Оператор If](../../../../visual-basic/language-reference/operators/if-operator.md)
