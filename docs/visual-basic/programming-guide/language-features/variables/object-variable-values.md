---
title: "Значения объектных переменных (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "типы данных [Visual Basic], переменная объекта"
  - "объектные переменные, значения"
  - "значения, переменных объекта"
  - "переменные [Visual Basic], объект"
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Значения объектных переменных (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Переменная типа [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) может ссылаться на данные любого типа.  Значение, сохраненное в переменной типа `Object`, хранится в области памяти, а сама переменная содержит указатель на данные.  
  
## Функции классификатора объектов  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] предоставляет функции, которые возвращают сведения о том, на что ссылается переменная типа `Object`, как показано в следующей таблице:  
  
|Функция|Возвращает True, если переменная объекта ссылается на|  
|-------------|-----------------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|Массив значений, а не на одно значение|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|Значение типа [Тип данных Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) или строку, которая может быть интерпретирована как значение даты и времени|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|Объект типа <xref:System.DBNull>, который представляет пропущенные или не существующие данные|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|Объект исключения, являющийся производным от <xref:System.Exception>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|[Nothing](../../../../visual-basic/language-reference/nothing.md), т. е. переменной в данный момент не присвоен объекта|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|Число или строковое значение, которое может быть интерпретировано как число|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|Ссылочный тип \(например, строка, массив, делегат или тип класса\)|  
  
 Можно использовать эти функции, чтобы избежать передачи несуществующего значения оператору или процедуре.  
  
## Оператор TypeOf  
 Можно также использовать оператор [Оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md), чтобы определить, ссылается ли в данный момент переменная объекта на конкретный тип данных.  Выражение `TypeOf`...`Is` равно `True`, если тип операнда во время выполнения является производным от указанного типа или реализует его.  
  
 В следующем примере оператор `TypeOf` применяется к переменным объектов, ссылающимся на значение и ссылочный тип.  
  
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
  
 В результате выполнения данного примера в окне **Отладка** отобразятся следующие строки:  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 Объектная переменная `num` ссылается на данные типа `Integer`, а `frm` ссылается на объект класса <xref:System.Windows.Forms.Form>.  
  
## Массивы объектов  
 Можно объявить и использовать массив переменных типа `Object`.  Это удобно, когда необходимо обработать различные типы данных и классы объектов.  Все элементы массива должны принадлежать одному объявленному типу данных.  Объявление этого типа данных как `Object` позволяет хранить объекты и экземпляры класса вместе с другими типами данных в массиве.  
  
## См. также  
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Объявление переменных объектов](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Практическое руководство. Ссылка на текущий экземпляр объекта](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)   
 [Практическое руководство. Определение типа, на который указывает объектная переменная](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)   
 [Практическое руководство. Определение наличия связи между двумя объектами](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)   
 [Практическое руководство. Определение идентичности двух объектов](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)   
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)