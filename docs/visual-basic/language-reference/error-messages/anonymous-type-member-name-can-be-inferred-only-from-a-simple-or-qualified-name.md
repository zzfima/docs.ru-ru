---
title: Имя члена анонимного типа может быть определено только из простого или уточненного имени без аргументов
ms.date: 07/20/2015
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords:
- BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
ms.openlocfilehash: 38f669fe183ac79ebed6e5a122bc70aedc9bb753
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701217"
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="1ae61-102">Имя члена анонимного типа может быть определено только из простого или уточненного имени без аргументов</span><span class="sxs-lookup"><span data-stu-id="1ae61-102">Anonymous type member name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="1ae61-103">Нельзя вывести имя члена анонимного типа из сложного выражения.</span><span class="sxs-lookup"><span data-stu-id="1ae61-103">You cannot infer an anonymous type member name from a complex expression.</span></span>  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 <span data-ttu-id="1ae61-104">Дополнительные сведения об источниках, из которых анонимные типы могут и не могут вычислять имена и типы членов, см. в разделе [How to: Выводит имена и типы свойств в объявлениях анонимного типа @ no__t-0.</span><span class="sxs-lookup"><span data-stu-id="1ae61-104">For more information about sources from which anonymous types can and cannot infer member names and types, see [How to: Infer Property Names and Types in Anonymous Type Declarations](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
 <span data-ttu-id="1ae61-105">**Идентификатор ошибки:** BC36556</span><span class="sxs-lookup"><span data-stu-id="1ae61-105">**Error ID:** BC36556</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1ae61-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="1ae61-106">To correct this error</span></span>  
  
- <span data-ttu-id="1ae61-107">Назначьте выражение имени члена, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="1ae61-107">Assign the expression to a member name, as shown in the following code:</span></span>  
  
    ```vb  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1ae61-108">См. также</span><span class="sxs-lookup"><span data-stu-id="1ae61-108">See also</span></span>

- [<span data-ttu-id="1ae61-109">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="1ae61-109">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- <span data-ttu-id="1ae61-110">[Практическое руководство. Выводит имена и типы свойств в объявлениях анонимного типа @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="1ae61-110">[How to: Infer Property Names and Types in Anonymous Type Declarations](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)</span></span>
