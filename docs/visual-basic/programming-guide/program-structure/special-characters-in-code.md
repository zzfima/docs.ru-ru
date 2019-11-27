---
title: Специальные символы в коде
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
ms.openlocfilehash: f4ab35b56d48ae86bdb024ffea27735b39decdc2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347257"
---
# <a name="special-characters-in-code-visual-basic"></a>Специальные символы в коде (Visual Basic)
Иногда в коде необходимо использовать специальные символы, то есть символы, не являющиеся алфавитными или числовыми. Знаки пунктуации и специальные символы в Visual Basic кодировке имеют различные варианты использования, от организации текста программы до определения задач, выполняемых компилятором или скомпилированной программой. Эти знаки не определяют операции, подлежащие выполнению.  
  
## <a name="parentheses"></a>скобки  
 Используйте круглые скобки при определении процедуры, например `Sub` или `Function`. Все списки аргументов процедур необходимо заключать в круглые скобки. Также круглые скобки используются для помещения переменных или аргументов в логические группы, особенно для переопределения порядка приоритета операторов по умолчанию в сложном выражении. Это показано в следующем примере.  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 После выполнения предыдущего кода значение `d` равно 8,225, а значение `e` равно 3. Вычисление для `d` использует приоритет по умолчанию `/` над `+` и эквивалентен `d = b + (c / a)`. Круглые скобки в вычислении для `e` переопределяют приоритет по умолчанию.  
  
## <a name="separators"></a>Разделители  
 Разделители выполняют свои имена: они разделяют разделы кода. В Visual Basic символ разделителя является двоеточием (`:`). Используйте разделители, если требуется включить несколько операторов в одну строку, а не отдельные строки. Это экономит пространство и повышает удобочитаемость кода. В следующем примере показаны три инструкции, разделенные двоеточиями.  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 Дополнительные сведения см. [в разделе инструкции. разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
 Символ двоеточия (`:`) также используется для обозначения метки оператора. Дополнительные сведения см. [в разделе инструкции. Метки](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
## <a name="concatenation"></a>Сцепление  
 Используйте оператор `&` для *объединения*или связывания строк. Не путайте его с оператором `+`, который добавляет вместе числовые значения. При использовании оператора `+` для сцепления при работе с числовыми значениями можно получить неверные результаты. В следующем примере это показано.  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 После выполнения предыдущего кода значение `resultA` равно 21,01, а значение `resultB` равно "10,0111".  
  
## <a name="member-access-operators"></a>Операторы доступа к членам  
 Для доступа к члену типа используется оператор точки (`.`) или восклицательный знак (`!`) между именем типа и именем члена.  
  
### <a name="dot--operator"></a>Точка (.) Станции  
 Используйте оператор `.` для класса, структуры, интерфейса или перечисления в качестве оператора доступа к членам. Элемент может быть полем, свойством, событием или методом. Это показано в следующем примере.  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a>Восклицательный знак (!) Станции  
 Оператор `!` используется только для класса или интерфейса в качестве оператора доступа к словарю. Класс или интерфейс должен иметь свойство по умолчанию, принимающее один аргумент `String`. Идентификатор, непосредственно следующий за оператором `!`, становится значением аргумента, передаваемым в свойство по умолчанию в виде строки. В следующем примере это показано.  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 Три строки вывода `MsgBox` все отображают значение `32856`. В первой строке используется традиционный доступ к свойству `index`, во втором используется тот факт, что `index` является свойством по умолчанию класса `hasDefault`, а третья использует словарный доступ к классу.  
  
 Обратите внимание, что второй операнд оператора `!` должен быть допустимым Visual Basicным идентификатором, не заключенным в двойные кавычки (`" "`). Иными словами, нельзя использовать строковый литерал или строковую переменную. Следующее изменение в последней строке вызова `MsgBox` приводит к ошибке, поскольку `"X"` является строкой, заключенной в строку.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
> Ссылки на коллекции по умолчанию должны быть явными. В частности, нельзя использовать оператор `!` в переменной с поздним связыванием.  
  
 Символ `!` также используется в качестве символа типа `Single`.  
  
## <a name="see-also"></a>См. также

- [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Знаки типов](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
