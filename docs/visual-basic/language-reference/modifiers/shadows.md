---
title: Shadows (Visual Basic)
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
ms.openlocfilehash: bbad42a2bffc397696a8da51bcdf86ebc5ff4ca6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647676"
---
# <a name="shadows-visual-basic"></a><span data-ttu-id="c1040-102">Shadows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1040-102">Shadows (Visual Basic)</span></span>
<span data-ttu-id="c1040-103">Указывает, что объявленный программный элемент повторно объявляет и скрывает одинаково названные элементы или набор перегруженных элементов в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="c1040-103">Specifies that a declared programming element redeclares and hides an identically named element, or set of overloaded elements, in a base class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1040-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="c1040-104">Remarks</span></span>  
 <span data-ttu-id="c1040-105">Основная цель затенение (который также называется *скрытие по имени*) — Сохранение определения членов класса.</span><span class="sxs-lookup"><span data-stu-id="c1040-105">The main purpose of shadowing (which is also known as *hiding by name*) is to preserve the definition of your class members.</span></span> <span data-ttu-id="c1040-106">Базовый класс может претерпеть изменения, создается элемент с тем же именем, как один, которые вы уже определили.</span><span class="sxs-lookup"><span data-stu-id="c1040-106">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="c1040-107">В этом случае `Shadows` применении модификатора ссылается в классе быть член определенный, а не к новому элементу базового класса.</span><span class="sxs-lookup"><span data-stu-id="c1040-107">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
 <span data-ttu-id="c1040-108">Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия.</span><span class="sxs-lookup"><span data-stu-id="c1040-108">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="c1040-109">Дополнительные сведения см. в разделе [сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="c1040-109">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="c1040-110">Правила</span><span class="sxs-lookup"><span data-stu-id="c1040-110">Rules</span></span>  
  
- <span data-ttu-id="c1040-111">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="c1040-111">**Declaration Context.**</span></span> <span data-ttu-id="c1040-112">Можно использовать `Shadows` только на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="c1040-112">You can use `Shadows` only at class level.</span></span> <span data-ttu-id="c1040-113">Это означает, что контекст объявления для `Shadows` элемент должен быть классом и не может быть исходный файл, пространство имен, интерфейс, модуль, структуру или процедуры.</span><span class="sxs-lookup"><span data-stu-id="c1040-113">This means the declaration context for a `Shadows` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>  
  
     <span data-ttu-id="c1040-114">Можно объявить только один затененный элемент в одном операторе объявления.</span><span class="sxs-lookup"><span data-stu-id="c1040-114">You can declare only one shadowing element in a single declaration statement.</span></span>  
  
- <span data-ttu-id="c1040-115">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="c1040-115">**Combined Modifiers.**</span></span> <span data-ttu-id="c1040-116">Нельзя указать `Shadows` вместе с `Overloads`, `Overrides`, или `Static` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="c1040-116">You cannot specify `Shadows` together with `Overloads`, `Overrides`, or `Static` in the same declaration.</span></span>  
  
- <span data-ttu-id="c1040-117">**Типы элементов.**</span><span class="sxs-lookup"><span data-stu-id="c1040-117">**Element Types.**</span></span> <span data-ttu-id="c1040-118">Можно скрыть любой тип объявленного элемента, используя любой другой тип.</span><span class="sxs-lookup"><span data-stu-id="c1040-118">You can shadow any kind of declared element with any other kind.</span></span> <span data-ttu-id="c1040-119">При скрытии свойства или процедуры с другое свойство или процедура, параметры и тип возвращаемого значения имеют для получения соответствия строкам в процедуру или свойство базового класса.</span><span class="sxs-lookup"><span data-stu-id="c1040-119">If you shadow a property or procedure with another property or procedure, the parameters and the return type do not have to match those in the base class property or procedure.</span></span>  
  
- <span data-ttu-id="c1040-120">**Доступ к.**</span><span class="sxs-lookup"><span data-stu-id="c1040-120">**Accessing.**</span></span> <span data-ttu-id="c1040-121">Затененный элемент в базовом классе обычно недоступен из производного класса, который его скрывает.</span><span class="sxs-lookup"><span data-stu-id="c1040-121">The shadowed element in the base class is normally unavailable from within the derived class that shadows it.</span></span> <span data-ttu-id="c1040-122">Тем не менее следующие соображения.</span><span class="sxs-lookup"><span data-stu-id="c1040-122">However, the following considerations apply.</span></span>  
  
    - <span data-ttu-id="c1040-123">Если скрывающий элемент недоступен из кода, обращения к нему, ссылка разрешается переопределяемый элемент.</span><span class="sxs-lookup"><span data-stu-id="c1040-123">If the shadowing element is not accessible from the code referring to it, the reference is resolved to the shadowed element.</span></span> <span data-ttu-id="c1040-124">Например если `Private` элемент скрывает элемент базового класса, код, который не имеет разрешения на доступ к `Private` элемент обращается к элементу базового класса.</span><span class="sxs-lookup"><span data-stu-id="c1040-124">For example, if a `Private` element shadows a base class element, code that does not have permission to access the `Private` element accesses the base class element instead.</span></span>  
  
    - <span data-ttu-id="c1040-125">При скрытии элемент скрыт элемент можно получить доступ через объект объявлен с типом базового класса.</span><span class="sxs-lookup"><span data-stu-id="c1040-125">If you shadow an element, you can still access the shadowed element through an object declared with the type of the base class.</span></span> <span data-ttu-id="c1040-126">Также доступен через `MyBase`.</span><span class="sxs-lookup"><span data-stu-id="c1040-126">You can also access it through `MyBase`.</span></span>  
  
 <span data-ttu-id="c1040-127">Модификатор `Shadows` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="c1040-127">The `Shadows` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="c1040-128">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="c1040-128">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="c1040-129">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="c1040-129">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="c1040-130">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="c1040-130">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="c1040-131">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="c1040-131">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="c1040-132">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="c1040-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="c1040-133">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="c1040-133">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="c1040-134">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="c1040-134">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="c1040-135">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="c1040-135">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="c1040-136">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="c1040-136">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="c1040-137">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="c1040-137">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="c1040-138">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="c1040-138">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="c1040-139">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="c1040-139">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="c1040-140">См. также</span><span class="sxs-lookup"><span data-stu-id="c1040-140">See also</span></span>

- [<span data-ttu-id="c1040-141">Общие</span><span class="sxs-lookup"><span data-stu-id="c1040-141">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="c1040-142">Статические</span><span class="sxs-lookup"><span data-stu-id="c1040-142">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="c1040-143">Закрытые</span><span class="sxs-lookup"><span data-stu-id="c1040-143">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="c1040-144">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="c1040-144">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="c1040-145">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="c1040-145">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="c1040-146">MustOverride</span><span class="sxs-lookup"><span data-stu-id="c1040-146">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="c1040-147">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="c1040-147">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="c1040-148">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="c1040-148">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="c1040-149">Переопределяемые</span><span class="sxs-lookup"><span data-stu-id="c1040-149">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="c1040-150">Переопределения</span><span class="sxs-lookup"><span data-stu-id="c1040-150">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="c1040-151">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c1040-151">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
