---
title: "Переменная использует тип автоматизации, не поддерживаемый в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID458"
dev_langs: 
  - "VB"
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Переменная использует тип автоматизации, не поддерживаемый в Visual Basic
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Предпринята попытка использования переменной, определенной в библиотеке типов или библиотеке объектов, в которых содержится тип данных, не поддерживаемый в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
### Чтобы исправить эту ошибку  
  
-   Используйте переменную такого типа, который распознается в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
     \-или\-  
  
-   Если эта ошибка возникает при использовании функции `FileGet` или `FileGetOBject`, убедитесь, что используемый файл был записан с помощью метода `FilePut` или `FilePutObject`.  
  
## См. также  
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)