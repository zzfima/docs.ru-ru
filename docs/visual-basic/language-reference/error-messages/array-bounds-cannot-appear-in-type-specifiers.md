---
title: "В спецификаторах типов не могут задаваться границы массива | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30638"
  - "bc30638"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30638"
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# В спецификаторах типов не могут задаваться границы массива
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Размеры массива не могут объявляться как часть спецификатора типа данных.  
  
 **Идентификатор ошибки**: BC30638  
  
### Чтобы исправить эту ошибку  
  
-   Укажите размер массива сразу после имени переменной, а не после типа, как показано в следующем примере:  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   Определите массив и выполните его инициализацию с помощью требуемого числа элементов, как показано в следующем примере:  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## См. также  
 [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)