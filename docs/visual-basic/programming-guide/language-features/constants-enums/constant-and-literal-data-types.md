---
title: Типы данных констант и литералов
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: 8ebecddfab0724023c269e92c1fc5534f096bf1c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333731"
---
# <a name="constant-and-literal-data-types-visual-basic"></a>Типы данных констант и литералов (Visual Basic)
Литерал — это значение, которое выражено как само по себе, а не как значение переменной или результат выражения, например число 3 или строка "Hello". Константа — это понятное имя, которое принимает место литерала и сохраняется в программе в отличие от переменной, значение которой может измениться.  
  
 Если [параметр Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) имеет значение `Off` и [Option строго](../../../../visual-basic/language-reference/statements/option-strict-statement.md) `On`, необходимо явно объявить все константы с типом данных. В следующем примере тип данных `MyByte` явно объявлен как тип данных `Byte`:  
  
 [!code-vb[VbVbalrConstants#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#1)]  
  
 Если `Option Infer` имеет `On` или `Option Strict` `Off`, можно объявить константу без указания типа данных с помощью предложения `As`. Компилятор определяет тип константы на основе типа выражения. Числовой целочисленный литерал по умолчанию приводится к типу данных `Integer`. Типом данных по умолчанию для чисел с плавающей запятой является `Double`, а ключевые слова `True` и `False` указать константу `Boolean`.  
  
## <a name="literals-and-type-coercion"></a>Литералы и приведение типов  
 В некоторых случаях может потребоваться принудительно применить литерал к конкретному типу данных. Например, при присваивании особо большого целочисленного значения литерала переменной типа `Decimal`. Следующий пример приводит к ошибке:  
  
```vb  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 Эта ошибка возникает из представления литерала. Тип данных `Decimal` может содержать это большое значение, но литерал неявно представляется как `Long`, что не может.  
  
 Можно привести литерал к определенному типу данных двумя способами: путем добавления к нему символа типа или путем помещения его в окружающие символы. Символ типа или заключенные в него символы должны находиться непосредственно перед и/или следовать за литералом без промежуточного пробела или символов какого-либо типа.  
  
 Чтобы предыдущий пример работал, можно добавить к литералу символ типа `D`, что приводит к его представлению в виде `Decimal`:  
  
 [!code-vb[VbVbalrConstants#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#2)]  
  
 В следующем примере показано правильное использование символов типа и окружающих символов:  
  
 [!code-vb[VbVbalrConstants#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#3)]  
  
 В следующей таблице показаны окружающие символы и символы типа, доступные в Visual Basic.  
  
|Тип данных|Вложенный символ|Символ добавленного типа|  
|---|---|---|  
|`Boolean`|(нет)|(нет)|  
|`Byte`|(нет)|(нет)|  
|`Char`|"|C|  
|`Date`|#|(нет)|  
|`Decimal`|(нет)|D или @|  
|`Double`|(нет)|R или #|  
|`Integer`|(нет)|I или%|  
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
- [Инструкции. Объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Типы данных](../../../../visual-basic/language-reference/data-types/index.md)
- [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)
