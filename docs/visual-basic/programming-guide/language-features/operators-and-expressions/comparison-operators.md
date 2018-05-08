---
title: Comparison Operators in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- comparison operators [Visual Basic], comparing objects
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- string comparison [Visual Basic], operators
- objects [Visual Basic], comparing
- numbers [Visual Basic], comparing
- Visual Basic code, operators
- string comparison [Visual Basic]
- numeric values [Visual Basic], comparing
- comparison operators [Visual Basic], comparing numeric values
- operators [Visual Basic], comparison
ms.assetid: 0b570339-5407-474f-8421-e183a8b303ee
ms.openlocfilehash: 873ee31bf9c2ab195d66337d52e4a1bb7075ac76
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="comparison-operators-in-visual-basic"></a>Comparison Operators in Visual Basic
Операторы сравнения сравнивают два выражения и возвращают `Boolean` значение, которое представляет связь между значениями. Существуют операторы для сравнения числовых значений, операторы для сравнения строк и операторы для сравнения объектов. Ниже представлено описание всех трех типов операторов.  
  
## <a name="comparing-numeric-values"></a>Сравнение числовых значений  
 Visual Basic сравнивает числовые значения с помощью шести числовых операторов сравнения. Каждый оператор принимает в качестве операндов два выражения, которые были оценены как числовые значения. В следующей таблице перечислены операторы и приведены примеры каждого.  
  
|Оператор|Проверяемое условие|Примеры|  
|--------------|----------------------|--------------|  
|`=` (Равенство)|Значение первого выражения равно значению второго?|`23`   `=`   `33    ' False`<br /><br /> `23`   `=`   `23    ' True`<br /><br /> `23`   `=`   `12    ' False`|  
|`<>` (Неравенство)|Значение первого выражения равно значению второго?|`23`   `<>`   `33    ' True`<br /><br /> `23`   `<>`   `23    ' False`<br /><br /> `23`   `<>`   `12    ' True`|  
|`<` (Меньше)|Значение первого выражения меньше, чем значение второго?|`23`   `<`   `33    ' True`<br /><br /> `23`   `<`   `23    ' False`<br /><br /> `23`   `<`   `12    ' False`|  
|`>` (Больше)|Значение первого выражения больше значения второго?|`23`   `>`   `33    ' False`<br /><br /> `23`   `>`   `23    ' False`<br /><br /> `23`   `>`   `12    ' True`|  
|`<=` (Меньше или равно)|Является значением первое выражение меньше или равно значению второго?|`23`   `<=`   `33    ' True`<br /><br /> `23`   `<=`   `23    ' True`<br /><br /> `23`   `<=`   `12    ' False`|  
|`>=` (Больше или равно)|Значение первого выражения больше или равно значению второго?|`23`   `>=`   `33    ' False`<br /><br /> `23`   `>=`   `23    ' True`<br /><br /> `23`   `>=`   `12    ' True`|  
  
## <a name="comparing-strings"></a>Сравнение строк  
 Visual Basic проводит сравнение строк с помощью [оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md) и числовых операторов сравнения. `Like` Оператор позволяет указать шаблон. Строка затем сравнивается с шаблоном, и если он соответствует, результат будет `True`. В противном случае результатом является `False`. Числовые операторы позволяют сравнивать `String` значения в зависимости от их порядка сортировки, как показано в следующем примере.  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 В предыдущем примере результатом является `True` , так как первый символ в первой строке сортируется до первого символа во второй строке. Если первые символы равны, сравнение будет по-прежнему следующий символ в обе строки и так далее. Также можно проверить равенство строк с помощью оператора равенства, как показано в следующем примере.  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 Если одна строка является префиксом другой, например «aa» и «aaa», более длинная строка считается больше, чем более короткие строки. Это показано в следующем примере.  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 Порядок сортировки основан на двоичное сравнение или текстовые сравнения в зависимости от значения `Option Compare`. Дополнительные сведения см. [Option Compare Statement](../../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="comparing-objects"></a>Сравнение объектов  
 Visual Basic сравнивает две переменные объектной ссылки с [оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) и [оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md). Чтобы определить, ссылаются ли два переменных ссылки на тот же экземпляр объекта, можно использовать любой из этих операторов. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#65](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 В приведенном выше примере `x Is y` равен `True`, поскольку обе переменные ссылаются на один экземпляр. Сравните результат в следующем примере.  
  
 [!code-vb[VbVbalrOperators#66](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_2.vb)]  
  
 В приведенном выше примере `x Is y` равен `False`, поскольку несмотря на то, что переменные и ссылаются на объекты одного типа, они ссылаются на разные экземпляры этого типа.  
  
 Если проверяемых для двух объектов, не указывает на том же экземпляре `IsNot` оператор позволяет избежать грамматических ляпов сочетание `Not` и `Is`. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#67](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_3.vb)]  
  
 В приведенном выше примере `If a IsNot b` эквивалентно `If Not a Is b`.  
  
### <a name="comparing-object-type"></a>Сравнение типов объектов  
 Можно проверить, имеет ли объект определенного типа с `TypeOf`... `Is` выражение. Синтаксис выглядит следующим образом:  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 Когда `typename` указывает тип интерфейса, то `TypeOf`... `Is` возвращает значение `True` Если объект реализует тип интерфейса. Когда `typename` является типом класса, выражение возвращает `True` Если объект является экземпляром указанного класса или класса, производного от указанного класса. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#68](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_4.vb)]  
  
 В приведенном выше примере `TypeOf x Is Control` выражение, результатом которого является `True` так как тип `x` — `Button`, который наследует от `Control`.  
  
 Дополнительные сведения см. в разделе [оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## <a name="see-also"></a>См. также  
 [Сравнения значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [Операторы сравнения](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Операторы](../../../../visual-basic/language-reference/operators/index.md)  
 [Арифметические операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Операторы объединения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
