---
title: "/ Оператор (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb./
dev_langs:
- VB
helpviewer_keywords:
- division operator, floating point
- floating-point numbers, division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators, division
- division, by zero
- operators [Visual Basic], division
- division operator, syntax
- / operator [Visual Basic]
- math operators
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 71b4f64f6deeb334412c87131ccd9480620f284f
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

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
 Все числовые типы, включая типы без знака и с плавающей запятой и `Decimal`.  
  
## <a name="result"></a>Результат  
 Результатом является полное частное от деления `expression1` деленное `expression2`, включая остаток.  
  
 [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) возвращает целочисленное частное, без остатка.  
  
## <a name="remarks"></a>Примечания  
 Тип данных результата зависит от типов операндов. Следующая таблица показывает, как тип данных результата определяется.  
  
|Типы данных операндов|Тип данных результата|  
|------------------------|----------------------|  
|Оба выражения являются целочисленные типы данных ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [байтов](../../../visual-basic/language-reference/data-types/byte-data-type.md), [короткие](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [целое](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|`Double`|  
|Одно выражение — [одного](../../../visual-basic/language-reference/data-types/single-data-type.md) тип данных, а другой — не [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Single`|  
|Одно выражение — [десятичное](../../../visual-basic/language-reference/data-types/decimal-data-type.md) тип данных, а другой — не [одного](../../../visual-basic/language-reference/data-types/single-data-type.md) или [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Decimal`|  
|Одно из выражений имеет [двойные](../../../visual-basic/language-reference/data-types/double-data-type.md) тип данных|`Double`|  
  
 Перед выполнением деления все целочисленные числовые выражения преобразуются в тип `Double`. Если присвоить результат целочисленный тип данных, Visual Basic попытается преобразовать результат из `Double` к этому типу. Это может вызвать исключение, если результат не умещается в этом типе. В частности в разделе «Попытка деления на ноль» на этой странице справки.  
  
 Если `expression1` или `expression2` равен [ничего](../../../visual-basic/language-reference/nothing.md), оно интерпретируется как ноль.  
  
## <a name="attempted-division-by-zero"></a>Попытка деления на ноль  
 Если `expression2` равен нулю, `/` оператор различается для разных типов данных операнда. В следующей таблице показаны возможные результаты.  
  
|Типы данных операндов|Поведение при `expression2` равно нулю|  
|------------------------|---------------------------------------|  
|С плавающей запятой (`Single` или `Double`)|Возвращает бесконечность (<xref:System.Double.PositiveInfinity> или <xref:System.Double.NegativeInfinity>), или <xref:System.Double.NaN>(не число) Если `expression1` также имеет нулевое значение</xref:System.Double.NaN> </xref:System.Double.NegativeInfinity> </xref:System.Double.PositiveInfinity>|  
|`Decimal`|Создает исключение<xref:System.DivideByZeroException></xref:System.DivideByZeroException>|  
|Целочисленное (знаковое или без знака)|Выполняется преобразование обратно к целому типу возникает исключение <xref:System.OverflowException>, так как не принимает целочисленные типы <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, или <xref:System.Double.NaN></xref:System.Double.NaN> </xref:System.Double.NegativeInfinity> </xref:System.Double.PositiveInfinity> </xref:System.OverflowException>|  
  
> [!NOTE]
>  `/` Оператор может быть *перегруженные*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `/` оператора для выполнения операции деления с плавающей запятой. Результатом является частное двух операндов.  
  
 [!code-vb[VbVbalrOperators №&16;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]  
  
 Выражения в предыдущем примере возвращают значения 2,5 и 3,333333. Обратите внимание, что результат всегда с плавающей запятой (`Double`), даже если оба операнда являются целочисленными константами.  
  
## <a name="see-also"></a>См. также  
 [/ =-Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)   
 [\ Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)   
 [Типы данных результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)   
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Приоритет операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)

