---
title: "Структуры решений (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "условные операторы, структуры критериев"
  - "поток управления, структуры критериев"
  - "структуры критериев"
  - "If - оператор, структуры критериев"
  - "If - оператор, If...Then...Else"
  - "операторы [Visual Basic], поток управления"
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
caps.latest.revision: 29
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 29
---
# Структуры решений (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] позволяет проверять условия и выполнять различные операции в зависимости от результатов такой проверки.  Можно проверять истинность или ложность условия для различных значений выражений или исключений, выдаваемых при выполнении последовательности операторов.  
  
 Следующий пример показывает структуру решений, которая проверяет условие и выполняет различные действия в зависимости от того, выполняется оно или нет.  
  
 ![Таблица потока конструкции “If...Then...Else”](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")  
Выполняет различные действия, когда условие имеет значение true или false  
  
## Конструкция If...Then...Else  
 Конструкции `If...Then...Else` позволяют проверить одно или несколько условий и выполнить один или несколько операторов для каждого условия.  Можно проверить условия и выполнить действия следующими способами:  
  
-   Если условие `True`, выполнить один или несколько операторов  
  
-   Если условие `False`, выполнить один или несколько операторов  
  
-   Если условие `True`, выполнить некоторые операторы, а другие — если условие `False`  
  
-   Проверить дополнительное условие, если предыдущее условие `False`  
  
 Управляющая структура, обеспечивающая все эти возможности — [Оператор If...Then...Else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).  Можно использовать простую версию при наличии только одного условия и одного оператора.  Если имеется более сложный набор условий и действий, можно использовать составную версию.  
  
## Конструкция Select...Case  
 Конструкция `Select...Case` позволяет вычислить выражение один раз и выполнить различные наборы операторов на основе различных значений выражения.  Дополнительные сведения см. в разделе [Оператор Select...Case](../../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## Конструкция Try...Catch...Finally  
 Конструкции `Try...Catch...Finally` позволяют выполнять набор операторов в среде, которая сохраняет управление, если какой\-либо из операторов вызовет исключение.  Можно выполнять различные действия для различных исключений.  Можно указать блок кода, который будет выполняться перед выходом из всей конструкции `Try...Catch...Finally` независимо от того, что произошло.  Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
>  Для многих структур управления действует правило, что при нажатии мышью на ключевое слово все ключевые слова в структуре выделяются.  Например, при щелчке `If` в конструкции `If...Then...Else` выделяются все экземпляры `If`, `Then`, `ElseIf`, `Else` и `End If`.  Для перемещения к следующему или предыдущему выделенному ключевому слову нажмите сочетание клавиш CTRL\+SHIFT\+СТРЕЛКА ВНИЗ или CTRL\+SHIFT\+СТРЕЛКА ВВЕРХ.  
  
## См. также  
 [Управление ходом выполнения](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)   
 [Вложенные структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Оператор If](../../../../visual-basic/language-reference/operators/if-operator.md)