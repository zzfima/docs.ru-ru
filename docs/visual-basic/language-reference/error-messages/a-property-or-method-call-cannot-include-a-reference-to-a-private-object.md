---
title: Нельзя включить ссылку на закрытый объект при вызове свойства или функции в качестве аргумента или возвращаемого значения
ms.date: 07/20/2015
f1_keywords:
- vbrID98
ms.assetid: 059b43e1-202d-4fa2-806b-7bad63c1e7ca
ms.openlocfilehash: 53f9052555555a5b9dcb038dfee9cd54dc2b4251
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976198"
---
# <a name="a-property-or-method-call-cannot-include-a-reference-to-a-private-object-either-as-an-argument-or-as-a-return-value"></a><span data-ttu-id="3a5cb-102">Нельзя включить ссылку на закрытый объект при вызове свойства или функции в качестве аргумента или возвращаемого значения</span><span class="sxs-lookup"><span data-stu-id="3a5cb-102">A property or method call cannot include a reference to a private object, either as an argument or as a return value</span></span>

<span data-ttu-id="3a5cb-103">Некоторые из возможных причин этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="3a5cb-103">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="3a5cb-104">клиент вызвал свойство или метод внепроцессного компонента и предпринял попытку передать ссылку на закрытый объект в качестве одного из аргументов;</span><span class="sxs-lookup"><span data-stu-id="3a5cb-104">A client invoked a property or method of an out-of-process component and attempted to pass a reference to a private object as one of the arguments.</span></span>  
  
- <span data-ttu-id="3a5cb-105">внепроцессный компонент задействовал для клиента метод обратного вызова и предпринял попытку передать ссылку на закрытый объект;</span><span class="sxs-lookup"><span data-stu-id="3a5cb-105">An out-of-process component invoked a call-back method on its client and attempted to pass a reference to a private object.</span></span>  
  
- <span data-ttu-id="3a5cb-106">внепроцессный компонент предпринял попытку передать ссылку на закрытый объект в качестве аргумента события, которые он вызывал;</span><span class="sxs-lookup"><span data-stu-id="3a5cb-106">An out-of-process component attempted to pass a reference to a private object as an argument of an event it was raising.</span></span>  
  
- <span data-ttu-id="3a5cb-107">клиент предпринял попытку назначить ссылку на закрытый объект для аргумента `ByRef` события, которое он обрабатывал.</span><span class="sxs-lookup"><span data-stu-id="3a5cb-107">A client attempted to assign a private object reference to a `ByRef` argument of an event it was handling.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3a5cb-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="3a5cb-108">To correct this error</span></span>  
  
1. <span data-ttu-id="3a5cb-109">Удалите ссылку.</span><span class="sxs-lookup"><span data-stu-id="3a5cb-109">Remove the reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a5cb-110">См. также</span><span class="sxs-lookup"><span data-stu-id="3a5cb-110">See also</span></span>

- [<span data-ttu-id="3a5cb-111">Закрытые</span><span class="sxs-lookup"><span data-stu-id="3a5cb-111">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
