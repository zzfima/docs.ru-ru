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
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="9783c-102">"\<имя_члена >" не может представлять тип "\<typename >" вне проекта посредством \<containertype > "\<containertypename >"</span><span class="sxs-lookup"><span data-stu-id="9783c-102">'\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>
<span data-ttu-id="9783c-103">Переменная, параметр процедуры или возвращаемое значение функции предоставляется вне контейнера, но он объявлен как тип, который может быть предоставлен вне контейнера.</span><span class="sxs-lookup"><span data-stu-id="9783c-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="9783c-104">Следующий код демонстрирует ситуацию, которая создает эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="9783c-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="9783c-105">Тип, объявленный `Protected`, `Friend`, `Protected Friend`, или `Private` должен иметь ограниченный доступ вне контекста его объявления.</span><span class="sxs-lookup"><span data-stu-id="9783c-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="9783c-106">Используя в качестве данных тип переменной с меньшими ограничениями доступа будет достижению этой цели.</span><span class="sxs-lookup"><span data-stu-id="9783c-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="9783c-107">В приведенном выше коде `exposedVar` — `Public` и предоставит `privateClass` в код, который не должны иметь доступ к нему.</span><span class="sxs-lookup"><span data-stu-id="9783c-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="9783c-108">**Идентификатор ошибки:** BC30909</span><span class="sxs-lookup"><span data-stu-id="9783c-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9783c-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="9783c-109">To correct this error</span></span>  
  
-   <span data-ttu-id="9783c-110">Изменение уровня доступа к переменной, параметр процедуры или функции возвращают быть менее строгий уровень доступа соответствующего типа данных.</span><span class="sxs-lookup"><span data-stu-id="9783c-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9783c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9783c-111">See also</span></span>
- [<span data-ttu-id="9783c-112">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9783c-112">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
