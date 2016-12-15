---
title: "Метод &lt;имяМетода&gt; несколько раз определен с одинаковыми подписями | Microsoft Docs"
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
  - "vbc30269"
  - "bc30269"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30269"
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Метод &lt;имяМетода&gt; несколько раз определен с одинаковыми подписями
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В объявлении процедуры `Function` или `Sub` используются то же имя процедуры и список аргументов, как и в предыдущем объявлении.  Возможной причиной этого может быть попытка перегрузки исходной процедуры.  Перегруженные процедуры должны иметь разные списки аргументов.  
  
 **Идентификатор ошибки:** BC30269  
  
### Чтобы исправить эту ошибку  
  
-   Измените имя процедуры или список аргументов или удалите повторяющееся объявление.  
  
## См. также  
 [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Вопросы, связанные с перегрузкой процедур](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)