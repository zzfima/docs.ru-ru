---
title: '&#39;&lt;имя пользователя&gt; &#39; не может представлять тип &#39; &lt;typename&gt; &#39; вне проекта посредством &lt;containertype&gt; &#39; &lt;containertypename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 36add48ebee2d1804921eeeec0b59cdd4cbafecc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="39ltmembernamegt39-cannot-expose-type-39lttypenamegt39-outside-the-project-through-ltcontainertypegt-39ltcontainertypenamegt39"></a>&#39;&lt;имя пользователя&gt; &#39; не может представлять тип &#39; &lt;typename&gt; &#39; вне проекта посредством &lt;containertype&gt; &#39; &lt;containertypename&gt;&#39;
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
