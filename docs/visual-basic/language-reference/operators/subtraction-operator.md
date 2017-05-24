---
title: "- Operator (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Negate
- vb.-
dev_langs:
- VB
helpviewer_keywords:
- '- operator [Visual Basic]'
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator
- operators [Visual Basic], arithmetic
- subtraction operator, syntax
- arithmetic operators, subtraction
- difference operator
- math operators
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7f45094da7bc61687d9c767d25858aa214bf1978
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="--operator-visual-basic"></a>Оператор - (Visual Basic)
Возвращает разность двух числовых выражений или отрицательное значение числового выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a>Части  
 `expression1`  
 Обязательный. Произвольное числовое выражение.  
  
 `expression2`  
 Требуется, если `–` оператор вычисляет отрицательное значение. Произвольное числовое выражение.  
  
## <a name="result"></a>Результат  
 Результат — это разница между `expression1` и `expression2`, или отрицательным значением `expression1`.  
  
 Тип данных результата является числовым типом, соответствующим типам данных `expression1` и `expression2`. В таблице «Целочисленных арифметических операций» в [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 Все числовые типы. Сюда входят типы без знака и с плавающей запятой и `Decimal`.  
  
## <a name="remarks"></a>Примечания  
 При первом использовании показано в приведенном примере `–` оператор *двоичных* оператор арифметического вычитания для нахождения разности двух числовых выражений.  
  
 При втором использовании показано в приведенном примере `–` оператор *унарный* оператор отрицания отрицательного значения выражения. В этом смысле отрицание представляет собой замену знака `expression1` , чтобы результат был положительным, если `expression1` является отрицательным.  
  
 Если выражение [ничего](../../../visual-basic/language-reference/nothing.md), `–` оператор интерпретирует его как ноль.  
  
> [!NOTE]
>  `–` Оператор может быть *перегруженные*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `–` оператор вычисляет и возвращает разность двух чисел, а затем меняет знак числа.  
  
 [!code-vb[VbVbalrOperators&#10;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]  
  
 После выполнения этих инструкций `binaryResult` содержит значение 124,45 и `unaryResult` содержит значение – 334,90.  
  
## <a name="see-also"></a>См. также  
 [-= Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
 [арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Приоритет операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)

