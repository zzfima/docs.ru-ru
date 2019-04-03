---
title: Различия между аргументами Modifiable и Nonmodifiable (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: a880ae8c13eebd5d9d325468098e058f58d3fa71
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826669"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a><span data-ttu-id="bf6b6-102">Различия между аргументами Modifiable и Nonmodifiable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf6b6-102">Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic)</span></span>
<span data-ttu-id="bf6b6-103">При вызове процедуры, обычно передается один или несколько аргументов к нему.</span><span class="sxs-lookup"><span data-stu-id="bf6b6-103">When you call a procedure, you typically pass one or more arguments to it.</span></span> <span data-ttu-id="bf6b6-104">Каждый аргумент соответствует базовому элементу программирования.</span><span class="sxs-lookup"><span data-stu-id="bf6b6-104">Each argument corresponds to an underlying programming element.</span></span> <span data-ttu-id="bf6b6-105">Базовые элементы и сами аргументы может быть либо изменяемыми либо неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="bf6b6-105">Both the underlying elements and the arguments themselves can be either modifiable or nonmodifiable.</span></span>  
  
## <a name="modifiable-and-nonmodifiable-elements"></a><span data-ttu-id="bf6b6-106">Изменяемые и неизменяемые элементы</span><span class="sxs-lookup"><span data-stu-id="bf6b6-106">Modifiable and Nonmodifiable Elements</span></span>  
 <span data-ttu-id="bf6b6-107">Программный элемент может быть либо *изменяемого элемента*, который может менять свое значение, или *неизменяемым*, который имеет фиксированное значение после его создания.</span><span class="sxs-lookup"><span data-stu-id="bf6b6-107">A programming element can be either a *modifiable element*, which can have its value changed, or a *nonmodifiable element*, which has a fixed value once it has been created.</span></span>  
  
 <span data-ttu-id="bf6b6-108">В следующей таблице перечислены изменяемые и неизменяемые элементы программирования.</span><span class="sxs-lookup"><span data-stu-id="bf6b6-108">The following table lists modifiable and nonmodifiable programming elements.</span></span>  
  
|<span data-ttu-id="bf6b6-109">Изменяемые элементы</span><span class="sxs-lookup"><span data-stu-id="bf6b6-109">Modifiable elements</span></span>|<span data-ttu-id="bf6b6-110">Неизменяемые элементы</span><span class="sxs-lookup"><span data-stu-id="bf6b6-110">Nonmodifiable elements</span></span>|  
|-------------------------|----------------------------|  
|<span data-ttu-id="bf6b6-111">Локальные переменные (объявленные внутри процедур), включая объектные переменные, доступные только для чтения</span><span class="sxs-lookup"><span data-stu-id="bf6b6-111">Local variables (declared inside procedures), including object variables, except for read-only</span></span>|<span data-ttu-id="bf6b6-112">Переменные только для чтения, поля и свойства</span><span class="sxs-lookup"><span data-stu-id="bf6b6-112">Read-only variables, fields, and properties</span></span>|  
|<span data-ttu-id="bf6b6-113">Поля (переменные-члены модулей, классов и структур), доступные только для чтения</span><span class="sxs-lookup"><span data-stu-id="bf6b6-113">Fields (member variables of modules, classes, and structures), except for read-only</span></span>|<span data-ttu-id="bf6b6-114">Константы и литералы</span><span class="sxs-lookup"><span data-stu-id="bf6b6-114">Constants and literals</span></span>|  
|<span data-ttu-id="bf6b6-115">Свойства, доступные только для чтения</span><span class="sxs-lookup"><span data-stu-id="bf6b6-115">Properties, except for read-only</span></span>|<span data-ttu-id="bf6b6-116">Члены перечисления</span><span class="sxs-lookup"><span data-stu-id="bf6b6-116">Enumeration members</span></span>|  
|<span data-ttu-id="bf6b6-117">Элементы массива</span><span class="sxs-lookup"><span data-stu-id="bf6b6-117">Array elements</span></span>|<span data-ttu-id="bf6b6-118">Выражения (даже если их элементы являются изменяемыми)</span><span class="sxs-lookup"><span data-stu-id="bf6b6-118">Expressions (even if their elements are modifiable)</span></span>|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a><span data-ttu-id="bf6b6-119">Аргументами modifiable и Nonmodifiable</span><span class="sxs-lookup"><span data-stu-id="bf6b6-119">Modifiable and Nonmodifiable Arguments</span></span>  
 <span data-ttu-id="bf6b6-120">Объект *изменяемые аргумент* — один с изменяемым базового элемента.</span><span class="sxs-lookup"><span data-stu-id="bf6b6-120">A *modifiable argument* is one with a modifiable underlying element.</span></span> <span data-ttu-id="bf6b6-121">Вызывающий код может хранить новое значение в любое время, и если передается аргумент [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), код в процедуру также можно изменить элемент в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="bf6b6-121">The calling code can store a new value at any time, and if you pass the argument [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the code in the procedure can also modify the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="bf6b6-122">Объект *неизменяемого аргумента* базовой неизменяемым или он передается [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="bf6b6-122">A *nonmodifiable argument* either has a nonmodifiable underlying element or is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="bf6b6-123">Процедура не может изменить элемент в вызывающем коде, даже если он является изменяемым.</span><span class="sxs-lookup"><span data-stu-id="bf6b6-123">The procedure cannot modify the underlying element in the calling code, even if it is a modifiable element.</span></span> <span data-ttu-id="bf6b6-124">Если он является неизменяемым, в вызывающем коде нельзя изменять.</span><span class="sxs-lookup"><span data-stu-id="bf6b6-124">If it is a nonmodifiable element, the calling code itself cannot modify it.</span></span>  
  
 <span data-ttu-id="bf6b6-125">Вызванная процедура может изменить свою локальную копию неизменяемого аргумента, но это изменение не влияет на базовый элемент в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="bf6b6-125">The called procedure might modify its local copy of a nonmodifiable argument, but that modification does not affect the underlying element in the calling code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf6b6-126">См. также</span><span class="sxs-lookup"><span data-stu-id="bf6b6-126">See also</span></span>

- [<span data-ttu-id="bf6b6-127">Процедуры</span><span class="sxs-lookup"><span data-stu-id="bf6b6-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="bf6b6-128">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="bf6b6-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="bf6b6-129">Практическое руководство. Передача аргументов в процедуру</span><span class="sxs-lookup"><span data-stu-id="bf6b6-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="bf6b6-130">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="bf6b6-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="bf6b6-131">Различия между передачей аргумента по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="bf6b6-131">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="bf6b6-132">Практическое руководство. Изменение значения аргумента процедуры</span><span class="sxs-lookup"><span data-stu-id="bf6b6-132">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="bf6b6-133">Практическое руководство. Защита аргумента процедуры от изменения значения</span><span class="sxs-lookup"><span data-stu-id="bf6b6-133">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="bf6b6-134">Практическое руководство. Принудительная передаваться по значению аргумента</span><span class="sxs-lookup"><span data-stu-id="bf6b6-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="bf6b6-135">Передача аргументов по позиции и по имени</span><span class="sxs-lookup"><span data-stu-id="bf6b6-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="bf6b6-136">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="bf6b6-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
