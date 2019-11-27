---
title: Оператор Operator
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
ms.openlocfilehash: aa6ae3977977ded05e47d12dabe72f09251f262d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353798"
---
# <a name="operator-statement"></a><span data-ttu-id="98ab7-102">Оператор Operator</span><span class="sxs-lookup"><span data-stu-id="98ab7-102">Operator Statement</span></span>

<span data-ttu-id="98ab7-103">Объявляет символ оператора, операнды и код, определяющие процедуру оператора для класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="98ab7-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="98ab7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98ab7-104">Syntax</span></span>

```vb
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]
    [ statements ]
    [ statements ]
    Return returnvalue
    [ statements ]
End Operator
```

## <a name="parts"></a><span data-ttu-id="98ab7-105">Части</span><span class="sxs-lookup"><span data-stu-id="98ab7-105">Parts</span></span>

`attrlist`  
<span data-ttu-id="98ab7-106">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="98ab7-106">Optional.</span></span> <span data-ttu-id="98ab7-107">См. [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="98ab7-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>

`Public`  
<span data-ttu-id="98ab7-108">Обязательное.</span><span class="sxs-lookup"><span data-stu-id="98ab7-108">Required.</span></span> <span data-ttu-id="98ab7-109">Указывает, что эта процедура оператора имеет [открытый](../../../visual-basic/language-reference/modifiers/public.md) доступ.</span><span class="sxs-lookup"><span data-stu-id="98ab7-109">Indicates that this operator procedure has [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span></span>

`Overloads`  
<span data-ttu-id="98ab7-110">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="98ab7-110">Optional.</span></span> <span data-ttu-id="98ab7-111">См. раздел [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span><span class="sxs-lookup"><span data-stu-id="98ab7-111">See [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span></span>

`Shared`  
<span data-ttu-id="98ab7-112">Обязательное.</span><span class="sxs-lookup"><span data-stu-id="98ab7-112">Required.</span></span> <span data-ttu-id="98ab7-113">Указывает, что эта процедура оператора является [общей](../../../visual-basic/language-reference/modifiers/shared.md) процедурой.</span><span class="sxs-lookup"><span data-stu-id="98ab7-113">Indicates that this operator procedure is a [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span></span>

`Shadows`  
<span data-ttu-id="98ab7-114">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="98ab7-114">Optional.</span></span> <span data-ttu-id="98ab7-115">См. раздел [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="98ab7-115">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

`Widening`  
<span data-ttu-id="98ab7-116">Требуется для оператора преобразования, если не указано `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="98ab7-117">Указывает, что эта процедура оператора определяет [расширяющее](../../../visual-basic/language-reference/modifiers/widening.md) преобразование.</span><span class="sxs-lookup"><span data-stu-id="98ab7-117">Indicates that this operator procedure defines a [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversion.</span></span> <span data-ttu-id="98ab7-118">См. раздел "расширяющие и сужающие преобразования" на этой странице справки.</span><span class="sxs-lookup"><span data-stu-id="98ab7-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`Narrowing`  
<span data-ttu-id="98ab7-119">Требуется для оператора преобразования, если не указано `Widening`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="98ab7-120">Указывает, что эта процедура оператора определяет [понижающие](../../../visual-basic/language-reference/modifiers/narrowing.md) преобразования.</span><span class="sxs-lookup"><span data-stu-id="98ab7-120">Indicates that this operator procedure defines a [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="98ab7-121">См. раздел "расширяющие и сужающие преобразования" на этой странице справки.</span><span class="sxs-lookup"><span data-stu-id="98ab7-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`operatorsymbol`  
<span data-ttu-id="98ab7-122">Обязательное.</span><span class="sxs-lookup"><span data-stu-id="98ab7-122">Required.</span></span> <span data-ttu-id="98ab7-123">Символ или идентификатор оператора, определяемого данной процедурой оператора.</span><span class="sxs-lookup"><span data-stu-id="98ab7-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>

`operand1`  
<span data-ttu-id="98ab7-124">Обязательное.</span><span class="sxs-lookup"><span data-stu-id="98ab7-124">Required.</span></span> <span data-ttu-id="98ab7-125">Имя и тип одного операнда унарного оператора (включая оператор преобразования) или левого операнда бинарного оператора.</span><span class="sxs-lookup"><span data-stu-id="98ab7-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>

`operand2`  
<span data-ttu-id="98ab7-126">Требуется для бинарных операторов.</span><span class="sxs-lookup"><span data-stu-id="98ab7-126">Required for binary operators.</span></span> <span data-ttu-id="98ab7-127">Имя и тип правого операнда бинарного оператора.</span><span class="sxs-lookup"><span data-stu-id="98ab7-127">The name and type of the right operand of a binary operator.</span></span>

<span data-ttu-id="98ab7-128">`operand1` и `operand2` имеют следующие синтаксис и части:</span><span class="sxs-lookup"><span data-stu-id="98ab7-128">`operand1` and `operand2` have the following syntax and parts:</span></span>

`[ ByVal ] operandname [ As operandtype ]`

|<span data-ttu-id="98ab7-129">Отделение</span><span class="sxs-lookup"><span data-stu-id="98ab7-129">Part</span></span>|<span data-ttu-id="98ab7-130">Описание</span><span class="sxs-lookup"><span data-stu-id="98ab7-130">Description</span></span>|
|----------|-----------------|
|`ByVal`|<span data-ttu-id="98ab7-131">Необязательно, но механизм передачи должен быть [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="98ab7-131">Optional, but the passing mechanism must be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>|
|`operandname`|<span data-ttu-id="98ab7-132">Обязательное.</span><span class="sxs-lookup"><span data-stu-id="98ab7-132">Required.</span></span> <span data-ttu-id="98ab7-133">Имя переменной, представляющей этот операнд.</span><span class="sxs-lookup"><span data-stu-id="98ab7-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="98ab7-134">См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="98ab7-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
|`operandtype`|<span data-ttu-id="98ab7-135">Необязательно, если не `On``Option Strict`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="98ab7-136">Тип данных этого операнда.</span><span class="sxs-lookup"><span data-stu-id="98ab7-136">Data type of this operand.</span></span>|

`type`  
<span data-ttu-id="98ab7-137">Необязательно, если не `On``Option Strict`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="98ab7-138">Тип данных значения, возвращаемого процедурой оператора.</span><span class="sxs-lookup"><span data-stu-id="98ab7-138">Data type of the value the operator procedure returns.</span></span>

`statements`  
<span data-ttu-id="98ab7-139">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="98ab7-139">Optional.</span></span> <span data-ttu-id="98ab7-140">Блок инструкций, выполняемых процедурой оператора.</span><span class="sxs-lookup"><span data-stu-id="98ab7-140">Block of statements that the operator procedure runs.</span></span>

`returnvalue`  
<span data-ttu-id="98ab7-141">Обязательное.</span><span class="sxs-lookup"><span data-stu-id="98ab7-141">Required.</span></span> <span data-ttu-id="98ab7-142">Значение, возвращаемое процедурой оператора в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="98ab7-142">The value that the operator procedure returns to the calling code.</span></span>

<span data-ttu-id="98ab7-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="98ab7-143">`End` `Operator`</span></span>  
<span data-ttu-id="98ab7-144">Обязательное.</span><span class="sxs-lookup"><span data-stu-id="98ab7-144">Required.</span></span> <span data-ttu-id="98ab7-145">Завершает определение этой процедуры оператора.</span><span class="sxs-lookup"><span data-stu-id="98ab7-145">Terminates the definition of this operator procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="98ab7-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="98ab7-146">Remarks</span></span>

<span data-ttu-id="98ab7-147">`Operator` можно использовать только в классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="98ab7-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="98ab7-148">Это означает, что *контекст объявления* для оператора не может быть исходным файлом, пространством имен, модулем, интерфейсом, процедурой или блоком.</span><span class="sxs-lookup"><span data-stu-id="98ab7-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="98ab7-149">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="98ab7-149">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="98ab7-150">Все операторы должны быть `Public Shared`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="98ab7-151">Для любого операнда нельзя указать `ByRef`, `Optional`или `ParamArray`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>

<span data-ttu-id="98ab7-152">Нельзя использовать символ оператора или идентификатор для хранения возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="98ab7-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="98ab7-153">Необходимо использовать оператор `Return` и указать значение.</span><span class="sxs-lookup"><span data-stu-id="98ab7-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="98ab7-154">Любое количество инструкций `Return` может находиться в любом месте процедуры.</span><span class="sxs-lookup"><span data-stu-id="98ab7-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>

<span data-ttu-id="98ab7-155">Определение оператора таким образом называется *перегрузкой оператора*, независимо от того, используется ли ключевое слово `Overloads`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="98ab7-156">В приведенной ниже таблице перечислены операторы, которые можно определить.</span><span class="sxs-lookup"><span data-stu-id="98ab7-156">The following table lists the operators you can define.</span></span>

|<span data-ttu-id="98ab7-157">Тип</span><span class="sxs-lookup"><span data-stu-id="98ab7-157">Type</span></span>|<span data-ttu-id="98ab7-158">Операторы</span><span class="sxs-lookup"><span data-stu-id="98ab7-158">Operators</span></span>|
|----------|---------------|
|<span data-ttu-id="98ab7-159">Унарный</span><span class="sxs-lookup"><span data-stu-id="98ab7-159">Unary</span></span>|<span data-ttu-id="98ab7-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="98ab7-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|
|<span data-ttu-id="98ab7-161">Binary</span><span class="sxs-lookup"><span data-stu-id="98ab7-161">Binary</span></span>|<span data-ttu-id="98ab7-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="98ab7-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|
|<span data-ttu-id="98ab7-163">Преобразование (унарный)</span><span class="sxs-lookup"><span data-stu-id="98ab7-163">Conversion (unary)</span></span>|`CType`|

<span data-ttu-id="98ab7-164">Обратите внимание, что оператор `=` в списке binary является оператором сравнения, а не оператором присваивания.</span><span class="sxs-lookup"><span data-stu-id="98ab7-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>

<span data-ttu-id="98ab7-165">При определении `CType`необходимо указать либо `Widening`, либо `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>

## <a name="matched-pairs"></a><span data-ttu-id="98ab7-166">Парные пары</span><span class="sxs-lookup"><span data-stu-id="98ab7-166">Matched Pairs</span></span>

<span data-ttu-id="98ab7-167">Необходимо определить определенные операторы в качестве совпадающих пар.</span><span class="sxs-lookup"><span data-stu-id="98ab7-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="98ab7-168">При определении любого из этих двух операторов такой пары необходимо определить и другое.</span><span class="sxs-lookup"><span data-stu-id="98ab7-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="98ab7-169">Сопоставленные пары являются следующими:</span><span class="sxs-lookup"><span data-stu-id="98ab7-169">The matched pairs are the following:</span></span>

- <span data-ttu-id="98ab7-170">`=` и `<>`</span><span class="sxs-lookup"><span data-stu-id="98ab7-170">`=` and `<>`</span></span>

- <span data-ttu-id="98ab7-171">`>` и `<`</span><span class="sxs-lookup"><span data-stu-id="98ab7-171">`>` and `<`</span></span>

- <span data-ttu-id="98ab7-172">`>=` и `<=`</span><span class="sxs-lookup"><span data-stu-id="98ab7-172">`>=` and `<=`</span></span>

- <span data-ttu-id="98ab7-173">`IsTrue` и `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="98ab7-173">`IsTrue` and `IsFalse`</span></span>

## <a name="data-type-restrictions"></a><span data-ttu-id="98ab7-174">Ограничения типов данных</span><span class="sxs-lookup"><span data-stu-id="98ab7-174">Data Type Restrictions</span></span>

<span data-ttu-id="98ab7-175">Каждый определяемый оператор должен содержать класс или структуру, в которых он определен.</span><span class="sxs-lookup"><span data-stu-id="98ab7-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="98ab7-176">Это означает, что класс или структура должны выглядеть как тип данных следующего:</span><span class="sxs-lookup"><span data-stu-id="98ab7-176">This means that the class or structure must appear as the data type of the following:</span></span>

- <span data-ttu-id="98ab7-177">Операнд унарного оператора.</span><span class="sxs-lookup"><span data-stu-id="98ab7-177">The operand of a unary operator.</span></span>

- <span data-ttu-id="98ab7-178">По крайней мере один из операндов бинарного оператора.</span><span class="sxs-lookup"><span data-stu-id="98ab7-178">At least one of the operands of a binary operator.</span></span>

- <span data-ttu-id="98ab7-179">Либо операнд, либо тип возвращаемого значения оператора преобразования.</span><span class="sxs-lookup"><span data-stu-id="98ab7-179">Either the operand or the return type of a conversion operator.</span></span>

 <span data-ttu-id="98ab7-180">Некоторые операторы имеют дополнительные ограничения по типам данных, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="98ab7-180">Certain operators have additional data type restrictions, as follows:</span></span>

- <span data-ttu-id="98ab7-181">Если вы определяете операторы `IsTrue` и `IsFalse`, они должны возвращать тип `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>

- <span data-ttu-id="98ab7-182">Если вы определяете операторы `<<` и `>>`, они должны указывать тип `Integer` для `operandtype` `operand2`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>

<span data-ttu-id="98ab7-183">Тип возвращаемого значения не должен соответствовать типу любого из операндов.</span><span class="sxs-lookup"><span data-stu-id="98ab7-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="98ab7-184">Например, оператор сравнения, например `=` или `<>`, может возвращать `Boolean`, даже если ни один из операндов не `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>

## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="98ab7-185">Логические и побитовые операторы</span><span class="sxs-lookup"><span data-stu-id="98ab7-185">Logical and Bitwise Operators</span></span>

<span data-ttu-id="98ab7-186">Операторы `And`, `Or`, `Not`и `Xor` могут выполнять логические или побитовые операции в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="98ab7-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="98ab7-187">Однако при определении одного из этих операторов для класса или структуры можно определить только его побитовую операцию.</span><span class="sxs-lookup"><span data-stu-id="98ab7-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>

<span data-ttu-id="98ab7-188">Оператор `AndAlso` нельзя определить непосредственно с помощью оператора `Operator`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="98ab7-189">Однако можно использовать `AndAlso`, если выполнены следующие условия.</span><span class="sxs-lookup"><span data-stu-id="98ab7-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>

- <span data-ttu-id="98ab7-190">Вы определили `And` для тех же типов операндов, которые вы хотите использовать для `AndAlso`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>

- <span data-ttu-id="98ab7-191">Определение `And` возвращает тот же тип, что и класс или структура, в которой он определен.</span><span class="sxs-lookup"><span data-stu-id="98ab7-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>

- <span data-ttu-id="98ab7-192">Вы определили оператор `IsFalse` в классе или структуре, для которой определены `And`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>

<span data-ttu-id="98ab7-193">Аналогичным образом можно использовать `OrElse`, если вы определили `Or` для одних и тех же операндов с типом возвращаемого значения класса или структуры и в классе или структуре определено `IsTrue`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>

## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="98ab7-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="98ab7-194">Widening and Narrowing Conversions</span></span>

<span data-ttu-id="98ab7-195">*Расширяющее преобразование* всегда выполняется успешно во время выполнения, в то время как *понижающие преобразования* могут завершиться ошибкой во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="98ab7-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="98ab7-196">Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="98ab7-196">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>

<span data-ttu-id="98ab7-197">При объявлении процедуры преобразования, которая будет `Widening`, код процедуры не должен создавать ошибок.</span><span class="sxs-lookup"><span data-stu-id="98ab7-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="98ab7-198">Это подразумевает следующее:</span><span class="sxs-lookup"><span data-stu-id="98ab7-198">This means the following:</span></span>

- <span data-ttu-id="98ab7-199">Он должен всегда возвращать допустимое значение типа `type`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-199">It must always return a valid value of type `type`.</span></span>

- <span data-ttu-id="98ab7-200">Он должен поддерживать все возможные исключения и другие условия возникновения ошибок.</span><span class="sxs-lookup"><span data-stu-id="98ab7-200">It must handle all possible exceptions and other error conditions.</span></span>

- <span data-ttu-id="98ab7-201">Она должна поддерживать любые ошибки, возвращаемые из всех процедур, которые она вызывает.</span><span class="sxs-lookup"><span data-stu-id="98ab7-201">It must handle any error returns from any procedures it calls.</span></span>

<span data-ttu-id="98ab7-202">Если существует вероятность того, что процедура преобразования может не быть выполнена или что она может вызвать необработанное исключение, необходимо объявить ее `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>

## <a name="example"></a><span data-ttu-id="98ab7-203">Пример</span><span class="sxs-lookup"><span data-stu-id="98ab7-203">Example</span></span>

<span data-ttu-id="98ab7-204">В следующем примере кода используется оператор `Operator` для определения структуры, которая включает в себя процедуры оператора для `And`, `Or`, `IsFalse`и `IsTrue` операторов.</span><span class="sxs-lookup"><span data-stu-id="98ab7-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="98ab7-205">`And` и `Or` принимают два операнда типа `abc` и тип возвращаемого значения `abc`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="98ab7-206">`IsFalse` и `IsTrue` принимают один операнд типа `abc` и возвращают `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="98ab7-207">Эти определения позволяют вызывающему коду использовать `And`, `AndAlso`, `Or`и `OrElse` с операндами типа `abc`.</span><span class="sxs-lookup"><span data-stu-id="98ab7-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a><span data-ttu-id="98ab7-208">См. также:</span><span class="sxs-lookup"><span data-stu-id="98ab7-208">See also</span></span>

- [<span data-ttu-id="98ab7-209">Оператор IsFalse</span><span class="sxs-lookup"><span data-stu-id="98ab7-209">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="98ab7-210">Оператор IsTrue</span><span class="sxs-lookup"><span data-stu-id="98ab7-210">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="98ab7-211">Расширение</span><span class="sxs-lookup"><span data-stu-id="98ab7-211">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="98ab7-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="98ab7-212">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="98ab7-213">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="98ab7-213">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="98ab7-214">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="98ab7-214">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="98ab7-215">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="98ab7-215">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="98ab7-216">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="98ab7-216">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="98ab7-217">Практическое руководство. Вызов процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="98ab7-217">How to: Call an Operator Procedure</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="98ab7-218">Практическое руководство. Использование класса, в котором определяются операторы</span><span class="sxs-lookup"><span data-stu-id="98ab7-218">How to: Use a Class that Defines Operators</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
