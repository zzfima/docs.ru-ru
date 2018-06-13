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
ms.openlocfilehash: 9d24b455d92cbd00b268df26283aab082b7703a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604579"
---
# <a name="selectcase-statement-visual-basic"></a>Оператор Select...Case (Visual Basic)
Запускает один из нескольких групп операторов в зависимости от значения выражения.  
  
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
|`testexpression`|Обязательно. Выражение. Необходимо иметь один из простейших типов данных (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, и `UShort`).|  
|`expressionlist`|Требуется в `Case` инструкции. Список предложений выражение, представляющее совпадают со значениями для `testexpression`. Несколько предложений выражения разделяются запятыми. Каждое условие может принимать одно из следующих форм:<br /><br /> -   *expression1* `To` *expression2*<br />-[ `Is` ] *comparisonoperator* *выражение*<br />-   *Выражение*<br /><br /> Используйте `To` ключевое слово, чтобы задать границы диапазона совпадения значений для `testexpression`. Значение `expression1` должно быть меньше или равно значению `expression2`.<br /><br /> Используйте `Is` ключевое слово с помощью оператора сравнения (`=`, `<>`, `<`, `<=`, `>`, или `>=`) для определения ограничения возможных значений для `testexpression`. Если `Is` ключевое слово не предоставляется, то он автоматически вставляется перед *comparisonoperator*.<br /><br /> Формы, указав только `expression` рассматривается как особый случай `Is` форме where *comparisonoperator* является знак равенства (`=`). Эта форма вычисляется как `testexpression`  =  `expression`.<br /><br /> Выражения в `expressionlist` может быть любого типа данных, если они неявно преобразуются в тип `testexpression` и соответствующий `comparisonoperator` является допустимым для двух типов, он используется с.|  
|`statements`|Необязательный. Один или несколько следующих инструкций `Case` , если выполнения `testexpression` соответствует любое предложение в `expressionlist`.|  
|`elsestatements`|Необязательный. Один или несколько следующих инструкций `Case Else` , если выполнения `testexpression` не соответствует любое предложение в `expressionlist` любого `Case` инструкции.|  
|`End Select`|Завершает определение `Select`... `Case` построения.|  
  
## <a name="remarks"></a>Примечания  
 Если `testexpression` соответствует любому `Case` `expressionlist` предложение, инструкции, следующие за, `Case` запущена инструкция до следующего `Case`, `Case Else`, или `End Select` инструкции. Затем управление передается оператору, следующему `End Select`. Если `testexpression` соответствует `expressionlist` предложение в нескольких `Case` предложение, выполнить инструкции, следующие за первое совпадение.  
  
 `Case Else` Оператор используется для представления `elsestatements` для запуска, если совпадение не найдено между `testexpression` и `expressionlist` предложения в любой другой `Case` инструкции. Несмотря на то, что не обязательно, рекомендуется иметь `Case Else` инструкции в вашей `Select Case` построения для обработки непредвиденных `testexpression` значения. Если не `Case` `expressionlist` предложение соответствует `testexpression` и не `Case Else` инструкции, управление передается оператору, следующему `End Select`.  
  
 Можно использовать несколько выражений и диапазонов в каждом `Case` предложения. Например следующая строка является допустимым.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
>  `Is` Используется ключевое слово `Case` и `Case Else` инструкции не является таким же, как [оператор Is](../../../visual-basic/language-reference/operators/is-operator.md), который используется для сравнения объекта ссылки.  
  
 Можно указать диапазоны и несколько выражений для строк. В следующем примере `Case` соответствует любой строке, которая равна «apples», имеет значение между «nuts» и «soup» в алфавитном порядке или содержит точно совпадает со значением текущего значения `testItem`.  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 Параметр `Option Compare` может влиять на сравнения строк. В разделе `Option Compare Text`, строки «Яблоки» и «яблоки» считаются равными, но в разделе `Option Compare Binary`, это не так.  
  
> [!NOTE]
>  Объект `Case` инструкции с несколькими предложениями может демонстрировать поведение, известный как *сокращенного вычисления*. Visual Basic вычисляет предложения слева направо и если он найдено соответствие с `testexpression`, оставшиеся предложения не обрабатываются. Сокращенные вычисления могут повысить производительность, но он может привести к непредвиденным результатам, если ожидалось, что каждое выражение в `expressionlist` для оценки. Дополнительные сведения о сокращенное вычисление в разделе [логические выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Если код внутри `Case` или `Case Else` блок инструкций необходимо выполнения любых дополнительных инструкций в блоке, можно выйти из блока с помощью `Exit Select` инструкции. Управление передается оператору, следующему `End Select`.  
  
 `Select Case` конструкции могут быть вложенными. Каждая вложенная `Select Case` конструкция должна иметь соответствующий `End Select` инструкции и должны полностью содержаться в одном `Case` или `Case Else` блок операторов внешнего `Select Case` построения, в течение которого он является вложенным.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Select Case` конструкции для записи строки, соответствующей значению переменной `number`. Второй `Case` инструкция содержит значение, соответствующее значение текущей `number`, поэтому инструкция, которая записывает «между 6 и 8, inclusive» работает.  
  
 [!code-vb[VbVbalrStatements#54](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/select-case-statement_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 [Оператор End](../../../visual-basic/language-reference/statements/end-statement.md)  
 [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
