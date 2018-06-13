---
title: Overridable (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Overridable
- vb.Overridable
helpviewer_keywords:
- elements [Visual Basic], concrete
- properties [Visual Basic], redefining
- overriding, Overridable keyword
- elements [Visual Basic], virtual
- virtual [elements VB]
- procedures [Visual Basic], overriding
- concrete [elements VB]
- procedures [Visual Basic], redefining
- Overridable keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
ms.openlocfilehash: 4844bf7f3ecf23335715b950a96be15e54ebc601
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603773"
---
# <a name="overridable-visual-basic"></a><span data-ttu-id="23ee1-102">Overridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23ee1-102">Overridable (Visual Basic)</span></span>
<span data-ttu-id="23ee1-103">Указывает, что свойство или процедура могут быть переопределены одноименную свойство или процедура в производном классе.</span><span class="sxs-lookup"><span data-stu-id="23ee1-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23ee1-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="23ee1-104">Remarks</span></span>  
 <span data-ttu-id="23ee1-105">`Overridable` Модификатор разрешает свойства или метода в классе для переопределения в производном классе.</span><span class="sxs-lookup"><span data-stu-id="23ee1-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="23ee1-106">[NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) модификатор не позволяет переопределять свойства или метода в производном классе.</span><span class="sxs-lookup"><span data-stu-id="23ee1-106">The [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="23ee1-107">Дополнительные сведения см. в статье [Inheritance Basics (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md) (Основная информация о наследовании в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="23ee1-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="23ee1-108">Если `Overridable` или `NotOverridable` модификатор не указан, значение по умолчанию зависит от того, является ли метод или свойство переопределяет свойство базового класса или метода.</span><span class="sxs-lookup"><span data-stu-id="23ee1-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="23ee1-109">Если метод или свойство переопределяет свойство базового класса или метода, значение по умолчанию — `Overridable`; в противном случае он является `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="23ee1-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="23ee1-110">Можно скрывать или переопределить, чтобы переопределить наследуемый элемент, но существуют значительные различия между двумя способами.</span><span class="sxs-lookup"><span data-stu-id="23ee1-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="23ee1-111">Дополнительные сведения см. в разделе [сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="23ee1-111">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="23ee1-112">Элемент, который может быть переопределен, иногда называют *виртуальных* элемента.</span><span class="sxs-lookup"><span data-stu-id="23ee1-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="23ee1-113">Если он может быть переопределен, но не должен быть, она иногда называется *конкретных* элемента.</span><span class="sxs-lookup"><span data-stu-id="23ee1-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="23ee1-114">`Overridable` можно использовать только в операторе объявления свойства или процедуры.</span><span class="sxs-lookup"><span data-stu-id="23ee1-114">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="23ee1-115">Комбинированные модификаторы</span><span class="sxs-lookup"><span data-stu-id="23ee1-115">Combined Modifiers</span></span>  
 <span data-ttu-id="23ee1-116">Нельзя указать `Overridable` или `NotOverridable` для `Private` метод.</span><span class="sxs-lookup"><span data-stu-id="23ee1-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="23ee1-117">Нельзя указать `Overridable` вместе с `MustOverride`, `NotOverridable`, или `Shared` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="23ee1-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="23ee1-118">Так как переопределяемый элемент является неявно переопределяемым, нельзя объединять `Overridable` с `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="23ee1-118">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="23ee1-119">Использование</span><span class="sxs-lookup"><span data-stu-id="23ee1-119">Usage</span></span>  
 <span data-ttu-id="23ee1-120">Модификатор `Overridable` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="23ee1-120">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="23ee1-121">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="23ee1-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="23ee1-122">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="23ee1-122">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="23ee1-123">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="23ee1-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="23ee1-124">См. также</span><span class="sxs-lookup"><span data-stu-id="23ee1-124">See Also</span></span>  
 [<span data-ttu-id="23ee1-125">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="23ee1-125">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)  
 [<span data-ttu-id="23ee1-126">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="23ee1-126">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="23ee1-127">MustOverride</span><span class="sxs-lookup"><span data-stu-id="23ee1-127">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [<span data-ttu-id="23ee1-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="23ee1-128">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [<span data-ttu-id="23ee1-129">Переопределения</span><span class="sxs-lookup"><span data-stu-id="23ee1-129">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="23ee1-130">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="23ee1-130">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="23ee1-131">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="23ee1-131">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
