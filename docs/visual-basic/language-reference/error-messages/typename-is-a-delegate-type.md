---
title: "&lt;имяТипа&gt; является типом делегата | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc32008"
  - "vbc32008"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32008"
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# &lt;имяТипа&gt; является типом делегата
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

\<имяТипа\> является типом делегата.Конструкция делегата позволяет использовать только одно выражение AddressOf в качестве списка аргументов.Часто выражение AddressOf может использоваться вместо конструкции делегата.  
  
 Оператор `New` при создании экземпляра класса делегата передает недопустимый список аргументов в конструктор делегата.  
  
 При создании нового экземпляра делегата можно задать только одно выражение `AddressOf`.  
  
 Эта ошибка может произойти, если конструктору делегата не передается никаких аргументов, передается несколько аргументов или передается один аргумент, не являющийся допустимым выражением `AddressOf`.  
  
 **Идентификатор ошибки**: BC32008  
  
### Чтобы исправить эту ошибку  
  
-   Используйте одно выражение `AddressOf` в списке аргументов для класса делегата в операторе `New`  
  
## См. также  
 [Оператор New](../../../visual-basic/language-reference/operators/new-operator.md)   
 [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Практическое руководство. Вызов метода делегата](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)