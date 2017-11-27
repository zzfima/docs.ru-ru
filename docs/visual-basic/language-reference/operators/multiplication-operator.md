---
title: "* Оператор (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 450d728e44ef5639d75369e05b47cb3009b4d769
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>Оператор * (Visual Basic)
Выполняет умножение двух чисел.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
number1 * number2  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`number1`|Обязательный. Произвольное числовое выражение.|  
|`number2`|Обязательный. Произвольное числовое выражение.|  
  
## <a name="result"></a>Результат  
 Результат — это совокупность `number1` и `number2`.  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 Все числовые типы, включая типы без знака и с плавающей запятой и `Decimal`.  
  
## <a name="remarks"></a>Примечания  
 Тип данных результата зависит от типов операндов. Следующая таблица показывает, как определяется тип данных результата.  
  
|Типы данных операндов|Тип данных результата|  
|---|---|  
|Оба выражения имеют целочисленные типы данных ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [байтов](../../../visual-basic/language-reference/data-types/byte-data-type.md), [короткие](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [целое](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [длинные](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|Числовой тип данных для типов данных `number1` и `number2`. В таблице «Целочисленных арифметических операций» в [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Оба выражения имеют [десятичное число](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`|  
|Оба выражения имеют [один](../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`|  
|Любое из выражений имеет тип данных с плавающей запятой (`Single` или [двойные](../../../visual-basic/language-reference/data-types/double-data-type.md)), но не оба `Single` (Примечание `Decimal` не является типом данных с плавающей запятой)|`Double`|  
  
 Если результатом выражения [ничего](../../../visual-basic/language-reference/nothing.md), интерпретируется как ноль.  
  
## <a name="overloading"></a>Перегрузка  
 `*` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `*` оператор для умножения двух чисел. Результатом является произведение двух операндов.  
  
 [!code-vb[VbVbalrOperators#4](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-operator_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор *=](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)  
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
