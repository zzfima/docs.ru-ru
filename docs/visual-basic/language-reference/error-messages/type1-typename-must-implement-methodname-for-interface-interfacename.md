---
title: "Тип &lt;тип1&gt;&lt;имяТипа&gt; должен реализовать &lt;имяМетода&gt; для интерфейса &lt;имяИнтерфейса&gt; | Microsoft Docs"
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
  - "vbc30149"
  - "bc30149"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30149"
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Тип &lt;тип1&gt;&lt;имяТипа&gt; должен реализовать &lt;имяМетода&gt; для интерфейса &lt;имяИнтерфейса&gt;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Класс или структура объявляет о реализации интерфейса, но не реализует процедуру, определенную этим интерфейсом.  Каждый член интерфейса должен быть реализован.  
  
 **Идентификатор ошибки**: BC30149  
  
### Чтобы исправить эту ошибку  
  
1.  Объявите процедуру с тем же именем и сигнатурой, что и процедура, определенная в интерфейсе.  Не забудьте включить оператор `End Function` или `End Sub`.  
  
2.  Добавьте предложение `Implements` в конец оператора `Function` или `Sub`.  Примеры.  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## См. также  
 [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)