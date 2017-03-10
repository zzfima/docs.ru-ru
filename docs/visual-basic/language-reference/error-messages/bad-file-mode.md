---
title: "Недопустимый режим файла | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID54"
dev_langs: 
  - "VB"
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Недопустимый режим файла
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Операторы, используемые для управления содержимым файла, должны соответствовать режиму, в котором открыт файл.  Возможные причины:  
  
-   Оператор `FilePutObject` или `FileGetObject` задает последовательный файл.  
  
-   Оператор `Print` задает файл, открытый в режиме доступа отличном от `Output` или `Append`.  
  
-   Оператор `Input` задает файл, открытый в режиме доступа отличном от `Input`.  
  
-   Предпринята попытка записи в файл, доступный только для чтения.  
  
### Чтобы исправить эту ошибку  
  
-   Убедитесь, что `FilePutObject` и `FileGetObject` ссылаются только на файлы, открытые для `Random` или `Binary`.  
  
-   Убедитесь, что `Print` задает файл, открытый в режиме доступа `Output` или `Append`.  Если файл открыт в другом режиме доступа, используйте другой оператор для помещения данных в файл или откройте его повторно в необходимом режиме.  
  
-   Убедитесь, что `Input` указывает файл, открытый для `Input`.  Если файл открыт в другом режиме доступа, используйте другой оператор для помещения данных в файл или откройте его повторно в необходимом режиме.  
  
-   При записи в файл, доступный только для чтения, измените статус файла запись\/чтение или не пытайтесь в него записать.  
  
-   Используйте функциональность объекта `My.Computer.FileSystem`.  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileSystem>   
 [Исправление неполадок, связанных с чтением из текстовых файлов и записью в такие файлы](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)