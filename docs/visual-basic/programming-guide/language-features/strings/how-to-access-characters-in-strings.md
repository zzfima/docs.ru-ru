---
title: "Практическое руководство. Доступ к символам строк в Visual Basic | Microsoft Docs"
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
  - "знаки [Visual Basic], доступ к строкам"
  - "строки [Visual Basic], доступ к знакам"
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Практическое руководство. Доступ к символам строк в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

В данном примере демонстрируется, как использовать свойство <xref:System.String.Chars%2A>, чтобы получить доступ к символу в указанном месте строки.  
  
## Пример  
 Иногда полезно располагать сведениями о содержащихся в строке символах и положениях этих символов.  Строку можно представить в виде массива символов \(экземпляров класса `Char`\); таким образом, можно извлечь из строки конкретный символ, обратившись к нему через индекс символа с помощью свойства <xref:System.String.Chars%2A>.  
  
 [!code-vb[VbVbalrStrings#49](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-access-characters-in-strings_1.vb)]  
  
 Индексация параметра `index` свойства <xref:System.String.Chars%2A> ведется от нуля.  
  
## Отказоустойчивость  
 Свойство <xref:System.String.Chars%2A> возвращает символ в указанном положении.  Однако некоторые символы в формате Юникод могут быть представлены несколькими символами.  Дополнительные сведения о работе с символами в формате Юникод см. в разделе [Практическое руководство. Преобразование строки в массив символов](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).  
  
 Свойство <xref:System.String.Chars%2A> создает исключение <xref:System.IndexOutOfRangeException>, если параметр `index` больше или равен длине строки, или если он меньше нуля  
  
## См. также  
 <xref:System.String.Chars%2A>   
 [Практическое руководство. Преобразование строки в массив символов](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)   
 [Преобразование между строками и другими типами данных в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)   
 [Строки](../../../../visual-basic/programming-guide/language-features/strings/index.md)