---
title: Метод <methodname> несколько раз определен с одинаковыми подписями
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: fe8d1d8e11e25bcd79894ed82a57dd06748c3d68
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831882"
---
# <a name="methodname-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="1795c-102">"\<имя_метода >" имеет несколько определений с одинаковыми сигнатурами</span><span class="sxs-lookup"><span data-stu-id="1795c-102">'\<methodname>' has multiple definitions with identical signatures</span></span>
<span data-ttu-id="1795c-103">Объект `Function` или `Sub` в объявлении процедуры используются одинаковые процедуры имя и список аргументов, как и в предыдущем объявлении.</span><span class="sxs-lookup"><span data-stu-id="1795c-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="1795c-104">Одной из возможных причин является попытка перегрузить исходный текст процедуры.</span><span class="sxs-lookup"><span data-stu-id="1795c-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="1795c-105">Перегруженные процедуры должны иметь разные списки аргументов.</span><span class="sxs-lookup"><span data-stu-id="1795c-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="1795c-106">**Идентификатор ошибки:** BC30269</span><span class="sxs-lookup"><span data-stu-id="1795c-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1795c-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="1795c-107">To correct this error</span></span>  
  
-   <span data-ttu-id="1795c-108">Измените имя процедуры или список аргументов, или удалите повторяющееся объявление.</span><span class="sxs-lookup"><span data-stu-id="1795c-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1795c-109">См. также</span><span class="sxs-lookup"><span data-stu-id="1795c-109">See also</span></span>

- [<span data-ttu-id="1795c-110">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="1795c-110">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="1795c-111">Вопросы, связанные с перегрузкой процедур</span><span class="sxs-lookup"><span data-stu-id="1795c-111">Considerations in Overloading Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
