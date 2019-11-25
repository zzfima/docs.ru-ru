---
title: Shadows
ms.date: 07/20/2015
f1_keywords:
- vb.Shadows
- shadows
helpviewer_keywords:
- shadowing
- duplicate names [Visual Basic]
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic]
- names [Visual Basic], shadowing
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
ms.openlocfilehash: e9a423fa69ad1dcd8c1d4a5b7085e5b5da548f93
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351266"
---
# <a name="shadows-visual-basic"></a><span data-ttu-id="07b9a-102">Shadows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07b9a-102">Shadows (Visual Basic)</span></span>

<span data-ttu-id="07b9a-103">Specifies that a declared programming element redeclares and hides an identically named element, or set of overloaded elements, in a base class.</span><span class="sxs-lookup"><span data-stu-id="07b9a-103">Specifies that a declared programming element redeclares and hides an identically named element, or set of overloaded elements, in a base class.</span></span>

## <a name="remarks"></a><span data-ttu-id="07b9a-104">Заметки</span><span class="sxs-lookup"><span data-stu-id="07b9a-104">Remarks</span></span>

<span data-ttu-id="07b9a-105">The main purpose of shadowing (which is also known as *hiding by name*) is to preserve the definition of your class members.</span><span class="sxs-lookup"><span data-stu-id="07b9a-105">The main purpose of shadowing (which is also known as *hiding by name*) is to preserve the definition of your class members.</span></span> <span data-ttu-id="07b9a-106">The base class might undergo a change that creates an element with the same name as one you have already defined.</span><span class="sxs-lookup"><span data-stu-id="07b9a-106">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="07b9a-107">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span><span class="sxs-lookup"><span data-stu-id="07b9a-107">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>

<span data-ttu-id="07b9a-108">Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия.</span><span class="sxs-lookup"><span data-stu-id="07b9a-108">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="07b9a-109">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="07b9a-109">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>

## <a name="rules"></a><span data-ttu-id="07b9a-110">Правила</span><span class="sxs-lookup"><span data-stu-id="07b9a-110">Rules</span></span>

- <span data-ttu-id="07b9a-111">**Declaration Context.**</span><span class="sxs-lookup"><span data-stu-id="07b9a-111">**Declaration Context.**</span></span> <span data-ttu-id="07b9a-112">You can use `Shadows` only at class level.</span><span class="sxs-lookup"><span data-stu-id="07b9a-112">You can use `Shadows` only at class level.</span></span> <span data-ttu-id="07b9a-113">This means the declaration context for a `Shadows` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span><span class="sxs-lookup"><span data-stu-id="07b9a-113">This means the declaration context for a `Shadows` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

  <span data-ttu-id="07b9a-114">You can declare only one shadowing element in a single declaration statement.</span><span class="sxs-lookup"><span data-stu-id="07b9a-114">You can declare only one shadowing element in a single declaration statement.</span></span>

- <span data-ttu-id="07b9a-115">**Combined Modifiers.**</span><span class="sxs-lookup"><span data-stu-id="07b9a-115">**Combined Modifiers.**</span></span> <span data-ttu-id="07b9a-116">You cannot specify `Shadows` together with `Overloads`, `Overrides`, or `Static` in the same declaration.</span><span class="sxs-lookup"><span data-stu-id="07b9a-116">You cannot specify `Shadows` together with `Overloads`, `Overrides`, or `Static` in the same declaration.</span></span>

- <span data-ttu-id="07b9a-117">**Element Types.**</span><span class="sxs-lookup"><span data-stu-id="07b9a-117">**Element Types.**</span></span> <span data-ttu-id="07b9a-118">Можно скрыть любой тип объявленного элемента, используя любой другой тип.</span><span class="sxs-lookup"><span data-stu-id="07b9a-118">You can shadow any kind of declared element with any other kind.</span></span> <span data-ttu-id="07b9a-119">If you shadow a property or procedure with another property or procedure, the parameters and the return type do not have to match those in the base class property or procedure.</span><span class="sxs-lookup"><span data-stu-id="07b9a-119">If you shadow a property or procedure with another property or procedure, the parameters and the return type do not have to match those in the base class property or procedure.</span></span>

- <span data-ttu-id="07b9a-120">**Accessing.**</span><span class="sxs-lookup"><span data-stu-id="07b9a-120">**Accessing.**</span></span> <span data-ttu-id="07b9a-121">The shadowed element in the base class is normally unavailable from within the derived class that shadows it.</span><span class="sxs-lookup"><span data-stu-id="07b9a-121">The shadowed element in the base class is normally unavailable from within the derived class that shadows it.</span></span> <span data-ttu-id="07b9a-122">However, the following considerations apply.</span><span class="sxs-lookup"><span data-stu-id="07b9a-122">However, the following considerations apply.</span></span>

  - <span data-ttu-id="07b9a-123">If the shadowing element is not accessible from the code referring to it, the reference is resolved to the shadowed element.</span><span class="sxs-lookup"><span data-stu-id="07b9a-123">If the shadowing element is not accessible from the code referring to it, the reference is resolved to the shadowed element.</span></span> <span data-ttu-id="07b9a-124">For example, if a `Private` element shadows a base class element, code that does not have permission to access the `Private` element accesses the base class element instead.</span><span class="sxs-lookup"><span data-stu-id="07b9a-124">For example, if a `Private` element shadows a base class element, code that does not have permission to access the `Private` element accesses the base class element instead.</span></span>

  - <span data-ttu-id="07b9a-125">If you shadow an element, you can still access the shadowed element through an object declared with the type of the base class.</span><span class="sxs-lookup"><span data-stu-id="07b9a-125">If you shadow an element, you can still access the shadowed element through an object declared with the type of the base class.</span></span> <span data-ttu-id="07b9a-126">You can also access it through `MyBase`.</span><span class="sxs-lookup"><span data-stu-id="07b9a-126">You can also access it through `MyBase`.</span></span>

<span data-ttu-id="07b9a-127">Модификатор `Shadows` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="07b9a-127">The `Shadows` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="07b9a-128">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="07b9a-128">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)

- [<span data-ttu-id="07b9a-129">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="07b9a-129">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="07b9a-130">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="07b9a-130">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- [<span data-ttu-id="07b9a-131">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="07b9a-131">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)

- [<span data-ttu-id="07b9a-132">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="07b9a-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- [<span data-ttu-id="07b9a-133">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="07b9a-133">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)

- [<span data-ttu-id="07b9a-134">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="07b9a-134">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="07b9a-135">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="07b9a-135">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- [<span data-ttu-id="07b9a-136">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="07b9a-136">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)

- [<span data-ttu-id="07b9a-137">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="07b9a-137">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- [<span data-ttu-id="07b9a-138">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="07b9a-138">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)

- [<span data-ttu-id="07b9a-139">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="07b9a-139">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="07b9a-140">См. также</span><span class="sxs-lookup"><span data-stu-id="07b9a-140">See also</span></span>

- [<span data-ttu-id="07b9a-141">Общие</span><span class="sxs-lookup"><span data-stu-id="07b9a-141">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="07b9a-142">Статические</span><span class="sxs-lookup"><span data-stu-id="07b9a-142">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="07b9a-143">Закрытые</span><span class="sxs-lookup"><span data-stu-id="07b9a-143">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="07b9a-144">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="07b9a-144">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="07b9a-145">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="07b9a-145">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="07b9a-146">MustOverride</span><span class="sxs-lookup"><span data-stu-id="07b9a-146">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="07b9a-147">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="07b9a-147">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="07b9a-148">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="07b9a-148">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="07b9a-149">Переопределяемые</span><span class="sxs-lookup"><span data-stu-id="07b9a-149">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="07b9a-150">Переопределения</span><span class="sxs-lookup"><span data-stu-id="07b9a-150">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="07b9a-151">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="07b9a-151">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
