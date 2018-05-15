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
ms.openlocfilehash: 756a18da74ff49cbefaf6a63980302bbcb141713
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="friend-visual-basic"></a><span data-ttu-id="13814-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13814-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="13814-103">Указывает, что один или несколько объявленных программных элементов доступны только из внутри сборки, содержащей их объявления.</span><span class="sxs-lookup"><span data-stu-id="13814-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13814-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="13814-104">Remarks</span></span>  
 <span data-ttu-id="13814-105">Во многих случаях требуется программных элементов, таких как классы и структуры, используемые всей сборке, не только компонентом, который объявляет их.</span><span class="sxs-lookup"><span data-stu-id="13814-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="13814-106">Тем не менее могут не хотелось бы быть доступны для кода за пределами сборки (например, если приложение является собственным).</span><span class="sxs-lookup"><span data-stu-id="13814-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="13814-107">Если вы хотите ограничить доступ к элементу таким образом, можно объявить его с помощью `Friend` модификатор.</span><span class="sxs-lookup"><span data-stu-id="13814-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="13814-108">Код в других классах, структурах и модули, скомпилированные с тем же сборке может получать доступ ко всем `Friend` элементы в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="13814-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="13814-109">`Friend` доступ часто является предпочтительным уровнем для элементов программирования приложений, и `Friend` — доступ по умолчанию уровне интерфейса, модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="13814-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="13814-110">Можно использовать `Friend` только на уровне модуля, интерфейсом или пространством имен.</span><span class="sxs-lookup"><span data-stu-id="13814-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="13814-111">Таким образом, что контекст объявления для `Friend` элемент должен быть исходный файл, пространство имен, интерфейсом, модуля, класса или структуры; он не может быть процедурой.</span><span class="sxs-lookup"><span data-stu-id="13814-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  
  
 <span data-ttu-id="13814-112">Можно использовать `Friend` модификатор вместе с [Protected](../../../visual-basic/language-reference/modifiers/protected.md) модификатор в объявлении.</span><span class="sxs-lookup"><span data-stu-id="13814-112">You can use the `Friend` modifier in conjunction with the [Protected](../../../visual-basic/language-reference/modifiers/protected.md) modifier in the same declaration.</span></span> <span data-ttu-id="13814-113">Указанное сочетание задает оба `Friend` доступа и защищенный доступ к объявленным элементам, поэтому они доступны в любом месте той же сборки, из собственного класса и из производных классов.</span><span class="sxs-lookup"><span data-stu-id="13814-113">This combination confers both `Friend` access and protected access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="13814-114">Можно указать `Protected Friend` только для членов классов.</span><span class="sxs-lookup"><span data-stu-id="13814-114">You can specify `Protected Friend` only on members of classes.</span></span>  
  
 <span data-ttu-id="13814-115">Сравнение `Friend` и другие модификаторы доступа см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="13814-115">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13814-116">Можно указать, что другая сборка является дружественной сборки, что позволяет получить доступ к все типы и члены, помеченные как `Friend`.</span><span class="sxs-lookup"><span data-stu-id="13814-116">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="13814-117">Дополнительные сведения см. в разделе [Дружественные сборки](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="13814-117">For more information, see [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="13814-118">Пример</span><span class="sxs-lookup"><span data-stu-id="13814-118">Example</span></span>  
 <span data-ttu-id="13814-119">Следующий класс использует `Friend` модификатор, чтобы разрешить другими элементами программирования в одной и той же сборки для доступа к определенным элементам.</span><span class="sxs-lookup"><span data-stu-id="13814-119">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/friend_1.vb)]  
  
## <a name="usage"></a><span data-ttu-id="13814-120">Использование</span><span class="sxs-lookup"><span data-stu-id="13814-120">Usage</span></span>  
 <span data-ttu-id="13814-121">Можно использовать `Friend` модификатор в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="13814-121">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="13814-122">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="13814-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="13814-123">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="13814-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="13814-124">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="13814-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="13814-125">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="13814-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="13814-126">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="13814-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="13814-127">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="13814-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="13814-128">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="13814-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="13814-129">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="13814-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="13814-130">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="13814-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="13814-131">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="13814-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="13814-132">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="13814-132">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="13814-133">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="13814-133">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="13814-134">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="13814-134">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="13814-135">См. также</span><span class="sxs-lookup"><span data-stu-id="13814-135">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [<span data-ttu-id="13814-136">Public</span><span class="sxs-lookup"><span data-stu-id="13814-136">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="13814-137">Protected</span><span class="sxs-lookup"><span data-stu-id="13814-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="13814-138">Закрытые</span><span class="sxs-lookup"><span data-stu-id="13814-138">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="13814-139">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="13814-139">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="13814-140">Процедуры</span><span class="sxs-lookup"><span data-stu-id="13814-140">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="13814-141">Структуры</span><span class="sxs-lookup"><span data-stu-id="13814-141">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="13814-142">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="13814-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
