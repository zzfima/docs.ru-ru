---
title: "Тип &lt;тип1&gt;&lt;имяТипа&gt; должен реализовать &lt;имяЧлена&gt; для интерфейса &lt;имяИнтерфейса&gt; | Microsoft Docs"
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
  - "vbc30154"
  - "bc30154"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30154"
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Тип &lt;тип1&gt;&lt;имяТипа&gt; должен реализовать &lt;имяЧлена&gt; для интерфейса &lt;имяИнтерфейса&gt;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Тип \<имя\_типа\> должен реализовывать \<имя\_члена\> для интерфейса \<имя\_интерфейса\>.Реализующее свойство должно иметь соответствующие ему спецификаторы ReadOnly или WriteOnly.  
  
 Класс или структура объявляет о реализации интерфейса, но не реализует процедуру, свойство или событие, определенные этим интерфейсом.  Каждый член интерфейса должен быть реализован.  
  
 **Идентификатор ошибки**: BC30154  
  
### Чтобы исправить эту ошибку  
  
1.  Объявите член интерфейса с теми же именем и сигнатурой, что и определенный в интерфейсе член.  Не забудьте включить `End Function`, `End Sub` или `End Property`.  
  
2.  Добавьте предложение `Implements` в конец оператора функции `Function`, процедуры `Sub`, свойства `Property` или события `Event`.  Примеры.  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  При реализации свойства убедитесь, что ключевое слово `ReadOnly` или `WriteOnly` используется так же, как и в определении интерфейса.  
  
4.  При реализации свойства при необходимости объявите процедуры `Get` и `Set`.  
  
## См. также  
 [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)