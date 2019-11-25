---
title: Оператор Dim
ms.date: 05/12/2018
f1_keywords:
- vb.Dim
- Dim
helpviewer_keywords:
- Public keyword [Visual Basic], in Dim statement
- Dim statement [Visual Basic]
- fixed-length strings [Visual Basic], declaring
- variables [Visual Basic], declaring
- WithEvents keyword [Visual Basic], Dim statement
- dynamic arrays [Visual Basic], Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields [Visual Basic], as member variables
- declarations [Visual Basic], dynamic arrays
- member variables [Visual Basic]
- default values [Visual Basic]
- data types [Visual Basic], assigning
- braces {}
- As keyword [Visual Basic], in Dim statement
- arrays [Visual Basic], declaring
- New keyword [Visual Basic], Dim statement
- To keyword [Visual Basic], in Dim statement
- storage [Visual Basic], allocating
- local variables [Visual Basic]
- declaration statements [Visual Basic]
- Dim statement [Visual Basic], syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
ms.openlocfilehash: ac66ffdba622673ef42017d147c05b2a2733dede
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343770"
---
# <a name="dim-statement-visual-basic"></a><span data-ttu-id="f4085-102">Оператор Dim (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4085-102">Dim Statement (Visual Basic)</span></span>

<span data-ttu-id="f4085-103">Declares and allocates storage space for one or more variables.</span><span class="sxs-lookup"><span data-stu-id="f4085-103">Declares and allocates storage space for one or more variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="f4085-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4085-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]
Dim [ WithEvents ] variablelist
```

## <a name="parts"></a><span data-ttu-id="f4085-105">Части</span><span class="sxs-lookup"><span data-stu-id="f4085-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="f4085-106">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="f4085-106">Optional.</span></span> <span data-ttu-id="f4085-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="f4085-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="f4085-108">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="f4085-108">Optional.</span></span> <span data-ttu-id="f4085-109">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="f4085-109">Can be one of the following:</span></span>

  - [<span data-ttu-id="f4085-110">Public</span><span class="sxs-lookup"><span data-stu-id="f4085-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

  - [<span data-ttu-id="f4085-111">Protected</span><span class="sxs-lookup"><span data-stu-id="f4085-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)

  - [<span data-ttu-id="f4085-112">Friend</span><span class="sxs-lookup"><span data-stu-id="f4085-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

  - [<span data-ttu-id="f4085-113">Закрытые</span><span class="sxs-lookup"><span data-stu-id="f4085-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)

  - [<span data-ttu-id="f4085-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="f4085-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="f4085-115">Private Protected</span><span class="sxs-lookup"><span data-stu-id="f4085-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="f4085-116">См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f4085-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `Shared`

  <span data-ttu-id="f4085-117">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="f4085-117">Optional.</span></span> <span data-ttu-id="f4085-118">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="f4085-118">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="f4085-119">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="f4085-119">Optional.</span></span> <span data-ttu-id="f4085-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="f4085-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

- `Static`

  <span data-ttu-id="f4085-121">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="f4085-121">Optional.</span></span> <span data-ttu-id="f4085-122">See [Static](../../../visual-basic/language-reference/modifiers/static.md).</span><span class="sxs-lookup"><span data-stu-id="f4085-122">See [Static](../../../visual-basic/language-reference/modifiers/static.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="f4085-123">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="f4085-123">Optional.</span></span> <span data-ttu-id="f4085-124">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="f4085-124">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>

- `WithEvents`

<span data-ttu-id="f4085-125">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="f4085-125">Optional.</span></span> <span data-ttu-id="f4085-126">Specifies that these are object variables that refer to instances of a class that can raise events.</span><span class="sxs-lookup"><span data-stu-id="f4085-126">Specifies that these are object variables that refer to instances of a class that can raise events.</span></span> <span data-ttu-id="f4085-127">See [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="f4085-127">See [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span></span>

- `variablelist`

  <span data-ttu-id="f4085-128">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f4085-128">Required.</span></span> <span data-ttu-id="f4085-129">List of variables being declared in this statement.</span><span class="sxs-lookup"><span data-stu-id="f4085-129">List of variables being declared in this statement.</span></span>

  `variable [ , variable ... ]`

  <span data-ttu-id="f4085-130">Каждый элемент `variable` имеет перечисленные ниже синтаксис и компоненты.</span><span class="sxs-lookup"><span data-stu-id="f4085-130">Each `variable` has the following syntax and parts:</span></span>

  <span data-ttu-id="f4085-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="f4085-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span></span>

  |<span data-ttu-id="f4085-132">Отделение</span><span class="sxs-lookup"><span data-stu-id="f4085-132">Part</span></span>|<span data-ttu-id="f4085-133">Описание</span><span class="sxs-lookup"><span data-stu-id="f4085-133">Description</span></span>|
  |---|---|
  |`variablename`|<span data-ttu-id="f4085-134">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f4085-134">Required.</span></span> <span data-ttu-id="f4085-135">Имя переменной.</span><span class="sxs-lookup"><span data-stu-id="f4085-135">Name of the variable.</span></span> <span data-ttu-id="f4085-136">См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="f4085-136">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
  |`boundslist`|<span data-ttu-id="f4085-137">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="f4085-137">Optional.</span></span> <span data-ttu-id="f4085-138">List of bounds of each dimension of an array variable.</span><span class="sxs-lookup"><span data-stu-id="f4085-138">List of bounds of each dimension of an array variable.</span></span>|
  |`New`|<span data-ttu-id="f4085-139">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="f4085-139">Optional.</span></span> <span data-ttu-id="f4085-140">Creates a new instance of the class when the `Dim` statement runs.</span><span class="sxs-lookup"><span data-stu-id="f4085-140">Creates a new instance of the class when the `Dim` statement runs.</span></span>|
  |`datatype`|<span data-ttu-id="f4085-141">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="f4085-141">Optional.</span></span> <span data-ttu-id="f4085-142">Data type of the variable.</span><span class="sxs-lookup"><span data-stu-id="f4085-142">Data type of the variable.</span></span>|
  |`With`|<span data-ttu-id="f4085-143">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="f4085-143">Optional.</span></span> <span data-ttu-id="f4085-144">Introduces the object initializer list.</span><span class="sxs-lookup"><span data-stu-id="f4085-144">Introduces the object initializer list.</span></span>|
  |`propertyname`|<span data-ttu-id="f4085-145">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="f4085-145">Optional.</span></span> <span data-ttu-id="f4085-146">The name of a property in the class you are making an instance of.</span><span class="sxs-lookup"><span data-stu-id="f4085-146">The name of a property in the class you are making an instance of.</span></span>|
  |`propinitializer`|<span data-ttu-id="f4085-147">Required after `propertyname` =.</span><span class="sxs-lookup"><span data-stu-id="f4085-147">Required after `propertyname` =.</span></span> <span data-ttu-id="f4085-148">The expression that is evaluated and assigned to the property name.</span><span class="sxs-lookup"><span data-stu-id="f4085-148">The expression that is evaluated and assigned to the property name.</span></span>|
  |`initializer`|<span data-ttu-id="f4085-149">Optional if `New` is not specified.</span><span class="sxs-lookup"><span data-stu-id="f4085-149">Optional if `New` is not specified.</span></span> <span data-ttu-id="f4085-150">Expression that is evaluated and assigned to the variable when it is created.</span><span class="sxs-lookup"><span data-stu-id="f4085-150">Expression that is evaluated and assigned to the variable when it is created.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f4085-151">Заметки</span><span class="sxs-lookup"><span data-stu-id="f4085-151">Remarks</span></span>

<span data-ttu-id="f4085-152">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span><span class="sxs-lookup"><span data-stu-id="f4085-152">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span></span> <span data-ttu-id="f4085-153">The following example declares a variable to hold an `Integer` value.</span><span class="sxs-lookup"><span data-stu-id="f4085-153">The following example declares a variable to hold an `Integer` value.</span></span>

```vb
Dim numberOfStudents As Integer
```

<span data-ttu-id="f4085-154">You can specify any data type or the name of an enumeration, structure, class, or interface.</span><span class="sxs-lookup"><span data-stu-id="f4085-154">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

```vb
Dim finished As Boolean
Dim monitorBox As System.Windows.Forms.Form
```

<span data-ttu-id="f4085-155">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span><span class="sxs-lookup"><span data-stu-id="f4085-155">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span></span> <span data-ttu-id="f4085-156">If you use `New`, you do not use an initializer expression.</span><span class="sxs-lookup"><span data-stu-id="f4085-156">If you use `New`, you do not use an initializer expression.</span></span> <span data-ttu-id="f4085-157">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span><span class="sxs-lookup"><span data-stu-id="f4085-157">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span></span>

```vb
Dim bottomLabel As New System.Windows.Forms.Label
```

<span data-ttu-id="f4085-158">You can declare a variable in a procedure, block, class, structure, or module.</span><span class="sxs-lookup"><span data-stu-id="f4085-158">You can declare a variable in a procedure, block, class, structure, or module.</span></span> <span data-ttu-id="f4085-159">You cannot declare a variable in a source file, namespace, or interface.</span><span class="sxs-lookup"><span data-stu-id="f4085-159">You cannot declare a variable in a source file, namespace, or interface.</span></span> <span data-ttu-id="f4085-160">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f4085-160">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="f4085-161">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span><span class="sxs-lookup"><span data-stu-id="f4085-161">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span></span> <span data-ttu-id="f4085-162">Member variables are in scope throughout their class, structure, or module.</span><span class="sxs-lookup"><span data-stu-id="f4085-162">Member variables are in scope throughout their class, structure, or module.</span></span> <span data-ttu-id="f4085-163">A variable that is declared at procedure level is a *local variable*.</span><span class="sxs-lookup"><span data-stu-id="f4085-163">A variable that is declared at procedure level is a *local variable*.</span></span> <span data-ttu-id="f4085-164">Local variables are in scope only within their procedure or block.</span><span class="sxs-lookup"><span data-stu-id="f4085-164">Local variables are in scope only within their procedure or block.</span></span>

<span data-ttu-id="f4085-165">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span><span class="sxs-lookup"><span data-stu-id="f4085-165">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span></span> <span data-ttu-id="f4085-166">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f4085-166">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="f4085-167">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="f4085-167">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span></span>

```vb
Public maximumAllowed As Double
Protected Friend currentUserName As String
Private salary As Decimal
Static runningTotal As Integer
```

<span data-ttu-id="f4085-168">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span><span class="sxs-lookup"><span data-stu-id="f4085-168">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span></span> <span data-ttu-id="f4085-169">For more information, see [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f4085-169">For more information, see [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span></span>

## <a name="specifying-an-initial-value"></a><span data-ttu-id="f4085-170">Specifying an Initial Value</span><span class="sxs-lookup"><span data-stu-id="f4085-170">Specifying an Initial Value</span></span>

<span data-ttu-id="f4085-171">You can assign a value to a variable when it is created.</span><span class="sxs-lookup"><span data-stu-id="f4085-171">You can assign a value to a variable when it is created.</span></span> <span data-ttu-id="f4085-172">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span><span class="sxs-lookup"><span data-stu-id="f4085-172">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span></span> <span data-ttu-id="f4085-173">The expression must evaluate to a constant that can be calculated at compile time.</span><span class="sxs-lookup"><span data-stu-id="f4085-173">The expression must evaluate to a constant that can be calculated at compile time.</span></span>

```vb
Dim quantity As Integer = 10
Dim message As String = "Just started"
```

<span data-ttu-id="f4085-174">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span><span class="sxs-lookup"><span data-stu-id="f4085-174">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span></span> <span data-ttu-id="f4085-175">In the following example, both `num1` and `num2` are strongly typed as integers.</span><span class="sxs-lookup"><span data-stu-id="f4085-175">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span> <span data-ttu-id="f4085-176">In the second declaration, type inference infers the type from the value 3.</span><span class="sxs-lookup"><span data-stu-id="f4085-176">In the second declaration, type inference infers the type from the value 3.</span></span>

```vb
' Use explicit typing.
Dim num1 As Integer = 3

' Use local type inference.
Dim num2 = 3
```

<span data-ttu-id="f4085-177">Type inference applies at the procedure level.</span><span class="sxs-lookup"><span data-stu-id="f4085-177">Type inference applies at the procedure level.</span></span> <span data-ttu-id="f4085-178">It does not apply outside a procedure in a class, structure, module, or interface.</span><span class="sxs-lookup"><span data-stu-id="f4085-178">It does not apply outside a procedure in a class, structure, module, or interface.</span></span> <span data-ttu-id="f4085-179">For more information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="f4085-179">For more information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>

<span data-ttu-id="f4085-180">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](../../../visual-basic/language-reference/statements/dim-statement.md#default) later in this topic.</span><span class="sxs-lookup"><span data-stu-id="f4085-180">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](../../../visual-basic/language-reference/statements/dim-statement.md#default) later in this topic.</span></span>

<span data-ttu-id="f4085-181">You can use an *object initializer* to declare instances of named and anonymous types.</span><span class="sxs-lookup"><span data-stu-id="f4085-181">You can use an *object initializer* to declare instances of named and anonymous types.</span></span> <span data-ttu-id="f4085-182">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span><span class="sxs-lookup"><span data-stu-id="f4085-182">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span></span>

```vb
Dim student1 As New Student With {.First = "Michael",
                                  .Last = "Tucker"}
```

<span data-ttu-id="f4085-183">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="f4085-183">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

## <a name="declaring-multiple-variables"></a><span data-ttu-id="f4085-184">Declaring Multiple Variables</span><span class="sxs-lookup"><span data-stu-id="f4085-184">Declaring Multiple Variables</span></span>

<span data-ttu-id="f4085-185">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span><span class="sxs-lookup"><span data-stu-id="f4085-185">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span></span> <span data-ttu-id="f4085-186">Переменные разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="f4085-186">Multiple variables are separated by commas.</span></span>

```vb
Dim lastTime, nextTime, allTimes() As Date
```

<span data-ttu-id="f4085-187">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span><span class="sxs-lookup"><span data-stu-id="f4085-187">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span></span>

<span data-ttu-id="f4085-188">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span><span class="sxs-lookup"><span data-stu-id="f4085-188">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="f4085-189">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span><span class="sxs-lookup"><span data-stu-id="f4085-189">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span></span>

```vb
Dim a, b, c As Single, x, y As Double, i As Integer
' a, b, and c are all Single; x and y are both Double
```

## <a name="arrays"></a><span data-ttu-id="f4085-190">Массивы</span><span class="sxs-lookup"><span data-stu-id="f4085-190">Arrays</span></span>

<span data-ttu-id="f4085-191">You can declare a variable to hold an *array*, which can hold multiple values.</span><span class="sxs-lookup"><span data-stu-id="f4085-191">You can declare a variable to hold an *array*, which can hold multiple values.</span></span> <span data-ttu-id="f4085-192">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span><span class="sxs-lookup"><span data-stu-id="f4085-192">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span></span> <span data-ttu-id="f4085-193">Дополнительные сведения см. в руководстве по работе с [массивами](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="f4085-193">For more information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>

<span data-ttu-id="f4085-194">You can specify the lower and upper bound of each dimension of an array.</span><span class="sxs-lookup"><span data-stu-id="f4085-194">You can specify the lower and upper bound of each dimension of an array.</span></span> <span data-ttu-id="f4085-195">To do this, include a `boundslist` inside the parentheses.</span><span class="sxs-lookup"><span data-stu-id="f4085-195">To do this, include a `boundslist` inside the parentheses.</span></span> <span data-ttu-id="f4085-196">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span><span class="sxs-lookup"><span data-stu-id="f4085-196">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span></span> <span data-ttu-id="f4085-197">The lower bound is always zero, whether you specify it or not.</span><span class="sxs-lookup"><span data-stu-id="f4085-197">The lower bound is always zero, whether you specify it or not.</span></span> <span data-ttu-id="f4085-198">Each index can vary from zero through its upper bound value.</span><span class="sxs-lookup"><span data-stu-id="f4085-198">Each index can vary from zero through its upper bound value.</span></span>

<span data-ttu-id="f4085-199">The following two statements are equivalent.</span><span class="sxs-lookup"><span data-stu-id="f4085-199">The following two statements are equivalent.</span></span> <span data-ttu-id="f4085-200">Each statement declares an array of 21 `Integer` elements.</span><span class="sxs-lookup"><span data-stu-id="f4085-200">Each statement declares an array of 21 `Integer` elements.</span></span> <span data-ttu-id="f4085-201">When you access the array, the index can vary from 0 through 20.</span><span class="sxs-lookup"><span data-stu-id="f4085-201">When you access the array, the index can vary from 0 through 20.</span></span>

```vb
Dim totals(20) As Integer
Dim totals(0 To 20) As Integer
```

<span data-ttu-id="f4085-202">The following statement declares a two-dimensional array of type `Double`.</span><span class="sxs-lookup"><span data-stu-id="f4085-202">The following statement declares a two-dimensional array of type `Double`.</span></span> <span data-ttu-id="f4085-203">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span><span class="sxs-lookup"><span data-stu-id="f4085-203">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span></span> <span data-ttu-id="f4085-204">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span><span class="sxs-lookup"><span data-stu-id="f4085-204">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span></span> <span data-ttu-id="f4085-205">The length of the dimension is the upper bound plus one.</span><span class="sxs-lookup"><span data-stu-id="f4085-205">The length of the dimension is the upper bound plus one.</span></span>

```vb
Dim matrix2(3, 5) As Double
```

<span data-ttu-id="f4085-206">An array can have from 1 to 32 dimensions.</span><span class="sxs-lookup"><span data-stu-id="f4085-206">An array can have from 1 to 32 dimensions.</span></span>

<span data-ttu-id="f4085-207">You can leave all the bounds blank in an array declaration.</span><span class="sxs-lookup"><span data-stu-id="f4085-207">You can leave all the bounds blank in an array declaration.</span></span> <span data-ttu-id="f4085-208">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span><span class="sxs-lookup"><span data-stu-id="f4085-208">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span></span> <span data-ttu-id="f4085-209">It has a value of `Nothing` until you initialize at least some of its elements.</span><span class="sxs-lookup"><span data-stu-id="f4085-209">It has a value of `Nothing` until you initialize at least some of its elements.</span></span> <span data-ttu-id="f4085-210">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span><span class="sxs-lookup"><span data-stu-id="f4085-210">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span></span>

```vb
' Declare an array with blank array bounds.
Dim messages() As String
' Initialize the array.
ReDim messages(4)
```

<span data-ttu-id="f4085-211">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span><span class="sxs-lookup"><span data-stu-id="f4085-211">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span></span>

```vb
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte
```

<span data-ttu-id="f4085-212">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span><span class="sxs-lookup"><span data-stu-id="f4085-212">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span></span> <span data-ttu-id="f4085-213">A variable that holds a zero-length array does not have the value `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="f4085-213">A variable that holds a zero-length array does not have the value `Nothing`.</span></span> <span data-ttu-id="f4085-214">Zero-length arrays are required by certain common language runtime functions.</span><span class="sxs-lookup"><span data-stu-id="f4085-214">Zero-length arrays are required by certain common language runtime functions.</span></span> <span data-ttu-id="f4085-215">If you try to access such an array, a runtime exception occurs.</span><span class="sxs-lookup"><span data-stu-id="f4085-215">If you try to access such an array, a runtime exception occurs.</span></span> <span data-ttu-id="f4085-216">Дополнительные сведения см. в статье [Arrays (C++/CLI and C++/CX)](../../../visual-basic/programming-guide/language-features/arrays/index.md) (Массивы (C++/CLI и C++/CX)).</span><span class="sxs-lookup"><span data-stu-id="f4085-216">For more information, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>

<span data-ttu-id="f4085-217">You can initialize the values of an array by using an array literal.</span><span class="sxs-lookup"><span data-stu-id="f4085-217">You can initialize the values of an array by using an array literal.</span></span> <span data-ttu-id="f4085-218">To do this, surround the initialization values with braces (`{}`).</span><span class="sxs-lookup"><span data-stu-id="f4085-218">To do this, surround the initialization values with braces (`{}`).</span></span>

```vb
Dim longArray() As Long = {0, 1, 2, 3}
```

<span data-ttu-id="f4085-219">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span><span class="sxs-lookup"><span data-stu-id="f4085-219">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span></span> <span data-ttu-id="f4085-220">The elements are specified in row-major order.</span><span class="sxs-lookup"><span data-stu-id="f4085-220">The elements are specified in row-major order.</span></span>

```vb
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}
```

<span data-ttu-id="f4085-221">For more information about array literals, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="f4085-221">For more information about array literals, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>

## <a name="default"></a> <span data-ttu-id="f4085-222">Default Data Types and Values</span><span class="sxs-lookup"><span data-stu-id="f4085-222">Default Data Types and Values</span></span>

<span data-ttu-id="f4085-223">В следующей таблице перечислены результаты различных сочетаний заданных типов данных и инициализаторов в операторе `Dim`.</span><span class="sxs-lookup"><span data-stu-id="f4085-223">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>

|<span data-ttu-id="f4085-224">Указан тип данных?</span><span class="sxs-lookup"><span data-stu-id="f4085-224">Data type specified?</span></span>|<span data-ttu-id="f4085-225">Указан инициализатор?</span><span class="sxs-lookup"><span data-stu-id="f4085-225">Initializer specified?</span></span>|<span data-ttu-id="f4085-226">Пример</span><span class="sxs-lookup"><span data-stu-id="f4085-226">Example</span></span>|<span data-ttu-id="f4085-227">Результат</span><span class="sxs-lookup"><span data-stu-id="f4085-227">Result</span></span>|
|---|---|---|---|
|<span data-ttu-id="f4085-228">Нет</span><span class="sxs-lookup"><span data-stu-id="f4085-228">No</span></span>|<span data-ttu-id="f4085-229">Нет</span><span class="sxs-lookup"><span data-stu-id="f4085-229">No</span></span>|`Dim qty`|<span data-ttu-id="f4085-230">If [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="f4085-230">If [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="f4085-231">Если параметр `Option Strict` включен, возникает ошибка времени при компиляции.</span><span class="sxs-lookup"><span data-stu-id="f4085-231">If `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="f4085-232">Нет</span><span class="sxs-lookup"><span data-stu-id="f4085-232">No</span></span>|<span data-ttu-id="f4085-233">Да</span><span class="sxs-lookup"><span data-stu-id="f4085-233">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="f4085-234">If [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span><span class="sxs-lookup"><span data-stu-id="f4085-234">If [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="f4085-235">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="f4085-235">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="f4085-236">Если параметры `Option Infer` и `Option Strict` отключены, переменная получает тип данных `Object`.</span><span class="sxs-lookup"><span data-stu-id="f4085-236">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="f4085-237">Если параметр `Option Infer` отключен, а параметр `Option Strict` включен, возникает ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="f4085-237">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="f4085-238">Да</span><span class="sxs-lookup"><span data-stu-id="f4085-238">Yes</span></span>|<span data-ttu-id="f4085-239">Нет</span><span class="sxs-lookup"><span data-stu-id="f4085-239">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="f4085-240">Переменная инициализируется со значением по умолчанию для типа данных.</span><span class="sxs-lookup"><span data-stu-id="f4085-240">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="f4085-241">See the table later in this section.</span><span class="sxs-lookup"><span data-stu-id="f4085-241">See the table later in this section.</span></span>|
|<span data-ttu-id="f4085-242">Да</span><span class="sxs-lookup"><span data-stu-id="f4085-242">Yes</span></span>|<span data-ttu-id="f4085-243">Да</span><span class="sxs-lookup"><span data-stu-id="f4085-243">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="f4085-244">Если тип данных инициализатора нельзя преобразовать в указанный тип данных, возникает ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="f4085-244">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|

<span data-ttu-id="f4085-245">If you specify a data type but do not specify an initializer, Visual Basic initializes the variable to the default value for its data type.</span><span class="sxs-lookup"><span data-stu-id="f4085-245">If you specify a data type but do not specify an initializer, Visual Basic initializes the variable to the default value for its data type.</span></span> <span data-ttu-id="f4085-246">The following table shows the default initialization values.</span><span class="sxs-lookup"><span data-stu-id="f4085-246">The following table shows the default initialization values.</span></span>

|<span data-ttu-id="f4085-247">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f4085-247">Data type</span></span>|<span data-ttu-id="f4085-248">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f4085-248">Default value</span></span>|
|---|---|
|<span data-ttu-id="f4085-249">All numeric types (including `Byte` and `SByte`)</span><span class="sxs-lookup"><span data-stu-id="f4085-249">All numeric types (including `Byte` and `SByte`)</span></span>|<span data-ttu-id="f4085-250">0</span><span class="sxs-lookup"><span data-stu-id="f4085-250">0</span></span>|
|`Char`|<span data-ttu-id="f4085-251">Binary 0</span><span class="sxs-lookup"><span data-stu-id="f4085-251">Binary 0</span></span>|
|<span data-ttu-id="f4085-252">All reference types (including `Object`, `String`, and all arrays)</span><span class="sxs-lookup"><span data-stu-id="f4085-252">All reference types (including `Object`, `String`, and all arrays)</span></span>|`Nothing`|
|`Boolean`|`False`|
|`Date`|<span data-ttu-id="f4085-253">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span><span class="sxs-lookup"><span data-stu-id="f4085-253">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span></span>|

<span data-ttu-id="f4085-254">Each element of a structure is initialized as if it were a separate variable.</span><span class="sxs-lookup"><span data-stu-id="f4085-254">Each element of a structure is initialized as if it were a separate variable.</span></span> <span data-ttu-id="f4085-255">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span><span class="sxs-lookup"><span data-stu-id="f4085-255">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span></span>

## <a name="static-local-variable-lifetime"></a><span data-ttu-id="f4085-256">Static Local Variable Lifetime</span><span class="sxs-lookup"><span data-stu-id="f4085-256">Static Local Variable Lifetime</span></span>

<span data-ttu-id="f4085-257">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span><span class="sxs-lookup"><span data-stu-id="f4085-257">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span></span> <span data-ttu-id="f4085-258">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span><span class="sxs-lookup"><span data-stu-id="f4085-258">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span></span>

|<span data-ttu-id="f4085-259">Procedure declaration</span><span class="sxs-lookup"><span data-stu-id="f4085-259">Procedure declaration</span></span>|<span data-ttu-id="f4085-260">Variable initialized</span><span class="sxs-lookup"><span data-stu-id="f4085-260">Variable initialized</span></span>|<span data-ttu-id="f4085-261">Variable stops existing</span><span class="sxs-lookup"><span data-stu-id="f4085-261">Variable stops existing</span></span>|
|---|---|---|
|<span data-ttu-id="f4085-262">In a module</span><span class="sxs-lookup"><span data-stu-id="f4085-262">In a module</span></span>|<span data-ttu-id="f4085-263">The first time the procedure is called</span><span class="sxs-lookup"><span data-stu-id="f4085-263">The first time the procedure is called</span></span>|<span data-ttu-id="f4085-264">When your program stops execution</span><span class="sxs-lookup"><span data-stu-id="f4085-264">When your program stops execution</span></span>|
|<span data-ttu-id="f4085-265">In a class or structure, procedure is `Shared`</span><span class="sxs-lookup"><span data-stu-id="f4085-265">In a class or structure, procedure is `Shared`</span></span>|<span data-ttu-id="f4085-266">The first time the procedure is called either on a specific instance or on the class or structure itself</span><span class="sxs-lookup"><span data-stu-id="f4085-266">The first time the procedure is called either on a specific instance or on the class or structure itself</span></span>|<span data-ttu-id="f4085-267">When your program stops execution</span><span class="sxs-lookup"><span data-stu-id="f4085-267">When your program stops execution</span></span>|
|<span data-ttu-id="f4085-268">In a class or structure, procedure isn't `Shared`</span><span class="sxs-lookup"><span data-stu-id="f4085-268">In a class or structure, procedure isn't `Shared`</span></span>|<span data-ttu-id="f4085-269">The first time the procedure is called on a specific instance</span><span class="sxs-lookup"><span data-stu-id="f4085-269">The first time the procedure is called on a specific instance</span></span>|<span data-ttu-id="f4085-270">When the instance is released for garbage collection (GC)</span><span class="sxs-lookup"><span data-stu-id="f4085-270">When the instance is released for garbage collection (GC)</span></span>|

## <a name="attributes-and-modifiers"></a><span data-ttu-id="f4085-271">Attributes and Modifiers</span><span class="sxs-lookup"><span data-stu-id="f4085-271">Attributes and Modifiers</span></span>

<span data-ttu-id="f4085-272">You can apply attributes only to member variables, not to local variables.</span><span class="sxs-lookup"><span data-stu-id="f4085-272">You can apply attributes only to member variables, not to local variables.</span></span> <span data-ttu-id="f4085-273">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span><span class="sxs-lookup"><span data-stu-id="f4085-273">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span></span>

<span data-ttu-id="f4085-274">At module level, you cannot use the `Static` modifier to declare member variables.</span><span class="sxs-lookup"><span data-stu-id="f4085-274">At module level, you cannot use the `Static` modifier to declare member variables.</span></span> <span data-ttu-id="f4085-275">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span><span class="sxs-lookup"><span data-stu-id="f4085-275">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span></span>

<span data-ttu-id="f4085-276">You can specify what code can access a variable by supplying an `accessmodifier`.</span><span class="sxs-lookup"><span data-stu-id="f4085-276">You can specify what code can access a variable by supplying an `accessmodifier`.</span></span> <span data-ttu-id="f4085-277">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span><span class="sxs-lookup"><span data-stu-id="f4085-277">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span></span> <span data-ttu-id="f4085-278">You can adjust their access levels with the access modifiers.</span><span class="sxs-lookup"><span data-stu-id="f4085-278">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="f4085-279">You cannot use access modifiers on local variables (inside a procedure).</span><span class="sxs-lookup"><span data-stu-id="f4085-279">You cannot use access modifiers on local variables (inside a procedure).</span></span>

<span data-ttu-id="f4085-280">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span><span class="sxs-lookup"><span data-stu-id="f4085-280">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span></span> <span data-ttu-id="f4085-281">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span><span class="sxs-lookup"><span data-stu-id="f4085-281">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span></span> <span data-ttu-id="f4085-282">You cannot declare an array with `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="f4085-282">You cannot declare an array with `WithEvents`.</span></span> <span data-ttu-id="f4085-283">For more information about events, see [Events](../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="f4085-283">For more information about events, see [Events](../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f4085-284">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span><span class="sxs-lookup"><span data-stu-id="f4085-284">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="f4085-285">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span><span class="sxs-lookup"><span data-stu-id="f4085-285">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span></span>

## <a name="releasing-managed-resources"></a><span data-ttu-id="f4085-286">Releasing Managed Resources</span><span class="sxs-lookup"><span data-stu-id="f4085-286">Releasing Managed Resources</span></span>

<span data-ttu-id="f4085-287">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span><span class="sxs-lookup"><span data-stu-id="f4085-287">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span></span> <span data-ttu-id="f4085-288">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span><span class="sxs-lookup"><span data-stu-id="f4085-288">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>

<span data-ttu-id="f4085-289">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span><span class="sxs-lookup"><span data-stu-id="f4085-289">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span></span> <span data-ttu-id="f4085-290">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="f4085-290">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span></span> <span data-ttu-id="f4085-291">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span><span class="sxs-lookup"><span data-stu-id="f4085-291">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span></span>

<span data-ttu-id="f4085-292">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span><span class="sxs-lookup"><span data-stu-id="f4085-292">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span></span> <span data-ttu-id="f4085-293">However, the resource must implement the <xref:System.IDisposable> interface.</span><span class="sxs-lookup"><span data-stu-id="f4085-293">However, the resource must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="f4085-294">Дополнительные сведения см. в разделе [Оператор using](../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f4085-294">For more information, see [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="f4085-295">Пример</span><span class="sxs-lookup"><span data-stu-id="f4085-295">Example</span></span>

<span data-ttu-id="f4085-296">The following example declares variables by using the `Dim` statement with various options.</span><span class="sxs-lookup"><span data-stu-id="f4085-296">The following example declares variables by using the `Dim` statement with various options.</span></span>

[!code-vb[VbVbalrStatements#141](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#141)]

## <a name="example"></a><span data-ttu-id="f4085-297">Пример</span><span class="sxs-lookup"><span data-stu-id="f4085-297">Example</span></span>

<span data-ttu-id="f4085-298">The following example lists the prime numbers between 1 and 30.</span><span class="sxs-lookup"><span data-stu-id="f4085-298">The following example lists the prime numbers between 1 and 30.</span></span> <span data-ttu-id="f4085-299">The scope of local variables is described in code comments.</span><span class="sxs-lookup"><span data-stu-id="f4085-299">The scope of local variables is described in code comments.</span></span>

[!code-vb[VbVbalrStatements#142](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#142)]

## <a name="example"></a><span data-ttu-id="f4085-300">Пример</span><span class="sxs-lookup"><span data-stu-id="f4085-300">Example</span></span>

<span data-ttu-id="f4085-301">In the following example, the `speedValue` variable is declared at the class level.</span><span class="sxs-lookup"><span data-stu-id="f4085-301">In the following example, the `speedValue` variable is declared at the class level.</span></span> <span data-ttu-id="f4085-302">The `Private` keyword is used to declare the variable.</span><span class="sxs-lookup"><span data-stu-id="f4085-302">The `Private` keyword is used to declare the variable.</span></span> <span data-ttu-id="f4085-303">The variable can be accessed by any procedure in the `Car` class.</span><span class="sxs-lookup"><span data-stu-id="f4085-303">The variable can be accessed by any procedure in the `Car` class.</span></span>

[!code-vb[VbVbalrStatements#144](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#144)]

[!code-vb[VbVbalrStatements#145](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#145)]

## <a name="see-also"></a><span data-ttu-id="f4085-304">См. также</span><span class="sxs-lookup"><span data-stu-id="f4085-304">See also</span></span>

- [<span data-ttu-id="f4085-305">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="f4085-305">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="f4085-306">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="f4085-306">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="f4085-307">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="f4085-307">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="f4085-308">Оператор Option Infer</span><span class="sxs-lookup"><span data-stu-id="f4085-308">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="f4085-309">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="f4085-309">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="f4085-310">Страница "Компиляция" в конструкторе проектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4085-310">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="f4085-311">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="f4085-311">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="f4085-312">Массивы</span><span class="sxs-lookup"><span data-stu-id="f4085-312">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="f4085-313">Инициализаторы объектов. Именованные и анонимные типы</span><span class="sxs-lookup"><span data-stu-id="f4085-313">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="f4085-314">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="f4085-314">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="f4085-315">Инициализаторы объектов. Именованные и анонимные типы</span><span class="sxs-lookup"><span data-stu-id="f4085-315">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="f4085-316">Практическое руководство. Объявление объекта с помощью инициализатора объектов</span><span class="sxs-lookup"><span data-stu-id="f4085-316">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
- [<span data-ttu-id="f4085-317">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="f4085-317">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
