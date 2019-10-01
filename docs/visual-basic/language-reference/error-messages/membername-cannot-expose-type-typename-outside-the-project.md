---
title: <membername> не может представлять тип <typename> вне проекта посредством <containertype><containertypename>
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: ca67e74d7790352bd1842cb8a59fe1525af6e18c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700899"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a>"\<membername >" не может представлять тип "\<typename >" за пределами проекта с помощью \<containertype > "\<containertypename >"
Переменная, параметр процедуры или возвращаемое значение функции предоставляется за пределами своего контейнера, но она объявляется как тип, который не должен предоставляться за пределами контейнера.  
  
 В приведенном ниже коде показана ситуация, которая приводит к возникновению этой ошибки.  
  
```vb  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 Тип, объявленный `Protected`, `Friend`, `Protected Friend` или `Private`, должен иметь ограниченный доступ за пределами контекста объявления. Использование его в качестве типа данных переменной с меньшим доступом было бы непреднамеренно. В приведенном выше скелете кода `exposedVar` имеет `Public` и будет предоставлять `privateClass` коду, который не должен иметь к нему доступа.  
  
 **Идентификатор ошибки:** BC30909  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Измените уровень доступа переменной, параметра процедуры или функции, чтобы он был по крайней мере ограничен уровнем доступа его типа данных.  
  
## <a name="see-also"></a>См. также

- [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
