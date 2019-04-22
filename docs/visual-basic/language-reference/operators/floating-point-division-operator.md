---
title: Оператор / (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./
helpviewer_keywords:
- division operator [Visual Basic], floating point
- floating-point numbers [Visual Basic], division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- operators [Visual Basic], division
- division operator [Visual Basic], syntax
- / operator [Visual Basic]
- math operators [Visual Basic]
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
ms.openlocfilehash: af2316f92e2904eee1e8c046b34b8147e40cb513
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825070"
---
# <a name="-operator-visual-basic"></a>Оператор / (Visual Basic)
Делит два числа и возвращает результат с плавающей запятой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a>Части  
 `expression1`  
 Обязательный. Произвольное числовое выражение.  
  
 `expression2`  
 Обязательный. Произвольное числовое выражение.  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 Все числовые типы, включая типы без знака и с плавающей запятой и `Decimal`.  
  
## <a name="result"></a>Результат  
 Результатом является полное частное от `expression1` деления на `expression2`, включая остаток.  
  
 [\ Оператора (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) возвращает частное целого числа, без остатка.  
  
## <a name="remarks"></a>Примечания  
 Тип данных результата зависит от типов операндов. Следующая таблица показывает, как определяется тип данных результата.  
  
|Типы данных операндов|Тип данных результата|  
|------------------------|----------------------|  
|Оба выражения имеют целочисленных типов данных ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [байтов](../../../visual-basic/language-reference/data-types/byte-data-type.md), [короткие](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [целое число](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|`Double`|  
|Одно выражение имеет тип [единый](../../../visual-basic/language-reference/data-types/single-data-type.md) тип данных, а другой — не [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Single`|  
|Одно выражение имеет тип [десятичное](../../../visual-basic/language-reference/data-types/decimal-data-type.md) тип данных, а другой — не [единый](../../../visual-basic/language-reference/data-types/single-data-type.md) или [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Decimal`|  
|Одно из выражений имеет [двойные](../../../visual-basic/language-reference/data-types/double-data-type.md) тип данных|`Double`|  
  
 Прежде чем деления все целочисленные числовые выражения преобразуются в тип `Double`. Если назначить результат в целочисленный тип данных, Visual Basic пытается преобразовать результат из `Double` к этому типу. Это может вызвать исключение, если результат не умещается в этом типе. В частности см. в разделе «Попытка деления на нуль» на этой странице справки.  
  
 Если `expression1` или `expression2` принимает значение [ничего не](../../../visual-basic/language-reference/nothing.md), он интерпретируется как ноль.  
  
## <a name="attempted-division-by-zero"></a>Попытка деления на ноль  
 Если `expression2` результатом которого является ноль, `/` оператор ведет себя по-разному для разных типов данных операнда. В следующей таблице показаны возможные результаты.  
  
|Типы данных операндов|Поведение при `expression2` равно нулю|  
|------------------------|---------------------------------------|  
|С плавающей запятой (`Single` или `Double`)|Возвращает бесконечность (<xref:System.Double.PositiveInfinity> или <xref:System.Double.NegativeInfinity>), или <xref:System.Double.NaN> (не число) Если `expression1` также имеет нулевое значение|  
|`Decimal`|Создает исключение <xref:System.DivideByZeroException>|  
|Целочисленный тип (со знаком или без знака)|Выполняется преобразование в целочисленный тип создает исключение <xref:System.OverflowException> поскольку целочисленных типов не может принимать <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, или <xref:System.Double.NaN>|  
  
> [!NOTE]
>  `/` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `/` оператора для выполнения операции деления с плавающей запятой. Результатом является частное двух операндов.  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 Выражения в предыдущем примере возвращают значения 2,5 и 3,333333. Обратите внимание, что результат всегда с плавающей запятой (`Double`), несмотря на то, что оба операнда являются целочисленными константами.  
  
## <a name="see-also"></a>См. также

- [/ =-Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [\ Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [Типы данных результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
