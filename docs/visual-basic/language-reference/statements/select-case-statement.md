---
title: Оператор Select…Case
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
ms.openlocfilehash: 4dddfe5fbf7092c911291ffc6841e76f8c2748e9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352830"
---
# <a name="selectcase-statement-visual-basic"></a>Оператор Select...Case (Visual Basic)
Выполняет одну из нескольких групп инструкций в зависимости от значения выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
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
|`testexpression`|Обязательно. Выражение. Необходимо вычислить один из простейших типов данных (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`и `Single`).`String``UInteger``ULong``UShort`|  
|`expressionlist`|Требуется в операторе `Case`. Список предложений выражений, представляющих значения соответствия для `testexpression`. Несколько предложений выражений разделяются запятыми. Каждое предложение может принимать одну из следующих форм:<br /><br /> -   *выражение1* `To` *выражение2*<br />-[`Is`] *выражение* компарисоноператор<br />*выражение* -   <br /><br /> Используйте ключевое слово `To`, чтобы указать границы диапазона значений соответствия для `testexpression`. Значение `expression1` должно быть меньше или равно значению `expression2`.<br /><br /> Используйте ключевое слово `Is` с оператором сравнения (`=`, `<>`, `<`, `<=`, `>`или `>=`), чтобы указать ограничение на значения сопоставления для `testexpression`. Если ключевое слово `Is` не указано, оно автоматически вставляется перед *компарисоноператор*.<br /><br /> Форма, указывающая только `expression`, рассматривается как особый случай формы `Is`, где *компарисоноператор* — знак равенства (`=`). Эта форма вычисляется как `testexpression` = `expression`.<br /><br /> Выражения в `expressionlist` могут быть любого типа данных, если они неявно преобразуются в тип `testexpression` и соответствующие `comparisonoperator` допустимы для двух типов, с которыми он используется.|  
|`statements`|Необязательно. Один или несколько инструкций, следующих за `Case`, которые выполняются, если `testexpression` соответствует любому предложению в `expressionlist`.|  
|`elsestatements`|Необязательно. Одна или несколько инструкций, следующих за `Case Else`, которые выполняются, если `testexpression` не соответствует ни одному предложению в `expressionlist` каких либо инструкций `Case`.|  
|`End Select`|Завершает определение конструкции `Select`...`Case`.|  
  
## <a name="remarks"></a>Заметки  
 Если `testexpression` соответствует любому предложению `Case` `expressionlist`, то инструкции, следующие за тем, что `Case` оператор, запускаются до следующей `Case`, `Case Else`или `End Select` инструкции. Затем управление передается оператору, следующему `End Select`. Если `testexpression` соответствует предложению `expressionlist` в более чем одном предложении `Case`, выполняются только инструкции, следующие за первым совпадением.  
  
 Оператор `Case Else` используется для представления `elsestatements` для запуска, если между `testexpression` и предложением `expressionlist` в других инструкциях `Case` не найдено совпадений. Хотя это и не является обязательным, рекомендуется иметь оператор `Case Else` в конструкции `Select Case` для управления непредвиденными значениями `testexpression`. Если предложение `Case` `expressionlist` не соответствует `testexpression` и отсутствует оператор `Case Else`, управление передается оператору, следующему за `End Select`.  
  
 В каждом предложении `Case` можно использовать несколько выражений или диапазонов. Например, следующая строка допустима.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> Ключевое слово `Is`, используемое в инструкциях `Case` и `Case Else`, не совпадает с [оператором is](../../../visual-basic/language-reference/operators/is-operator.md), который используется для сравнения ссылок на объекты.  
  
 Можно указать диапазоны и несколько выражений для символьных строк. В следующем примере `Case` соответствует любой строке, точно равной «яблоки», имеет значение между «гайкями» и «полный курс» в алфавитном порядке или содержит то же значение, что и текущее значение `testItem`.  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 Параметр `Option Compare` может повлиять на сравнение строк. В разделе `Option Compare Text`строки "яблоки" и "яблоки" считаются равными, но в `Option Compare Binary`они не имеют.  
  
> [!NOTE]
> Оператор `Case` с несколькими предложениями может демонстрировать поведение, называемое *сокращенным вычислением*. Visual Basic вычисляет предложения слева направо, и если одно из них выдает совпадение с `testexpression`, оставшиеся предложения не оцениваются. Сокращенное вычисление может повысить производительность, но может привести к непредвиденным результатам, если ожидается оценка каждого выражения в `expressionlist`. Дополнительные сведения об сокращенном вычислении см. в разделе [логические выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Если код в блоке инструкций `Case` или `Case Else` не требует выполнения каких-либо инструкций в блоке, он может выйти из блока с помощью инструкции `Exit Select`. Это немедленно передает управление оператору, следующему за `End Select`.  
  
 `Select Case`ные конструкции могут быть вложенными. Каждая вложенная конструкция `Select Case` должна иметь совпадающую `End Select` инструкцию и должна полностью содержаться в пределах одного блока инструкций `Case` или `Case Else` внешнего `Select Case`, внутри которого она вложена.  
  
## <a name="example"></a>Пример  
 В следующем примере конструкция `Select Case` используется для записи строки, соответствующей значению переменной `number`. Вторая инструкция `Case` содержит значение, соответствующее текущему значению `number`, поэтому выполняется инструкция, записывающая "Between 6 и 8 включительно".  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [Оператор End](../../../visual-basic/language-reference/statements/end-statement.md)
- [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
