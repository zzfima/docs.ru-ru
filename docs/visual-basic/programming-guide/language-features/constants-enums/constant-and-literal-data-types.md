---
title: "Типы данных констант и литералов (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declaring constants, literal data types
- data types [Visual Basic], declaring
- constants, declaring
- explicit declarations
- literals, coercing data type
- declarations, data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 22ad31415ab560b7fd0180a6dadd6d2dcd7ec77a
ms.lasthandoff: 03/13/2017

---
# <a name="constant-and-literal-data-types-visual-basic"></a>Типы данных констант и литералов (Visual Basic)
Литерал — это значение, выраженное самостоятельно, а не как значение переменной или результата выражения, например число 3 или строка «Hello». Константа представляет собой значимое имя, занимает место литерал и сохраняет этот же значение на протяжении всей программы, в отличие от переменной, значение которого может измениться.  
  
 Когда [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) — `Off` и [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) — `On`, можно явно объявить все константы с типом данных. В следующем примере тип данных `MyByte` явно объявляется как тип данных `Byte`:  
  
 [!code-vb[VbVbalrConstants&#1;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 Когда `Option Infer` — `On` или `Option Strict` — `Off`, можно объявить константу без указания типа данных с `As` предложения. Компилятор определяет тип константы из типа выражения. Целочисленный литерал приведен по умолчанию для `Integer` тип данных. Тип данных по умолчанию для чисел с плавающей запятой — `Double`и ключевые слова `True` и `False` укажите `Boolean` константой.  
  
## <a name="literals-and-type-coercion"></a>Литералы и приведение типов  
 В некоторых случаях может потребоваться принудительно литерала к определенному типу данных. Например, при назначении особенно большого целочисленного значения литерала переменной типа `Decimal`. Следующий пример приводит к ошибке:  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 Эта ошибка возникает из представления литерала. `Decimal` Тип данных может содержать значение такой величины, но литерал неявно представлен как `Long`, который невозможно.  
  
 Приведение литерала к определенному типу данных двумя способами: путем добавления к литералу символа типа либо путем заключения его между окружающими символами. Символ типа или окружающие символы должны непосредственно предшествовать и/или выполните литерал без промежуточных пробелов или знаков любого типа.  
  
 Чтобы предыдущий пример работал, добавьте `D` введите знак в литерал, вследствие чего он представлен как `Decimal`:  
  
 [!code-vb[VbVbalrConstants&#2;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 В следующем примере показано правильное использование символов типа и окружающих символов:  
  
 [!code-vb[VbVbalrConstants&#3;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 В следующей таблице показаны окружающие символы и тип символов, доступных в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
|Тип данных|Окружающий символ|Добавленный символ типа|  
|---|---|---|  
|`Boolean`|(нет)|(нет)|  
|`Byte`|(нет)|(нет)|  
|`Char`|"|C|  
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
 [Практическое руководство: объявление константы](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)   
 [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Оператор Option Explicit](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Общие сведения о перечислениях](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Практическое руководство: объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)
