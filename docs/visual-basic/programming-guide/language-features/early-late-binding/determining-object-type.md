---
title: Определение типа объекта (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: 625ddb8fc153708a80e8cf475f48d595efbe4df2
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842633"
---
# <a name="determining-object-type-visual-basic"></a>Определение типа объекта (Visual Basic)
Универсальные объектные переменные (то есть переменные необходимо обозначить как `Object`) может содержать объекты любого класса. При использовании переменных типа `Object`, может потребоваться предпринять различные действия на основе класса объекта; например, некоторые объекты могут не поддерживать определенное свойство или метод. Visual Basic предоставляет два средства определения типа объекта, хранящегося в переменной объекта: `TypeName` функции и `TypeOf...Is` оператор.  
  
## <a name="typename-and-typeofis"></a>Имя типа и TypeOf... —  
 `TypeName` Функция возвращает строку и является лучшим выбором, если вам нужно хранить или отображать имя класса объекта, как показано в следующем фрагменте кода:  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 `TypeOf...Is` Оператор отлично подходит для тестирования тип объекта, так как это намного быстрее, чем в эквивалентное ему строковое сравнение с помощью `TypeName`. В следующем фрагменте кода используется `TypeOf...Is` в `If...Then...Else` инструкции:  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 Предупреждение здесь должно быть выполнено. `TypeOf...Is` Оператор возвращает `True` Если определенного типа, или объекта является производным от определенного типа. Почти все, что делается с помощью Visual Basic включает в себя объекты, которые содержат элементы считаются не обычно объекты, такие как строки и целые числа. Эти объекты являются производными от и наследуют методы из <xref:System.Object>. При передаче `Integer` и вычислении с `Object`, `TypeOf...Is` оператор возвращает `True`. В следующем примере сообщается, что параметр `InParam` одновременно `Object` и `Integer`:  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 В следующем примере используются оба `TypeOf...Is` и `TypeName` для определения типа объекта, переданного в него в `Ctrl` аргумент. `TestObject` Вызовы процедур `ShowType` с три различных типа элементов управления.  
  
#### <a name="to-run-the-example"></a>Запуск примера  
  
1.  Создайте новый проект приложения Windows и добавьте <xref:System.Windows.Forms.Button> управления <xref:System.Windows.Forms.CheckBox> элемента управления и <xref:System.Windows.Forms.RadioButton> на форму элемент управления.  
  
2.  С помощью кнопки на форме, вызовите `TestObject` процедуры.  
  
3.  Добавьте следующий код в форму:  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [Вызов свойства или метода с помощью строкового имени](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)
- [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Оператор If...Then...Else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Тип данных String](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [Тип данных Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
