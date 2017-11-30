---
title: Private (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07450c2a5443bf6bc147cad2cfc779072bfc363b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="private-visual-basic"></a><span data-ttu-id="ce504-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce504-102">Private (Visual Basic)</span></span>
<span data-ttu-id="ce504-103">Указывает, что один или несколько элементов доступны только внутри контекста, включая из любых вложенных типов.</span><span class="sxs-lookup"><span data-stu-id="ce504-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce504-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="ce504-104">Remarks</span></span>  
 <span data-ttu-id="ce504-105">Если элемент программирования представляет особые возможности или содержит конфиденциальные данные, обычно требуется максимально ограничить доступ к нему.</span><span class="sxs-lookup"><span data-stu-id="ce504-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="ce504-106">Максимальное ограничение добиться, позволяя модуля, класса или структуры, которые определяют его для доступа к нему.</span><span class="sxs-lookup"><span data-stu-id="ce504-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="ce504-107">Чтобы ограничить доступ к элементу таким образом, можно объявить его с `Private`.</span><span class="sxs-lookup"><span data-stu-id="ce504-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="ce504-108">Правила</span><span class="sxs-lookup"><span data-stu-id="ce504-108">Rules</span></span>  
  
-   <span data-ttu-id="ce504-109">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="ce504-109">**Declaration Context.**</span></span> <span data-ttu-id="ce504-110">`Private` можно использовать только на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="ce504-110">You can use `Private` only at module level.</span></span> <span data-ttu-id="ce504-111">Это означает, что контекст объявления для `Private` элемент должен быть модуля, класса или структуры и не может быть исходным файлом, пространства имен, интерфейса или процедуры.</span><span class="sxs-lookup"><span data-stu-id="ce504-111">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="ce504-112">Поведение</span><span class="sxs-lookup"><span data-stu-id="ce504-112">Behavior</span></span>  
  
-   <span data-ttu-id="ce504-113">**Уровень доступа.**</span><span class="sxs-lookup"><span data-stu-id="ce504-113">**Access Level.**</span></span> <span data-ttu-id="ce504-114">Весь код в контексте объявления можно получить доступ к его `Private` элементов.</span><span class="sxs-lookup"><span data-stu-id="ce504-114">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="ce504-115">Это относится к коду вложенного типа, такие как вложенный класс или выражение присваивания в перечислении.</span><span class="sxs-lookup"><span data-stu-id="ce504-115">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="ce504-116">Код вне контекста объявления можно получить доступ к его `Private` элементов.</span><span class="sxs-lookup"><span data-stu-id="ce504-116">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
-   <span data-ttu-id="ce504-117">**Модификаторы доступа.**</span><span class="sxs-lookup"><span data-stu-id="ce504-117">**Access Modifiers.**</span></span> <span data-ttu-id="ce504-118">Ключевые слова, указывающие уровень доступа, называются *модификаторы доступа*.</span><span class="sxs-lookup"><span data-stu-id="ce504-118">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="ce504-119">Сравнение модификаторов доступа см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ce504-119">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="ce504-120">Модификатор `Private` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="ce504-120">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="ce504-121">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="ce504-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="ce504-122">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="ce504-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="ce504-123">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="ce504-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="ce504-124">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="ce504-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="ce504-125">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="ce504-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="ce504-126">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="ce504-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="ce504-127">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="ce504-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="ce504-128">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="ce504-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="ce504-129">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="ce504-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="ce504-130">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="ce504-130">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="ce504-131">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="ce504-131">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="ce504-132">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="ce504-132">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="ce504-133">См. также</span><span class="sxs-lookup"><span data-stu-id="ce504-133">See Also</span></span>  
 [<span data-ttu-id="ce504-134">Public</span><span class="sxs-lookup"><span data-stu-id="ce504-134">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="ce504-135">Protected</span><span class="sxs-lookup"><span data-stu-id="ce504-135">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="ce504-136">Friend</span><span class="sxs-lookup"><span data-stu-id="ce504-136">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="ce504-137">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ce504-137">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="ce504-138">Процедуры</span><span class="sxs-lookup"><span data-stu-id="ce504-138">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="ce504-139">Структуры</span><span class="sxs-lookup"><span data-stu-id="ce504-139">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="ce504-140">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="ce504-140">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
