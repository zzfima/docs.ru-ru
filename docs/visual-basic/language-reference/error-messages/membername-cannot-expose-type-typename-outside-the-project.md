---
title: <membername> не может представлять тип <typename> вне проекта посредством <containertype><containertypename>
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 03767501488a395073f925e27adea439751c0de6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265068"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a>"\<имя_члена >" не может представлять тип "\<typename >" вне проекта посредством \<containertype > "\<containertypename >"
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
