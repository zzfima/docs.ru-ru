---
title: Операторы сравнения
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
ms.openlocfilehash: e1feb08539e47ec6fda64aa1a1f8ec2cc19f7b62
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346071"
---
# <a name="comparison-operators-in-visual-basic"></a>Comparison Operators in Visual Basic
Операторы сравнения сравнивают два выражения и возвращают `Boolean` значение, представляющее связь их значений. Существуют операторы для сравнения числовых значений, операторы для сравнения строк и операторы для сравнения объектов. Здесь обсуждаются все три типа операторов.  
  
## <a name="comparing-numeric-values"></a>Сравнение числовых значений  
 Visual Basic сравнивает числовые значения с помощью шести числовых операторов сравнения. Каждый оператор принимает в качестве операндов два выражения, результатом вычисления которых являются числовые значения. В следующей таблице перечислены операторы и приведены примеры каждого из них.  
  
|оператора|Проверяемое условие|Примеры|  
|--------------|----------------------|--------------|  
|`=` (равенство)|Значение первого выражения, равное значению второго?|`23`   `=`   `33    ' False`<br /><br /> `23`   `=`   `23    ' True`<br /><br /> `23`   `=`   `12    ' False`|  
|`<>` (неравенство)|Значение первого выражения, не равное значению второго?|`23`   `<>`   `33    ' True`<br /><br /> `23`   `<>`   `23    ' False`<br /><br /> `23`   `<>`   `12    ' True`|  
|`<` (меньше)|Значение первого выражения меньше значения второго?|`23`   `<`   `33    ' True`<br /><br /> `23`   `<`   `23    ' False`<br /><br /> `23`   `<`   `12    ' False`|  
|`>` (больше)|Значение первого выражения, превышающего значение второго?|`23`   `>`   `33    ' False`<br /><br /> `23`   `>`   `23    ' False`<br /><br /> `23`   `>`   `12    ' True`|  
|`<=` (меньше или равно)|Значение первого выражения, которое меньше или равно значению второго?|`23`   `<=`   `33    ' True`<br /><br /> `23`   `<=`   `23    ' True`<br /><br /> `23`   `<=`   `12    ' False`|  
|`>=` (больше или равно)|Значение первого выражения, которое больше или равно значению второго?|`23`   `>=`   `33    ' False`<br /><br /> `23`   `>=`   `23    ' True`<br /><br /> `23`   `>=`   `12    ' True`|  
  
## <a name="comparing-strings"></a>Сравнение строк  
 Visual Basic сравнивает строки с помощью [оператора Like](../../../../visual-basic/language-reference/operators/like-operator.md) , а также числовых операторов сравнения. Оператор `Like` позволяет указать шаблон. Затем Строка сравнивается с шаблоном, и, если он соответствует, результат будет `True`. В противном случае результат будет `False`. Числовые операторы позволяют сравнивать значения `String` на основе их порядка сортировки, как показано в следующем примере.  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 Результатом в предыдущем примере является `True`, так как первый символ в первой строке сортируется перед первым символом во второй строке. Если первые символы равны, то сравнение будет продолжаться со следующим символом в обеих строках и т. д. Можно также проверить равенство строк с помощью оператора равенства, как показано в следующем примере.  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 Если одна строка является префиксом другой, например "AA" и "AAA", более длинная строка считается больше чем укороченная строка. Это показано в следующем примере.  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 Порядок сортировки основан на двоичном сравнении или текстовом сравнении в зависимости от значения параметра `Option Compare`. Дополнительные сведения см. в разделе [вариант инструкции Compare](../../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="comparing-objects"></a>Сравнение объектов  
 Visual Basic сравнивает две переменные ссылки на объект с помощью [оператора is](../../../../visual-basic/language-reference/operators/is-operator.md) и [оператора IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md). Чтобы определить, ссылаются ли две ссылочные переменные на один и тот же экземпляр объекта, можно использовать любой из этих операторов. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#65)]  
  
 В предыдущем примере `x Is y` вычисляется как `True`, так как обе переменные ссылаются на один и тот же экземпляр. Сравните этот результат со следующим примером.  
  
 [!code-vb[VbVbalrOperators#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#66)]  
  
 В предыдущем примере `x Is y` оценивается как `False`, поскольку переменные ссылаются на объекты одного типа, они ссылаются на разные экземпляры этого типа.  
  
 Если требуется проверить наличие двух объектов, не указывающих на один и тот же экземпляр, оператор `IsNot` позволяет избежать сочетания `Not` и `Is`для грамматически неловкий. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#67)]  
  
 В предыдущем примере `If a IsNot b` эквивалентен `If Not a Is b`.  
  
### <a name="comparing-object-type"></a>Сравнение типа объекта  
 Можно проверить, относится ли объект к определенному типу с помощью выражения `TypeOf`...`Is`. Синтаксис выглядит следующим образом:  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 Если `typename` указывает тип интерфейса, выражение `TypeOf`...`Is` возвращает `True`, если объект реализует тип интерфейса. Если `typename` является типом класса, выражение возвращает `True`, если объект является экземпляром указанного класса или класса, производного от указанного класса. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#68)]  
  
 В предыдущем примере выражение `TypeOf x Is Control` вычисляется как `True`, так как тип `x` `Button`, который наследует от `Control`.  
  
 Дополнительные сведения см. в разделе [оператор typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## <a name="see-also"></a>См. также

- [Сравнения значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Операторы сравнения](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Операторы](../../../../visual-basic/language-reference/operators/index.md)
- [Арифметические операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Операторы объединения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
