---
title: Public (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: a5e9161132ba6d571daa30ce82e1bfb1dd2b064f
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34235922"
---
# <a name="public-visual-basic"></a><span data-ttu-id="813f7-102">Public (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="813f7-102">Public (Visual Basic)</span></span>
<span data-ttu-id="813f7-103">Указывает, что один или несколько элементов не имеют ограничений доступа.</span><span class="sxs-lookup"><span data-stu-id="813f7-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="813f7-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="813f7-104">Remarks</span></span>  
 <span data-ttu-id="813f7-105">При публикации компонента или набора компонентов, таких как библиотеки классов, обычно требуется, элементов программирования, должна быть доступна из любого кода, взаимодействующего со сборкой.</span><span class="sxs-lookup"><span data-stu-id="813f7-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="813f7-106">Чтобы предоставить такой неограниченный доступ для элемента, его можно объявить с `Public`.</span><span class="sxs-lookup"><span data-stu-id="813f7-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="813f7-107">Общий доступ является обычным уровнем для элемента программирования, при необходимости ограничить доступ к нему.</span><span class="sxs-lookup"><span data-stu-id="813f7-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="813f7-108">Обратите внимание, что уровень доступа элемент объявлен внутри интерфейса, модуля, класса или структуры по умолчанию используется значение `Public` Если иное не объявлено.</span><span class="sxs-lookup"><span data-stu-id="813f7-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="813f7-109">Правила</span><span class="sxs-lookup"><span data-stu-id="813f7-109">Rules</span></span>  
  
-   <span data-ttu-id="813f7-110">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="813f7-110">**Declaration Context.**</span></span> <span data-ttu-id="813f7-111">Можно использовать `Public` только на уровне модуля, интерфейсом или пространством имен.</span><span class="sxs-lookup"><span data-stu-id="813f7-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="813f7-112">Это означает, что контекст объявления для `Public` элемент должен быть исходный файл, пространство имен, интерфейса, модуля, класса или структуры и не может быть процедурой.</span><span class="sxs-lookup"><span data-stu-id="813f7-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="813f7-113">Поведение</span><span class="sxs-lookup"><span data-stu-id="813f7-113">Behavior</span></span>  
  
-   <span data-ttu-id="813f7-114">**Уровень доступа.**</span><span class="sxs-lookup"><span data-stu-id="813f7-114">**Access Level.**</span></span> <span data-ttu-id="813f7-115">Весь код, можно получить доступ, модуля, класса или структуры можно получить доступ к его `Public` элементов.</span><span class="sxs-lookup"><span data-stu-id="813f7-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
-   <span data-ttu-id="813f7-116">**Доступ по умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="813f7-116">**Default Access.**</span></span> <span data-ttu-id="813f7-117">Локальные переменные внутри процедуры по умолчанию для общего доступа и нельзя использовать модификаторы доступа на них.</span><span class="sxs-lookup"><span data-stu-id="813f7-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
-   <span data-ttu-id="813f7-118">**Модификаторы доступа.**</span><span class="sxs-lookup"><span data-stu-id="813f7-118">**Access Modifiers.**</span></span> <span data-ttu-id="813f7-119">Ключевые слова, указывающие уровень доступа, называются *модификаторы доступа*.</span><span class="sxs-lookup"><span data-stu-id="813f7-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="813f7-120">Сравнение модификаторов доступа см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="813f7-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="813f7-121">Модификатор `Public` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="813f7-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="813f7-122">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="813f7-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="813f7-123">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="813f7-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="813f7-124">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="813f7-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="813f7-125">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="813f7-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="813f7-126">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="813f7-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="813f7-127">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="813f7-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="813f7-128">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="813f7-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="813f7-129">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="813f7-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="813f7-130">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="813f7-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="813f7-131">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="813f7-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="813f7-132">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="813f7-132">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="813f7-133">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="813f7-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="813f7-134">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="813f7-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="813f7-135">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="813f7-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="813f7-136">См. также</span><span class="sxs-lookup"><span data-stu-id="813f7-136">See Also</span></span>  
 [<span data-ttu-id="813f7-137">Protected</span><span class="sxs-lookup"><span data-stu-id="813f7-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="813f7-138">Friend</span><span class="sxs-lookup"><span data-stu-id="813f7-138">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="813f7-139">Закрытые</span><span class="sxs-lookup"><span data-stu-id="813f7-139">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 <span data-ttu-id="813f7-140">[Protected Private](private-protected.md) </span><span class="sxs-lookup"><span data-stu-id="813f7-140">[Private Protected](private-protected.md) </span></span>  
 <span data-ttu-id="813f7-141">[Protected Friend](protected-friend.md) </span><span class="sxs-lookup"><span data-stu-id="813f7-141">[Protected Friend](protected-friend.md) </span></span>  
 [<span data-ttu-id="813f7-142">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="813f7-142">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="813f7-143">Процедуры</span><span class="sxs-lookup"><span data-stu-id="813f7-143">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="813f7-144">Структуры</span><span class="sxs-lookup"><span data-stu-id="813f7-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="813f7-145">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="813f7-145">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
