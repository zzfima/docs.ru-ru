---
title: "Типы данных результатов оператора (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "типы данных [Visual Basic], типы данных результатов оператора"
  - "типы данных [Visual Basic], диапазоны"
  - "типы данных результатов оператора"
  - "операторы [Visual Basic], типы данных"
  - "операторы [Visual Basic], типы данных результата"
  - "типы данных результата"
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Типы данных результатов оператора (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] определяет тип данных результата операции, основанной на типах данных операндов.  В некоторых случаях он может быть типом данных с диапазоном больше, чем у любого из операндов.  
  
## Диапазоны типов данных  
 Диапазоны соответствующих типов данных, в порядке от наименьшего к наибольшему, следующие:  
  
-   [Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md) — два возможных значения  
  
-   [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md) — 256 возможных целых значений  
  
-   [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md) — 65,536 \(6,5...E\+4\) возможных целых значений  
  
-   [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md),  [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) — 4 294 967 296 \(4.2...E\+9\) возможных целых значений  
  
-   [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md) — 18 446 744 073 709 551 615 \(1.8...E\+19\) возможных целых значений  
  
-   [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) — 1,5...E\+29 возможных целых значений, максимальный диапазон 7,9...E\+28 \(абсолютное значение\)  
  
-   [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) — максимальный диапазон 3.4...E\+38 \(абсолютное значение\)  
  
-   [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) — максимальный диапазон 1.7...E\+308 \(абсолютное значение\)  
  
 Дополнительные сведения о типах данных [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] содержатся в разделе [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
 Если операнд вычисляется для [Nothing](../../../visual-basic/language-reference/nothing.md), арифметические операторы [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] рассматривают его как ноль.  
  
## Десятичная система исчисления  
 Обратите внимание, что тип данных [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) не является ни числом с плавающей запятой, ни целым числом.  
  
 Если один операнд `+`, `–`, `*`, `/`, или операция `Mod` является `Decimal`, a другой не является `Single` или `Double`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] расширяет другой операнд до `Decimal`.  Он выполняет операцию в `Decimal`, и тип данных результата является `Decimal`.  
  
## Арифметика чисел с плавающей запятой  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выполняет большинство операций арифметики чисел с плавающей запятой в [Double](../../../visual-basic/language-reference/data-types/double-data-type.md), который является наиболее эффективным типом данных для таких операций.  Однако если один операнд является [Singlе](../../../visual-basic/language-reference/data-types/single-data-type.md), а другой не является `Double`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выполнит операцию в `Single`.  Он при необходимости расширяет каждый операнд до соответствующего типа данных перед операцией, и результат обладает этим типом данных.  
  
### Операторы \/ и ^  
 Оператор `/` определяется только для типов данных [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) и [Double](../../../visual-basic/language-reference/data-types/double-data-type.md).  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] при необходимости расширяет каждый операнд до соответствующего типа данных перед операцией, а результат обладает этим типом данных.  
  
 В следующей таблице показаны типы данных результата для оператора `/`.  Обратите внимание, что эта таблица является симметричной; для данной комбинации типов данных операнда тип данных результата одинаков независимо от порядка операндов.  
  
||||||  
|-|-|-|-|-|  
||`Decimal`|`Single`|`Double`|Любой целочисленный тип|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|Любой целочисленный тип|Decimal|Single|Double|Double|  
  
 Оператор `^` определяется только для типа данных `Double`.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] по мере необходимости расширяет каждый операнд в `Double` перед выполнением операции, и результирующий тип данных всегда `Double`.  
  
## Целочисленные арифметические операции  
 Тип данных результата целочисленной операции зависит от типов данных операндов.  Как правило, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] использует следующие политики для определения типа данных результата:  
  
-   Если оба операнда бинарного оператора имеют одинаковый тип данных, результат обладает этим типом данных.  Исключением является тип `Boolean`, который принудительно преобразован в `Short`.  
  
-   Если беззнаковый операнд участвует в операции со знаковым операндом, результат имеет знаковый тип с диапазоном как минимум равным диапазону любого из операндов.  
  
-   В противном случае результат обычно имеет наибольший из двух типов данных операндов.  
  
 Обратите внимание, что тип данных результата может не совпадать с типом данных любого из операндов.  
  
> [!NOTE]
>  Тип данных результата не всегда обладает размером, достаточным для хранения всех возможных значений результата операции.  Исключение <xref:System.OverflowException> возникает, если значение слишком велико для типа данных результата.  
  
### Унарные операторы \+ и –  
 Следующая таблица показывает типы данных результата для двух унарных операторов, `+` и `–`.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|Унарный `+`|Short|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|Унарный `–`|Short|SByte|Short|Short|Integer|Integer|Long|Long|Decimal|  
  
### Операторы \<\< и \>\>  
 В следующей таблице приведены типы данных результата для двух операторов поразрядного сдвига, `<<` и `>>`.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] рассматривает каждый оператор поразрядного сдвига, как унарный оператор для операнда из левой части \(битовая комбинация, которая будет сдвинута\).  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
  
 Если операнд из левой части является `Decimal`, `Single` `Double` или `String`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] попытается преобразовать его в `Long` перед операцией, и тип данных результата будет `Long`.  Операнд из правой части \(число битовых позиций для сдвига\) должен быть типа `Integer`, или типа, который расширяется до `Integer`.  
  
### Двоичные операторы \+, –, \* и Mod  
 Следующая таблица демонстрирует типы данных результата бинарных операторов `+` и`–` и операторов `*` и `Mod`.  Обратите внимание, что эта таблица является симметричной; для данной комбинации типов данных операнда тип данных результата одинаков независимо от порядка операндов.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Integer|Integer|Long|Long|Decimal|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|Long|Long|Decimal|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|Long|Long|Decimal|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Decimal|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Decimal|  
|`ULong`|Decimal|Decimal|ULong|Decimal|ULong|Decimal|ULong|Decimal|ULong|  
  
### Оператор \\  
 В следующей таблице показаны типы данных результата для оператора `\`.  Обратите внимание, что эта таблица является симметричной; для данной комбинации типов данных операнда тип данных результата одинаков независимо от порядка операндов.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|Long|Long|Long|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Если один из операндов оператора `\` является [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) или [Double](../../../visual-basic/language-reference/data-types/double-data-type.md), [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] попытается преобразовать его в [Long](../../../visual-basic/language-reference/data-types/long-data-type.md) перед операцией, и типом данных результата будет `Long`.  
  
## Реляционные и побитовые сравнения  
 Типом данных результата реляционной операции \(`=` `<>` `<`, `>`, `<=`, `>=`\) всегда является `Boolean`[Тип данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md).  То же самое верно для логических операций \(`And` `AndAlso` `Not`, `Or`, `OrElse`, `Xor`\) на операндах типа `Boolean`.  
  
 Тип данных результата побитовой логической операции зависит от типов данных операндов.  Обратите внимание, что `AndAlso` и `OrElse` определяются только для `Boolean`, и [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] при необходимости преобразует каждый операнд в `Boolean` перед выполнением операции.  
  
### Операторы \=, \<\>, \<, \>, \<\=, и \>\=  
 Если оба операнда являются `Boolean`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] считает, что значение `True` меньше, чем `False`.  При сравнении числового типа с `String`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] попытается преобразовать `String` в `Double` перед выполнением операции.  Операнд типа `Char` или `Date` можно сравнивать только с другим операндом с тем же типом данных.  Тип данных результата всегда `Boolean`.  
  
### Поразрядный оператор Not  
 В следующей таблице показаны типы данных результата для побитового \(поразрядного\) оператора `Not`.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Boolean|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
  
 При операнде `Decimal`, `Single` `Double` или `String`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] попытается преобразовать его в `Long` перед выполнением операции, и тип данных результата будет `Long`.  
  
### Поразрядные операторы And, Or и Xor  
 Следующая таблица показывает типы данных результата для побитовых операторов `And` и `Or` и `Xor`.  Обратите внимание, что эта таблица является симметричной; для данной комбинации типов данных операнда тип данных результата одинаков независимо от порядка операндов.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Boolean|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|Long|Long|Long|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Операнды `Decimal`, `Single` `Double` или `String`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] попытается преобразовать в `Long` перед выполнением операции, и тип данных результата будет тот же, как при операнде типа `Long`.  
  
## Прочие операторы  
 Оператор `&` определяется только для объединения операндов `String`.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] по мере необходимости преобразует каждый операнд в `String` перед выполнением операции, и результирующий тип данных всегда `String`.  Все преобразования в `String` для оператора `&` считаются расширяющимся, даже если для параметра `Option Strict` установлено значение `On`.  
  
 Операторы `Is` и `IsNot` требуют, чтобы оба операнда были ссылочного типа.  Выражение `TypeOf`...`Is` требует, чтобы первый операнд был ссылочного типа, а второй операнд являлся именем типа данных.  Во всех этих случаях результат типа данных — `Boolean`.  
  
 Оператор `Like` определяется только для подбора шаблонов операндов `String`.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] пытается по мере необходимости преобразовывать каждый операнд в `String` перед выполнением операции.  Тип данных результата всегда `Boolean`.  
  
## См. также  
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Операторы сравнения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Операторы](../../../visual-basic/language-reference/operators/index.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)