---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: b72cbee0394043620e792d1c014bfe55121e175e
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/18/2018
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="d2de0-102">Protected Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2de0-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="d2de0-103">`Protected Friend` Сочетание ключевых слов — это модификатор доступа члена.</span><span class="sxs-lookup"><span data-stu-id="d2de0-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="d2de0-104">Он предоставляет оба [Friend](friend.md) доступа и [Protected](protected.md) доступ на объявленные элементы, поэтому они доступны в любом месте той же сборки, из собственного класса и из производных классов.</span><span class="sxs-lookup"><span data-stu-id="d2de0-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="d2de0-105">Можно указать `Protected Friend` только для членов классов; не удается применить `Protected Friend` к членам структуры, так как структуры не наследуется.</span><span class="sxs-lookup"><span data-stu-id="d2de0-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="d2de0-106">В Visual Studio, выбрав Справка F1 на `protected friend` предоставляет справку для любого [защищенных](protected.md) или [friend](friend.md).</span><span class="sxs-lookup"><span data-stu-id="d2de0-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="d2de0-107">Интегрированная среда разработки выбирает один токен в курсор, а не составное слово.</span><span class="sxs-lookup"><span data-stu-id="d2de0-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="d2de0-108">Правила</span><span class="sxs-lookup"><span data-stu-id="d2de0-108">Rules</span></span>

- <span data-ttu-id="d2de0-109">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="d2de0-109">**Declaration Context.**</span></span> <span data-ttu-id="d2de0-110">Можно использовать `Protected Friend` только на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="d2de0-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="d2de0-111">Это означает, что контекст объявления для `Protected` элемент должен быть классом и не может быть исходный файл, пространство имен, интерфейса, модуля, структуры или процедуры.</span><span class="sxs-lookup"><span data-stu-id="d2de0-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span> 


## <a name="see-also"></a><span data-ttu-id="d2de0-112">См. также</span><span class="sxs-lookup"><span data-stu-id="d2de0-112">See Also</span></span>

[<span data-ttu-id="d2de0-113">Public</span><span class="sxs-lookup"><span data-stu-id="d2de0-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
[<span data-ttu-id="d2de0-114">Protected</span><span class="sxs-lookup"><span data-stu-id="d2de0-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
<span data-ttu-id="d2de0-115">[Friend](friend.md) </span><span class="sxs-lookup"><span data-stu-id="d2de0-115">[Friend](friend.md) </span></span>  
[<span data-ttu-id="d2de0-116">Закрытые</span><span class="sxs-lookup"><span data-stu-id="d2de0-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
<span data-ttu-id="d2de0-117">[Protected Private](./private-protected.md) </span><span class="sxs-lookup"><span data-stu-id="d2de0-117">[Private Protected](./private-protected.md) </span></span>  
[<span data-ttu-id="d2de0-118">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d2de0-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[<span data-ttu-id="d2de0-119">Процедуры</span><span class="sxs-lookup"><span data-stu-id="d2de0-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[<span data-ttu-id="d2de0-120">Структуры</span><span class="sxs-lookup"><span data-stu-id="d2de0-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[<span data-ttu-id="d2de0-121">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="d2de0-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
