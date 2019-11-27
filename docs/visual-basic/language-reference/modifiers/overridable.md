---
title: Overridable
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
ms.openlocfilehash: 9c639665fd92a56de6fb6e5147cda873ef457b45
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351391"
---
# <a name="overridable-visual-basic"></a><span data-ttu-id="73cb7-102">Overridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73cb7-102">Overridable (Visual Basic)</span></span>
<span data-ttu-id="73cb7-103">Указывает, что свойство или процедура может быть переопределена свойством или процедурой с идентичным именем в производном классе.</span><span class="sxs-lookup"><span data-stu-id="73cb7-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73cb7-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="73cb7-104">Remarks</span></span>  
 <span data-ttu-id="73cb7-105">Модификатор `Overridable` позволяет переопределить свойство или метод в классе в производном классе.</span><span class="sxs-lookup"><span data-stu-id="73cb7-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="73cb7-106">Модификатор [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) предотвращает переопределение свойства или метода в производном классе.</span><span class="sxs-lookup"><span data-stu-id="73cb7-106">The [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="73cb7-107">Дополнительные сведения см. в статье [Inheritance Basics (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md) (Основная информация о наследовании в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="73cb7-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="73cb7-108">Если модификатор `Overridable` или `NotOverridable` не указан, значение по умолчанию зависит от того, переопределяет ли свойство или метод свойство или метод базового класса.</span><span class="sxs-lookup"><span data-stu-id="73cb7-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="73cb7-109">Если свойство или метод переопределяет свойство или метод базового класса, значение по умолчанию — `Overridable`. в противном случае это `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="73cb7-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="73cb7-110">Можно выполнить затенение или переопределение, чтобы переопределить наследуемый элемент, но существуют значительные различия между этими двумя подходами.</span><span class="sxs-lookup"><span data-stu-id="73cb7-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="73cb7-111">Дополнительные сведения см. [в разделе теневая поддержка в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="73cb7-111">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="73cb7-112">Элемент, который можно переопределить, иногда называется *виртуальным* элементом.</span><span class="sxs-lookup"><span data-stu-id="73cb7-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="73cb7-113">Если он может быть переопределен, но не обязательно должен быть, он иногда также называется *конкретным* элементом.</span><span class="sxs-lookup"><span data-stu-id="73cb7-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="73cb7-114">`Overridable` можно использовать только в операторе объявления свойства или процедуры.</span><span class="sxs-lookup"><span data-stu-id="73cb7-114">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="73cb7-115">Комбинированные модификаторы</span><span class="sxs-lookup"><span data-stu-id="73cb7-115">Combined Modifiers</span></span>  
 <span data-ttu-id="73cb7-116">Для метода `Private` нельзя указать `Overridable` или `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="73cb7-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="73cb7-117">В одном объявлении нельзя указать `Overridable` вместе с `MustOverride`, `NotOverridable`или `Shared`.</span><span class="sxs-lookup"><span data-stu-id="73cb7-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="73cb7-118">Так как переопределяемый элемент является неявно переопределяемым, нельзя объединять `Overridable` с `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="73cb7-118">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="73cb7-119">Использование</span><span class="sxs-lookup"><span data-stu-id="73cb7-119">Usage</span></span>  
 <span data-ttu-id="73cb7-120">Модификатор `Overridable` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="73cb7-120">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="73cb7-121">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="73cb7-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="73cb7-122">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="73cb7-122">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="73cb7-123">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="73cb7-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="73cb7-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="73cb7-124">See also</span></span>

- [<span data-ttu-id="73cb7-125">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="73cb7-125">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)
- [<span data-ttu-id="73cb7-126">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="73cb7-126">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="73cb7-127">MustOverride</span><span class="sxs-lookup"><span data-stu-id="73cb7-127">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="73cb7-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="73cb7-128">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="73cb7-129">Переопределения</span><span class="sxs-lookup"><span data-stu-id="73cb7-129">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="73cb7-130">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="73cb7-130">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="73cb7-131">Затенение в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="73cb7-131">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
