---
title: Оператор \ (Visual Basic)
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
ms.openlocfilehash: 7ce7bdaa2bcbf2ba67f24c7e129f8f9a03a28c52
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57201915"
---
# <a name="-operator-visual-basic"></a>Оператор \ (Visual Basic)
Делит два числа и возвращает целочисленный результат.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
expression1 \ expression2  
```  
  
## <a name="parts"></a>Части  
 `expression1`  
 Обязательный. Произвольное числовое выражение.  
  
 `expression2`  
 Обязательный. Произвольное числовое выражение.  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 Все числовые типы, включая типы без знака и с плавающей запятой и `Decimal`.  
  
## <a name="result"></a>Результат  
 Результатом является целочисленное частное `expression1` деления на `expression2`, котором остаток отбрасывается и возвращается только целая часть результата. Этот процесс называется *усечение*.  
  
 Тип данных результата является числовым типом, соответствующим типам данных `expression1` и `expression2`. См. в таблицах «Целочисленных арифметических операций» [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
 [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) возвращает полное частное, в котором сохраняется остаток в дробной части.  
  
## <a name="remarks"></a>Примечания  
 Перед выполнением деления, Visual Basic пытается преобразовать любое с плавающей запятой числовое выражение, чтобы `Long`. Если `Option Strict` является `On`, возникает ошибка компилятора. Если `Option Strict` — `Off`, <xref:System.OverflowException> возможно в том случае, если значение находится вне диапазона [тип данных Long](../../../visual-basic/language-reference/data-types/long-data-type.md). Преобразование в `Long` также является *банковское округление*. Дополнительные сведения см. в разделе «Дробных частей» в [функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Если `expression1` или `expression2` принимает значение [ничего не](../../../visual-basic/language-reference/nothing.md), он интерпретируется как ноль.  
  
## <a name="attempted-division-by-zero"></a>Попытка деления на ноль  
 Если `expression2` результатом которого является ноль, `\` вызывает оператор <xref:System.DivideByZeroException> исключение. Это справедливо для всех числовых типов данных операндов.  
  
> [!NOTE]
>  `\` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `\` оператора для выполнения операции деления целое число. Результатом является целое число, представляющее целочисленное частное двух операндов, а остальное удаляются.  
  
 [!code-vb[VbVbalrOperators#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#18)]  
  
 Выражения в предыдущем примере возвращают значения 2, 3, 33 и -22 соответственно.  
  
## <a name="see-also"></a>См. также
- [\\= Оператор](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [/ Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
