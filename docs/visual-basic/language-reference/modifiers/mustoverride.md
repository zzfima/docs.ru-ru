---
title: MustOverride (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.MustOverride
- MustOverride
helpviewer_keywords:
- virtual elements [Visual Basic], pure
- elements [Visual Basic], pure virtual
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- overriding, MustOverride keyword
- procedures [Visual Basic], redefining
- pure virtual elements [Visual Basic]
- MustOverride keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
ms.openlocfilehash: 0ddd7d0d2a57afc02aa7483ba5e83b65c48af534
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58822821"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="eb229-102">MustOverride (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb229-102">MustOverride (Visual Basic)</span></span>
<span data-ttu-id="eb229-103">Указывает, что свойство или процедура в этом классе не реализован и должен быть переопределен в производном классе, прежде чем можно будет использовать.</span><span class="sxs-lookup"><span data-stu-id="eb229-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb229-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="eb229-104">Remarks</span></span>  
 <span data-ttu-id="eb229-105">`MustOverride` можно использовать только в операторе объявления свойства или процедуры.</span><span class="sxs-lookup"><span data-stu-id="eb229-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="eb229-106">Свойство или процедуру, которая указывает `MustOverride` должен быть членом класса, и класс должен быть помечен [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span><span class="sxs-lookup"><span data-stu-id="eb229-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="eb229-107">Правила</span><span class="sxs-lookup"><span data-stu-id="eb229-107">Rules</span></span>  
  
-   <span data-ttu-id="eb229-108">**Неполное объявление.**</span><span class="sxs-lookup"><span data-stu-id="eb229-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="eb229-109">При указании `MustOverride`, не нужно вводить любые дополнительные строки кода для свойства или процедуры, не даже `End Function`, `End Property`, или `End Sub` инструкции.</span><span class="sxs-lookup"><span data-stu-id="eb229-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
-   <span data-ttu-id="eb229-110">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="eb229-110">**Combined Modifiers.**</span></span> <span data-ttu-id="eb229-111">Нельзя указать `MustOverride` вместе с `NotOverridable`, `Overridable`, или `Shared` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="eb229-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
-   <span data-ttu-id="eb229-112">**Сокрытие и переопределение.**</span><span class="sxs-lookup"><span data-stu-id="eb229-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="eb229-113">Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия.</span><span class="sxs-lookup"><span data-stu-id="eb229-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="eb229-114">Дополнительные сведения см. в разделе [сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="eb229-114">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
-   <span data-ttu-id="eb229-115">**Альтернативные условия.**</span><span class="sxs-lookup"><span data-stu-id="eb229-115">**Alternate Terms.**</span></span> <span data-ttu-id="eb229-116">Элемент, который не может использоваться только в переопределении иногда называют *чисто виртуальный* элемент.</span><span class="sxs-lookup"><span data-stu-id="eb229-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="eb229-117">Модификатор `MustOverride` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="eb229-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="eb229-118">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="eb229-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="eb229-119">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="eb229-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="eb229-120">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="eb229-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="eb229-121">См. также</span><span class="sxs-lookup"><span data-stu-id="eb229-121">See also</span></span>

- [<span data-ttu-id="eb229-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="eb229-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="eb229-123">Переопределяемые</span><span class="sxs-lookup"><span data-stu-id="eb229-123">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="eb229-124">Переопределения</span><span class="sxs-lookup"><span data-stu-id="eb229-124">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="eb229-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="eb229-125">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="eb229-126">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="eb229-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="eb229-127">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="eb229-127">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
