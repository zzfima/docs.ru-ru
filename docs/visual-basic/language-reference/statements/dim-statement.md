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
# <a name="dim-statement-visual-basic"></a><span data-ttu-id="3140d-102">Оператор Dim (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3140d-102">Dim Statement (Visual Basic)</span></span>

<span data-ttu-id="3140d-103">Объявляет и выделяет дисковое пространство для одной или нескольких переменных.</span><span class="sxs-lookup"><span data-stu-id="3140d-103">Declares and allocates storage space for one or more variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="3140d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3140d-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]
Dim [ WithEvents ] variablelist
```

## <a name="parts"></a><span data-ttu-id="3140d-105">Части</span><span class="sxs-lookup"><span data-stu-id="3140d-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="3140d-106">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="3140d-106">Optional.</span></span> <span data-ttu-id="3140d-107">См. [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="3140d-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="3140d-108">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="3140d-108">Optional.</span></span> <span data-ttu-id="3140d-109">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="3140d-109">Can be one of the following:</span></span>

  - [<span data-ttu-id="3140d-110">Public</span><span class="sxs-lookup"><span data-stu-id="3140d-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

  - [<span data-ttu-id="3140d-111">Protected</span><span class="sxs-lookup"><span data-stu-id="3140d-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)

  - [<span data-ttu-id="3140d-112">Friend</span><span class="sxs-lookup"><span data-stu-id="3140d-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

  - [<span data-ttu-id="3140d-113">Закрытые</span><span class="sxs-lookup"><span data-stu-id="3140d-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)

  - [<span data-ttu-id="3140d-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="3140d-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="3140d-115">Private Protected</span><span class="sxs-lookup"><span data-stu-id="3140d-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="3140d-116">См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3140d-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `Shared`

  <span data-ttu-id="3140d-117">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="3140d-117">Optional.</span></span> <span data-ttu-id="3140d-118">См. раздел [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="3140d-118">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="3140d-119">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="3140d-119">Optional.</span></span> <span data-ttu-id="3140d-120">См. раздел [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="3140d-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

- `Static`

  <span data-ttu-id="3140d-121">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="3140d-121">Optional.</span></span> <span data-ttu-id="3140d-122">См. раздел [static](../../../visual-basic/language-reference/modifiers/static.md).</span><span class="sxs-lookup"><span data-stu-id="3140d-122">See [Static](../../../visual-basic/language-reference/modifiers/static.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="3140d-123">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="3140d-123">Optional.</span></span> <span data-ttu-id="3140d-124">См. раздел [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="3140d-124">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>

- `WithEvents`

<span data-ttu-id="3140d-125">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="3140d-125">Optional.</span></span> <span data-ttu-id="3140d-126">Указывает, что это переменные объекта, которые ссылаются на экземпляры класса, которые могут создавать события.</span><span class="sxs-lookup"><span data-stu-id="3140d-126">Specifies that these are object variables that refer to instances of a class that can raise events.</span></span> <span data-ttu-id="3140d-127">См. раздел [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="3140d-127">See [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span></span>

- `variablelist`

  <span data-ttu-id="3140d-128">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="3140d-128">Required.</span></span> <span data-ttu-id="3140d-129">Список переменных, объявляемых в этой инструкции.</span><span class="sxs-lookup"><span data-stu-id="3140d-129">List of variables being declared in this statement.</span></span>

  `variable [ , variable ... ]`

  <span data-ttu-id="3140d-130">Каждый элемент `variable` имеет перечисленные ниже синтаксис и компоненты.</span><span class="sxs-lookup"><span data-stu-id="3140d-130">Each `variable` has the following syntax and parts:</span></span>

  <span data-ttu-id="3140d-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="3140d-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span></span>

  |<span data-ttu-id="3140d-132">Отделение</span><span class="sxs-lookup"><span data-stu-id="3140d-132">Part</span></span>|<span data-ttu-id="3140d-133">Описание</span><span class="sxs-lookup"><span data-stu-id="3140d-133">Description</span></span>|
  |---|---|
  |`variablename`|<span data-ttu-id="3140d-134">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="3140d-134">Required.</span></span> <span data-ttu-id="3140d-135">Имя переменной.</span><span class="sxs-lookup"><span data-stu-id="3140d-135">Name of the variable.</span></span> <span data-ttu-id="3140d-136">См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="3140d-136">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
  |`boundslist`|<span data-ttu-id="3140d-137">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="3140d-137">Optional.</span></span> <span data-ttu-id="3140d-138">Список границ каждого измерения переменной массива.</span><span class="sxs-lookup"><span data-stu-id="3140d-138">List of bounds of each dimension of an array variable.</span></span>|
  |`New`|<span data-ttu-id="3140d-139">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="3140d-139">Optional.</span></span> <span data-ttu-id="3140d-140">Создает новый экземпляр класса при выполнении инструкции `Dim`.</span><span class="sxs-lookup"><span data-stu-id="3140d-140">Creates a new instance of the class when the `Dim` statement runs.</span></span>|
  |`datatype`|<span data-ttu-id="3140d-141">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="3140d-141">Optional.</span></span> <span data-ttu-id="3140d-142">Тип данных переменной.</span><span class="sxs-lookup"><span data-stu-id="3140d-142">Data type of the variable.</span></span>|
  |`With`|<span data-ttu-id="3140d-143">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="3140d-143">Optional.</span></span> <span data-ttu-id="3140d-144">Представляет список инициализаторов объектов.</span><span class="sxs-lookup"><span data-stu-id="3140d-144">Introduces the object initializer list.</span></span>|
  |`propertyname`|<span data-ttu-id="3140d-145">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="3140d-145">Optional.</span></span> <span data-ttu-id="3140d-146">Имя свойства в классе, экземпляр которого вы вносите.</span><span class="sxs-lookup"><span data-stu-id="3140d-146">The name of a property in the class you are making an instance of.</span></span>|
  |`propinitializer`|<span data-ttu-id="3140d-147">Требуется после `propertyname` =.</span><span class="sxs-lookup"><span data-stu-id="3140d-147">Required after `propertyname` =.</span></span> <span data-ttu-id="3140d-148">Выражение, которое вычисляется и присваивается имени свойства.</span><span class="sxs-lookup"><span data-stu-id="3140d-148">The expression that is evaluated and assigned to the property name.</span></span>|
  |`initializer`|<span data-ttu-id="3140d-149">Необязательный, если не указан `New`.</span><span class="sxs-lookup"><span data-stu-id="3140d-149">Optional if `New` is not specified.</span></span> <span data-ttu-id="3140d-150">Выражение, которое вычисляется и присваивается переменной при ее создании.</span><span class="sxs-lookup"><span data-stu-id="3140d-150">Expression that is evaluated and assigned to the variable when it is created.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3140d-151">Заметки</span><span class="sxs-lookup"><span data-stu-id="3140d-151">Remarks</span></span>

<span data-ttu-id="3140d-152">Компилятор Visual Basic использует инструкцию `Dim` для определения типа данных переменной и других сведений, например кода, который может получить доступ к переменной.</span><span class="sxs-lookup"><span data-stu-id="3140d-152">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span></span> <span data-ttu-id="3140d-153">В следующем примере объявляется переменная для хранения `Integer` значения.</span><span class="sxs-lookup"><span data-stu-id="3140d-153">The following example declares a variable to hold an `Integer` value.</span></span>

```vb
Dim numberOfStudents As Integer
```

<span data-ttu-id="3140d-154">Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3140d-154">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

```vb
Dim finished As Boolean
Dim monitorBox As System.Windows.Forms.Form
```

<span data-ttu-id="3140d-155">Для ссылочного типа используется ключевое слово `New` для создания нового экземпляра класса или структуры, определяемой типом данных.</span><span class="sxs-lookup"><span data-stu-id="3140d-155">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span></span> <span data-ttu-id="3140d-156">Если используется `New`, выражение инициализатора не используется.</span><span class="sxs-lookup"><span data-stu-id="3140d-156">If you use `New`, you do not use an initializer expression.</span></span> <span data-ttu-id="3140d-157">Вместо этого вы предоставляете аргументы, если они требуются, в конструктор класса, из которого создается переменная.</span><span class="sxs-lookup"><span data-stu-id="3140d-157">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span></span>

```vb
Dim bottomLabel As New System.Windows.Forms.Label
```

<span data-ttu-id="3140d-158">Переменную можно объявить в процедуре, блоке, классе, структуре или модуле.</span><span class="sxs-lookup"><span data-stu-id="3140d-158">You can declare a variable in a procedure, block, class, structure, or module.</span></span> <span data-ttu-id="3140d-159">Нельзя объявить переменную в исходном файле, пространстве имен или интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="3140d-159">You cannot declare a variable in a source file, namespace, or interface.</span></span> <span data-ttu-id="3140d-160">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3140d-160">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="3140d-161">Переменная, объявленная на уровне модуля вне любой процедуры, является переменной или *полем* *члена* .</span><span class="sxs-lookup"><span data-stu-id="3140d-161">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span></span> <span data-ttu-id="3140d-162">Переменные членов находятся в области действия класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="3140d-162">Member variables are in scope throughout their class, structure, or module.</span></span> <span data-ttu-id="3140d-163">Переменная, объявленная на уровне процедуры, является *локальной переменной*.</span><span class="sxs-lookup"><span data-stu-id="3140d-163">A variable that is declared at procedure level is a *local variable*.</span></span> <span data-ttu-id="3140d-164">Локальные переменные находятся в области действия только в пределах их процедуры или блока.</span><span class="sxs-lookup"><span data-stu-id="3140d-164">Local variables are in scope only within their procedure or block.</span></span>

<span data-ttu-id="3140d-165">Следующие модификаторы доступа используются для объявления переменных вне процедуры: `Public`, `Protected`, `Friend`, `Protected Friend`и `Private`.</span><span class="sxs-lookup"><span data-stu-id="3140d-165">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span></span> <span data-ttu-id="3140d-166">Дополнительные сведения см. [в разделе уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3140d-166">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="3140d-167">Ключевое слово `Dim` является необязательным и обычно опускается при указании любого из следующих модификаторов: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`или `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="3140d-167">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span></span>

```vb
Public maximumAllowed As Double
Protected Friend currentUserName As String
Private salary As Decimal
Static runningTotal As Integer
```

<span data-ttu-id="3140d-168">Если `Option Explicit` имеет значение On (значение по умолчанию), компилятору требуется объявление для каждой используемой переменной.</span><span class="sxs-lookup"><span data-stu-id="3140d-168">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span></span> <span data-ttu-id="3140d-169">Дополнительные сведения см. в разделе [оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3140d-169">For more information, see [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span></span>

## <a name="specifying-an-initial-value"></a><span data-ttu-id="3140d-170">Указание начального значения</span><span class="sxs-lookup"><span data-stu-id="3140d-170">Specifying an Initial Value</span></span>

<span data-ttu-id="3140d-171">При создании переменной можно присвоить значение.</span><span class="sxs-lookup"><span data-stu-id="3140d-171">You can assign a value to a variable when it is created.</span></span> <span data-ttu-id="3140d-172">Для типа значения используйте *инициализатор* , чтобы указать выражение, присваиваемое переменной.</span><span class="sxs-lookup"><span data-stu-id="3140d-172">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span></span> <span data-ttu-id="3140d-173">Результатом вычисления выражения должно быть константа, которую можно вычислить во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="3140d-173">The expression must evaluate to a constant that can be calculated at compile time.</span></span>

```vb
Dim quantity As Integer = 10
Dim message As String = "Just started"
```

<span data-ttu-id="3140d-174">Если инициализатор указан и тип данных не указан в предложении `As`, *Определение* типа используется для получения типа данных из инициализатора.</span><span class="sxs-lookup"><span data-stu-id="3140d-174">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span></span> <span data-ttu-id="3140d-175">В следующем примере и `num1`, и `num2` строго типизированы как целые числа.</span><span class="sxs-lookup"><span data-stu-id="3140d-175">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span> <span data-ttu-id="3140d-176">Во втором объявлении определение типа выводит тип из значения 3.</span><span class="sxs-lookup"><span data-stu-id="3140d-176">In the second declaration, type inference infers the type from the value 3.</span></span>

```vb
' Use explicit typing.
Dim num1 As Integer = 3

' Use local type inference.
Dim num2 = 3
```

<span data-ttu-id="3140d-177">Определение типа применяется на уровне процедуры.</span><span class="sxs-lookup"><span data-stu-id="3140d-177">Type inference applies at the procedure level.</span></span> <span data-ttu-id="3140d-178">Он не применяется за пределами процедуры в классе, структуре, модуле или интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="3140d-178">It does not apply outside a procedure in a class, structure, module, or interface.</span></span> <span data-ttu-id="3140d-179">Дополнительные сведения о выводе типа см. в разделе [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) и [определение локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="3140d-179">For more information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>

<span data-ttu-id="3140d-180">Сведения о том, что происходит, если не указан тип данных или инициализатор, см. в подразделе [типы данных и значения по умолчанию](../../../visual-basic/language-reference/statements/dim-statement.md#default) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="3140d-180">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](../../../visual-basic/language-reference/statements/dim-statement.md#default) later in this topic.</span></span>

<span data-ttu-id="3140d-181">*Инициализатор объекта* можно использовать для объявления экземпляров именованных и анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="3140d-181">You can use an *object initializer* to declare instances of named and anonymous types.</span></span> <span data-ttu-id="3140d-182">Следующий код создает экземпляр класса `Student` и использует инициализатор объекта для инициализации свойств.</span><span class="sxs-lookup"><span data-stu-id="3140d-182">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span></span>

```vb
Dim student1 As New Student With {.First = "Michael",
                                  .Last = "Tucker"}
```

<span data-ttu-id="3140d-183">Дополнительные сведения об инициализаторах объектов см. [в разделе как объявить объект с помощью инициализатора](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)объекта, [инициализаторов объектов: именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)и [анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="3140d-183">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

## <a name="declaring-multiple-variables"></a><span data-ttu-id="3140d-184">Объявление нескольких переменных</span><span class="sxs-lookup"><span data-stu-id="3140d-184">Declaring Multiple Variables</span></span>

<span data-ttu-id="3140d-185">Можно объявить несколько переменных в одном операторе объявления, указав имя переменной для каждой из них, и после каждого имени массива с круглыми скобками.</span><span class="sxs-lookup"><span data-stu-id="3140d-185">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span></span> <span data-ttu-id="3140d-186">Переменные разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="3140d-186">Multiple variables are separated by commas.</span></span>

```vb
Dim lastTime, nextTime, allTimes() As Date
```

<span data-ttu-id="3140d-187">Если объявить более одной переменной с одним предложением `As`, вы не сможете предоставить инициализатор для этой группы переменных.</span><span class="sxs-lookup"><span data-stu-id="3140d-187">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span></span>

<span data-ttu-id="3140d-188">Можно указать различные типы данных для разных переменных, используя отдельное предложение `As` для каждой объявляемой переменной.</span><span class="sxs-lookup"><span data-stu-id="3140d-188">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="3140d-189">Каждая переменная принимает тип данных, указанный в первом предложении `As`, обнаруженном после его части `variablename`.</span><span class="sxs-lookup"><span data-stu-id="3140d-189">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span></span>

```vb
Dim a, b, c As Single, x, y As Double, i As Integer
' a, b, and c are all Single; x and y are both Double
```

## <a name="arrays"></a><span data-ttu-id="3140d-190">Массивы</span><span class="sxs-lookup"><span data-stu-id="3140d-190">Arrays</span></span>

<span data-ttu-id="3140d-191">Можно объявить переменную для хранения *массива*, который может содержать несколько значений.</span><span class="sxs-lookup"><span data-stu-id="3140d-191">You can declare a variable to hold an *array*, which can hold multiple values.</span></span> <span data-ttu-id="3140d-192">Чтобы указать, что переменная содержит массив, следует следовать его `variablename` сразу же с круглыми скобками.</span><span class="sxs-lookup"><span data-stu-id="3140d-192">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span></span> <span data-ttu-id="3140d-193">Дополнительные сведения см. в руководстве по работе с [массивами](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="3140d-193">For more information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>

<span data-ttu-id="3140d-194">Можно указать нижнюю и верхнюю границы каждого измерения массива.</span><span class="sxs-lookup"><span data-stu-id="3140d-194">You can specify the lower and upper bound of each dimension of an array.</span></span> <span data-ttu-id="3140d-195">Для этого включите `boundslist` в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="3140d-195">To do this, include a `boundslist` inside the parentheses.</span></span> <span data-ttu-id="3140d-196">Для каждого измерения `boundslist` указывает верхнюю границу и, при необходимости, нижнюю границу.</span><span class="sxs-lookup"><span data-stu-id="3140d-196">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span></span> <span data-ttu-id="3140d-197">Нижняя граница всегда равна нулю, независимо от того, указана она или нет.</span><span class="sxs-lookup"><span data-stu-id="3140d-197">The lower bound is always zero, whether you specify it or not.</span></span> <span data-ttu-id="3140d-198">Каждый индекс может изменяться от нуля до значения его верхней границы.</span><span class="sxs-lookup"><span data-stu-id="3140d-198">Each index can vary from zero through its upper bound value.</span></span>

<span data-ttu-id="3140d-199">Следующие две инструкции эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="3140d-199">The following two statements are equivalent.</span></span> <span data-ttu-id="3140d-200">Каждый оператор объявляет массив из 21 `Integer` элементов.</span><span class="sxs-lookup"><span data-stu-id="3140d-200">Each statement declares an array of 21 `Integer` elements.</span></span> <span data-ttu-id="3140d-201">При доступе к массиву индекс может изменяться от 0 до 20.</span><span class="sxs-lookup"><span data-stu-id="3140d-201">When you access the array, the index can vary from 0 through 20.</span></span>

```vb
Dim totals(20) As Integer
Dim totals(0 To 20) As Integer
```

<span data-ttu-id="3140d-202">В следующей инструкции объявляется двухмерный массив типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="3140d-202">The following statement declares a two-dimensional array of type `Double`.</span></span> <span data-ttu-id="3140d-203">Массив содержит 4 строки (3 + 1) из 6 столбцов (5 + 1) каждого.</span><span class="sxs-lookup"><span data-stu-id="3140d-203">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span></span> <span data-ttu-id="3140d-204">Обратите внимание, что верхняя граница представляет наибольшее возможное значение индекса, а не длину измерения.</span><span class="sxs-lookup"><span data-stu-id="3140d-204">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span></span> <span data-ttu-id="3140d-205">Длина измерения является верхней границей плюс единица.</span><span class="sxs-lookup"><span data-stu-id="3140d-205">The length of the dimension is the upper bound plus one.</span></span>

```vb
Dim matrix2(3, 5) As Double
```

<span data-ttu-id="3140d-206">Массив может иметь размер от 1 до 32.</span><span class="sxs-lookup"><span data-stu-id="3140d-206">An array can have from 1 to 32 dimensions.</span></span>

<span data-ttu-id="3140d-207">Все границы в объявлении массива можно оставить пустыми.</span><span class="sxs-lookup"><span data-stu-id="3140d-207">You can leave all the bounds blank in an array declaration.</span></span> <span data-ttu-id="3140d-208">В этом случае массив имеет указанное число измерений, но не инициализировано.</span><span class="sxs-lookup"><span data-stu-id="3140d-208">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span></span> <span data-ttu-id="3140d-209">Он имеет значение `Nothing`, пока не будут инициализированы хотя бы некоторые его элементы.</span><span class="sxs-lookup"><span data-stu-id="3140d-209">It has a value of `Nothing` until you initialize at least some of its elements.</span></span> <span data-ttu-id="3140d-210">В операторе `Dim` должны быть указаны границы для всех измерений или для отсутствия измерений.</span><span class="sxs-lookup"><span data-stu-id="3140d-210">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span></span>

```vb
' Declare an array with blank array bounds.
Dim messages() As String
' Initialize the array.
ReDim messages(4)
```

<span data-ttu-id="3140d-211">Если массив имеет более одного измерения, необходимо включить запятые между круглыми скобками, чтобы указать количество измерений.</span><span class="sxs-lookup"><span data-stu-id="3140d-211">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span></span>

```vb
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte
```

<span data-ttu-id="3140d-212">Можно объявить *массив нулевой длины* , объявляя один из измерений массива равным-1.</span><span class="sxs-lookup"><span data-stu-id="3140d-212">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span></span> <span data-ttu-id="3140d-213">Переменная, содержащая массив нулевой длины, не имеет значения `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="3140d-213">A variable that holds a zero-length array does not have the value `Nothing`.</span></span> <span data-ttu-id="3140d-214">Для некоторых функций среды CLR требуются массивы нулевой длины.</span><span class="sxs-lookup"><span data-stu-id="3140d-214">Zero-length arrays are required by certain common language runtime functions.</span></span> <span data-ttu-id="3140d-215">При попытке доступа к такому массиву возникает исключение времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="3140d-215">If you try to access such an array, a runtime exception occurs.</span></span> <span data-ttu-id="3140d-216">Дополнительные сведения см. в статье [Arrays (C++/CLI and C++/CX)](../../../visual-basic/programming-guide/language-features/arrays/index.md) (Массивы (C++/CLI и C++/CX)).</span><span class="sxs-lookup"><span data-stu-id="3140d-216">For more information, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>

<span data-ttu-id="3140d-217">Значения массива можно инициализировать с помощью литерала массива.</span><span class="sxs-lookup"><span data-stu-id="3140d-217">You can initialize the values of an array by using an array literal.</span></span> <span data-ttu-id="3140d-218">Для этого заключите значения инициализации в фигурные скобки (`{}`).</span><span class="sxs-lookup"><span data-stu-id="3140d-218">To do this, surround the initialization values with braces (`{}`).</span></span>

```vb
Dim longArray() As Long = {0, 1, 2, 3}
```

<span data-ttu-id="3140d-219">Для многомерных массивов инициализация каждого отдельного измерения заключается в фигурные скобки во внешнем измерении.</span><span class="sxs-lookup"><span data-stu-id="3140d-219">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span></span> <span data-ttu-id="3140d-220">Элементы задаются в построчном порядке.</span><span class="sxs-lookup"><span data-stu-id="3140d-220">The elements are specified in row-major order.</span></span>

```vb
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}
```

<span data-ttu-id="3140d-221">Дополнительные сведения о литералах массивов см. в разделе [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="3140d-221">For more information about array literals, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>

## <a name="default"></a><span data-ttu-id="3140d-222">Типы данных и значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="3140d-222">Default Data Types and Values</span></span>

<span data-ttu-id="3140d-223">В следующей таблице перечислены результаты различных сочетаний заданных типов данных и инициализаторов в операторе `Dim`.</span><span class="sxs-lookup"><span data-stu-id="3140d-223">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>

|<span data-ttu-id="3140d-224">Указан тип данных?</span><span class="sxs-lookup"><span data-stu-id="3140d-224">Data type specified?</span></span>|<span data-ttu-id="3140d-225">Указан инициализатор?</span><span class="sxs-lookup"><span data-stu-id="3140d-225">Initializer specified?</span></span>|<span data-ttu-id="3140d-226">Пример</span><span class="sxs-lookup"><span data-stu-id="3140d-226">Example</span></span>|<span data-ttu-id="3140d-227">Результат</span><span class="sxs-lookup"><span data-stu-id="3140d-227">Result</span></span>|
|---|---|---|---|
|<span data-ttu-id="3140d-228">Нет</span><span class="sxs-lookup"><span data-stu-id="3140d-228">No</span></span>|<span data-ttu-id="3140d-229">Нет</span><span class="sxs-lookup"><span data-stu-id="3140d-229">No</span></span>|`Dim qty`|<span data-ttu-id="3140d-230">Если [параметр optioned](../../../visual-basic/language-reference/statements/option-strict-statement.md) имеет значение OFF (значение по умолчанию), то переменной присваивается значение `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="3140d-230">If [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="3140d-231">Если параметр `Option Strict` включен, возникает ошибка времени при компиляции.</span><span class="sxs-lookup"><span data-stu-id="3140d-231">If `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="3140d-232">Нет</span><span class="sxs-lookup"><span data-stu-id="3140d-232">No</span></span>|<span data-ttu-id="3140d-233">Да</span><span class="sxs-lookup"><span data-stu-id="3140d-233">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="3140d-234">Если [параметр Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) имеет значение On (значение по умолчанию), переменная принимает тип данных инициализатора.</span><span class="sxs-lookup"><span data-stu-id="3140d-234">If [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="3140d-235">См. раздел [определение локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="3140d-235">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="3140d-236">Если параметры `Option Infer` и `Option Strict` отключены, переменная получает тип данных `Object`.</span><span class="sxs-lookup"><span data-stu-id="3140d-236">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="3140d-237">Если параметр `Option Infer` отключен, а параметр `Option Strict` включен, возникает ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="3140d-237">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="3140d-238">Да</span><span class="sxs-lookup"><span data-stu-id="3140d-238">Yes</span></span>|<span data-ttu-id="3140d-239">Нет</span><span class="sxs-lookup"><span data-stu-id="3140d-239">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="3140d-240">Переменная инициализируется со значением по умолчанию для типа данных.</span><span class="sxs-lookup"><span data-stu-id="3140d-240">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="3140d-241">См. таблицу далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="3140d-241">See the table later in this section.</span></span>|
|<span data-ttu-id="3140d-242">Да</span><span class="sxs-lookup"><span data-stu-id="3140d-242">Yes</span></span>|<span data-ttu-id="3140d-243">Да</span><span class="sxs-lookup"><span data-stu-id="3140d-243">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="3140d-244">Если тип данных инициализатора нельзя преобразовать в указанный тип данных, возникает ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="3140d-244">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|

<span data-ttu-id="3140d-245">Если указать тип данных, но не указать инициализатор, Visual Basic инициализирует переменную как значение по умолчанию для ее типа данных.</span><span class="sxs-lookup"><span data-stu-id="3140d-245">If you specify a data type but do not specify an initializer, Visual Basic initializes the variable to the default value for its data type.</span></span> <span data-ttu-id="3140d-246">В следующей таблице приведены значения инициализации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3140d-246">The following table shows the default initialization values.</span></span>

|<span data-ttu-id="3140d-247">Тип данных</span><span class="sxs-lookup"><span data-stu-id="3140d-247">Data type</span></span>|<span data-ttu-id="3140d-248">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="3140d-248">Default value</span></span>|
|---|---|
|<span data-ttu-id="3140d-249">Все числовые типы (включая `Byte` и `SByte`)</span><span class="sxs-lookup"><span data-stu-id="3140d-249">All numeric types (including `Byte` and `SByte`)</span></span>|<span data-ttu-id="3140d-250">0</span><span class="sxs-lookup"><span data-stu-id="3140d-250">0</span></span>|
|`Char`|<span data-ttu-id="3140d-251">Двоичный 0</span><span class="sxs-lookup"><span data-stu-id="3140d-251">Binary 0</span></span>|
|<span data-ttu-id="3140d-252">Все ссылочные типы (включая `Object`, `String`и все массивы)</span><span class="sxs-lookup"><span data-stu-id="3140d-252">All reference types (including `Object`, `String`, and all arrays)</span></span>|`Nothing`|
|`Boolean`|`False`|
|`Date`|<span data-ttu-id="3140d-253">12:00 AM 1 января 1 года (01/01/0001 12:00:00 AM)</span><span class="sxs-lookup"><span data-stu-id="3140d-253">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span></span>|

<span data-ttu-id="3140d-254">Каждый элемент структуры инициализируется так, как если бы он был отдельной переменной.</span><span class="sxs-lookup"><span data-stu-id="3140d-254">Each element of a structure is initialized as if it were a separate variable.</span></span> <span data-ttu-id="3140d-255">Если вы объявили длину массива, но не инициализируйте его элементы, каждый элемент инициализируется так, как если бы он был отдельной переменной.</span><span class="sxs-lookup"><span data-stu-id="3140d-255">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span></span>

## <a name="static-local-variable-lifetime"></a><span data-ttu-id="3140d-256">Время существования статической локальной переменной</span><span class="sxs-lookup"><span data-stu-id="3140d-256">Static Local Variable Lifetime</span></span>

<span data-ttu-id="3140d-257">`Static` локальная переменная имеет более длительное время существования, чем процедура, в которой она объявлена.</span><span class="sxs-lookup"><span data-stu-id="3140d-257">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span></span> <span data-ttu-id="3140d-258">Границы времени существования переменной зависят от того, где была объявлена процедура и является ли она `Shared`ой.</span><span class="sxs-lookup"><span data-stu-id="3140d-258">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span></span>

|<span data-ttu-id="3140d-259">Объявление процедуры</span><span class="sxs-lookup"><span data-stu-id="3140d-259">Procedure declaration</span></span>|<span data-ttu-id="3140d-260">Переменная инициализирована</span><span class="sxs-lookup"><span data-stu-id="3140d-260">Variable initialized</span></span>|<span data-ttu-id="3140d-261">Переменная останавливается</span><span class="sxs-lookup"><span data-stu-id="3140d-261">Variable stops existing</span></span>|
|---|---|---|
|<span data-ttu-id="3140d-262">В модуле</span><span class="sxs-lookup"><span data-stu-id="3140d-262">In a module</span></span>|<span data-ttu-id="3140d-263">При первом вызове процедуры</span><span class="sxs-lookup"><span data-stu-id="3140d-263">The first time the procedure is called</span></span>|<span data-ttu-id="3140d-264">При остановке выполнения программы</span><span class="sxs-lookup"><span data-stu-id="3140d-264">When your program stops execution</span></span>|
|<span data-ttu-id="3140d-265">В классе или структуре процедура `Shared`</span><span class="sxs-lookup"><span data-stu-id="3140d-265">In a class or structure, procedure is `Shared`</span></span>|<span data-ttu-id="3140d-266">При первом вызове процедуры либо в определенном экземпляре, либо в самом классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="3140d-266">The first time the procedure is called either on a specific instance or on the class or structure itself</span></span>|<span data-ttu-id="3140d-267">При остановке выполнения программы</span><span class="sxs-lookup"><span data-stu-id="3140d-267">When your program stops execution</span></span>|
|<span data-ttu-id="3140d-268">В классе или структуре процедура не `Shared`</span><span class="sxs-lookup"><span data-stu-id="3140d-268">In a class or structure, procedure isn't `Shared`</span></span>|<span data-ttu-id="3140d-269">При первом вызове процедуры в определенном экземпляре</span><span class="sxs-lookup"><span data-stu-id="3140d-269">The first time the procedure is called on a specific instance</span></span>|<span data-ttu-id="3140d-270">Когда экземпляр выпускается для сборки мусора (GC)</span><span class="sxs-lookup"><span data-stu-id="3140d-270">When the instance is released for garbage collection (GC)</span></span>|

## <a name="attributes-and-modifiers"></a><span data-ttu-id="3140d-271">Атрибуты и модификаторы</span><span class="sxs-lookup"><span data-stu-id="3140d-271">Attributes and Modifiers</span></span>

<span data-ttu-id="3140d-272">Атрибуты можно применять только к переменным члена, а не к локальным переменным.</span><span class="sxs-lookup"><span data-stu-id="3140d-272">You can apply attributes only to member variables, not to local variables.</span></span> <span data-ttu-id="3140d-273">Атрибут вносит сведения в метаданные сборки, что не имеет смысла для временного хранения, например локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="3140d-273">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span></span>

<span data-ttu-id="3140d-274">На уровне модуля нельзя использовать модификатор `Static` для объявления переменных члена.</span><span class="sxs-lookup"><span data-stu-id="3140d-274">At module level, you cannot use the `Static` modifier to declare member variables.</span></span> <span data-ttu-id="3140d-275">На уровне процедуры нельзя использовать `Shared`, `Shadows`, `ReadOnly`, `WithEvents`или модификаторы доступа для объявления локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="3140d-275">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span></span>

<span data-ttu-id="3140d-276">Можно указать, какой код может получить доступ к переменной, указав `accessmodifier`.</span><span class="sxs-lookup"><span data-stu-id="3140d-276">You can specify what code can access a variable by supplying an `accessmodifier`.</span></span> <span data-ttu-id="3140d-277">Переменные-члены класса и модуля (вне любой процедуры) по умолчанию имеют частный доступ, а переменные-члены структуры по умолчанию имеют общий доступ.</span><span class="sxs-lookup"><span data-stu-id="3140d-277">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span></span> <span data-ttu-id="3140d-278">Уровни доступа можно изменить с помощью модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="3140d-278">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="3140d-279">Нельзя использовать модификаторы доступа для локальных переменных (внутри процедуры).</span><span class="sxs-lookup"><span data-stu-id="3140d-279">You cannot use access modifiers on local variables (inside a procedure).</span></span>

<span data-ttu-id="3140d-280">Можно указать `WithEvents` только для переменных-членов, но не для локальных переменных внутри процедуры.</span><span class="sxs-lookup"><span data-stu-id="3140d-280">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span></span> <span data-ttu-id="3140d-281">При указании `WithEvents`тип данных переменной должен быть конкретным типом класса, а не `Object`.</span><span class="sxs-lookup"><span data-stu-id="3140d-281">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span></span> <span data-ttu-id="3140d-282">Нельзя объявить массив с `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="3140d-282">You cannot declare an array with `WithEvents`.</span></span> <span data-ttu-id="3140d-283">Дополнительные сведения о событиях см. в разделе [события](../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="3140d-283">For more information about events, see [Events](../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3140d-284">Код за пределами класса, структуры или модуля должен уточнять имя переменной-члена именем этого класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="3140d-284">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="3140d-285">Код за пределами процедуры или блока не может ссылаться на локальные переменные в этой процедуре или блоке.</span><span class="sxs-lookup"><span data-stu-id="3140d-285">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span></span>

## <a name="releasing-managed-resources"></a><span data-ttu-id="3140d-286">Освобождение управляемых ресурсов</span><span class="sxs-lookup"><span data-stu-id="3140d-286">Releasing Managed Resources</span></span>

<span data-ttu-id="3140d-287">Сборщик мусора .NET Framework уничтожает управляемые ресурсы без дополнительного программирования.</span><span class="sxs-lookup"><span data-stu-id="3140d-287">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span></span> <span data-ttu-id="3140d-288">Однако можно вызвать принудительное удаление управляемого ресурса вместо ожидания сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="3140d-288">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>

<span data-ttu-id="3140d-289">Если класс принадлежит особому ценному и ограниченному ресурсу (например, к подключению к базе данных или файлу), может возникнуть необходимость в ожидании следующей сборки мусора для очистки экземпляра класса, который больше не используется.</span><span class="sxs-lookup"><span data-stu-id="3140d-289">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span></span> <span data-ttu-id="3140d-290">Класс может реализовывать интерфейс <xref:System.IDisposable>, чтобы предоставить способ освобождения ресурсов перед сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="3140d-290">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span></span> <span data-ttu-id="3140d-291">Класс, реализующий этот интерфейс, предоставляет метод `Dispose`, который может быть вызван для немедленного освобождения ценных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="3140d-291">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span></span>

<span data-ttu-id="3140d-292">Инструкция `Using` автоматизирует процесс получения ресурса, выполнения набора инструкций и последующего удаления ресурса.</span><span class="sxs-lookup"><span data-stu-id="3140d-292">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span></span> <span data-ttu-id="3140d-293">Однако ресурс должен реализовывать интерфейс <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="3140d-293">However, the resource must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="3140d-294">Дополнительные сведения см. в разделе [Оператор using](../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3140d-294">For more information, see [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="3140d-295">Пример</span><span class="sxs-lookup"><span data-stu-id="3140d-295">Example</span></span>

<span data-ttu-id="3140d-296">В следующем примере переменные объявляются с помощью оператора `Dim` с различными параметрами.</span><span class="sxs-lookup"><span data-stu-id="3140d-296">The following example declares variables by using the `Dim` statement with various options.</span></span>

[!code-vb[VbVbalrStatements#141](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#141)]

## <a name="example"></a><span data-ttu-id="3140d-297">Пример</span><span class="sxs-lookup"><span data-stu-id="3140d-297">Example</span></span>

<span data-ttu-id="3140d-298">В следующем примере выводятся простые числа от 1 до 30.</span><span class="sxs-lookup"><span data-stu-id="3140d-298">The following example lists the prime numbers between 1 and 30.</span></span> <span data-ttu-id="3140d-299">Область локальных переменных описывается в разделе Комментарии к коду.</span><span class="sxs-lookup"><span data-stu-id="3140d-299">The scope of local variables is described in code comments.</span></span>

[!code-vb[VbVbalrStatements#142](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#142)]

## <a name="example"></a><span data-ttu-id="3140d-300">Пример</span><span class="sxs-lookup"><span data-stu-id="3140d-300">Example</span></span>

<span data-ttu-id="3140d-301">В следующем примере переменная `speedValue` объявляется на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="3140d-301">In the following example, the `speedValue` variable is declared at the class level.</span></span> <span data-ttu-id="3140d-302">Ключевое слово `Private` используется для объявления переменной.</span><span class="sxs-lookup"><span data-stu-id="3140d-302">The `Private` keyword is used to declare the variable.</span></span> <span data-ttu-id="3140d-303">Доступ к переменной может осуществляться любой процедурой в классе `Car`.</span><span class="sxs-lookup"><span data-stu-id="3140d-303">The variable can be accessed by any procedure in the `Car` class.</span></span>

[!code-vb[VbVbalrStatements#144](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#144)]

[!code-vb[VbVbalrStatements#145](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#145)]

## <a name="see-also"></a><span data-ttu-id="3140d-304">См. также</span><span class="sxs-lookup"><span data-stu-id="3140d-304">See also</span></span>

- [<span data-ttu-id="3140d-305">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="3140d-305">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="3140d-306">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="3140d-306">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="3140d-307">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="3140d-307">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="3140d-308">Оператор Option Infer</span><span class="sxs-lookup"><span data-stu-id="3140d-308">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="3140d-309">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="3140d-309">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="3140d-310">Страница "Компиляция" в конструкторе проектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3140d-310">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="3140d-311">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="3140d-311">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="3140d-312">Массивы</span><span class="sxs-lookup"><span data-stu-id="3140d-312">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="3140d-313">Инициализаторы объектов. Именованные и анонимные типы</span><span class="sxs-lookup"><span data-stu-id="3140d-313">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="3140d-314">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="3140d-314">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="3140d-315">Инициализаторы объектов. Именованные и анонимные типы</span><span class="sxs-lookup"><span data-stu-id="3140d-315">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="3140d-316">Практическое руководство. Объявление объекта с помощью инициализатора объектов</span><span class="sxs-lookup"><span data-stu-id="3140d-316">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
- [<span data-ttu-id="3140d-317">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="3140d-317">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
