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
# <a name="39ltmembernamegt39-cannot-expose-type-39lttypenamegt39-outside-the-project-through-ltcontainertypegt-39ltcontainertypenamegt39"></a><span data-ttu-id="8e3db-102">&#39;&lt;имя пользователя&gt; &#39; не может представлять тип &#39; &lt;typename&gt; &#39; вне проекта посредством &lt;containertype&gt; &#39; &lt;containertypename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="8e3db-102">&#39;&lt;membername&gt;&#39; cannot expose type &#39;&lt;typename&gt;&#39; outside the project through &lt;containertype&gt; &#39;&lt;containertypename&gt;&#39;</span></span>
<span data-ttu-id="8e3db-103">Переменная, параметр процедуры или возвращаемое функцией предоставляется вне контейнера, но он объявлен как тип, который может быть предоставлен вне контейнера.</span><span class="sxs-lookup"><span data-stu-id="8e3db-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="8e3db-104">Следующий код демонстрирует ситуацию, которая создает эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="8e3db-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="8e3db-105">Тип, объявленный `Protected`, `Friend`, `Protected Friend`, или `Private` должен иметь ограниченный доступ вне контекста его объявления.</span><span class="sxs-lookup"><span data-stu-id="8e3db-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="8e3db-106">Используя его как данные типа переменной меньше ограничения доступа будет достижению этой цели.</span><span class="sxs-lookup"><span data-stu-id="8e3db-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="8e3db-107">В приведенном выше коде `exposedVar` — `Public` и предоставит `privateClass` код, который должен иметь доступ к нему.</span><span class="sxs-lookup"><span data-stu-id="8e3db-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="8e3db-108">**Идентификатор ошибки:** BC30909</span><span class="sxs-lookup"><span data-stu-id="8e3db-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8e3db-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="8e3db-109">To correct this error</span></span>  
  
-   <span data-ttu-id="8e3db-110">Измените уровень доступа к переменной, параметр процедуры или функции возвращают быть менее строгие, чем уровень доступа для его типа данных.</span><span class="sxs-lookup"><span data-stu-id="8e3db-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e3db-111">См. также</span><span class="sxs-lookup"><span data-stu-id="8e3db-111">See Also</span></span>  
 [<span data-ttu-id="8e3db-112">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8e3db-112">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
