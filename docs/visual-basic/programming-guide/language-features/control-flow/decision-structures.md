---
title: "Структуры (Visual Basic) критериев | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement, decision structures
- If statement, If...Then...Else
- control flow, decision structures
- decision structures
- conditional statements, decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c69b487322dc75ae8d54f42c1c62f8f5cc35757d
ms.lasthandoff: 03/13/2017

---
# <a name="decision-structures-visual-basic"></a>Структуры решений (Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]позволяет проверять условия и выполнять различные операции в зависимости от результатов такой проверки. Можно проверить условие true или false для различных значений выражений или исключений, выдаваемых при выполнении последовательности инструкций.  
  
 На следующем рисунке структуру решений, которая проверяет условие и выполняет различные действия в зависимости от того, является ли true или false.  
  
 ![Таблица потока конструкции If... Затем... Конструкции else](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")  
Выполняет различные действия, если условие имеет значение true, а если он имеет значение false  
  
## <a name="ifthenelse-construction"></a>If... Затем... Конструкции else  
 `If...Then...Else`позволяют проверить одно или несколько условий и выполнить один или несколько операторов для каждого условия. Можно проверить условия и выполнить действия следующими способами:  
  
-   Выполните один или несколько операторов, если условие равно`True`  
  
-   Выполните один или несколько операторов, если условие равно`False`  
  
-   Выполнить некоторые операторы, если условие равно `True` и другие — если`False`  
  
-   Проверить дополнительное условие, если предыдущее условие`False`  
  
 Управляющая структура, обеспечивающая все эти возможности — [Если... Затем... Оператор Else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md). Можно использовать простую версию при наличии только одного условия и одного оператора для выполнения. Если имеется более сложный набор условий и действий, можно использовать составную версию.  
  
## <a name="selectcase-construction"></a>Выберите... Конструкции case  
 `Select...Case` Позволяет вычислить выражение один раз и выполнить различные наборы операторов на основе различных значений. Дополнительные сведения см. в разделе [выберите... Case-оператор](../../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="trycatchfinally-construction"></a>Конструкция TRY... CATCH... Наконец построения  
 `Try...Catch...Finally`позволяют выполнять набор инструкций в среде, которая сохраняет управление, если какой-либо из операторов вызовет исключение. Можно выполнять различные действия для различных исключений. Можно указать блок кода, который выполняется перед выходом из всей `Try...Catch...Finally` конструкции, независимо от того, что происходит. Дополнительные сведения см. в разделе [Try... CATCH... Оператор Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
>  Для многих структур управления что при щелчке ключевого слова, все ключевые слова в структуре выделяются. Например, при нажатии кнопки `If` в `If...Then...Else` конструкции, все экземпляры `If`, `Then`, `ElseIf`, `Else`, и `End If` при построении выделяются. Чтобы переместить выделенные следующего или предыдущего ключевое слово, нажмите клавиши CTRL + SHIFT + СТРЕЛКА ВНИЗ или CTRL + SHIFT + Стрелка вверх.  
  
## <a name="see-also"></a>См. также  
 [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)   
 [Вложенные структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Оператор If](../../../../visual-basic/language-reference/operators/if-operator.md)
