---
title: "Практическое руководство. Объявление константы (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.constant"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "boolean - тип данных, объявление констант"
  - "Byte - тип данных, объявление констант"
  - "Const - оператор [Visual Basic], объявление констант"
  - "константы, объявление"
  - "Currency - тип данных, объявление констант и вариантов"
  - "типы данных [Visual Basic], константы"
  - "Date - тип данных, объявление констант"
  - "объявление констант, const - ключевое слово"
  - "Double - тип данных, объявление констант"
  - "Integer - тип данных, объявление констант"
  - "Long - тип данных, объявление констант"
  - "переменные и константы уровня модуля"
  - "модули, объявление констант"
  - "Object - тип данных, объявление констант"
  - "процедуры, объявление"
  - "Single - тип данных, объявление констант"
  - "String - тип данных, объявление констант"
  - "код Visual Basic, объявление переменных и констант"
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Практическое руководство. Объявление константы (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Для определения константы и ее значения используется оператор `Const`.  Объявляя константу, пользователь присваивает значению имеющее смысл имя.  После объявления константы ее нельзя изменить или присвоить ей новое значение.  
  
 Константа объявляется в процедуре либо в разделе объявлений модуля, класса или структуры.  Константы класса или уровня структуры являются `Private` по умолчанию, но могут также объявляться как `Public`, `Friend` `Protected` или `Protected Friend` для соответствующего уровня доступа к коду.  
  
 Константа должна иметь допустимое символьное имя \(правила идентичны правилам выбора имени для переменной\) и выражение, состоящее из числовых или строковых констант и операторов \(но не вызовов функций\).  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Объявление константы  
  
-   Следует написать объявление, которое включает спецификатор доступа, ключевое слово `Const` и выражение, как показано в следующих примерах:  
  
     [!code-vb[VbEnumsTask#8](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]  
  
     Если параметру [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) присвоено значение `Off`, а параметру [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) — значение `On`, необходимо явным образом объявить константу, задав тип данных \(`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single` или `String`\).  
  
     Если параметру `Option Infer` присвоено значение `On` или параметру `Option Strict` — значение `Off`, можно объявить константу, не задавая тип данных с предложением `As`.  Компилятор определяет тип константы по типу выражения.  Дополнительные сведения см. в разделе [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md).  
  
### Объявление константы с явно заданным типом данных  
  
-   Создайте объявление с ключевым словом `As` и явным типом данных, как в следующих примерах.  
  
     [!code-vb[VbEnumsTask#9](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]  
  
     В одной строке можно объявить несколько констант, хотя лучше читается тот код, в котором в одной строке объявлена только одна константа.  Если в одной строке объявляется несколько констант, все они должны иметь один и тот же уровень доступа \(`Public`, `Private` `Friend`, `Protected` или `Protected Friend`\).  
  
### Объявление нескольких констант в одной строке  
  
-   Разделите объявления запятой и пробелом, как показано в следующем примере:  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## См. также  
 [Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md)   
 [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Константы и перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)   
 [Общие сведения о перечислениях](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Практическое руководство. Объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)