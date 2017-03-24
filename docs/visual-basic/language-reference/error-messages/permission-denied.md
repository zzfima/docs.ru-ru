---
title: "Доступ запрещен (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID70"
dev_langs: 
  - "VB"
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Доступ запрещен (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Предпринята попытка записи на защищенный от записи диск или получения доступа к заблокированному файлу.  
  
### Чтобы исправить эту ошибку  
  
1.  Чтобы открыть файл, защищенный от записи, измените атрибут защиты от записи файла.  
  
2.  Убедитесь, что файл не заблокирован другим процессом, и попытайтесь открыть файл после того, как этот процесс его освободит.  
  
3.  Чтобы получить доступ к реестру, проверьте, что разрешения пользователя включают этот тип доступа к реестру.  
  
## См. также  
 [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)