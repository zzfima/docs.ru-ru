---
title: "Типы данных констант и литералов (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "константы, объявление"
  - "типы данных [Visual Basic], объявление"
  - "объявления, типы данных"
  - "объявление констант, типы данных литералов"
  - "явные объявления"
  - "литералы, приведение типов данных"
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Типы данных констант и литералов (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Литерал представляет собой значение, выраженное самостоятельно, а не в качестве значения переменной или результата вычисления выражения, например число 3 или строка "Hello".  Константа представляет собой значимое имя, замещающее литерал и сохраняющее одно и то же значение на протяжении всей программы в отличие от переменных, которые могут изменяться.  
  
 Если параметру [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) присвоено значение `Off`, а параметру [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) — значение `On`, необходимо явно объявить все константы с использованием типа данных.  В следующем примере тип данных константы `MyByte` явным образом объявлен как `Byte`:  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 Если параметру `Option Infer` присвоено значение `On` или параметру `Option Strict` — значение `Off`, можно объявить константу, не задавая тип данных с предложением `As`.  Компилятор определяет тип константы по типу выражения.  Целочисленный литерал по умолчанию приводится к типу данных `Integer`.  По умолчанию для чисел с плавающей запятой используется тип данных `Double`, а ключевые слова `True` и `False` определяют константу типа `Boolean`.  
  
## Литералы и приведение типов  
 В некоторых случаях требуется выполнить принудительное приведение литерала к определенному типу данных, например, при назначении особо большого целочисленного значения литерала переменной типа `Decimal`.  В результате следующего примера получается ошибка:  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 Эта ошибка появляется из\-за представления литерала.  Тип данных `Decimal` может содержать значение такой величины, но литерал неявным образом представлен как тип `Long`, который не имеет такой возможности.  
  
 Приведение литерала к определенному типу данных осуществляется двумя способами: путем добавления к литералу символа типа либо путем заключения его между окружающими символами.  Символ типа или окружающие символы должны непосредственно предшествовать литералу и\/или следовать за ним без каких\-либо промежуточных пробелов или символов.  
  
 Чтобы предыдущий пример работал, добавьте к литералу символ типа `D`, чтобы он был представлен как `Decimal`:  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 В следующем примере показано правильное использование символов типа и окружающих символов:  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 В приведенной ниже таблице показаны окружающие символы и символы типов, доступные в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
||||  
|-|-|-|  
|Тип данных|Окружающий символ|Добавленный символ типа|  
|`Boolean`|\(нет\)|\(нет\)|  
|`Byte`|\(нет\)|\(нет\)|  
|`Char`|"|C|  
|`Date`|\#|\(нет\)|  
|`Decimal`|\(нет\)|D или @|  
|`Double`|\(нет\)|R или \#|  
|`Integer`|\(нет\)|I или %|  
|`Long`|\(нет\)|L или &|  
|`Short`|\(нет\)|S|  
|`Single`|\(нет\)|F или \!|  
|`String`|"|\(нет\)|  
  
## См. также  
 [Константы, определенные пользователем](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)   
 [Практическое руководство. Объявление константы](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)   
 [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Оператор Option Explicit](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Общие сведения о перечислениях](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Практическое руководство. Объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)