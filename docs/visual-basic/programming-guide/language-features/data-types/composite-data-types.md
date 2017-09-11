---
title: "Составные типы данных (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types
- composite data types
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures, composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5f0c6215ce45d724a7b5c8c4f8e34ea27bce8fe4
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="bf371-102">Составные типы данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf371-102">Composite Data Types (Visual Basic)</span></span>
<span data-ttu-id="bf371-103">Помимо простых типов данных [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] блоки, можно создавать из элементов различных типов для создания *составные типы данных* как структуры, массивы и классы.</span><span class="sxs-lookup"><span data-stu-id="bf371-103">In addition to the elementary data types [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="bf371-104">Можно создавать составные типы данных из простых типов или из других составных типов.</span><span class="sxs-lookup"><span data-stu-id="bf371-104">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="bf371-105">Например можно определить массив элементов структуры или структуру с членами массива.</span><span class="sxs-lookup"><span data-stu-id="bf371-105">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="bf371-106">Типы данных</span><span class="sxs-lookup"><span data-stu-id="bf371-106">Data Types</span></span>  
 <span data-ttu-id="bf371-107">Составной тип отличается от типа данных любого из его компонентов.</span><span class="sxs-lookup"><span data-stu-id="bf371-107">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="bf371-108">Например, массив `Integer` элементы не `Integer` тип данных.</span><span class="sxs-lookup"><span data-stu-id="bf371-108">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="bf371-109">Тип данных массива обычно представляется с помощью типа элемента, скобок и запятых при необходимости.</span><span class="sxs-lookup"><span data-stu-id="bf371-109">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="bf371-110">Например, одномерный массив `String` элементов представляется в виде `String()`, а двумерный массив `Boolean` элементов представляется в виде `Boolean(,)`.</span><span class="sxs-lookup"><span data-stu-id="bf371-110">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="bf371-111">Типы структур</span><span class="sxs-lookup"><span data-stu-id="bf371-111">Structure Types</span></span>  
 <span data-ttu-id="bf371-112">Отсутствует тип данных single включающего в себя все структуры.</span><span class="sxs-lookup"><span data-stu-id="bf371-112">There is no single data type comprising all structures.</span></span> <span data-ttu-id="bf371-113">Вместо этого каждое определение структуры представляет собой уникальный тип данных, даже если две структуры определяют идентичные элементы в том же порядке.</span><span class="sxs-lookup"><span data-stu-id="bf371-113">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="bf371-114">Однако, если создать два или более экземпляров одной и той же структуры, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] рассматривает их как элементы одного типа данных.</span><span class="sxs-lookup"><span data-stu-id="bf371-114">However, if you create two or more instances of the same structure, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] considers them to be of the same data type.</span></span>  
  
## <a name="array-types"></a><span data-ttu-id="bf371-115">Типы массивов</span><span class="sxs-lookup"><span data-stu-id="bf371-115">Array Types</span></span>  
 <span data-ttu-id="bf371-116">Отсутствует тип данных single включающего в себя все массивы.</span><span class="sxs-lookup"><span data-stu-id="bf371-116">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="bf371-117">Тип данных отдельного экземпляра массива определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bf371-117">The data type of a particular instance of an array is determined by the following:</span></span>  
  
-   <span data-ttu-id="bf371-118">Факт существования массива</span><span class="sxs-lookup"><span data-stu-id="bf371-118">The fact of being an array</span></span>  
  
-   <span data-ttu-id="bf371-119">Ранг (размерность) массива</span><span class="sxs-lookup"><span data-stu-id="bf371-119">The rank (number of dimensions) of the array</span></span>  
  
-   <span data-ttu-id="bf371-120">Тип элемента массива</span><span class="sxs-lookup"><span data-stu-id="bf371-120">The element type of the array</span></span>  
  
 <span data-ttu-id="bf371-121">В частности длина данного измерения не является частью типа данных экземпляра.</span><span class="sxs-lookup"><span data-stu-id="bf371-121">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="bf371-122">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bf371-122">The following example illustrates this.</span></span>  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="bf371-123">В предыдущем примере массив переменных `arrayA` и `arrayB` считаются тот же тип данных — `Byte()` — даже если они инициализируются для различной длины.</span><span class="sxs-lookup"><span data-stu-id="bf371-123">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="bf371-124">Переменные `arrayB` и `arrayC` не являются того же типа, так как типы их элементов различны.</span><span class="sxs-lookup"><span data-stu-id="bf371-124">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="bf371-125">Переменные `arrayC` и `arrayD` не являются того же типа, так как их ранги различны.</span><span class="sxs-lookup"><span data-stu-id="bf371-125">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="bf371-126">Переменные `arrayD` и `arrayE` имеют одинаковый тип — `Short(,)` , так как их ранги и типы элементов одинаковы, даже если `arrayD` еще не инициализирован.</span><span class="sxs-lookup"><span data-stu-id="bf371-126">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="bf371-127">Дополнительные сведения о массивах см. в разделе [массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="bf371-127">For more information on arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="bf371-128">Типы классов</span><span class="sxs-lookup"><span data-stu-id="bf371-128">Class Types</span></span>  
 <span data-ttu-id="bf371-129">Нет нет типа данных, включающего в себя все классы.</span><span class="sxs-lookup"><span data-stu-id="bf371-129">There is no single data type comprising all classes.</span></span> <span data-ttu-id="bf371-130">Несмотря на то, что один класс может наследовать от другого класса, каждый является отдельным типом данных.</span><span class="sxs-lookup"><span data-stu-id="bf371-130">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="bf371-131">Несколько экземпляров одного класса имеют одинаковый тип данных.</span><span class="sxs-lookup"><span data-stu-id="bf371-131">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="bf371-132">Если назначить одну переменную экземпляра класса в другой, не только они имеют тот же тип данных, они указывают на один экземпляр класса в памяти.</span><span class="sxs-lookup"><span data-stu-id="bf371-132">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="bf371-133">Дополнительные сведения о классах см. в разделе [объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="bf371-133">For more information on classes, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf371-134">См. также</span><span class="sxs-lookup"><span data-stu-id="bf371-134">See Also</span></span>  
 <span data-ttu-id="bf371-135">[Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="bf371-135">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="bf371-136"> [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="bf371-136"> [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="bf371-137"> [Универсальные типы в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="bf371-137"> [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
<span data-ttu-id="bf371-138"> [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="bf371-138"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="bf371-139"> [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="bf371-139"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="bf371-140"> [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span><span class="sxs-lookup"><span data-stu-id="bf371-140"> [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span></span>  
<span data-ttu-id="bf371-141"> [Устранение неполадок типы данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="bf371-141"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="bf371-142"> [Практическое руководство. Хранение нескольких значений в переменной](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)</span><span class="sxs-lookup"><span data-stu-id="bf371-142"> [How to: Hold More Than One Value in a Variable](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)</span></span>
