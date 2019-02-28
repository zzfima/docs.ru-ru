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
ms.openlocfilehash: cd7ee90e749be76012cf7143787bc6f1d096da03
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969379"
---
# <a name="comparison-operators-in-visual-basic"></a>Comparison Operators in Visual Basic
Операторы сравнения сравнивают два выражения и возвращают `Boolean` значение, представляющее отношение их значения. Для сравнения числовых значений, операторы для сравнения строк и операторы для сравнения объектов существует оператора. Ниже представлено описание всех трех типов операторов.  
  
## <a name="comparing-numeric-values"></a>Сравнение числовых значений  
 Visual Basic сравнивает числовые значения с помощью шести числовые операторы сравнения. Каждый оператор принимает в качестве операндов два выражения, которые возвращают числовые значения. В следующей таблице перечислены операторы и приведены примеры каждого из них.  
  
|Оператор|Проверяемое условие|Примеры|  
|--------------|----------------------|--------------|  
|`=` (Равенство)|Значение первого выражения равно значению второго?|`23`   `=`   `33    ' False`<br /><br /> `23`   `=`   `23    ' True`<br /><br /> `23`   `=`   `12    ' False`|  
|`<>` (Неравенство)|Является ли значение первого выражения равно значению второго?|`23`   `<>`   `33    ' True`<br /><br /> `23`   `<>`   `23    ' False`<br /><br /> `23`   `<>`   `12    ' True`|  
|`<` (Меньше)|Значение первого выражения меньше, чем значение второго?|`23`   `<`   `33    ' True`<br /><br /> `23`   `<`   `23    ' False`<br /><br /> `23`   `<`   `12    ' False`|  
|`>` (Больше)|Является ли значение первого выражения больше значения второго?|`23`   `>`   `33    ' False`<br /><br /> `23`   `>`   `23    ' False`<br /><br /> `23`   `>`   `12    ' True`|  
|`<=` (Меньше или равно)|Такое значение первое выражение меньше или равно значению второго?|`23`   `<=`   `33    ' True`<br /><br /> `23`   `<=`   `23    ' True`<br /><br /> `23`   `<=`   `12    ' False`|  
|`>=` (Больше или равно)|Такое значение первое выражение больше или равно значению второго?|`23`   `>=`   `33    ' False`<br /><br /> `23`   `>=`   `23    ' True`<br /><br /> `23`   `>=`   `12    ' True`|  
  
## <a name="comparing-strings"></a>Сравнение строк  
 Visual Basic сравнение строк с помощью [оператор Like](../../../../visual-basic/language-reference/operators/like-operator.md) а также числовые операторы сравнения. `Like` Оператор позволяет указать шаблон. Строка затем сравнивается с шаблоном, и если он соответствует, то результатом является `True`. В противном случае результат будет `False`. Числовые операторы позволяют сравнивать `String` значений на основе их порядка сортировки, как показано в следующем примере.  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 В приведенном выше примере результатом является `True` так, как первый символ в первой строке сортируется до первого символа во второй строке. Если первые символы, сравнение будет по-прежнему следующий символ в обеих строк и так далее. Можно также проверить равенство строк с помощью оператора равенства, как показано в следующем примере.  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 Если одна строка является префиксом другой, например «aa» и «aaa», более длинная строка считается больше, чем более короткая строка. Это показано в следующем примере.  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 Порядок сортировки основан на двоичное сравнение или текстовое сравнение зависимости от настройки `Option Compare`. Дополнительные сведения см. в разделе [оператор Option Compare](../../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="comparing-objects"></a>Сравнение объектов  
 Visual Basic сравнивает две переменные объектной ссылки с [оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) и [оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md). Чтобы определить, если две ссылочные переменные ссылаются на один и тот же экземпляр объекта, можно использовать любой из этих операторов. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#65)]  
  
 В приведенном выше примере `x Is y` принимает значение `True`, так как обе переменные ссылаются на один экземпляр. Сравните этот результат, показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#66)]  
  
 В приведенном выше примере `x Is y` принимает значение `False`, так как несмотря на то, что переменные ссылаются на объекты одного типа, они ссылаются на разные экземпляры этого типа.  
  
 Если вы хотите проверить два объекта, не указывает на один и тот же экземпляр `IsNot` оператор позволяет избежать грамматически неловкий сочетание `Not` и `Is`. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#67)]  
  
 В приведенном выше примере `If a IsNot b` эквивалентен `If Not a Is b`.  
  
### <a name="comparing-object-type"></a>Сравнение типов объектов  
 Можно проверить, имеет ли объект определенного типа с `TypeOf`... `Is` выражение. Синтаксис выглядит следующим образом:  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 Когда `typename` указывает тип интерфейса, а затем `TypeOf`... `Is` возвращает значение `True` Если объект реализует тип интерфейса. Когда `typename` является типом класса, то выражение возвращает `True` Если объект является экземпляром указанного класса или класса, производного от указанного класса. Это показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#68)]  
  
 В приведенном выше примере `TypeOf x Is Control` выражение, результатом которого является `True` так как тип `x` — `Button`, который наследует от `Control`.  
  
 Дополнительные сведения см. в разделе [оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## <a name="see-also"></a>См. также
- [Сравнения значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Операторы сравнения](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Инструкции](../../../../visual-basic/language-reference/operators/index.md)
- [Арифметические операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Операторы объединения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
