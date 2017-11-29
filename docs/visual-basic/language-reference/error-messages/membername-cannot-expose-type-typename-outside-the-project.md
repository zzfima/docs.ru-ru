---
title: "&#39; &lt;membername&gt;&#39; не может представлять тип &#39;&lt; TypeName&gt;&#39; вне проекта посредством &lt;containertype&gt; &#39;&lt; containertypename&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords: BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fd64c815286a5ffec111bcf1f68674a8e3558403
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="39ltmembernamegt39-cannot-expose-type-39lttypenamegt39-outside-the-project-through-ltcontainertypegt-39ltcontainertypenamegt39"></a>&#39; &lt;membername&gt;&#39; не может представлять тип &#39;&lt; TypeName&gt;&#39; вне проекта посредством &lt;containertype&gt; &#39;&lt; containertypename&gt;&#39;
Переменная, параметр процедуры или возвращаемое функцией предоставляется вне контейнера, но он объявлен как тип, который может быть предоставлен вне контейнера.  
  
 Следующий код демонстрирует ситуацию, которая создает эту ошибку.  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 Тип, объявленный `Protected`, `Friend`, `Protected Friend`, или `Private` должен иметь ограниченный доступ вне контекста его объявления. Используя его как данные типа переменной меньше ограничения доступа будет достижению этой цели. В приведенном выше коде `exposedVar` — `Public` и предоставит `privateClass` код, который должен иметь доступ к нему.  
  
 **Идентификатор ошибки:** BC30909  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Измените уровень доступа к переменной, параметр процедуры или функции возвращают быть менее строгие, чем уровень доступа для его типа данных.  
  
## <a name="see-also"></a>См. также  
 [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
