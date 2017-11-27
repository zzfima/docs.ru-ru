---
title: "Структура &#39; &lt;имя_структуры&gt;&#39; должна содержать по крайней мере один экземпляр переменной-члена или объявление события по крайней мере один экземпляр не помечен &#39; Настраиваемый &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords: BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b28dd59271bdaca52072710ea797fae6e9168eab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a><span data-ttu-id="b60f6-102">Структура &#39; &lt;имя_структуры&gt;&#39; должна содержать по крайней мере один экземпляр переменной-члена или объявление события по крайней мере один экземпляр не помечен &#39; Настраиваемый &#39;</span><span class="sxs-lookup"><span data-stu-id="b60f6-102">Structure &#39;&lt;structurename&gt;&#39; must contain at least one instance member variable or at least one instance event declaration not marked &#39;Custom&#39;</span></span>
<span data-ttu-id="b60f6-103">Определение структуры не включает неиспользуемые совместно переменные или обычные события.</span><span class="sxs-lookup"><span data-stu-id="b60f6-103">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>  
  
 <span data-ttu-id="b60f6-104">Каждая структура должна иметь переменную либо событие, которое применяется к каждому определенному экземпляру (неиспользуемому совместно), а не ко всем экземплярам совокупности ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span><span class="sxs-lookup"><span data-stu-id="b60f6-104">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span></span> <span data-ttu-id="b60f6-105">Неиспользуемые совместно константы, свойства и процедуры не удовлетворяют этим требованиям.</span><span class="sxs-lookup"><span data-stu-id="b60f6-105">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="b60f6-106">Кроме того, если нет неиспользуемых совместно переменных и только одно событие, не являющихся общими, это событие не может быть `Custom` событий.</span><span class="sxs-lookup"><span data-stu-id="b60f6-106">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>  
  
 <span data-ttu-id="b60f6-107">**Идентификатор ошибки:** BC30941</span><span class="sxs-lookup"><span data-stu-id="b60f6-107">**Error ID:** BC30941</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b60f6-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="b60f6-108">To correct this error</span></span>  
  
-   <span data-ttu-id="b60f6-109">Определите по крайней мере одну переменную или событие, которое не `Shared`.</span><span class="sxs-lookup"><span data-stu-id="b60f6-109">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="b60f6-110">Если определить только одно событие, должен быть являющуюся, а также не являющихся общими.</span><span class="sxs-lookup"><span data-stu-id="b60f6-110">If you define only one event, it must be noncustom as well as nonshared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b60f6-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b60f6-111">See Also</span></span>  
 [<span data-ttu-id="b60f6-112">Структуры</span><span class="sxs-lookup"><span data-stu-id="b60f6-112">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="b60f6-113">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="b60f6-113">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="b60f6-114">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="b60f6-114">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
