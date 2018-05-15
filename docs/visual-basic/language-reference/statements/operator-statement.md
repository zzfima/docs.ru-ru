---
title: Operator Statement
ms.date: 07/20/2015
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
ms.openlocfilehash: cb7fe7929e4b6e61ca3b39be5615e09182f2fe0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="operator-statement"></a><span data-ttu-id="0257c-102">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="0257c-102">Operator Statement</span></span>
<span data-ttu-id="0257c-103">Объявляет символ оператора, операнды и код, которые определяют процедуру оператора для класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="0257c-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0257c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0257c-104">Syntax</span></span>  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## <a name="parts"></a><span data-ttu-id="0257c-105">Части</span><span class="sxs-lookup"><span data-stu-id="0257c-105">Parts</span></span>  
 `attrlist`  
 <span data-ttu-id="0257c-106">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="0257c-106">Optional.</span></span> <span data-ttu-id="0257c-107">В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="0257c-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `Public`  
 <span data-ttu-id="0257c-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0257c-108">Required.</span></span> <span data-ttu-id="0257c-109">Указывает, что эта процедура оператора [открытый](../../../visual-basic/language-reference/modifiers/public.md) доступа.</span><span class="sxs-lookup"><span data-stu-id="0257c-109">Indicates that this operator procedure has [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span></span>  
  
 `Overloads`  
 <span data-ttu-id="0257c-110">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="0257c-110">Optional.</span></span> <span data-ttu-id="0257c-111">В разделе [перегрузки](../../../visual-basic/language-reference/modifiers/overloads.md).</span><span class="sxs-lookup"><span data-stu-id="0257c-111">See [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span></span>  
  
 `Shared`  
 <span data-ttu-id="0257c-112">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0257c-112">Required.</span></span> <span data-ttu-id="0257c-113">Указывает, что эта процедура оператора [Shared](../../../visual-basic/language-reference/modifiers/shared.md) процедуры.</span><span class="sxs-lookup"><span data-stu-id="0257c-113">Indicates that this operator procedure is a [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span></span>  
  
 `Shadows`  
 <span data-ttu-id="0257c-114">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="0257c-114">Optional.</span></span> <span data-ttu-id="0257c-115">В разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="0257c-115">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
 `Widening`  
 <span data-ttu-id="0257c-116">Требуется для оператора преобразования, если не указать `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="0257c-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="0257c-117">Указывает, что эта процедура оператора определяет [Widening](../../../visual-basic/language-reference/modifiers/widening.md) преобразования.</span><span class="sxs-lookup"><span data-stu-id="0257c-117">Indicates that this operator procedure defines a [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversion.</span></span> <span data-ttu-id="0257c-118">В разделе «Расширяющие и сужающие преобразования» на этой странице справки.</span><span class="sxs-lookup"><span data-stu-id="0257c-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `Narrowing`  
 <span data-ttu-id="0257c-119">Требуется для оператора преобразования, если не указать `Widening`.</span><span class="sxs-lookup"><span data-stu-id="0257c-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="0257c-120">Указывает, что эта процедура оператора определяет [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) преобразования.</span><span class="sxs-lookup"><span data-stu-id="0257c-120">Indicates that this operator procedure defines a [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="0257c-121">В разделе «Расширяющие и сужающие преобразования» на этой странице справки.</span><span class="sxs-lookup"><span data-stu-id="0257c-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `operatorsymbol`  
 <span data-ttu-id="0257c-122">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0257c-122">Required.</span></span> <span data-ttu-id="0257c-123">Символ или идентификатор оператора, который определяет Эта процедура оператора.</span><span class="sxs-lookup"><span data-stu-id="0257c-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>  
  
 `operand1`  
 <span data-ttu-id="0257c-124">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0257c-124">Required.</span></span> <span data-ttu-id="0257c-125">Имя и тип одного операнда унарного оператора (включая оператор преобразования) или левого операнда бинарного оператора.</span><span class="sxs-lookup"><span data-stu-id="0257c-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>  
  
 `operand2`  
 <span data-ttu-id="0257c-126">Требуется для бинарных операторов.</span><span class="sxs-lookup"><span data-stu-id="0257c-126">Required for binary operators.</span></span> <span data-ttu-id="0257c-127">Имя и тип правого операнда бинарного оператора.</span><span class="sxs-lookup"><span data-stu-id="0257c-127">The name and type of the right operand of a binary operator.</span></span>  
  
 <span data-ttu-id="0257c-128">`operand1` и `operand2` имеет следующий синтаксис и компоненты:</span><span class="sxs-lookup"><span data-stu-id="0257c-128">`operand1` and `operand2` have the following syntax and parts:</span></span>  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|<span data-ttu-id="0257c-129">Отделение</span><span class="sxs-lookup"><span data-stu-id="0257c-129">Part</span></span>|<span data-ttu-id="0257c-130">Описание</span><span class="sxs-lookup"><span data-stu-id="0257c-130">Description</span></span>|  
|----------|-----------------|  
|`ByVal`|<span data-ttu-id="0257c-131">Необязательно, но механизм передачи должен быть [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="0257c-131">Optional, but the passing mechanism must be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>|  
|`operandname`|<span data-ttu-id="0257c-132">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0257c-132">Required.</span></span> <span data-ttu-id="0257c-133">Имя переменной, представляющей этот операнд.</span><span class="sxs-lookup"><span data-stu-id="0257c-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="0257c-134">В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="0257c-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`operandtype`|<span data-ttu-id="0257c-135">Необязательный Если `Option Strict` — `On`.</span><span class="sxs-lookup"><span data-stu-id="0257c-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="0257c-136">Тип данных этого операнда.</span><span class="sxs-lookup"><span data-stu-id="0257c-136">Data type of this operand.</span></span>|  
  
 `type`  
 <span data-ttu-id="0257c-137">Необязательный Если `Option Strict` — `On`.</span><span class="sxs-lookup"><span data-stu-id="0257c-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="0257c-138">Возвращает тип данных значения процедура оператора.</span><span class="sxs-lookup"><span data-stu-id="0257c-138">Data type of the value the operator procedure returns.</span></span>  
  
 `statements`  
 <span data-ttu-id="0257c-139">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="0257c-139">Optional.</span></span> <span data-ttu-id="0257c-140">Блок операторов, процедура оператора.</span><span class="sxs-lookup"><span data-stu-id="0257c-140">Block of statements that the operator procedure runs.</span></span>  
  
 `returnvalue`  
 <span data-ttu-id="0257c-141">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0257c-141">Required.</span></span> <span data-ttu-id="0257c-142">Значение, которое процедура оператора возвращает в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="0257c-142">The value that the operator procedure returns to the calling code.</span></span>  
  
 <span data-ttu-id="0257c-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="0257c-143">`End` `Operator`</span></span>  
 <span data-ttu-id="0257c-144">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0257c-144">Required.</span></span> <span data-ttu-id="0257c-145">Завершает определение данной процедуры оператора.</span><span class="sxs-lookup"><span data-stu-id="0257c-145">Terminates the definition of this operator procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0257c-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="0257c-146">Remarks</span></span>  
 <span data-ttu-id="0257c-147">Можно использовать `Operator` только в классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="0257c-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="0257c-148">Это означает *контекст объявления* оператор не может быть исходный файл, пространство имен, модуля, интерфейса, процедуры или блока.</span><span class="sxs-lookup"><span data-stu-id="0257c-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="0257c-149">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0257c-149">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="0257c-150">Все операторы должны быть `Public Shared`.</span><span class="sxs-lookup"><span data-stu-id="0257c-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="0257c-151">Нельзя указать `ByRef`, `Optional`, или `ParamArray` для любой из операндов.</span><span class="sxs-lookup"><span data-stu-id="0257c-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>  
  
 <span data-ttu-id="0257c-152">Нельзя использовать символ оператора или идентификатор для хранения возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="0257c-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="0257c-153">Необходимо использовать `Return` оператор, который необходимо указать значение.</span><span class="sxs-lookup"><span data-stu-id="0257c-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="0257c-154">Любое количество `Return` операторы могут использоваться в любом месте в процедуре.</span><span class="sxs-lookup"><span data-stu-id="0257c-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>  
  
 <span data-ttu-id="0257c-155">Определение оператора таким образом называется *перегрузка операторов*, независимо от того, имеется ли вы использовать `Overloads` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="0257c-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="0257c-156">В приведенной ниже таблице перечислены операторы, которые можно определить.</span><span class="sxs-lookup"><span data-stu-id="0257c-156">The following table lists the operators you can define.</span></span>  
  
|<span data-ttu-id="0257c-157">Тип</span><span class="sxs-lookup"><span data-stu-id="0257c-157">Type</span></span>|<span data-ttu-id="0257c-158">Операторы</span><span class="sxs-lookup"><span data-stu-id="0257c-158">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="0257c-159">Унарный</span><span class="sxs-lookup"><span data-stu-id="0257c-159">Unary</span></span>|<span data-ttu-id="0257c-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="0257c-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="0257c-161">Binary</span><span class="sxs-lookup"><span data-stu-id="0257c-161">Binary</span></span>|<span data-ttu-id="0257c-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="0257c-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="0257c-163">Преобразование (унарный)</span><span class="sxs-lookup"><span data-stu-id="0257c-163">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="0257c-164">Обратите внимание, что `=` в списке бинарных является оператором сравнения, не оператором присваивания.</span><span class="sxs-lookup"><span data-stu-id="0257c-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="0257c-165">При определении `CType`, необходимо указать либо `Widening` или `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="0257c-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>  
  
## <a name="matched-pairs"></a><span data-ttu-id="0257c-166">Совпадающие пары</span><span class="sxs-lookup"><span data-stu-id="0257c-166">Matched Pairs</span></span>  
 <span data-ttu-id="0257c-167">Необходимо определить определенные операторы как пары.</span><span class="sxs-lookup"><span data-stu-id="0257c-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="0257c-168">Если определен один оператор такой пары, необходимо определить другой.</span><span class="sxs-lookup"><span data-stu-id="0257c-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="0257c-169">Ниже перечислены соответствующие пары.</span><span class="sxs-lookup"><span data-stu-id="0257c-169">The matched pairs are the following:</span></span>  
  
-   <span data-ttu-id="0257c-170">`=` и `<>`</span><span class="sxs-lookup"><span data-stu-id="0257c-170">`=` and `<>`</span></span>  
  
-   <span data-ttu-id="0257c-171">`>` и `<`</span><span class="sxs-lookup"><span data-stu-id="0257c-171">`>` and `<`</span></span>  
  
-   <span data-ttu-id="0257c-172">`>=` и `<=`</span><span class="sxs-lookup"><span data-stu-id="0257c-172">`>=` and `<=`</span></span>  
  
-   <span data-ttu-id="0257c-173">`IsTrue` и `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="0257c-173">`IsTrue` and `IsFalse`</span></span>  
  
## <a name="data-type-restrictions"></a><span data-ttu-id="0257c-174">Ограничения типа данных</span><span class="sxs-lookup"><span data-stu-id="0257c-174">Data Type Restrictions</span></span>  
 <span data-ttu-id="0257c-175">Каждый оператор должен включать класса или структуры, в которой вы его определяете.</span><span class="sxs-lookup"><span data-stu-id="0257c-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="0257c-176">Это означает, что класс или структура должно отображаться как тип данных из следующих:</span><span class="sxs-lookup"><span data-stu-id="0257c-176">This means that the class or structure must appear as the data type of the following:</span></span>  
  
-   <span data-ttu-id="0257c-177">Операнд унарного оператора.</span><span class="sxs-lookup"><span data-stu-id="0257c-177">The operand of a unary operator.</span></span>  
  
-   <span data-ttu-id="0257c-178">По крайней мере один из операндов бинарного оператора.</span><span class="sxs-lookup"><span data-stu-id="0257c-178">At least one of the operands of a binary operator.</span></span>  
  
-   <span data-ttu-id="0257c-179">Операнд или тип возвращаемого значения оператора преобразования.</span><span class="sxs-lookup"><span data-stu-id="0257c-179">Either the operand or the return type of a conversion operator.</span></span>  
  
 <span data-ttu-id="0257c-180">Некоторые операторы имеют дополнительные ограничения типа данных, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="0257c-180">Certain operators have additional data type restrictions, as follows:</span></span>  
  
-   <span data-ttu-id="0257c-181">Если определить `IsTrue` и `IsFalse` операторов, они должны оба возвращать `Boolean` типа.</span><span class="sxs-lookup"><span data-stu-id="0257c-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>  
  
-   <span data-ttu-id="0257c-182">Если определить `<<` и `>>` операторы, их необходимо указать `Integer` тип для `operandtype` из `operand2`.</span><span class="sxs-lookup"><span data-stu-id="0257c-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>  
  
 <span data-ttu-id="0257c-183">Для соответствия типу одного из операндов имеет тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="0257c-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="0257c-184">Например, оператор сравнения, такие как `=` или `<>` может возвращать `Boolean` даже если оба операнда являются `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="0257c-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>  
  
## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="0257c-185">Логические и битовые операторы</span><span class="sxs-lookup"><span data-stu-id="0257c-185">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="0257c-186">`And`, `Or`, `Not`, И `Xor` операторы могут выполнять либо логические или битовые операции в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0257c-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="0257c-187">Тем не менее если определить один из этих операторов в классе или структуре, можно определить только его побитовую операцию.</span><span class="sxs-lookup"><span data-stu-id="0257c-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>  
  
 <span data-ttu-id="0257c-188">Невозможно определить `AndAlso` оператор непосредственно с `Operator` инструкции.</span><span class="sxs-lookup"><span data-stu-id="0257c-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="0257c-189">Тем не менее, можно использовать `AndAlso` Если выполнены следующие условия:</span><span class="sxs-lookup"><span data-stu-id="0257c-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>  
  
-   <span data-ttu-id="0257c-190">Вы определили `And` с теми же типами операнд, который вы хотите использовать для `AndAlso`.</span><span class="sxs-lookup"><span data-stu-id="0257c-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>  
  
-   <span data-ttu-id="0257c-191">Определение `And` возвращает совпадает с типом класса или структуры, на котором оно было настроено.</span><span class="sxs-lookup"><span data-stu-id="0257c-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>  
  
-   <span data-ttu-id="0257c-192">Вы определили `IsFalse` оператор в классе или структуре, на котором вы определили `And`.</span><span class="sxs-lookup"><span data-stu-id="0257c-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>  
  
 <span data-ttu-id="0257c-193">Аналогично, можно использовать `OrElse` Если вы определили `Or` на теми же операндами определили с возвращаемым типом класса или структуры, и `IsTrue` для класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="0257c-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>  
  
## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="0257c-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="0257c-194">Widening and Narrowing Conversions</span></span>  
 <span data-ttu-id="0257c-195">A *расширяющее преобразование* всегда успешно во время выполнения, хотя *сужающее преобразование* могут вызвать сбой во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0257c-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="0257c-196">Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="0257c-196">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
 <span data-ttu-id="0257c-197">При объявлении процедуры преобразования быть `Widening`, ваш код процедуры не должен давать сбои.</span><span class="sxs-lookup"><span data-stu-id="0257c-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="0257c-198">Это означает следующее.</span><span class="sxs-lookup"><span data-stu-id="0257c-198">This means the following:</span></span>  
  
-   <span data-ttu-id="0257c-199">Оно должно всегда возвращать допустимое значение типа `type`.</span><span class="sxs-lookup"><span data-stu-id="0257c-199">It must always return a valid value of type `type`.</span></span>  
  
-   <span data-ttu-id="0257c-200">Он должен обрабатывать все возможные исключения и другие условия возникновения ошибок.</span><span class="sxs-lookup"><span data-stu-id="0257c-200">It must handle all possible exceptions and other error conditions.</span></span>  
  
-   <span data-ttu-id="0257c-201">Он должен обрабатывать любую ошибку, возвращаемую из любой процедуры, которые она вызывает.</span><span class="sxs-lookup"><span data-stu-id="0257c-201">It must handle any error returns from any procedures it calls.</span></span>  
  
 <span data-ttu-id="0257c-202">Если есть вероятность того, что процедуры преобразования не может завершиться успешно, или что он может вызвать необработанное исключение, необходимо объявить ее `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="0257c-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0257c-203">Пример</span><span class="sxs-lookup"><span data-stu-id="0257c-203">Example</span></span>  
 <span data-ttu-id="0257c-204">Следующий пример кода использует `Operator` инструкции для определения контура структуры, которая включает в себя процедуры оператора `And`, `Or`, `IsFalse`, и `IsTrue` операторы.</span><span class="sxs-lookup"><span data-stu-id="0257c-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="0257c-205">`And` и `Or` каждый из которых принимает два операнда типа `abc` и тип возвращаемого значения `abc`.</span><span class="sxs-lookup"><span data-stu-id="0257c-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="0257c-206">`IsFalse` и `IsTrue` каждый из которых принимает один операнд типа `abc` и возвращают `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="0257c-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="0257c-207">Эти определения позволяют вызывающий код, чтобы использовать `And`, `AndAlso`, `Or`, и `OrElse` с операндами типа `abc`.</span><span class="sxs-lookup"><span data-stu-id="0257c-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>  
  
 [!code-vb[VbVbalrStatements#44](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/operator-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0257c-208">См. также</span><span class="sxs-lookup"><span data-stu-id="0257c-208">See Also</span></span>  
 [<span data-ttu-id="0257c-209">Оператор IsFalse</span><span class="sxs-lookup"><span data-stu-id="0257c-209">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [<span data-ttu-id="0257c-210">Оператор IsTrue</span><span class="sxs-lookup"><span data-stu-id="0257c-210">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [<span data-ttu-id="0257c-211">Расширение</span><span class="sxs-lookup"><span data-stu-id="0257c-211">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="0257c-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="0257c-212">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="0257c-213">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="0257c-213">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="0257c-214">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="0257c-214">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="0257c-215">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="0257c-215">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="0257c-216">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="0257c-216">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="0257c-217">Практическое руководство. Вызов процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="0257c-217">How to: Call an Operator Procedure</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="0257c-218">Практическое руководство. Использование класса, в котором определяются операторы</span><span class="sxs-lookup"><span data-stu-id="0257c-218">How to: Use a Class that Defines Operators</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
