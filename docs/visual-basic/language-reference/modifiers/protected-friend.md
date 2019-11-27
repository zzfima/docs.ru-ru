---
title: Protected Friend
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: f92021f5f0dab9762470c270bdd5182187d587e5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351321"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="bf591-102">Protected Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf591-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="bf591-103">Комбинация ключевых слов `Protected Friend` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="bf591-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="bf591-104">Он предоставляет [дружественный](friend.md) доступ и [защищенный](protected.md) доступ к объявленным элементам, поэтому они доступны из любого места в одной сборке, из их собственного класса и из производных классов.</span><span class="sxs-lookup"><span data-stu-id="bf591-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="bf591-105">Можно указать `Protected Friend` только для членов классов; к членам структуры нельзя применять `Protected Friend`, поскольку структуры не могут наследоваться.</span><span class="sxs-lookup"><span data-stu-id="bf591-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="bf591-106">В Visual Studio выбор справки F1 в `protected friend` предоставляет справку для [защищенного](protected.md) или [дружественного](friend.md)доступа.</span><span class="sxs-lookup"><span data-stu-id="bf591-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="bf591-107">Интегрированная среда разработки выбирает один маркер под курсором, а не составное слово.</span><span class="sxs-lookup"><span data-stu-id="bf591-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="bf591-108">Правила</span><span class="sxs-lookup"><span data-stu-id="bf591-108">Rules</span></span>

<span data-ttu-id="bf591-109">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="bf591-109">**Declaration Context.**</span></span> <span data-ttu-id="bf591-110">`Protected Friend` можно использовать только на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="bf591-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="bf591-111">Это означает, что контекст объявления для элемента `Protected` должен быть классом и не может быть исходным файлом, пространством имен, интерфейсом, модулем, структурой или процедурой.</span><span class="sxs-lookup"><span data-stu-id="bf591-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf591-112">См. также</span><span class="sxs-lookup"><span data-stu-id="bf591-112">See also</span></span>

- [<span data-ttu-id="bf591-113">Public</span><span class="sxs-lookup"><span data-stu-id="bf591-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="bf591-114">Protected</span><span class="sxs-lookup"><span data-stu-id="bf591-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="bf591-115">Friend</span><span class="sxs-lookup"><span data-stu-id="bf591-115">Friend</span></span>](friend.md)
- [<span data-ttu-id="bf591-116">Закрытые</span><span class="sxs-lookup"><span data-stu-id="bf591-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="bf591-117">Private Protected</span><span class="sxs-lookup"><span data-stu-id="bf591-117">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="bf591-118">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bf591-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="bf591-119">Процедуры</span><span class="sxs-lookup"><span data-stu-id="bf591-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="bf591-120">Структуры</span><span class="sxs-lookup"><span data-stu-id="bf591-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="bf591-121">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="bf591-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
