---
title: Значения объектных переменных (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 28307cc477f661c3046e125f297c1519485ad797
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="object-variable-values-visual-basic"></a>Значения объектных переменных (Visual Basic)
Переменная [тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) может ссылаться на данные любого типа. Значение, сохраненное в `Object` переменной хранится в памяти, а сама переменная содержит указатель на данные.  
  
## <a name="object-classifier-functions"></a>Объект функции-классификаторы  
 Visual Basic предоставляет функции, которые возвращают сведения о том, что `Object` ссылается переменная, как показано в следующей таблице.  
  
|Функция|Возвращает значение True, если переменная объекта ссылается на|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|Массив значений, а не одно значение|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|Объект [тип данных Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) значением или строкой, которая может быть интерпретирована как значение даты и времени|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|Объект типа <xref:System.DBNull>, который представляет пропущенные или несуществующие данные|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|Объект исключения, который является производным от <xref:System.Exception>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|[Ничего не](../../../../visual-basic/language-reference/nothing.md), то есть не в настоящее время назначен объект переменной|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|Число или строку, которая может быть интерпретирована как число|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|Ссылочный тип (например, строка, массив, делегат или тип класса)|  
  
 Чтобы избежать передачи несуществующего значения в операции и процедуры можно использовать эти функции.  
  
## <a name="typeof-operator"></a>Оператор TypeOf  
 Можно также использовать [оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) определить, ссылается ли в данный момент переменная объекта на определенный тип данных. `TypeOf`... `Is` выражение, результатом которого является `True` , если тип операнда во время выполнения является производным от указанного типа или реализует.  
  
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
  
 Предыдущий пример записывает следующие строки для **отладки** окна:  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 Переменная объекта `num` ссылается на данные типа `Integer`, и `frm` ссылается на объект класса <xref:System.Windows.Forms.Form>.  
  
## <a name="object-arrays"></a>Массивы объектов  
 Можно объявить и использовать массив `Object` переменных. Это полезно, когда требуется обрабатывать различные типы данных и классы объектов. Все элементы массива должны иметь тот же объявленный тип данных. Объявление этого типа данных как `Object` позволяет хранить объекты и экземпляры класса вместе с другими типами данных в массиве.  
  
## <a name="see-also"></a>См. также  
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Объявление объектной переменной](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Практическое руководство. Ссылка на текущий экземпляр объекта](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)  
 [Практическое руководство. Определение типа, на который указывает объектная переменная](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)  
 [Практическое руководство. Определение наличия связи между двумя объектами](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [Практическое руководство. Определение идентичности двух объектов](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
