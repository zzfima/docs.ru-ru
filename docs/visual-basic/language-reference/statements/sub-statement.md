---
title: Оператор Sub (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
caps.latest.revision: 52
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0a2d0d5ffdca857a3a5ca58cd38b0930f254526f
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2017
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="de0d9-102">Оператор Sub (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de0d9-102">Sub Statement (Visual Basic)</span></span>
<span data-ttu-id="de0d9-103">Объявляет имя, параметры и код, определяющие `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="de0d9-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de0d9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de0d9-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]  
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Sub ]  
    [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="de0d9-105">Части</span><span class="sxs-lookup"><span data-stu-id="de0d9-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="de0d9-106">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="de0d9-106">Optional.</span></span> <span data-ttu-id="de0d9-107">В разделе [список атрибутов](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="de0d9-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `Partial`  
  
     <span data-ttu-id="de0d9-108">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="de0d9-108">Optional.</span></span> <span data-ttu-id="de0d9-109">Указывает определение разделяемого метода.</span><span class="sxs-lookup"><span data-stu-id="de0d9-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="de0d9-110">В разделе [разделяемые методы](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="de0d9-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="de0d9-111">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="de0d9-111">Optional.</span></span> <span data-ttu-id="de0d9-112">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="de0d9-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="de0d9-113">Public</span><span class="sxs-lookup"><span data-stu-id="de0d9-113">Public</span></span>](../modifiers/public.md)  
  
    -   [<span data-ttu-id="de0d9-114">Protected</span><span class="sxs-lookup"><span data-stu-id="de0d9-114">Protected</span></span>](../modifiers/protected.md)  
  
    -   [<span data-ttu-id="de0d9-115">Friend</span><span class="sxs-lookup"><span data-stu-id="de0d9-115">Friend</span></span>](../modifiers/friend.md)  
  
    -   [<span data-ttu-id="de0d9-116">Закрытые</span><span class="sxs-lookup"><span data-stu-id="de0d9-116">Private</span></span>](../modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="de0d9-117">В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="de0d9-117">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="de0d9-118">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="de0d9-118">Optional.</span></span> <span data-ttu-id="de0d9-119">Ниже указаны доступные значения.</span><span class="sxs-lookup"><span data-stu-id="de0d9-119">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="de0d9-120">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="de0d9-120">Overloads</span></span>](../modifiers/overloads.md)  
  
    -   [<span data-ttu-id="de0d9-121">Переопределения</span><span class="sxs-lookup"><span data-stu-id="de0d9-121">Overrides</span></span>](../modifiers/overrides.md)  
  
    -   [<span data-ttu-id="de0d9-122">Переопределяемые</span><span class="sxs-lookup"><span data-stu-id="de0d9-122">Overridable</span></span>](../modifiers/overridable.md)  
  
    -   [<span data-ttu-id="de0d9-123">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="de0d9-123">NotOverridable</span></span>](../modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="de0d9-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="de0d9-124">MustOverride</span></span>](../modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="de0d9-125">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="de0d9-125">Optional.</span></span> <span data-ttu-id="de0d9-126">В разделе [общих](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="de0d9-126">See [Shared](../modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="de0d9-127">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="de0d9-127">Optional.</span></span> <span data-ttu-id="de0d9-128">В разделе [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="de0d9-128">See [Shadows](../modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="de0d9-129">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="de0d9-129">Optional.</span></span> <span data-ttu-id="de0d9-130">В разделе [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="de0d9-130">See [Async](../modifiers/async.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="de0d9-131">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="de0d9-131">Required.</span></span> <span data-ttu-id="de0d9-132">Имя процедуры.</span><span class="sxs-lookup"><span data-stu-id="de0d9-132">Name of the procedure.</span></span> <span data-ttu-id="de0d9-133">В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="de0d9-133">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="de0d9-134">Чтобы создать процедуру конструктора для класса, задайте имя `Sub` процедура `New` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="de0d9-134">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="de0d9-135">Дополнительные сведения см. в разделе [время существования объекта: как объекты, создание и удаление](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="de0d9-135">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="de0d9-136">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="de0d9-136">Optional.</span></span> <span data-ttu-id="de0d9-137">Список параметров типа для универсальной процедуры.</span><span class="sxs-lookup"><span data-stu-id="de0d9-137">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="de0d9-138">В разделе [введите список](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="de0d9-138">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="de0d9-139">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="de0d9-139">Optional.</span></span> <span data-ttu-id="de0d9-140">Список имен локальных переменных, представляющих параметры этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="de0d9-140">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="de0d9-141">В разделе [список параметров](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="de0d9-141">See [Parameter List](parameter-list.md).</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="de0d9-142">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="de0d9-142">Optional.</span></span> <span data-ttu-id="de0d9-143">Указывает, что эта процедура реализует один или несколько `Sub` процедуры, каждая из которых определена в интерфейс, реализуемый этой процедуры классом или структурой.</span><span class="sxs-lookup"><span data-stu-id="de0d9-143">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="de0d9-144">В разделе [реализует оператор](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="de0d9-144">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="de0d9-145">Является обязательным, если предоставлен параметр `Implements`.</span><span class="sxs-lookup"><span data-stu-id="de0d9-145">Required if `Implements` is supplied.</span></span> <span data-ttu-id="de0d9-146">Список реализуемых процедур `Sub`.</span><span class="sxs-lookup"><span data-stu-id="de0d9-146">List of `Sub` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="de0d9-147">Каждый элемент `implementedprocedure` имеет перечисленные ниже синтаксис и компоненты.</span><span class="sxs-lookup"><span data-stu-id="de0d9-147">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="de0d9-148">Отделение</span><span class="sxs-lookup"><span data-stu-id="de0d9-148">Part</span></span>|<span data-ttu-id="de0d9-149">Описание</span><span class="sxs-lookup"><span data-stu-id="de0d9-149">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="de0d9-150">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="de0d9-150">Required.</span></span> <span data-ttu-id="de0d9-151">Имя интерфейса, реализуемого данной процедурой, содержащего класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="de0d9-151">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="de0d9-152">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="de0d9-152">Required.</span></span> <span data-ttu-id="de0d9-153">Имя, под которым процедура определена в `interface`.</span><span class="sxs-lookup"><span data-stu-id="de0d9-153">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="de0d9-154">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="de0d9-154">Optional.</span></span> <span data-ttu-id="de0d9-155">Указывает, что эта процедура может обрабатывать одно или несколько конкретных событий.</span><span class="sxs-lookup"><span data-stu-id="de0d9-155">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="de0d9-156">В разделе [обрабатывает](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="de0d9-156">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="de0d9-157">Является обязательным, если предоставлен параметр `Handles`.</span><span class="sxs-lookup"><span data-stu-id="de0d9-157">Required if `Handles` is supplied.</span></span> <span data-ttu-id="de0d9-158">Список событий, которые обрабатывает данная процедура.</span><span class="sxs-lookup"><span data-stu-id="de0d9-158">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="de0d9-159">Каждый элемент `eventspecifier` имеет перечисленные ниже синтаксис и компоненты.</span><span class="sxs-lookup"><span data-stu-id="de0d9-159">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="de0d9-160">Отделение</span><span class="sxs-lookup"><span data-stu-id="de0d9-160">Part</span></span>|<span data-ttu-id="de0d9-161">Описание</span><span class="sxs-lookup"><span data-stu-id="de0d9-161">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="de0d9-162">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="de0d9-162">Required.</span></span> <span data-ttu-id="de0d9-163">Объектная переменная объявлена с типом данных класса или структуры, который инициирует событие.</span><span class="sxs-lookup"><span data-stu-id="de0d9-163">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="de0d9-164">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="de0d9-164">Required.</span></span> <span data-ttu-id="de0d9-165">Имя события, которое обрабатывает данная процедура.</span><span class="sxs-lookup"><span data-stu-id="de0d9-165">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="de0d9-166">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="de0d9-166">Optional.</span></span> <span data-ttu-id="de0d9-167">Блок операторов для работы в рамках этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="de0d9-167">Block of statements to run within this procedure.</span></span>  
  
-   `End Sub`  
  
     <span data-ttu-id="de0d9-168">Завершает определение данной процедуры.</span><span class="sxs-lookup"><span data-stu-id="de0d9-168">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de0d9-169">Примечания</span><span class="sxs-lookup"><span data-stu-id="de0d9-169">Remarks</span></span>  
 <span data-ttu-id="de0d9-170">Весь исполняемый код должен быть внутри процедуры.</span><span class="sxs-lookup"><span data-stu-id="de0d9-170">All executable code must be inside a procedure.</span></span> <span data-ttu-id="de0d9-171">Используйте `Sub` процедуру, когда не требуется возвращать значение вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="de0d9-171">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="de0d9-172">Используйте `Function` процедуру, когда требуется вернуть значение.</span><span class="sxs-lookup"><span data-stu-id="de0d9-172">Use a `Function` procedure when you want to return a value.</span></span>  
  
## <a name="defining-a-sub-procedure"></a><span data-ttu-id="de0d9-173">Определение процедуры Sub</span><span class="sxs-lookup"><span data-stu-id="de0d9-173">Defining a Sub Procedure</span></span>  
 <span data-ttu-id="de0d9-174">Можно определить `Sub` процедуры только на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="de0d9-174">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="de0d9-175">Контекст объявления подпроцедуры таким образом, должен быть класс, структура, модуль или интерфейс и не может быть исходным файлом, пространство имен, процедура или блок.</span><span class="sxs-lookup"><span data-stu-id="de0d9-175">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="de0d9-176">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="de0d9-176">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="de0d9-177">`Sub`процедуры по умолчанию для общего доступа.</span><span class="sxs-lookup"><span data-stu-id="de0d9-177">`Sub` procedures default to public access.</span></span> <span data-ttu-id="de0d9-178">Уровни доступа можно настроить с помощью модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="de0d9-178">You can adjust their access levels by using the access modifiers.</span></span>  
  
 <span data-ttu-id="de0d9-179">Если в процедуре используется `Implements` ключевое слово, содержащего класса или структуры, должен иметь `Implements` оператор, который следует сразу за его `Class` или `Structure` инструкции.</span><span class="sxs-lookup"><span data-stu-id="de0d9-179">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="de0d9-180">`Implements` Инструкция должна включать каждого интерфейса, который указан в `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="de0d9-180">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="de0d9-181">Тем не менее имя, по которому интерфейс определяет `Sub` (в `definedname`) не должен совпадать с именем этой процедуры (в `name`).</span><span class="sxs-lookup"><span data-stu-id="de0d9-181">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>  
  
## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="de0d9-182">Возвращение из процедуры Sub</span><span class="sxs-lookup"><span data-stu-id="de0d9-182">Returning from a Sub Procedure</span></span>  
 <span data-ttu-id="de0d9-183">Когда `Sub` процедура возвращает в вызывающий код, выполнение продолжается с оператора после инструкции, который вызвал его.</span><span class="sxs-lookup"><span data-stu-id="de0d9-183">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>  
  
 <span data-ttu-id="de0d9-184">В следующем примере показан возврат из `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="de0d9-184">The following example shows a return from a `Sub` procedure.</span></span>  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 <span data-ttu-id="de0d9-185">`Exit Sub` И `Return` инструкции вызывают Немедленный выход из `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="de0d9-185">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="de0d9-186">Любое количество `Exit Sub` и `Return` операторы могут использоваться в любом месте в процедуре, и могут быть использованы смешанные `Exit Sub` и `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="de0d9-186">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>  
  
## <a name="calling-a-sub-procedure"></a><span data-ttu-id="de0d9-187">Вызов процедуры Sub</span><span class="sxs-lookup"><span data-stu-id="de0d9-187">Calling a Sub Procedure</span></span>  
 <span data-ttu-id="de0d9-188">Вызывается `Sub` процедуры с помощью имени процедуры в инструкции и затем согласно этим именем его список аргументов, заключенный в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="de0d9-188">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="de0d9-189">Круглые скобки можно опустить только в том случае, если никакие аргументы не передаются.</span><span class="sxs-lookup"><span data-stu-id="de0d9-189">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="de0d9-190">Тем не менее код является более удобочитаемым, если всегда использовать круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="de0d9-190">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="de0d9-191">Объект `Sub` процедуры и `Function` процедуры могут содержать параметры и выполнять последовательность операторов.</span><span class="sxs-lookup"><span data-stu-id="de0d9-191">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="de0d9-192">Тем не менее `Function` процедура возвращает значение, а также `Sub` не процедуры.</span><span class="sxs-lookup"><span data-stu-id="de0d9-192">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="de0d9-193">Следовательно, нельзя использовать `Sub` процедуры в выражении.</span><span class="sxs-lookup"><span data-stu-id="de0d9-193">Therefore, you can't use a `Sub` procedure in an expression.</span></span>  
  
 <span data-ttu-id="de0d9-194">Можно использовать `Call` ключевое слово, при вызове `Sub` процедура, но его не рекомендуется для большинства случаев.</span><span class="sxs-lookup"><span data-stu-id="de0d9-194">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="de0d9-195">Дополнительные сведения см. в разделе [инструкции Call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="de0d9-195">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="de0d9-196">Visual Basic иногда упорядочение арифметические выражения для повышения внутренней эффективности.</span><span class="sxs-lookup"><span data-stu-id="de0d9-196">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="de0d9-197">По этой причине если ваш список аргументов включает выражения, вызывающие другие процедуры не следует предполагается, что эти выражения будет вызываться в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="de0d9-197">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>  
  
## <a name="async-sub-procedures"></a><span data-ttu-id="de0d9-198">Async Sub-процедуры</span><span class="sxs-lookup"><span data-stu-id="de0d9-198">Async Sub Procedures</span></span>  
 <span data-ttu-id="de0d9-199">С помощью функции Async можно вызывать асинхронные функции без использованию явных обратных вызовов или ручному разделению кода между несколькими функции или лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="de0d9-199">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="de0d9-200">Если пометить процедуры с [Async](../modifiers/async.md) модификатор, можно использовать [Await](../../../visual-basic/language-reference/operators/await-operator.md) оператор в процедуре.</span><span class="sxs-lookup"><span data-stu-id="de0d9-200">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="de0d9-201">Когда управление достигает `Await` выражения в `Async` процедуры, управление возвращается вызывающему объекту и выполнение в процедуре приостанавливается до завершения выполнения ожидающей задачи.</span><span class="sxs-lookup"><span data-stu-id="de0d9-201">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="de0d9-202">После завершения задачи можно возобновить выполнение в процедуре.</span><span class="sxs-lookup"><span data-stu-id="de0d9-202">When the task is complete, execution can resume in the procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de0d9-203">`Async` Процедура возвращает вызывающий объект при обнаружении либо первый ожидаемый объект, пока не завершена или в конце `Async` достигается процедуры, какое событие происходит раньше.</span><span class="sxs-lookup"><span data-stu-id="de0d9-203">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>  
  
 <span data-ttu-id="de0d9-204">Можно также пометить [Function, инструкция](function-statement.md) с `Async` модификатор.</span><span class="sxs-lookup"><span data-stu-id="de0d9-204">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="de0d9-205">`Async` Функция может иметь тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> или <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="de0d9-205">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="de0d9-206">Пример далее в этом разделе показано, `Async` функции, которая имеет тип возвращаемого значения <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="de0d9-206">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="de0d9-207">`Async``Sub` процедуры в основном используются для обработчиков событий, где не может быть возвращено значение.</span><span class="sxs-lookup"><span data-stu-id="de0d9-207">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="de0d9-208">`Async``Sub` Процедуру нельзя ожидать и код, вызывающий `Async``Sub` процедуры не могут перехватывать исключения, `Sub` процедура вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="de0d9-208">An `Async``Sub` procedure can't be awaited, and the caller of an `Async``Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>  
  
 <span data-ttu-id="de0d9-209">`Async` Процедура не может объявить все [ByRef](../modifiers/byref.md) параметров.</span><span class="sxs-lookup"><span data-stu-id="de0d9-209">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="de0d9-210">Дополнительные сведения о `Async` процедуры см. в разделе [асинхронное программирование с использованием ключевых слов Async и Await](../../../visual-basic/programming-guide/concepts/async/index.md), [поток управления в асинхронных программах](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), и [асинхронные типы возвращаемых значений](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="de0d9-210">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="de0d9-211">Пример</span><span class="sxs-lookup"><span data-stu-id="de0d9-211">Example</span></span>  
 <span data-ttu-id="de0d9-212">В следующем примере используется `Sub` инструкции для определения имени, параметров и кода, образующих текст `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="de0d9-212">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#58](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="de0d9-213">Пример</span><span class="sxs-lookup"><span data-stu-id="de0d9-213">Example</span></span>  
 <span data-ttu-id="de0d9-214">В следующем примере `DelayAsync` — `Async``Function` с типом возвращаемого значения <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="de0d9-214">In the following example, `DelayAsync` is an `Async``Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="de0d9-215">`DelayAsync` имеет инструкцию `Return`, которая возвращает целое число.</span><span class="sxs-lookup"><span data-stu-id="de0d9-215">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="de0d9-216">Таким образом, объявление функции `DelayAsync` должен иметь тип возвращаемого значения `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="de0d9-216">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="de0d9-217">Так как возвращаемый тип — `Task(Of Integer)`, вычисление `Await` выражения в `DoSomethingAsync` создает целое число, как показывает следующая инструкция: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="de0d9-217">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="de0d9-218">`startButton_Click` Процедура является примером `Async Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="de0d9-218">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="de0d9-219">Поскольку `DoSomethingAsync` — `Async` функции, задача для вызова `DoSomethingAsync` должна быть ожидаемой, как показывает следующая инструкция: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="de0d9-219">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="de0d9-220">`startButton_Click``Sub` Процедура должна быть определена с `Async` модификатор из-за `Await` выражение.</span><span class="sxs-lookup"><span data-stu-id="de0d9-220">The `startButton_Click``Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="de0d9-221">См. также</span><span class="sxs-lookup"><span data-stu-id="de0d9-221">See Also</span></span>  
 [<span data-ttu-id="de0d9-222">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="de0d9-222">Implements Statement</span></span>](implements-statement.md)  
 [<span data-ttu-id="de0d9-223">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="de0d9-223">Function Statement</span></span>](function-statement.md)  
 [<span data-ttu-id="de0d9-224">Список параметров</span><span class="sxs-lookup"><span data-stu-id="de0d9-224">Parameter List</span></span>](parameter-list.md)  
 [<span data-ttu-id="de0d9-225">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="de0d9-225">Dim Statement</span></span>](dim-statement.md)  
 [<span data-ttu-id="de0d9-226">Оператор Call</span><span class="sxs-lookup"><span data-stu-id="de0d9-226">Call Statement</span></span>](call-statement.md)  
 [<span data-ttu-id="de0d9-227">Of</span><span class="sxs-lookup"><span data-stu-id="de0d9-227">Of</span></span>](of-clause.md)  
 [<span data-ttu-id="de0d9-228">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="de0d9-228">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [<span data-ttu-id="de0d9-229">Практическое руководство. Использование универсального класса</span><span class="sxs-lookup"><span data-stu-id="de0d9-229">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="de0d9-230">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="de0d9-230">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [<span data-ttu-id="de0d9-231">Разделяемые методы</span><span class="sxs-lookup"><span data-stu-id="de0d9-231">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
