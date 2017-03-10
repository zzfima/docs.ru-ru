---
title: "Операторы сравнения в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "операторы сравнения"
  - "операторы сравнения, сравнение числовых значений"
  - "операторы сравнения, сравнение объектов"
  - "операторы сравнения, сравнение строк"
  - "числа, сравнение"
  - "числовые значения, сравнение"
  - "объекты [Visual Basic], сравнение"
  - "операторы [Visual Basic], сравнение"
  - "сравнение строк [Visual Basic]"
  - "сравнение строк [Visual Basic], операторы"
  - "строки [Visual Basic], сравнение"
  - "код Visual Basic, операторы"
ms.assetid: 0b570339-5407-474f-8421-e183a8b303ee
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Операторы сравнения в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Операторы сравнения сравнивают два выражения и возвращают логическое значение `Boolean`, представляющее отношение двух значений.  Существуют операторы для сравнения числовых значений, операторы для сравнения строк и операторы для сравнения объектов.  Ниже представлено описание всех трех типов операторов.  
  
## Сравнение числовых значений  
 Числовые значения в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] можно сравнить с помощью шести числовых операторов сравнения.  Каждый оператор принимает в качестве операндов два выражения, которые после вычисления принимают числовые значения.  В приведенной ниже таблице перечислены операторы и приведены примеры каждого из них.  
  
|Оператор|Проверяемое условие|Примеры|  
|--------------|-------------------------|-------------|  
|`=` \(равенство\)|Значение первого выражения равно значению второго?|`23`   `=`   `33    ' False`<br /><br /> `23`   `=`   `23    ' True`<br /><br /> `23`   `=`   `12    ' False`|  
|`<>` \(неравенство\)|Значение первого выражения не равно значению второго?|`23`   `<>`   `33    ' True`<br /><br /> `23`   `<>`   `23    ' False`<br /><br /> `23`   `<>`   `12    ' True`|  
|`<` \(меньше\)|Значение первого выражения меньше значения второго?|`23`   `<`   `33    ' True`<br /><br /> `23`   `<`   `23    ' False`<br /><br /> `23`   `<`   `12    ' False`|  
|`>` \(больше\)|Значение первого выражения больше значения второго?|`23`   `>`   `33    ' False`<br /><br /> `23`   `>`   `23    ' False`<br /><br /> `23`   `>`   `12    ' True`|  
|`<=` \(меньше или равно\)|Значение первого выражения меньше или равно значению второго?|`23`   `<=`   `33    ' True`<br /><br /> `23`   `<=`   `23    ' True`<br /><br /> `23`   `<=`   `12    ' False`|  
|`>=` \(больше или равно\)|Значение первого выражения больше или равно значению второго?|`23`   `>=`   `33    ' False`<br /><br /> `23`   `>=`   `23    ' True`<br /><br /> `23`   `>=`   `12    ' True`|  
  
## Сравнение строк  
 В [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] можно сравнивать строки, используя [Оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md) с тем же успехом, что и для числовых операторов сравнения.  Оператор `Like` позволяет указать шаблон.  Строка затем сравнивается с шаблоном, и если она ему соответствует, то результатом сравнения будет `True`.  В противном случае результатом будет `False`.  Числовые операторы позволяют сравнивать значения `String` на основе их порядка сортировки, как это показано в следующем примере:  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 Результатом предыдущего примера является значение `True`, поскольку первый символ в первой строке сортируется до первого символа во второй строке.  Если первые символы равны, продолжается сравнение следующих символов в обеих строках и т.д.  Можно также проверить равенство строк с помощью оператора равенства, как показано в следующем примере:  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 Если в одной строке префикс отличается, например "аа" и "ааа", то та строка, которая длиннее, считается больше той строки, которая короче.  Это показано в приведенном ниже примере.  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 Порядок сортировки основан на двоичном сравнении или текстовом сравнении в зависимости от настройки `Option Compare`.  Дополнительные сведения см. в разделе [Оператор Option Compare](../../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## Сравнение объектов  
 В [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] сравниваются две ссылочные переменные объекта с использованием [Оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) и [Оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md).  Можно использовать любой из этих операторов, чтобы определить, ссылаются ли две ссылочные переменные на один и тот же экземпляр объекта.  Это показано в приведенном ниже примере.  
  
 [!code-vb[VbVbalrOperators#65](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/comparison-operators_1.vb)]  
  
 В предыдущем примере `x Is y` возвращает значение `True`, поскольку обе переменные ссылаются на один и тот же экземпляр.  В следующем примере получается противоположный результат:  
  
 [!code-vb[VbVbalrOperators#66](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/comparison-operators_2.vb)]  
  
 В предыдущем примере `x Is y` возвращает значение `False`, поскольку, хотя переменные и ссылаются на объекты одного типа, ссылки адресованы разным экземплярам этого типа.  
  
 Если требуется проверить, не указывают ли два объекта на один и тот же экземпляр, оператор `IsNot` позволяет избежать грамматических ляпов в сочетании операторов `Not` и `Is`.  Это показано в приведенном ниже примере.  
  
 [!code-vb[VbVbalrOperators#67](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/comparison-operators_3.vb)]  
  
 В предыдущем примере конструкция `If a IsNot b` эквивалентна `If Not a Is b`.  
  
### Сравнение типов объектов  
 Чтобы проверить, имеет ли объект определенный тип, используйте выражение `TypeOf`...`Is`.  Синтаксис выглядит следующим образом:  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 Если `typename` указывает тип интерфейса, то выражение `TypeOf`...`Is` возвращает значение `True`, если объект реализует тип интерфейса.  Если `typename` является типом класса, выражение возвращает значение `True`, если объект является экземпляром указанного класса или класса, производного от указанного класса.  Это показано в приведенном ниже примере.  
  
 [!code-vb[VbVbalrOperators#68](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/comparison-operators_4.vb)]  
  
 В предыдущем примере выражение `TypeOf x Is Control` возвращает значение `True`, поскольку `x` имеет тип `Button`, который наследуется от `Control`.  
  
 Дополнительные сведения см. в разделе [Оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## См. также  
 [Сравнения значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Операторы сравнения](../../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Операторы](../../../../visual-basic/language-reference/operators/index.md)   
 [Арифметические операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Операторы объединения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)   
 [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)