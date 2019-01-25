---
title: Оператор Function (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Function
helpviewer_keywords:
- procedures [Visual Basic], creating
- Function procedures [Visual Basic], Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword [Visual Basic], Function statements
- Private keyword [Visual Basic], Function statements
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- Public keyword [Visual Basic], in Function statement
- ByVal keyword [Visual Basic], Function statements
- procedures [Visual Basic], recursive
- Implements keyword [Visual Basic], Function statements
- procedures [Visual Basic], returning values
- Exit statement [Visual Basic], in Function procedures
- recursive procedures
- As keyword [Visual Basic], in Function statement
- Optional keyword [Visual Basic], Function statements
- Function statement [Visual Basic]
- Visual Basic code, Function procedures
- procedures [Visual Basic], function
- ByRef keyword [Visual Basic], Function statements
- Friend keyword [Visual Basic], Function statements
- End keyword [Visual Basic], Function statements
- Handles keyword [Visual Basic], Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
ms.openlocfilehash: 5018aebb0401ce5a1c46ecf04a7c65ca676271e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565908"
---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="b31a5-102">Оператор Function (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b31a5-102">Function Statement (Visual Basic)</span></span>
<span data-ttu-id="b31a5-103">Объявляет имя, параметры и код, которые определяют `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="b31a5-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b31a5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b31a5-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]  
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Function ]  
    [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="b31a5-105">Части</span><span class="sxs-lookup"><span data-stu-id="b31a5-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="b31a5-106">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b31a5-106">Optional.</span></span> <span data-ttu-id="b31a5-107">См. в разделе [список атрибутов](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="b31a5-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="b31a5-108">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b31a5-108">Optional.</span></span> <span data-ttu-id="b31a5-109">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="b31a5-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="b31a5-110">Public</span><span class="sxs-lookup"><span data-stu-id="b31a5-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="b31a5-111">Protected</span><span class="sxs-lookup"><span data-stu-id="b31a5-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="b31a5-112">Friend</span><span class="sxs-lookup"><span data-stu-id="b31a5-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="b31a5-113">Закрытые</span><span class="sxs-lookup"><span data-stu-id="b31a5-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   [<span data-ttu-id="b31a5-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="b31a5-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

    - [<span data-ttu-id="b31a5-115">Private Protected</span><span class="sxs-lookup"><span data-stu-id="b31a5-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)  
  
     <span data-ttu-id="b31a5-116">См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="b31a5-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="b31a5-117">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b31a5-117">Optional.</span></span> <span data-ttu-id="b31a5-118">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="b31a5-118">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="b31a5-119">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="b31a5-119">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="b31a5-120">Переопределения</span><span class="sxs-lookup"><span data-stu-id="b31a5-120">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="b31a5-121">Переопределяемые</span><span class="sxs-lookup"><span data-stu-id="b31a5-121">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="b31a5-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="b31a5-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="b31a5-123">MustOverride</span><span class="sxs-lookup"><span data-stu-id="b31a5-123">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="b31a5-124">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b31a5-124">Optional.</span></span> <span data-ttu-id="b31a5-125">См. в разделе [общих](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="b31a5-125">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="b31a5-126">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b31a5-126">Optional.</span></span> <span data-ttu-id="b31a5-127">См. в разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="b31a5-127">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="b31a5-128">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b31a5-128">Optional.</span></span> <span data-ttu-id="b31a5-129">См. в разделе [Async](../../../visual-basic/language-reference/modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="b31a5-129">See [Async](../../../visual-basic/language-reference/modifiers/async.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="b31a5-130">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b31a5-130">Optional.</span></span> <span data-ttu-id="b31a5-131">См. в разделе [итератор](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="b31a5-131">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="b31a5-132">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b31a5-132">Required.</span></span> <span data-ttu-id="b31a5-133">Имя процедуры.</span><span class="sxs-lookup"><span data-stu-id="b31a5-133">Name of the procedure.</span></span> <span data-ttu-id="b31a5-134">См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="b31a5-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="b31a5-135">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b31a5-135">Optional.</span></span> <span data-ttu-id="b31a5-136">Список параметров типа для универсальной процедуры.</span><span class="sxs-lookup"><span data-stu-id="b31a5-136">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="b31a5-137">См. в разделе [введите список](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="b31a5-137">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="b31a5-138">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b31a5-138">Optional.</span></span> <span data-ttu-id="b31a5-139">Список имен локальных переменных, представляющих параметры этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="b31a5-139">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="b31a5-140">См. в разделе [список параметров](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="b31a5-140">See [Parameter List](parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="b31a5-141">Обязателен, если `Option Strict` является `On`.</span><span class="sxs-lookup"><span data-stu-id="b31a5-141">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="b31a5-142">Тип данных значения, возвращаемые этой процедурой.</span><span class="sxs-lookup"><span data-stu-id="b31a5-142">Data type of the value returned by this procedure.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="b31a5-143">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b31a5-143">Optional.</span></span> <span data-ttu-id="b31a5-144">Указывает, что эта процедура реализует один или несколько `Function` процедуры, каждая из которых определена в интерфейс, реализуемый этой процедуры классом или структурой.</span><span class="sxs-lookup"><span data-stu-id="b31a5-144">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="b31a5-145">См. в разделе [реализует оператор](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b31a5-145">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="b31a5-146">Является обязательным, если предоставлен параметр `Implements`.</span><span class="sxs-lookup"><span data-stu-id="b31a5-146">Required if `Implements` is supplied.</span></span> <span data-ttu-id="b31a5-147">Список реализуемых процедур `Function`.</span><span class="sxs-lookup"><span data-stu-id="b31a5-147">List of `Function` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="b31a5-148">Каждый элемент `implementedprocedure` имеет перечисленные ниже синтаксис и компоненты.</span><span class="sxs-lookup"><span data-stu-id="b31a5-148">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="b31a5-149">Отделение</span><span class="sxs-lookup"><span data-stu-id="b31a5-149">Part</span></span>|<span data-ttu-id="b31a5-150">Описание</span><span class="sxs-lookup"><span data-stu-id="b31a5-150">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="b31a5-151">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b31a5-151">Required.</span></span> <span data-ttu-id="b31a5-152">Имя интерфейса, реализуемого этой процедуры содержащей класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="b31a5-152">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="b31a5-153">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b31a5-153">Required.</span></span> <span data-ttu-id="b31a5-154">Имя, под которым процедура определена в `interface`.</span><span class="sxs-lookup"><span data-stu-id="b31a5-154">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="b31a5-155">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b31a5-155">Optional.</span></span> <span data-ttu-id="b31a5-156">Указывает, что эта процедура может обрабатывать один или несколько определенных событий.</span><span class="sxs-lookup"><span data-stu-id="b31a5-156">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="b31a5-157">См. в разделе [обрабатывает](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b31a5-157">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="b31a5-158">Является обязательным, если предоставлен параметр `Handles`.</span><span class="sxs-lookup"><span data-stu-id="b31a5-158">Required if `Handles` is supplied.</span></span> <span data-ttu-id="b31a5-159">Список событий, которые обрабатывает эту процедуру.</span><span class="sxs-lookup"><span data-stu-id="b31a5-159">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="b31a5-160">Каждый элемент `eventspecifier` имеет перечисленные ниже синтаксис и компоненты.</span><span class="sxs-lookup"><span data-stu-id="b31a5-160">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="b31a5-161">Отделение</span><span class="sxs-lookup"><span data-stu-id="b31a5-161">Part</span></span>|<span data-ttu-id="b31a5-162">Описание:</span><span class="sxs-lookup"><span data-stu-id="b31a5-162">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="b31a5-163">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b31a5-163">Required.</span></span> <span data-ttu-id="b31a5-164">Объектной переменной, объявленной с типом данных класса или структуры, который вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="b31a5-164">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="b31a5-165">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b31a5-165">Required.</span></span> <span data-ttu-id="b31a5-166">Имя события, которое обрабатывает эту процедуру.</span><span class="sxs-lookup"><span data-stu-id="b31a5-166">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="b31a5-167">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b31a5-167">Optional.</span></span> <span data-ttu-id="b31a5-168">Блок операторов, выполняемый в рамках этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="b31a5-168">Block of statements to be executed within this procedure.</span></span>  
  
-   `End Function`  
  
     <span data-ttu-id="b31a5-169">Завершает определение этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="b31a5-169">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b31a5-170">Примечания</span><span class="sxs-lookup"><span data-stu-id="b31a5-170">Remarks</span></span>  
 <span data-ttu-id="b31a5-171">Весь исполняемый код должен быть внутри процедуры.</span><span class="sxs-lookup"><span data-stu-id="b31a5-171">All executable code must be inside a procedure.</span></span> <span data-ttu-id="b31a5-172">Каждая процедура в свою очередь, объявляется внутри класса, структуры или модуль, который называется содержащего класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="b31a5-172">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>  
  
 <span data-ttu-id="b31a5-173">Чтобы вернуть значение в вызывающий код, используйте `Function` процедуры; в противном случае используйте `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="b31a5-173">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>  
  
## <a name="defining-a-function"></a><span data-ttu-id="b31a5-174">Определение функции</span><span class="sxs-lookup"><span data-stu-id="b31a5-174">Defining a Function</span></span>  
 <span data-ttu-id="b31a5-175">Вы можете определить `Function` процедуры только на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="b31a5-175">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="b31a5-176">Таким образом контекст объявления для функции должен быть класс, структура, модуль или интерфейс и не может быть исходным файлом, пространство имен, процедура или блок.</span><span class="sxs-lookup"><span data-stu-id="b31a5-176">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="b31a5-177">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="b31a5-177">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="b31a5-178">`Function` процедуры по умолчанию для общего доступа.</span><span class="sxs-lookup"><span data-stu-id="b31a5-178">`Function` procedures default to public access.</span></span> <span data-ttu-id="b31a5-179">Вы можете настроить уровни доступа с помощью модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="b31a5-179">You can adjust their access levels with the access modifiers.</span></span>  
  
 <span data-ttu-id="b31a5-180">Объект `Function` процедуре можно объявить тип данных, процедура возвращает значения.</span><span class="sxs-lookup"><span data-stu-id="b31a5-180">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="b31a5-181">Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b31a5-181">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="b31a5-182">Если вы не укажете `returntype` параметра, процедура возвращает `Object`.</span><span class="sxs-lookup"><span data-stu-id="b31a5-182">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>  
  
 <span data-ttu-id="b31a5-183">Если в этой процедуре используется `Implements` ключевое слово, содержащем классе или структуре также должен иметь `Implements` оператор, который следует сразу за его `Class` или `Structure` инструкции.</span><span class="sxs-lookup"><span data-stu-id="b31a5-183">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="b31a5-184">`Implements` Инструкция должна включать каждого интерфейса, который указан в `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="b31a5-184">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="b31a5-185">Тем не менее имя, по которому определяется интерфейс `Function` (в `definedname`) не должно совпадать с именем этой процедуры (в `name`).</span><span class="sxs-lookup"><span data-stu-id="b31a5-185">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b31a5-186">Лямбда-выражения можно использовать для определения выражения встроенную функцию.</span><span class="sxs-lookup"><span data-stu-id="b31a5-186">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="b31a5-187">Дополнительные сведения см. в разделе [выражение функции](../../../visual-basic/language-reference/operators/function-expression.md) и [лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="b31a5-187">For more information, see [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md) and [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="returning-from-a-function"></a><span data-ttu-id="b31a5-188">Возврат из функции</span><span class="sxs-lookup"><span data-stu-id="b31a5-188">Returning from a Function</span></span>  
 <span data-ttu-id="b31a5-189">Когда `Function` процедура возвращает в вызывающий код, выполнение продолжается с оператора, который расположен после оператора, который вызвал процедуру.</span><span class="sxs-lookup"><span data-stu-id="b31a5-189">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>  
  
 <span data-ttu-id="b31a5-190">Для возврата значения из функции, можно присвоить значение имени функции или включить ее в `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="b31a5-190">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>  
  
 <span data-ttu-id="b31a5-191">`Return` Инструкции одновременно назначает возвращаемое значение и выход из функции, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b31a5-191">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]  
  
 <span data-ttu-id="b31a5-192">В следующем примере присваивается значение имени функции `myFunction` , а затем использует `Exit Function` инструкция возвращает.</span><span class="sxs-lookup"><span data-stu-id="b31a5-192">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]  
  
 <span data-ttu-id="b31a5-193">`Exit Function` И `Return` инструкции вызывают Немедленный выход из `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="b31a5-193">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="b31a5-194">Любое количество `Exit Function` и `Return` инструкций может находиться в любом в процедуре, и вы можете комбинировать `Exit Function` и `Return` инструкций.</span><span class="sxs-lookup"><span data-stu-id="b31a5-194">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>  
  
 <span data-ttu-id="b31a5-195">Если вы используете `Exit Function` без присвоения значения `name`, процедура возвращает значение по умолчанию для типа данных, который указан в `returntype`.</span><span class="sxs-lookup"><span data-stu-id="b31a5-195">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="b31a5-196">Если `returntype` не указан, процедура возвращает `Nothing`, который является значением по умолчанию для `Object`.</span><span class="sxs-lookup"><span data-stu-id="b31a5-196">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>  
  
## <a name="calling-a-function"></a><span data-ttu-id="b31a5-197">Вызов функции</span><span class="sxs-lookup"><span data-stu-id="b31a5-197">Calling a Function</span></span>  
 <span data-ttu-id="b31a5-198">Вы вызываете `Function` процедуры с помощью имени процедуры, за которым следует список аргументов в скобки в выражении.</span><span class="sxs-lookup"><span data-stu-id="b31a5-198">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="b31a5-199">Скобки могут опускаться только в том случае, если вы не имеет аргументов.</span><span class="sxs-lookup"><span data-stu-id="b31a5-199">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="b31a5-200">Тем не менее код является более удобочитаемым, если всегда использовать круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="b31a5-200">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="b31a5-201">Вы вызываете `Function` процедуры, так же, что вызывать любую библиотеку функций, таких как `Sqrt`, `Cos`, или `ChrW`.</span><span class="sxs-lookup"><span data-stu-id="b31a5-201">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>  
  
 <span data-ttu-id="b31a5-202">Можно также вызвать функцию с помощью `Call` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="b31a5-202">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="b31a5-203">В этом случае возвращаемое значение учитывается.</span><span class="sxs-lookup"><span data-stu-id="b31a5-203">In that case, the return value is ignored.</span></span> <span data-ttu-id="b31a5-204">Использование `Call` ключевое слово не рекомендуется в большинстве случаев.</span><span class="sxs-lookup"><span data-stu-id="b31a5-204">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="b31a5-205">Дополнительные сведения см. в разделе [инструкции Call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b31a5-205">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="b31a5-206">Visual Basic иногда упорядочение арифметические выражения для повышения эффективности внутренней.</span><span class="sxs-lookup"><span data-stu-id="b31a5-206">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="b31a5-207">По этой причине не следует использовать `Function` процедуры в арифметическом выражении, если функция изменяет значение переменных в одном выражении.</span><span class="sxs-lookup"><span data-stu-id="b31a5-207">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>  
  
## <a name="async-functions"></a><span data-ttu-id="b31a5-208">Асинхронные функции</span><span class="sxs-lookup"><span data-stu-id="b31a5-208">Async Functions</span></span>  
 <span data-ttu-id="b31a5-209">*Async* позволяет вызывать асинхронные функции без использованию явных обратных вызовов или ручному разделению кода между несколькими функции или лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="b31a5-209">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="b31a5-210">Если пометить функцию с [Async](../../../visual-basic/language-reference/modifiers/async.md) модификатор, можно использовать [Await](../../../visual-basic/language-reference/operators/await-operator.md) оператор в функции.</span><span class="sxs-lookup"><span data-stu-id="b31a5-210">If you mark a function with the [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="b31a5-211">Когда управление достигает `Await` выражение в `Async` функции, управление возвращается вызывающему объекту и выполнение в функции приостанавливается до завершения выполнения ожидающей задачи.</span><span class="sxs-lookup"><span data-stu-id="b31a5-211">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="b31a5-212">После завершения задачи можно возобновить выполнение в функцию.</span><span class="sxs-lookup"><span data-stu-id="b31a5-212">When the task is complete, execution can resume in the function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b31a5-213">`Async` Процедура возвращает вызывающему объекту, когда либо он встречает первый ожидаемый объект, который еще не завершено, или он получает в конец `Async` процедуры, что произойдет раньше.</span><span class="sxs-lookup"><span data-stu-id="b31a5-213">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>  
  
 <span data-ttu-id="b31a5-214">`Async` Функция может иметь тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> или <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="b31a5-214">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="b31a5-215">Пример `Async` функции с типом возвращаемого значения <xref:System.Threading.Tasks.Task%601> приведен ниже.</span><span class="sxs-lookup"><span data-stu-id="b31a5-215">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>  
  
 <span data-ttu-id="b31a5-216">`Async` Функция не может объявлять [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) параметров.</span><span class="sxs-lookup"><span data-stu-id="b31a5-216">An `Async` function cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="b31a5-217">Объект [оператор Sub](sub-statement.md) можно также пометить `Async` модификатор.</span><span class="sxs-lookup"><span data-stu-id="b31a5-217">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="b31a5-218">Это в основном используется для обработчиков событий, где не может быть возвращено значение.</span><span class="sxs-lookup"><span data-stu-id="b31a5-218">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="b31a5-219">`Async` `Sub` Процедуру нельзя ожидать и вызывающий `Async` `Sub` процедура не может перехватывать исключения, вызываемые по `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="b31a5-219">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>  
  
 <span data-ttu-id="b31a5-220">Дополнительные сведения о `Async` функции, см. в разделе [асинхронное программирование с использованием Async и Await](../../../visual-basic/programming-guide/concepts/async/index.md), [поток управления в асинхронных программах](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), и [асинхронные типы возвращаемых значений](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="b31a5-220">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="iterator-functions"></a><span data-ttu-id="b31a5-221">Функции итераторов</span><span class="sxs-lookup"><span data-stu-id="b31a5-221">Iterator Functions</span></span>  
 <span data-ttu-id="b31a5-222">*Итератор* функция выполняет настраиваемую итерацию по коллекции, такие как список или массив.</span><span class="sxs-lookup"><span data-stu-id="b31a5-222">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="b31a5-223">Использует функцию итератор [Yield](yield-statement.md) инструкцию для возврата всех элементов одному за раз.</span><span class="sxs-lookup"><span data-stu-id="b31a5-223">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="b31a5-224">Когда [Yield](yield-statement.md) оператору текущее расположение в коде запоминается.</span><span class="sxs-lookup"><span data-stu-id="b31a5-224">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="b31a5-225">При следующем вызове функции итератора выполнение возобновляется с этого места.</span><span class="sxs-lookup"><span data-stu-id="b31a5-225">Execution is restarted from that location the next time the iterator function is called.</span></span>  
  
 <span data-ttu-id="b31a5-226">Итератор вызывается из клиентского кода с помощью [для каждого... Далее](for-each-next-statement.md) инструкции.</span><span class="sxs-lookup"><span data-stu-id="b31a5-226">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>  
  
 <span data-ttu-id="b31a5-227">Тип возвращаемого значения функции итератора может быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, или <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="b31a5-227">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="b31a5-228">Дополнительные сведения см. в разделе [Итераторы](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="b31a5-228">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b31a5-229">Пример</span><span class="sxs-lookup"><span data-stu-id="b31a5-229">Example</span></span>  
 <span data-ttu-id="b31a5-230">В следующем примере используется `Function` инструкцию для объявления имени, параметров и кода, образующих текст `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="b31a5-230">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="b31a5-231">`ParamArray` Модификатор разрешает функции принимать переменное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="b31a5-231">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#25](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="b31a5-232">Пример</span><span class="sxs-lookup"><span data-stu-id="b31a5-232">Example</span></span>  
 <span data-ttu-id="b31a5-233">В следующем примере вызывается функция, объявленная в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="b31a5-233">The following example invokes the function declared in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="b31a5-234">Пример</span><span class="sxs-lookup"><span data-stu-id="b31a5-234">Example</span></span>  
 <span data-ttu-id="b31a5-235">В следующем примере `DelayAsync` — `Async` `Function` с типом возвращаемого значения <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="b31a5-235">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="b31a5-236">`DelayAsync` имеет инструкцию `Return` , которая возвращает целое число.</span><span class="sxs-lookup"><span data-stu-id="b31a5-236">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="b31a5-237">Поэтому объявление функции `DelayAsync` должен иметь тип возвращаемого значения `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="b31a5-237">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="b31a5-238">Так как возвращаемый тип — `Task(Of Integer)`, вычисление `Await` выражение в `DoSomethingAsync` создает целое.</span><span class="sxs-lookup"><span data-stu-id="b31a5-238">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="b31a5-239">Это показано в этом операторе: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="b31a5-239">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="b31a5-240">`startButton_Click` Процедура является примером `Async Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="b31a5-240">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="b31a5-241">Так как `DoSomethingAsync` — `Async` функции, задача для вызова `DoSomethingAsync` должна быть ожидаемой, как показано в следующей инструкции: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="b31a5-241">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="b31a5-242">`startButton_Click` `Sub` Процедура должна быть определена с помощью `Async` модификатор из-за `Await` выражение.</span><span class="sxs-lookup"><span data-stu-id="b31a5-242">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b31a5-243">См. также</span><span class="sxs-lookup"><span data-stu-id="b31a5-243">See also</span></span>
- [<span data-ttu-id="b31a5-244">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="b31a5-244">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="b31a5-245">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="b31a5-245">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="b31a5-246">Список параметров</span><span class="sxs-lookup"><span data-stu-id="b31a5-246">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="b31a5-247">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="b31a5-247">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="b31a5-248">Оператор Call</span><span class="sxs-lookup"><span data-stu-id="b31a5-248">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="b31a5-249">Of</span><span class="sxs-lookup"><span data-stu-id="b31a5-249">Of</span></span>](of-clause.md)
- [<span data-ttu-id="b31a5-250">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="b31a5-250">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="b31a5-251">Практическое руководство. Использование универсального класса</span><span class="sxs-lookup"><span data-stu-id="b31a5-251">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="b31a5-252">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="b31a5-252">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="b31a5-253">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="b31a5-253">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="b31a5-254">Выражение функции</span><span class="sxs-lookup"><span data-stu-id="b31a5-254">Function Expression</span></span>](../../../visual-basic/language-reference/operators/function-expression.md)
