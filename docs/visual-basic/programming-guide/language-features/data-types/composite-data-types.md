---
title: Составные типы данных (Visual Basic)
ms.date: 04/25/2017
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
ms.openlocfilehash: ea719b60a6bcd40494666d4923fad296a8ddae70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833819"
---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="fa60c-102">Составные типы данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa60c-102">Composite Data Types (Visual Basic)</span></span>
<span data-ttu-id="fa60c-103">В дополнение к простейших данных типов Visual Basic, можно создавать элементы различных типов для создания *составные типы данных* например структуры, массивы и классы.</span><span class="sxs-lookup"><span data-stu-id="fa60c-103">In addition to the elementary data types Visual Basic supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="fa60c-104">Можно создавать составные типы данных из простых типов или из других составных типов.</span><span class="sxs-lookup"><span data-stu-id="fa60c-104">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="fa60c-105">Например можно определить массив элементов структуры или структуру с членами массива.</span><span class="sxs-lookup"><span data-stu-id="fa60c-105">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="fa60c-106">Типы данных</span><span class="sxs-lookup"><span data-stu-id="fa60c-106">Data Types</span></span>  
 <span data-ttu-id="fa60c-107">Составной тип отличается от типа данных любого из его компонентов.</span><span class="sxs-lookup"><span data-stu-id="fa60c-107">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="fa60c-108">Например, массив `Integer` элементов не относится к `Integer` тип данных.</span><span class="sxs-lookup"><span data-stu-id="fa60c-108">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="fa60c-109">Тип данных массива обычно представляется с помощью типа элемента, круглые скобки и запятые при необходимости.</span><span class="sxs-lookup"><span data-stu-id="fa60c-109">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="fa60c-110">Например, одномерный массив `String` элементов представляется в виде `String()`и двухмерный массив `Boolean` элементов представляется в виде `Boolean(,)`.</span><span class="sxs-lookup"><span data-stu-id="fa60c-110">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="fa60c-111">Типы структуры</span><span class="sxs-lookup"><span data-stu-id="fa60c-111">Structure Types</span></span>  
 <span data-ttu-id="fa60c-112">Нет единого типа данных, включающего в себя все структуры.</span><span class="sxs-lookup"><span data-stu-id="fa60c-112">There is no single data type comprising all structures.</span></span> <span data-ttu-id="fa60c-113">Вместо этого каждое определение структуры представляет уникальный тип данных, даже если две структуры определяют идентичные элементы в том же порядке.</span><span class="sxs-lookup"><span data-stu-id="fa60c-113">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="fa60c-114">Тем не менее при создании двух или более экземпляров той же структуры, Visual Basic рассматривает их как одного типа данных.</span><span class="sxs-lookup"><span data-stu-id="fa60c-114">However, if you create two or more instances of the same structure, Visual Basic considers them to be of the same data type.</span></span>  
  
## <a name="tuples"></a><span data-ttu-id="fa60c-115">Кортежи</span><span class="sxs-lookup"><span data-stu-id="fa60c-115">Tuples</span></span>

<span data-ttu-id="fa60c-116">Кортеж — это упрощенный структуру, содержащую два или несколько полей, типы которых являются предопределенными.</span><span class="sxs-lookup"><span data-stu-id="fa60c-116">A tuple is a lightweight structure that contains two or more fields whose types are predefined.</span></span> <span data-ttu-id="fa60c-117">Кортежи поддерживаются начиная с Visual Basic 2017.</span><span class="sxs-lookup"><span data-stu-id="fa60c-117">Tuples are supported starting with Visual Basic 2017.</span></span> <span data-ttu-id="fa60c-118">Кортежи наиболее часто используются для возврата нескольких значений из одного вызова метода без необходимости передавать аргументы по ссылке или упаковки возвращаемых полей в более всего спектра класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="fa60c-118">Tuples are most commonly used to return multiple values from a single method call without having to pass arguments by reference or packaging the returned fields in a more heavy-weight class or structure.</span></span> <span data-ttu-id="fa60c-119">См. в разделе [кортежей](tuples.md) приведены дополнительные сведения об кортежей.</span><span class="sxs-lookup"><span data-stu-id="fa60c-119">See the [Tuples](tuples.md) topic for more information on tuples.</span></span>

## <a name="array-types"></a><span data-ttu-id="fa60c-120">Типы массивов</span><span class="sxs-lookup"><span data-stu-id="fa60c-120">Array Types</span></span>  
 <span data-ttu-id="fa60c-121">Нет единого типа данных, включающего в себя все массивы.</span><span class="sxs-lookup"><span data-stu-id="fa60c-121">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="fa60c-122">Тип данных определенного экземпляра массива определяется следующее:</span><span class="sxs-lookup"><span data-stu-id="fa60c-122">The data type of a particular instance of an array is determined by the following:</span></span>  
  
-   <span data-ttu-id="fa60c-123">Факт существования массива</span><span class="sxs-lookup"><span data-stu-id="fa60c-123">The fact of being an array</span></span>  
  
-   <span data-ttu-id="fa60c-124">Ранг (число измерений) массива</span><span class="sxs-lookup"><span data-stu-id="fa60c-124">The rank (number of dimensions) of the array</span></span>  
  
-   <span data-ttu-id="fa60c-125">Тип элемента массива</span><span class="sxs-lookup"><span data-stu-id="fa60c-125">The element type of the array</span></span>  
  
 <span data-ttu-id="fa60c-126">В частности длина данного измерения, не является частью типа данных экземпляра.</span><span class="sxs-lookup"><span data-stu-id="fa60c-126">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="fa60c-127">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fa60c-127">The following example illustrates this.</span></span>  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="fa60c-128">В приведенном выше примере массив переменных `arrayA` и `arrayB` считаются одного типа данных — `Byte()` , несмотря на то, что они инициализируются для различной длины.</span><span class="sxs-lookup"><span data-stu-id="fa60c-128">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="fa60c-129">Переменные `arrayB` и `arrayC` не являются того же типа, так как типы их элементов различаются.</span><span class="sxs-lookup"><span data-stu-id="fa60c-129">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="fa60c-130">Переменные `arrayC` и `arrayD` не являются того же типа, так как их ранги различны.</span><span class="sxs-lookup"><span data-stu-id="fa60c-130">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="fa60c-131">Переменные `arrayD` и `arrayE` имеют одинаковый тип — `Short(,)` , так как их ранги и типы элементов одинаковы, даже если `arrayD` еще не инициализирован.</span><span class="sxs-lookup"><span data-stu-id="fa60c-131">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="fa60c-132">Дополнительные сведения о массивах см. в разделе [массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="fa60c-132">For more information on arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="fa60c-133">Типы классов</span><span class="sxs-lookup"><span data-stu-id="fa60c-133">Class Types</span></span>  
 <span data-ttu-id="fa60c-134">Нет единого типа данных, включающего в себя все классы.</span><span class="sxs-lookup"><span data-stu-id="fa60c-134">There is no single data type comprising all classes.</span></span> <span data-ttu-id="fa60c-135">Несмотря на то, что один класс может наследовать от другого класса, каждый является отдельным типом данных.</span><span class="sxs-lookup"><span data-stu-id="fa60c-135">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="fa60c-136">Несколько экземпляров одного класса имеют одинаковый тип данных.</span><span class="sxs-lookup"><span data-stu-id="fa60c-136">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="fa60c-137">Если назначить одну переменную экземпляра класса в другой, не только у них есть тот же тип данных, они указывают на один экземпляр класса в памяти.</span><span class="sxs-lookup"><span data-stu-id="fa60c-137">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="fa60c-138">Дополнительные сведения о классах см. в разделе [объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="fa60c-138">For more information on classes, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa60c-139">См. также</span><span class="sxs-lookup"><span data-stu-id="fa60c-139">See also</span></span>

- [<span data-ttu-id="fa60c-140">Типы данных</span><span class="sxs-lookup"><span data-stu-id="fa60c-140">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="fa60c-141">Простые типы данных</span><span class="sxs-lookup"><span data-stu-id="fa60c-141">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="fa60c-142">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fa60c-142">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="fa60c-143">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="fa60c-143">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="fa60c-144">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fa60c-144">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="fa60c-145">Структуры</span><span class="sxs-lookup"><span data-stu-id="fa60c-145">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="fa60c-146">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="fa60c-146">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="fa60c-147">Практическое руководство. Хранение нескольких значений в переменной</span><span class="sxs-lookup"><span data-stu-id="fa60c-147">How to: Hold More Than One Value in a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
