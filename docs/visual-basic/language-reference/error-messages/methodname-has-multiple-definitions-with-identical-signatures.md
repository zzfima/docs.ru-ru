---
title: '&#39; &lt;имя_метода&gt;&#39; имеет несколько определений с одинаковыми сигнатурами'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1a71d51690d6318a559a94ac81de625289d7587d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="39ltmethodnamegt39-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="1707c-102">&#39; &lt;имя_метода&gt;&#39; имеет несколько определений с одинаковыми сигнатурами</span><span class="sxs-lookup"><span data-stu-id="1707c-102">&#39;&lt;methodname&gt;&#39; has multiple definitions with identical signatures</span></span>
<span data-ttu-id="1707c-103">Объект `Function` или `Sub` в объявлении процедуры используются процедуры одинаковые имя и список аргументов, как и в предыдущем объявлении.</span><span class="sxs-lookup"><span data-stu-id="1707c-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="1707c-104">Возможной причиной этого может быть попытка перегрузки исходной процедуры.</span><span class="sxs-lookup"><span data-stu-id="1707c-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="1707c-105">Перегруженные процедуры должны иметь разные списки аргументов.</span><span class="sxs-lookup"><span data-stu-id="1707c-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="1707c-106">**Идентификатор ошибки:** BC30269</span><span class="sxs-lookup"><span data-stu-id="1707c-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1707c-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="1707c-107">To correct this error</span></span>  
  
-   <span data-ttu-id="1707c-108">Измените имя процедуры или список аргументов или удалите повторяющееся объявление.</span><span class="sxs-lookup"><span data-stu-id="1707c-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1707c-109">См. также</span><span class="sxs-lookup"><span data-stu-id="1707c-109">See Also</span></span>  
 [<span data-ttu-id="1707c-110">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="1707c-110">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="1707c-111">Вопросы, связанные с перегрузкой процедур</span><span class="sxs-lookup"><span data-stu-id="1707c-111">Considerations in Overloading Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
