---
title: Оператор Dim (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: c051572e83b915346d48ec12fb5d97f77b47e4c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="dim-statement-visual-basic"></a><span data-ttu-id="26e43-102">Оператор Dim (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26e43-102">Dim Statement (Visual Basic)</span></span>
<span data-ttu-id="26e43-103">Объявляет и выделяет место для одной или нескольких переменных.</span><span class="sxs-lookup"><span data-stu-id="26e43-103">Declares and allocates storage space for one or more variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26e43-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26e43-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]   
Dim [ WithEvents ] variablelist  
```  
  
## <a name="parts"></a><span data-ttu-id="26e43-105">Части</span><span class="sxs-lookup"><span data-stu-id="26e43-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="26e43-106">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="26e43-106">Optional.</span></span> <span data-ttu-id="26e43-107">В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="26e43-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="26e43-108">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="26e43-108">Optional.</span></span> <span data-ttu-id="26e43-109">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="26e43-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="26e43-110">Public</span><span class="sxs-lookup"><span data-stu-id="26e43-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="26e43-111">Protected</span><span class="sxs-lookup"><span data-stu-id="26e43-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="26e43-112">Friend</span><span class="sxs-lookup"><span data-stu-id="26e43-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="26e43-113">Закрытые</span><span class="sxs-lookup"><span data-stu-id="26e43-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="26e43-114">В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="26e43-114">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `Shared`  
  
     <span data-ttu-id="26e43-115">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="26e43-115">Optional.</span></span> <span data-ttu-id="26e43-116">В разделе [общих](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="26e43-116">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="26e43-117">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="26e43-117">Optional.</span></span> <span data-ttu-id="26e43-118">В разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="26e43-118">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Static`  
  
     <span data-ttu-id="26e43-119">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="26e43-119">Optional.</span></span> <span data-ttu-id="26e43-120">В разделе [статических](../../../visual-basic/language-reference/modifiers/static.md).</span><span class="sxs-lookup"><span data-stu-id="26e43-120">See [Static](../../../visual-basic/language-reference/modifiers/static.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="26e43-121">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="26e43-121">Optional.</span></span> <span data-ttu-id="26e43-122">В разделе [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="26e43-122">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WithEvents`  
  
     <span data-ttu-id="26e43-123">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="26e43-123">Optional.</span></span> <span data-ttu-id="26e43-124">Указывает, что они объектные переменные, которые ссылаются на экземпляры класса, который может порождать события.</span><span class="sxs-lookup"><span data-stu-id="26e43-124">Specifies that these are object variables that refer to instances of a class that can raise events.</span></span> <span data-ttu-id="26e43-125">В разделе [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="26e43-125">See [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span></span>  
  
-   `variablelist`  
  
     <span data-ttu-id="26e43-126">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="26e43-126">Required.</span></span> <span data-ttu-id="26e43-127">Список переменных, объявляемых в этом операторе.</span><span class="sxs-lookup"><span data-stu-id="26e43-127">List of variables being declared in this statement.</span></span>  
  
     `variable [ , variable ... ]`  
  
     <span data-ttu-id="26e43-128">Каждый элемент `variable` имеет перечисленные ниже синтаксис и компоненты.</span><span class="sxs-lookup"><span data-stu-id="26e43-128">Each `variable` has the following syntax and parts:</span></span>  
  
     <span data-ttu-id="26e43-129">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="26e43-129">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="26e43-130">Отделение</span><span class="sxs-lookup"><span data-stu-id="26e43-130">Part</span></span>|<span data-ttu-id="26e43-131">Описание</span><span class="sxs-lookup"><span data-stu-id="26e43-131">Description</span></span>|  
    |---|---|  
    |`variablename`|<span data-ttu-id="26e43-132">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="26e43-132">Required.</span></span> <span data-ttu-id="26e43-133">Имя переменной.</span><span class="sxs-lookup"><span data-stu-id="26e43-133">Name of the variable.</span></span> <span data-ttu-id="26e43-134">В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="26e43-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
    |`boundslist`|<span data-ttu-id="26e43-135">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="26e43-135">Optional.</span></span> <span data-ttu-id="26e43-136">Список границ для каждого измерения массива.</span><span class="sxs-lookup"><span data-stu-id="26e43-136">List of bounds of each dimension of an array variable.</span></span>|  
    |`New`|<span data-ttu-id="26e43-137">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="26e43-137">Optional.</span></span> <span data-ttu-id="26e43-138">Создает новый экземпляр класса при `Dim` выполняется инструкция.</span><span class="sxs-lookup"><span data-stu-id="26e43-138">Creates a new instance of the class when the `Dim` statement runs.</span></span>|  
    |`datatype`|<span data-ttu-id="26e43-139">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="26e43-139">Optional.</span></span> <span data-ttu-id="26e43-140">Тип данных переменной.</span><span class="sxs-lookup"><span data-stu-id="26e43-140">Data type of the variable.</span></span>|  
    |`With`|<span data-ttu-id="26e43-141">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="26e43-141">Optional.</span></span> <span data-ttu-id="26e43-142">Появился в списке инициализаторов объекта.</span><span class="sxs-lookup"><span data-stu-id="26e43-142">Introduces the object initializer list.</span></span>|  
    |`propertyname`|<span data-ttu-id="26e43-143">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="26e43-143">Optional.</span></span> <span data-ttu-id="26e43-144">Имя свойства в классе становится экземпляром.</span><span class="sxs-lookup"><span data-stu-id="26e43-144">The name of a property in the class you are making an instance of.</span></span>|  
    |`propinitializer`|<span data-ttu-id="26e43-145">После `propertyname` =.</span><span class="sxs-lookup"><span data-stu-id="26e43-145">Required after `propertyname` =.</span></span> <span data-ttu-id="26e43-146">Выражение, которое является вычисляется и присваивается имя свойства.</span><span class="sxs-lookup"><span data-stu-id="26e43-146">The expression that is evaluated and assigned to the property name.</span></span>|  
    |`initializer`|<span data-ttu-id="26e43-147">Необязательный, если `New` не указан.</span><span class="sxs-lookup"><span data-stu-id="26e43-147">Optional if `New` is not specified.</span></span> <span data-ttu-id="26e43-148">Выражение, которое вычисляется и присваивается переменной при ее создании.</span><span class="sxs-lookup"><span data-stu-id="26e43-148">Expression that is evaluated and assigned to the variable when it is created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26e43-149">Примечания</span><span class="sxs-lookup"><span data-stu-id="26e43-149">Remarks</span></span>  
 <span data-ttu-id="26e43-150">Компилятор Visual Basic использует `Dim` инструкцию, чтобы определить тип данных переменной и другие сведения, например, какой код может обращаться к переменной.</span><span class="sxs-lookup"><span data-stu-id="26e43-150">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span></span> <span data-ttu-id="26e43-151">В следующем примере объявляется переменная для хранения `Integer` значение.</span><span class="sxs-lookup"><span data-stu-id="26e43-151">The following example declares a variable to hold an `Integer` value.</span></span>  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 <span data-ttu-id="26e43-152">Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="26e43-152">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="26e43-153">Для ссылочного типа, используйте `New` указано ключевое слово для создания нового экземпляра класса или структуры, для типа данных.</span><span class="sxs-lookup"><span data-stu-id="26e43-153">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span></span> <span data-ttu-id="26e43-154">Если вы используете `New`, тип выражения инициализатора не используется.</span><span class="sxs-lookup"><span data-stu-id="26e43-154">If you use `New`, you do not use an initializer expression.</span></span> <span data-ttu-id="26e43-155">Вместо этого аргументы, если они требуются, чтобы конструктор класса, из которого создается переменная.</span><span class="sxs-lookup"><span data-stu-id="26e43-155">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span></span>  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 <span data-ttu-id="26e43-156">Можно объявить переменную в процедуре, блок, класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="26e43-156">You can declare a variable in a procedure, block, class, structure, or module.</span></span> <span data-ttu-id="26e43-157">Невозможно объявить переменную в исходный файл, пространство имен или интерфейс.</span><span class="sxs-lookup"><span data-stu-id="26e43-157">You cannot declare a variable in a source file, namespace, or interface.</span></span> <span data-ttu-id="26e43-158">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="26e43-158">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="26e43-159">Переменная, объявленная на уровне модуля, вне любой процедуры — *переменной-члена* или *поля*.</span><span class="sxs-lookup"><span data-stu-id="26e43-159">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span></span> <span data-ttu-id="26e43-160">Переменные-члены находятся в области всего их класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="26e43-160">Member variables are in scope throughout their class, structure, or module.</span></span> <span data-ttu-id="26e43-161">Переменная, объявленная на уровне процедуры — *локальной переменной*.</span><span class="sxs-lookup"><span data-stu-id="26e43-161">A variable that is declared at procedure level is a *local variable*.</span></span> <span data-ttu-id="26e43-162">Локальные переменные находятся в области действия только в пределах их процедуры или блока.</span><span class="sxs-lookup"><span data-stu-id="26e43-162">Local variables are in scope only within their procedure or block.</span></span>  
  
 <span data-ttu-id="26e43-163">Следующие модификаторы доступа используются для объявления переменных вне процедуры: `Public`, `Protected`, `Friend`, `Protected Friend`, и `Private`.</span><span class="sxs-lookup"><span data-stu-id="26e43-163">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span></span> <span data-ttu-id="26e43-164">Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="26e43-164">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="26e43-165">`Dim` Ключевое слово является необязательным и обычно указывается, если указать один из следующих модификаторов: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, или `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="26e43-165">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span></span>  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 <span data-ttu-id="26e43-166">Если `Option Explicit` является on (по умолчанию), компилятор требует объявления для каждой переменной можно использовать.</span><span class="sxs-lookup"><span data-stu-id="26e43-166">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span></span> <span data-ttu-id="26e43-167">Дополнительные сведения см. в разделе [оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="26e43-167">For more information, see [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span></span>  
  
## <a name="specifying-an-initial-value"></a><span data-ttu-id="26e43-168">Указание начального значения</span><span class="sxs-lookup"><span data-stu-id="26e43-168">Specifying an Initial Value</span></span>  
 <span data-ttu-id="26e43-169">Можно назначить значение переменной при ее создании.</span><span class="sxs-lookup"><span data-stu-id="26e43-169">You can assign a value to a variable when it is created.</span></span> <span data-ttu-id="26e43-170">Для типа значения используйте *инициализатора* позволяет указать выражение, назначаемое переменной.</span><span class="sxs-lookup"><span data-stu-id="26e43-170">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span></span> <span data-ttu-id="26e43-171">Выражение должно возвращать константой, может быть вычислено во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="26e43-171">The expression must evaluate to a constant that can be calculated at compile time.</span></span>  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 <span data-ttu-id="26e43-172">Если указан инициализатор и тип данных не указан в `As` предложение, *вывод типа* используется для определения типа данных из инициализатора.</span><span class="sxs-lookup"><span data-stu-id="26e43-172">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span></span> <span data-ttu-id="26e43-173">В следующем примере оба `num1` и `num2` являются строго типизированными как целые числа.</span><span class="sxs-lookup"><span data-stu-id="26e43-173">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span> <span data-ttu-id="26e43-174">Во втором объявлении определения типов определяет тип значение 3.</span><span class="sxs-lookup"><span data-stu-id="26e43-174">In the second declaration, type inference infers the type from the value 3.</span></span>  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 <span data-ttu-id="26e43-175">Определение типов применяется на уровне процедуры.</span><span class="sxs-lookup"><span data-stu-id="26e43-175">Type inference applies at the procedure level.</span></span> <span data-ttu-id="26e43-176">Не применяется вне процедур в класс, структура, модуль или интерфейс.</span><span class="sxs-lookup"><span data-stu-id="26e43-176">It does not apply outside a procedure in a class, structure, module, or interface.</span></span> <span data-ttu-id="26e43-177">Дополнительные сведения о выводе типа см. в разделе [Option Infer-оператор](../../../visual-basic/language-reference/statements/option-infer-statement.md) и [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="26e43-177">For more information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="26e43-178">Сведения о том, что происходит, когда не указан тип данных или инициализатор в разделе [по умолчанию типы данных и значения](../../../visual-basic/language-reference/statements/dim-statement.md#default) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="26e43-178">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](../../../visual-basic/language-reference/statements/dim-statement.md#default) later in this topic.</span></span>  
  
 <span data-ttu-id="26e43-179">Можно использовать *инициализатора объекта* объявлять экземпляров именованные и анонимные типы.</span><span class="sxs-lookup"><span data-stu-id="26e43-179">You can use an *object initializer* to declare instances of named and anonymous types.</span></span> <span data-ttu-id="26e43-180">Следующий код создает экземпляр `Student` класса и использует инициализатора объекта для инициализации свойств.</span><span class="sxs-lookup"><span data-stu-id="26e43-180">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span></span>  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 <span data-ttu-id="26e43-181">Дополнительные сведения об инициализаторах объектов см. в разделе [как: объявление объекта с помощью инициализатора объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [инициализаторы объектов: именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), и [анонимные типы ](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="26e43-181">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="declaring-multiple-variables"></a><span data-ttu-id="26e43-182">Объявление нескольких переменных</span><span class="sxs-lookup"><span data-stu-id="26e43-182">Declaring Multiple Variables</span></span>  
 <span data-ttu-id="26e43-183">Можно объявить несколько переменных в одном операторе объявления, указав имя переменной для каждого из них и имя массива в скобки.</span><span class="sxs-lookup"><span data-stu-id="26e43-183">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span></span> <span data-ttu-id="26e43-184">Переменные разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="26e43-184">Multiple variables are separated by commas.</span></span>  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 <span data-ttu-id="26e43-185">Если объявляется несколько переменных с одним `As` предложение, невозможно указать инициализатор для этой группы переменных.</span><span class="sxs-lookup"><span data-stu-id="26e43-185">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span></span>  
  
 <span data-ttu-id="26e43-186">Можно указать различные типы данных для переменных с помощью отдельных `As` предложение для каждой объявляемой переменной.</span><span class="sxs-lookup"><span data-stu-id="26e43-186">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="26e43-187">Каждая переменная имеет тип данных, указанный в первом `As` предложение возникли после его `variablename` части.</span><span class="sxs-lookup"><span data-stu-id="26e43-187">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span></span>  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a><span data-ttu-id="26e43-188">Массивы</span><span class="sxs-lookup"><span data-stu-id="26e43-188">Arrays</span></span>  
 <span data-ttu-id="26e43-189">Можно объявить переменную для хранения *массив*, который может содержать несколько значений.</span><span class="sxs-lookup"><span data-stu-id="26e43-189">You can declare a variable to hold an *array*, which can hold multiple values.</span></span> <span data-ttu-id="26e43-190">Чтобы указать, что переменная содержит массив, выполните его `variablename` немедленно со скобками.</span><span class="sxs-lookup"><span data-stu-id="26e43-190">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span></span> <span data-ttu-id="26e43-191">Дополнительные сведения о массивах см. в разделе [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="26e43-191">For more information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="26e43-192">Можно указать нижнюю и верхнюю границу для каждого измерения массива.</span><span class="sxs-lookup"><span data-stu-id="26e43-192">You can specify the lower and upper bound of each dimension of an array.</span></span> <span data-ttu-id="26e43-193">Чтобы сделать это, включите `boundslist` в скобках.</span><span class="sxs-lookup"><span data-stu-id="26e43-193">To do this, include a `boundslist` inside the parentheses.</span></span> <span data-ttu-id="26e43-194">Для каждого измерения `boundslist` указывает верхнюю границу и при необходимости нижнюю границу.</span><span class="sxs-lookup"><span data-stu-id="26e43-194">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span></span> <span data-ttu-id="26e43-195">Нижняя граница всегда равно нулю, задания или нет.</span><span class="sxs-lookup"><span data-stu-id="26e43-195">The lower bound is always zero, whether you specify it or not.</span></span> <span data-ttu-id="26e43-196">Каждый индекс может изменяться от нуля до значения верхней границы.</span><span class="sxs-lookup"><span data-stu-id="26e43-196">Each index can vary from zero through its upper bound value.</span></span>  
  
 <span data-ttu-id="26e43-197">Следующие две инструкции эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="26e43-197">The following two statements are equivalent.</span></span> <span data-ttu-id="26e43-198">Каждый оператор объявляет массив из 21 `Integer` элементов.</span><span class="sxs-lookup"><span data-stu-id="26e43-198">Each statement declares an array of 21 `Integer` elements.</span></span> <span data-ttu-id="26e43-199">При доступе к массива, индекс может изменяться от 0 до 20.</span><span class="sxs-lookup"><span data-stu-id="26e43-199">When you access the array, the index can vary from 0 through 20.</span></span>  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 <span data-ttu-id="26e43-200">Следующий оператор объявляет двумерный массив типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="26e43-200">The following statement declares a two-dimensional array of type `Double`.</span></span> <span data-ttu-id="26e43-201">Массив имеет 4 строки (3 + 1) по 6 столбцов (5 + 1) каждая.</span><span class="sxs-lookup"><span data-stu-id="26e43-201">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span></span> <span data-ttu-id="26e43-202">Обратите внимание, что верхняя граница представляет наибольшее возможное значение для индекса, но не длину измерения.</span><span class="sxs-lookup"><span data-stu-id="26e43-202">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span></span> <span data-ttu-id="26e43-203">Длина измерения равна верхней границе плюс один.</span><span class="sxs-lookup"><span data-stu-id="26e43-203">The length of the dimension is the upper bound plus one.</span></span>  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 <span data-ttu-id="26e43-204">Массив может быть в диапазоне от 1 до 32 измерений.</span><span class="sxs-lookup"><span data-stu-id="26e43-204">An array can have from 1 to 32 dimensions.</span></span>  
  
 <span data-ttu-id="26e43-205">Все границы можно оставить пустым в объявлении массива.</span><span class="sxs-lookup"><span data-stu-id="26e43-205">You can leave all the bounds blank in an array declaration.</span></span> <span data-ttu-id="26e43-206">После этого массив имеет размерность, указываемые, но он не инициализирован.</span><span class="sxs-lookup"><span data-stu-id="26e43-206">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span></span> <span data-ttu-id="26e43-207">Он имеет значение `Nothing` до инициализации по крайней мере некоторые из его элементов.</span><span class="sxs-lookup"><span data-stu-id="26e43-207">It has a value of `Nothing` until you initialize at least some of its elements.</span></span> <span data-ttu-id="26e43-208">`Dim` Инструкции должны быть указаны границы для всех измерений либо измерения не.</span><span class="sxs-lookup"><span data-stu-id="26e43-208">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span></span>  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 <span data-ttu-id="26e43-209">Если массив имеет более одного измерения, необходимо включить запятые заключено в круглые скобки, чтобы указать число измерений.</span><span class="sxs-lookup"><span data-stu-id="26e43-209">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span></span>  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 <span data-ttu-id="26e43-210">Можно объявить *массив нулевой длины* , объявив одно из измерений массива равным – 1.</span><span class="sxs-lookup"><span data-stu-id="26e43-210">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span></span> <span data-ttu-id="26e43-211">Переменная, содержащая массив нулевой длины не имеет значения `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="26e43-211">A variable that holds a zero-length array does not have the value `Nothing`.</span></span> <span data-ttu-id="26e43-212">Массивы с нулевой длиной необходимы определенные функции среды CLR.</span><span class="sxs-lookup"><span data-stu-id="26e43-212">Zero-length arrays are required by certain common language runtime functions.</span></span> <span data-ttu-id="26e43-213">При попытке получить доступ к такой массив, возникает исключение времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="26e43-213">If you try to access such an array, a runtime exception occurs.</span></span> <span data-ttu-id="26e43-214">Дополнительные сведения см. в разделе [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="26e43-214">For more information, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="26e43-215">Значения массива можно инициализировать с помощью литерала массива.</span><span class="sxs-lookup"><span data-stu-id="26e43-215">You can initialize the values of an array by using an array literal.</span></span> <span data-ttu-id="26e43-216">Чтобы сделать это, заключите начальных значений в фигурные скобки (`{}`).</span><span class="sxs-lookup"><span data-stu-id="26e43-216">To do this, surround the initialization values with braces (`{}`).</span></span>  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 <span data-ttu-id="26e43-217">Для многомерных массивов инициализация для каждой отдельной размерности заключается в фигурные скобки внешней размерности.</span><span class="sxs-lookup"><span data-stu-id="26e43-217">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span></span> <span data-ttu-id="26e43-218">Имена указываются в строках заказа.</span><span class="sxs-lookup"><span data-stu-id="26e43-218">The elements are specified in row-major order.</span></span>  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 <span data-ttu-id="26e43-219">Дополнительные сведения о литералах массива см. в разделе [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="26e43-219">For more information about array literals, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
##  <a name="default"></a> <span data-ttu-id="26e43-220">Типы данных по умолчанию и значения</span><span class="sxs-lookup"><span data-stu-id="26e43-220">Default Data Types and Values</span></span>  
 <span data-ttu-id="26e43-221">В следующей таблице перечислены результаты различных сочетаний заданных типов данных и инициализаторов в операторе `Dim`.</span><span class="sxs-lookup"><span data-stu-id="26e43-221">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="26e43-222">Указан тип данных?</span><span class="sxs-lookup"><span data-stu-id="26e43-222">Data type specified?</span></span>|<span data-ttu-id="26e43-223">Указан инициализатор?</span><span class="sxs-lookup"><span data-stu-id="26e43-223">Initializer specified?</span></span>|<span data-ttu-id="26e43-224">Пример</span><span class="sxs-lookup"><span data-stu-id="26e43-224">Example</span></span>|<span data-ttu-id="26e43-225">Результат</span><span class="sxs-lookup"><span data-stu-id="26e43-225">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="26e43-226">Нет</span><span class="sxs-lookup"><span data-stu-id="26e43-226">No</span></span>|<span data-ttu-id="26e43-227">Нет</span><span class="sxs-lookup"><span data-stu-id="26e43-227">No</span></span>|`Dim qty`|<span data-ttu-id="26e43-228">Если [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) — off (по умолчанию), переменная принимает значение `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="26e43-228">If [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="26e43-229">Если параметр `Option Strict` включен, при компиляции возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="26e43-229">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="26e43-230">Нет</span><span class="sxs-lookup"><span data-stu-id="26e43-230">No</span></span>|<span data-ttu-id="26e43-231">Да</span><span class="sxs-lookup"><span data-stu-id="26e43-231">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="26e43-232">Если [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) включен (по умолчанию), переменная получает тип данных инициализатора.</span><span class="sxs-lookup"><span data-stu-id="26e43-232">If [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="26e43-233">В разделе [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="26e43-233">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="26e43-234">Если параметры `Option Infer` и `Option Strict` отключены, переменная получает тип данных `Object`.</span><span class="sxs-lookup"><span data-stu-id="26e43-234">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="26e43-235">Если параметр `Option Infer` отключен, а параметр `Option Strict` включен, при компиляции возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="26e43-235">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="26e43-236">Да</span><span class="sxs-lookup"><span data-stu-id="26e43-236">Yes</span></span>|<span data-ttu-id="26e43-237">Нет</span><span class="sxs-lookup"><span data-stu-id="26e43-237">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="26e43-238">Переменная инициализируется со значением по умолчанию для типа данных.</span><span class="sxs-lookup"><span data-stu-id="26e43-238">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="26e43-239">См. в таблице ниже в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="26e43-239">See the table later in this section.</span></span>|  
|<span data-ttu-id="26e43-240">Да</span><span class="sxs-lookup"><span data-stu-id="26e43-240">Yes</span></span>|<span data-ttu-id="26e43-241">Да</span><span class="sxs-lookup"><span data-stu-id="26e43-241">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="26e43-242">Если тип данных инициализатора нельзя преобразовать в указанный тип данных, возникает ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="26e43-242">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
 <span data-ttu-id="26e43-243">Если указать тип данных, но не указан инициализатор, Visual Basic инициализирует переменную со значением по умолчанию для своего типа данных.</span><span class="sxs-lookup"><span data-stu-id="26e43-243">If you specify a data type but do not specify an initializer, Visual Basic initializes the variable to the default value for its data type.</span></span> <span data-ttu-id="26e43-244">В следующей таблице представлены значения инициализации.</span><span class="sxs-lookup"><span data-stu-id="26e43-244">The following table shows the default initialization values.</span></span>  
  
|<span data-ttu-id="26e43-245">Тип данных</span><span class="sxs-lookup"><span data-stu-id="26e43-245">Data type</span></span>|<span data-ttu-id="26e43-246">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="26e43-246">Default value</span></span>|  
|---|---|  
|<span data-ttu-id="26e43-247">Все числовые типы (включая `Byte` и `SByte`)</span><span class="sxs-lookup"><span data-stu-id="26e43-247">All numeric types (including `Byte` and `SByte`)</span></span>|<span data-ttu-id="26e43-248">0</span><span class="sxs-lookup"><span data-stu-id="26e43-248">0</span></span>|  
|`Char`|<span data-ttu-id="26e43-249">Двоичный 0</span><span class="sxs-lookup"><span data-stu-id="26e43-249">Binary 0</span></span>|  
|<span data-ttu-id="26e43-250">Все ссылочные типы (включая `Object`, `String`и все массивы)</span><span class="sxs-lookup"><span data-stu-id="26e43-250">All reference types (including `Object`, `String`, and all arrays)</span></span>|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|<span data-ttu-id="26e43-251">Полночь 1 января 1 года (01/01/0001 12:00:00 AM)</span><span class="sxs-lookup"><span data-stu-id="26e43-251">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span></span>|  
  
 <span data-ttu-id="26e43-252">Каждый элемент структуры инициализируется, как если бы он был отдельной переменной.</span><span class="sxs-lookup"><span data-stu-id="26e43-252">Each element of a structure is initialized as if it were a separate variable.</span></span> <span data-ttu-id="26e43-253">Если объявляется длина массива, но не инициализируются его элементы, каждый элемент инициализируется, как если бы он был отдельной переменной.</span><span class="sxs-lookup"><span data-stu-id="26e43-253">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span></span>  
  
## <a name="static-local-variable-lifetime"></a><span data-ttu-id="26e43-254">Время существования статической локальной переменной</span><span class="sxs-lookup"><span data-stu-id="26e43-254">Static Local Variable Lifetime</span></span>  
 <span data-ttu-id="26e43-255">Объект `Static` локальная переменная имеет дольше процедуры, в котором она объявлена.</span><span class="sxs-lookup"><span data-stu-id="26e43-255">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span></span> <span data-ttu-id="26e43-256">Пределы существования переменной зависят от того, где объявлен процедуры и является ли оно `Shared`.</span><span class="sxs-lookup"><span data-stu-id="26e43-256">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span></span>  
  
|<span data-ttu-id="26e43-257">Объявление процедуры</span><span class="sxs-lookup"><span data-stu-id="26e43-257">Procedure declaration</span></span>|<span data-ttu-id="26e43-258">Переменная инициализирована</span><span class="sxs-lookup"><span data-stu-id="26e43-258">Variable initialized</span></span>|<span data-ttu-id="26e43-259">Переменная прекращает существующие</span><span class="sxs-lookup"><span data-stu-id="26e43-259">Variable stops existing</span></span>|  
|---|---|---|  
|<span data-ttu-id="26e43-260">В модуле</span><span class="sxs-lookup"><span data-stu-id="26e43-260">In a module</span></span>|<span data-ttu-id="26e43-261">Первый раз при вызове процедуры</span><span class="sxs-lookup"><span data-stu-id="26e43-261">The first time the procedure is called</span></span>|<span data-ttu-id="26e43-262">Когда программа завершает выполнение</span><span class="sxs-lookup"><span data-stu-id="26e43-262">When your program stops execution</span></span>|  
|<span data-ttu-id="26e43-263">В классе или структуре процедура является `Shared`</span><span class="sxs-lookup"><span data-stu-id="26e43-263">In a class or structure, procedure is `Shared`</span></span>|<span data-ttu-id="26e43-264">Первый раз процедура вызывается на определенном экземпляре или на классе или структуре самой</span><span class="sxs-lookup"><span data-stu-id="26e43-264">The first time the procedure is called either on a specific instance or on the class or structure itself</span></span>|<span data-ttu-id="26e43-265">Когда программа завершает выполнение</span><span class="sxs-lookup"><span data-stu-id="26e43-265">When your program stops execution</span></span>|  
|<span data-ttu-id="26e43-266">В классе или структуре не процедуры `Shared`</span><span class="sxs-lookup"><span data-stu-id="26e43-266">In a class or structure, procedure isn't `Shared`</span></span>|<span data-ttu-id="26e43-267">При первом запуске при вызове процедуры на определенном экземпляре</span><span class="sxs-lookup"><span data-stu-id="26e43-267">The first time the procedure is called on a specific instance</span></span>|<span data-ttu-id="26e43-268">Если этот экземпляр освобождается для сборки мусора (GC)</span><span class="sxs-lookup"><span data-stu-id="26e43-268">When the instance is released for garbage collection (GC)</span></span>|  
  
## <a name="attributes-and-modifiers"></a><span data-ttu-id="26e43-269">Атрибуты и модификаторы</span><span class="sxs-lookup"><span data-stu-id="26e43-269">Attributes and Modifiers</span></span>  
 <span data-ttu-id="26e43-270">Можно применить атрибуты только для переменных-членов, а не к локальным переменным.</span><span class="sxs-lookup"><span data-stu-id="26e43-270">You can apply attributes only to member variables, not to local variables.</span></span> <span data-ttu-id="26e43-271">Атрибут вносит сведения для метаданных сборки, которые не имеют смысла для временного хранения, такие как локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="26e43-271">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span></span>  
  
 <span data-ttu-id="26e43-272">На уровне модуля нельзя использовать `Static` модификатор для объявления переменных-членов.</span><span class="sxs-lookup"><span data-stu-id="26e43-272">At module level, you cannot use the `Static` modifier to declare member variables.</span></span> <span data-ttu-id="26e43-273">На уровне процедуры, нельзя использовать `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, или любой доступ модификаторы объявления локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="26e43-273">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span></span>  
  
 <span data-ttu-id="26e43-274">Можно указать, какой код может обращаться к переменной, указав `accessmodifier`.</span><span class="sxs-lookup"><span data-stu-id="26e43-274">You can specify what code can access a variable by supplying an `accessmodifier`.</span></span> <span data-ttu-id="26e43-275">Класс модуля члены и переменные (вне любых процедур) по умолчанию имеют закрытый доступ, а переменные-члены структуры по умолчанию общий доступ.</span><span class="sxs-lookup"><span data-stu-id="26e43-275">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span></span> <span data-ttu-id="26e43-276">Вы можете настроить уровни доступа с помощью модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="26e43-276">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="26e43-277">Невозможно использовать модификаторы доступа для локальных переменных (внутри процедуры).</span><span class="sxs-lookup"><span data-stu-id="26e43-277">You cannot use access modifiers on local variables (inside a procedure).</span></span>  
  
 <span data-ttu-id="26e43-278">Можно указать `WithEvents` только для переменных-членов, но не для локальных переменных в процедуре.</span><span class="sxs-lookup"><span data-stu-id="26e43-278">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span></span> <span data-ttu-id="26e43-279">При указании `WithEvents`, тип данных переменной должен быть определенный тип класса, не `Object`.</span><span class="sxs-lookup"><span data-stu-id="26e43-279">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span></span> <span data-ttu-id="26e43-280">Не удается объявить массив с `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="26e43-280">You cannot declare an array with `WithEvents`.</span></span> <span data-ttu-id="26e43-281">Дополнительные сведения о событиях см. в разделе [события](../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="26e43-281">For more information about events, see [Events](../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26e43-282">Код вне класса, структуры или модуля необходимо определять имя переменной-члена с именем этого класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="26e43-282">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="26e43-283">Код за пределами процедуры или блока не может ссылаться на любые локальные переменные в рамках этой процедуры или блока.</span><span class="sxs-lookup"><span data-stu-id="26e43-283">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span></span>  
  
## <a name="releasing-managed-resources"></a><span data-ttu-id="26e43-284">Освободить управляемые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="26e43-284">Releasing Managed Resources</span></span>  
 <span data-ttu-id="26e43-285">Сборщик мусора .NET Framework без дополнительного кодирования с вашей стороны освобождает управляемые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="26e43-285">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span></span> <span data-ttu-id="26e43-286">Тем не менее можно принудительно при реализации управляемых ресурсов, а не ждет, пока сборщик мусора.</span><span class="sxs-lookup"><span data-stu-id="26e43-286">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="26e43-287">Если класс удерживает особо ценный и редкий ресурс (например, дескриптор соединения или файла базы данных), может не потребоваться дождаться следующей сборки мусора для очистки экземпляра класса, который больше не используется.</span><span class="sxs-lookup"><span data-stu-id="26e43-287">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span></span> <span data-ttu-id="26e43-288">Класс может реализовывать <xref:System.IDisposable> интерфейс предоставляет способ освободить ресурсы перед сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="26e43-288">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span></span> <span data-ttu-id="26e43-289">Класс, реализующий этот интерфейс предоставляет `Dispose` метод, который можно вызвать, чтобы принудительно ценных ресурсов освобождается сразу.</span><span class="sxs-lookup"><span data-stu-id="26e43-289">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span></span>  
  
 <span data-ttu-id="26e43-290">`Using` Инструкция автоматизирует процесс получения ресурса, выполнение набора операторов и последующего освобождения ресурса.</span><span class="sxs-lookup"><span data-stu-id="26e43-290">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span></span> <span data-ttu-id="26e43-291">Тем не менее, необходимо реализовать ресурса <xref:System.IDisposable> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="26e43-291">However, the resource must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="26e43-292">Дополнительные сведения см. в разделе [Оператор using](../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="26e43-292">For more information, see [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="26e43-293">Пример</span><span class="sxs-lookup"><span data-stu-id="26e43-293">Example</span></span>  
 <span data-ttu-id="26e43-294">В следующем примере объявляется переменных с помощью `Dim` инструкции с различными параметрами.</span><span class="sxs-lookup"><span data-stu-id="26e43-294">The following example declares variables by using the `Dim` statement with various options.</span></span>  
  
 [!code-vb[VbVbalrStatements#141](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="26e43-295">Пример</span><span class="sxs-lookup"><span data-stu-id="26e43-295">Example</span></span>  
 <span data-ttu-id="26e43-296">Приведенный ниже список простых чисел от 1 до 30.</span><span class="sxs-lookup"><span data-stu-id="26e43-296">The following example lists the prime numbers between 1 and 30.</span></span> <span data-ttu-id="26e43-297">Область локальных переменных, описывается в комментариях к коду.</span><span class="sxs-lookup"><span data-stu-id="26e43-297">The scope of local variables is described in code comments.</span></span>  
  
 [!code-vb[VbVbalrStatements#142](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="26e43-298">Пример</span><span class="sxs-lookup"><span data-stu-id="26e43-298">Example</span></span>  
 <span data-ttu-id="26e43-299">В следующем примере `speedValue` переменная, объявленная на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="26e43-299">In the following example, the `speedValue` variable is declared at the class level.</span></span> <span data-ttu-id="26e43-300">`Private` Ключевое слово используется для объявления переменной.</span><span class="sxs-lookup"><span data-stu-id="26e43-300">The `Private` keyword is used to declare the variable.</span></span> <span data-ttu-id="26e43-301">Переменная может осуществляться в любую процедуру `Car` класса.</span><span class="sxs-lookup"><span data-stu-id="26e43-301">The variable can be accessed by any procedure in the `Car` class.</span></span>  
  
 [!code-vb[VbVbalrStatements#144](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#145](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="26e43-302">См. также</span><span class="sxs-lookup"><span data-stu-id="26e43-302">See Also</span></span>  
 [<span data-ttu-id="26e43-303">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="26e43-303">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="26e43-304">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="26e43-304">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="26e43-305">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="26e43-305">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="26e43-306">Оператор Option Infer</span><span class="sxs-lookup"><span data-stu-id="26e43-306">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [<span data-ttu-id="26e43-307">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="26e43-307">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="26e43-308">Страница "Компиляция" в конструкторе проектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26e43-308">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [<span data-ttu-id="26e43-309">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="26e43-309">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="26e43-310">Массивы</span><span class="sxs-lookup"><span data-stu-id="26e43-310">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="26e43-311">Инициализаторы объектов. Именованные и анонимные типы</span><span class="sxs-lookup"><span data-stu-id="26e43-311">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="26e43-312">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="26e43-312">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="26e43-313">Инициализаторы объектов. Именованные и анонимные типы</span><span class="sxs-lookup"><span data-stu-id="26e43-313">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="26e43-314">Практическое руководство. Объявление объекта с помощью инициализатора объектов</span><span class="sxs-lookup"><span data-stu-id="26e43-314">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)  
 [<span data-ttu-id="26e43-315">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="26e43-315">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
