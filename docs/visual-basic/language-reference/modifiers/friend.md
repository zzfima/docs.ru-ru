---
title: Friend (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
ms.openlocfilehash: 3e30267c8aa11ce97b3b3064ff0954378dab57af
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959804"
---
# <a name="friend-visual-basic"></a><span data-ttu-id="a65d2-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a65d2-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="a65d2-103">Указывает, что один или несколько объявленных программных элементов доступны только в пределах сборки, содержащей их объявление.</span><span class="sxs-lookup"><span data-stu-id="a65d2-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a65d2-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="a65d2-104">Remarks</span></span>  
 <span data-ttu-id="a65d2-105">Во многих случаях требуется, чтобы элементы программирования, такие как классы и структуры, использовались целой сборкой, а не только компонентом, который их объявляет.</span><span class="sxs-lookup"><span data-stu-id="a65d2-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="a65d2-106">Однако может быть нежелательно, чтобы они были доступны коду за пределами сборки (например, если приложение является собственным).</span><span class="sxs-lookup"><span data-stu-id="a65d2-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="a65d2-107">Если требуется ограничить доступ к элементу таким образом, его можно объявить с помощью `Friend` модификатора.</span><span class="sxs-lookup"><span data-stu-id="a65d2-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="a65d2-108">Код в других классах, структурах и модулях, компилируемых в одну и ту же сборку `Friend` , может обращаться ко всем элементам в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="a65d2-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="a65d2-109">`Friend`доступ часто является предпочтительным уровнем для программных элементов приложения, а `Friend` также уровнем доступа по умолчанию для интерфейса, модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="a65d2-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="a65d2-110">Можно использовать `Friend` только на уровне модуля, интерфейса или пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a65d2-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="a65d2-111">Таким образом, контекст объявления для `Friend` элемента должен быть исходным файлом, пространством имен, интерфейсом, модулем, классом или структурой. он не может быть процедурой.</span><span class="sxs-lookup"><span data-stu-id="a65d2-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  

> [!NOTE]
> <span data-ttu-id="a65d2-112">Можно также использовать модификатор доступа [Protected Friend](protected-friend.md) , который делает член класса доступным из этого класса, из производных классов и из той же сборки, в которой определен класс.</span><span class="sxs-lookup"><span data-stu-id="a65d2-112">You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> <span data-ttu-id="a65d2-113">Для ограничения доступа к члену из его класса и из производных классов в той же сборке используется модификатор [закрытого](private-protected.md) доступа.</span><span class="sxs-lookup"><span data-stu-id="a65d2-113">To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.</span></span>

 <span data-ttu-id="a65d2-114">Сравнение `Friend` и других модификаторов доступа см. [в разделе уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a65d2-114">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a65d2-115">Можно указать, что другая сборка является дружественной, что позволяет ей получить доступ ко всем типам и членам, помеченным как `Friend`.</span><span class="sxs-lookup"><span data-stu-id="a65d2-115">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="a65d2-116">Дополнительные сведения см. в разделе [Дружественные сборки](../../../standard/assembly/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="a65d2-116">For more information, see [Friend Assemblies](../../../standard/assembly/friend-assemblies.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a65d2-117">Пример</span><span class="sxs-lookup"><span data-stu-id="a65d2-117">Example</span></span>  
 <span data-ttu-id="a65d2-118">Следующий класс использует `Friend` модификатор, чтобы разрешить другим элементам программирования в той же сборке доступ к определенным элементам.</span><span class="sxs-lookup"><span data-stu-id="a65d2-118">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a><span data-ttu-id="a65d2-119">Использование</span><span class="sxs-lookup"><span data-stu-id="a65d2-119">Usage</span></span>  
 <span data-ttu-id="a65d2-120">`Friend` Модификатор можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="a65d2-120">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="a65d2-121">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="a65d2-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="a65d2-122">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="a65d2-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="a65d2-123">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="a65d2-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="a65d2-124">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="a65d2-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="a65d2-125">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="a65d2-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="a65d2-126">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="a65d2-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="a65d2-127">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="a65d2-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="a65d2-128">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="a65d2-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="a65d2-129">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="a65d2-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="a65d2-130">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="a65d2-130">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="a65d2-131">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="a65d2-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="a65d2-132">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="a65d2-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="a65d2-133">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="a65d2-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="a65d2-134">См. также</span><span class="sxs-lookup"><span data-stu-id="a65d2-134">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="a65d2-135">Public</span><span class="sxs-lookup"><span data-stu-id="a65d2-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="a65d2-136">Protected</span><span class="sxs-lookup"><span data-stu-id="a65d2-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="a65d2-137">Закрытые</span><span class="sxs-lookup"><span data-stu-id="a65d2-137">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="a65d2-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="a65d2-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="a65d2-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="a65d2-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="a65d2-140">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a65d2-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="a65d2-141">Процедуры</span><span class="sxs-lookup"><span data-stu-id="a65d2-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="a65d2-142">Структуры</span><span class="sxs-lookup"><span data-stu-id="a65d2-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="a65d2-143">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="a65d2-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
