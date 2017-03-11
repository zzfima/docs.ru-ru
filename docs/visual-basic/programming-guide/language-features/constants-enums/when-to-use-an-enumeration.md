---
title: "Когда следует использовать перечисление (Visual Basic) | Microsoft Docs"
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
  - "перечисления [Visual Basic]"
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Когда следует использовать перечисление (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Перечисления предоставляют простой способ работы с наборами связанных констант.  Перечисление \(`Enum`\) является символическим именем для набора значений.  Перечисления обрабатываются как типы данных и их можно использовать для создания наборов констант для использования с переменными и свойствами.  
  
## Когда следует использовать перечисление  
 Когда процедура принимает ограниченный набор переменных, следует использовать перечисление.  Перечисление делает код более удобочитаемым, особенно при использовании осмысленных имен.  
  
 Преимущества использования перечисления включают:  
  
-   Уменьшение ошибок, вызванных перемещением или неправильным вводом значений.  
  
-   Упрощение будущего изменения значений.  
  
-   Облегчение чтения кода, что означает меньшую вероятность возникновения в нем ошибки.  
  
-   Обеспечение прямой совместимости.  С использованием перечислений менее вероятно, что код завершится с ошибкой, если в будущем кто\-либо изменит значения, соответствующие именам элементов.  
  
## Именование перечислений  
 Следует использовать соглашения об именах для членов перечисления.  Когда в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] встречается имя члена перечисления, может возникнуть исключение, если то же имя содержится в других библиотеках типов.  Используйте уникальный префикс для идентификации значения из приложения или компонента.  
  
 При ссылке на член перечисления необходимо предварять имя члена именем перечисления или использовать оператор `Imports`.  Дополнительные сведения см. в разделе [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
## Предопределенные перечисления  
 Для упрощения кода [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] предоставляет ряд стандартных перечислений, таких как `FirstDayOfWeek` и `MsgBoxResul`t.  Список этих перечислений см. в разделе [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md).  
  
## См. также  
 [Практическое руководство. Объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Практическое руководство. Ссылка на член перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Практическое руководство. Перебор элементов перечисления в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [Практическое руководство. Определение строки, связанной со значением из перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [Оператор Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)