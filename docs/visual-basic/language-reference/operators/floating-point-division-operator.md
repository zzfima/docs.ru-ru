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
ms.openlocfilehash: d30d871d48bc87e050a072cd01a38065be20616c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933261"
---
# <a name="-operator-visual-basic"></a>Оператор / (Visual Basic)
Делит два числа и возвращает результат с плавающей точкой.  
  
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
 Все числовые типы, включая неподписанные и типы с плавающей запятой `Decimal`, и.  
  
## <a name="result"></a>Результат  
 Результатом является полное частное от `expression1` `expression2`деления на, включая остаток.  
  
 [Оператор \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) возвращает целочисленное частное, которое удаляет остаток.  
  
## <a name="remarks"></a>Примечания  
 Тип данных результата зависит от типов операндов. В следующей таблице показано, как определяется тип данных результата.  
  
|Типы данных операндов|Тип данных результата|  
|------------------------|----------------------|  
|Оба выражения являются целочисленными типами данных ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ulong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)).|`Double`|  
|Одно выражение имеет [один](../../../visual-basic/language-reference/data-types/single-data-type.md) тип данных, а другой — не [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) .|`Single`|  
|Одно выражение имеет тип данных [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) , а второй не является [одиночным](../../../visual-basic/language-reference/data-types/single-data-type.md) или [double](../../../visual-basic/language-reference/data-types/double-data-type.md) .|`Decimal`|  
|Любое выражение является типом данных [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
  
 Перед выполнением деления все целочисленные числовые выражения расширяются до `Double`. Если результат присваивается целочисленному типу данных, Visual Basic пытается преобразовать результат из `Double` в этот тип. Это может вызвать исключение, если результат не умещается в этом типе. В частности, см. раздел "попыток деления на ноль" на этой странице справки.  
  
 Если `expression1` или`expression2` имеет значение [Nothing](../../../visual-basic/language-reference/nothing.md), оно считается нулевым.  
  
## <a name="attempted-division-by-zero"></a>Попыток деления на ноль  
 Если `expression2` значение равно нулю `/` , оператор ведет себя по-разному для разных типов данных операндов. В следующей таблице показаны возможные варианты поведения.  
  
|Типы данных операндов|Поведение, `expression2` если равно нулю|  
|------------------------|---------------------------------------|  
|С плавающей запятой`Single` ( `Double`или)|Возвращает бесконечное<xref:System.Double.PositiveInfinity> значение <xref:System.Double.NegativeInfinity>(или) <xref:System.Double.NaN> или (не число), `expression1` если равно нулю|  
|`Decimal`|Создает<xref:System.DivideByZeroException>|  
|Интеграл (со знаком или без знака)|Попытка преобразования обратно в целочисленный тип <xref:System.OverflowException> вызывается из-за <xref:System.Double.PositiveInfinity>того <xref:System.Double.NegativeInfinity>, что целочисленные типы не могут принимать, или<xref:System.Double.NaN>|  
  
> [!NOTE]
> Оператор можно перегрузить, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. `/` Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В этом примере `/` оператор используется для выполнения деления с плавающей запятой. Результатом является частное двух операндов.  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 Выражения в предыдущем примере возвращают значения 2,5 и 3,333333. Обратите внимание, что результат всегда имеет тип с`Double`плавающей запятой (), хотя оба операнда являются целочисленными константами.  
  
## <a name="see-also"></a>См. также

- [Оператор/= (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [Оператор \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [Типы данных результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
