---
title: "Практическое руководство. Преобразование шестнадцатеричных строк в числа (Visual Basic) | Microsoft Docs"
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
  - "десятичные знаки, шестнадцатеричные"
  - "примеры [Visual Basic], преобразование строк"
  - "шестнадцатеричные, десятичные знаки"
  - "числа, шестнадцатеричные"
  - "преобразование строк, шестнадцатеричные знаки в числа"
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Преобразование шестнадцатеричных строк в числа (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Этот пример преобразует шестнадцатеричную строку в целое число, используя метод <xref:System.Convert.ToInt32%2A>.  
  
### Преобразование шестнадцатеричной строки в число  
  
-   Используйте метод <xref:System.Convert.ToInt32%2A> для преобразования числа, выраженного в шестнадцатеричном исчислении, в целое.  
  
     Первый аргумент метода <xref:System.Convert.ToInt32%2A> — это преобразуемая строка.  Второй аргумент описывает, в каком исчислении представлено число.  
  
     [!code-vb[VbVbalrStrings#62](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-hexadecimal-strings-to-numbers_1.vb)]  
  
## См. также  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>   
 <xref:System.Convert.ToInt32%2A>