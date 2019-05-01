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
ms.openlocfilehash: 0c85564503f3c83e436044cd92ee3014945f1ef3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051875"
---
# <a name="public-visual-basic"></a><span data-ttu-id="51461-102">Public (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51461-102">Public (Visual Basic)</span></span>
<span data-ttu-id="51461-103">Указывает, что один или несколько объявленных программных элементов не имеют ограничений доступа.</span><span class="sxs-lookup"><span data-stu-id="51461-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51461-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="51461-104">Remarks</span></span>  
 <span data-ttu-id="51461-105">При публикации компонента или набора компонентов, таких как библиотеки классов, вам бы хотелось элементы программирования могут оказаться недоступными из любого кода, который взаимодействует со сборкой.</span><span class="sxs-lookup"><span data-stu-id="51461-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="51461-106">Чтобы предоставить такой неограниченный доступ для элемента, его можно объявить с `Public`.</span><span class="sxs-lookup"><span data-stu-id="51461-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="51461-107">Общий доступ при обычном уровне для элемента программирования необходимо ограничить доступ к нему.</span><span class="sxs-lookup"><span data-stu-id="51461-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="51461-108">Обратите внимание, что уровень доступа для элемента, объявленные в интерфейсе, модуля, класса или структуры по умолчанию используется `Public` Если иное не объявлено.</span><span class="sxs-lookup"><span data-stu-id="51461-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="51461-109">Правила</span><span class="sxs-lookup"><span data-stu-id="51461-109">Rules</span></span>  
  
- <span data-ttu-id="51461-110">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="51461-110">**Declaration Context.**</span></span> <span data-ttu-id="51461-111">Можно использовать `Public` только на уровне модуля, интерфейса или пространства имен.</span><span class="sxs-lookup"><span data-stu-id="51461-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="51461-112">Это означает, что контекст объявления для `Public` элемент должен быть исходный файл, пространство имен, интерфейс, модуля, класса или структуры и не может быть процедурой.</span><span class="sxs-lookup"><span data-stu-id="51461-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="51461-113">Поведение</span><span class="sxs-lookup"><span data-stu-id="51461-113">Behavior</span></span>  
  
- <span data-ttu-id="51461-114">**Уровень доступа.**</span><span class="sxs-lookup"><span data-stu-id="51461-114">**Access Level.**</span></span> <span data-ttu-id="51461-115">Весь код, который можно получить доступ к модуля, класса или структуры можно получить доступ к его `Public` элементов.</span><span class="sxs-lookup"><span data-stu-id="51461-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
- <span data-ttu-id="51461-116">**Доступ по умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="51461-116">**Default Access.**</span></span> <span data-ttu-id="51461-117">Локальные переменные внутри процедуры по умолчанию общий доступ и невозможно использовать модификаторы доступа на них.</span><span class="sxs-lookup"><span data-stu-id="51461-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
- <span data-ttu-id="51461-118">**Модификаторы доступа.**</span><span class="sxs-lookup"><span data-stu-id="51461-118">**Access Modifiers.**</span></span> <span data-ttu-id="51461-119">Ключевые слова, указывающие уровень доступа, называются *модификаторы доступа*.</span><span class="sxs-lookup"><span data-stu-id="51461-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="51461-120">Сравнение модификаторов доступа, см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="51461-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="51461-121">Модификатор `Public` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="51461-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="51461-122">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="51461-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="51461-123">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="51461-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="51461-124">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="51461-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="51461-125">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="51461-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="51461-126">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="51461-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="51461-127">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="51461-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="51461-128">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="51461-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="51461-129">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="51461-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="51461-130">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="51461-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="51461-131">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="51461-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="51461-132">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="51461-132">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="51461-133">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="51461-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="51461-134">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="51461-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="51461-135">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="51461-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="51461-136">См. также</span><span class="sxs-lookup"><span data-stu-id="51461-136">See also</span></span>

- [<span data-ttu-id="51461-137">Protected</span><span class="sxs-lookup"><span data-stu-id="51461-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="51461-138">Friend</span><span class="sxs-lookup"><span data-stu-id="51461-138">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="51461-139">Закрытые</span><span class="sxs-lookup"><span data-stu-id="51461-139">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="51461-140">Private Protected</span><span class="sxs-lookup"><span data-stu-id="51461-140">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="51461-141">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="51461-141">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="51461-142">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="51461-142">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="51461-143">Процедуры</span><span class="sxs-lookup"><span data-stu-id="51461-143">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="51461-144">Структуры</span><span class="sxs-lookup"><span data-stu-id="51461-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="51461-145">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="51461-145">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
