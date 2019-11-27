---
title: Значения объектных переменных
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
ms.openlocfilehash: 8b93063d2d97802b1a7fdbc93e01040ff3337753
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351804"
---
# <a name="object-variable-values-visual-basic"></a>Значения объектных переменных (Visual Basic)
Переменная [типа данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) может ссылаться на данные любого типа. Значение, сохраняемое в переменной `Object`, хранится в любом месте в памяти, а сама переменная содержит указатель на данные.  
  
## <a name="object-classifier-functions"></a>Функции-классификаторы объектов  
 Visual Basic предоставляет функции, возвращающие сведения о том, на что ссылается `Object`ая переменная, как показано в следующей таблице.  
  
|Функция|Возвращает значение true, если объектная переменная ссылается на|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|Массив значений, а не одно значение|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|Значение [типа данных Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) или строка, которая может быть интерпретирована как значение даты и времени|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|Объект типа <xref:System.DBNull>, представляющий отсутствующие или несуществующие данные|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|Объект Exception, производный от <xref:System.Exception>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|[Ничего](../../../../visual-basic/language-reference/nothing.md), т. е. в данный момент ни один объект не назначен переменной|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|Число или строка, которую можно интерпретировать как число|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|Ссылочный тип (например, строка, массив, делегат или тип класса);|  
  
 Эти функции можно использовать, чтобы избежать отправки недопустимого значения в операцию или процедуру.  
  
## <a name="typeof-operator"></a>Оператор TypeOf  
 [Оператор typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md) также можно использовать для определения того, относится ли переменная объекта к конкретному типу данных. Выражение `TypeOf`...`Is` принимает значение `True`, если тип операнда во время выполнения является производным от или реализует указанный тип.  
  
 В следующем примере используется `TypeOf` для переменных объекта, ссылающихся на значения и ссылочные типы.  
  
```vb  
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
  
 В предыдущем примере в окно **отладки** записываются следующие строки:  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 Объектная переменная `num` ссылается на данные типа `Integer`, а `frm` ссылается на объект класса <xref:System.Windows.Forms.Form>.  
  
## <a name="object-arrays"></a>Массивы объектов  
 Можно объявить и использовать массив переменных `Object`. Это полезно, когда необходимо управлять множеством типов данных и классов объектов. Все элементы в массиве должны иметь один и тот же объявленный тип данных. Объявление этого типа данных как `Object` позволяет хранить объекты и экземпляры классов вместе с другими типами данных в массиве.  
  
## <a name="see-also"></a>См. также

- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Объявление объектной переменной](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Практическое руководство. Ссылка на текущий экземпляр объекта](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [Практическое руководство. Определение типа, на который указывает объектная переменная](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)
- [Практическое руководство. Определение наличия связи между двумя объектами](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Практическое руководство. Определение идентичности двух объектов](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
