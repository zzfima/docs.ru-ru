---
title: "Массивы, объявленные как члены структуры, не могут быть объявлены с указанием начального размера | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc31043"
  - "bc31043"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31043"
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Массивы, объявленные как члены структуры, не могут быть объявлены с указанием начального размера
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Массив, содержащийся в структуре, объявлен с указанием начального размера.  Нельзя инициализировать любой элемент структуры и объявить размер массива в одной форме инициализации.  
  
 **Идентификатор ошибки:** BC31043  
  
### Чтобы исправить эту ошибку  
  
1.  Определите массив в структуре как динамический \(без указания начального размера\).  
  
2.  Если требуется массив определенного размера, можно использовать преобразование динамического массива с помощью [Оператор ReDim](../../../visual-basic/language-reference/statements/redim-statement.md) при запуске кода.  Это показано в приведенном ниже примере.  
  
    ```  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## См. также  
 [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Практическое руководство. Объявление структуры](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)