---
title: Определение типа объекта
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: a77cc0603a0b61f58a4aa703c4b1e6ef4c26729c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345200"
---
# <a name="determining-object-type-visual-basic"></a>Определение типа объекта (Visual Basic)
Универсальные объектные переменные (т. е. переменные, объявляемые как `Object`) могут содержать объекты из любого класса. При использовании переменных типа `Object`может потребоваться выполнить различные действия в зависимости от класса объекта. Например, некоторые объекты могут не поддерживать определенное свойство или метод. Visual Basic предоставляет два способа определения типа объекта, хранящегося в объектной переменной: функция `TypeName` и оператор `TypeOf...Is`.  
  
## <a name="typename-and-typeofis"></a>TypeName и TypeOf... Рекомендуется  
 Функция `TypeName` возвращает строку и является лучшим выбором, если необходимо сохранить или отобразить имя класса объекта, как показано в следующем фрагменте кода:  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 Оператор `TypeOf...Is` является лучшим выбором для тестирования типа объекта, так как он гораздо быстрее, чем эквивалентное сравнение строк с помощью `TypeName`. В следующем фрагменте кода используется `TypeOf...Is` в инструкции `If...Then...Else`:  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 В этом случае следует соблюдать осторожность. Оператор `TypeOf...Is` возвращает `True`, если объект относится к конкретному типу или является производным от определенного типа. Почти все, что выполняется с Visual Basic, включает объекты, которые включают в себя некоторые элементы, которые обычно не считаются объектами, например строками и целыми числами. Эти объекты являются производными от <xref:System.Object>и наследуют от них методы. При передаче `Integer` и вычислении с `Object`оператор `TypeOf...Is` возвращает `True`. В следующем примере сообщается, что параметр `InParam` является как `Object`, так и `Integer`:  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 В следующем примере используются как `TypeOf...Is`, так и `TypeName` для определения типа объекта, переданного в него в аргументе `Ctrl`. `TestObject` процедура вызывает `ShowType` с тремя различными видами элементов управления.  
  
#### <a name="to-run-the-example"></a>Запуск примера  
  
1. Создайте новый проект приложения Windows и добавьте в форму элемент управления <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox> и элемент управления <xref:System.Windows.Forms.RadioButton>.  
  
2. С помощью кнопки в форме вызовите процедуру `TestObject`.  
  
3. Добавьте в форму следующий код:  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [Вызов свойства или метода с помощью строкового имени](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)
- [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Оператор If...Then...Else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Тип данных String](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [Тип данных Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
