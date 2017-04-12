---
title: "Объект значения переменной (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- object variables, values
- values, of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
caps.latest.revision: 18
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
ms.openlocfilehash: ff219571de9c76802d3f8d3046cf6b6f9d5be9d5
ms.lasthandoff: 03/13/2017

---
# <a name="object-variable-values-visual-basic"></a>Значения объектных переменных (Visual Basic)
Переменная [тип данных объекта](../../../../visual-basic/language-reference/data-types/object-data-type.md) может ссылаться на данные любого типа. Значение, сохраненное в `Object` переменной хранится в памяти, а сама переменная содержит указатель на данные.  
  
## <a name="object-classifier-functions"></a>Функции классификатора объектов  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]предоставляет функции, которые возвращают сведения о том, что `Object` ссылается переменная, как показано в следующей таблице.  
  
|Функция|Возвращает значение True, если переменная объекта ссылается на|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A></xref:Microsoft.VisualBasic.Information.IsArray%2A>|Массив значений, а не одно значение|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A></xref:Microsoft.VisualBasic.Information.IsDate%2A>|Объект [тип данных Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) значение или строку, которая может быть интерпретирована как значение даты и времени|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A></xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|Объект типа <xref:System.DBNull>который представляет пропущенные или несуществующие данные</xref:System.DBNull>|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A></xref:Microsoft.VisualBasic.Information.IsError%2A>|Объект исключения, являющийся производным от<xref:System.Exception></xref:System.Exception>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A></xref:Microsoft.VisualBasic.Information.IsNothing%2A>|[Ничего не](../../../../visual-basic/language-reference/nothing.md), то есть объект не назначено в настоящий момент в переменную|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A></xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|Число или строку, которое может быть интерпретировано как число|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A></xref:Microsoft.VisualBasic.Information.IsReference%2A>|Ссылочный тип (например, строка, массив, делегат или тип класса)|  
  
 Эти функции позволяют избежать передачи несуществующего значения оператору или процедуре.  
  
## <a name="typeof-operator"></a>Оператор TypeOf  
 Можно также использовать [оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) определить, ссылается ли в данный момент переменная объекта для определенного типа данных. The `TypeOf`... `Is` выражение `True` Если тип операнда во время выполнения является производным от указанного типа или реализует.  
  
 В следующем примере используется `TypeOf` на переменным объектов, ссылающимся на значение и ссылочный тип.  
  
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
  
 Предыдущий пример записывает следующие строки в **отладки** окна:  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 Объектная переменная `num` ссылается на данные типа `Integer`, и `frm` ссылается на объект класса <xref:System.Windows.Forms.Form>.</xref:System.Windows.Forms.Form>  
  
## <a name="object-arrays"></a>Массивы объектов  
 Можно объявить и использовать массив `Object` переменных. Это полезно, когда необходимо обработать различные типы данных и классы объектов. Все элементы массива должны иметь тот же объявленный тип данных. Объявление этого типа данных как `Object` позволяет хранить объекты и экземпляры класса вместе с другими типами данных в массиве.  
  
## <a name="see-also"></a>См. также  
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Объявление переменных объектов](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Практическое руководство: ссылки на текущий экземпляр объекта](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)   
 [Практическое руководство: определение типа, который указывает объектная переменная](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)   
 [Практическое руководство: определение связи между двумя объектами](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)   
 [Практическое руководство: Определение идентичности двух объектов](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)   
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
