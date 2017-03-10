---
title: "Оператор If...Then...Else (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ElseIf"
  - "vb.Then"
  - "vb.If"
  - "vb.EndIf"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ветвление, условный"
  - "поток управления, ветвление"
  - "Else - оператор [Visual Basic]"
  - "ElseIf - оператор, If...Then...Else"
  - "выполнение, условный"
  - "If - оператор [Visual Basic]"
  - "If - оператор"
  - "If - оператор, If...Then...Else"
  - "If...Then...Else - операторы"
  - "IIf - функция, и If...Then...Else - операторы"
  - "Is - оператор [Visual Basic], в If...Then...Else - операторы"
  - "Then - оператор, If...Then...Else"
  - "TypeOf...Is - выражение, и If...Then...Else - операторы"
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
caps.latest.revision: 29
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 29
---
# Оператор If...Then...Else (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

В зависимости от значения выражения будет выполнена та или иная группа операторов.  
  
## Синтаксис  
  
```  
' Multiple-line syntax:  
If condition [ Then ]  
    [ statements ]  
[ ElseIf elseifcondition [ Then ]  
    [ elseifstatements ] ]  
[ Else  
    [ elsestatements ] ]  
End If  
  
' Single-line syntax:  
If condition Then [ statements ] [ Else [ elsestatements ] ]  
```  
  
## Части  
 `condition`  
 Обязательное.  Выражение.  Должен принимать значение `True` или `False` или должен быть типом данных, который можно преобразовть в `Boolean`.  
  
 Если выражение переменной, [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean`, результатом которого является значение [Nothing](../../../visual-basic/language-reference/nothing.md) условие обрабатывается, если выражение не является `True` и блок `Else` выполнения.  
  
 `Then`  
 В однострочном синтаксисе является обязательным параметром, а в многострочной — необязательным.  
  
 `statements`  
 Необязательный параметр.  Один или несколько операторов следующих за `If`...`Then`, которые выполняются, если результатом вычисления `condition` является `True`.  
  
 `elseifcondition`  
 Требуется, если имеется `ElseIf`.  Выражение.  Должен принимать значение `True` или `False` или должен быть типом данных, который можно преобразовть в `Boolean`.  
  
 `elseifstatements`  
 Необязательный параметр.  Один или несколько операторов следующих за `ElseIf`...`Then`, которые выполняются, если результатом вычисления `elseifcondition` является `True`.  
  
 `elsestatements`  
 Необязательный параметр.  Один или несколько операторов, которые выполняются, если нет предшествующего выражения `condition` или `elseifcondition`, которое имеет значение `True`.  
  
 `End If`  
 Завершает блок `If`...`Then`...`Else`.  
  
## Заметки  
  
## Многострочный синтаксис  
 Когда встречается оператор `If`...`Then`...`Else`, проверяется `condition`.  Если `condition` имеет значение `True`, операторы, следующие за `Then`, выполняются.  Если `condition` имеет значение `False`, то все операторы `ElseIf` \(если они есть\) выполняются по порядку.  Если найдено `elseifcondition`, которое имеет значение `True`, выполняются операторы, следующие непосредственно за соответствующим оператором `ElseIf`.  Если отсутствуют `elseifcondition`, которые имеют значение `True` или отсутствуют операторы `ElseIf`, то вызываются операторы, следующие за `Else`.  После выполнения операторов следующих за `Then`, `ElseIf` и `Else`, выполнение продолжается с оператора, следующего за `End If`.  
  
 Предложения `ElseIf` и `Else` являются необязательными.  Можно поместить любое количество выражений `ElseIf` внутри оператора `If`...`Then`...`Else`, но `ElseIf` не может находиться после выражения `Else`.  Операторы `If`...`Then`...`Else` могут быть вложены друг друга.  
  
 В многострочном синтаксисе оператор `If` должен быть единственным оператором в первой строке.  Операторам `ElseIf`, `Else` и `End If` может предшествовать только метка строки.  Блок `If`...`Then`...`Else` должен заканчиваться оператором `End If`.  
  
> [!TIP]
>  Оператор [Оператор Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md) может оказаться более полезным при работе с одним выражением, которое может иметь несколько возможных значений.  
  
## Однострочный синтаксис  
 Можно использовать однострочный синтаксис для коротких, простых проверок.  Однако многострочный синтаксис предоставляет большую структурированность, гибкость и обычно ее легче читать, обслуживать и отлаживать, чем однострочную.  
  
 Данные, следующие за ключевым словом `Then`, проверяются, чтобы определить, является ли оператор однострочным `If`.  Если после `Then` есть какое\-то выражение в той же строке, кроме примечаний, то данный оператор является однострочным оператором `If`.  Если отсутствует `Then`, это должно быть началом многострочного `If`...`Then`...`Else`.  
  
 При использовании однострочного синтаксиса возможно выполнение нескольких операторов в результате решения `If`...`Then`.  Все операторы должны быть в одной строке и разделяться двоеточием.  
  
## Пример  
 В следующем примере показано использование многострочного синтаксиса оператора `If`...`Then`...`Else`.  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/if-then-else-statement_1.vb)]  
  
## Пример  
 В следующем примере содержатся вложенные операторы `If`...`Then`...`Else`.  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/if-then-else-statement_2.vb)]  
  
## Пример  
 В следующем примере показано использование однострочного синтаксиса.  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/if-then-else-statement_3.vb)]  
  
## См. также  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>   
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>   
 [Директивы \#If...Then...\#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [Оператор Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md)   
 [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Структуры решений](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)   
 [Оператор If](../../../visual-basic/language-reference/operators/if-operator.md)