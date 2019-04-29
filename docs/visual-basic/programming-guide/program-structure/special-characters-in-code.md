---
title: Специальные символы в коде (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 65fcd10521742e287c7934080b3352a06668df7a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967990"
---
# <a name="special-characters-in-code-visual-basic"></a>Специальные символы в коде (Visual Basic)
Иногда необходимо использовать специальные символы в коде, то есть символы, которые не являются буквой или цифрой. Знаки препинания и специальные символы в кодировке Visual Basic имеют различные применения, от организации текста программы до определения задач, выполняемых компилятором или скомпилированной программой. Эти знаки не определяют операции, подлежащие выполнению.  
  
## <a name="parentheses"></a>Круглые скобки  
 Используйте круглые скобки при определении процедуры, такие как `Sub` или `Function`. Все списки аргументов в процедуру необходимо заключить в круглые скобки. Можно также использовать круглые скобки для помещения переменные или аргументы в логические группы, особенно в том, чтобы переопределить порядок применения операторов в сложное выражение по умолчанию. Это показано в следующем примере.  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 После выполнения предыдущего примера кода, значение `d` 8,225 и значение `e` равно 3. Расчет `d` использует приоритет по умолчанию `/` над `+` и эквивалентно `d = b + (c / a)`. Круглые скобки в вычислении `e` наивысший приоритет.  
  
## <a name="separators"></a>Разделители  
 Разделители выполняют предполагает их название: они разделяют сегменты кода. В Visual Basic, разделителя используется двоеточие (`:`). Разделители используются в том случае, если вы хотите использовать несколько операторов в отдельных строках в одну строку. Это позволяет сэкономить место и улучшает читаемость кода. В следующем примере показано три инструкции, разделенные точкой с запятой.  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 Дополнительные сведения см. в разделе [Как Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
 Двоеточие (`:`) символ также используется для установления метки оператора. Дополнительные сведения см. в разделе [Как Операторы меток](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
## <a name="concatenation"></a>Сцепление  
 Используйте `&` оператор для *объединение*, или связывание строк друг с другом. Не следует путать его с `+` оператор, который складывает числовых значений. Если вы используете `+` оператор для сцепления при работе с числовыми значениями, можно получить неверные результаты. В следующем примере это показано.  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 После выполнения предыдущего примера кода, значение `resultA` 21.01 и значение `resultB` — «10.0111».  
  
## <a name="member-access-operators"></a>Операторы доступа к членам  
 Для доступа к члену типа, используйте точку (`.`) или восклицательный знак (`!`) оператор имя типа и именем члена.  
  
### <a name="dot--operator"></a>Точка (.) Оператор  
 Используйте `.` оператор на класс, структуру, интерфейс или перечисление, как оператор доступа к члену. Элемент может быть поле, свойство, событие или метод. Это показано в следующем примере.  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a>Восклицательный знак (!) Оператор  
 Используйте `!` оператор только для класса или интерфейса, как оператор доступа к словарям. Класс или интерфейс должен иметь свойство по умолчанию, принимающего один `String` аргумент. Идентификатор, следующий сразу `!` оператор становится значение аргумента, передаваемое свойство по умолчанию в виде строки. В следующем примере это показано.  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 Три выходных строк `MsgBox` все отобразить значение `32856`. В первой строке используется традиционный доступ к свойству `index`, вторая использует тот факт, `index` является свойством по умолчанию класса `hasDefault`, а третья использует словарный доступ к классу.  
  
 Обратите внимание, что второй операнд `!` оператор должен быть допустимым идентификатором Visual Basic, не заключаются в двойные кавычки (`" "`). Другими словами нельзя использовать строковый литерал или строковую переменную. Следующее изменение в последней строки `MsgBox` вызов вызовет ошибку, поскольку `"X"` — вложенный строковый литерал.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  Ссылки на коллекции по умолчанию должны быть явными. В частности, нельзя использовать `!` оператор на переменную с поздним связыванием.  
  
 `!` Символ используется в качестве `Single` символ типа.  
  
## <a name="see-also"></a>См. также

- [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Знаки типов](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
