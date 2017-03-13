---
title: "Константы, определенные пользователем (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "циклические ссылки между константами"
  - "Const - оператор [Visual Basic], пользовательские константы"
  - "константы, циклические ссылки"
  - "константы, определяемые пользователем"
  - "область действия, константы"
  - "пользовательские константы"
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Константы, определенные пользователем (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Константа по своей сути — имя со смысловой нагрузкой, которое используется вместо неизменного числа или строки.  Константы хранят значения, которые, как видно из самого названия, остаются при выполнении приложения постоянными.  Можно использовать константы, определенные с помощью используемых элементов управления или компонентов, или создать свои собственные.  Созданные пользователем константы называются *определяемыми пользователем*.  
  
 Константы объявляют при помощи оператора `Const`, руководствуясь теми же правилами, что и при создании имени переменной.  Если `Option Strict` имеет значение `On`, необходимо явно объявлять тип константы.  
  
## Использование оператора Const  
 Оператор `Const` представляет числовые и временные показатели:  
  
 [!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]  
  
 С его помощью также определяют константы типа `String`:  
  
 [!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]  
  
 Правая сторона тождества \(`=`\) зачастую является числом или буквенной строкой, но она может быть и выражением, которое дает в итоге строку или число \(хотя это выражение не может содержать вызов функции\).  Константы можно определять, даже с помощью уже определенных констант.  
  
 [!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]  
  
## Область действия определяемых пользователем констант  
 Область действия оператора `Const` соответствует области действия переменной, объявленной в том же расположении.  Можно задать область действия одним из следующих способов:  
  
-   Чтобы создать константу, которая существует в пределах процедуры, следует объявить ее в этой процедуре.  
  
-   Чтобы создать константу, доступную всем процедурам класса, но не коду за пределами модуля, следует объявить ее в разделе объявлений класса.  
  
-   Чтобы создать константу, доступную всем членам сборки, но не внешним клиентам сборки, следует объявить ее в разделе объявлений класса с использованием ключевого слова `Friend`.  
  
-   Чтобы создать константу, доступную в рамках всего приложения, следует объявить ее в разделе объявлений класса, используя ключевое слово `Public`.  
  
 Дополнительные сведения см. в разделе [Практическое руководство. Объявление константы](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).  
  
### Профилактика циклических ссылок  
 Поскольку константы могут определяться другими константами, существует опасность случайного создания *цикла* или циклической ссылки между двумя или несколькими константами.  Цикл возникает в том случае, если две или несколько открытых констант определены друг через друга, как показано в следующем примере:  
  
 [!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]  
[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]  
  
 При возникновении цикла [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] выдает ошибку компилятора.  
  
## См. также  
 [Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md)   
 [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Константы и перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)   
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [Общие сведения о перечислениях](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Практическое руководство. Объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)