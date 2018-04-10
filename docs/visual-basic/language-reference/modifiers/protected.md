---
title: Protected (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d0cc7a0cb626a9ec8e2a0e47abc02e5268aed56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="protected-visual-basic"></a><span data-ttu-id="4ced2-102">Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ced2-102">Protected (Visual Basic)</span></span>
<span data-ttu-id="4ced2-103">Указывает, что один или несколько объявленных программных элементов доступны только из своего собственного класса или из производного класса.</span><span class="sxs-lookup"><span data-stu-id="4ced2-103">Specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ced2-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="4ced2-104">Remarks</span></span>  
 <span data-ttu-id="4ced2-105">Иногда программный элемент объявлен в классе содержит конфиденциальные данные или ограниченный код, и вы хотите ограничить доступ к элементу.</span><span class="sxs-lookup"><span data-stu-id="4ced2-105">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span></span> <span data-ttu-id="4ced2-106">Однако если класс является наследуемым и предполагается в иерархии производных классов, возможно, необходимые для этих производных классов для доступа к данным или коду.</span><span class="sxs-lookup"><span data-stu-id="4ced2-106">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span></span> <span data-ttu-id="4ced2-107">В этом случае требуется, чтобы элемент был доступен как из базового класса, так и из всех производных классов.</span><span class="sxs-lookup"><span data-stu-id="4ced2-107">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span></span> <span data-ttu-id="4ced2-108">Чтобы ограничить доступ к элементу таким образом, можно объявить его с `Protected`.</span><span class="sxs-lookup"><span data-stu-id="4ced2-108">To limit access to an element in this manner, you can declare it with `Protected`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="4ced2-109">Правила</span><span class="sxs-lookup"><span data-stu-id="4ced2-109">Rules</span></span>  
  
-   <span data-ttu-id="4ced2-110">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="4ced2-110">**Declaration Context.**</span></span> <span data-ttu-id="4ced2-111">Можно использовать `Protected` только на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="4ced2-111">You can use `Protected` only at class level.</span></span> <span data-ttu-id="4ced2-112">Это означает, что контекст объявления для `Protected` элемент должен быть классом и не может быть исходный файл, пространство имен, интерфейса, модуля, структуры или процедуры.</span><span class="sxs-lookup"><span data-stu-id="4ced2-112">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>  
  
-   <span data-ttu-id="4ced2-113">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="4ced2-113">**Combined Modifiers.**</span></span> <span data-ttu-id="4ced2-114">Можно использовать `Protected` модификатор вместе с [Friend](../../../visual-basic/language-reference/modifiers/friend.md) модификатор в объявлении.</span><span class="sxs-lookup"><span data-stu-id="4ced2-114">You can use the `Protected` modifier together with the [Friend](../../../visual-basic/language-reference/modifiers/friend.md) modifier in the same declaration.</span></span> <span data-ttu-id="4ced2-115">Эта комбинация делает объявленные элементы доступны из любой той же сборки, из собственного класса и из производных классов.</span><span class="sxs-lookup"><span data-stu-id="4ced2-115">This combination makes the declared elements accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="4ced2-116">Можно указать `Protected Friend` только для членов классов.</span><span class="sxs-lookup"><span data-stu-id="4ced2-116">You can specify `Protected Friend` only on members of classes.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="4ced2-117">Поведение</span><span class="sxs-lookup"><span data-stu-id="4ced2-117">Behavior</span></span>  
  
-   <span data-ttu-id="4ced2-118">**Уровень доступа.**</span><span class="sxs-lookup"><span data-stu-id="4ced2-118">**Access Level.**</span></span> <span data-ttu-id="4ced2-119">Весь код в классе можно получить доступ к его элементам.</span><span class="sxs-lookup"><span data-stu-id="4ced2-119">All code in a class can access its elements.</span></span> <span data-ttu-id="4ced2-120">Код в любой класс, производный от базового класса можно получить доступ ко всем `Protected` элементы базового класса.</span><span class="sxs-lookup"><span data-stu-id="4ced2-120">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span></span> <span data-ttu-id="4ced2-121">Это справедливо для всех поколений наследования.</span><span class="sxs-lookup"><span data-stu-id="4ced2-121">This is true for all generations of derivation.</span></span> <span data-ttu-id="4ced2-122">Это означает, что класс может получить доступ к `Protected` элементы базового класса базового класса и т. д.</span><span class="sxs-lookup"><span data-stu-id="4ced2-122">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span></span>  
  
     <span data-ttu-id="4ced2-123">Защищенный доступ не является надмножеством или подмножеством дружественный доступ.</span><span class="sxs-lookup"><span data-stu-id="4ced2-123">Protected access is not a superset or subset of friend access.</span></span>  
  
-   <span data-ttu-id="4ced2-124">**Модификаторы доступа.**</span><span class="sxs-lookup"><span data-stu-id="4ced2-124">**Access Modifiers.**</span></span> <span data-ttu-id="4ced2-125">Ключевые слова, указывающие уровень доступа, называются *модификаторы доступа*.</span><span class="sxs-lookup"><span data-stu-id="4ced2-125">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="4ced2-126">Сравнение модификаторов доступа см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4ced2-126">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="4ced2-127">Модификатор `Protected` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="4ced2-127">The `Protected` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="4ced2-128">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="4ced2-128">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="4ced2-129">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="4ced2-129">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="4ced2-130">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="4ced2-130">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="4ced2-131">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="4ced2-131">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="4ced2-132">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="4ced2-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="4ced2-133">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="4ced2-133">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="4ced2-134">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="4ced2-134">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="4ced2-135">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="4ced2-135">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="4ced2-136">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="4ced2-136">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="4ced2-137">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="4ced2-137">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="4ced2-138">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="4ced2-138">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="4ced2-139">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="4ced2-139">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="4ced2-140">См. также</span><span class="sxs-lookup"><span data-stu-id="4ced2-140">See Also</span></span>  
 [<span data-ttu-id="4ced2-141">Public</span><span class="sxs-lookup"><span data-stu-id="4ced2-141">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="4ced2-142">Friend</span><span class="sxs-lookup"><span data-stu-id="4ced2-142">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="4ced2-143">Закрытые</span><span class="sxs-lookup"><span data-stu-id="4ced2-143">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="4ced2-144">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4ced2-144">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="4ced2-145">Процедуры</span><span class="sxs-lookup"><span data-stu-id="4ced2-145">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="4ced2-146">Структуры</span><span class="sxs-lookup"><span data-stu-id="4ced2-146">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="4ced2-147">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="4ced2-147">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
