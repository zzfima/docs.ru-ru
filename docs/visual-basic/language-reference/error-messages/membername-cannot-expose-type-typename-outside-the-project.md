---
title: '&#39; &lt;membername&gt;&#39; не может представлять тип &#39;&lt; TypeName&gt;&#39; вне проекта посредством &lt;containertype&gt; &#39;&lt; containertypename&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fd64c815286a5ffec111bcf1f68674a8e3558403
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="39ltmembernamegt39-cannot-expose-type-39lttypenamegt39-outside-the-project-through-ltcontainertypegt-39ltcontainertypenamegt39"></a><span data-ttu-id="0904f-102">&#39; &lt;membername&gt;&#39; не может представлять тип &#39;&lt; TypeName&gt;&#39; вне проекта посредством &lt;containertype&gt; &#39;&lt; containertypename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="0904f-102">&#39;&lt;membername&gt;&#39; cannot expose type &#39;&lt;typename&gt;&#39; outside the project through &lt;containertype&gt; &#39;&lt;containertypename&gt;&#39;</span></span>
<span data-ttu-id="0904f-103">Переменная, параметр процедуры или возвращаемое функцией предоставляется вне контейнера, но он объявлен как тип, который может быть предоставлен вне контейнера.</span><span class="sxs-lookup"><span data-stu-id="0904f-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="0904f-104">Следующий код демонстрирует ситуацию, которая создает эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="0904f-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="0904f-105">Тип, объявленный `Protected`, `Friend`, `Protected Friend`, или `Private` должен иметь ограниченный доступ вне контекста его объявления.</span><span class="sxs-lookup"><span data-stu-id="0904f-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="0904f-106">Используя его как данные типа переменной меньше ограничения доступа будет достижению этой цели.</span><span class="sxs-lookup"><span data-stu-id="0904f-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="0904f-107">В приведенном выше коде `exposedVar` — `Public` и предоставит `privateClass` код, который должен иметь доступ к нему.</span><span class="sxs-lookup"><span data-stu-id="0904f-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="0904f-108">**Идентификатор ошибки:** BC30909</span><span class="sxs-lookup"><span data-stu-id="0904f-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0904f-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="0904f-109">To correct this error</span></span>  
  
-   <span data-ttu-id="0904f-110">Измените уровень доступа к переменной, параметр процедуры или функции возвращают быть менее строгие, чем уровень доступа для его типа данных.</span><span class="sxs-lookup"><span data-stu-id="0904f-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0904f-111">См. также</span><span class="sxs-lookup"><span data-stu-id="0904f-111">See Also</span></span>  
 [<span data-ttu-id="0904f-112">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0904f-112">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
