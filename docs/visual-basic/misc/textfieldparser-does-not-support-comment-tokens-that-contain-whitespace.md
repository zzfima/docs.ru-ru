---
title: "TextFieldParser не поддерживает токены комментариев, содержащие пробелы. | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrTextFieldParser_WhitespaceInToken"
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# TextFieldParser не поддерживает токены комментариев, содержащие пробелы.
Представлен токен комментария, содержащий пробел.`TextFieldParser` не поддерживает токены комментариев, содержащие пробелы, если это не пробел в начале токена. Пробелы в начале токена игнорируются.  
  
### Исправление ошибки  
  
-   Укажите правильный токен комментария.  
  
## См. также  
 [Свойство TextFieldParser.CommentTokens](http://msdn.microsoft.com/ru-ru/2e6b6435-4bee-4c14-a353-e8f2c82e2d61)   
 [Анализ текстовых файлов с помощью объекта TextFieldParser](../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)   
 [Объект TextFieldParser](../../visual-basic/language-reference/objects/textfieldparser-object.md)