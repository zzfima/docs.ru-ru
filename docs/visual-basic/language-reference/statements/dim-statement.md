---
title: "Оператор Dim (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Dim
- Dim
dev_langs:
- VB
helpviewer_keywords:
- Public keyword, in Dim statement
- Dim statement
- fixed-length strings, declaring
- variables [Visual Basic], declaring
- WithEvents keyword, Dim statement
- dynamic arrays, Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields, as member variables
- declarations, dynamic arrays
- member variables
- default values
- data types [Visual Basic], assigning
- braces {}
- As keyword, in Dim statement
- arrays [Visual Basic], declaring
- New keyword, Dim statement
- To keyword, in Dim statement
- storage, allocating
- local variables
- declaration statements
- Dim statement, syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
caps.latest.revision: 72
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
ms.sourcegitcommit: dc1c456c71efb3cc6e60a8fdc77384e65975f110
ms.openlocfilehash: 049ab1e82bac6c9f94bc411cd3e7c859e334d739
ms.contentlocale: ru-ru
ms.lasthandoff: 05/15/2017

---
# <a name="dim-statement-visual-basic"></a><span data-ttu-id="244f3-102">Оператор Dim (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="244f3-102">Dim Statement (Visual Basic)</span></span>
<span data-ttu-id="244f3-103">Объявляет и выделяет место для одной или нескольких переменных.</span><span class="sxs-lookup"><span data-stu-id="244f3-103">Declares and allocates storage space for one or more variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="244f3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="244f3-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]   
Dim [ WithEvents ] variablelist  
```  
  
## <a name="parts"></a><span data-ttu-id="244f3-105">Части</span><span class="sxs-lookup"><span data-stu-id="244f3-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="244f3-106">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="244f3-106">Optional.</span></span> <span data-ttu-id="244f3-107">В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="244f3-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="244f3-108">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="244f3-108">Optional.</span></span> <span data-ttu-id="244f3-109">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="244f3-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="244f3-110">Public</span><span class="sxs-lookup"><span data-stu-id="244f3-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="244f3-111">Protected</span><span class="sxs-lookup"><span data-stu-id="244f3-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="244f3-112">Friend</span><span class="sxs-lookup"><span data-stu-id="244f3-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="244f3-113">Закрытые</span><span class="sxs-lookup"><span data-stu-id="244f3-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="244f3-114">В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="244f3-114">See [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `Shared`  
  
     <span data-ttu-id="244f3-115">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="244f3-115">Optional.</span></span> <span data-ttu-id="244f3-116">В разделе [общего](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="244f3-116">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="244f3-117">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="244f3-117">Optional.</span></span> <span data-ttu-id="244f3-118">В разделе [тени](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="244f3-118">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Static`  
  
     <span data-ttu-id="244f3-119">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="244f3-119">Optional.</span></span> <span data-ttu-id="244f3-120">В разделе [статических](../../../visual-basic/language-reference/modifiers/static.md).</span><span class="sxs-lookup"><span data-stu-id="244f3-120">See [Static](../../../visual-basic/language-reference/modifiers/static.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="244f3-121">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="244f3-121">Optional.</span></span> <span data-ttu-id="244f3-122">В разделе [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="244f3-122">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WithEvents`  
  
     <span data-ttu-id="244f3-123">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="244f3-123">Optional.</span></span> <span data-ttu-id="244f3-124">Указывает, что эти объектные переменные, которые ссылаются на экземпляры класса, который может порождать события.</span><span class="sxs-lookup"><span data-stu-id="244f3-124">Specifies that these are object variables that refer to instances of a class that can raise events.</span></span> <span data-ttu-id="244f3-125">В разделе [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="244f3-125">See [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span></span>  
  
-   `variablelist`  
  
     <span data-ttu-id="244f3-126">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="244f3-126">Required.</span></span> <span data-ttu-id="244f3-127">Список переменных, объявляемых в этом операторе.</span><span class="sxs-lookup"><span data-stu-id="244f3-127">List of variables being declared in this statement.</span></span>  
  
     `variable [ , variable ... ]`  
  
     <span data-ttu-id="244f3-128">Каждый элемент `variable` имеет перечисленные ниже синтаксис и компоненты.</span><span class="sxs-lookup"><span data-stu-id="244f3-128">Each `variable` has the following syntax and parts:</span></span>  
  
     <span data-ttu-id="244f3-129">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="244f3-129">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="244f3-130">Отделение</span><span class="sxs-lookup"><span data-stu-id="244f3-130">Part</span></span>|<span data-ttu-id="244f3-131">Описание</span><span class="sxs-lookup"><span data-stu-id="244f3-131">Description</span></span>|  
    |---|---|  
    |`variablename`|<span data-ttu-id="244f3-132">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="244f3-132">Required.</span></span> <span data-ttu-id="244f3-133">Имя переменной.</span><span class="sxs-lookup"><span data-stu-id="244f3-133">Name of the variable.</span></span> <span data-ttu-id="244f3-134">В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="244f3-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
    |`boundslist`|<span data-ttu-id="244f3-135">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="244f3-135">Optional.</span></span> <span data-ttu-id="244f3-136">Список границ каждого измерения массива.</span><span class="sxs-lookup"><span data-stu-id="244f3-136">List of bounds of each dimension of an array variable.</span></span>|  
    |`New`|<span data-ttu-id="244f3-137">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="244f3-137">Optional.</span></span> <span data-ttu-id="244f3-138">Создает новый экземпляр класса при `Dim` выполняется инструкция.</span><span class="sxs-lookup"><span data-stu-id="244f3-138">Creates a new instance of the class when the `Dim` statement runs.</span></span>|  
    |`datatype`|<span data-ttu-id="244f3-139">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="244f3-139">Optional.</span></span> <span data-ttu-id="244f3-140">Тип данных переменной.</span><span class="sxs-lookup"><span data-stu-id="244f3-140">Data type of the variable.</span></span>|  
    |`With`|<span data-ttu-id="244f3-141">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="244f3-141">Optional.</span></span> <span data-ttu-id="244f3-142">Введение в список инициализаторов объекта.</span><span class="sxs-lookup"><span data-stu-id="244f3-142">Introduces the object initializer list.</span></span>|  
    |`propertyname`|<span data-ttu-id="244f3-143">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="244f3-143">Optional.</span></span> <span data-ttu-id="244f3-144">Имя свойства в классе при создании экземпляра.</span><span class="sxs-lookup"><span data-stu-id="244f3-144">The name of a property in the class you are making an instance of.</span></span>|  
    |`propinitializer`|<span data-ttu-id="244f3-145">После `propertyname` =.</span><span class="sxs-lookup"><span data-stu-id="244f3-145">Required after `propertyname` =.</span></span> <span data-ttu-id="244f3-146">Выражение, которое является вычисляется и присваивается имя свойства.</span><span class="sxs-lookup"><span data-stu-id="244f3-146">The expression that is evaluated and assigned to the property name.</span></span>|  
    |`initializer`|<span data-ttu-id="244f3-147">Необязателен при `New` не указан.</span><span class="sxs-lookup"><span data-stu-id="244f3-147">Optional if `New` is not specified.</span></span> <span data-ttu-id="244f3-148">Выражение, которое вычисляется и присваивается переменной при ее создании.</span><span class="sxs-lookup"><span data-stu-id="244f3-148">Expression that is evaluated and assigned to the variable when it is created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="244f3-149">Примечания</span><span class="sxs-lookup"><span data-stu-id="244f3-149">Remarks</span></span>  
 <span data-ttu-id="244f3-150">Компилятор Visual Basic использует `Dim` инструкцию, чтобы определить тип данных переменной и другие сведения, например, какой код может получить доступ к переменной.</span><span class="sxs-lookup"><span data-stu-id="244f3-150">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span></span> <span data-ttu-id="244f3-151">В следующем примере объявляется переменная для хранения `Integer` значение.</span><span class="sxs-lookup"><span data-stu-id="244f3-151">The following example declares a variable to hold an `Integer` value.</span></span>  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 <span data-ttu-id="244f3-152">Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="244f3-152">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="244f3-153">Для ссылочного типа, используйте `New` указано ключевое слово для создания экземпляра класса или структуры, типом данных.</span><span class="sxs-lookup"><span data-stu-id="244f3-153">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span></span> <span data-ttu-id="244f3-154">При использовании `New`, не используйте тип выражения инициализатора.</span><span class="sxs-lookup"><span data-stu-id="244f3-154">If you use `New`, you do not use an initializer expression.</span></span> <span data-ttu-id="244f3-155">Вместо этого аргументы, если они требуются, чтобы конструктор класса, из которого создается переменная.</span><span class="sxs-lookup"><span data-stu-id="244f3-155">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span></span>  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 <span data-ttu-id="244f3-156">Можно объявить переменную в процедуре, блок, класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="244f3-156">You can declare a variable in a procedure, block, class, structure, or module.</span></span> <span data-ttu-id="244f3-157">Невозможно объявить переменную в исходный файл, пространство имен или интерфейс.</span><span class="sxs-lookup"><span data-stu-id="244f3-157">You cannot declare a variable in a source file, namespace, or interface.</span></span> <span data-ttu-id="244f3-158">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="244f3-158">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="244f3-159">Переменная, объявленная на уровне модуля, вне любой процедуры *переменной-члена* или *поля*.</span><span class="sxs-lookup"><span data-stu-id="244f3-159">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span></span> <span data-ttu-id="244f3-160">Переменные-члены находятся в области всего их класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="244f3-160">Member variables are in scope throughout their class, structure, or module.</span></span> <span data-ttu-id="244f3-161">Переменная, объявленная на уровне процедуры является *локальной переменной*.</span><span class="sxs-lookup"><span data-stu-id="244f3-161">A variable that is declared at procedure level is a *local variable*.</span></span> <span data-ttu-id="244f3-162">Локальные переменные находятся в области действия только в процедурах или блоках.</span><span class="sxs-lookup"><span data-stu-id="244f3-162">Local variables are in scope only within their procedure or block.</span></span>  
  
 <span data-ttu-id="244f3-163">Следующие модификаторы доступа используются для объявления переменных вне процедуры: `Public`, `Protected`, `Friend`, `Protected Friend`, и `Private`.</span><span class="sxs-lookup"><span data-stu-id="244f3-163">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span></span> <span data-ttu-id="244f3-164">Дополнительные сведения см. в разделе [уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="244f3-164">For more information, see [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="244f3-165">`Dim` Ключевое слово является необязательным и обычно указывается, если необходимо указать любой из следующих модификаторов: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, или `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="244f3-165">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span></span>  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 <span data-ttu-id="244f3-166">Если `Option Explicit` является on (по умолчанию), компилятор требует объявления для каждой переменной можно использовать.</span><span class="sxs-lookup"><span data-stu-id="244f3-166">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span></span> <span data-ttu-id="244f3-167">Дополнительные сведения см. в разделе [оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="244f3-167">For more information, see [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span></span>  
  
## <a name="specifying-an-initial-value"></a><span data-ttu-id="244f3-168">Указание начального значения</span><span class="sxs-lookup"><span data-stu-id="244f3-168">Specifying an Initial Value</span></span>  
 <span data-ttu-id="244f3-169">Можно присвоить значение переменной при ее создании.</span><span class="sxs-lookup"><span data-stu-id="244f3-169">You can assign a value to a variable when it is created.</span></span> <span data-ttu-id="244f3-170">Для типа значения, используйте *инициализатора* позволяет указать выражение, назначаемое переменной.</span><span class="sxs-lookup"><span data-stu-id="244f3-170">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span></span> <span data-ttu-id="244f3-171">Выражение должно иметь константа, которая может быть вычислена во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="244f3-171">The expression must evaluate to a constant that can be calculated at compile time.</span></span>  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 <span data-ttu-id="244f3-172">Если указан инициализатор и тип данных не указан в `As` предложение, *вывод типа* используется для вывода типа данных на основе инициализатора.</span><span class="sxs-lookup"><span data-stu-id="244f3-172">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span></span> <span data-ttu-id="244f3-173">В следующем примере оба `num1` и `num2` являются строго типизированными как целые числа.</span><span class="sxs-lookup"><span data-stu-id="244f3-173">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span> <span data-ttu-id="244f3-174">Во втором объявлении вывод типа определяет тип значение 3.</span><span class="sxs-lookup"><span data-stu-id="244f3-174">In the second declaration, type inference infers the type from the value 3.</span></span>  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 <span data-ttu-id="244f3-175">Определение типов применяется на уровне процедуры.</span><span class="sxs-lookup"><span data-stu-id="244f3-175">Type inference applies at the procedure level.</span></span> <span data-ttu-id="244f3-176">Он не применяется вне процедур в класс, структура, модуль или интерфейс.</span><span class="sxs-lookup"><span data-stu-id="244f3-176">It does not apply outside a procedure in a class, structure, module, or interface.</span></span> <span data-ttu-id="244f3-177">Дополнительные сведения о выводе типа см. в разделе [Option Infer оператор](../../../visual-basic/language-reference/statements/option-infer-statement.md) и [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="244f3-177">For more information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="244f3-178">Сведения о что происходит, если не указан тип данных или инициализатор в разделе [по умолчанию типы данных и значения](../../../visual-basic/language-reference/statements/dim-statement.md#default) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="244f3-178">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](../../../visual-basic/language-reference/statements/dim-statement.md#default) later in this topic.</span></span>  
  
 <span data-ttu-id="244f3-179">Можно использовать *инициализатора объекта* для объявления экземпляров именованных и анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="244f3-179">You can use an *object initializer* to declare instances of named and anonymous types.</span></span> <span data-ttu-id="244f3-180">Следующий код создает экземпляр `Student` класса и использует инициализатор объектов для инициализации свойств.</span><span class="sxs-lookup"><span data-stu-id="244f3-180">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span></span>  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 <span data-ttu-id="244f3-181">Дополнительные сведения об инициализаторах объектов см. в разделе [как: объявление объекта с помощью инициализатора объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [инициализаторы объектов: именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), и [анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="244f3-181">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="declaring-multiple-variables"></a><span data-ttu-id="244f3-182">Объявление нескольких переменных</span><span class="sxs-lookup"><span data-stu-id="244f3-182">Declaring Multiple Variables</span></span>  
 <span data-ttu-id="244f3-183">Можно объявить несколько переменных в одном операторе объявления, указав имя переменной для каждого из них и имя массива в скобки.</span><span class="sxs-lookup"><span data-stu-id="244f3-183">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span></span> <span data-ttu-id="244f3-184">Переменные разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="244f3-184">Multiple variables are separated by commas.</span></span>  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 <span data-ttu-id="244f3-185">Если объявить несколько переменных с одним `As` предложения, не может предоставить инициализатор для этой группы переменных.</span><span class="sxs-lookup"><span data-stu-id="244f3-185">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span></span>  
  
 <span data-ttu-id="244f3-186">Можно указать различные типы данных для переменных с помощью отдельных `As` предложения для каждой объявляемой переменной.</span><span class="sxs-lookup"><span data-stu-id="244f3-186">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="244f3-187">Каждая переменная имеет тип данных, указанный в первой `As` предложение обнаружил после его `variablename` часть.</span><span class="sxs-lookup"><span data-stu-id="244f3-187">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span></span>  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a><span data-ttu-id="244f3-188">Массивы</span><span class="sxs-lookup"><span data-stu-id="244f3-188">Arrays</span></span>  
 <span data-ttu-id="244f3-189">Можно объявить переменную для хранения *массив*, который может содержать несколько значений.</span><span class="sxs-lookup"><span data-stu-id="244f3-189">You can declare a variable to hold an *array*, which can hold multiple values.</span></span> <span data-ttu-id="244f3-190">Чтобы указать, что переменная содержит массив, выполните его `variablename` немедленно со скобками.</span><span class="sxs-lookup"><span data-stu-id="244f3-190">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span></span> <span data-ttu-id="244f3-191">Дополнительные сведения о массивах см. в разделе [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="244f3-191">For more information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="244f3-192">Можно указать нижнюю и верхнюю границы каждого измерения массива.</span><span class="sxs-lookup"><span data-stu-id="244f3-192">You can specify the lower and upper bound of each dimension of an array.</span></span> <span data-ttu-id="244f3-193">Чтобы сделать это, включите `boundslist` в скобках.</span><span class="sxs-lookup"><span data-stu-id="244f3-193">To do this, include a `boundslist` inside the parentheses.</span></span> <span data-ttu-id="244f3-194">Для каждого измерения `boundslist` указывает верхнюю границу и при необходимости нижнюю границу.</span><span class="sxs-lookup"><span data-stu-id="244f3-194">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span></span> <span data-ttu-id="244f3-195">Нижняя граница всегда равно нулю, задания или нет.</span><span class="sxs-lookup"><span data-stu-id="244f3-195">The lower bound is always zero, whether you specify it or not.</span></span> <span data-ttu-id="244f3-196">Каждый индекс может изменяться от нуля до значения верхней границы.</span><span class="sxs-lookup"><span data-stu-id="244f3-196">Each index can vary from zero through its upper bound value.</span></span>  
  
 <span data-ttu-id="244f3-197">Следующие две инструкции эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="244f3-197">The following two statements are equivalent.</span></span> <span data-ttu-id="244f3-198">Каждый оператор объявляет массив из 21 `Integer` элементы.</span><span class="sxs-lookup"><span data-stu-id="244f3-198">Each statement declares an array of 21 `Integer` elements.</span></span> <span data-ttu-id="244f3-199">При доступе к массива, индекс может изменяться от 0 до 20.</span><span class="sxs-lookup"><span data-stu-id="244f3-199">When you access the array, the index can vary from 0 through 20.</span></span>  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 <span data-ttu-id="244f3-200">Следующий оператор объявляет двумерный массив типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="244f3-200">The following statement declares a two-dimensional array of type `Double`.</span></span> <span data-ttu-id="244f3-201">Массив имеет 4 строки (3 + 1) по 6 столбцов (5 + 1) каждая.</span><span class="sxs-lookup"><span data-stu-id="244f3-201">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span></span> <span data-ttu-id="244f3-202">Обратите внимание, что верхняя граница представляет наибольшее возможное значение для индекса, не длину измерения.</span><span class="sxs-lookup"><span data-stu-id="244f3-202">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span></span> <span data-ttu-id="244f3-203">Длина измерения равна значению верхней границы плюс один.</span><span class="sxs-lookup"><span data-stu-id="244f3-203">The length of the dimension is the upper bound plus one.</span></span>  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 <span data-ttu-id="244f3-204">Массив может содержать от 1 до 32 размерностей.</span><span class="sxs-lookup"><span data-stu-id="244f3-204">An array can have from 1 to 32 dimensions.</span></span>  
  
 <span data-ttu-id="244f3-205">Можно оставить все границы пустыми в объявлении массива.</span><span class="sxs-lookup"><span data-stu-id="244f3-205">You can leave all the bounds blank in an array declaration.</span></span> <span data-ttu-id="244f3-206">После этого массив содержит число измерений, которые указываются, но не будет инициализирован.</span><span class="sxs-lookup"><span data-stu-id="244f3-206">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span></span> <span data-ttu-id="244f3-207">Он имеет значение `Nothing` пока не инициализирована по крайней мере часть его элементов.</span><span class="sxs-lookup"><span data-stu-id="244f3-207">It has a value of `Nothing` until you initialize at least some of its elements.</span></span> <span data-ttu-id="244f3-208">`Dim` Инструкции необходимо указать границы для всех измерений или для измерения.</span><span class="sxs-lookup"><span data-stu-id="244f3-208">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span></span>  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 <span data-ttu-id="244f3-209">Если массив имеет более одного измерения, необходимо включить запятые между скобки, чтобы указать число размерностей.</span><span class="sxs-lookup"><span data-stu-id="244f3-209">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span></span>  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 <span data-ttu-id="244f3-210">Можно объявить *массив нулевой длины* объявив одно из измерений массива равным -1.</span><span class="sxs-lookup"><span data-stu-id="244f3-210">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span></span> <span data-ttu-id="244f3-211">Переменная, содержащая массив нулевой длины не имеет значения `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="244f3-211">A variable that holds a zero-length array does not have the value `Nothing`.</span></span> <span data-ttu-id="244f3-212">Массивы нулевой длины необходимы определенные функции среды CLR.</span><span class="sxs-lookup"><span data-stu-id="244f3-212">Zero-length arrays are required by certain common language runtime functions.</span></span> <span data-ttu-id="244f3-213">При попытке получить доступ к такой массив, возникает исключение времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="244f3-213">If you try to access such an array, a runtime exception occurs.</span></span> <span data-ttu-id="244f3-214">Дополнительные сведения см. в разделе [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="244f3-214">For more information, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="244f3-215">Значения массива можно инициализировать с помощью литерала массива.</span><span class="sxs-lookup"><span data-stu-id="244f3-215">You can initialize the values of an array by using an array literal.</span></span> <span data-ttu-id="244f3-216">Чтобы сделать это, заключите начальных значений в фигурные скобки (`{}`).</span><span class="sxs-lookup"><span data-stu-id="244f3-216">To do this, surround the initialization values with braces (`{}`).</span></span>  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 <span data-ttu-id="244f3-217">Для многомерных массивов инициализация для каждой отдельной размерности заключается в фигурные скобки внешней размерности.</span><span class="sxs-lookup"><span data-stu-id="244f3-217">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span></span> <span data-ttu-id="244f3-218">Элементы массивов задаются по строкам.</span><span class="sxs-lookup"><span data-stu-id="244f3-218">The elements are specified in row-major order.</span></span>  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 <span data-ttu-id="244f3-219">Дополнительные сведения о литералах массива в разделе [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="244f3-219">For more information about array literals, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
##  <span data-ttu-id="244f3-220"><a name="default"></a>Типы данных по умолчанию и значения</span><span class="sxs-lookup"><span data-stu-id="244f3-220"><a name="default"></a> Default Data Types and Values</span></span>  
 <span data-ttu-id="244f3-221">В следующей таблице перечислены результаты различных сочетаний заданных типов данных и инициализаторов в операторе `Dim`.</span><span class="sxs-lookup"><span data-stu-id="244f3-221">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="244f3-222">Указан тип данных?</span><span class="sxs-lookup"><span data-stu-id="244f3-222">Data type specified?</span></span>|<span data-ttu-id="244f3-223">Указан инициализатор?</span><span class="sxs-lookup"><span data-stu-id="244f3-223">Initializer specified?</span></span>|<span data-ttu-id="244f3-224">Пример</span><span class="sxs-lookup"><span data-stu-id="244f3-224">Example</span></span>|<span data-ttu-id="244f3-225">Результат</span><span class="sxs-lookup"><span data-stu-id="244f3-225">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="244f3-226">Нет</span><span class="sxs-lookup"><span data-stu-id="244f3-226">No</span></span>|<span data-ttu-id="244f3-227">Нет</span><span class="sxs-lookup"><span data-stu-id="244f3-227">No</span></span>|`Dim qty`|<span data-ttu-id="244f3-228">Если [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) — off (по умолчанию), значение переменной `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="244f3-228">If [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="244f3-229">Если параметр `Option Strict` включен, при компиляции возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="244f3-229">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="244f3-230">Нет</span><span class="sxs-lookup"><span data-stu-id="244f3-230">No</span></span>|<span data-ttu-id="244f3-231">Да</span><span class="sxs-lookup"><span data-stu-id="244f3-231">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="244f3-232">Если [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) включен (по умолчанию), переменная получает тип данных инициализатора.</span><span class="sxs-lookup"><span data-stu-id="244f3-232">If [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="244f3-233">В разделе [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="244f3-233">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="244f3-234">Если параметры `Option Infer` и `Option Strict` отключены, переменная получает тип данных `Object`.</span><span class="sxs-lookup"><span data-stu-id="244f3-234">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="244f3-235">Если параметр `Option Infer` отключен, а параметр `Option Strict` включен, при компиляции возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="244f3-235">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="244f3-236">Да</span><span class="sxs-lookup"><span data-stu-id="244f3-236">Yes</span></span>|<span data-ttu-id="244f3-237">Нет</span><span class="sxs-lookup"><span data-stu-id="244f3-237">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="244f3-238">Переменная инициализируется со значением по умолчанию для типа данных.</span><span class="sxs-lookup"><span data-stu-id="244f3-238">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="244f3-239">См. в таблице ниже в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="244f3-239">See the table later in this section.</span></span>|  
|<span data-ttu-id="244f3-240">Да</span><span class="sxs-lookup"><span data-stu-id="244f3-240">Yes</span></span>|<span data-ttu-id="244f3-241">Да</span><span class="sxs-lookup"><span data-stu-id="244f3-241">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="244f3-242">Если тип данных инициализатора нельзя преобразовать в указанный тип данных, возникает ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="244f3-242">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
 <span data-ttu-id="244f3-243">Если указать тип данных, но не указан инициализатор, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] инициализирует переменную со значением по умолчанию для его типа данных.</span><span class="sxs-lookup"><span data-stu-id="244f3-243">If you specify a data type but do not specify an initializer, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] initializes the variable to the default value for its data type.</span></span> <span data-ttu-id="244f3-244">В следующей таблице представлены значения инициализации.</span><span class="sxs-lookup"><span data-stu-id="244f3-244">The following table shows the default initialization values.</span></span>  
  
|<span data-ttu-id="244f3-245">Тип данных</span><span class="sxs-lookup"><span data-stu-id="244f3-245">Data type</span></span>|<span data-ttu-id="244f3-246">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="244f3-246">Default value</span></span>|  
|---|---|  
|<span data-ttu-id="244f3-247">Все числовые типы (включая `Byte` и `SByte`)</span><span class="sxs-lookup"><span data-stu-id="244f3-247">All numeric types (including `Byte` and `SByte`)</span></span>|<span data-ttu-id="244f3-248">0</span><span class="sxs-lookup"><span data-stu-id="244f3-248">0</span></span>|  
|`Char`|<span data-ttu-id="244f3-249">Двоичный 0</span><span class="sxs-lookup"><span data-stu-id="244f3-249">Binary 0</span></span>|  
|<span data-ttu-id="244f3-250">Все ссылочные типы (включая `Object`, `String`и все массивы)</span><span class="sxs-lookup"><span data-stu-id="244f3-250">All reference types (including `Object`, `String`, and all arrays)</span></span>|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|<span data-ttu-id="244f3-251">00:00:00 1 января 1 года (01/01/0001 12:00:00 AM)</span><span class="sxs-lookup"><span data-stu-id="244f3-251">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span></span>|  
  
 <span data-ttu-id="244f3-252">Каждый элемент структуры инициализируется, как если бы он был отдельной переменной.</span><span class="sxs-lookup"><span data-stu-id="244f3-252">Each element of a structure is initialized as if it were a separate variable.</span></span> <span data-ttu-id="244f3-253">Если объявляется длина массива, но не инициализируются его элементы, каждый элемент инициализируется, как если бы он был отдельной переменной.</span><span class="sxs-lookup"><span data-stu-id="244f3-253">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span></span>  
  
## <a name="static-local-variable-lifetime"></a><span data-ttu-id="244f3-254">Время существования статической локальной переменной</span><span class="sxs-lookup"><span data-stu-id="244f3-254">Static Local Variable Lifetime</span></span>  
 <span data-ttu-id="244f3-255">A `Static` локальная переменная имеет дольше процедуры, в котором она объявлена.</span><span class="sxs-lookup"><span data-stu-id="244f3-255">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span></span> <span data-ttu-id="244f3-256">Пределы существования переменной зависят от того, где объявлен процедуры и является ли оно `Shared`.</span><span class="sxs-lookup"><span data-stu-id="244f3-256">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span></span>  
  
|<span data-ttu-id="244f3-257">Объявление процедуры</span><span class="sxs-lookup"><span data-stu-id="244f3-257">Procedure declaration</span></span>|<span data-ttu-id="244f3-258">Переменная, инициализированная</span><span class="sxs-lookup"><span data-stu-id="244f3-258">Variable initialized</span></span>|<span data-ttu-id="244f3-259">Переменная прекращает существующие</span><span class="sxs-lookup"><span data-stu-id="244f3-259">Variable stops existing</span></span>|  
|---|---|---|  
|<span data-ttu-id="244f3-260">В модуле</span><span class="sxs-lookup"><span data-stu-id="244f3-260">In a module</span></span>|<span data-ttu-id="244f3-261">Первый раз при вызове процедуры</span><span class="sxs-lookup"><span data-stu-id="244f3-261">The first time the procedure is called</span></span>|<span data-ttu-id="244f3-262">Когда программа завершает выполнение</span><span class="sxs-lookup"><span data-stu-id="244f3-262">When your program stops execution</span></span>|  
|<span data-ttu-id="244f3-263">В классе или структуре — процедуры`Shared`</span><span class="sxs-lookup"><span data-stu-id="244f3-263">In a class or structure, procedure is `Shared`</span></span>|<span data-ttu-id="244f3-264">Первый раз при вызове процедуры на определенном экземпляре или на классе или структуре самой</span><span class="sxs-lookup"><span data-stu-id="244f3-264">The first time the procedure is called either on a specific instance or on the class or structure itself</span></span>|<span data-ttu-id="244f3-265">Когда программа завершает выполнение</span><span class="sxs-lookup"><span data-stu-id="244f3-265">When your program stops execution</span></span>|  
|<span data-ttu-id="244f3-266">В классе или структуре не процедуры`Shared`</span><span class="sxs-lookup"><span data-stu-id="244f3-266">In a class or structure, procedure isn't `Shared`</span></span>|<span data-ttu-id="244f3-267">При первом вызове процедуры на определенном экземпляре</span><span class="sxs-lookup"><span data-stu-id="244f3-267">The first time the procedure is called on a specific instance</span></span>|<span data-ttu-id="244f3-268">Когда экземпляр освобождается для сборки мусора (GC)</span><span class="sxs-lookup"><span data-stu-id="244f3-268">When the instance is released for garbage collection (GC)</span></span>|  
  
## <a name="attributes-and-modifiers"></a><span data-ttu-id="244f3-269">Атрибуты и модификаторы</span><span class="sxs-lookup"><span data-stu-id="244f3-269">Attributes and Modifiers</span></span>  
 <span data-ttu-id="244f3-270">Можно применить атрибуты только для переменных-членов, а не к локальным переменным.</span><span class="sxs-lookup"><span data-stu-id="244f3-270">You can apply attributes only to member variables, not to local variables.</span></span> <span data-ttu-id="244f3-271">Атрибут вносит сведения для метаданных сборки, которые не имеют смысла для временного хранения, такие как локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="244f3-271">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span></span>  
  
 <span data-ttu-id="244f3-272">На уровне модуля нельзя использовать `Static` модификатор объявления переменных-членов.</span><span class="sxs-lookup"><span data-stu-id="244f3-272">At module level, you cannot use the `Static` modifier to declare member variables.</span></span> <span data-ttu-id="244f3-273">На уровне процедур нельзя использовать `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, или любой доступ модификаторы объявления локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="244f3-273">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span></span>  
  
 <span data-ttu-id="244f3-274">Можно указать, какой код может обращаться к переменной, указав `accessmodifier`.</span><span class="sxs-lookup"><span data-stu-id="244f3-274">You can specify what code can access a variable by supplying an `accessmodifier`.</span></span> <span data-ttu-id="244f3-275">Класс модуля члены и переменные (вне любых процедур) по умолчанию имеют закрытый доступ, а переменные-члены структуры по умолчанию общий доступ.</span><span class="sxs-lookup"><span data-stu-id="244f3-275">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span></span> <span data-ttu-id="244f3-276">Можно настроить их уровни доступа с помощью модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="244f3-276">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="244f3-277">Нельзя использовать модификаторы доступа для локальных переменных (внутри процедуры).</span><span class="sxs-lookup"><span data-stu-id="244f3-277">You cannot use access modifiers on local variables (inside a procedure).</span></span>  
  
 <span data-ttu-id="244f3-278">Можно указать `WithEvents` только для переменных-членов, но не для локальных переменных внутри процедуры.</span><span class="sxs-lookup"><span data-stu-id="244f3-278">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span></span> <span data-ttu-id="244f3-279">При указании `WithEvents`, тип данных переменной должен быть определенный тип класса, не `Object`.</span><span class="sxs-lookup"><span data-stu-id="244f3-279">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span></span> <span data-ttu-id="244f3-280">Нельзя объявить массив с `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="244f3-280">You cannot declare an array with `WithEvents`.</span></span> <span data-ttu-id="244f3-281">Дополнительные сведения о событиях см. в разделе [события](../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="244f3-281">For more information about events, see [Events](../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="244f3-282">Код вне класса, структуры или модуля необходимо определять именем переменной-члена с именем этого класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="244f3-282">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="244f3-283">Код за пределами процедуры или блока не может ссылаться на любые локальные переменные в пределах этой процедуры или блока.</span><span class="sxs-lookup"><span data-stu-id="244f3-283">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span></span>  
  
## <a name="releasing-managed-resources"></a><span data-ttu-id="244f3-284">Освобождает управляемые ресурсы</span><span class="sxs-lookup"><span data-stu-id="244f3-284">Releasing Managed Resources</span></span>  
 <span data-ttu-id="244f3-285">Сборщик мусора .NET Framework без дополнительного кодирования с вашей стороны освобождает управляемые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="244f3-285">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span></span> <span data-ttu-id="244f3-286">Однако можно принудительно реализации управляемых ресурсов, а не ждать, пока сборщик мусора.</span><span class="sxs-lookup"><span data-stu-id="244f3-286">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="244f3-287">Если класс удерживает особо ценный и редкий ресурс (например, дескриптор подключения или файла базы данных), вы можете не дождаться следующей сборки мусора для очистки экземпляр класса, который больше не используется.</span><span class="sxs-lookup"><span data-stu-id="244f3-287">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span></span> <span data-ttu-id="244f3-288">Класс может реализовывать <xref:System.IDisposable>интерфейс позволяет освободить ресурсы перед сборкой мусора.</xref:System.IDisposable></span><span class="sxs-lookup"><span data-stu-id="244f3-288">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span></span> <span data-ttu-id="244f3-289">Класс, реализующий этот интерфейс предоставляет `Dispose` метод, который можно вызывать для принудительного ценные ресурсы, которые немедленно высвобождены.</span><span class="sxs-lookup"><span data-stu-id="244f3-289">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span></span>  
  
 <span data-ttu-id="244f3-290">`Using` Инструкция автоматизирует процесс получения ресурса, выполнения набора операторов и последующего освобождения ресурса.</span><span class="sxs-lookup"><span data-stu-id="244f3-290">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span></span> <span data-ttu-id="244f3-291">Тем не менее, необходимо реализовать ресурса <xref:System.IDisposable>интерфейса.</xref:System.IDisposable></span><span class="sxs-lookup"><span data-stu-id="244f3-291">However, the resource must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="244f3-292">Дополнительные сведения см. в разделе [с помощью инструкции](../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="244f3-292">For more information, see [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="244f3-293">Пример</span><span class="sxs-lookup"><span data-stu-id="244f3-293">Example</span></span>  
 <span data-ttu-id="244f3-294">В следующем примере объявляется переменных с помощью `Dim` инструкции с различными параметрами.</span><span class="sxs-lookup"><span data-stu-id="244f3-294">The following example declares variables by using the `Dim` statement with various options.</span></span>  
  
 <span data-ttu-id="244f3-295">[!code-vb[VbVbalrStatements&#141;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="244f3-295">[!code-vb[VbVbalrStatements#141](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="244f3-296">Пример</span><span class="sxs-lookup"><span data-stu-id="244f3-296">Example</span></span>  
 <span data-ttu-id="244f3-297">В следующем примере перечисляются простых чисел от 1 до 30.</span><span class="sxs-lookup"><span data-stu-id="244f3-297">The following example lists the prime numbers between 1 and 30.</span></span> <span data-ttu-id="244f3-298">Область локальных переменных, описан в комментариях к коду.</span><span class="sxs-lookup"><span data-stu-id="244f3-298">The scope of local variables is described in code comments.</span></span>  
  
 <span data-ttu-id="244f3-299">[!code-vb[VbVbalrStatements&#142;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="244f3-299">[!code-vb[VbVbalrStatements#142](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="244f3-300">Пример</span><span class="sxs-lookup"><span data-stu-id="244f3-300">Example</span></span>  
 <span data-ttu-id="244f3-301">В следующем примере `speedValue` переменная, объявленная на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="244f3-301">In the following example, the `speedValue` variable is declared at the class level.</span></span> <span data-ttu-id="244f3-302">`Private` Ключевое слово используется для объявления переменной.</span><span class="sxs-lookup"><span data-stu-id="244f3-302">The `Private` keyword is used to declare the variable.</span></span> <span data-ttu-id="244f3-303">Переменная может осуществляться из любой процедуры в `Car` класса.</span><span class="sxs-lookup"><span data-stu-id="244f3-303">The variable can be accessed by any procedure in the `Car` class.</span></span>  
  
 <span data-ttu-id="244f3-304">[!code-vb[VbVbalrStatements&#144;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="244f3-304">[!code-vb[VbVbalrStatements#144](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_3.vb)]</span></span>  
  
 <span data-ttu-id="244f3-305">[!code-vb[VbVbalrStatements&#145;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="244f3-305">[!code-vb[VbVbalrStatements#145](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="244f3-306">См. также</span><span class="sxs-lookup"><span data-stu-id="244f3-306">See Also</span></span>  
 <span data-ttu-id="244f3-307">[Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md) </span><span class="sxs-lookup"><span data-stu-id="244f3-307">[Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) </span></span>  
<span data-ttu-id="244f3-308"> [Оператор reDim](../../../visual-basic/language-reference/statements/redim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="244f3-308"> [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) </span></span>  
<span data-ttu-id="244f3-309"> [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span><span class="sxs-lookup"><span data-stu-id="244f3-309"> [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span></span>  
<span data-ttu-id="244f3-310"> [Оператор Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) </span><span class="sxs-lookup"><span data-stu-id="244f3-310"> [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) </span></span>  
<span data-ttu-id="244f3-311"> [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="244f3-311"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="244f3-312"> [Страница "Компиляция" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="244f3-312"> [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="244f3-313"> [Объявление переменных](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="244f3-313"> [Variable Declaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="244f3-314"> [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="244f3-314"> [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md) </span></span>  
<span data-ttu-id="244f3-315"> [Инициализаторы объектов: Именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="244f3-315"> [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) </span></span>  
<span data-ttu-id="244f3-316"> [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="244f3-316"> [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span></span>  
<span data-ttu-id="244f3-317"> [Инициализаторы объектов: Именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="244f3-317"> [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) </span></span>  
<span data-ttu-id="244f3-318"> [Практическое руководство: объявление объекта с помощью инициализатора объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md) </span><span class="sxs-lookup"><span data-stu-id="244f3-318"> [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md) </span></span>  
<span data-ttu-id="244f3-319"> [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)</span><span class="sxs-lookup"><span data-stu-id="244f3-319"> [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)</span></span>

