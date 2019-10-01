---
title: '- Оператор (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
ms.openlocfilehash: 5f6b6b67e2999d380cfca078a43162b3e1db2206
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701304"
---
# <a name="--operator-visual-basic"></a>Оператор - (Visual Basic)
Возвращает разность между двумя числовыми выражениями или отрицательным значением числового выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
expression1 – expression2
```
  
или

```vb  
–expression1  
```  
  
## <a name="parts"></a>Части  
 `expression1`  
 Обязательный. Произвольное числовое выражение.  
  
 `expression2`  
 Требуется, если оператор `–` не вычисляет отрицательное значение. Произвольное числовое выражение.  
  
## <a name="result"></a>Результат  
 Результатом является разница между `expression1` и `expression2` или отрицательным значением `expression1`.  
  
 Тип данных result является числовым типом, подходящим для типов данных `expression1` и `expression2`. См. таблицу "целочисленные арифметические операции" в [типах данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 все числовые типы. К ним относятся типы без знака и тип с плавающей запятой `Decimal`и.  
  
## <a name="remarks"></a>Примечания  
 При первом использовании, показанном в приведенном выше синтаксисе, оператор `–` является *бинарным* арифметическим оператором вычитания для разности двух числовых выражений.  
  
 Во втором описании синтаксиса, показанного ранее, оператор `–` является *унарным* оператором отрицания для отрицательного значения выражения. В этом смысле отрицание состоит из обратного знака `expression1`, чтобы результат был положительным, если `expression1` имеет отрицательное значение.  
  
 Если любое из выражений имеет значение [Nothing](../../../visual-basic/language-reference/nothing.md), оператор `–` обрабатывает его как ноль.  
  
> [!NOTE]
> Оператор `–` можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `–` используется для вычисления и возврата разницы между двумя числами, а затем для отрицания числа.  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 После выполнения этих инструкций `binaryResult` содержит 124,45, а `unaryResult` содержит – 334,90.  
  
## <a name="see-also"></a>См. также

- [Оператор-= (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
