---
title: "Специальные символы в коде (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
dev_langs:
- VB
helpviewer_keywords:
- special characters, in code
- parentheses, using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator
- concatenation operators, special characters in code
- concatenation operators, vs. addition operator
- '! operator'
- separators, using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator
- addition operator
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
caps.latest.revision: 21
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 6d4b6e74ef3dfab3a7174da07cff7100fa4b2a2f
ms.lasthandoff: 03/13/2017

---
# <a name="special-characters-in-code-visual-basic"></a>Специальные символы в коде (Visual Basic)
Иногда необходимо использовать специальные символы в коде, то есть символы, которые не являются буквой или цифрой. Знаки пунктуации и специальные символы в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] набор символов имеет различное применение, от организации текста программы, до определения задач, выполняемых компилятором или скомпилированной программой. Эти знаки не определяют операции, подлежащие выполнению.  
  
## <a name="parentheses"></a>Круглые скобки  
 Используйте круглые скобки при определении процедуры, такие как `Sub` или `Function`. Все списки аргументов процедуры необходимо заключить в круглые скобки. Вы также использовать круглые скобки для распределения переменных или аргументов на логические группы, особенно для того, чтобы переопределить порядок приоритета операторов в сложном выражении. Это показано в следующем примере.  
  
 [!code-vb[VbVbcnConventions&11;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]  
  
 После выполнения предыдущего кода значение `d` равняется 8,225, а значение `e` равно 3. Расчет `d` использует приоритет по умолчанию `/` над `+` и эквивалентен `d = b + (c / a)`. Круглые скобки в вычислении `e` наивысший приоритет.  
  
## <a name="separators"></a>Разделители  
 Разделители выполняют предполагает их название: они разделяют сегменты кода. В [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], разделителя используется двоеточие (`:`). Разделители используются в том случае, если требуется использовать несколько операторов в одной строке, а не в отдельных строках. Это экономит место и повышает удобочитаемость кода. В следующем примере показано три оператора, разделенных точкой с запятой.  
  
 [!code-vb[VbVbcnConventions&#12;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]  
  
 Дополнительные сведения см. в разделе [как: Break и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
 Двоеточие (`:`) символ также используется для установления метки оператора. Дополнительные сведения см. в разделе [как: операторы метку](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
## <a name="concatenation"></a>Сцепление  
 Используйте `&` оператор для *объединение*, или сцепления, строк вместе. Не следует путать его с `+` оператор, который складывает числовых значений. Если вы используете `+` оператор для сцепления при работе с числовыми значениями, можно получить неверные результаты. В следующем примере это показано.  
  
 [!code-vb[VbVbcnConventions&#13;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]  
  
 После выполнения предыдущего кода значение `resultA` имеет значение 21.01, а `resultB` — «10.0111».  
  
## <a name="member-access-operators"></a>Операторы доступа к членам  
 Для доступа к члену типа, используйте точку (`.`) или восклицательный знак (`!`) оператор между именем типа и имя элемента.  
  
### <a name="dot--operator"></a>Точка (.) Оператор  
 Используйте `.` оператором оператор доступа к члену класса, структуры, интерфейса или перечисления. Элемент может быть поле, свойство, событие или метод. Это показано в следующем примере.  
  
 [!code-vb[VbVbcnConventions&#14;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]  
  
### <a name="exclamation-point--operator"></a>Восклицательный знак (!) Оператор  
 Используйте `!` оператор только для класса или интерфейса, как оператор доступа к словарям. Класс или интерфейс должен иметь свойство по умолчанию, который принимает один `String` аргумент. Идентификатор, следующий сразу `!` оператор становится значение аргумента, переданного свойства по умолчанию как строку. В следующем примере это показано.  
  
 [!code-vb[VbVbcnConventions&#15;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]  
  
 Три выходных строк `MsgBox` все отображать значение `32856`. В первой строке используется традиционный доступ к свойству `index`, вторая использует тот факт, `index` — свойство по умолчанию класса `hasDefault`, а третья использует словарный доступ к классу.  
  
 Обратите внимание, что второй операнд `!` оператор должен быть допустимым идентификатором Visual Basic, не заключенный в двойные кавычки (`" "`). Другими словами нельзя использовать строковый литерал или строковую переменную. Следующее изменение в последней строке `MsgBox` вызов приводит к ошибке, поскольку `"X"` является закрытой строка литерала.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  Ссылки на коллекции по умолчанию должны быть явными. В частности, нельзя использовать `!` оператор переменной позднего связывания.  
  
 `!` Символ также используется в качестве `Single` знак типа.  
  
## <a name="see-also"></a>См. также  
 [Структура программы и соглашения о коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Знаки типов](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
