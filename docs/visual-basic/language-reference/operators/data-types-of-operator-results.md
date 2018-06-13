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
ms.openlocfilehash: c2e94a80e83becf25bf47ef7837362f0ebf441a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605437"
---
# <a name="data-types-of-operator-results-visual-basic"></a>Типы данных результатов оператора (Visual Basic)
Visual Basic определяет тип данных результата операции на основе типов данных операндов. В некоторых случаях это может быть тип данных с диапазоном больше, чем один из операндов.  
  
## <a name="data-type-ranges"></a>Диапазоны типов данных  
 Диапазоны соответствующих типов данных, в порядке от наименьшего к наибольшему, выглядят следующим образом:  
  
-   [Логическое](../../../visual-basic/language-reference/data-types/boolean-data-type.md) — два возможных значения  
  
-   [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [байтов](../../../visual-basic/language-reference/data-types/byte-data-type.md) — 256 возможных целых значений  
  
-   [Краткое](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md) — 65 536 байт (6.5... E + 4) возможных целых значений  
  
-   [Целое число со знаком](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) — 4 294 967 296 (4.2... E + 9) возможных целых значений  
  
-   [Длинное](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md) — 18446744073709551615 (1.8... E + 19) возможных целых значений  
  
-   [Десятичное число](../../../visual-basic/language-reference/data-types/decimal-data-type.md) — 1.5... E + 29 возможных целых значений, максимальный диапазон 7, 9... E + 28 (абсолютное значение)  
  
-   [Один](../../../visual-basic/language-reference/data-types/single-data-type.md) — максимальный диапазон 3.4... E + 38 (абсолютное значение)  
  
-   [Двойные](../../../visual-basic/language-reference/data-types/double-data-type.md) — максимальный диапазон 1.7... E + 308 (абсолютное значение)  
  
 Дополнительные сведения о типах данных Visual Basic см. в разделе [типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
 Если операнд имеет значение [ничего](../../../visual-basic/language-reference/nothing.md), арифметических операторов Visual Basic рассматривать его как ноль.  
  
## <a name="decimal-arithmetic"></a>Десятичному  
 Обратите внимание, что [десятичное](../../../visual-basic/language-reference/data-types/decimal-data-type.md) не является типом данных с плавающей запятой ни целым числом.  
  
 Если хотя бы один операнд `+`, `–`, `*`, `/`, или `Mod` операция `Decimal` , а другой — не `Single` или `Double`, Visual Basic может быть расширен второй операнд `Decimal`. Он выполняет операцию в `Decimal`, и тип данных результата является `Decimal`.  
  
## <a name="floating-point-arithmetic"></a>Арифметические операции с плавающей запятой  
 Visual Basic выполняет большинство арифметических операций с плавающей запятой, в [двойные](../../../visual-basic/language-reference/data-types/double-data-type.md), который является наиболее эффективным данных введите для таких операций. Тем не менее если один из операндов является [один](../../../visual-basic/language-reference/data-types/single-data-type.md) , а другой — не `Double`, Visual Basic выполняет операцию в `Single`. Он расширяет каждый операнд при необходимости для соответствующего типа данных перед операцией, и результат обладает этим типом данных.  
  
### <a name="-and--operators"></a>/ и ^ операторы  
 `/` Оператор определен только для [десятичное](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [один](../../../visual-basic/language-reference/data-types/single-data-type.md), и [двойные](../../../visual-basic/language-reference/data-types/double-data-type.md) типов данных. Visual Basic расширяет каждый операнд при необходимости для соответствующего типа данных перед операцией, и результат обладает этим типом данных.  
  
 Ниже показан результат типы данных для `/` оператор. Обратите внимание, что эта таблица является симметричной; для данной комбинации типов данных операнда тип данных результата одинаково независимо от порядка операндов.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|Любой целочисленный тип|  
|`Decimal`|Десятичное число|Single|Double|Десятичное число|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|Любой целочисленный тип|Десятичное число|Single|Double|Double|  
  
 `^` Оператор определен только для `Double` тип данных. Visual Basic расширяет каждый операнд при необходимости `Double` до операции, а результат всегда имеет тип данных `Double`.  
  
## <a name="integer-arithmetic"></a>Целочисленных арифметических операций  
 Тип данных результата целочисленной операции зависит от типов данных операндов. Как правило Visual Basic использует следующие политики для определения типа данных результата:  
  
-   Если оба операнда бинарного оператора имеют одинаковый тип данных, результат обладает этим типом данных. Исключением является `Boolean`, который принудительно `Short`.  
  
-   Если беззнаковый операнд участвует в операции со знаковым операндом, результат имеет тип со знаком с по крайней мере большой диапазон как один из операндов.  
  
-   В противном случае результат обычно имеет большее из двух типов данных операндов.  
  
 Обратите внимание, что тип данных результата может не совпадать с любым типом данных операнда.  
  
> [!NOTE]
>  Тип данных результата не всегда достаточно велик для хранения всех возможных значений, получающиеся при операции. <xref:System.OverflowException> Исключение может возникнуть, если значение слишком велико для типа данных результата.  
  
### <a name="unary--and--operators"></a>Унарный + и -операторы  
 Ниже показан результат типы данных для двух унарных операторов, `+` и `–`.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|Унарный `+`|Short|SByte|Byte|Short|UShort|Целое число|UInteger|Long|ULong|  
|Унарный `–`|Short|SByte|Short|Short|целое число|Целое число|Long|Long|Десятичное число|  
  
### <a name="-and--operators"></a><\< и >> операторы  
 Ниже показан результат типы данных для двух операторов сдвига `<<` и `>>`. Visual Basic рассматривает каждый оператор поразрядного сдвига как унарный оператор для его левый операнд (битовый шаблон сдвиг).  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Целое число|UInteger|Long|ULong|  
  
 Если левый операнд является `Decimal`, `Single`, `Double`, или `String`, Visual Basic попытается преобразовать его в `Long` до операции, а результат имеет тип данных `Long`. Правый операнд (количество позиций битов для сдвига) должен быть `Integer` или тип, который расширяется до `Integer`.  
  
### <a name="binary----and-mod-operators"></a>Двоичный +, -, * и операторы, Mod  
 Ниже показан результат типы данных для двоичного файла `+` и `–` операторы и `*` и `Mod` операторы. Обратите внимание, что эта таблица является симметричной; для данной комбинации типов данных операнда тип данных результата одинаково независимо от порядка операндов.  
  
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
 Ниже показан результат типы данных для `\` оператор. Обратите внимание, что эта таблица является симметричной; для данной комбинации типов данных операнда тип данных результата одинаково независимо от порядка операндов.  
  
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
  
 Если хотя бы один операнд `\` оператор [десятичное](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [один](../../../visual-basic/language-reference/data-types/single-data-type.md), или [двойные](../../../visual-basic/language-reference/data-types/double-data-type.md), Visual Basic попытается преобразовать его в [долго](../../../visual-basic/language-reference/data-types/long-data-type.md)до операции, а результат имеет тип данных `Long`.  
  
## <a name="relational-and-bitwise-comparisons"></a>Реляционные и побитовые сравнения  
 Тип данных результата операции реляционной (`=`, `<>`, `<`, `>`, `<=`, `>=`) всегда `Boolean` [тип данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md). То же самое верно для логических операций (`And`, `AndAlso`, `Not`, `Or`, `OrElse`, `Xor`) на `Boolean` операндов.  
  
 Тип данных результата побитовой логической операции зависит от типов данных операндов. Обратите внимание, что `AndAlso` и `OrElse` определены только для `Boolean`, и Visual Basic преобразует каждый операнд при необходимости `Boolean` перед выполнением операции.  
  
### <a name="-----and--operators"></a>= <>, \<, >, \<= и > =, операторы  
 Если оба операнда имеют `Boolean`, Visual Basic рассматривает `True` быть меньше, чем `False`. Если числовой тип, сравнивается с `String`, Visual Basic пытается преобразовать `String` для `Double` перед операцией. Объект `Char` или `Date` операнд можно сравнивать только с другим операндом того же типа данных. Тип данных результата всегда является `Boolean`.  
  
### <a name="bitwise-not-operator"></a>Побитовый оператор Not  
 Ниже показан результат типы данных для побитового `Not` оператор.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Boolean|SByte|Byte|Short|UShort|Целое число|UInteger|Long|ULong|  
  
 Если операнд равен `Decimal`, `Single`, `Double`, или `String`, Visual Basic попытается преобразовать его в `Long` до операции, а результат имеет тип данных `Long`.  
  
### <a name="bitwise-and-or-and-xor-operators"></a>Побитовое и, или и операторы исключающего или  
 Ниже показан результат типы данных для побитового `And`, `Or`, и `Xor` операторы. Обратите внимание, что эта таблица является симметричной; для данной комбинации типов данных операнда тип данных результата одинаково независимо от порядка операндов.  
  
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
  
 Если операнд `Decimal`, `Single`, `Double`, или `String`, Visual Basic попытается преобразовать его в `Long` до операции, а результирующие данные указан тот же тип как если бы этот операнд уже была `Long`.  
  
## <a name="miscellaneous-operators"></a>Прочие операторы  
 `&` Оператор определен только для объединения `String` операндов. Visual Basic каждый операнд при необходимости преобразуется к `String` до операции, а результат всегда имеет тип данных `String`. В целях `&` оператор, все преобразования в `String` считаются расширяющими, даже если `Option Strict` — `On`.  
  
 `Is` И `IsNot` операторов нужно иметь ссылочный тип обоих операндов. `TypeOf`... `Is` выражение требует, чтобы первый операнд был ссылочного типа, а второй операнд на имя типа данных. Во всех этих случаях данные результирующий тип — `Boolean`.  
  
 `Like` Оператор определен только для соответствия шаблону `String` операндов. Visual Basic предпринимается попытка преобразовать каждый операнд при необходимости `String` перед операцией. Тип данных результата всегда является `Boolean`.  
  
## <a name="see-also"></a>См. также  
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Операторы сравнения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Операторы](../../../visual-basic/language-reference/operators/index.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
