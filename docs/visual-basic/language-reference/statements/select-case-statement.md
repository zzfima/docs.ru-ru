---
title: "Оператор Select...Case (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Select"
  - "vb.Case"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ветвление, conditional"
  - "Case Else - оператор, Select...Case"
  - "Case - оператор"
  - "Case - оператор, Select...Case"
  - "условные операторы, Select Case"
  - "поток управления, ветвление"
  - "Else - ключевое слово [Visual Basic], в Select...Case - операторы"
  - "End - ключевое слово, Select...Case - операторы"
  - "выполнение, conditional"
  - "Is - оператор [Visual Basic], в Select...Case - операторы"
  - "Select Case - оператор, Select...Case"
  - "Select - оператор"
  - "Select - оператор, Select...Case"
  - "Select...Case - операторы"
  - "To - ключевое слово, в Select...Case - операторы"
ms.assetid: 68877b65-5419-4bf0-a465-20cd0e4c7d44
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Оператор Select...Case (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Выполняет один из блоков операторов в зависимости от значения выражения.  
  
## Синтаксис  
  
```  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`testexpression`|Обязательный.  Выражение.  Должен быть равен одному их простых типов данных \(`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong` и `UShort`\).|  
|`expressionlist`|Обязателен в операторе `Case`.  Список возможных значений для `testexpression`.  Несколько выражений разделяются запятыми.  Каждое условие может принимать следующие формы:<br /><br /> -   *expression1* `To` *expression2*<br />-   `Is` \] *comparisonoperator* *expression*<br />-   *expression*<br /><br /> Используйте зарезервированное слово `To`, чтобы указать диапазон значений для `testexpression`.  Значение `expression1` должно быть меньше или равно значению `expression2`.<br /><br /> Используйте зарезервированное слово `Is` с оператором сравнения \(`=`, `<>`, `<`, `<=`, `>` или `>=`\) для ограничения возможных значений `testexpression`.  Если зарезервированное слово `Is` отсутствует, оно автоматически вставляется перед *comparisonoperator*.<br /><br /> Вид, в котором предоставляется только `expression`, рассматривается как особый случай использования `Is`, где *comparisonoperator* — знак равенства \(`=`\).  Данная форма вычисляется как `testexpression` \= `expression`.<br /><br /> Выражения в `expressionlist` могут иметь любой тип данных, если они неявно преобразуемы в тип данных, к которому относится `testexpression` и соответствующий элемент `comparisonoperator` подходит для двух используемых с ним типов данных.|  
|`statements`|Необязательный.  Один или несколько операторов, следующих за `Case`, которые запускаются, если `testexpression` соответствует любому предложению в `expressionlist`.|  
|`elsestatements`|Необязательный.  Один или несколько операторов, следующих за `Case Else`, которые выполняются, если `testexpression` не соответствует ни одному из предложений в `expressionlist` всех операторов `Case`.|  
|`End Select`|Завершает определение конструкции `Select`...`Case`.|  
  
## Заметки  
 Если `testexpression` соответствует любому `Case` предложения `expressionlist`, операторы, следующие за инструкцией `Case` переводят к следующему оператору `Case`, `Case Else` или `End Select`.  Затем управление передается оператору, следующему за оператором `End Select`.  Если `testexpression` соответствует предложению `expressionlist` более чем в одном условии `Case`, выполнятся только операторы, следующие за первым сопоставлением.  
  
 Оператор `Case Else` используется для выполнения `elsestatements`, если не найдено ни одного соответствия между `testexpression` и `expressionlist` в любом из других операторов `Case`.  Рекомендуется \(хотя это не обязательно\) иметь оператор `Case Else` в конструкции `Select Case` для обработки непредвиденных значений `testexpression`.  Если отсутствует оператор `Case`, для которого предложение `expressionlist` сопоставляется `testexpression` и отсутствует `Case Else`, то управление будет передано следующему оператору `End Select`.  
  
 В каждом предложении `Case` можно использовать несколько выражений и диапазонов.  Например, допустима следующая строка:  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
>  Ключевое слово `Is`, используемое в операторах `Case` и `Case Else` отличается от [Оператор Is](../../../visual-basic/language-reference/operators/is-operator.md), который используется для сравнения ссылок объекта.  
  
 Можно указывать диапазоны и несколько выражений для строк.  В следующем примере `Case` пропускает любую строку, которая равна "apples", имеет значение между "nuts" и "soup" в алфавитном порядке или содержит точно такие же значения, как текущее значение `testItem`.  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 Параметр `Option Compare` может повлиять на сравнение.  В `Option Compare Text` строки "Apples" и "apples" при сравнении воспринимаются как одинаковые, а при `Option Compare Binary` — нет.  
  
> [!NOTE]
>  Оператор `Case` с несколькими предложениями может демонстрировать поведение, называемое *short\-circuiting*.  Visual Basic вычисляет предложения слева направо, и если одно из них совпадает с `testexpression`, то оставшиеся предложения не обрабатываются.  Укорачивание может повысить производительность, однако оно может привести к непредсказуемым результатам, если ожидалось, что оцениваться будет каждое выражение в `expressionlist`.  Дополнительные сведения об укорачивании содержатся в разделе [Логические выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Если код в пределах блока операторов `Case` или `Case Else` не требует выполнения любых дополнительных операторов в блоке, можно выйти из блока с помощью оператора `Exit Select`.  Это позволяет немедленно передать управление оператору, следующему за оператором `End Select`.  
  
 Конструкции `Select Case` могут быть вложенными.  Каждая вложенная конструкция `Select Case` должна иметь соответствующий оператор `End Select` и должна целиком содержаться внутри одного оператора `Case` или `Case Else` внешнего блока конструкции `Select Case` в которой она является вложенной.  
  
## Пример  
 В следующем примере используется оператор `Select Case` для записи строки, соответствующей значению переменной `number`.  Второй оператор `Case` содержит значение, соответствующее текущему значению `number`, поэтому выполняется оператор, выводящий строку "Between 6 and 8, inclusive".  
  
 [!code-vb[VbVbalrStatements#54](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/select-case-statement_1.vb)]  
  
## См. также  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>   
 [Оператор End](../../../visual-basic/language-reference/statements/end-statement.md)   
 [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)