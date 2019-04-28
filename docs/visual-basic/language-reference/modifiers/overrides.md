---
title: Overrides (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: 9eb19bf5e89b12a32cae28b2c087570acc10f3ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920575"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="24a6f-102">Overrides (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24a6f-102">Overrides (Visual Basic)</span></span>
<span data-ttu-id="24a6f-103">Указывает, что свойство или процедура переопределяет свойство или процедуру с идентичным названием, унаследованную от базового класса.</span><span class="sxs-lookup"><span data-stu-id="24a6f-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24a6f-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="24a6f-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="24a6f-105">Правила</span><span class="sxs-lookup"><span data-stu-id="24a6f-105">Rules</span></span>  
  
-   <span data-ttu-id="24a6f-106">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="24a6f-106">**Declaration Context.**</span></span> <span data-ttu-id="24a6f-107">`Overrides` можно использовать только в операторе объявления свойства или процедуры.</span><span class="sxs-lookup"><span data-stu-id="24a6f-107">You can use `Overrides` only in a property or procedure declaration statement.</span></span>  
  
-   <span data-ttu-id="24a6f-108">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="24a6f-108">**Combined Modifiers.**</span></span> <span data-ttu-id="24a6f-109">Невозможно указать `Overrides` вместе с `Shadows` или `Shared` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="24a6f-109">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="24a6f-110">Так как переопределяемый элемент является неявно переопределяемым, нельзя объединять `Overridable` с `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="24a6f-110">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
-   <span data-ttu-id="24a6f-111">**Соответствие сигнатур.**</span><span class="sxs-lookup"><span data-stu-id="24a6f-111">**Matching Signatures.**</span></span> <span data-ttu-id="24a6f-112">Сигнатура этого объявления должна точно соответствовать *подпись* свойства или процедуры, который он переопределяет.</span><span class="sxs-lookup"><span data-stu-id="24a6f-112">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="24a6f-113">Это означает, что списки параметров должны содержать одинаковое число параметров, в том же порядке и с теми же типами данных.</span><span class="sxs-lookup"><span data-stu-id="24a6f-113">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>  
  
     <span data-ttu-id="24a6f-114">Помимо сигнатуры, для объявления переопределения должны также совпадать следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="24a6f-114">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>  
  
    -   <span data-ttu-id="24a6f-115">уровень доступа;</span><span class="sxs-lookup"><span data-stu-id="24a6f-115">The access level</span></span>  
  
    -   <span data-ttu-id="24a6f-116">тип возвращаемого значения (если применимо).</span><span class="sxs-lookup"><span data-stu-id="24a6f-116">The return type, if any</span></span>  
  
-   <span data-ttu-id="24a6f-117">**Универсальные сигнатуры.**</span><span class="sxs-lookup"><span data-stu-id="24a6f-117">**Generic Signatures.**</span></span> <span data-ttu-id="24a6f-118">Для универсальной процедуры сигнатура содержит число параметров типа.</span><span class="sxs-lookup"><span data-stu-id="24a6f-118">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="24a6f-119">Поэтому объявление переопределения должно соответствовать версии базового класса и в этом аспекте.</span><span class="sxs-lookup"><span data-stu-id="24a6f-119">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>  
  
-   <span data-ttu-id="24a6f-120">**Дополнительные соответствия.**</span><span class="sxs-lookup"><span data-stu-id="24a6f-120">**Additional Matching.**</span></span> <span data-ttu-id="24a6f-121">Помимо соответствия сигнатуры версии базового класса, это объявление должно также соответствовать ему в следующих аспектах:</span><span class="sxs-lookup"><span data-stu-id="24a6f-121">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>  
  
    -   <span data-ttu-id="24a6f-122">Модификатор уровня доступа (такие как [открытый](../../../visual-basic/language-reference/modifiers/public.md))</span><span class="sxs-lookup"><span data-stu-id="24a6f-122">Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))</span></span>  
  
    -   <span data-ttu-id="24a6f-123">Механизм каждого параметра передачи ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span><span class="sxs-lookup"><span data-stu-id="24a6f-123">Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span></span>  
  
    -   <span data-ttu-id="24a6f-124">списки ограничений для каждого типа параметра универсальной процедуры.</span><span class="sxs-lookup"><span data-stu-id="24a6f-124">Constraint lists on each type parameter of a generic procedure</span></span>  
  
-   <span data-ttu-id="24a6f-125">**Сокрытие и переопределение.**</span><span class="sxs-lookup"><span data-stu-id="24a6f-125">**Shadowing and Overriding.**</span></span> <span data-ttu-id="24a6f-126">Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия.</span><span class="sxs-lookup"><span data-stu-id="24a6f-126">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="24a6f-127">Дополнительные сведения см. в разделе [сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="24a6f-127">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="24a6f-128">При использовании `Overrides` компилятор неявно добавляет `Overloads`, чтобы упростить работу API-интерфейсов с библиотекой C#.</span><span class="sxs-lookup"><span data-stu-id="24a6f-128">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>  
  
 <span data-ttu-id="24a6f-129">Модификатор `Overrides` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="24a6f-129">The `Overrides` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="24a6f-130">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="24a6f-130">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="24a6f-131">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="24a6f-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="24a6f-132">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="24a6f-132">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="24a6f-133">См. также</span><span class="sxs-lookup"><span data-stu-id="24a6f-133">See also</span></span>

- [<span data-ttu-id="24a6f-134">MustOverride</span><span class="sxs-lookup"><span data-stu-id="24a6f-134">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="24a6f-135">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="24a6f-135">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="24a6f-136">Переопределяемые</span><span class="sxs-lookup"><span data-stu-id="24a6f-136">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="24a6f-137">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="24a6f-137">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="24a6f-138">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="24a6f-138">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="24a6f-139">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="24a6f-139">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="24a6f-140">Список типов</span><span class="sxs-lookup"><span data-stu-id="24a6f-140">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
