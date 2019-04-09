---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: 331c63dc290d4096e8158f265ee869b47743a273
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151779"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="747aa-102">Protected Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="747aa-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="747aa-103">Комбинация ключевых слов `Protected Friend` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="747aa-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="747aa-104">Он предоставляет оба [Friend](friend.md) доступа и [Protected](protected.md) доступ к объявленным элементам, поэтому они доступны в любом месте той же сборки, из собственного класса, а также из производных классов.</span><span class="sxs-lookup"><span data-stu-id="747aa-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="747aa-105">Можно указать `Protected Friend` только для членов классов; нельзя применить `Protected Friend` к членам структуры, так как структуры не может быть унаследован.</span><span class="sxs-lookup"><span data-stu-id="747aa-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="747aa-106">В Visual Studio, выбрав Справка F1 на `protected friend` предоставляет справку для любого [защищенные](protected.md) или [friend](friend.md).</span><span class="sxs-lookup"><span data-stu-id="747aa-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="747aa-107">Интегрированная среда разработки выбирает один токен в курсор, а не составное слово.</span><span class="sxs-lookup"><span data-stu-id="747aa-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="747aa-108">Правила</span><span class="sxs-lookup"><span data-stu-id="747aa-108">Rules</span></span>

- **<span data-ttu-id="747aa-109">Контекст объявления.</span><span class="sxs-lookup"><span data-stu-id="747aa-109">Declaration Context.</span></span>** <span data-ttu-id="747aa-110">Можно использовать `Protected Friend` только на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="747aa-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="747aa-111">Это означает, что контекст объявления для `Protected` элемент должен быть классом и не может быть исходный файл, пространство имен, интерфейс, модуль, структуру или процедуры.</span><span class="sxs-lookup"><span data-stu-id="747aa-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span> 

## <a name="see-also"></a><span data-ttu-id="747aa-112">См. также</span><span class="sxs-lookup"><span data-stu-id="747aa-112">See also</span></span>

- [<span data-ttu-id="747aa-113">Public</span><span class="sxs-lookup"><span data-stu-id="747aa-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="747aa-114">Защищенный</span><span class="sxs-lookup"><span data-stu-id="747aa-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="747aa-115">Friend</span><span class="sxs-lookup"><span data-stu-id="747aa-115">Friend</span></span>](friend.md)
- [<span data-ttu-id="747aa-116">Private</span><span class="sxs-lookup"><span data-stu-id="747aa-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="747aa-117">Частный защищенный</span><span class="sxs-lookup"><span data-stu-id="747aa-117">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="747aa-118">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="747aa-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="747aa-119">Процедуры</span><span class="sxs-lookup"><span data-stu-id="747aa-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="747aa-120">Структуры</span><span class="sxs-lookup"><span data-stu-id="747aa-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="747aa-121">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="747aa-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
