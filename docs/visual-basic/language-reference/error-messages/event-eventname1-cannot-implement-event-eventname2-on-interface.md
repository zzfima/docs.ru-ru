---
title: "Событие &lt;имяСобытия1&gt; не может реализовать событие &lt;имяСобытия2&gt; в интерфейсе &lt;интерфейс&gt;, так как их делегируемые типы &lt;делегат1&gt; и &lt;делегат2&gt; не совпадают | Microsoft Docs"
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
  - "vbc31423"
  - "bc31423"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31423"
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Событие &lt;имяСобытия1&gt; не может реализовать событие &lt;имяСобытия2&gt; в интерфейсе &lt;интерфейс&gt;, так как их делегируемые типы &lt;делегат1&gt; и &lt;делегат2&gt; не совпадают
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не может реализовать событие, поскольку его тип делегата не соответствует типу делегата события интерфейса.  Эта ошибка может появиться при определении нескольких событий в интерфейсе и последующей попытке их совместной реализации с использованием одного события.  Событие может реализовывать несколько событий только в том случае, если все они объявлены с помощью синтаксиса `As` и указывают один и тот же тип делегата.  
  
 **Идентификатор ошибки**: BC31423  
  
### Чтобы исправить эту ошибку  
  
-   Реализуйте события по отдельности.  
  
     —или—  
  
-   Определите события в интерфейсе, используя синтаксис `As`, и укажите тот же тип делегата.  
  
## См. также  
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [События](../../../visual-basic/programming-guide/language-features/events/events.md)