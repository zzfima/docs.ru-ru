---
title: Список параметров
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
ms.openlocfilehash: ec4ce0f12b540478d889832fb18f1ef008613f1f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346482"
---
# <a name="parameter-list-visual-basic"></a><span data-ttu-id="9e2cf-102">Список параметров (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e2cf-102">Parameter List (Visual Basic)</span></span>

<span data-ttu-id="9e2cf-103">Указывает параметры, которые должны быть вызваны процедурой при ее вызове.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-103">Specifies the parameters a procedure expects when it is called.</span></span> <span data-ttu-id="9e2cf-104">Несколько параметров разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="9e2cf-105">Ниже приведен синтаксис для одного параметра.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-105">The following is the syntax for one parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="9e2cf-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e2cf-106">Syntax</span></span>

```vb
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]
parametername[( )] [ As parametertype ] [ = defaultvalue ]
```

## <a name="parts"></a><span data-ttu-id="9e2cf-107">Части</span><span class="sxs-lookup"><span data-stu-id="9e2cf-107">Parts</span></span>

`attributelist`  
<span data-ttu-id="9e2cf-108">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-108">Optional.</span></span> <span data-ttu-id="9e2cf-109">Список атрибутов, применяемых к этому параметру.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-109">List of attributes that apply to this parameter.</span></span> <span data-ttu-id="9e2cf-110">[Список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) необходимо заключить в угловые скобки ("`<`" и "`>`").</span><span class="sxs-lookup"><span data-stu-id="9e2cf-110">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>

`Optional`  
<span data-ttu-id="9e2cf-111">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-111">Optional.</span></span> <span data-ttu-id="9e2cf-112">Указывает, что этот параметр не является обязательным при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-112">Specifies that this parameter is not required when the procedure is called.</span></span>

`ByVal`  
<span data-ttu-id="9e2cf-113">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-113">Optional.</span></span> <span data-ttu-id="9e2cf-114">Указывает, что процедура не может заменить или переназначить элемент переменной, лежащий в основе соответствующего аргумента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-114">Specifies that the procedure cannot replace or reassign the variable element underlying the corresponding argument in the calling code.</span></span>

`ByRef`  
<span data-ttu-id="9e2cf-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-115">Optional.</span></span> <span data-ttu-id="9e2cf-116">Указывает, что процедура может изменить базовый элемент Variable в вызывающем коде так же, как и сам вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-116">Specifies that the procedure can modify the underlying variable element in the calling code the same way the calling code itself can.</span></span>

`ParamArray`  
<span data-ttu-id="9e2cf-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-117">Optional.</span></span> <span data-ttu-id="9e2cf-118">Указывает, что последний параметр в списке параметров является необязательным массивом элементов указанного типа данных.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-118">Specifies that the last parameter in the parameter list is an optional array of elements of the specified data type.</span></span> <span data-ttu-id="9e2cf-119">Это позволяет вызывающему коду передавать процедуре произвольное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-119">This lets the calling code pass an arbitrary number of arguments to the procedure.</span></span>

`parametername`  
<span data-ttu-id="9e2cf-120">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-120">Required.</span></span> <span data-ttu-id="9e2cf-121">Имя локальной переменной, представляющей параметр.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-121">Name of the local variable representing the parameter.</span></span>

`parametertype`  
<span data-ttu-id="9e2cf-122">Требуется, если `Option Strict` `On`.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-122">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="9e2cf-123">Тип данных локальной переменной, представляющей параметр.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-123">Data type of the local variable representing the parameter.</span></span>

`defaultvalue`  
<span data-ttu-id="9e2cf-124">Требуется для `Optional` параметров.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-124">Required for `Optional` parameters.</span></span> <span data-ttu-id="9e2cf-125">Любое константное или константное выражение, результатом которого является тип данных параметра.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-125">Any constant or constant expression that evaluates to the data type of the parameter.</span></span> <span data-ttu-id="9e2cf-126">Если тип `Object`или класс, интерфейс, массив или структура, значение по умолчанию можно только `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-126">If the type is `Object`, or a class, interface, array, or structure, the default value can only be `Nothing`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9e2cf-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="9e2cf-127">Remarks</span></span>

<span data-ttu-id="9e2cf-128">Параметры заключаются в круглые скобки и разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-128">Parameters are surrounded by parentheses and separated by commas.</span></span> <span data-ttu-id="9e2cf-129">Параметр может быть объявлен с любым типом данных.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-129">A parameter can be declared with any data type.</span></span> <span data-ttu-id="9e2cf-130">Если не указать `parametertype`, по умолчанию используется `Object`.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-130">If you do not specify `parametertype`, it defaults to `Object`.</span></span>

<span data-ttu-id="9e2cf-131">Когда вызывающий код вызывает процедуру, он передает *аргумент* в каждый обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-131">When the calling code calls the procedure, it passes an *argument* to each required parameter.</span></span> <span data-ttu-id="9e2cf-132">Дополнительные сведения см. в разделе [различия между параметрами и аргументами](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="9e2cf-132">For more information, see [Differences Between Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span></span>

<span data-ttu-id="9e2cf-133">Аргумент, который вызывающий код передает каждому параметру, является указателем на базовый элемент в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-133">The argument the calling code passes to each parameter is a pointer to an underlying element in the calling code.</span></span> <span data-ttu-id="9e2cf-134">Если этот элемент является *неизменяемым* (константой, литералом, перечислением или выражением), любой код изменить его невозможно.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-134">If this element is *nonvariable* (a constant, literal, enumeration, or expression), it is impossible for any code to change it.</span></span> <span data-ttu-id="9e2cf-135">Если это элемент *переменной* (объявленная переменная, поле, свойство, элемент массива или элемент структуры), вызывающий код может изменить его.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-135">If it is a *variable* element (a declared variable, field, property, array element, or structure element), the calling code can change it.</span></span> <span data-ttu-id="9e2cf-136">Дополнительные сведения см. в разделе [различия между изменяемыми и неизменяемыми аргументами](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="9e2cf-136">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span></span>

<span data-ttu-id="9e2cf-137">Если элемент переменной передается `ByRef`, процедура также может изменить ее.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-137">If a variable element is passed `ByRef`, the procedure can change it as well.</span></span> <span data-ttu-id="9e2cf-138">Дополнительные сведения см. в разделе [различия между передачей аргумента по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span><span class="sxs-lookup"><span data-stu-id="9e2cf-138">For more information, see [Differences Between Passing an Argument By Value and By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>

## <a name="rules"></a><span data-ttu-id="9e2cf-139">Правила</span><span class="sxs-lookup"><span data-stu-id="9e2cf-139">Rules</span></span>

- <span data-ttu-id="9e2cf-140">**Скобки.**</span><span class="sxs-lookup"><span data-stu-id="9e2cf-140">**Parentheses.**</span></span> <span data-ttu-id="9e2cf-141">Если указан список параметров, его необходимо заключить в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-141">If you specify a parameter list, you must enclose it in parentheses.</span></span> <span data-ttu-id="9e2cf-142">Если параметры отсутствуют, можно по-прежнему использовать круглые скобки, включающие пустой список.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-142">If there are no parameters, you can still use parentheses enclosing an empty list.</span></span> <span data-ttu-id="9e2cf-143">Это повышает удобочитаемость кода путем уточнения того, что элемент является процедурой.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-143">This improves the readability of your code by clarifying that the element is a procedure.</span></span>

- <span data-ttu-id="9e2cf-144">**Необязательные параметры.**</span><span class="sxs-lookup"><span data-stu-id="9e2cf-144">**Optional Parameters.**</span></span> <span data-ttu-id="9e2cf-145">При использовании модификатора `Optional` для параметра все последующие параметры в списке также должны быть необязательными и объявлены с помощью модификатора `Optional`.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-145">If you use the `Optional` modifier on a parameter, all subsequent parameters in the list must also be optional and be declared by using the `Optional` modifier.</span></span>

     <span data-ttu-id="9e2cf-146">Каждое объявление необязательного параметра должно предоставлять предложение `defaultvalue`.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-146">Every optional parameter declaration must supply the `defaultvalue` clause.</span></span>

     <span data-ttu-id="9e2cf-147">Дополнительные сведения см. в разделе [необязательные параметры](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="9e2cf-147">For more information, see [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span></span>

- <span data-ttu-id="9e2cf-148">**Массивы параметров.**</span><span class="sxs-lookup"><span data-stu-id="9e2cf-148">**Parameter Arrays.**</span></span> <span data-ttu-id="9e2cf-149">Для параметра `ParamArray` необходимо указать `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-149">You must specify `ByVal` for a `ParamArray` parameter.</span></span>

     <span data-ttu-id="9e2cf-150">В одном списке параметров нельзя использовать как `Optional`, так и `ParamArray`.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-150">You cannot use both `Optional` and `ParamArray` in the same parameter list.</span></span>

     <span data-ttu-id="9e2cf-151">Дополнительные сведения см. в разделе [массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="9e2cf-151">For more information, see [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>

- <span data-ttu-id="9e2cf-152">**Механизм передачи.**</span><span class="sxs-lookup"><span data-stu-id="9e2cf-152">**Passing Mechanism.**</span></span> <span data-ttu-id="9e2cf-153">Механизмом по умолчанию для каждого аргумента является `ByVal`, что означает, что процедура не может изменить базовый элемент Variable.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-153">The default mechanism for every argument is `ByVal`, which means the procedure cannot change the underlying variable element.</span></span> <span data-ttu-id="9e2cf-154">Однако если элемент является ссылочным типом, процедура может изменить содержимое или члены базового объекта, даже если он не может заменить или переназначить сам объект.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-154">However, if the element is a reference type, the procedure can modify the contents or members of the underlying object, even though it cannot replace or reassign the object itself.</span></span>

- <span data-ttu-id="9e2cf-155">**Имена параметров.**</span><span class="sxs-lookup"><span data-stu-id="9e2cf-155">**Parameter Names.**</span></span> <span data-ttu-id="9e2cf-156">Если тип данных параметра является массивом, следуйте указаниям, `parametername`, сразу после круглых скобок.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-156">If the parameter's data type is an array, follow `parametername` immediately by parentheses.</span></span> <span data-ttu-id="9e2cf-157">Дополнительные сведения об именах параметров см. в разделе [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="9e2cf-157">For more information on parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

## <a name="example"></a><span data-ttu-id="9e2cf-158">Пример</span><span class="sxs-lookup"><span data-stu-id="9e2cf-158">Example</span></span>

<span data-ttu-id="9e2cf-159">В следующем примере показана `Function` процедура, определяющая два параметра.</span><span class="sxs-lookup"><span data-stu-id="9e2cf-159">The following example shows a `Function` procedure that defines two parameters.</span></span>

[!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]

## <a name="see-also"></a><span data-ttu-id="9e2cf-160">См. также</span><span class="sxs-lookup"><span data-stu-id="9e2cf-160">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="9e2cf-161">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="9e2cf-161">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="9e2cf-162">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="9e2cf-162">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="9e2cf-163">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="9e2cf-163">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="9e2cf-164">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="9e2cf-164">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="9e2cf-165">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="9e2cf-165">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="9e2cf-166">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="9e2cf-166">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="9e2cf-167">Практическое руководство. Разбиение и объединение инструкций в коде</span><span class="sxs-lookup"><span data-stu-id="9e2cf-167">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
