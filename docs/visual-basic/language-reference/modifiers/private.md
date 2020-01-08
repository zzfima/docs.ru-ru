---
title: Private
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 0c855c4e08b365b4cb75ab062d2ec304a79612ab
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347918"
---
# <a name="private-visual-basic"></a><span data-ttu-id="3c1d7-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c1d7-102">Private (Visual Basic)</span></span>
<span data-ttu-id="3c1d7-103">Указывает, что один или несколько объявленных программных элементов доступны только в контексте объявления, включая из любых содержащихся в них типов.</span><span class="sxs-lookup"><span data-stu-id="3c1d7-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c1d7-104">Заметки</span><span class="sxs-lookup"><span data-stu-id="3c1d7-104">Remarks</span></span>  
 <span data-ttu-id="3c1d7-105">Если программный элемент представляет собственные функции или содержит конфиденциальные данные, обычно требуется ограничить доступ к нему как можно более строгим.</span><span class="sxs-lookup"><span data-stu-id="3c1d7-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="3c1d7-106">Максимальное ограничение достигается за счет предоставления только модулю, классу или структуре, определяющей его доступ.</span><span class="sxs-lookup"><span data-stu-id="3c1d7-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="3c1d7-107">Чтобы ограничить доступ к элементу таким образом, его можно объявить с помощью `Private`.</span><span class="sxs-lookup"><span data-stu-id="3c1d7-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="3c1d7-108">Можно также использовать модификатор [закрытого](private-protected.md) доступа, который делает член доступным из этого класса и из производных классов, расположенных в содержащей его сборке.</span><span class="sxs-lookup"><span data-stu-id="3c1d7-108">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="3c1d7-109">Правила</span><span class="sxs-lookup"><span data-stu-id="3c1d7-109">Rules</span></span>  

- <span data-ttu-id="3c1d7-110">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="3c1d7-110">**Declaration Context.**</span></span> <span data-ttu-id="3c1d7-111">`Private` можно использовать только на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="3c1d7-111">You can use `Private` only at module level.</span></span> <span data-ttu-id="3c1d7-112">Это означает, что контекст объявления для элемента `Private` должен быть модулем, классом или структурой и не может быть исходным файлом, пространством имен, интерфейсом или процедурой.</span><span class="sxs-lookup"><span data-stu-id="3c1d7-112">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="3c1d7-113">Поведение</span><span class="sxs-lookup"><span data-stu-id="3c1d7-113">Behavior</span></span>  
  
- <span data-ttu-id="3c1d7-114">**Уровень доступа.**</span><span class="sxs-lookup"><span data-stu-id="3c1d7-114">**Access Level.**</span></span> <span data-ttu-id="3c1d7-115">Весь код в контексте объявления может получать доступ к его `Private` элементам.</span><span class="sxs-lookup"><span data-stu-id="3c1d7-115">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="3c1d7-116">Сюда входит код внутри содержащегося типа, например вложенный класс или выражение присваивания в перечислении.</span><span class="sxs-lookup"><span data-stu-id="3c1d7-116">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="3c1d7-117">Ни один код за пределами контекста объявления не может получить доступ к его элементам `Private`.</span><span class="sxs-lookup"><span data-stu-id="3c1d7-117">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
- <span data-ttu-id="3c1d7-118">**Модификаторы доступа.**</span><span class="sxs-lookup"><span data-stu-id="3c1d7-118">**Access Modifiers.**</span></span> <span data-ttu-id="3c1d7-119">Ключевые слова, определяющие уровень доступа, называются *модификаторами доступа*.</span><span class="sxs-lookup"><span data-stu-id="3c1d7-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="3c1d7-120">Сравнение модификаторов доступа см. [в разделе уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3c1d7-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="3c1d7-121">Модификатор `Private` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="3c1d7-121">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="3c1d7-122">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="3c1d7-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="3c1d7-123">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="3c1d7-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="3c1d7-124">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="3c1d7-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="3c1d7-125">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="3c1d7-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="3c1d7-126">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="3c1d7-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="3c1d7-127">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="3c1d7-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="3c1d7-128">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="3c1d7-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="3c1d7-129">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="3c1d7-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="3c1d7-130">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="3c1d7-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="3c1d7-131">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="3c1d7-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="3c1d7-132">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="3c1d7-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="3c1d7-133">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="3c1d7-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="3c1d7-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="3c1d7-134">See also</span></span>

- [<span data-ttu-id="3c1d7-135">Public</span><span class="sxs-lookup"><span data-stu-id="3c1d7-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="3c1d7-136">Protected</span><span class="sxs-lookup"><span data-stu-id="3c1d7-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="3c1d7-137">Friend</span><span class="sxs-lookup"><span data-stu-id="3c1d7-137">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="3c1d7-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="3c1d7-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="3c1d7-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="3c1d7-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="3c1d7-140">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3c1d7-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="3c1d7-141">Процедуры</span><span class="sxs-lookup"><span data-stu-id="3c1d7-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="3c1d7-142">Структуры</span><span class="sxs-lookup"><span data-stu-id="3c1d7-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="3c1d7-143">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="3c1d7-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
