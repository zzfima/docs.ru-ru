---
title: Структура &#39; &lt;имя_структуры&gt; &#39; должен содержать по крайней мере один экземпляр переменной-члена или объявление события по крайней мере один экземпляр не помечен &#39;Custom&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 85a4babc808e274a99f2c9faf08a02abf8aa4e93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594504"
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a><span data-ttu-id="42100-102">Структура &#39; &lt;имя_структуры&gt; &#39; должен содержать по крайней мере один экземпляр переменной-члена или объявление события по крайней мере один экземпляр не помечен &#39;Custom&#39;</span><span class="sxs-lookup"><span data-stu-id="42100-102">Structure &#39;&lt;structurename&gt;&#39; must contain at least one instance member variable or at least one instance event declaration not marked &#39;Custom&#39;</span></span>
<span data-ttu-id="42100-103">Определение структуры не включает неиспользуемые совместно переменные или обычные события.</span><span class="sxs-lookup"><span data-stu-id="42100-103">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>  
  
 <span data-ttu-id="42100-104">Каждая структура должна иметь переменную либо событие, которое применяется к каждому определенному экземпляру (неиспользуемому совместно), а не ко всем экземплярам совокупности ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span><span class="sxs-lookup"><span data-stu-id="42100-104">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span></span> <span data-ttu-id="42100-105">Неиспользуемые совместно константы, свойства и процедуры не удовлетворяют этим требованиям.</span><span class="sxs-lookup"><span data-stu-id="42100-105">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="42100-106">Кроме того, если нет неиспользуемых совместно переменных и только одно событие, не являющихся общими, это событие не может быть `Custom` событий.</span><span class="sxs-lookup"><span data-stu-id="42100-106">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>  
  
 <span data-ttu-id="42100-107">**Идентификатор ошибки:** BC30941</span><span class="sxs-lookup"><span data-stu-id="42100-107">**Error ID:** BC30941</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="42100-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="42100-108">To correct this error</span></span>  
  
-   <span data-ttu-id="42100-109">Определите по крайней мере одну переменную или событие, которое не `Shared`.</span><span class="sxs-lookup"><span data-stu-id="42100-109">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="42100-110">Если определить только одно событие, должен быть являющуюся, а также не являющихся общими.</span><span class="sxs-lookup"><span data-stu-id="42100-110">If you define only one event, it must be noncustom as well as nonshared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42100-111">См. также</span><span class="sxs-lookup"><span data-stu-id="42100-111">See Also</span></span>  
 [<span data-ttu-id="42100-112">Структуры</span><span class="sxs-lookup"><span data-stu-id="42100-112">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="42100-113">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="42100-113">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="42100-114">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="42100-114">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
