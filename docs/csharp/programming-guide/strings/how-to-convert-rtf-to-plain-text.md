---
title: "Практическое руководство. Преобразование формата RTF в обычный текст (Руководство по программированию в C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "строки [C#], преобразование из RTF"
ms.assetid: 3b386a87-899d-4d98-bc82-a980526ddaac
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# Практическое руководство. Преобразование формата RTF в обычный текст (Руководство по программированию в C#)
Формат RTF является форматом документов, разработанный корпорацией Microsoft в конце 80\-х годов для предоставления возможности использования одних и тех же документов в разных операционных системах.  И Microsoft Word, и WordPad могут читать документы RTF и записывать в них.  В платформе .NET Framework можно использовать элемент управления <xref:System.Windows.Forms.RichTextBox> для создания текстового процессора, который поддерживает RTF и дает возможность пользователю применять форматирование текста в режиме WYSIWIG.  
  
 Можно также использовать элемент управления <xref:System.Windows.Forms.RichTextBox> для удаления программным способом котов форматирования RTF из документа и преобразования его в обычный текст.  Для выполнения этого вида операций нет необходимости внедрять элемент управления в форме Windows Forms.  
  
### Использование в проекте элемента управления RichTextBox  
  
1.  Добавьте ссылку на System.Windows.Forms.dll.  
  
2.  Добавьте директиву using для пространства имен `System.Windows.Forms` \(необязательно\).  
  
## Пример  
 В следующем примере показано преобразование файл RTF примера к обычному тексту.  Файл содержит rtf\-форматирование \(например, данные о шрифте.\), 4 символов юникода и 4 удлиненных символа.  Пример кода будет открыт файл, передает его содержимое в <xref:System.Windows.Forms.RichTextBox> в формате RTF, получающие содержимое в виде текста, отображает текст в <xref:System.Windows.Forms.MessageBox> и выводит текст в файл в кодировке UTF\-8.  
  
 `MessageBox` и выходной файл содержит следующий текст:  
  
```  
The Greek word for "psyche" is spelled ψυχή. The Greek letters are encoded in Unicode.  
These characters are from the extended ASCII character set (Windows code page 1252):  âäӑå  
  
```  
  
 [!code-cs[csProgGuideStrings#33](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-rtf-to-plain-text_1.cs)]  
  
 Символы RTF кодируются восемью битами.  Тем не менее, пользователь может указать символы юникода в дополнение к дополнительным символам ASCII из заданных кодовых страниц.  Поскольку свойство <xref:System.Windows.Forms.RichTextBox.Text%2A?displayProperty=fullName> имеет тип [string](../../../csharp/language-reference/keywords/string.md), символы кодируются как Юникод UTF\-16.  Дополнительные символы ASCII и символы Юникода из исходного RTF\-документа правильно кодируются в выводимый текст.  
  
 При использовании метода <xref:System.IO.File.WriteAllText%2A?displayProperty=fullName> для записи текста на диск, текст кодируется как UTF\-8 \(без отметки порядка байтов\).  
  
## См. также  
 <xref:System.Windows.Forms.RichTextBox?displayProperty=fullName>   
 [Строки](../../../csharp/programming-guide/strings/index.md)