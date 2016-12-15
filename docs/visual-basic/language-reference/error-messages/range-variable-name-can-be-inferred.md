---
title: "Имя переменной диапазона может быть выведено только из простого или полного имени без аргументов | Microsoft Docs"
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
  - "vbc36599"
  - "bc36599"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36599"
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Имя переменной диапазона может быть выведено только из простого или полного имени без аргументов
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В запрос LINQ включен элемент программирования, принимающий один или несколько аргументов.  Компилятору не удается вывести переменную диапазона из этого элемента программирования.  
  
 **Идентификатор ошибки**: BC36599  
  
### Чтобы исправить эту ошибку  
  
1.  Явно присвойте переменной элемент программирования, как показано в следующем примере.  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias = SampleFunction(var1), var1  
```  
  
## См. также  
 [Знакомство с LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)