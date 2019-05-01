---
title: Значения объектных переменных (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
ms.openlocfilehash: c17c5f85952596f0a080ca473e8f792740e66b8f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054189"
---
# <a name="object-variable-values-visual-basic"></a>Значения объектных переменных (Visual Basic)
Переменная [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) может ссылаться на данные любого типа. Значение, сохраненное в `Object` переменной хранится в памяти, а сама переменная содержит указатель на данные.  
  
## <a name="object-classifier-functions"></a>Объект функции-классификаторы  
 Visual Basic предоставляет функции, возвращающие сведения о том, что `Object` ссылается переменная, как показано в следующей таблице.  
  
|Функция|Возвращает значение True, если переменная объекта ссылается на|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|Массив значений, а не одно значение|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|Объект [тип данных Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) значением или строкой, которая может быть интерпретирована как значение даты и времени|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|Объект типа <xref:System.DBNull>, представляющий данные отсутствуют или не существует|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|Объект исключения, который является производным от <xref:System.Exception>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|[Ничего не](../../../../visual-basic/language-reference/nothing.md), то есть объект не назначено в настоящий момент в переменную|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|Число или строку, которая может быть интерпретирована как число|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|Ссылочный тип (например, строка, массив, делегата или тип класса)|  
  
 Эти функции позволяют избежать передачи недопустимое значение для операции или процедуры.  
  
## <a name="typeof-operator"></a>Оператор TypeOf  
 Можно также использовать [оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) для определения, ссылается ли в данный момент переменной объекта на определенный тип данных. `TypeOf`... `Is` выражение, результатом которого является `True` Если тип операнда во время выполнения является производным от указанного типа или реализует.  
  
 В следующем примере используется `TypeOf` на объектные переменные, ссылающиеся на типы значений и ссылок.  
  
```  
' The following statement puts a value type (Integer) in an Object variable.  
Dim num As Object = 10  
' The following statement puts a reference type (Form) in an Object variable.  
Dim frm As Object = New Form()  
If TypeOf num Is Long Then Debug.WriteLine("num is Long")  
If TypeOf num Is Integer Then Debug.WriteLine("num is Integer")  
If TypeOf num Is Short Then Debug.WriteLine("num is Short")  
If TypeOf num Is Object Then Debug.WriteLine("num is Object")  
If TypeOf frm Is Form Then Debug.WriteLine("frm is Form")  
If TypeOf frm Is Label Then Debug.WriteLine("frm is Label")  
If TypeOf frm Is Object Then Debug.WriteLine("frm is Object")  
```  
  
 Предыдущий пример записывает следующие строки, чтобы **Отладка** окна:  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 Переменная объекта `num` ссылается на данные типа `Integer`, и `frm` ссылается на объект класса <xref:System.Windows.Forms.Form>.  
  
## <a name="object-arrays"></a>Массивы объектов  
 Можно объявить и использовать массив `Object` переменные. Это полезно в тех случаях, когда вам нужно обрабатывать различные типы данных и классы объектов. Все элементы в массиве, должны иметь тот же объявленный тип данных. Объявление этого типа данных как `Object` позволяет хранить объекты и экземпляры класса вместе с другими типами данных в массиве.  
  
## <a name="see-also"></a>См. также

- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Объявление объектной переменной](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Практическое руководство. Ссылка на текущий экземпляр объекта](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [Практическое руководство. Определить, какой тип, переменная объекта ссылается на](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)
- [Практическое руководство. Определение связи между двумя объектами](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Практическое руководство. Определение идентичности двух объектов](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
