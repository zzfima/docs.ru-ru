---
title: "Операторы сравнения в Visual Basic | Документы Microsoft"
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
- comparison operators, comparing strings
- comparison operators, comparing objects
- strings [Visual Basic], comparing
- comparison operators
- string comparison [Visual Basic], operators
- objects [Visual Basic], comparing
- numbers, comparing
- Visual Basic code, operators
- string comparison [Visual Basic]
- numeric values, comparing
- comparison operators, comparing numeric values
- operators [Visual Basic], comparison
ms.assetid: 0b570339-5407-474f-8421-e183a8b303ee
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
ms.openlocfilehash: 6185d1676f2cd160c9c3e855cce4a6d2bbe2ffb4
ms.lasthandoff: 03/13/2017

---
# <a name="comparison-operators-in-visual-basic"></a>Comparison Operators in Visual Basic
Операторы сравнения сравнивают два выражения и возвращают `Boolean` значение, которое представляет связь между значениями. Операторы используются для сравнения числовых значений, операторы для сравнения строк и операторы для сравнения объектов. Ниже представлено описание всех трех типов операторов.  
  
## <a name="comparing-numeric-values"></a>Сравнение числовых значений  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]сравнивает числовые значения с помощью шести числовых операторов сравнения. Каждый оператор принимает в качестве операндов два выражения, которые возвращают числовые значения. В следующей таблице перечислены операторы и приведены примеры каждого.  
  
|Оператор|Проверяемое условие|Примеры|  
|--------------|----------------------|--------------|  
|`=`(Равенство)|Значение первого выражения равно значению второго?|`23`   `=`   `33    ' False`<br /><br /> `23`   `=`   `23    ' True`<br /><br /> `23`   `=`   `12    ' False`|  
|`<>`(Неравенство)|Значение первого выражения равно значению второго?|`23`   `<>`   `33    ' True`<br /><br /> `23`   `<>`   `23    ' False`<br /><br /> `23`   `<>`   `12    ' True`|  
|`<`(Меньше чем)|Значение первого выражения меньше значения второго?|`23`   `<`   `33    ' True`<br /><br /> `23`   `<`   `23    ' False`<br /><br /> `23`   `<`   `12    ' False`|  
|`>`(Больше)|Значение первого выражения больше значения второго?|`23`   `>`   `33    ' False`<br /><br /> `23`   `>`   `23    ' False`<br /><br /> `23`   `>`   `12    ' True`|  
|`<=`(Меньше или равно)|Значение первого выражения меньше или равно значению второго?|`23`   `<=`   `33    ' True`<br /><br /> `23`   `<=`   `23    ' True`<br /><br /> `23`   `<=`   `12    ' False`|  
|`>=`(Больше или равно)|Значение первого выражения больше или равно значению второго?|`23`   `>=`   `33    ' False`<br /><br /> `23`   `>=`   `23    ' True`<br /><br /> `23`   `>=`   `12    ' True`|  
  
## <a name="comparing-strings"></a>Сравнение строк  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]сравнение строк с помощью [оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md) и числовых операторов сравнения. `Like` Оператор позволяет указать шаблон. Строка затем сравнивается с шаблоном, и если он соответствует, результатом будет `True`. В противном случае результатом является `False`. Числовые операторы позволяют сравнивать `String` значения на основе их порядка сортировки, как показано в следующем примере.  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 В предыдущем примере результатом является `True` , поскольку первый символ в первой строке сортируется до первого символа во второй строке. Если первые символы равны, сравнение будет по-прежнему следующий символ в обеих строках и т.д. Можно также проверить равенство строк с помощью оператора равенства, как показано в следующем примере.  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 Если одна строка является префиксом другой, например «aa» и «aaa», более длинная строка считается больше, чем более короткие строки. Это показано в следующем примере.  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 Порядок сортировки основан на двоичном сравнении или текстовом сравнении в зависимости от параметра `Option Compare`. Дополнительные сведения см. [Option Compare Statement](../../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="comparing-objects"></a>Сравнение объектов  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]сравниваются две ссылочные переменные объекта с [оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) и [оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md). Чтобы определить, если две ссылочные переменные ссылаются на один и тот же экземпляр объекта, можно использовать любой из этих операторов. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators&#65;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 В предыдущем примере `x Is y` равен `True`, поскольку обе переменные ссылаются на один экземпляр. Противоположный результат в следующем примере.  
  
 [!code-vb[VbVbalrOperators&#66;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_2.vb)]  
  
 В предыдущем примере `x Is y` равен `False`, поскольку, хотя переменные и ссылаются на объекты одного типа, ссылки на разные экземпляры этого типа.  
  
 При необходимости тестирования для двух объектов, не указывает на тот же экземпляр `IsNot` оператор позволяет избежать грамматически грубо сочетание `Not` и `Is`. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators&#67;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_3.vb)]  
  
 В предыдущем примере `If a IsNot b` эквивалентно `If Not a Is b`.  
  
### <a name="comparing-object-type"></a>Сравнение типов объектов  
 Можно проверить, является ли объект определенного типа с `TypeOf`... `Is` выражение. Синтаксис выглядит следующим образом:  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 Когда `typename` указывает тип интерфейса, то `TypeOf`... `Is` возвращает значение `True` , если объект реализует тип интерфейса. Когда `typename` является типом класса, выражение возвращает `True` , если объект является экземпляром указанного класса или класса, производного от указанного класса. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators&#68;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_4.vb)]  
  
 В предыдущем примере `TypeOf x Is Control` выражение `True` так как тип `x` — `Button`, который наследуется от `Control`.  
  
 Дополнительные сведения см. в разделе [оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## <a name="see-also"></a>См. также  
 [Сравнение значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Операторы сравнения](../../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Операторы](../../../../visual-basic/language-reference/operators/index.md)   
 [Арифметические операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Операторы объединения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)   
 [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
