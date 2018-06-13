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
ms.openlocfilehash: 17eb3eddfae3cf7c818514a2fee20f646876a6ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604527"
---
# <a name="-operator-visual-basic"></a>Оператор / (Visual Basic)
Делит два числа и возвращает результат с плавающей запятой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a>Части  
 `expression1`  
 Обязательно. Произвольное числовое выражение.  
  
 `expression2`  
 Обязательно. Произвольное числовое выражение.  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 Все числовые типы, включая типы без знака и с плавающей запятой и `Decimal`.  
  
## <a name="result"></a>Результат  
 Результатом является полное частное от деления `expression1` деленная `expression2`, включая остаток.  
  
 [\ Оператора (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) возвращает целочисленное частное, без остатка.  
  
## <a name="remarks"></a>Примечания  
 Тип данных результата зависит от типов операндов. Следующая таблица показывает, как определяется тип данных результата.  
  
|Типы данных операндов|Тип данных результата|  
|------------------------|----------------------|  
|Оба выражения имеют целочисленные типы данных ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [байтов](../../../visual-basic/language-reference/data-types/byte-data-type.md), [короткие](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [целое](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [длинные](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|`Double`|  
|Одно выражение является [один](../../../visual-basic/language-reference/data-types/single-data-type.md) тип данных, а другой — не [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Single`|  
|Одно выражение является [десятичное](../../../visual-basic/language-reference/data-types/decimal-data-type.md) тип данных, а другой — не [один](../../../visual-basic/language-reference/data-types/single-data-type.md) или [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Decimal`|  
|Одно из выражений имеет [двойные](../../../visual-basic/language-reference/data-types/double-data-type.md) тип данных|`Double`|  
  
 Перед выполнением деления все целочисленные числовые выражения преобразуются в тип `Double`. Если вы назначаете результат целочисленный тип данных, Visual Basic пытается преобразовать результат из `Double` к этому типу. Это может вызвать исключение, если результат не умещается в этом типе. В частности в разделе «Попытка деления на ноль» на этой странице справки.  
  
 Если `expression1` или `expression2` равен [ничего](../../../visual-basic/language-reference/nothing.md), интерпретируется как ноль.  
  
## <a name="attempted-division-by-zero"></a>Попытка деления на ноль  
 Если `expression2` равняется нулю, `/` оператор различается для разных типов данных операнда. В следующей таблице показаны возможные результаты.  
  
|Типы данных операндов|Поведение при `expression2` равно нулю|  
|------------------------|---------------------------------------|  
|С плавающей запятой (`Single` или `Double`)|Возвращает бесконечность (<xref:System.Double.PositiveInfinity> или <xref:System.Double.NegativeInfinity>), или <xref:System.Double.NaN> (не число) Если `expression1` также равно нулю|  
|`Decimal`|Создает исключение <xref:System.DivideByZeroException>|  
|Целочисленное (знаковое или без знака)|Выполняется преобразование в целочисленный тип создает исключение <xref:System.OverflowException> , так как не может принимать целые типы <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, или <xref:System.Double.NaN>|  
  
> [!NOTE]
>  `/` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `/` оператора для выполнения операции деления с плавающей запятой. Результатом является частное двух операндов.  
  
 [!code-vb[VbVbalrOperators#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]  
  
 Выражения в предыдущем примере возвращают значения 2,5 и 3,333333. Обратите внимание, что результат всегда с плавающей запятой (`Double`), даже если оба операнда являются целочисленными константами.  
  
## <a name="see-also"></a>См. также  
 [/ =-Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [\ Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
 [Типы данных результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)  
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
