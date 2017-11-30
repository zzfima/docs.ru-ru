---
title: "Различия между аргументами Modifiable и Nonmodifiable (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ab108d064f5c6740f80328a9b6db4785334550ca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a><span data-ttu-id="d0221-102">Различия между аргументами Modifiable и Nonmodifiable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0221-102">Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic)</span></span>
<span data-ttu-id="d0221-103">При вызове процедуры обычно передаваемого один или несколько аргументов.</span><span class="sxs-lookup"><span data-stu-id="d0221-103">When you call a procedure, you typically pass one or more arguments to it.</span></span> <span data-ttu-id="d0221-104">Каждый аргумент соответствует базовому элементу программирования.</span><span class="sxs-lookup"><span data-stu-id="d0221-104">Each argument corresponds to an underlying programming element.</span></span> <span data-ttu-id="d0221-105">Базовые элементы и аргументы сами могут быть либо изменяемыми либо неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="d0221-105">Both the underlying elements and the arguments themselves can be either modifiable or nonmodifiable.</span></span>  
  
## <a name="modifiable-and-nonmodifiable-elements"></a><span data-ttu-id="d0221-106">Изменяемые и неизменяемые элементы</span><span class="sxs-lookup"><span data-stu-id="d0221-106">Modifiable and Nonmodifiable Elements</span></span>  
 <span data-ttu-id="d0221-107">Программный элемент может быть либо *изменяемого элемента*, которого можно менять свое значение, или *неизменяемым*, который имеет фиксированное значение после его создания.</span><span class="sxs-lookup"><span data-stu-id="d0221-107">A programming element can be either a *modifiable element*, which can have its value changed, or a *nonmodifiable element*, which has a fixed value once it has been created.</span></span>  
  
 <span data-ttu-id="d0221-108">В следующей таблице перечислены изменяемые и неизменяемые элементы программирования.</span><span class="sxs-lookup"><span data-stu-id="d0221-108">The following table lists modifiable and nonmodifiable programming elements.</span></span>  
  
|<span data-ttu-id="d0221-109">Изменяемые элементы</span><span class="sxs-lookup"><span data-stu-id="d0221-109">Modifiable elements</span></span>|<span data-ttu-id="d0221-110">Неизменяемые элементы</span><span class="sxs-lookup"><span data-stu-id="d0221-110">Nonmodifiable elements</span></span>|  
|-------------------------|----------------------------|  
|<span data-ttu-id="d0221-111">Локальные переменные (объявленные внутри процедур), включая объектные переменные, доступные только для чтения</span><span class="sxs-lookup"><span data-stu-id="d0221-111">Local variables (declared inside procedures), including object variables, except for read-only</span></span>|<span data-ttu-id="d0221-112">Переменные только для чтения, поля и свойства</span><span class="sxs-lookup"><span data-stu-id="d0221-112">Read-only variables, fields, and properties</span></span>|  
|<span data-ttu-id="d0221-113">Поля (переменные-члены модулей, классы и структуры), доступные только для чтения</span><span class="sxs-lookup"><span data-stu-id="d0221-113">Fields (member variables of modules, classes, and structures), except for read-only</span></span>|<span data-ttu-id="d0221-114">Константы и литералы</span><span class="sxs-lookup"><span data-stu-id="d0221-114">Constants and literals</span></span>|  
|<span data-ttu-id="d0221-115">Свойства, доступные только для чтения</span><span class="sxs-lookup"><span data-stu-id="d0221-115">Properties, except for read-only</span></span>|<span data-ttu-id="d0221-116">Члены перечисления</span><span class="sxs-lookup"><span data-stu-id="d0221-116">Enumeration members</span></span>|  
|<span data-ttu-id="d0221-117">Элементы массива</span><span class="sxs-lookup"><span data-stu-id="d0221-117">Array elements</span></span>|<span data-ttu-id="d0221-118">Выражения (даже если их элементы являются изменяемыми)</span><span class="sxs-lookup"><span data-stu-id="d0221-118">Expressions (even if their elements are modifiable)</span></span>|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a><span data-ttu-id="d0221-119">Изменяемые и неизменяемые аргументы</span><span class="sxs-lookup"><span data-stu-id="d0221-119">Modifiable and Nonmodifiable Arguments</span></span>  
 <span data-ttu-id="d0221-120">Объект *изменяемый аргумент* с изменяемым базового элемента.</span><span class="sxs-lookup"><span data-stu-id="d0221-120">A *modifiable argument* is one with a modifiable underlying element.</span></span> <span data-ttu-id="d0221-121">Вызывающий код может хранить новое значение в любое время, и если передать аргумент [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), код в процедуре сможет изменить базовый элемент в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="d0221-121">The calling code can store a new value at any time, and if you pass the argument [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the code in the procedure can also modify the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="d0221-122">Объект *неизменяемого аргумента* имеет базовый неизменяемым или параметром, переданным [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="d0221-122">A *nonmodifiable argument* either has a nonmodifiable underlying element or is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="d0221-123">Процедура не может изменить базовый элемент в вызывающем коде, даже если он является изменяемым.</span><span class="sxs-lookup"><span data-stu-id="d0221-123">The procedure cannot modify the underlying element in the calling code, even if it is a modifiable element.</span></span> <span data-ttu-id="d0221-124">Если он является неизменяемым, в вызывающем коде нельзя изменять.</span><span class="sxs-lookup"><span data-stu-id="d0221-124">If it is a nonmodifiable element, the calling code itself cannot modify it.</span></span>  
  
 <span data-ttu-id="d0221-125">Вызванная процедура может изменить свою локальную копию неизменяемого аргумента, но это изменение не затронет базовый элемент в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="d0221-125">The called procedure might modify its local copy of a nonmodifiable argument, but that modification does not affect the underlying element in the calling code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0221-126">См. также</span><span class="sxs-lookup"><span data-stu-id="d0221-126">See Also</span></span>  
 [<span data-ttu-id="d0221-127">Процедуры</span><span class="sxs-lookup"><span data-stu-id="d0221-127">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="d0221-128">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="d0221-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="d0221-129">Практическое руководство. Передача аргументов в процедуру</span><span class="sxs-lookup"><span data-stu-id="d0221-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="d0221-130">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="d0221-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="d0221-131">Различия между передачей аргумента по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="d0221-131">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="d0221-132">Практическое руководство. Изменение значения аргумента процедуры</span><span class="sxs-lookup"><span data-stu-id="d0221-132">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)  
 [<span data-ttu-id="d0221-133">Практическое руководство. Защита аргумента процедуры от изменений значения</span><span class="sxs-lookup"><span data-stu-id="d0221-133">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [<span data-ttu-id="d0221-134">Практическое руководство. Принудительная передача аргумента по значению</span><span class="sxs-lookup"><span data-stu-id="d0221-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [<span data-ttu-id="d0221-135">Передача аргументов по позиции и по имени</span><span class="sxs-lookup"><span data-stu-id="d0221-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="d0221-136">Типы значений и ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="d0221-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
