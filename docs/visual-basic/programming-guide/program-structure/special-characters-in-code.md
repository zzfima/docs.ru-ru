---
title: Специальные символы в коде (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
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
helpviewer_keywords:
- special characters [Visual Basic], in code
- parentheses [Visual Basic], using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator [Visual Basic]
- concatenation operators [Visual Basic], special characters in code
- concatenation operators [Visual Basic], vs. addition operator
- '! operator'
- separators [Visual Basic], using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator [Visual Basic]
- addition operator [Visual Basic]
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b724c48320f74045d7192be6d6e269c00511ffc9
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="special-characters-in-code-visual-basic"></a>Специальные символы в коде (Visual Basic)
Иногда необходимо использовать специальные символы в коде, то есть символы, которые не являются буквой или цифрой. Знаки пунктуации и специальные символы в кодировке Visual Basic имеют различные применения, от организации текста программы до определения задач, выполняемых компилятором или скомпилированной программой. Эти знаки не определяют операции, подлежащие выполнению.  
  
## <a name="parentheses"></a>Круглые скобки  
 Используйте круглые скобки при определении процедуры, такие как `Sub` или `Function`. Все списки аргументов в процедуру необходимо заключить в круглые скобки. Вы также использовать круглые скобки для помещения переменными или аргументами в логические группы, особенно, чтобы переопределить порядок приоритета операторов в сложное выражение по умолчанию. Это показано в следующем примере.  
  
 [!code-vb[VbVbcnConventions#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]  
  
 После выполнения предыдущего кода значение `d` равняется 8,225, а значение `e` равно 3. Расчет `d` используется приоритет по умолчанию `/` над `+` и эквивалентно `d = b + (c / a)`. Круглые скобки в вычислении `e` наивысший приоритет.  
  
## <a name="separators"></a>Разделители  
 В качестве разделителей сделать их названия: они разделяют сегменты кода. В Visual Basic, знак разделителя используется двоеточие (`:`). Разделители используются в том случае, если вы хотите использовать несколько операторов в отдельных строках в одну строку. Это экономит место и повышает удобочитаемость кода. В следующем примере показано три инструкции, разделенные точкой с запятой.  
  
 [!code-vb[VbVbcnConventions#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]  
  
 Дополнительные сведения см. в разделе [как: Break и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
 Двоеточие (`:`) символ также используется для установления метки оператора. Дополнительные сведения см. в разделе [как: метка инструкции](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
## <a name="concatenation"></a>Сцепление  
 Используйте `&` оператор для *объединение*, или связывания строки. Не следует путать с `+` оператор, который складывает числовых значений. Если вы используете `+` оператор для сцепления при работе с числовыми значениями, можно получить неверные результаты. В следующем примере это показано.  
  
 [!code-vb[VbVbcnConventions#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]  
  
 После выполнения предыдущего кода значение `resultA` 21.01 и значение `resultB` — «10.0111».  
  
## <a name="member-access-operators"></a>Операторы доступа к членам  
 Для доступа к члену типа, используется точка (`.`) или восклицательный знак (`!`) оператор между именем типа и имени элемента.  
  
### <a name="dot--operator"></a>Точка (.) Оператор  
 Используйте `.` оператора для класса, структуры, интерфейса или перечисления как оператор доступа к члену. Элемент может быть поле, свойство, событие или метод. Это показано в следующем примере.  
  
 [!code-vb[VbVbcnConventions#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]  
  
### <a name="exclamation-point--operator"></a>Восклицательный знак (!) Оператор  
 Используйте `!` оператор только для класса или интерфейса, как оператор доступа к словарям. Класс или интерфейс должен иметь свойство по умолчанию, который принимает один `String` аргумент. Идентификатор, следующий сразу `!` оператор становится значение аргумента, переданного свойства по умолчанию как строку. В следующем примере это показано.  
  
 [!code-vb[VbVbcnConventions#15](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]  
  
 Три выходных строк `MsgBox` все отобразить значение `32856`. В первой строке используется традиционный доступ к свойству `index`, вторая использует тот факт, `index` является свойством по умолчанию класса `hasDefault`, а третья использует словарный доступ к классу.  
  
 Обратите внимание, что второй операнд `!` оператор должен быть допустимым идентификатором Visual Basic не заключен в двойные кавычки (`" "`). Другими словами нельзя использовать строковый литерал или строковую переменную. Следующее изменение в последней строке `MsgBox` вызов приводит к ошибке, поскольку `"X"` является закрытой строка литерала.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  Ссылки на коллекции по умолчанию должны быть явными. В частности, нельзя использовать `!` оператор переменной позднего связывания.  
  
 `!` Символ также используется в качестве `Single` тип символа.  
  
## <a name="see-also"></a>См. также  
 [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Знаки типов](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
