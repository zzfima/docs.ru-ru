---
title: '* оператора'
ms.date: 07/20/2015
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
ms.openlocfilehash: 4f6a8ea2c5f4e23791afdfe98d2a08bf67219048
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348367"
---
# <a name="-operator-visual-basic"></a>Оператор * (Visual Basic)
Выполняет умножение двух чисел.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
number1 * number2  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`number1`|Обязательно. Произвольное числовое выражение.|  
|`number2`|Обязательно. Произвольное числовое выражение.|  
  
## <a name="result"></a>Результат  
 Результатом является произведение `number1` и `number2`.  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 Все числовые типы, включая неподписанные и типы с плавающей запятой, и `Decimal`.  
  
## <a name="remarks"></a>Примечания  
 Тип данных результата зависит от типов операндов. В следующей таблице показано, как определяется тип данных результата.  
  
|Типы данных операндов|Тип данных результата|  
|---|---|  
|Оба выражения являются целочисленными типами данных ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ulong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)).|Числовой тип данных, подходящий для типов данных `number1` и `number2`. См. таблицу "целочисленные арифметические операции" в [типах данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Оба выражения являются [десятичными](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`|  
|Оба выражения являются [одиночными](../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`|  
|Любое выражение является типом данных с плавающей запятой (`Single` или [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)), но не `Single` (Обратите внимание, `Decimal` не является типом данных с плавающей запятой).|`Double`|  
  
 Если выражение принимает значение [Nothing](../../../visual-basic/language-reference/nothing.md), оно считается нулевым.  
  
## <a name="overloading"></a>Перегрузка  
 Оператор `*` может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В этом примере оператор `*` используется для умножения двух чисел. Результатом является произведение двух операндов.  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>См. также

- [Оператор *=](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
