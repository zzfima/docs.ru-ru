---
title: "Переменная использует тип автоматизации, не поддерживаемый в Visual Basic | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID458"
dev_langs: 
  - "VB"
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Переменная использует тип автоматизации, не поддерживаемый в Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Предпринята попытка использования переменной, определенной в библиотеке типов или библиотеке объектов, в которых содержится тип данных, не поддерживаемый в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
### Чтобы исправить эту ошибку  
  
-   Используйте переменную такого типа, который распознается в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
     \-или\-  
  
-   Если эта ошибка возникает при использовании функции `FileGet` или `FileGetOBject`, убедитесь, что используемый файл был записан с помощью метода `FilePut` или `FilePutObject`.  
  
## См. также  
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)