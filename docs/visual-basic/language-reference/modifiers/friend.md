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
ms.openlocfilehash: 9be3200300de308a70559536905d1e118a4a5fe4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616203"
---
# <a name="friend-visual-basic"></a><span data-ttu-id="dc214-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dc214-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="dc214-103">Указывает, что один или несколько объявленных программных элементов доступны только внутри сборки, которая содержит их объявления.</span><span class="sxs-lookup"><span data-stu-id="dc214-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc214-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="dc214-104">Remarks</span></span>  
 <span data-ttu-id="dc214-105">Во многих случаях требуется программных элементов, таких как классы и структуры, используемые для всей сборки не только компонент, который объявляет их.</span><span class="sxs-lookup"><span data-stu-id="dc214-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="dc214-106">Тем не менее вы не можете их доступными коду вне сборки (например, если приложение является собственным).</span><span class="sxs-lookup"><span data-stu-id="dc214-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="dc214-107">Если вы хотите ограничить доступ к элементу таким образом, его можно объявить с помощью `Friend` модификатор.</span><span class="sxs-lookup"><span data-stu-id="dc214-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="dc214-108">Код в другие классы, структуры и модули, скомпилированные в тот же сборки можно получить доступ ко всем `Friend` элементы в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="dc214-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="dc214-109">`Friend` доступ часто является предпочтительным уровнем для элементов программирования приложения, и `Friend` — по умолчанию доступ уровня интерфейса, модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="dc214-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="dc214-110">Можно использовать `Friend` только на уровне модуля, интерфейса или пространства имен.</span><span class="sxs-lookup"><span data-stu-id="dc214-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="dc214-111">Таким образом, что контекст объявления для `Friend` элемент должен быть исходным файлом, пространство имен, интерфейсом, модуля, класса или структуры; не может быть процедуры.</span><span class="sxs-lookup"><span data-stu-id="dc214-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  

> [!NOTE]
> <span data-ttu-id="dc214-112">Можно также использовать [Protected Friend](protected-friend.md) модификатор доступа, что делает член класса, доступный из этого класса из производных классов, а также из той же сборке, в котором определен класс.</span><span class="sxs-lookup"><span data-stu-id="dc214-112">You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> <span data-ttu-id="dc214-113">Чтобы ограничить доступ к элементу из внутри класса и из производных классов в той же сборке, используйте [Private Protected](private-protected.md) модификатор доступа.</span><span class="sxs-lookup"><span data-stu-id="dc214-113">To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.</span></span>

 <span data-ttu-id="dc214-114">Сравнение `Friend` и другие модификаторы доступа, см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="dc214-114">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc214-115">Можно указать, что другой сборки является дружественной сборки, что обеспечивает доступ ко всем типы и члены, помеченные как `Friend`.</span><span class="sxs-lookup"><span data-stu-id="dc214-115">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="dc214-116">Дополнительные сведения см. в разделе [Дружественные сборки](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="dc214-116">For more information, see [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc214-117">Пример</span><span class="sxs-lookup"><span data-stu-id="dc214-117">Example</span></span>  
 <span data-ttu-id="dc214-118">Следующий класс использует `Friend` модификатор, чтобы разрешить другими элементами программирования в той же сборке, для доступа к определенным элементам.</span><span class="sxs-lookup"><span data-stu-id="dc214-118">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/friend_1.vb)]  
  
## <a name="usage"></a><span data-ttu-id="dc214-119">Использование</span><span class="sxs-lookup"><span data-stu-id="dc214-119">Usage</span></span>  
 <span data-ttu-id="dc214-120">Можно использовать `Friend` модификатор в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="dc214-120">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="dc214-121">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="dc214-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="dc214-122">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="dc214-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="dc214-123">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="dc214-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="dc214-124">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="dc214-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="dc214-125">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="dc214-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="dc214-126">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="dc214-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="dc214-127">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="dc214-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="dc214-128">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="dc214-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="dc214-129">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="dc214-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="dc214-130">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="dc214-130">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="dc214-131">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="dc214-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="dc214-132">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="dc214-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="dc214-133">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="dc214-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="dc214-134">См. также</span><span class="sxs-lookup"><span data-stu-id="dc214-134">See also</span></span>
- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="dc214-135">Public</span><span class="sxs-lookup"><span data-stu-id="dc214-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="dc214-136">Protected</span><span class="sxs-lookup"><span data-stu-id="dc214-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="dc214-137">Закрытые</span><span class="sxs-lookup"><span data-stu-id="dc214-137">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="dc214-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="dc214-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="dc214-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="dc214-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="dc214-140">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dc214-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="dc214-141">Процедуры</span><span class="sxs-lookup"><span data-stu-id="dc214-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="dc214-142">Структуры</span><span class="sxs-lookup"><span data-stu-id="dc214-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="dc214-143">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="dc214-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
