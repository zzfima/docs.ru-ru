---
title: "Практическое руководство. Преобразование строки (String) в массив символов в Visual Basic | Microsoft Docs"
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
  - "массивы [Visual Basic], преобразование строк в"
  - "массив знаков, преобразование строк"
  - "примеры [Visual Basic], преобразование строк"
  - "преобразование строк [Visual Basic], массивы"
  - "строки [Visual Basic], преобразование в массивы"
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Преобразование строки (String) в массив символов в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В некоторых случаях, например при анализе строки, полезно располагать сведениями о содержащихся в строке символах и позициях этих символов.  В этом примере показано, как получить массив знаков в строке, вызывая метод <xref:System.String.ToCharArray%2A> строки.  
  
## Пример  
 В этом примере показано, как разбить строку в массив `Char` и как разбить строку в массив `String` знаков Юникода.  Причина различия в том, что знак Юникода может состоять из двух или более знаков `Char` \(например пары символов\-заместителей или последовательности несамостоятельных знаков\).  Дополнительные сведения см. в разделе <xref:System.Globalization.TextElementEnumerator> и на веб\-узле стандарта Юникод \(http:\/\/www.unicode.org\).  
  
 [!code-vb[VbVbalrStrings#75](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_1.vb)]  
  
## Пример  
 Разбить строку на знаки Юникод труднее, но это необходимо для получения сведений о визуальном представлении строки.  В этом примере используется метод <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> для получения сведений о символах, составляющих строку Юникод.  
  
 [!code-vb[VbVbalrStrings#76](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_2.vb)]  
  
## См. также  
 <xref:System.String.Chars%2A>   
 <xref:System.Globalization.StringInfo?displayProperty=fullName>   
 [Практическое руководство. Доступ к символам в строках](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)   
 [Преобразование между строками и другими типами данных в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)   
 [Строки](../../../../visual-basic/programming-guide/language-features/strings/index.md)