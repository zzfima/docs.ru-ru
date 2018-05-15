---
title: NotOverridable (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
ms.openlocfilehash: 3fae1a4b587c379dbc459cbc973982851e713785
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="notoverridable-visual-basic"></a><span data-ttu-id="632c4-102">NotOverridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="632c4-102">NotOverridable (Visual Basic)</span></span>
<span data-ttu-id="632c4-103">Указывает, что свойство или процедура не может переопределяться в производном классе.</span><span class="sxs-lookup"><span data-stu-id="632c4-103">Specifies that a property or procedure cannot be overridden in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="632c4-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="632c4-104">Remarks</span></span>  
 <span data-ttu-id="632c4-105">`NotOverridable` Модификатор не позволяет переопределять свойства или метода в производном классе.</span><span class="sxs-lookup"><span data-stu-id="632c4-105">The `NotOverridable` modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="632c4-106">[Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) модификатор разрешает свойства или метода в классе для переопределения в производном классе.</span><span class="sxs-lookup"><span data-stu-id="632c4-106">The [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="632c4-107">Дополнительные сведения см. в статье [Inheritance Basics (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md) (Основная информация о наследовании в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="632c4-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="632c4-108">Если `Overridable` или `NotOverridable` модификатор не указан, значение по умолчанию зависит от того, является ли метод или свойство переопределяет свойство базового класса или метода.</span><span class="sxs-lookup"><span data-stu-id="632c4-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="632c4-109">Если метод или свойство переопределяет свойство базового класса или метода, значение по умолчанию — `Overridable`; в противном случае он является `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="632c4-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="632c4-110">Элемент, который не может быть переопределен, иногда называется *запечатанный* элемента.</span><span class="sxs-lookup"><span data-stu-id="632c4-110">An element that cannot be overridden is sometimes called a *sealed* element.</span></span>  
  
 <span data-ttu-id="632c4-111">`NotOverridable` можно использовать только в операторе объявления свойства или процедуры.</span><span class="sxs-lookup"><span data-stu-id="632c4-111">You can use `NotOverridable` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="632c4-112">Можно указать `NotOverridable` только для свойства или процедуры, которая переопределяет другое свойство или процедура, то есть только в сочетании с `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="632c4-112">You can specify `NotOverridable` only on a property or procedure that overrides another property or procedure, that is, only in combination with `Overrides`.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="632c4-113">Комбинированные модификаторы</span><span class="sxs-lookup"><span data-stu-id="632c4-113">Combined Modifiers</span></span>  
 <span data-ttu-id="632c4-114">Нельзя указать `Overridable` или `NotOverridable` для `Private` метод.</span><span class="sxs-lookup"><span data-stu-id="632c4-114">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="632c4-115">Нельзя указать `NotOverridable` вместе с `MustOverride`, `Overridable`, или `Shared` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="632c4-115">You cannot specify `NotOverridable` together with `MustOverride`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="632c4-116">Использование</span><span class="sxs-lookup"><span data-stu-id="632c4-116">Usage</span></span>  
 <span data-ttu-id="632c4-117">Модификатор `NotOverridable` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="632c4-117">The `NotOverridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="632c4-118">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="632c4-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="632c4-119">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="632c4-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="632c4-120">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="632c4-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="632c4-121">См. также</span><span class="sxs-lookup"><span data-stu-id="632c4-121">See Also</span></span>  
 [<span data-ttu-id="632c4-122">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="632c4-122">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)  
 [<span data-ttu-id="632c4-123">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="632c4-123">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="632c4-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="632c4-124">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [<span data-ttu-id="632c4-125">Переопределяемые</span><span class="sxs-lookup"><span data-stu-id="632c4-125">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [<span data-ttu-id="632c4-126">Переопределения</span><span class="sxs-lookup"><span data-stu-id="632c4-126">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="632c4-127">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="632c4-127">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="632c4-128">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="632c4-128">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
