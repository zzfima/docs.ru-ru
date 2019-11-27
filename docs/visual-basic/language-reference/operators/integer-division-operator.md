---
title: Оператор \
ms.date: 07/20/2015
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
ms.openlocfilehash: 2b4cca99ed54195162530bb8eb950bd251bfbff9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347122"
---
# <a name="-operator-visual-basic"></a>Оператор \ (Visual Basic)
Делит два числа и возвращает целочисленный результат.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
expression1 \ expression2  
```  
  
## <a name="parts"></a>Части  
 `expression1`  
 Обязательно. Произвольное числовое выражение.  
  
 `expression2`  
 Обязательно. Произвольное числовое выражение.  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 Все числовые типы, включая неподписанные и типы с плавающей запятой, и `Decimal`.  
  
## <a name="result"></a>Результат  
 Результатом является целочисленное частное `expression1`, разделенное на `expression2`, которое отклоняет остаток и оставляет только целую часть. Это называется *усечением*.  
  
 Тип данных result является числовым типом, подходящим для типов данных `expression1` и `expression2`. См. таблицу "целочисленные арифметические операции" в [типах данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
 [Оператор/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) возвращает полное частное, сохраняющее остаток в дробной части.  
  
## <a name="remarks"></a>Примечания  
 Перед выполнением деления Visual Basic пытается преобразовать любое числовое выражение с плавающей запятой в `Long`. Если `Option Strict` `On`, возникает ошибка компилятора. Если `Option Strict` `Off`, возможно <xref:System.OverflowException>, если значение выходит за пределы диапазона [данных типа Long](../../../visual-basic/language-reference/data-types/long-data-type.md). Преобразование в `Long` также регулируется *округлением банка*. Дополнительные сведения см. в разделе "Дробные части" [функций преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Если `expression1` или `expression2` принимает значение [Nothing](../../../visual-basic/language-reference/nothing.md), оно считается нулевым.  
  
## <a name="attempted-division-by-zero"></a>Попыток деления на ноль  
 Если `expression2` равен нулю, оператор `\` выдает исключение <xref:System.DivideByZeroException>. Это справедливо для всех числовых типов данных операндов.  
  
> [!NOTE]
> Оператор `\` может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `\` используется для выполнения целочисленного деления. Результатом является целое число, представляющее целочисленное частное двух операндов с отброшенным остатком.  
  
 [!code-vb[VbVbalrOperators#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#18)]  
  
 Выражения в предыдущем примере возвращают значения 2, 3, 33 и-22 соответственно.  
  
## <a name="see-also"></a>См. также

- [Оператор \\=](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [Оператор/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
