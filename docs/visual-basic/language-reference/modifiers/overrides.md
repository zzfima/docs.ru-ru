---
title: Переопределения
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
ms.openlocfilehash: 04f1cb27d6a8366c2dd13f8fdc1d975d382f1cfd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351389"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="96bcc-102">Overrides (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96bcc-102">Overrides (Visual Basic)</span></span>

<span data-ttu-id="96bcc-103">Указывает, что свойство или процедура переопределяет свойство или процедуру с идентичным названием, унаследованную от базового класса.</span><span class="sxs-lookup"><span data-stu-id="96bcc-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>

## <a name="rules"></a><span data-ttu-id="96bcc-104">Правила</span><span class="sxs-lookup"><span data-stu-id="96bcc-104">Rules</span></span>

- <span data-ttu-id="96bcc-105">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="96bcc-105">**Declaration Context.**</span></span> <span data-ttu-id="96bcc-106">`Overrides` можно использовать только в операторе объявления свойства или процедуры.</span><span class="sxs-lookup"><span data-stu-id="96bcc-106">You can use `Overrides` only in a property or procedure declaration statement.</span></span>

- <span data-ttu-id="96bcc-107">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="96bcc-107">**Combined Modifiers.**</span></span> <span data-ttu-id="96bcc-108">Нельзя указать `Overrides` вместе с `Shadows` или `Shared` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="96bcc-108">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="96bcc-109">Так как переопределяемый элемент является неявно переопределяемым, нельзя объединять `Overridable` с `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="96bcc-109">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>

- <span data-ttu-id="96bcc-110">**Сопоставление сигнатур.**</span><span class="sxs-lookup"><span data-stu-id="96bcc-110">**Matching Signatures.**</span></span> <span data-ttu-id="96bcc-111">Сигнатура этого объявления должна точно совпадать с *сигнатурой* свойства или процедуры, которую он переопределяет.</span><span class="sxs-lookup"><span data-stu-id="96bcc-111">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="96bcc-112">Это означает, что списки параметров должны содержать одинаковое число параметров, в том же порядке и с теми же типами данных.</span><span class="sxs-lookup"><span data-stu-id="96bcc-112">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>

  <span data-ttu-id="96bcc-113">Помимо сигнатуры, для объявления переопределения должны также совпадать следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="96bcc-113">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>

  - <span data-ttu-id="96bcc-114">уровень доступа;</span><span class="sxs-lookup"><span data-stu-id="96bcc-114">The access level</span></span>

  - <span data-ttu-id="96bcc-115">тип возвращаемого значения (если применимо).</span><span class="sxs-lookup"><span data-stu-id="96bcc-115">The return type, if any</span></span>

- <span data-ttu-id="96bcc-116">**Универсальные подписи.**</span><span class="sxs-lookup"><span data-stu-id="96bcc-116">**Generic Signatures.**</span></span> <span data-ttu-id="96bcc-117">Для универсальной процедуры сигнатура содержит число параметров типа.</span><span class="sxs-lookup"><span data-stu-id="96bcc-117">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="96bcc-118">Поэтому объявление переопределения должно соответствовать версии базового класса и в этом аспекте.</span><span class="sxs-lookup"><span data-stu-id="96bcc-118">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>

- <span data-ttu-id="96bcc-119">**Дополнительное сопоставление.**</span><span class="sxs-lookup"><span data-stu-id="96bcc-119">**Additional Matching.**</span></span> <span data-ttu-id="96bcc-120">Помимо соответствия сигнатуры версии базового класса, это объявление должно также соответствовать ему в следующих аспектах:</span><span class="sxs-lookup"><span data-stu-id="96bcc-120">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>

  - <span data-ttu-id="96bcc-121">Модификатор уровня доступа (например, [Public](../../../visual-basic/language-reference/modifiers/public.md))</span><span class="sxs-lookup"><span data-stu-id="96bcc-121">Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))</span></span>

  - <span data-ttu-id="96bcc-122">Механизм передачи каждого параметра ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span><span class="sxs-lookup"><span data-stu-id="96bcc-122">Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span></span>

  - <span data-ttu-id="96bcc-123">списки ограничений для каждого типа параметра универсальной процедуры.</span><span class="sxs-lookup"><span data-stu-id="96bcc-123">Constraint lists on each type parameter of a generic procedure</span></span>

- <span data-ttu-id="96bcc-124">**Затенение и переопределение.**</span><span class="sxs-lookup"><span data-stu-id="96bcc-124">**Shadowing and Overriding.**</span></span> <span data-ttu-id="96bcc-125">Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия.</span><span class="sxs-lookup"><span data-stu-id="96bcc-125">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="96bcc-126">Дополнительные сведения см. [в разделе теневая поддержка в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="96bcc-126">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>

<span data-ttu-id="96bcc-127">При использовании `Overrides` компилятор неявно добавляет `Overloads`, чтобы упростить работу API-интерфейсов с библиотекой C#.</span><span class="sxs-lookup"><span data-stu-id="96bcc-127">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>

<span data-ttu-id="96bcc-128">Модификатор `Overrides` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="96bcc-128">The `Overrides` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="96bcc-129">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="96bcc-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- [<span data-ttu-id="96bcc-130">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="96bcc-130">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- [<span data-ttu-id="96bcc-131">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="96bcc-131">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="96bcc-132">См. также</span><span class="sxs-lookup"><span data-stu-id="96bcc-132">See also</span></span>

- [<span data-ttu-id="96bcc-133">MustOverride</span><span class="sxs-lookup"><span data-stu-id="96bcc-133">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="96bcc-134">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="96bcc-134">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="96bcc-135">Overridable</span><span class="sxs-lookup"><span data-stu-id="96bcc-135">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="96bcc-136">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="96bcc-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="96bcc-137">Затенение в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96bcc-137">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="96bcc-138">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96bcc-138">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="96bcc-139">Список типов</span><span class="sxs-lookup"><span data-stu-id="96bcc-139">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
