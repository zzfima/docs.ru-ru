---
title: Операторы сравнения (Visual Basic)
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
- comparison operators [Visual Basic], Visual Basicl
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
ms.openlocfilehash: 4e37f55b4c873c3dbea22a8edf0e5e2b58824720
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604930"
---
# <a name="comparison-operators-visual-basic"></a>Операторы сравнения (Visual Basic)
Ниже приведены операторы сравнения, определенные в Visual Basic.  
  
 `<` Оператор  
  
 `<=` Оператор  
  
 `>` Оператор  
  
 `>=` Оператор  
  
 `=` Оператор  
  
 `<>` Оператор  
  
 [Оператор Is](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [Оператор IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [Оператор Like](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 Эти операторы сравнивают два выражения и определяет ли они равны, и если это не так, как они отличаются. `Is`, `IsNot`, и `Like` подробно описаны на отдельных страницах справки. На этой странице, подробно обсуждаются операторы сравнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательно. Объект `Boolean` значение, представляющее результат сравнения.  
  
 `expression`  
 Обязательно. Любое выражение.  
  
 `comparisonoperator`  
 Обязательно. Любой оператор сравнения.  
  
 `object1`, `object2`  
 Обязательно. Имя любого ссылочного объекта.  
  
 `string`  
 Обязательно. Произвольное выражение `String`.  
  
 `pattern`  
 Обязательно. Любой `String` выражение или диапазона символов.  
  
## <a name="remarks"></a>Примечания  
 Следующая таблица содержит список операторов сравнения и условий, определяющих, будет ли `result` — `True` или `False`.  
  
|Оператор|`True` Если|`False` Если|  
|--------------|---------------|----------------|  
|`<` (Меньше)|`expression1` < `expression2`|`expression1` >= `expression2`|  
|`<=` (Меньше или равно)|`expression1` <= `expression2`|`expression1` > `expression2`|  
|`>` (Больше)|`expression1` > `expression2`|`expression1` <= `expression2`|  
|`>=` (Больше или равно)|`expression1` >= `expression2`|`expression1` < `expression2`|  
|`=` (Равно)|`expression1` = `expression2`|`expression1` <> `expression2`|  
|`<>` (Не равно)|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  [=-Оператор](../../../visual-basic/language-reference/operators/assignment-operator.md) также используется как оператор присваивания.  
  
 `Is` Оператор, `IsNot` оператор и `Like` оператор имеют особые функциональные возможности сравнения, отличающиеся от операторов в предыдущей таблице.  
  
## <a name="comparing-numbers"></a>Сравнение чисел  
 При сравнении выражения типа `Single` для одного из типов, `Double`, `Single` выражение преобразуется в `Double`. Это отличие от поведения в Visual Basic 6.  
  
 Аналогично, при сравнении выражения типа `Decimal` к выражению типа `Single` или `Double`, `Decimal` выражение преобразуется в `Single` или `Double`. Для `Decimal` выражения, дробное значение меньше, чем 1E-28 могут быть утеряны. Такая потеря дробного значения может привести к сравнении считаются равными, если они не двух значений. По этой причине следует проявлять осторожность при использовании проверки на равенство (`=`) для сравнения двух переменных с плавающей запятой. Проверьте, является ли абсолютное значение разницы между двумя числами меньше, чем небольшой приемлемый допуск безопаснее.  
  
### <a name="floating-point-imprecision"></a>С плавающей запятой неточности  
 При работе с числами с плавающей запятой, имейте в виду, что они не всегда имеют точное представление в памяти. Это может привести к непредвиденным результатам определенных операций, таких как значение сравнения и [оператор Mod](../../../visual-basic/language-reference/operators/mod-operator.md). Дополнительные сведения см. в разделе [Устранение неполадок типы данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="comparing-strings"></a>Сравнение строк  
 При сравнении строк строковые выражения вычисляются на основе их порядка сортировки в алфавитном порядке, в зависимости от `Option Compare` параметр.  
  
 `Option Compare Binary` Сравнение на основе порядка сортировки, производного от внутренних двоичных представлений символов строк базовых классов. Порядок сортировки определяется кодовой странице. В следующем примере показано двоичный порядок сортировки.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 `Option Compare Text` Сравнение на основе порядка сортировки без учета регистра, текстовое, определяемого языком приложения строк базовых классов. При задании `Option Compare Text` и сортировки символов в предыдущем примере, применяется следующий порядок сортировки текста:  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a>Зависимость от языкового стандарта  
 При задании `Option Compare Text`, результат сравнения строк может зависеть от языкового стандарта, в котором выполняется приложение. Два символа могут считаться равными в одной среде, но в другом. При использовании сравнения строк для важных решений, например следует ли принять попытку входа в систему, должен быть чувствительность к языковым стандартам. Рассмотрите вариант либо `Option Compare Binary` или вызывающей <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, который учитывает языковой стандарт.  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a>Программирование с операторами сравнения  
 Использование операторов сравнения с `Object` выражения не разрешен в `Option Strict On`. При `Option Strict` — `Off`и либо `expression1` или `expression2` — `Object` выражения, типы во время выполнения определить, как выполняется сравнение. Следующая таблица показывает сравнение выражений и результаты сравнения в зависимости от типа среды выполнения операндов.  
  
|Если операнды имеют|Сравнение|  
|---------------------|-------------------|  
|Оба `String`|Сравнение сортировки, основанное на характеристиках сортировки строк.|  
|Числовые|Объекты преобразуются `Double`, числовое сравнение объектов.|  
|Один числовой и один `String`|`String` Преобразуется в `Double` и выполняется числовое сравнение. Если `String` не может быть преобразован `Double`, <xref:System.InvalidCastException> возникает исключение.|  
|Одно или оба значения имеют ссылочных типов, отличных от `String`|Возникает исключение <xref:System.InvalidCastException>.|  
  
 Числовое сравнение обрабатывает `Nothing` как 0. Строковое сравнение рассматривает `Nothing` как `""` (пустая строка).  
  
## <a name="overloading"></a>Перегрузка  
 Операторы сравнения (`<`. `<=``>`, `>=`, `=`, `<>`) может быть *перегружены*, что означает, что класс или структура может переопределить их поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует эти операторы для класса или структуры, убедитесь, что переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
 Обратите внимание, что [=-оператор](../../../visual-basic/language-reference/operators/assignment-operator.md) может быть перегружен только как оператор сравнения, а не как оператор присваивания.  
  
## <a name="example"></a>Пример  
 В следующем примере показаны различные способы использования операторов сравнения, которые используются для сравнения выражений. Операторы сравнения возвращают `Boolean` результат, представляющий ли указанное выражение, результатом которого является `True`. При применении `>` и `<` операторы в строки, будет выполнено сравнение с использованием обычной алфавитной сортировки строк. Этот порядок может зависеть от настроек языкового стандарта. Зависит ли порядок сортировки учитывает регистр, или не [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) параметр.  
  
 [!code-vb[VbVbalrOperators#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 В приведенном выше примере первое сравнение возвращает `False` и возвращает оставшиеся сравнения `True`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.InvalidCastException>  
 [Оператор =](../../../visual-basic/language-reference/operators/assignment-operator.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Операторы сравнения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
