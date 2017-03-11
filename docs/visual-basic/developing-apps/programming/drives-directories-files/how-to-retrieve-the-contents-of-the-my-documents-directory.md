---
title: "Практическое руководство. Извлечение содержимого каталога &quot;Мои документы&quot; в Visual Basic | Microsoft Docs"
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
  - "каталог "Мои документы""
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Практическое руководство. Извлечение содержимого каталога &quot;Мои документы&quot; в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Объект <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> можно использовать для чтения многих каталогов **Все пользователи**, таких как **Мои документы** или **Рабочий стол**.  
  
### Чтобы выполнить чтение из каталога "Мои документы"  
  
-   Используйте метод `ReadAllText` для считывания текста из каждого файла в заданном каталоге.  Следующий код задает каталог и файл, а затем использует метод `ReadAllText` для чтения их в строку с именем `patients`.  
  
     [!code-vb[VbVbcnMyFileSystem#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-retrieve-the-cont_1.vb)]  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>