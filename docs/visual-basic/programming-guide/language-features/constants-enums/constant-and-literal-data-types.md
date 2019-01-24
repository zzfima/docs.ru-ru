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
ms.openlocfilehash: d85ff343587e8689a4859a09c8dc80932374a82e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498652"
---
# <a name="constant-and-literal-data-types-visual-basic"></a>Типы данных констант и литералов (Visual Basic)
Литерал — это значение, которое выражается само по себе, а не как значение переменной или результат выражения, например число 3 или строка «Hello». Константа представляет собой значимое имя, которое занимает место литерал и хранит это же значение для программы, в отличие от переменной, значения которых могут меняться.  
  
 Когда [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) — `Off` и [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) является `On`, необходимо объявить все константы явным образом с типом данных. В следующем примере, тип данных `MyByte` явно объявлен как тип данных `Byte`:  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 При `Option Infer` — `On` или `Option Strict` — `Off`, можно объявить без указания типа данных с константой `As` предложение. Компилятор определяет тип константы из типа выражения. По умолчанию для приводится целочисленный литерал `Integer` тип данных. Тип данных по умолчанию для чисел с плавающей запятой — `Double`и ключевые слова `True` и `False` укажите `Boolean` константы.  
  
## <a name="literals-and-type-coercion"></a>Литералы и приведение типов  
 В некоторых случаях может потребоваться принудительно литерала к определенному типу данных; Например, при назначении особенно большой целочисленный литерал переменной типа `Decimal`. Следующий пример приводит к ошибке:  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 Эта ошибка возникает из представления литерала. `Decimal` Тип данных может содержать значение такого размера, но литерал неявно представлен как `Long`, какие нельзя.  
  
 Приведение литерала к определенному типу данных двумя способами: путем добавления к литералу символа типа, или путем помещения его в окружающие символы. Символ типа или окружающие символы необходимо сразу же перед и/или выполните литерала, без промежуточных пробелов или символов любого типа.  
  
 Чтобы предыдущий пример работал, можно добавить `D` знак в литерал, что приводит к его в виде типа `Decimal`:  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 В следующем примере показано правильное использование символов типа и окружающих символов:  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 Показано в следующей таблице окружающие символы и символы типов, доступные в Visual Basic.  
  
|Тип данных|Заключения символа|Добавленный символ типа|  
|---|---|---|  
|`Boolean`|(нет)|(нет)|  
|`Byte`|(нет)|(нет)|  
|`Char`|"|В|  
|`Date`|#|(нет)|  
|`Decimal`|(нет)|D или @|  
|`Double`|(нет)|R или #|  
|`Integer`|(нет)|Я или %|  
|`Long`|(нет)|L или &|  
|`Short`|(нет)|S|  
|`Single`|(нет)|F или!|  
|`String`|"|(нет)|  
  
## <a name="see-also"></a>См. также
- [Константы, определенные пользователем](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)
- [Практическое руководство. Объявление константы](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)
- [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Оператор Option Explicit](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Общие сведения о перечислениях](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [Практическое руководство. Объявления перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Типы данных](../../../../visual-basic/language-reference/data-types/index.md)
- [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)
