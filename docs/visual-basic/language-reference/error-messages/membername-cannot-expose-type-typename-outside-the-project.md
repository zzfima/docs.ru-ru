---
title: '&#39;&lt;имя пользователя&gt; &#39; не может представлять тип &#39; &lt;typename&gt; &#39; вне проекта посредством &lt;containertype&gt; &#39; &lt;containertypename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 39d316aca5ec306de4b1e43e2eb2d1495f5525d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672348"
---
# <a name="39ltmembernamegt39-cannot-expose-type-39lttypenamegt39-outside-the-project-through-ltcontainertypegt-39ltcontainertypenamegt39"></a>&#39;&lt;имя пользователя&gt; &#39; не может представлять тип &#39; &lt;typename&gt; &#39; вне проекта посредством &lt;containertype&gt; &#39; &lt;containertypename&gt;&#39;
Переменная, параметр процедуры или возвращаемое значение функции предоставляется вне контейнера, но он объявлен как тип, который может быть предоставлен вне контейнера.  
  
 Следующий код демонстрирует ситуацию, которая создает эту ошибку.  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 Тип, объявленный `Protected`, `Friend`, `Protected Friend`, или `Private` должен иметь ограниченный доступ вне контекста его объявления. Используя в качестве данных тип переменной с меньшими ограничениями доступа будет достижению этой цели. В приведенном выше коде `exposedVar` — `Public` и предоставит `privateClass` в код, который не должны иметь доступ к нему.  
  
 **Идентификатор ошибки:** BC30909  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Изменение уровня доступа к переменной, параметр процедуры или функции возвращают быть менее строгий уровень доступа соответствующего типа данных.  
  
## <a name="see-also"></a>См. также
- [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
