---
title: Типы данных результатов оператора (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], operator result data types
- result data types [Visual Basic]
- operator result data types [Visual Basic]
- operators [Visual Basic], data types
- data types [Visual Basic], ranges
- operators [Visual Basic], result data types
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
ms.openlocfilehash: 135c44217debcddb15fd4cef7e73ca2f98903c43
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45591806"
---
# <a name="data-types-of-operator-results-visual-basic"></a>Типы данных результатов оператора (Visual Basic)
Visual Basic определяет тип данных результата операции на основе типов данных операндов. В некоторых случаях это может быть типом данных с диапазоном больше, чем один из операндов.  
  
## <a name="data-type-ranges"></a>Диапазоны типов данных  
 Диапазоны соответствующих типов данных, в порядке от наименьшего к наибольшему, таковы:  
  
-   [Логическое](../../../visual-basic/language-reference/data-types/boolean-data-type.md) — два возможных значения  
  
-   [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [байтов](../../../visual-basic/language-reference/data-types/byte-data-type.md) — 256 возможных целых значений  
  
-   [Короткий](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md) — 65 536 (6.5... E + 4) возможных целых значений  
  
-   [Целое число](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) — 4 294 967 296 (4.2 … E + 9) возможных целых значений  
  
-   [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md) — 18446744073709551615 (1,8 … E + 19) возможных целых значений  
  
-   [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) — 1.5 … E + 29 возможных целых значений, максимальный диапазон 7, 9... E + 28 (абсолютное значение)  
  
-   [Единый](../../../visual-basic/language-reference/data-types/single-data-type.md) — максимальный диапазон 3.4... E + 38 (абсолютное значение)  
  
-   [Двойные](../../../visual-basic/language-reference/data-types/double-data-type.md) — максимальный диапазон 1.7... E + 308 (абсолютное значение)  
  
 Дополнительные сведения о типах данных Visual Basic см. в разделе [типы данных](../../../visual-basic/language-reference/data-types/index.md).  
  
 Если операнд вычисляется для [ничего не](../../../visual-basic/language-reference/nothing.md), арифметических операторов Visual Basic расценивать это как ноль.  
  
## <a name="decimal-arithmetic"></a>Десятичному  
 Обратите внимание, что [десятичное](../../../visual-basic/language-reference/data-types/decimal-data-type.md) тип данных не является ни с плавающей запятой и целое число.  
  
 Если один из операндов `+`, `–`, `*`, `/`, или `Mod` операции `Decimal` , а другой — не `Single` или `Double`, Visual Basic можно расширить, то другой операнд `Decimal`. Выполняет операцию в `Decimal`, и тип данных результата — `Decimal`.  
  
## <a name="floating-point-arithmetic"></a>Арифметические операции с плавающей запятой  
 Visual Basic выполняет большинство арифметики с плавающей запятой в [двойные](../../../visual-basic/language-reference/data-types/double-data-type.md), который является самым эффективным данных введите для таких операций. Тем не менее если один операнд является [единый](../../../visual-basic/language-reference/data-types/single-data-type.md) , а другой — не `Double`, Visual Basic выполняет операцию в `Single`. Он расширяет каждый операнд при необходимости для соответствующего типа данных перед операцией, и результат содержит этот тип данных.  
  
### <a name="-and--operators"></a>/ и ^ операторы  
 `/` Оператор определен только для [десятичное](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [единый](../../../visual-basic/language-reference/data-types/single-data-type.md), и [двойные](../../../visual-basic/language-reference/data-types/double-data-type.md) типов данных. Visual Basic расширяет каждый операнд при необходимости для соответствующего типа данных перед операцией, и результат содержит этот тип данных.  
  
 Следующая таблица показывает результат типы данных для `/` оператор. Обратите внимание, что эта таблица симметричный; для этого сочетания типов данных операндов тип данных результата является таким же, независимо от порядка операндов.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|Любой целочисленный тип|  
|`Decimal`|Десятичное число|Single|Double|Десятичное число|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|Любой целочисленный тип|Десятичное число|Single|Double|Double|  
  
 `^` Оператор определен только для `Double` тип данных. Visual Basic расширяет каждый операнд при необходимости `Double` перед выполнением операции и результат, тип данных — всегда `Double`.  
  
## <a name="integer-arithmetic"></a>Целочисленных арифметических операций  
 Тип данных результата целочисленной операции зависит от типов данных операндов. Как правило Visual Basic использует следующие политики для определения типа данных результата:  
  
-   Если оба операнда бинарного оператора имеют одинаковый тип данных, результат содержит этот тип данных. Исключением является `Boolean`, который принудительно `Short`.  
  
-   Если беззнаковый операнд участвует с операндом со знаком, результат имеет тип со знаком с по крайней мере большой диапазон как один из операндов.  
  
-   В противном случае результат обычно имеет большее из двух типов данных операндов.  
  
 Обратите внимание на то, что тип данных результата может не совпадать с любым типом данных операнда.  
  
> [!NOTE]
>  Тип данных результата не всегда достаточно велик для хранения всех возможных значений, получающиеся при операции. <xref:System.OverflowException> Исключение может возникнуть, если значение слишком велико для типа данных результата.  
  
### <a name="unary--and--operators"></a>Унарный + и -операторы  
 Следующей таблице показаны типы данных результата для двух унарных операторов, `+` и `–`.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|Унарный `+`|Short|SByte|Byte|Short|UShort|Целое число|UInteger|Long|ULong|  
|Унарный `–`|Short|SByte|Short|Short|целое число|Целое число|Long|Long|Десятичное число|  
  
### <a name="-and--operators"></a><\< и >> операторы  
 Следующей таблице показаны типы данных результата для двух операторов сдвига, `<<` и `>>`. Visual Basic обрабатывает каждый оператор битового сдвига как унарный оператор на левый операнд (битовый шаблон должны сдвигаться).  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Целое число|UInteger|Long|ULong|  
  
 Если левый операнд является `Decimal`, `Single`, `Double`, или `String`, Visual Basic пытается преобразовать его в `Long` перед выполнением операции и результат, тип данных является `Long`. Правый операнд (количество позиций битов для сдвига) должен иметь `Integer` или типом, который расширяется до `Integer`.  
  
### <a name="binary----and-mod-operators"></a>Двоичный +, -, * и операторы, Mod  
 Следующая таблица показывает результат типы данных для двоичного файла `+` и `–` операторы и `*` и `Mod` операторы. Обратите внимание, что эта таблица симметричный; для этого сочетания типов данных операндов тип данных результата является таким же, независимо от порядка операндов.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|целое число|Целое число|Long|Long|Десятичное число|  
|`SByte`|SByte|SByte|Short|Short|целое число|Целое число|Long|Long|Десятичное число|  
|`Byte`|Short|Short|Byte|Short|UShort|Целое число|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|целое число|Целое число|Long|Long|Десятичное число|  
|`UShort`|Целое число|Целое число|UShort|Целое число|UShort|Целое число|UInteger|Long|ULong|  
|`Integer`|Целое число|Целое число|Целое число|Целое число|Целое число|Целое число|Long|Long|Десятичное число|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Десятичное число|  
|`ULong`|Десятичное число|Десятичное число|ULong|Десятичное число|ULong|Десятичное число|ULong|Десятичное число|ULong|  
  
### <a name="-operator"></a>Оператор \  
 Следующая таблица показывает результат типы данных для `\` оператор. Обратите внимание, что эта таблица симметричный; для этого сочетания типов данных операндов тип данных результата является таким же, независимо от порядка операндов.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|целое число|Целое число|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|целое число|Целое число|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Целое число|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|целое число|Целое число|Long|Long|Long|  
|`UShort`|Целое число|Целое число|UShort|Целое число|UShort|Целое число|UInteger|Long|ULong|  
|`Integer`|Целое число|Целое число|Целое число|Целое число|Целое число|Целое число|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Если один из операндов `\` оператор [десятичное](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [единый](../../../visual-basic/language-reference/data-types/single-data-type.md), или [двойные](../../../visual-basic/language-reference/data-types/double-data-type.md), Visual Basic пытается преобразовать его в [долго](../../../visual-basic/language-reference/data-types/long-data-type.md)перед выполнением операции и результат, тип данных является `Long`.  
  
## <a name="relational-and-bitwise-comparisons"></a>Реляционные и побитовые сравнения  
 Тип данных результата реляционные операции (`=`, `<>`, `<`, `>`, `<=`, `>=`) всегда `Boolean` [логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md). То же самое верно для логических операций (`And`, `AndAlso`, `Not`, `Or`, `OrElse`, `Xor`) на `Boolean` операндов.  
  
 Тип данных результата побитовой логической операции зависит от типов данных операндов. Обратите внимание, что `AndAlso` и `OrElse` определены только для `Boolean`, и Visual Basic преобразует каждый операнд при необходимости `Boolean` перед выполнением операции.  
  
### <a name="-----and--operators"></a>= <>, \<, >, \<= и > = операторы  
 Если оба операнда имеют `Boolean`, Visual Basic рассматривает `True` быть меньше, чем `False`. Если числовой тип будет сравниваться со значением `String`, Visual Basic пытается преобразовать `String` для `Double` перед выполнением операции. Объект `Char` или `Date` операнд можно сравнивать только с другой операнд тот же тип данных. Тип данных результата — всегда `Boolean`.  
  
### <a name="bitwise-not-operator"></a>Побитовый оператор Not  
 Ниже показан результат типы данных для побитового `Not` оператор.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Boolean|SByte|Byte|Short|UShort|Целое число|UInteger|Long|ULong|  
  
 Если операнд является `Decimal`, `Single`, `Double`, или `String`, Visual Basic пытается преобразовать его в `Long` перед выполнением операции и результат, тип данных является `Long`.  
  
### <a name="bitwise-and-or-and-xor-operators"></a>Побитовое и, или и операторы исключающего или  
 Ниже показан результат типы данных для побитового `And`, `Or`, и `Xor` операторы. Обратите внимание, что эта таблица симметричный; для этого сочетания типов данных операндов тип данных результата является таким же, независимо от порядка операндов.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Boolean|SByte|Short|Short|целое число|Целое число|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|целое число|Целое число|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Целое число|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|целое число|Целое число|Long|Long|Long|  
|`UShort`|Целое число|Целое число|UShort|Целое число|UShort|Целое число|UInteger|Long|ULong|  
|`Integer`|Целое число|Целое число|Целое число|Целое число|Целое число|Целое число|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Если операнд — `Decimal`, `Single`, `Double`, или `String`, Visual Basic пытается преобразовать его в `Long` перед операции и данные результатов тип такой же, как в случае операнда уже `Long`.  
  
## <a name="miscellaneous-operators"></a>Прочие операторы  
 `&` Оператор определен только для объединения `String` операндов. Visual Basic преобразует каждый операнд при необходимости `String` перед выполнением операции и результат, тип данных — всегда `String`. В рамках `&` оператор, все преобразования в `String` считаются расширяющимся, даже если `Option Strict` является `On`.  
  
 `Is` И `IsNot` операторов нужно иметь ссылочный тип обоих операндов. `TypeOf`... `Is` выражение требует первый операнд должен быть ссылочного типа, а второй операнд должен быть именем типа данных. Во всех этих случаях данные результата является тип `Boolean`.  
  
 `Like` Оператор определен только для сопоставления шаблонов `String` операндов. Visual Basic пытается преобразовать каждый операнд при необходимости `String` перед выполнением операции. Тип данных результата — всегда `Boolean`.  
  
## <a name="see-also"></a>См. также  
 [Типы данных](../../../visual-basic/language-reference/data-types/index.md)  
 [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Операторы сравнения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Операторы](../../../visual-basic/language-reference/operators/index.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
