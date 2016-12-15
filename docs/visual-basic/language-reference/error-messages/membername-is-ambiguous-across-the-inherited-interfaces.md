---
title: "Член &lt;имяЧлена&gt; является неоднозначным в наследуемых интерфейсах &lt;имяИнтерфейса1&gt; и &lt;имяИнтерфейса2&gt; | Microsoft Docs"
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
  - "vbc30685"
  - "bc30685"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30685"
ms.assetid: 756add7a-23d5-4b4f-a48d-8297d6459c73
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Член &lt;имяЧлена&gt; является неоднозначным в наследуемых интерфейсах &lt;имяИнтерфейса1&gt; и &lt;имяИнтерфейса2&gt;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Интерфейс наследует из нескольких интерфейсов два или более элемента с одним и тем же именем.  
  
 **Идентификатор ошибки**: BC30685  
  
### Чтобы исправить эту ошибку  
  
-   Приведите значение к требуемому базовому интерфейсу, например:  
  
    ```  
    Interface Left  
        Sub MySub()  
    End Interface  
  
    Interface Right  
        Sub MySub()  
    End Interface  
  
    Interface LeftRight  
        Inherits Left, Right  
    End Interface  
  
    Module test  
        Sub Main()  
            Dim x As LeftRight  
            ' x.MySub()  'x is ambiguous.  
            CType(x, Left).MySub() ' Cast to base type.  
            CType(x, Right).MySub() ' Call the other base type.  
        End Sub  
    End Module  
    ```  
  
## См. также  
 [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)