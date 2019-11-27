---
title: MustOverride
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
ms.openlocfilehash: dc6a153a604fd0e5cee9d7d46ebcd63294f33628
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351482"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="3c2cb-102">MustOverride (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c2cb-102">MustOverride (Visual Basic)</span></span>
<span data-ttu-id="3c2cb-103">Указывает, что свойство или процедура не реализованы в этом классе и должны быть переопределены в производном классе, прежде чем его можно будет использовать.</span><span class="sxs-lookup"><span data-stu-id="3c2cb-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c2cb-104">Заметки</span><span class="sxs-lookup"><span data-stu-id="3c2cb-104">Remarks</span></span>  
 <span data-ttu-id="3c2cb-105">`MustOverride` можно использовать только в операторе объявления свойства или процедуры.</span><span class="sxs-lookup"><span data-stu-id="3c2cb-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="3c2cb-106">Свойство или процедура, указывающая `MustOverride` должен быть членом класса, а класс должен быть помечен как [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span><span class="sxs-lookup"><span data-stu-id="3c2cb-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="3c2cb-107">Правила</span><span class="sxs-lookup"><span data-stu-id="3c2cb-107">Rules</span></span>  
  
- <span data-ttu-id="3c2cb-108">**Неполное объявление.**</span><span class="sxs-lookup"><span data-stu-id="3c2cb-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="3c2cb-109">При указании `MustOverride`не предоставляются дополнительные строки кода для свойства или процедуры, а не инструкции `End Function`, `End Property`или `End Sub`.</span><span class="sxs-lookup"><span data-stu-id="3c2cb-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="3c2cb-110">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="3c2cb-110">**Combined Modifiers.**</span></span> <span data-ttu-id="3c2cb-111">В одном объявлении нельзя указать `MustOverride` вместе с `NotOverridable`, `Overridable`или `Shared`.</span><span class="sxs-lookup"><span data-stu-id="3c2cb-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
- <span data-ttu-id="3c2cb-112">**Затенение и переопределение.**</span><span class="sxs-lookup"><span data-stu-id="3c2cb-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="3c2cb-113">Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия.</span><span class="sxs-lookup"><span data-stu-id="3c2cb-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="3c2cb-114">Дополнительные сведения см. [в разделе теневая поддержка в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="3c2cb-114">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
- <span data-ttu-id="3c2cb-115">**Альтернативные условия.**</span><span class="sxs-lookup"><span data-stu-id="3c2cb-115">**Alternate Terms.**</span></span> <span data-ttu-id="3c2cb-116">Элемент, который нельзя использовать, за исключением переопределения, иногда называют *чисто виртуальным* элементом.</span><span class="sxs-lookup"><span data-stu-id="3c2cb-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="3c2cb-117">Модификатор `MustOverride` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="3c2cb-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="3c2cb-118">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="3c2cb-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="3c2cb-119">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="3c2cb-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="3c2cb-120">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="3c2cb-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="3c2cb-121">См. также</span><span class="sxs-lookup"><span data-stu-id="3c2cb-121">See also</span></span>

- [<span data-ttu-id="3c2cb-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="3c2cb-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="3c2cb-123">Overridable</span><span class="sxs-lookup"><span data-stu-id="3c2cb-123">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="3c2cb-124">Переопределения</span><span class="sxs-lookup"><span data-stu-id="3c2cb-124">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="3c2cb-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="3c2cb-125">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="3c2cb-126">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3c2cb-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="3c2cb-127">Затенение в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3c2cb-127">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
