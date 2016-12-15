---
title: "&lt;имяЧлена&gt; не может представлять тип &lt;имяТипа&gt; вне проекта посредством &lt;типКонтейнера&gt; &lt;имяТипаКонтейнера&gt; | Microsoft Docs"
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
  - "bc30909"
  - "vbc30909"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30909"
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;имяЧлена&gt; не может представлять тип &lt;имяТипа&gt; вне проекта посредством &lt;типКонтейнера&gt; &lt;имяТипаКонтейнера&gt;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Переменная, параметр процедуры или возврата функции предоставляется вне контейнера, но является типом, который может быть предоставлен вне контейнера.  
  
 Следующий код демонстрирует ситуацию, в которой создается эта ошибка.  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 Тип, объявленный как `Protected`, `Friend`, `Protected Friend` или `Private` должен иметь ограниченный доступ вне контекста его объявления.  Использование его в качестве типа данных переменной с менее ограниченным доступом не приведет к достижению этой цели.  В приведенном выше коде `exposedVar` является `Public`, и предоставит `privateClass` коду, который не должен иметь к нему доступа.  
  
 **Идентификатор ошибки:** BC30909  
  
### Чтобы исправить эту ошибку  
  
-   Измените уровень доступа к переменной, параметру процедуры или параметру, который возвращает функция, ограничив его по крайней мере уровнем доступа его типа данных.  
  
## См. также  
 [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)