---
title: Оператор ^ (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponention
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: 426c3e9913dadda1091f4ba53c66c6b65e40e768
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-visual-basic"></a>Оператор ^ (Visual Basic)
Возводит число в степень другого числа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
number ^ exponent  
```  
  
## <a name="parts"></a>Части  
 `number`  
 Обязательно. Произвольное числовое выражение.  
  
 `exponent`  
 Обязательно. Произвольное числовое выражение.  
  
## <a name="result"></a>Результат  
 В результате `number` степени `exponent`, всегда как `Double` значение.  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 `Double`. Операнды любого другого типа преобразуются в `Double`.  
  
## <a name="remarks"></a>Примечания  
 Visual Basic всегда выполняет возведение в степень, в [тип данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md).  
  
 Значение `exponent` может быть дробным, отрицательным или оба.  
  
 При выполнении нескольких возведения в степень в одном выражении `^` оператор выполняется при его обнаружении в направлении слева направо.  
  
> [!NOTE]
>  `^` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `^` оператор для возведения числа в степень экспоненты. Результатом является первый операнд, возведенное в степень второго.  
  
 [!code-vb[VbVbalrOperators#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-operator_1.vb)]  
  
 В предыдущем примере получаются следующие результаты:  
  
 `exp1` имеет значение 4 (2 в квадрате).  
  
 `exp2` имеет значение 19683 (3 в кубе, затем полученное значение в кубе).  
  
 `exp3` устанавливается в 125 (5 в кубе).  
  
 `exp4` имеет значение (-5 в четвертой степени) 625.  
  
 `exp5` имеет значение 2 (кубический корень из 8).  
  
 `exp6` имеет значение 0,5 (1.0, разделенное на кубический корень из 8).  
  
 Обратите внимание на важность круглых скобок в выражениях в предыдущем примере. Из-за *приоритета операторов*, Visual Basic обычно выполняет `^` оператор перед любыми другими, даже унарный `–` оператор. Если `exp4` и `exp6` были рассчитаны без скобок, они имели бы следующие результаты:  
  
 `exp4 = -5 ^ 4` будет вычисляться как – (5 в четвертой степени), что приведет к появлению-625.  
  
 `exp6 = 8 ^ -1.0 / 3.0` будет вычисляться как (8-1 или 0,125) разделить на 3,0, что привело бы к равно 0,041666666666666666666666666666667.  
  
## <a name="see-also"></a>См. также  
 [Оператор ^=](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
