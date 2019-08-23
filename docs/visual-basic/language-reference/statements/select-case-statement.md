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
ms.openlocfilehash: 627318677270ba4ffa8ee430febea7ddf83bd245
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957645"
---
# <a name="selectcase-statement-visual-basic"></a>Оператор Select...Case (Visual Basic)
Выполняет одну из нескольких групп инструкций в зависимости от значения выражения.  
  
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
|`testexpression`|Обязательный. Выражение. Необходимо вычислить до одного из простейших типов`Boolean`данных `Byte`( `Char`, `Date`, `Double` `Long` `Integer` `Decimal` `Object` ,,`SByte`,,,,,,, `Short` `Single`, ,`String` ,и`UShort`). `UInteger` `ULong`|  
|`expressionlist`|Требуется в `Case` операторе. Список предложений выражений, представляющих значения соответствия для `testexpression`. Несколько предложений выражений разделяются запятыми. Каждое предложение может принимать одну из следующих форм:<br /><br /> -   *expression1* `To` *выражение2*<br />-[ `Is` ] *компарисоноператор* *выражение*<br />-   *выражение*<br /><br /> Используйте ключевое слово, чтобы указать границы диапазона значений соответствия для `testexpression`. `To` Значение `expression1` должно быть меньше или равно `expression2`значению.<br /><br /> `<` `<=` `<>` `>` `>=`Используйте ключевое слово с оператором сравнения`=`(,,,, или), чтобы указать ограничение на значения сопоставления для `testexpression`. `Is` Если ключевое слово не указано, оно автоматически вставляется перед *компарисоноператор.* `Is`<br /><br /> Форма, указывающая `expression` только, рассматривается как особый случай `Is` формы, где *компарисоноператор* — знак равенства (`=`). Эта форма вычисляется как `testexpression`.  =  `expression`<br /><br /> Выражения в `expressionlist` могут быть любого типа данных при условии, что они неявно преобразуются в `testexpression` тип, а подходящее `comparisonoperator` значение допустимо для двух типов, с которыми он используется.|  
|`statements`|Необязательный параметр. Одна или несколько следующих `Case` инструкций, которые выполняются, если `testexpression` совпадают с `expressionlist`любым предложением в.|  
|`elsestatements`|Необязательный параметр. `Case Else` Одна или несколько следующих инструкций, которые выполняются, если `testexpression` не `expressionlist` соответствуют ни одному из предложений в ни одной `Case` из инструкций.|  
|`End Select`|Завершает определение `Select`... `Case` создание.|  
  
## <a name="remarks"></a>Примечания  
 Если `testexpression` соответствует любому `Case` `End Select` `Case` `Case Else` `Case` предложению, инструкции, следующие за этим оператором, выполняются до следующей инструкции, или. `expressionlist` Затем управление передается следующему `End Select`оператору. Если `testexpression` `Case` соответствует предложению в более чем одном предложении, выполняются только инструкции, следующие за первым совпадением. `expressionlist`  
  
 `testexpression` `elsestatements` `Case` `expressionlist` Оператор используется для представления для запуска, если между предложением и в других инструкциях не найдено совпадений. `Case Else` Хотя это и не является обязательным, рекомендуется иметь `Case Else` `Select Case` в конструкции оператор, обрабатывающий непредвиденные `testexpression` значения. Если предложение `Case` не `expressionlist` `End Select`совпадает и отсутствует оператор, управление передается оператору ниже. `Case Else` `testexpression`  
  
 В каждом `Case` предложении можно использовать несколько выражений или диапазонов. Например, следующая строка допустима.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> Ключевое слово `Case` , используемое `Case Else` в операторах и, не совпадает с [оператором is](../../../visual-basic/language-reference/operators/is-operator.md), который используется для сравнения ссылок на объекты. `Is`  
  
 Можно указать диапазоны и несколько выражений для символьных строк. В следующем примере `Case` соответствует любой строке, которая равна «яблоки», имеет значение между «гайкями» и «полный курс» в алфавитном порядке или содержит точно то же значение, что и текущее `testItem`значение.  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 Параметр `Option Compare` может влиять на сравнения строк. В строках «яблоки» и «яблоки» сравниваются как одинаковые, `Option Compare Binary`но в противном случае — нет. `Option Compare Text`  
  
> [!NOTE]
> Оператор с несколькими предложениями может демонстрировать поведение, называемое *сокращенным вычислением.* `Case` Visual Basic вычисляет предложения слева направо, и если одно из них создает совпадение с `testexpression`, оставшиеся предложения не оцениваются. Сокращенное вычисление может повысить производительность, но может привести к непредвиденным результатам, если ожидается вычисление каждого `expressionlist` выражения в. Дополнительные сведения об сокращенном вычислении см. в разделе [логические выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Если код в `Case` блоке инструкций `Case Else` или не требует выполнения каких-либо инструкций в блоке, он может выйти из блока с помощью `Exit Select` инструкции. Это немедленно передает управление оператору, приведенному ниже `End Select`.  
  
 `Select Case`конструкции могут быть вложенными. `Select Case` Каждая вложенная конструкция должна иметь соответствующий `End Select` оператор и должна быть полностью заключена в один `Case` блок `Case Else` инструкций или внешней `Select Case` конструкции, внутри которой он вложен.  
  
## <a name="example"></a>Пример  
 В следующем примере `Select Case` конструкция используется для записи строки, соответствующей значению переменной `number`. Вторая `Case` инструкция содержит значение, совпадающее с текущим `number`значением, поэтому инструкция, записывающая "между 6 и 8 включительно", выполняется.  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [Оператор End](../../../visual-basic/language-reference/statements/end-statement.md)
- [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
