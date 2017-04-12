---
title: "Определение типа объекта (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables, testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 2486d989801fc4866a50747aa963b509a627994d
ms.lasthandoff: 03/13/2017

---
# <a name="determining-object-type-visual-basic"></a>Определение типа объекта (Visual Basic)
Универсальные объектные переменные (то есть переменные можно объявить как `Object`) содержат объекты любого класса. При использовании переменных типа `Object`, может потребоваться предпринять различные действия в зависимости от класса объекта; например, некоторые объекты не поддерживают определенное свойство или метод. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]предоставляет два средства определения типа объекта, хранящегося в переменной объекта: `TypeName` функции и `TypeOf...Is` оператор.  
  
## <a name="typename-and-typeofis"></a>TypeName и TypeOf... —  
 `TypeName` Функция возвращает строку и лучше всего подходит при необходимости хранить или отображать имя класса объекта, как показано в следующем фрагменте кода:  
  
 [!code-vb[VbVbalrOOP&#92;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]  
  
 `TypeOf...Is` Оператор лучше всего подходит для тестирования тип объекта, так как он работает намного быстрее, чем эквивалентное строковое сравнение с помощью `TypeName`. В следующем фрагменте кода используется `TypeOf...Is` в `If...Then...Else` инструкции:  
  
 [!code-vb[VbVbalrOOP&#93;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]  
  
 Здесь в качестве предупреждения должно быть выполнено. `TypeOf...Is` Оператор возвращает `True` , если объект имеет конкретный тип или является производным от конкретного типа. Почти все в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выполняется с помощью объектов, содержащих некоторые элементы, которые не считаются обычно объектами, например строки и целые числа. Эти объекты являются производными и наследуют методы от <xref:System.Object>.</xref:System.Object> При передаче `Integer` и вычислении с `Object`, `TypeOf...Is` оператор возвращает `True`. В следующем примере сообщается, что параметр `InParam` одновременно `Object` и `Integer`:  
  
 [!code-vb[VbVbalrOOP&#94;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]  
  
 В следующем примере оба `TypeOf...Is` и `TypeName` для определения типа объекта, переданного в `Ctrl` аргумент. `TestObject` Вызовы процедур `ShowType` с три различных типа элементов управления.  
  
#### <a name="to-run-the-example"></a>Запуск примера  
  
1.  Создание нового проекта приложения Windows и добавление <xref:System.Windows.Forms.Button>управления <xref:System.Windows.Forms.CheckBox>управления и <xref:System.Windows.Forms.RadioButton>на форму элемент управления.</xref:System.Windows.Forms.RadioButton> </xref:System.Windows.Forms.CheckBox> </xref:System.Windows.Forms.Button>  
  
2.  С помощью кнопки на форме вызовите `TestObject` процедуры.  
  
3.  Добавьте следующий код в форму:  
  
     [!code-vb[VbVbalrOOP&#95;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Information.TypeName%2A></xref:Microsoft.VisualBasic.Information.TypeName%2A>   
 [Вызов свойства или метода с помощью строкового имени](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)   
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [If... Затем... Оператор else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Тип данных String](../../../../visual-basic/language-reference/data-types/string-data-type.md)   
 [Тип данных Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
