---
title: "Недопустимая длина записи | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID59"
dev_langs: 
  - "VB"
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Недопустимая длина записи
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Возможные причины появления этой ошибки:  
  
-   Длина переменной записи, указанной в операторе `FileGet`, `FileGetObject`, `FilePut` или `FilePutObject`, отличается от длины, указанной в соответствующем операторе `FileOpen`.  
  
-   Переменная в операторе `FilePut` или `FilePutObject` является строкой переменной длины или включает строку переменной длины.  
  
-   Переменная в `FilePut` или `FilePutObject` является типом `Variant` или включает этот тип.  
  
### Чтобы исправить эту ошибку  
  
1.  Убедитесь, что сумма размеров переменных фиксированной длины в заданном пользователем типе, который определяет тип переменной записи, совпадает со значением, заданным в предложении `Len` оператора `FileOpen`.  
  
2.  Если переменная в операторе `FilePut` или `FilePutObject` является строкой переменной длины или включает такую строку, убедитесь, что строка переменной длины хотя бы на 2 символа короче длины записи, указанной в предложении `Len` оператора `FileOpen`.  
  
3.  Если переменная в операторе `FilePut` или `FilePutObject` является типом `Variant` или включает этот тип, убедитесь, что строка переменной длины хотя бы на 4 байта короче длины записи, указанной в предложении `Len` оператора `FileOpen`  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>