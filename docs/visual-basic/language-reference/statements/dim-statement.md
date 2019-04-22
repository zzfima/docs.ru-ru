---
title: Оператор Dim (Visual Basic)
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
ms.openlocfilehash: cab1cc07d23a44e57bdb0962a323b014308cb1e5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836562"
---
# <a name="dim-statement-visual-basic"></a><span data-ttu-id="8f35d-102">Оператор Dim (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f35d-102">Dim Statement (Visual Basic)</span></span>
<span data-ttu-id="8f35d-103">Объявляет и выделяет область хранения для одной или нескольких переменных.</span><span class="sxs-lookup"><span data-stu-id="8f35d-103">Declares and allocates storage space for one or more variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f35d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f35d-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]   
Dim [ WithEvents ] variablelist  
```  
  
## <a name="parts"></a><span data-ttu-id="8f35d-105">Части</span><span class="sxs-lookup"><span data-stu-id="8f35d-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="8f35d-106">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8f35d-106">Optional.</span></span> <span data-ttu-id="8f35d-107">См. в разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="8f35d-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="8f35d-108">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8f35d-108">Optional.</span></span> <span data-ttu-id="8f35d-109">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="8f35d-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="8f35d-110">Public</span><span class="sxs-lookup"><span data-stu-id="8f35d-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="8f35d-111">Protected</span><span class="sxs-lookup"><span data-stu-id="8f35d-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="8f35d-112">Friend</span><span class="sxs-lookup"><span data-stu-id="8f35d-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="8f35d-113">Закрытые</span><span class="sxs-lookup"><span data-stu-id="8f35d-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   [<span data-ttu-id="8f35d-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="8f35d-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)
    
    - [<span data-ttu-id="8f35d-115">Private Protected</span><span class="sxs-lookup"><span data-stu-id="8f35d-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

     <span data-ttu-id="8f35d-116">См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8f35d-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `Shared`  
  
     <span data-ttu-id="8f35d-117">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8f35d-117">Optional.</span></span> <span data-ttu-id="8f35d-118">См. в разделе [общих](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="8f35d-118">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="8f35d-119">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8f35d-119">Optional.</span></span> <span data-ttu-id="8f35d-120">См. в разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="8f35d-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Static`  
  
     <span data-ttu-id="8f35d-121">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8f35d-121">Optional.</span></span> <span data-ttu-id="8f35d-122">См. в разделе [статических](../../../visual-basic/language-reference/modifiers/static.md).</span><span class="sxs-lookup"><span data-stu-id="8f35d-122">See [Static](../../../visual-basic/language-reference/modifiers/static.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="8f35d-123">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8f35d-123">Optional.</span></span> <span data-ttu-id="8f35d-124">См. в разделе [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="8f35d-124">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WithEvents`  
  
     <span data-ttu-id="8f35d-125">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8f35d-125">Optional.</span></span> <span data-ttu-id="8f35d-126">Указывает, что они объектные переменные, которые ссылаются на экземпляры класса, который может порождать события.</span><span class="sxs-lookup"><span data-stu-id="8f35d-126">Specifies that these are object variables that refer to instances of a class that can raise events.</span></span> <span data-ttu-id="8f35d-127">См. в разделе [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="8f35d-127">See [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span></span>  
  
-   `variablelist`  
  
     <span data-ttu-id="8f35d-128">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="8f35d-128">Required.</span></span> <span data-ttu-id="8f35d-129">Список переменных, объявляемых в этом операторе.</span><span class="sxs-lookup"><span data-stu-id="8f35d-129">List of variables being declared in this statement.</span></span>  
  
     `variable [ , variable ... ]`  
  
     <span data-ttu-id="8f35d-130">Каждый элемент `variable` имеет перечисленные ниже синтаксис и компоненты.</span><span class="sxs-lookup"><span data-stu-id="8f35d-130">Each `variable` has the following syntax and parts:</span></span>  
  
     <span data-ttu-id="8f35d-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="8f35d-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="8f35d-132">Отделение</span><span class="sxs-lookup"><span data-stu-id="8f35d-132">Part</span></span>|<span data-ttu-id="8f35d-133">Описание</span><span class="sxs-lookup"><span data-stu-id="8f35d-133">Description</span></span>|  
    |---|---|  
    |`variablename`|<span data-ttu-id="8f35d-134">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="8f35d-134">Required.</span></span> <span data-ttu-id="8f35d-135">Имя переменной.</span><span class="sxs-lookup"><span data-stu-id="8f35d-135">Name of the variable.</span></span> <span data-ttu-id="8f35d-136">См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="8f35d-136">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
    |`boundslist`|<span data-ttu-id="8f35d-137">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8f35d-137">Optional.</span></span> <span data-ttu-id="8f35d-138">Список границ для каждого измерения массива.</span><span class="sxs-lookup"><span data-stu-id="8f35d-138">List of bounds of each dimension of an array variable.</span></span>|  
    |`New`|<span data-ttu-id="8f35d-139">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8f35d-139">Optional.</span></span> <span data-ttu-id="8f35d-140">Создает новый экземпляр класса при `Dim` выполняется инструкция.</span><span class="sxs-lookup"><span data-stu-id="8f35d-140">Creates a new instance of the class when the `Dim` statement runs.</span></span>|  
    |`datatype`|<span data-ttu-id="8f35d-141">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8f35d-141">Optional.</span></span> <span data-ttu-id="8f35d-142">Тип данных переменной.</span><span class="sxs-lookup"><span data-stu-id="8f35d-142">Data type of the variable.</span></span>|  
    |`With`|<span data-ttu-id="8f35d-143">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8f35d-143">Optional.</span></span> <span data-ttu-id="8f35d-144">Представляет список инициализаторов объектов.</span><span class="sxs-lookup"><span data-stu-id="8f35d-144">Introduces the object initializer list.</span></span>|  
    |`propertyname`|<span data-ttu-id="8f35d-145">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8f35d-145">Optional.</span></span> <span data-ttu-id="8f35d-146">Имя свойства в классе создании экземпляра.</span><span class="sxs-lookup"><span data-stu-id="8f35d-146">The name of a property in the class you are making an instance of.</span></span>|  
    |`propinitializer`|<span data-ttu-id="8f35d-147">После `propertyname` =.</span><span class="sxs-lookup"><span data-stu-id="8f35d-147">Required after `propertyname` =.</span></span> <span data-ttu-id="8f35d-148">Выражение, которое вычисляется и назначено имя свойства.</span><span class="sxs-lookup"><span data-stu-id="8f35d-148">The expression that is evaluated and assigned to the property name.</span></span>|  
    |`initializer`|<span data-ttu-id="8f35d-149">Необязателен при `New` не указан.</span><span class="sxs-lookup"><span data-stu-id="8f35d-149">Optional if `New` is not specified.</span></span> <span data-ttu-id="8f35d-150">Выражение, которое вычисляется и присваивается переменной при ее создании.</span><span class="sxs-lookup"><span data-stu-id="8f35d-150">Expression that is evaluated and assigned to the variable when it is created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f35d-151">Примечания</span><span class="sxs-lookup"><span data-stu-id="8f35d-151">Remarks</span></span>  
 <span data-ttu-id="8f35d-152">Компилятор Visual Basic использует `Dim` инструкцию, чтобы определить тип данных переменной и другие сведения, например какой код может обращаться к переменной.</span><span class="sxs-lookup"><span data-stu-id="8f35d-152">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span></span> <span data-ttu-id="8f35d-153">В следующем примере объявляется переменная для хранения `Integer` значение.</span><span class="sxs-lookup"><span data-stu-id="8f35d-153">The following example declares a variable to hold an `Integer` value.</span></span>  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 <span data-ttu-id="8f35d-154">Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8f35d-154">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="8f35d-155">Для ссылочного типа, используйте `New` ключевое слово, чтобы создать новый экземпляр класса или структуры, задается тип данных.</span><span class="sxs-lookup"><span data-stu-id="8f35d-155">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span></span> <span data-ttu-id="8f35d-156">Если вы используете `New`, вы не используете выражения инициализатора.</span><span class="sxs-lookup"><span data-stu-id="8f35d-156">If you use `New`, you do not use an initializer expression.</span></span> <span data-ttu-id="8f35d-157">Вместо этого аргументы, если они требуются, чтобы конструктор класса, из которого вы создаете переменную.</span><span class="sxs-lookup"><span data-stu-id="8f35d-157">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span></span>  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 <span data-ttu-id="8f35d-158">Можно объявить переменную в процедуре, блок, класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="8f35d-158">You can declare a variable in a procedure, block, class, structure, or module.</span></span> <span data-ttu-id="8f35d-159">Невозможно объявить переменную в исходный файл, пространство имен или интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8f35d-159">You cannot declare a variable in a source file, namespace, or interface.</span></span> <span data-ttu-id="8f35d-160">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8f35d-160">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="8f35d-161">Является переменной, объявленной на уровне модуля, вне любых процедур *переменной-члена* или *поле*.</span><span class="sxs-lookup"><span data-stu-id="8f35d-161">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span></span> <span data-ttu-id="8f35d-162">Переменные-члены находятся в области всего их класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="8f35d-162">Member variables are in scope throughout their class, structure, or module.</span></span> <span data-ttu-id="8f35d-163">Переменная, объявленная на уровне процедуры, является *локальной переменной*.</span><span class="sxs-lookup"><span data-stu-id="8f35d-163">A variable that is declared at procedure level is a *local variable*.</span></span> <span data-ttu-id="8f35d-164">Локальные переменные находятся в области действия только в их процедуры или блока.</span><span class="sxs-lookup"><span data-stu-id="8f35d-164">Local variables are in scope only within their procedure or block.</span></span>  
  
 <span data-ttu-id="8f35d-165">Следующие модификаторы доступа используются для объявления переменных вне процедуры: `Public`, `Protected`, `Friend`, `Protected Friend`, и `Private`.</span><span class="sxs-lookup"><span data-stu-id="8f35d-165">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span></span> <span data-ttu-id="8f35d-166">Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8f35d-166">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="8f35d-167">`Dim` Ключевое слово является необязательным и обычно опускается, если указать один из следующих модификаторов: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, или `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="8f35d-167">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span></span>  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 <span data-ttu-id="8f35d-168">Если `Option Explicit` является on (по умолчанию), компилятор требует объявления для каждой переменной, можно использовать.</span><span class="sxs-lookup"><span data-stu-id="8f35d-168">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span></span> <span data-ttu-id="8f35d-169">Дополнительные сведения см. в разделе [оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8f35d-169">For more information, see [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span></span>  
  
## <a name="specifying-an-initial-value"></a><span data-ttu-id="8f35d-170">Указание начального значения</span><span class="sxs-lookup"><span data-stu-id="8f35d-170">Specifying an Initial Value</span></span>  
 <span data-ttu-id="8f35d-171">Можно присвоить значение переменной при ее создании.</span><span class="sxs-lookup"><span data-stu-id="8f35d-171">You can assign a value to a variable when it is created.</span></span> <span data-ttu-id="8f35d-172">Для типа значения, используйте *инициализатор* позволяет указать выражение, назначаемое переменной.</span><span class="sxs-lookup"><span data-stu-id="8f35d-172">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span></span> <span data-ttu-id="8f35d-173">Выражение должно возвращать константой, может быть вычислено во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="8f35d-173">The expression must evaluate to a constant that can be calculated at compile time.</span></span>  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 <span data-ttu-id="8f35d-174">Если указан инициализатор, и тип данных не указан в `As` предложение, *вывод типа* используется для определения типа данных из инициализатора.</span><span class="sxs-lookup"><span data-stu-id="8f35d-174">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span></span> <span data-ttu-id="8f35d-175">В следующем примере оба `num1` и `num2` являются строго типизированными как целые числа.</span><span class="sxs-lookup"><span data-stu-id="8f35d-175">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span> <span data-ttu-id="8f35d-176">Во втором объявлении вывод типа определяет тип значение 3.</span><span class="sxs-lookup"><span data-stu-id="8f35d-176">In the second declaration, type inference infers the type from the value 3.</span></span>  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 <span data-ttu-id="8f35d-177">Определение типов применяется на уровне процедуры.</span><span class="sxs-lookup"><span data-stu-id="8f35d-177">Type inference applies at the procedure level.</span></span> <span data-ttu-id="8f35d-178">Он не применяется вне процедур в класс, структура, модуль или интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8f35d-178">It does not apply outside a procedure in a class, structure, module, or interface.</span></span> <span data-ttu-id="8f35d-179">Дополнительные сведения о выводе типа см. в разделе [оператор Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) и [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="8f35d-179">For more information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="8f35d-180">Чтобы узнать, что произойдет, если не указан тип данных или инициализатор, см. в разделе [типами данных по умолчанию и значения](../../../visual-basic/language-reference/statements/dim-statement.md#default) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="8f35d-180">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](../../../visual-basic/language-reference/statements/dim-statement.md#default) later in this topic.</span></span>  
  
 <span data-ttu-id="8f35d-181">Можно использовать *инициализатора объекта* для объявления экземпляры именованных и анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="8f35d-181">You can use an *object initializer* to declare instances of named and anonymous types.</span></span> <span data-ttu-id="8f35d-182">Следующий код создает экземпляр `Student` класса и использует инициализатор объекта для инициализации свойств.</span><span class="sxs-lookup"><span data-stu-id="8f35d-182">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span></span>  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 <span data-ttu-id="8f35d-183">Дополнительные сведения об инициализаторах объектов см. в разделе [как: Объявление объекта с помощью инициализатора объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [инициализаторы объектов: Именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), и [анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="8f35d-183">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="declaring-multiple-variables"></a><span data-ttu-id="8f35d-184">Объявление нескольких переменных</span><span class="sxs-lookup"><span data-stu-id="8f35d-184">Declaring Multiple Variables</span></span>  
 <span data-ttu-id="8f35d-185">Можно объявить несколько переменных в одном операторе объявления, указав имя переменной для каждого из них, а также имя массива в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="8f35d-185">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span></span> <span data-ttu-id="8f35d-186">Переменные разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="8f35d-186">Multiple variables are separated by commas.</span></span>  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 <span data-ttu-id="8f35d-187">Если объявляется несколько переменных с одним `As` предложение, невозможно указать инициализатор для этой группы переменных.</span><span class="sxs-lookup"><span data-stu-id="8f35d-187">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span></span>  
  
 <span data-ttu-id="8f35d-188">Можно указать различные типы данных для переменных с помощью отдельного `As` предложение для каждой объявляемой переменной.</span><span class="sxs-lookup"><span data-stu-id="8f35d-188">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="8f35d-189">Каждая переменная имеет тип данных, указанный в первом `As` предложения возникли после его `variablename` часть.</span><span class="sxs-lookup"><span data-stu-id="8f35d-189">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span></span>  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a><span data-ttu-id="8f35d-190">Массивы</span><span class="sxs-lookup"><span data-stu-id="8f35d-190">Arrays</span></span>  
 <span data-ttu-id="8f35d-191">Можно объявить переменную для хранения *массив*, который может содержать несколько значений.</span><span class="sxs-lookup"><span data-stu-id="8f35d-191">You can declare a variable to hold an *array*, which can hold multiple values.</span></span> <span data-ttu-id="8f35d-192">Чтобы указать, что переменная содержит массив, выполните его `variablename` немедленно со скобками.</span><span class="sxs-lookup"><span data-stu-id="8f35d-192">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span></span> <span data-ttu-id="8f35d-193">Дополнительные сведения см. в руководстве по работе с [массивами](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="8f35d-193">For more information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="8f35d-194">Можно указать нижнюю и верхнюю границу каждого измерения массива.</span><span class="sxs-lookup"><span data-stu-id="8f35d-194">You can specify the lower and upper bound of each dimension of an array.</span></span> <span data-ttu-id="8f35d-195">Чтобы сделать это, включите `boundslist` в скобках.</span><span class="sxs-lookup"><span data-stu-id="8f35d-195">To do this, include a `boundslist` inside the parentheses.</span></span> <span data-ttu-id="8f35d-196">Для каждого измерения `boundslist` указывает верхнюю границу и при необходимости нижняя граница.</span><span class="sxs-lookup"><span data-stu-id="8f35d-196">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span></span> <span data-ttu-id="8f35d-197">Нижняя граница всегда равно нулю, задания или нет.</span><span class="sxs-lookup"><span data-stu-id="8f35d-197">The lower bound is always zero, whether you specify it or not.</span></span> <span data-ttu-id="8f35d-198">Каждый индекс может изменяться от нуля до значения верхней границы.</span><span class="sxs-lookup"><span data-stu-id="8f35d-198">Each index can vary from zero through its upper bound value.</span></span>  
  
 <span data-ttu-id="8f35d-199">Следующие две инструкции эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="8f35d-199">The following two statements are equivalent.</span></span> <span data-ttu-id="8f35d-200">Каждый оператор объявляет массив 21 `Integer` элементов.</span><span class="sxs-lookup"><span data-stu-id="8f35d-200">Each statement declares an array of 21 `Integer` elements.</span></span> <span data-ttu-id="8f35d-201">Когда вы обращаетесь массива, индекс может изменяться от 0 до 20.</span><span class="sxs-lookup"><span data-stu-id="8f35d-201">When you access the array, the index can vary from 0 through 20.</span></span>  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 <span data-ttu-id="8f35d-202">Следующий оператор объявляет двухмерный массив типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="8f35d-202">The following statement declares a two-dimensional array of type `Double`.</span></span> <span data-ttu-id="8f35d-203">Массив имеет 4 строки (3 + 1) 6 столбцов (5 + 1) каждого.</span><span class="sxs-lookup"><span data-stu-id="8f35d-203">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span></span> <span data-ttu-id="8f35d-204">Обратите внимание, что верхняя граница представляет наибольшее возможное значение для индекса, но не длину измерения.</span><span class="sxs-lookup"><span data-stu-id="8f35d-204">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span></span> <span data-ttu-id="8f35d-205">Длина измерения равна верхней границе плюс один.</span><span class="sxs-lookup"><span data-stu-id="8f35d-205">The length of the dimension is the upper bound plus one.</span></span>  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 <span data-ttu-id="8f35d-206">Массив может быть от 1 до 32 измерений.</span><span class="sxs-lookup"><span data-stu-id="8f35d-206">An array can have from 1 to 32 dimensions.</span></span>  
  
 <span data-ttu-id="8f35d-207">Можно оставить все границы в объявлении массива.</span><span class="sxs-lookup"><span data-stu-id="8f35d-207">You can leave all the bounds blank in an array declaration.</span></span> <span data-ttu-id="8f35d-208">После этого, массив содержит число измерений, которые вы указали, но он не инициализирован.</span><span class="sxs-lookup"><span data-stu-id="8f35d-208">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span></span> <span data-ttu-id="8f35d-209">Он имеет значение `Nothing` до инициализации по крайней мере некоторые из его элементов.</span><span class="sxs-lookup"><span data-stu-id="8f35d-209">It has a value of `Nothing` until you initialize at least some of its elements.</span></span> <span data-ttu-id="8f35d-210">`Dim` Инструкции необходимо указать границы для всех измерений или нет измерений.</span><span class="sxs-lookup"><span data-stu-id="8f35d-210">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span></span>  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 <span data-ttu-id="8f35d-211">Если массив имеет более одного измерения, должно включать запятые заключено в круглые скобки, чтобы указать число измерений.</span><span class="sxs-lookup"><span data-stu-id="8f35d-211">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span></span>  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 <span data-ttu-id="8f35d-212">Можно объявить *массив нулевой длины* , объявив одно из измерений массива равным – 1.</span><span class="sxs-lookup"><span data-stu-id="8f35d-212">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span></span> <span data-ttu-id="8f35d-213">Переменная, содержащая массив нулевой длины не имеет значение `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="8f35d-213">A variable that holds a zero-length array does not have the value `Nothing`.</span></span> <span data-ttu-id="8f35d-214">Массивы нулевой длины необходимы определенные функции среды CLR.</span><span class="sxs-lookup"><span data-stu-id="8f35d-214">Zero-length arrays are required by certain common language runtime functions.</span></span> <span data-ttu-id="8f35d-215">При попытке получить доступ к таким массивам, возникает исключение времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="8f35d-215">If you try to access such an array, a runtime exception occurs.</span></span> <span data-ttu-id="8f35d-216">Дополнительные сведения см. в разделе [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="8f35d-216">For more information, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="8f35d-217">С помощью литерала массива можно инициализировать значения массива.</span><span class="sxs-lookup"><span data-stu-id="8f35d-217">You can initialize the values of an array by using an array literal.</span></span> <span data-ttu-id="8f35d-218">Чтобы сделать это, заключите начальных значений в фигурные скобки (`{}`).</span><span class="sxs-lookup"><span data-stu-id="8f35d-218">To do this, surround the initialization values with braces (`{}`).</span></span>  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 <span data-ttu-id="8f35d-219">Для многомерных массивов инициализации для каждой отдельной размерности заключается в фигурные скобки, в измерении «внешнее».</span><span class="sxs-lookup"><span data-stu-id="8f35d-219">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span></span> <span data-ttu-id="8f35d-220">Элементы указываются в строкам.</span><span class="sxs-lookup"><span data-stu-id="8f35d-220">The elements are specified in row-major order.</span></span>  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 <span data-ttu-id="8f35d-221">Дополнительные сведения о литералах массива см. в разделе [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="8f35d-221">For more information about array literals, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="default"></a> <span data-ttu-id="8f35d-222">Типы данных по умолчанию и значения</span><span class="sxs-lookup"><span data-stu-id="8f35d-222">Default Data Types and Values</span></span>  
 <span data-ttu-id="8f35d-223">В следующей таблице перечислены результаты различных сочетаний заданных типов данных и инициализаторов в операторе `Dim`.</span><span class="sxs-lookup"><span data-stu-id="8f35d-223">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="8f35d-224">Указан тип данных?</span><span class="sxs-lookup"><span data-stu-id="8f35d-224">Data type specified?</span></span>|<span data-ttu-id="8f35d-225">Указан инициализатор?</span><span class="sxs-lookup"><span data-stu-id="8f35d-225">Initializer specified?</span></span>|<span data-ttu-id="8f35d-226">Пример</span><span class="sxs-lookup"><span data-stu-id="8f35d-226">Example</span></span>|<span data-ttu-id="8f35d-227">Результат</span><span class="sxs-lookup"><span data-stu-id="8f35d-227">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="8f35d-228">Нет</span><span class="sxs-lookup"><span data-stu-id="8f35d-228">No</span></span>|<span data-ttu-id="8f35d-229">Нет</span><span class="sxs-lookup"><span data-stu-id="8f35d-229">No</span></span>|`Dim qty`|<span data-ttu-id="8f35d-230">Если [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) — off (по умолчанию), переменной присваивается `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="8f35d-230">If [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="8f35d-231">Если параметр `Option Strict` включен, возникает ошибка времени при компиляции.</span><span class="sxs-lookup"><span data-stu-id="8f35d-231">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="8f35d-232">Нет</span><span class="sxs-lookup"><span data-stu-id="8f35d-232">No</span></span>|<span data-ttu-id="8f35d-233">Да</span><span class="sxs-lookup"><span data-stu-id="8f35d-233">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="8f35d-234">Если [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) включен (по умолчанию), переменная получает тип данных инициализатора.</span><span class="sxs-lookup"><span data-stu-id="8f35d-234">If [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="8f35d-235">См. в разделе [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="8f35d-235">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="8f35d-236">Если параметры `Option Infer` и `Option Strict` отключены, переменная получает тип данных `Object`.</span><span class="sxs-lookup"><span data-stu-id="8f35d-236">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="8f35d-237">Если параметр `Option Infer` отключен, а параметр `Option Strict` включен, возникает ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="8f35d-237">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="8f35d-238">Да</span><span class="sxs-lookup"><span data-stu-id="8f35d-238">Yes</span></span>|<span data-ttu-id="8f35d-239">Нет</span><span class="sxs-lookup"><span data-stu-id="8f35d-239">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="8f35d-240">Переменная инициализируется со значением по умолчанию для типа данных.</span><span class="sxs-lookup"><span data-stu-id="8f35d-240">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="8f35d-241">См. в таблице ниже в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="8f35d-241">See the table later in this section.</span></span>|  
|<span data-ttu-id="8f35d-242">Да</span><span class="sxs-lookup"><span data-stu-id="8f35d-242">Yes</span></span>|<span data-ttu-id="8f35d-243">Да</span><span class="sxs-lookup"><span data-stu-id="8f35d-243">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="8f35d-244">Если тип данных инициализатора нельзя преобразовать в указанный тип данных, возникает ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="8f35d-244">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
 <span data-ttu-id="8f35d-245">Если указать тип данных, но не указан инициализатор, Visual Basic инициализирует переменную со значением по умолчанию для типа данных.</span><span class="sxs-lookup"><span data-stu-id="8f35d-245">If you specify a data type but do not specify an initializer, Visual Basic initializes the variable to the default value for its data type.</span></span> <span data-ttu-id="8f35d-246">Следующая таблица показывает значение по умолчанию значения инициализации.</span><span class="sxs-lookup"><span data-stu-id="8f35d-246">The following table shows the default initialization values.</span></span>  
  
|<span data-ttu-id="8f35d-247">Тип данных</span><span class="sxs-lookup"><span data-stu-id="8f35d-247">Data type</span></span>|<span data-ttu-id="8f35d-248">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8f35d-248">Default value</span></span>|  
|---|---|  
|<span data-ttu-id="8f35d-249">Все числовые типы (включая `Byte` и `SByte`)</span><span class="sxs-lookup"><span data-stu-id="8f35d-249">All numeric types (including `Byte` and `SByte`)</span></span>|<span data-ttu-id="8f35d-250">0</span><span class="sxs-lookup"><span data-stu-id="8f35d-250">0</span></span>|  
|`Char`|<span data-ttu-id="8f35d-251">Двоичный 0</span><span class="sxs-lookup"><span data-stu-id="8f35d-251">Binary 0</span></span>|  
|<span data-ttu-id="8f35d-252">Все ссылочные типы (включая `Object`, `String`и все массивы)</span><span class="sxs-lookup"><span data-stu-id="8f35d-252">All reference types (including `Object`, `String`, and all arrays)</span></span>|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|<span data-ttu-id="8f35d-253">00:00:00 1 января 1 года (01/01/0001 12:00:00 AM)</span><span class="sxs-lookup"><span data-stu-id="8f35d-253">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span></span>|  
  
 <span data-ttu-id="8f35d-254">Каждый элемент структуры инициализируется, как если бы он был отдельной переменной.</span><span class="sxs-lookup"><span data-stu-id="8f35d-254">Each element of a structure is initialized as if it were a separate variable.</span></span> <span data-ttu-id="8f35d-255">Если вы объявите длину массива, но не инициализировать его элементы, каждый элемент инициализируется, как если бы он был отдельной переменной.</span><span class="sxs-lookup"><span data-stu-id="8f35d-255">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span></span>  
  
## <a name="static-local-variable-lifetime"></a><span data-ttu-id="8f35d-256">Время существования статической локальной переменной</span><span class="sxs-lookup"><span data-stu-id="8f35d-256">Static Local Variable Lifetime</span></span>  
 <span data-ttu-id="8f35d-257">Объект `Static` локальная переменная имеет дольше процедуры, в котором она объявлена.</span><span class="sxs-lookup"><span data-stu-id="8f35d-257">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span></span> <span data-ttu-id="8f35d-258">Пределы существования переменной зависят от того, где объявлен процедуру и является ли он `Shared`.</span><span class="sxs-lookup"><span data-stu-id="8f35d-258">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span></span>  
  
|<span data-ttu-id="8f35d-259">Объявление процедуры</span><span class="sxs-lookup"><span data-stu-id="8f35d-259">Procedure declaration</span></span>|<span data-ttu-id="8f35d-260">Переменная, инициализированная</span><span class="sxs-lookup"><span data-stu-id="8f35d-260">Variable initialized</span></span>|<span data-ttu-id="8f35d-261">Переменная прекращает существующие</span><span class="sxs-lookup"><span data-stu-id="8f35d-261">Variable stops existing</span></span>|  
|---|---|---|  
|<span data-ttu-id="8f35d-262">В модуле</span><span class="sxs-lookup"><span data-stu-id="8f35d-262">In a module</span></span>|<span data-ttu-id="8f35d-263">При первом вызове процедуры</span><span class="sxs-lookup"><span data-stu-id="8f35d-263">The first time the procedure is called</span></span>|<span data-ttu-id="8f35d-264">Когда программа останавливает выполнение</span><span class="sxs-lookup"><span data-stu-id="8f35d-264">When your program stops execution</span></span>|  
|<span data-ttu-id="8f35d-265">В классе или структуре процедура является `Shared`</span><span class="sxs-lookup"><span data-stu-id="8f35d-265">In a class or structure, procedure is `Shared`</span></span>|<span data-ttu-id="8f35d-266">Первый раз при вызове процедуры в определенном экземпляре или на классе или структуре самой</span><span class="sxs-lookup"><span data-stu-id="8f35d-266">The first time the procedure is called either on a specific instance or on the class or structure itself</span></span>|<span data-ttu-id="8f35d-267">Когда программа останавливает выполнение</span><span class="sxs-lookup"><span data-stu-id="8f35d-267">When your program stops execution</span></span>|  
|<span data-ttu-id="8f35d-268">В классе или структуре не процедуры `Shared`</span><span class="sxs-lookup"><span data-stu-id="8f35d-268">In a class or structure, procedure isn't `Shared`</span></span>|<span data-ttu-id="8f35d-269">При первом вызове процедуры в определенном экземпляре</span><span class="sxs-lookup"><span data-stu-id="8f35d-269">The first time the procedure is called on a specific instance</span></span>|<span data-ttu-id="8f35d-270">Когда экземпляр освобождается для сборки мусора (GC)</span><span class="sxs-lookup"><span data-stu-id="8f35d-270">When the instance is released for garbage collection (GC)</span></span>|  
  
## <a name="attributes-and-modifiers"></a><span data-ttu-id="8f35d-271">Атрибуты и модификаторы</span><span class="sxs-lookup"><span data-stu-id="8f35d-271">Attributes and Modifiers</span></span>  
 <span data-ttu-id="8f35d-272">Можно применять атрибуты только для переменных-членов, не для локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="8f35d-272">You can apply attributes only to member variables, not to local variables.</span></span> <span data-ttu-id="8f35d-273">Атрибут вносит сведения для метаданных сборки, которая не имеет смысла для временного хранения, такие как локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="8f35d-273">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span></span>  
  
 <span data-ttu-id="8f35d-274">На уровне модуля нельзя использовать `Static` модификатор для объявления переменных-членов.</span><span class="sxs-lookup"><span data-stu-id="8f35d-274">At module level, you cannot use the `Static` modifier to declare member variables.</span></span> <span data-ttu-id="8f35d-275">На уровне процедуры, нельзя использовать `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, или любой доступ модификаторы для объявления локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="8f35d-275">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span></span>  
  
 <span data-ttu-id="8f35d-276">Можно указать, какой код может обращаться к переменной, указав `accessmodifier`.</span><span class="sxs-lookup"><span data-stu-id="8f35d-276">You can specify what code can access a variable by supplying an `accessmodifier`.</span></span> <span data-ttu-id="8f35d-277">Класс модуля члены и переменные (за пределами любых процедур) по умолчанию закрытый доступ и переменные-члены структуры по умолчанию общий доступ.</span><span class="sxs-lookup"><span data-stu-id="8f35d-277">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span></span> <span data-ttu-id="8f35d-278">Вы можете настроить уровни доступа с помощью модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="8f35d-278">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="8f35d-279">Нельзя использовать модификаторы доступа для локальных переменных (внутри процедуры).</span><span class="sxs-lookup"><span data-stu-id="8f35d-279">You cannot use access modifiers on local variables (inside a procedure).</span></span>  
  
 <span data-ttu-id="8f35d-280">Можно указать `WithEvents` только для переменных-членов, а не на локальные переменные внутри процедуры.</span><span class="sxs-lookup"><span data-stu-id="8f35d-280">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span></span> <span data-ttu-id="8f35d-281">Если указать `WithEvents`, тип данных переменной должен быть определенный тип класса, не `Object`.</span><span class="sxs-lookup"><span data-stu-id="8f35d-281">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span></span> <span data-ttu-id="8f35d-282">Можно объявить массив, содержащий `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="8f35d-282">You cannot declare an array with `WithEvents`.</span></span> <span data-ttu-id="8f35d-283">Дополнительные сведения о событиях см. в разделе [события](../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="8f35d-283">For more information about events, see [Events](../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f35d-284">Код вне класса, структуры или модуля необходимо указать имя переменной-члена с именем этого класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="8f35d-284">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="8f35d-285">Код за пределами процедуры или блока не может ссылаться на всех локальных переменных в рамках этой процедуры или блока.</span><span class="sxs-lookup"><span data-stu-id="8f35d-285">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span></span>  
  
## <a name="releasing-managed-resources"></a><span data-ttu-id="8f35d-286">Освобождение управляемых ресурсов</span><span class="sxs-lookup"><span data-stu-id="8f35d-286">Releasing Managed Resources</span></span>  
 <span data-ttu-id="8f35d-287">Сборщик мусора .NET Framework освобождает управляемые ресурсы без дополнительного кодирования со стороны пользователя.</span><span class="sxs-lookup"><span data-stu-id="8f35d-287">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span></span> <span data-ttu-id="8f35d-288">Тем не менее вы можете принудительно реализации управляемых ресурсов, а не ждать, пока сборщик мусора.</span><span class="sxs-lookup"><span data-stu-id="8f35d-288">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="8f35d-289">Если класс удерживает особо ценный и редкий ресурс (например, дескриптор подключения или файл базы данных), может не потребоваться дождаться следующей сборки мусора для очистки экземпляра класса, который больше не используется.</span><span class="sxs-lookup"><span data-stu-id="8f35d-289">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span></span> <span data-ttu-id="8f35d-290">Класс может реализовывать <xref:System.IDisposable> интерфейс, который позволит освободить ресурсы перед сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="8f35d-290">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span></span> <span data-ttu-id="8f35d-291">Класс, реализующий этот интерфейс предоставляет `Dispose` метод, который может быть вызван для принудительного полезные материалы, которые немедленно высвобождены.</span><span class="sxs-lookup"><span data-stu-id="8f35d-291">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span></span>  
  
 <span data-ttu-id="8f35d-292">`Using` Инструкции автоматизирует процесс получения ресурса, выполнения набора инструкций и последующего освобождения ресурса.</span><span class="sxs-lookup"><span data-stu-id="8f35d-292">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span></span> <span data-ttu-id="8f35d-293">Тем не менее, необходимо реализовать ресурса <xref:System.IDisposable> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8f35d-293">However, the resource must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="8f35d-294">Дополнительные сведения см. в разделе [Оператор using](../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8f35d-294">For more information, see [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f35d-295">Пример</span><span class="sxs-lookup"><span data-stu-id="8f35d-295">Example</span></span>  
 <span data-ttu-id="8f35d-296">В следующем примере объявляется переменных с помощью `Dim` инструкции с различными параметрами.</span><span class="sxs-lookup"><span data-stu-id="8f35d-296">The following example declares variables by using the `Dim` statement with various options.</span></span>  
  
 [!code-vb[VbVbalrStatements#141](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#141)]  
  
## <a name="example"></a><span data-ttu-id="8f35d-297">Пример</span><span class="sxs-lookup"><span data-stu-id="8f35d-297">Example</span></span>  
 <span data-ttu-id="8f35d-298">В следующем примере перечисляются простых чисел от 1 до 30.</span><span class="sxs-lookup"><span data-stu-id="8f35d-298">The following example lists the prime numbers between 1 and 30.</span></span> <span data-ttu-id="8f35d-299">Область локальных переменных описан в комментариях к коду.</span><span class="sxs-lookup"><span data-stu-id="8f35d-299">The scope of local variables is described in code comments.</span></span>  
  
 [!code-vb[VbVbalrStatements#142](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#142)]  
  
## <a name="example"></a><span data-ttu-id="8f35d-300">Пример</span><span class="sxs-lookup"><span data-stu-id="8f35d-300">Example</span></span>  
 <span data-ttu-id="8f35d-301">В следующем примере `speedValue` переменная, объявленная на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="8f35d-301">In the following example, the `speedValue` variable is declared at the class level.</span></span> <span data-ttu-id="8f35d-302">`Private` Ключевое слово используется для объявления переменной.</span><span class="sxs-lookup"><span data-stu-id="8f35d-302">The `Private` keyword is used to declare the variable.</span></span> <span data-ttu-id="8f35d-303">Переменная может осуществляться в любой процедурой `Car` класса.</span><span class="sxs-lookup"><span data-stu-id="8f35d-303">The variable can be accessed by any procedure in the `Car` class.</span></span>  
  
 [!code-vb[VbVbalrStatements#144](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#144)]  
  
 [!code-vb[VbVbalrStatements#145](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#145)]  
  
## <a name="see-also"></a><span data-ttu-id="8f35d-304">См. также</span><span class="sxs-lookup"><span data-stu-id="8f35d-304">See also</span></span>

- [<span data-ttu-id="8f35d-305">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="8f35d-305">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="8f35d-306">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="8f35d-306">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="8f35d-307">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="8f35d-307">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="8f35d-308">Оператор Option Infer</span><span class="sxs-lookup"><span data-stu-id="8f35d-308">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="8f35d-309">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="8f35d-309">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="8f35d-310">Страница "Компиляция" в конструкторе проектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f35d-310">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="8f35d-311">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="8f35d-311">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="8f35d-312">Массивы</span><span class="sxs-lookup"><span data-stu-id="8f35d-312">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="8f35d-313">Инициализаторы объектов. Именованные и анонимные типы</span><span class="sxs-lookup"><span data-stu-id="8f35d-313">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="8f35d-314">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="8f35d-314">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="8f35d-315">Инициализаторы объектов. Именованные и анонимные типы</span><span class="sxs-lookup"><span data-stu-id="8f35d-315">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="8f35d-316">Практическое руководство. Объявление объекта с помощью инициализатора объектов</span><span class="sxs-lookup"><span data-stu-id="8f35d-316">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
- [<span data-ttu-id="8f35d-317">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="8f35d-317">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
