---
title: "Оператор Function (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Function
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
caps.latest.revision: "62"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 667ab7ceb54e1f339fd645883ca2686c0cbb72b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="4f7fe-102">Оператор Function (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f7fe-102">Function Statement (Visual Basic)</span></span>
<span data-ttu-id="4f7fe-103">Объявляет имя, параметры и код, определяющие `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f7fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f7fe-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]  
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Function ]  
    [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="4f7fe-105">Части</span><span class="sxs-lookup"><span data-stu-id="4f7fe-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="4f7fe-106">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-106">Optional.</span></span> <span data-ttu-id="4f7fe-107">В разделе [список атрибутов](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="4f7fe-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="4f7fe-108">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-108">Optional.</span></span> <span data-ttu-id="4f7fe-109">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="4f7fe-110">Public</span><span class="sxs-lookup"><span data-stu-id="4f7fe-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="4f7fe-111">Protected</span><span class="sxs-lookup"><span data-stu-id="4f7fe-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="4f7fe-112">Friend</span><span class="sxs-lookup"><span data-stu-id="4f7fe-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="4f7fe-113">Закрытые</span><span class="sxs-lookup"><span data-stu-id="4f7fe-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="4f7fe-114">В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4f7fe-114">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="4f7fe-115">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-115">Optional.</span></span> <span data-ttu-id="4f7fe-116">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-116">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="4f7fe-117">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="4f7fe-117">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="4f7fe-118">Переопределения</span><span class="sxs-lookup"><span data-stu-id="4f7fe-118">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="4f7fe-119">Переопределяемые</span><span class="sxs-lookup"><span data-stu-id="4f7fe-119">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="4f7fe-120">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="4f7fe-120">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="4f7fe-121">MustOverride</span><span class="sxs-lookup"><span data-stu-id="4f7fe-121">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="4f7fe-122">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-122">Optional.</span></span> <span data-ttu-id="4f7fe-123">В разделе [общих](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="4f7fe-123">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="4f7fe-124">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-124">Optional.</span></span> <span data-ttu-id="4f7fe-125">В разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="4f7fe-125">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="4f7fe-126">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-126">Optional.</span></span> <span data-ttu-id="4f7fe-127">В разделе [Async](../../../visual-basic/language-reference/modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="4f7fe-127">See [Async](../../../visual-basic/language-reference/modifiers/async.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="4f7fe-128">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-128">Optional.</span></span> <span data-ttu-id="4f7fe-129">В разделе [итератор](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="4f7fe-129">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="4f7fe-130">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-130">Required.</span></span> <span data-ttu-id="4f7fe-131">Имя процедуры.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-131">Name of the procedure.</span></span> <span data-ttu-id="4f7fe-132">В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="4f7fe-132">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="4f7fe-133">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-133">Optional.</span></span> <span data-ttu-id="4f7fe-134">Список параметров типа для универсальной процедуры.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-134">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="4f7fe-135">В разделе [введите список](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="4f7fe-135">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="4f7fe-136">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-136">Optional.</span></span> <span data-ttu-id="4f7fe-137">Список имен локальных переменных, представляющих параметры этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-137">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="4f7fe-138">В разделе [список параметров](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="4f7fe-138">See [Parameter List](parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="4f7fe-139">Обязателен, если `Option Strict` — `On`.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-139">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="4f7fe-140">Тип данных значения, возвращаемые этой процедурой.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-140">Data type of the value returned by this procedure.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="4f7fe-141">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-141">Optional.</span></span> <span data-ttu-id="4f7fe-142">Указывает, что эта процедура реализует один или несколько `Function` процедуры, каждая из которых определена в интерфейс, реализуемый этой процедуры классом или структурой.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-142">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="4f7fe-143">В разделе [реализует оператор](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4f7fe-143">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="4f7fe-144">Является обязательным, если предоставлен параметр `Implements`.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-144">Required if `Implements` is supplied.</span></span> <span data-ttu-id="4f7fe-145">Список реализуемых процедур `Function`.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-145">List of `Function` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="4f7fe-146">Каждый элемент `implementedprocedure` имеет перечисленные ниже синтаксис и компоненты.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-146">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="4f7fe-147">Отделение</span><span class="sxs-lookup"><span data-stu-id="4f7fe-147">Part</span></span>|<span data-ttu-id="4f7fe-148">Описание</span><span class="sxs-lookup"><span data-stu-id="4f7fe-148">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="4f7fe-149">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-149">Required.</span></span> <span data-ttu-id="4f7fe-150">Имя интерфейса, реализуемого данной процедурой, содержащего класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-150">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="4f7fe-151">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-151">Required.</span></span> <span data-ttu-id="4f7fe-152">Имя, под которым процедура определена в `interface`.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-152">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="4f7fe-153">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-153">Optional.</span></span> <span data-ttu-id="4f7fe-154">Указывает, что эта процедура может обрабатывать одно или несколько конкретных событий.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-154">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="4f7fe-155">В разделе [обрабатывает](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="4f7fe-155">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="4f7fe-156">Является обязательным, если предоставлен параметр `Handles`.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-156">Required if `Handles` is supplied.</span></span> <span data-ttu-id="4f7fe-157">Список событий, которые обрабатывает данная процедура.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-157">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="4f7fe-158">Каждый элемент `eventspecifier` имеет перечисленные ниже синтаксис и компоненты.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-158">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="4f7fe-159">Отделение</span><span class="sxs-lookup"><span data-stu-id="4f7fe-159">Part</span></span>|<span data-ttu-id="4f7fe-160">Описание</span><span class="sxs-lookup"><span data-stu-id="4f7fe-160">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="4f7fe-161">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-161">Required.</span></span> <span data-ttu-id="4f7fe-162">Объектная переменная объявлена с типом данных класса или структуры, который инициирует событие.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-162">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="4f7fe-163">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-163">Required.</span></span> <span data-ttu-id="4f7fe-164">Имя события, которое обрабатывает данная процедура.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-164">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="4f7fe-165">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-165">Optional.</span></span> <span data-ttu-id="4f7fe-166">Блок операторов для выполнения этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-166">Block of statements to be executed within this procedure.</span></span>  
  
-   `End Function`  
  
     <span data-ttu-id="4f7fe-167">Завершает определение данной процедуры.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-167">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f7fe-168">Примечания</span><span class="sxs-lookup"><span data-stu-id="4f7fe-168">Remarks</span></span>  
 <span data-ttu-id="4f7fe-169">Весь исполняемый код должен быть внутри процедуры.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-169">All executable code must be inside a procedure.</span></span> <span data-ttu-id="4f7fe-170">Каждая процедура в свою очередь, объявлен внутри класса, структуры или модуль, который называется содержащего класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-170">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>  
  
 <span data-ttu-id="4f7fe-171">Чтобы вернуть значение в вызывающий код, используйте `Function` процедуры; в противном случае используйте `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-171">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>  
  
## <a name="defining-a-function"></a><span data-ttu-id="4f7fe-172">Определение функции</span><span class="sxs-lookup"><span data-stu-id="4f7fe-172">Defining a Function</span></span>  
 <span data-ttu-id="4f7fe-173">Можно определить `Function` процедуры только на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-173">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="4f7fe-174">Таким образом что контекст объявления для функции должен быть класс, структура, модуль или интерфейс и не может быть исходным файлом, пространство имен, процедура или блок.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-174">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="4f7fe-175">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4f7fe-175">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="4f7fe-176">`Function`процедуры по умолчанию для общего доступа.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-176">`Function` procedures default to public access.</span></span> <span data-ttu-id="4f7fe-177">Вы можете настроить уровни доступа с помощью модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-177">You can adjust their access levels with the access modifiers.</span></span>  
  
 <span data-ttu-id="4f7fe-178">Объект `Function` процедура может объявить тип данных, процедура возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-178">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="4f7fe-179">Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-179">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="4f7fe-180">Если не указать `returntype` , процедура возвращает `Object`.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-180">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>  
  
 <span data-ttu-id="4f7fe-181">Если в этой процедуре используется `Implements` ключевое слово, содержащего класса или структуры, также должен иметь `Implements` оператор, который следует сразу за его `Class` или `Structure` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-181">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="4f7fe-182">`Implements` Инструкция должна включать каждого интерфейса, который указан в `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="4f7fe-183">Тем не менее имя, по которому интерфейс определяет `Function` (в `definedname`) не должны совпадать с именем этой процедуры (в `name`).</span><span class="sxs-lookup"><span data-stu-id="4f7fe-183">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f7fe-184">Лямбда-выражения можно использовать для определения встроенной функции выражения.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-184">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="4f7fe-185">Дополнительные сведения см. в разделе [выражение функции](../../../visual-basic/language-reference/operators/function-expression.md) и [лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4f7fe-185">For more information, see [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md) and [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="returning-from-a-function"></a><span data-ttu-id="4f7fe-186">Возврат из функции</span><span class="sxs-lookup"><span data-stu-id="4f7fe-186">Returning from a Function</span></span>  
 <span data-ttu-id="4f7fe-187">Когда `Function` процедура возвращает в вызывающий код, выполнение продолжается с оператора, следующего за оператором, который вызвал процедуру.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-187">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>  
  
 <span data-ttu-id="4f7fe-188">Для возврата значения из функции, можно присвоить значение имени функции или включить ее в `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-188">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>  
  
 <span data-ttu-id="4f7fe-189">`Return` Инструкция одновременно назначает возвращаемое значение и выходит из функции, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-189">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]  
  
 <span data-ttu-id="4f7fe-190">В следующем примере возвращаемое значение присваивается имени функции `myFunction` , а затем использует `Exit Function` для возврата.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-190">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]  
  
 <span data-ttu-id="4f7fe-191">`Exit Function` И `Return` инструкции вызывают Немедленный выход из `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-191">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="4f7fe-192">Любое количество `Exit Function` и `Return` операторы могут использоваться в любом месте в процедуре, и могут быть использованы смешанные `Exit Function` и `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-192">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>  
  
 <span data-ttu-id="4f7fe-193">Если вы используете `Exit Function` без присвоения значения `name`, процедура возвращает значение по умолчанию для типа данных, который указан в `returntype`.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-193">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="4f7fe-194">Если `returntype` не указан, процедура возвращает `Nothing`, который является значением по умолчанию для `Object`.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-194">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>  
  
## <a name="calling-a-function"></a><span data-ttu-id="4f7fe-195">Вызов функции</span><span class="sxs-lookup"><span data-stu-id="4f7fe-195">Calling a Function</span></span>  
 <span data-ttu-id="4f7fe-196">Вызывается `Function` процедуры с помощью имени процедуры, за которым следует список аргументов в скобки в выражении.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-196">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="4f7fe-197">Круглые скобки можно опустить только в том случае, если вы не имеет аргументов.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-197">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="4f7fe-198">Тем не менее код является более удобочитаемым, если всегда использовать круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-198">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="4f7fe-199">Можно вызвать `Function` процедуры одинаково вызывать любую библиотеку функции, такие как `Sqrt`, `Cos`, или `ChrW`.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-199">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>  
  
 <span data-ttu-id="4f7fe-200">Можно также вызвать функцию с помощью `Call` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-200">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="4f7fe-201">В этом случае возвращаемое значение игнорируется.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-201">In that case, the return value is ignored.</span></span> <span data-ttu-id="4f7fe-202">Использование `Call` ключевое слово не рекомендуется в большинстве случаев.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-202">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="4f7fe-203">Дополнительные сведения см. в разделе [инструкции Call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4f7fe-203">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="4f7fe-204">Visual Basic иногда упорядочение арифметические выражения для повышения внутренней эффективности.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-204">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="4f7fe-205">По этой причине не следует использовать `Function` процедуры в арифметическом выражении, если функция изменяет значение переменных в одном выражении.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-205">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>  
  
## <a name="async-functions"></a><span data-ttu-id="4f7fe-206">Асинхронные функции</span><span class="sxs-lookup"><span data-stu-id="4f7fe-206">Async Functions</span></span>  
 <span data-ttu-id="4f7fe-207">*Async* позволяет вызывать асинхронные функции, не прибегая к использованию явных обратных вызовов или ручному разделению кода между несколькими функции или лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-207">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="4f7fe-208">Если определить функцию с [Async](../../../visual-basic/language-reference/modifiers/async.md) модификатор, можно использовать [Await](../../../visual-basic/language-reference/operators/await-operator.md) оператор в функции.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-208">If you mark a function with the [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="4f7fe-209">Когда управление достигает `Await` выражения в `Async` функции, управление возвращается вызывающему объекту и выполнение в функции приостанавливается до завершения выполнения ожидающей задачи.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-209">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="4f7fe-210">После завершения задачи можно возобновить выполнение в функции.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-210">When the task is complete, execution can resume in the function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f7fe-211">`Async` Процедура возвращает вызывающему встречает первый ожидаемый объект, который еще не завершена, или он доходит до конца `Async` процедуры, какое событие происходит раньше.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-211">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>  
  
 <span data-ttu-id="4f7fe-212">`Async` Функция может иметь тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> или <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-212">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="4f7fe-213">Пример `Async` функции, которая имеет тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-213">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>  
  
 <span data-ttu-id="4f7fe-214">`Async` Функция не может объявить все [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) параметров.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-214">An `Async` function cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="4f7fe-215">Объект [оператор Sub](sub-statement.md) также могут быть помечены с помощью `Async` модификатор.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-215">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="4f7fe-216">Это в первую очередь для обработчиков событий, где не может быть возвращено значение.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-216">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="4f7fe-217">`Async``Sub` Процедуру нельзя ожидать и код, вызывающий `Async``Sub` процедура не может перехватывать исключения, возникающие с `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-217">An `Async``Sub` procedure can't be awaited, and the caller of an `Async``Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>  
  
 <span data-ttu-id="4f7fe-218">Дополнительные сведения о `Async` функции, в разделе [асинхронное программирование с использованием ключевых слов Async и Await](../../../visual-basic/programming-guide/concepts/async/index.md), [поток управления в асинхронных программах](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), и [асинхронные типы возвращаемых значений](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="4f7fe-218">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="iterator-functions"></a><span data-ttu-id="4f7fe-219">Функции итератора</span><span class="sxs-lookup"><span data-stu-id="4f7fe-219">Iterator Functions</span></span>  
 <span data-ttu-id="4f7fe-220">*Итератор* функция выполняет настраиваемую итерацию по коллекции, например список или массив.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-220">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="4f7fe-221">Использует функции итератора [Yield](yield-statement.md) инструкции для возврата всех элементов, одну за другой.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-221">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="4f7fe-222">Когда [Yield](yield-statement.md) инструкция исчерпана, текущее расположение в коде запоминается.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-222">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="4f7fe-223">При следующем вызове функции итератора выполнение возобновляется с этого места.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-223">Execution is restarted from that location the next time the iterator function is called.</span></span>  
  
 <span data-ttu-id="4f7fe-224">Итератор вызывается из клиентского кода с помощью [For Each... Далее](for-each-next-statement.md) инструкции.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-224">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>  
  
 <span data-ttu-id="4f7fe-225">Тип возвращаемого значения функции итератора может быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, или <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-225">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="4f7fe-226">Дополнительные сведения см. в разделе [Итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="4f7fe-226">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f7fe-227">Пример</span><span class="sxs-lookup"><span data-stu-id="4f7fe-227">Example</span></span>  
 <span data-ttu-id="4f7fe-228">В следующем примере используется `Function` инструкции для объявления имени, параметров и кода, образующих текст `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-228">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="4f7fe-229">`ParamArray` Модификатор разрешает функции принимать переменное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-229">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#25](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="4f7fe-230">Пример</span><span class="sxs-lookup"><span data-stu-id="4f7fe-230">Example</span></span>  
 <span data-ttu-id="4f7fe-231">В следующем примере вызывается функция, объявленная в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-231">The following example invokes the function declared in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="4f7fe-232">Пример</span><span class="sxs-lookup"><span data-stu-id="4f7fe-232">Example</span></span>  
 <span data-ttu-id="4f7fe-233">В следующем примере `DelayAsync` — `Async``Function` с типом возвращаемого значения <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-233">In the following example, `DelayAsync` is an `Async``Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="4f7fe-234">`DelayAsync` имеет инструкцию `Return`, которая возвращает целое число.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-234">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="4f7fe-235">Поэтому объявление функции `DelayAsync` должен иметь тип возвращаемого значения `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-235">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="4f7fe-236">Так как возвращаемый тип — `Task(Of Integer)`, вычисление `Await` выражения в `DoSomethingAsync` создает целое число.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-236">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="4f7fe-237">Это показано в этом операторе: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-237">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="4f7fe-238">`startButton_Click` Процедура является примером `Async Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-238">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="4f7fe-239">Поскольку `DoSomethingAsync` — `Async` функции, задача для вызова `DoSomethingAsync` должна быть ожидаемой, как показывает следующая инструкция: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-239">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="4f7fe-240">`startButton_Click``Sub` Процедура должна быть определена с `Async` модификатор из-за `Await` выражение.</span><span class="sxs-lookup"><span data-stu-id="4f7fe-240">The `startButton_Click``Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4f7fe-241">См. также</span><span class="sxs-lookup"><span data-stu-id="4f7fe-241">See Also</span></span>  
 [<span data-ttu-id="4f7fe-242">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="4f7fe-242">Sub Statement</span></span>](sub-statement.md)  
 [<span data-ttu-id="4f7fe-243">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="4f7fe-243">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [<span data-ttu-id="4f7fe-244">Список параметров</span><span class="sxs-lookup"><span data-stu-id="4f7fe-244">Parameter List</span></span>](parameter-list.md)  
 [<span data-ttu-id="4f7fe-245">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="4f7fe-245">Dim Statement</span></span>](dim-statement.md)  
 [<span data-ttu-id="4f7fe-246">Оператор Call</span><span class="sxs-lookup"><span data-stu-id="4f7fe-246">Call Statement</span></span>](call-statement.md)  
 [<span data-ttu-id="4f7fe-247">Of</span><span class="sxs-lookup"><span data-stu-id="4f7fe-247">Of</span></span>](of-clause.md)  
 [<span data-ttu-id="4f7fe-248">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="4f7fe-248">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [<span data-ttu-id="4f7fe-249">Практическое руководство. Использование универсального класса</span><span class="sxs-lookup"><span data-stu-id="4f7fe-249">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="4f7fe-250">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="4f7fe-250">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [<span data-ttu-id="4f7fe-251">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="4f7fe-251">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="4f7fe-252">Выражение функции</span><span class="sxs-lookup"><span data-stu-id="4f7fe-252">Function Expression</span></span>](../../../visual-basic/language-reference/operators/function-expression.md)
