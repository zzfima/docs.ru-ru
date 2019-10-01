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
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="0fc19-102">"\<membername >" не может представлять тип "\<typename >" за пределами проекта с помощью \<containertype > "\<containertypename >"</span><span class="sxs-lookup"><span data-stu-id="0fc19-102">'\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>
<span data-ttu-id="0fc19-103">Переменная, параметр процедуры или возвращаемое значение функции предоставляется за пределами своего контейнера, но она объявляется как тип, который не должен предоставляться за пределами контейнера.</span><span class="sxs-lookup"><span data-stu-id="0fc19-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="0fc19-104">В приведенном ниже коде показана ситуация, которая приводит к возникновению этой ошибки.</span><span class="sxs-lookup"><span data-stu-id="0fc19-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```vb  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="0fc19-105">Тип, объявленный `Protected`, `Friend`, `Protected Friend` или `Private`, должен иметь ограниченный доступ за пределами контекста объявления.</span><span class="sxs-lookup"><span data-stu-id="0fc19-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="0fc19-106">Использование его в качестве типа данных переменной с меньшим доступом было бы непреднамеренно.</span><span class="sxs-lookup"><span data-stu-id="0fc19-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="0fc19-107">В приведенном выше скелете кода `exposedVar` имеет `Public` и будет предоставлять `privateClass` коду, который не должен иметь к нему доступа.</span><span class="sxs-lookup"><span data-stu-id="0fc19-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="0fc19-108">**Идентификатор ошибки:** BC30909</span><span class="sxs-lookup"><span data-stu-id="0fc19-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0fc19-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="0fc19-109">To correct this error</span></span>  
  
- <span data-ttu-id="0fc19-110">Измените уровень доступа переменной, параметра процедуры или функции, чтобы он был по крайней мере ограничен уровнем доступа его типа данных.</span><span class="sxs-lookup"><span data-stu-id="0fc19-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fc19-111">См. также</span><span class="sxs-lookup"><span data-stu-id="0fc19-111">See also</span></span>

- [<span data-ttu-id="0fc19-112">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0fc19-112">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
