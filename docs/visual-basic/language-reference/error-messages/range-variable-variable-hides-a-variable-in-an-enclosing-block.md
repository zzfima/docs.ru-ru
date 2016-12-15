---
title: "Переменная диапазона &lt;переменная&gt; скрывает переменную во включающем блоке, ранее определенную переменную диапазона или неявно объявленную переменную в выражении запроса | Microsoft Docs"
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
  - "bc36633"
  - "vbc36633"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36633"
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Переменная диапазона &lt;переменная&gt; скрывает переменную во включающем блоке, ранее определенную переменную диапазона или неявно объявленную переменную в выражении запроса
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Имя переменной диапазона, указанное в предложении `Select`, `From`, `Aggregate` или `Let` дублирует имя переменной диапазона, уже указанное ранее в запросе, или имя переменной, неявно объявленной по запросу, такое как имя поля или имя агрегатной функции.  
  
 **Идентификатор ошибки:** BC36633  
  
### Чтобы исправить эту ошибку  
  
-   Убедитесь, что все переменные диапазона в области действия определенного запроса имеют уникальные имена.  Можно заключить запрос в скобки и убедиться, что вложенные запросы имеют уникальную область действия.  
  
## См. также  
 [Знакомство с LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Предложение Let](../../../visual-basic/language-reference/queries/let-clause.md)   
 [Предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)