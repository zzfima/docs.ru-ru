---
title: "Количество индексов превышает размерность индексированного массива | Microsoft Docs"
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
  - "bc30106"
  - "vbc30106"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30106"
ms.assetid: 2c5363e1-62c2-4f5a-b675-c7337aeb363d
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Количество индексов превышает размерность индексированного массива
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Количество индексов, используемых для доступа к элементу массива, должно совпадать с рангом массива, т. е. с количеством объявленных для массива измерений.  
  
 **Идентификатор ошибки**: BC30106  
  
### Чтобы исправить эту ошибку  
  
-   Удалите из ссылки на массив такое количество индексов, которое необходимо для совпадения общего количества индексов с рангом массива.  Примеры.  
  
    ```  
    [Visual Basic]  
    Dim gameBoard(3, 3) As String  
  
    ' Incorrect code. The array has two dimensions.  
    gameBoard(1, 1, 1) = "X"  
    gameBoard(2, 1, 1) = "O"  
  
    ' Correct code.  
    gameBoard(0, 0) = "X"  
    gameBoard(1, 0) = "O"  
    ```  
  
## См. также  
 [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)