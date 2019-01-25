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
ms.openlocfilehash: bf7ff1870a523903babd7140e0d8271f9946064b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628062"
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
  
 Эти операторы сравнивают два выражения и определяет ли они равны, и если это не так, как они отличаются. `Is`, `IsNot`, и `Like` подробно обсуждаются на отдельных страницах справки. Операторы сравнения подробно описаны на этой странице.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Объект `Boolean` значение, представляющее результат сравнения.  
  
 `expression`  
 Обязательный. Любое выражение.  
  
 `comparisonoperator`  
 Обязательный. Любой оператор сравнения отношений.  
  
 `object1`, `object2`  
 Обязательный. Имя любого ссылочного объекта.  
  
 `string`  
 Обязательный. Произвольное выражение `String` .  
  
 `pattern`  
 Обязательный. Любой `String` выражение или диапазона символов.  
  
## <a name="remarks"></a>Примечания  
 Следующая таблица содержит список операторов сравнения и условий, определяющих ли `result` — `True` или `False`.  
  
|Оператор|`True`, если|`False`, если|  
|--------------|---------------|----------------|  
|`<` (Меньше)|`expression1` < `expression2`|`expression1` >= `expression2`|  
|`<=` (Меньше или равно)|`expression1` <= `expression2`|`expression1` > `expression2`|  
|`>` (Больше)|`expression1` > `expression2`|`expression1` <= `expression2`|  
|`>=` (Больше или равно)|`expression1` >= `expression2`|`expression1` < `expression2`|  
|`=` (Равно)|`expression1` = `expression2`|`expression1` <> `expression2`|  
|`<>` (Не равно)|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  [=-Оператор](../../../visual-basic/language-reference/operators/assignment-operator.md) также используется как оператор присваивания.  
  
 `Is` Оператор, `IsNot` оператор и `Like` оператор имеют особые функциональные возможности сравнения, которые отличаются от операторы, перечисленные в приведенной выше таблице.  
  
## <a name="comparing-numbers"></a>Сравнение чисел  
 При сравнении выражения типа `Single` к одному из типов `Double`, `Single` будет преобразовано в `Double`. Это отличие поведению в Visual Basic 6.  
  
 Аналогично, при сравнении выражения типа `Decimal` к выражению типа `Single` или `Double`, `Decimal` будет преобразовано в `Single` или `Double`. Для `Decimal` выражения, дробное значение меньше 1E-28 могут быть потеряны. Такая потеря дробного значения может привести к два значения сравниваются как равные, если они не. По этой причине следует проявлять осторожность при использовании проверки на равенство (`=`) для сравнения двух переменных с плавающей запятой. Безопаснее проверить, является ли меньшим, чем небольшой приемлемый допуск абсолютное значение разницы между двумя числами.  
  
### <a name="floating-point-imprecision"></a>С плавающей запятой неточности  
 При работе с числами с плавающей запятой, имейте в виду, что они не всегда имеют точное представление в памяти. Это может привести к непредвиденным результатам определенных операций, таких как сравнения значений и [оператор Mod](../../../visual-basic/language-reference/operators/mod-operator.md). Дополнительные сведения см. в разделе [Устранение неполадок типы данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="comparing-strings"></a>Сравнение строк  
 При сравнении строк строковые выражения вычисляются в алфавитном порядке сортировки, который зависит от `Option Compare` параметр.  
  
 `Option Compare Binary` базовые типы операции сравнения строк на основе порядка сортировки, производного от внутренних двоичных представлений символов. Порядок сортировки определяется кодовой страницей. В следующем примере показано двоичный порядок сортировки.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 `Option Compare Text` базовые типы операции сравнения строк на порядок сортировки без учета регистра, специфичный определяется языкового стандарта приложения. При задании `Option Compare Text` и сортировку символов в предыдущем примере, применяется следующий порядок сортировки текста:  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a>Зависят от языкового стандарта  
 При задании `Option Compare Text`, результат сравнения строк может зависеть от языкового стандарта, в котором выполняется приложение. Два символа могут считаться равными, в разных национальных настройках, а в другом. Если вы используете сравнения строк для важных решений, например следует ли принять попытку входа в систему, можно чувствительность к языковым стандартам. Рассмотрите возможность либо присвоив `Option Compare Binary` или вызывающей <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, который учитывает языковой стандарт.  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a>Программирование с операторами сравнения  
 Использование операторов сравнения отношений с `Object` выражения не допускается в группе `Option Strict On`. При `Option Strict` — `Off`и либо `expression1` или `expression2` является `Object` выражения, типов во время выполнения определить, как выполняется сравнение. Следующая таблица показывает сравнение выражений и результат сравнения в зависимости от типа среды выполнения из операндов.  
  
|Если операнды имеют|Сравнение выполняется|  
|---------------------|-------------------|  
|Оба `String`|Сравнение сортировки, основанное на характеристиках сортировки строк.|  
|Числовые|Объекты преобразуются `Double`, числовое сравнение объектов.|  
|Один числовой и один `String`|`String` Преобразуется в `Double` и выполняется числовое сравнение. Если `String` невозможно преобразовать в `Double`, <xref:System.InvalidCastException> возникает исключение.|  
|Одно или оба являются ссылочными типами, отличное от `String`|Возникает исключение <xref:System.InvalidCastException>.|  
  
 Числовое сравнение обрабатывает `Nothing` как 0. Строковое сравнение рассматривает `Nothing` как `""` (пустая строка).  
  
## <a name="overloading"></a>Перегрузка  
 Операторы сравнения (`<`. `<=``>`, `>=`, `=`, `<>`) может быть *перегружены*, что означает, что класс или структура может переопределить их поведение, если операнд имеет тип этого класса или структуры. Если код использует эти операторы для класса или структуры, убедитесь, что переопределенное. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
 Обратите внимание, что [=-оператор](../../../visual-basic/language-reference/operators/assignment-operator.md) может быть перегружен только как оператор сравнения, а не как оператор присваивания.  
  
## <a name="example"></a>Пример  
 В следующем примере показаны различные способы использования операторов сравнения, используемые для сравнения выражений. Операторы сравнения возвращают `Boolean` результат, представляет ли указанное выражение, результатом которого является `True`. При применении `>` и `<` операторы в строки, будет выполнено сравнение с использованием обычной алфавитной сортировки строк. Этот порядок может зависеть от настроек языкового стандарта. Зависит ли порядок сортировки учитывает регистр, или не [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) параметр.  
  
 [!code-vb[VbVbalrOperators#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 В приведенном выше примере первое сравнение возвращает `False` и вернуть оставшиеся сравнения `True`.  
  
## <a name="see-also"></a>См. также
- <xref:System.InvalidCastException>
- [Оператор =](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Операторы сравнения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
