---
title: Private (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: d6e28e5e87c3a88e4db3fc81177894683dbb0908
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920449"
---
# <a name="private-visual-basic"></a><span data-ttu-id="da6a4-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da6a4-102">Private (Visual Basic)</span></span>
<span data-ttu-id="da6a4-103">Указывает, что один или несколько объявленных программных элементов доступны только из их объявление контекста, в том числе и из всех вложенных типов.</span><span class="sxs-lookup"><span data-stu-id="da6a4-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da6a4-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="da6a4-104">Remarks</span></span>  
 <span data-ttu-id="da6a4-105">Если программный элемент представляет особые возможности или содержит конфиденциальные данные, обычно требуется максимально ограничить доступ к нему.</span><span class="sxs-lookup"><span data-stu-id="da6a4-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="da6a4-106">Максимальное ограничение добиться, разрешив только модуля, класса или структуры, определяющего его для доступа к нему.</span><span class="sxs-lookup"><span data-stu-id="da6a4-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="da6a4-107">Чтобы ограничить доступ к элементу таким образом, его можно объявить с `Private`.</span><span class="sxs-lookup"><span data-stu-id="da6a4-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="da6a4-108">Можно также использовать [Private Protected](private-protected.md) модификатор доступа, что делает член доступен из внутри этого класса и из производных классов, расположенных в его соответствующая сборка.</span><span class="sxs-lookup"><span data-stu-id="da6a4-108">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="da6a4-109">Правила</span><span class="sxs-lookup"><span data-stu-id="da6a4-109">Rules</span></span>  

- <span data-ttu-id="da6a4-110">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="da6a4-110">**Declaration Context.**</span></span> <span data-ttu-id="da6a4-111">`Private` можно использовать только на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="da6a4-111">You can use `Private` only at module level.</span></span> <span data-ttu-id="da6a4-112">Это означает, что контекст объявления для `Private` элемент должен быть модуля, класса или структуры и не может быть исходный файл, пространство имен, интерфейса или процедуры.</span><span class="sxs-lookup"><span data-stu-id="da6a4-112">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="da6a4-113">Поведение</span><span class="sxs-lookup"><span data-stu-id="da6a4-113">Behavior</span></span>  
  
- <span data-ttu-id="da6a4-114">**Уровень доступа.**</span><span class="sxs-lookup"><span data-stu-id="da6a4-114">**Access Level.**</span></span> <span data-ttu-id="da6a4-115">Весь код в контексте объявления можно получить доступ к его `Private` элементов.</span><span class="sxs-lookup"><span data-stu-id="da6a4-115">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="da6a4-116">Это включает в себя код вложенного типа, таких как вложенный класс или выражения присваивания в перечисление.</span><span class="sxs-lookup"><span data-stu-id="da6a4-116">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="da6a4-117">Код вне контекста объявления можно получить доступ к его `Private` элементов.</span><span class="sxs-lookup"><span data-stu-id="da6a4-117">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
- <span data-ttu-id="da6a4-118">**Модификаторы доступа.**</span><span class="sxs-lookup"><span data-stu-id="da6a4-118">**Access Modifiers.**</span></span> <span data-ttu-id="da6a4-119">Ключевые слова, указывающие уровень доступа, называются *модификаторы доступа*.</span><span class="sxs-lookup"><span data-stu-id="da6a4-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="da6a4-120">Сравнение модификаторов доступа, см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="da6a4-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="da6a4-121">Модификатор `Private` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="da6a4-121">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="da6a4-122">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="da6a4-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="da6a4-123">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="da6a4-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="da6a4-124">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="da6a4-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="da6a4-125">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="da6a4-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="da6a4-126">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="da6a4-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="da6a4-127">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="da6a4-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="da6a4-128">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="da6a4-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="da6a4-129">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="da6a4-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="da6a4-130">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="da6a4-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="da6a4-131">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="da6a4-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="da6a4-132">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="da6a4-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="da6a4-133">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="da6a4-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="da6a4-134">См. также</span><span class="sxs-lookup"><span data-stu-id="da6a4-134">See also</span></span>

- [<span data-ttu-id="da6a4-135">Public</span><span class="sxs-lookup"><span data-stu-id="da6a4-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="da6a4-136">Protected</span><span class="sxs-lookup"><span data-stu-id="da6a4-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="da6a4-137">Friend</span><span class="sxs-lookup"><span data-stu-id="da6a4-137">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="da6a4-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="da6a4-138">Private Protected</span></span>](./private-protected.md)
- <span data-ttu-id="da6a4-139">[Protected Friend](./protected-friend.md)[Access levels в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span><span class="sxs-lookup"><span data-stu-id="da6a4-139">[Protected Friend](./protected-friend.md)    [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span></span>
- [<span data-ttu-id="da6a4-140">Процедуры</span><span class="sxs-lookup"><span data-stu-id="da6a4-140">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="da6a4-141">Структуры</span><span class="sxs-lookup"><span data-stu-id="da6a4-141">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="da6a4-142">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="da6a4-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
