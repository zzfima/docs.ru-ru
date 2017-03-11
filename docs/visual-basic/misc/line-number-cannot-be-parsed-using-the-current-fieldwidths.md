---
title: "Разбор строки &lt;номер&gt; с помощью текущего параметра FieldWidths невозможен | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrTextFieldParser_MalFormedFixedWidthLine"
ms.assetid: 84e14245-dfdf-4b62-8b84-e83a31608899
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Разбор строки &lt;номер&gt; с помощью текущего параметра FieldWidths невозможен
Указанная строка не может быть проанализирована, так как ее поля имеют ширину, отличную от указанной.  
  
### Исправление ошибки  
  
-   Настройте `FieldWidths` так, чтобы строка могла быть проанализирована правильно, или вставьте код обработки исключения, чтобы обработать строку.  
  
## См. также  
 [Практическое руководство. Чтение текстовых файлов различных форматов](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Метод My.Computer.FileSystem.OpenTextFieldParser](http://msdn.microsoft.com/ru-ru/e5869f85-c078-485f-8323-8dc716494546)   
 [Анализ текстовых файлов с помощью объекта TextFieldParser](../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)   
 [Объект TextFieldParser](../../visual-basic/language-reference/objects/textfieldparser-object.md)   
 [Свойство TextFieldParser.FieldWidths](http://msdn.microsoft.com/ru-ru/c6985360-60c6-494e-89e7-43b6b73f2597)   
 [Метод TextFieldParser.SetFieldWidths](http://msdn.microsoft.com/ru-ru/958fed9f-e0f3-4fc5-83b4-386156bdf036)