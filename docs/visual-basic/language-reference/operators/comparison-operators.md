---
title: Операторы сравнения
ms.date: 07/20/2015
f1_keywords:
- vb.<>
- vb.>=
- vb.<=
- vb.>
- vb.<
helpviewer_keywords:
- greater than or equal to operator [Visual Basic]
- '>= operator [Visual Basic]'
- = operator [Visual Basic]
- < operator [Visual Basic]
- less than operator [Visual Basic]
- relational operators [Visual Basic], syntax
- Like operator [Visual Basic]
- <> operator [Visual Basic]
- '> operator [Visual Basic]'
- equal operator [Visual Basic]
- less than or equal to operator [Visual Basic]
- symbols, operators
- greater than operator [Visual Basic]
- comparing values [Visual Basic]
- operators [Visual Basic], relational
- string comparison [Visual Basic]
- not equal to comparison operator [Visual Basic]
- <= operator [Visual Basic]
- operators [Visual Basic], comparison
- Is operator [Visual Basic]
- comparison operators [Visual Basic], Visual Basic
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
ms.openlocfilehash: ea7604626ede66da818e4bc22fe4922bc752dc2c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336084"
---
# <a name="comparison-operators-visual-basic"></a>Операторы сравнения (Visual Basic)
Ниже приведены операторы сравнения, определенные в Visual Basic.

 Оператор `<`

 Оператор `<=`

 Оператор `>`

 Оператор `>=`

 Оператор `=`

 Оператор `<>`

 [Оператор Is](../../../visual-basic/language-reference/operators/is-operator.md)

 [Оператор IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)

 [Оператор Like](../../../visual-basic/language-reference/operators/like-operator.md)

 Эти операторы сравнивают два выражения, чтобы определить, равны ли они, и если нет, то их отличия. `Is`, `IsNot`и `Like` подробно обсуждаются на отдельных страницах справки. Реляционные операторы сравнения подробно обсуждаются на этой странице.

## <a name="syntax"></a>Синтаксис
  
```vb
result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a>Части
 `result`  
 Обязательно. Значение `Boolean`, представляющее результат сравнения.

 `expression1`, `expression2`  
 Обязательно. Любое выражение.

 `comparisonoperator`  
 Обязательно. Любой оператор реляционного сравнения.

 `object1`, `object2`  
 Обязательно. Имена ссылочных объектов.

 `string`  
 Обязательно. Произвольное выражение `String` .

 `pattern`  
 Обязательно. Любое `String`ое выражение или диапазон символов.

## <a name="remarks"></a>Примечания
 В следующей таблице содержится список реляционных операторов сравнения и условий, которые определяют, является ли `result` `True` или `False`.

|оператора|`True`, если|`False`, если|
|--------------|---------------|----------------|
|`<` (меньше)|`expression1` < `expression2`|`expression1` >= `expression2`|
|`<=` (меньше или равно)|`expression1` <= `expression2`|`expression1` > `expression2`|
|`>` (больше)|`expression1` > `expression2`|`expression1` <= `expression2`|
|`>=` (больше или равно)|`expression1` >= `expression2`|`expression1` < `expression2`|
|`=` (равно)|`expression1` = `expression2`|`expression1` <> `expression2`|
|`<>` (не равно)|`expression1` <> `expression2`|`expression1` = `expression2`|

> [!NOTE]
> [Оператор =](../../../visual-basic/language-reference/operators/assignment-operator.md) также используется в качестве оператора присваивания.

 Оператор `Is`, оператор `IsNot` и оператор `Like` имеют определенные функции сравнения, отличные от операторов в предыдущей таблице.

## <a name="comparing-numbers"></a>Сравнение чисел
 При сравнении выражения типа `Single` с одним из типов `Double`выражение `Single` преобразуется в `Double`. Это поведение противоположено поведению, обнаруженному в Visual Basic 6.

 Аналогично, при сравнении выражения типа `Decimal` с выражением типа `Single` или `Double`выражение `Decimal` преобразуется в `Single` или `Double`. Для `Decimal`ных выражений любое значение дробной части меньше 1E-28 может быть потеряно. Такая утрата дробных значений может привести к тому, что два значения будут сравниваться как равные, если это не так. По этой причине следует соблюдать осторожность при использовании равенства (`=`) для сравнения двух переменных с плавающей запятой. Безопаснее проверить, является ли абсолютное значение разницы между двумя числами меньше, чем небольшая допустимая погрешность.

### <a name="floating-point-imprecision"></a>Точность чисел с плавающей запятой
 При работе с числами с плавающей запятой следует помнить, что они не всегда имеют точное представление в памяти. Это может привести к непредвиденным результатам некоторых операций, таких как сравнение значений и [оператор Mod](../../../visual-basic/language-reference/operators/mod-operator.md). Дополнительные сведения см. в разделе [Устранение неполадок типов данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).

## <a name="comparing-strings"></a>Сравнение строк
 При сравнении строк строковые выражения оцениваются на основе их порядка сортировки в алфавитном порядке, который зависит от параметра `Option Compare`.

 `Option Compare Binary` базовые сравнения строк по порядковому номеру сортировки, производным от внутренних двоичных представлений символов. Порядок сортировки определяется кодовой страницей. В следующем примере показан типичный порядок двоичной сортировки.

 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

 `Option Compare Text` базовые сравнения строк при сравнении без учета регистра, текстовый порядок сортировки определяется языковым стандартом приложения. При установке `Option Compare Text` и сортировке символов в предыдущем примере применяется следующий порядок сортировки текста:

 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`

### <a name="locale-dependence"></a>Зависимость от локали
 При установке `Option Compare Text`результат сравнения строк может зависеть от языкового стандарта, в котором выполняется приложение. Два символа могут сравниваться как одинаковые в одном языковом стандарте, но не в другом. Если вы используете сравнение строк для принятия важных решений, например, принимаете ли вы попытку входа в систему, вы должны быть извещены о конфиденциальности языкового стандарта. Попробуйте либо задать `Option Compare Binary`, либо вызвать <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, в котором учитывается языковой стандарт.

## <a name="typeless-programming-with-relational-comparison-operators"></a>Программирование без типов с помощью реляционных операторов сравнения
 Использование реляционных операторов сравнения с выражениями `Object` не допускается в `Option Strict On`. Если `Option Strict` `Off`и либо `expression1`, либо `expression2` является выражением `Object`, то типы времени выполнения определяют, как они сравниваются. В следующей таблице показано, как сравниваются выражения и результат сравнения, в зависимости от типа операндов среды выполнения.

|Если операнды|Сравнение:|
|---------------------|-------------------|
|Оба `String`|Сравнение сортировки на основе характеристик сортировки строк.|
|Оба числовых|Объекты, преобразованные в `Double`, числовое сравнение.|
|Один числовой и один `String`|`String` преобразуется в `Double` и выполняется числовое сравнение. Если `String` невозможно преобразовать в `Double`, создается исключение <xref:System.InvalidCastException>.|
|Один или оба являются ссылочными типами, отличными от `String`|Возникает исключение <xref:System.InvalidCastException>.|

 Числовые сравнения обрабатывают `Nothing` как 0. Сравнения строк обрабатывают `Nothing` как `""` (пустая строка).

## <a name="overloading"></a>Перегрузка
 Реляционные операторы сравнения (`<`. `<=`, `>`, `>=`, `=`, `<>`) могут быть *перегружены*. Это означает, что класс или структура могут переопределять их поведение, когда операнд имеет тип этого класса или структуры. Если в коде используются какие-либо из этих операторов в таком классе или структуре, убедитесь, что вы понимаете переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).

 Обратите внимание, что [оператор =](../../../visual-basic/language-reference/operators/assignment-operator.md) можно перегружать только как оператор реляционного сравнения, а не как оператор присваивания.

## <a name="example"></a>Пример
 В следующем примере показаны различные варианты использования реляционных операторов сравнения, которые используются для сравнения выражений. Реляционные операторы сравнения возвращают `Boolean` результат, который представляет, принимает ли указанное выражение значение `True`. При применении операторов `>` и `<` к строкам сравнение выполняется с использованием обычного алфавитного порядка сортировки строк. Этот порядок может зависеть от настроек языкового стандарта. Учитывается ли сортировка с учетом регистра или не зависит от параметра [параметра Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) .

 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]

 В предыдущем примере первое сравнение возвращает `False`, а оставшиеся сравнения возвращают `True`.

## <a name="see-also"></a>См. также

- <xref:System.InvalidCastException>
- [Оператор =](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Операторы сравнения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
