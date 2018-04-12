---
title: Начальные &#39;. &#39; или &#39;! &#39; может использоваться только внутри &#39; С &#39; инструкции
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 961f2d737123ab68b200d5fc7658cb81291a5de6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a><span data-ttu-id="ce8bf-102">Начальные &#39;. &#39; или &#39;! &#39; может использоваться только внутри &#39; С &#39; инструкции</span><span class="sxs-lookup"><span data-stu-id="ce8bf-102">Leading &#39;.&#39; or &#39;!&#39; can only appear inside a &#39;With&#39; statement</span></span>
<span data-ttu-id="ce8bf-103">Точка (.) или восклицательный знак (!), не находится внутри `With` блок происходит без выражения слева.</span><span class="sxs-lookup"><span data-stu-id="ce8bf-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="ce8bf-104">Доступ к членам (`.`) и доступ к членам словаря (`!`) требуется выражение, задающее элемент, содержащий элемент.</span><span class="sxs-lookup"><span data-stu-id="ce8bf-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="ce8bf-105">Это должно быть расположено слева от метода доступа или в качестве целевого объекта `With` блок, содержащий доступ к члену.</span><span class="sxs-lookup"><span data-stu-id="ce8bf-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="ce8bf-106">**Идентификатор ошибки:** BC30157</span><span class="sxs-lookup"><span data-stu-id="ce8bf-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ce8bf-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ce8bf-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="ce8bf-108">Убедитесь, что `With` блок имеет правильный формат.</span><span class="sxs-lookup"><span data-stu-id="ce8bf-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2.  <span data-ttu-id="ce8bf-109">При наличии не `With` блока, добавьте выражение слева от метода доступа, результатом вычисления элемента, содержащего элемент.</span><span class="sxs-lookup"><span data-stu-id="ce8bf-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce8bf-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ce8bf-110">See Also</span></span>  
 [<span data-ttu-id="ce8bf-111">Специальные символы в коде</span><span class="sxs-lookup"><span data-stu-id="ce8bf-111">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 [<span data-ttu-id="ce8bf-112">Оператор With...End With</span><span class="sxs-lookup"><span data-stu-id="ce8bf-112">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
