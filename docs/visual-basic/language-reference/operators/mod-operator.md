---
title: Оператор Mod (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5464b57c993e5703c09529b527a7bc714e045870
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="mod-operator-visual-basic"></a>Оператор Mod (Visual Basic)
Делит два числа и возвращает только остаток.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a>Части  
 `number1`  
 Обязательный. Произвольное числовое выражение.  
  
 `number2`  
 Обязательный. Произвольное числовое выражение.  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 Все числовые типы. Сюда входят типы без знака и с плавающей запятой и `Decimal`.  
  
## <a name="result"></a>Результат  
 Результат — остаток после `number1` делится на `number2`. Например, выражение `14 Mod 4` равно 2.  
  
## <a name="remarks"></a>Примечания  
 Если параметр `number1` или `number2` имеет значение с плавающей запятой с плавающей запятой остаток от деления возвращается. Тип данных результата — наименьший тип данных, который может содержать все возможные значения, которые являются результатом деления с типами данных `number1` и `number2`.  
  
 Если `number1` или `number2` равен [ничего](../../../visual-basic/language-reference/nothing.md), интерпретируется как ноль.  
  
 Связанные операторы включают в себя следующее:  
  
-   [\ Оператора (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) возвращает целочисленное частное от деления. Например, выражение `14 \ 4` равен 3.  
  
-   [-Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) возвращает полное частное, включая остаток, как число с плавающей запятой. Например, выражение `14 / 4` равно 3.5.  
  
## <a name="attempted-division-by-zero"></a>Попытка деления на ноль  
 Если `number2` оказался равным нулю, поведение `Mod` оператор зависит от типа данных операндов. Вызывает целочисленного деления <xref:System.DivideByZeroException> исключение. Возвращает деления с плавающей запятой <xref:System.Double.NaN>.  
  
## <a name="equivalent-formula"></a>Эквивалентная формула  
 Выражение `a Mod b` является эквивалентом для любой из следующих формул:  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a>С плавающей запятой неточности  
 При работе с числами с плавающей запятой, помните, что они не всегда имеют точное представление в памяти. Это может привести к непредвиденным результатам определенных операций, таких как значение сравнения и `Mod` оператор. Дополнительные сведения см. в разделе [Устранение неполадок типы данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="overloading"></a>Перегрузка  
 `Mod` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение. Если код применяет `Mod` к экземпляру класса или структуры, включающей такие перегрузки, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Mod` оператор деления двух чисел и возвращает только остаток. Если оба числа с плавающей запятой, результатом является число с плавающей запятой, представляющее остаток.  
  
 [!code-vb[VbVbalrOperators#31](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано возможная неточность операндов с плавающей запятой. В первом операторе операнды имеют `Double`, и 0,2 является периодической бесконечной двоичной дробью, сохраненное значение 0,20000000000000001. Во втором операторе знак типа литерала `D` приводит оба операнда для `Decimal`, и 0,2 имеет точное представление.  
  
 [!code-vb[VbVbalrOperators#32](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_2.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [\ Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
