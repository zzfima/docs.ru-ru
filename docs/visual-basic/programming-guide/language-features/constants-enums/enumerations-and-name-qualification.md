---
title: "Перечисления и уточнение имен (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "неоднозначные имена, перечисления"
  - "объявления, перечисления"
  - "объявления, пространства имен"
  - "объявление перечислений"
  - "объявление пространств имен, перечисления"
  - "перечисления [Visual Basic], квалификация имен"
  - "оператор Imports, объявления пространств имен"
  - "конфликты имен"
  - "имена, предотвращение конфликтов"
  - "пространства имен, объявление"
  - "конфликты имен, перечисления"
  - "конфликты имен, квалификация имен"
  - "соглашения об именовании, конфликты имен"
  - "ссылки, члены перечисления"
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Перечисления и уточнение имен (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Обычно при ссылке на член перечисления необходимо уточнить имя члена с помощью имени перечисления.  Например, при ссылке на член `Sunday` перечисления `Days` следует использовать следующий синтаксис:  
  
 [!code-vb[VbEnumsTask#18](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_1.vb)]  
  
## Использование оператора Imports  
 Чтобы не использовать полные имена, можно добавить в раздел объявлений пространства имен в коде оператор `Imports`, как показано в следующем примере:  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 Оператор `Imports` импортирует имена пространств имен из проектов и сборок, указанных в ссылке, а также из того же проекта, в котором находится модуль с этим оператором.  После добавления этого оператора можно указывать в ссылках члены перечисления без дополнительного уточнения, как показано в следующем примере:  
  
 [!code-vb[VbEnumsTask#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_3.vb)]  
  
 Организуя наборы связанных констант в перечисления, можно использовать одни и те же имена констант в различных контекстах.  Например, можно использовать одни и те же имена для констант дней недели в перечислениях `Days` и `WorkDays`.  Если с перечислениями используется оператор `Imports`, следует быть аккуратным, чтобы избежать неоднозначных ссылок.  Рассмотрим следующий пример:  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 [!code-vb[VbEnumsTask#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_4.vb)]  
  
 Если `Monday` является членом как перечисления `Days`, так и `Workdays`, этот код вызовет ошибку компиляции.  Чтобы избежать неоднозначности при ссылке на отдельную константу, уточните имя константы с помощью имени перечисления.  В приведенном ниже коде содержится ссылка на константы `Saturday` в перечислениях `Days` и `WorkDays`.  
  
 [!code-vb[VbEnumsTask#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_5.vb)]  
  
## См. также  
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [Практическое руководство. Объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Практическое руководство. Ссылка на член перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Практическое руководство. Перебор элементов перечисления в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [Практическое руководство. Определение строки, связанной со значением из перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [Когда следует использовать перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Оператор Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Оператор Imports \(пространство имен .NET и тип\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)