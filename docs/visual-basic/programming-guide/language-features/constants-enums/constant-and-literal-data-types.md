---
title: Типы данных констант и литералов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: 8d110ec17bcdb03f339d779b2950ba56d77957cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="constant-and-literal-data-types-visual-basic"></a>Типы данных констант и литералов (Visual Basic)
Литерал — это значение, выраженное самостоятельно, а не как значение переменной или результата выражения, например число 3 или строка «Hello». Константа — это понятное имя, которое занимает место литерал и сохраняет это же значение для программы, в отличие от переменной, значение которого может измениться.  
  
 Когда [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) — `Off` и [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) — `On`, вы должны явно объявить все константы с типом данных. В следующем примере тип данных `MyByte` явно объявляется как тип данных `Byte`:  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 Когда `Option Infer` — `On` или `Option Strict` — `Off`, можно объявить константу без указания типа данных с `As` предложения. Компилятор определяет тип константы из типа выражения. Целочисленный литерал приведен по умолчанию для `Integer` тип данных. Для чисел с плавающей запятой имеет тип данных по умолчанию `Double`, а также ключевые слова `True` и `False` укажите `Boolean` константой.  
  
## <a name="literals-and-type-coercion"></a>Литералы и приведение типов  
 В некоторых случаях может потребоваться принудительно литерала к определенному типу данных; Например, при назначении особенно большой целочисленное литеральное значение для переменной типа `Decimal`. Следующий пример приводит к ошибке:  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 Эта ошибка возникает из представления литерала. `Decimal` Тип данных может содержать значение такой величины, но литерал неявно представлен как `Long`, которые могут.  
  
 Приведение литерала к определенному типу данных двумя способами: путем добавления к литералу символа типа, или путем помещения его в пределах содержащего его символов. Символ типа или окружающие символы должны непосредственно предшествовать и/или выполните литерал без промежуточных пробелов и символов любого типа.  
  
 Чтобы предыдущий пример работал, можно добавить `D` знак в литерал, что приведет к представляется в виде типа `Decimal`:  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 В следующем примере показано правильное использование символов типа и окружающих символов:  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 Следующей таблице показаны окружающие символы и символы типов, доступные в Visual Basic.  
  
|Тип данных|Внешний символ|Добавленный символ типа|  
|---|---|---|  
|`Boolean`|(нет)|(нет)|  
|`Byte`|(нет)|(нет)|  
|`Char`|"|В|  
|`Date`|#|(нет)|  
|`Decimal`|(нет)|D или @|  
|`Double`|(нет)|R или #|  
|`Integer`|(нет)|I или %|  
|`Long`|(нет)|L или &|  
|`Short`|(нет)|S|  
|`Single`|(нет)|F или!|  
|`String`|"|(нет)|  
  
## <a name="see-also"></a>См. также  
 [Константы, определенные пользователем](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)  
 [Практическое руководство. Объявление константы](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)  
 [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Оператор Option Explicit](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [Общие сведения о перечислениях](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [Как: объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)
