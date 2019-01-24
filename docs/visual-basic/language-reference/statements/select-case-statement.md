---
title: Оператор Select...Case (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Select
- vb.Case
helpviewer_keywords:
- Select statement [Visual Basic]
- Case statement [Visual Basic]
- Select...Case statements
- conditional statements [Visual Basic], Select Case
- control flow [Visual Basic], branching
- Else keyword [Visual Basic], in Select...Case statements
- execution [Visual Basic], conditional
- To keyword [Visual Basic], in Select...Case statements
- Select Case statement [Visual Basic], Select...Case
- Select statement [Visual Basic], Select...Case
- Is operator [Visual Basic], in Select...Case statements
- branching [Visual Basic], conditional
- Case Else statement [Visual Basic], Select...Case
- End keyword [Visual Basic], Select Case statements
- Case statement [Visual Basic], Select...Case
ms.assetid: 68877b65-5419-4bf0-a465-20cd0e4c7d44
ms.openlocfilehash: bc0b5037dc4e728a45dfdeb97c1b6aff449fcf2b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54551025"
---
# <a name="selectcase-statement-visual-basic"></a>Оператор Select...Case (Visual Basic)
Выполняет одну из нескольких групп операторов в зависимости от значения выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`testexpression`|Обязательный. выражение. Необходимо иметь один из простых типов данных (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, и `UShort`).|  
|`expressionlist`|Требуется в `Case` инструкции. Список предложений выражение, представляющее совпадают со значениями для `testexpression`. Несколько предложений выражения разделяются запятыми. Каждое предложение может принимать одно из следующих форм:<br /><br /> -   *expression1* `To` *expression2*<br />-[ `Is` ] *comparisonoperator* *выражение*<br />-   *Выражение*<br /><br /> Используйте `To` ключевое слово для указания диапазона совпадения значений в параметре `testexpression`. Значение `expression1` должно быть меньше или равно значению `expression2`.<br /><br /> Используйте `Is` ключевое слово оператора сравнения (`=`, `<>`, `<`, `<=`, `>`, или `>=`) для определения ограничения возможных значений для `testexpression`. Если `Is` ключевое слово не предоставляется, то он автоматически вставляется перед *comparisonoperator*.<br /><br /> Формы, указав только `expression` рассматривается как особый вариант `Is` форме where *comparisonoperator* — знак равенства (`=`). Эта форма вычисляется как `testexpression`  =  `expression`.<br /><br /> Выражения в `expressionlist` может быть любого типа данных, если они неявно преобразуются в тип `testexpression` соответствующий `comparisonoperator` является допустимым для двух типов, он используется с.|  
|`statements`|Необязательный параметр. Один или несколько следующих инструкций `Case` , если выполнения `testexpression` соответствует любой конструкции в `expressionlist`.|  
|`elsestatements`|Необязательный параметр. Один или несколько следующих инструкций `Case Else` , если выполнения `testexpression` не соответствует любое предложение в `expressionlist` любого из `Case` инструкций.|  
|`End Select`|Завершает определение `Select`... `Case` конструкции.|  
  
## <a name="remarks"></a>Примечания  
 Если `testexpression` соответствует какой-либо `Case` `expressionlist` предложение, инструкции, следующие за, `Case` запустите инструкцию к следующему `Case`, `Case Else`, или `End Select` инструкции. Затем управление передается оператору, следующему `End Select`. Если `testexpression` соответствует `expressionlist` предложение в более чем одном `Case` предложения, выполните инструкции, следующие за первое совпадение.  
  
 `Case Else` Представить используется инструкция `elsestatements` выполнять, если совпадений не найдено между `testexpression` и `expressionlist` предложение в любые другие `Case` инструкций. Несмотря на то, что не обязательно, рекомендуется иметь `Case Else` инструкции в вашей `Select Case` конструкции для обработки непредвиденных `testexpression` значения. Если не `Case` `expressionlist` соответствует конструкция `testexpression` и не `Case Else` инструкции, управление передается оператору, следующему `End Select`.  
  
 Можно использовать несколько выражений или диапазонов в каждом `Case` предложение. Например следующая строка является допустимым.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
>  `Is` Ключевое слово, используемое в `Case` и `Case Else` инструкции не является таким же, как [оператор Is](../../../visual-basic/language-reference/operators/is-operator.md), который используется для сравнения объекта ссылки.  
  
 Можно указать диапазоны и несколько выражений для строк. В следующем примере `Case` соответствует любой строке, которая точно равно «apples», имеет значение в диапазоне от «nuts» и «soup» в алфавитном порядке или содержит точно совпадает со значением текущее значение `testItem`.  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 Параметр `Option Compare` может повлиять на сравнение строк. В разделе `Option Compare Text`, строки «Apples» и «apples» сравнении считаются равными, но в разделе `Option Compare Binary`, это не так.  
  
> [!NOTE]
>  Объект `Case` инструкции с несколькими предложениями может демонстрировать поведение, известный как *сокращенного вычисления*. Visual Basic вычисляет предложения слева направо и если оно найдено соответствие с `testexpression`, оставшиеся предложения не обрабатываются. Сокращенные вычисления могут повысить производительность, но он может привести к непредвиденным результатам, если ожидалось, что каждое выражение в `expressionlist` необходимо оценить. Дополнительные сведения о сокращении выполнения, см. в разделе [логических выражений](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Если код внутри `Case` или `Case Else` блока инструкций не должен выполнять большее количество инструкций в блоке, можно выйти из блока с помощью `Exit Select` инструкции. Управление передается оператору, следующему `End Select`.  
  
 `Select Case` конструкции могут быть вложенными. Каждая вложенная `Select Case` конструкция должна иметь соответствующий `End Select` инструкции и должны полностью содержаться в одной `Case` или `Case Else` блок операторов внешнего `Select Case` построения, в который он вложен.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Select Case` конструкции для записи строки, соответствующий значению переменной `number`. Второй `Case` инструкция содержит значение, соответствующее текущее значение `number`, поэтому оператор, который записывает «между 6 и 8, включающие» выполняется.  
  
 [!code-vb[VbVbalrStatements#54](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/select-case-statement_1.vb)]  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [Оператор End](../../../visual-basic/language-reference/statements/end-statement.md)
- [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
