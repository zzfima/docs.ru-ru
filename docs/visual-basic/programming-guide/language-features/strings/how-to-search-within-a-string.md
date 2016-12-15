---
title: "Практическое руководство. Поиск в строке (Visual Basic) | Microsoft Docs"
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
  - "примеры [Visual Basic], строки"
  - "строки [Visual Basic], поиск"
  - "строки [Visual Basic], поиск"
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Поиск в строке (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В этом примере вызывается метод <xref:System.String.IndexOf%2A> объекта <xref:System.String> для отображения индекса первого вхождения подстроки.  
  
## Пример  
 [!code-vb[VbVbalrStrings#71](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-search-within-a-string_1.vb)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Оператор `Imports`, задающий пространство имен <xref:System>.  Дополнительные сведения см. в разделе [Оператор Imports \(пространство имен .NET и тип\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## Отказоустойчивость  
 Метод <xref:System.String.IndexOf%2A> сообщает расположение первого символа первого вхождения подстроки.  Индекс начинается с нуля; это означает, что номер первого знака строки равен нулю.  
  
 Если <xref:System.String.IndexOf%2A> не удается найти подстроку, возвращается значение "\-1".  
  
 В методе <xref:System.String.IndexOf%2A> учитывается регистр и используется текущий язык и региональные параметры.  
  
 В целях оптимального управления ошибками можно заключить строку поиска в блок `Try` конструкции [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## См. также  
 <xref:System.String.IndexOf%2A>   
 [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)   
 [Строки](../../../../visual-basic/programming-guide/language-features/strings/index.md)