---
title: Private (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: d7935cf691d961591ff5e3d2a290afb88de9165a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="private-visual-basic"></a><span data-ttu-id="bf428-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf428-102">Private (Visual Basic)</span></span>
<span data-ttu-id="bf428-103">Указывает, что один или несколько элементов доступны только внутри контекста, включая из любых вложенных типов.</span><span class="sxs-lookup"><span data-stu-id="bf428-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf428-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="bf428-104">Remarks</span></span>  
 <span data-ttu-id="bf428-105">Если элемент программирования представляет особые возможности или содержит конфиденциальные данные, обычно требуется максимально ограничить доступ к нему.</span><span class="sxs-lookup"><span data-stu-id="bf428-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="bf428-106">Максимальное ограничение добиться, позволяя модуля, класса или структуры, которые определяют его для доступа к нему.</span><span class="sxs-lookup"><span data-stu-id="bf428-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="bf428-107">Чтобы ограничить доступ к элементу таким образом, можно объявить его с `Private`.</span><span class="sxs-lookup"><span data-stu-id="bf428-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="bf428-108">Правила</span><span class="sxs-lookup"><span data-stu-id="bf428-108">Rules</span></span>  
  
-   <span data-ttu-id="bf428-109">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="bf428-109">**Declaration Context.**</span></span> <span data-ttu-id="bf428-110">`Private` можно использовать только на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="bf428-110">You can use `Private` only at module level.</span></span> <span data-ttu-id="bf428-111">Это означает, что контекст объявления для `Private` элемент должен быть модуля, класса или структуры и не может быть исходным файлом, пространства имен, интерфейса или процедуры.</span><span class="sxs-lookup"><span data-stu-id="bf428-111">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="bf428-112">Поведение</span><span class="sxs-lookup"><span data-stu-id="bf428-112">Behavior</span></span>  
  
-   <span data-ttu-id="bf428-113">**Уровень доступа.**</span><span class="sxs-lookup"><span data-stu-id="bf428-113">**Access Level.**</span></span> <span data-ttu-id="bf428-114">Весь код в контексте объявления можно получить доступ к его `Private` элементов.</span><span class="sxs-lookup"><span data-stu-id="bf428-114">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="bf428-115">Это относится к коду вложенного типа, такие как вложенный класс или выражение присваивания в перечислении.</span><span class="sxs-lookup"><span data-stu-id="bf428-115">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="bf428-116">Код вне контекста объявления можно получить доступ к его `Private` элементов.</span><span class="sxs-lookup"><span data-stu-id="bf428-116">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
-   <span data-ttu-id="bf428-117">**Модификаторы доступа.**</span><span class="sxs-lookup"><span data-stu-id="bf428-117">**Access Modifiers.**</span></span> <span data-ttu-id="bf428-118">Ключевые слова, указывающие уровень доступа, называются *модификаторы доступа*.</span><span class="sxs-lookup"><span data-stu-id="bf428-118">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="bf428-119">Сравнение модификаторов доступа см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="bf428-119">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="bf428-120">Модификатор `Private` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="bf428-120">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="bf428-121">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="bf428-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="bf428-122">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="bf428-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="bf428-123">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="bf428-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="bf428-124">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="bf428-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="bf428-125">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="bf428-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="bf428-126">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="bf428-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="bf428-127">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="bf428-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="bf428-128">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="bf428-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="bf428-129">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="bf428-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="bf428-130">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="bf428-130">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="bf428-131">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="bf428-131">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="bf428-132">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="bf428-132">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="bf428-133">См. также</span><span class="sxs-lookup"><span data-stu-id="bf428-133">See Also</span></span>  
 [<span data-ttu-id="bf428-134">Public</span><span class="sxs-lookup"><span data-stu-id="bf428-134">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="bf428-135">Protected</span><span class="sxs-lookup"><span data-stu-id="bf428-135">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="bf428-136">Friend</span><span class="sxs-lookup"><span data-stu-id="bf428-136">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="bf428-137">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bf428-137">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="bf428-138">Процедуры</span><span class="sxs-lookup"><span data-stu-id="bf428-138">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="bf428-139">Структуры</span><span class="sxs-lookup"><span data-stu-id="bf428-139">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="bf428-140">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="bf428-140">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
