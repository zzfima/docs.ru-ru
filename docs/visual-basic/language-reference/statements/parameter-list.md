---
title: Список параметров (Visual Basic)
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
ms.openlocfilehash: 147a2501219db9f1f1c10f9cf1a81aa395b5ec2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="parameter-list-visual-basic"></a><span data-ttu-id="7fb6c-102">Список параметров (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7fb6c-102">Parameter List (Visual Basic)</span></span>
<span data-ttu-id="7fb6c-103">Задает параметры, ожидаемые процедурой при вызове.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-103">Specifies the parameters a procedure expects when it is called.</span></span> <span data-ttu-id="7fb6c-104">Несколько параметров разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="7fb6c-105">Ниже приведен синтаксис для одного параметра.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-105">The following is the syntax for one parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fb6c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7fb6c-106">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a><span data-ttu-id="7fb6c-107">Части</span><span class="sxs-lookup"><span data-stu-id="7fb6c-107">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="7fb6c-108">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-108">Optional.</span></span> <span data-ttu-id="7fb6c-109">Список атрибутов, которые применяются к данному параметру.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-109">List of attributes that apply to this parameter.</span></span> <span data-ttu-id="7fb6c-110">Необходимо заключить [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) в угловые скобки («`<`«и»`>`»).</span><span class="sxs-lookup"><span data-stu-id="7fb6c-110">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
 `Optional`  
 <span data-ttu-id="7fb6c-111">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-111">Optional.</span></span> <span data-ttu-id="7fb6c-112">Указывает, что этот параметр не требуется при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-112">Specifies that this parameter is not required when the procedure is called.</span></span>  
  
 `ByVal`  
 <span data-ttu-id="7fb6c-113">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-113">Optional.</span></span> <span data-ttu-id="7fb6c-114">Указывает, что процедура не может заменить или переназначить элемент переменной, представляющей соответствующий аргумент в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-114">Specifies that the procedure cannot replace or reassign the variable element underlying the corresponding argument in the calling code.</span></span>  
  
 `ByRef`  
 <span data-ttu-id="7fb6c-115">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-115">Optional.</span></span> <span data-ttu-id="7fb6c-116">Указывает, что процедура может изменить элемент базовой переменной в вызывающем коде так же, как в вызывающем коде можно.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-116">Specifies that the procedure can modify the underlying variable element in the calling code the same way the calling code itself can.</span></span>  
  
 `ParamArray`  
 <span data-ttu-id="7fb6c-117">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-117">Optional.</span></span> <span data-ttu-id="7fb6c-118">Указывает, что последний параметр в списке параметров необязательный массив элементов заданного типа данных.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-118">Specifies that the last parameter in the parameter list is an optional array of elements of the specified data type.</span></span> <span data-ttu-id="7fb6c-119">Это позволяет передать произвольное число аргументов в процедуру вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-119">This lets the calling code pass an arbitrary number of arguments to the procedure.</span></span>  
  
 `parametername`  
 <span data-ttu-id="7fb6c-120">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-120">Required.</span></span> <span data-ttu-id="7fb6c-121">Имя локальной переменной, представляющей параметр.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-121">Name of the local variable representing the parameter.</span></span>  
  
 `parametertype`  
 <span data-ttu-id="7fb6c-122">Обязателен, если `Option Strict` — `On`.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-122">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="7fb6c-123">Тип данных локальной переменной, представляющей параметр.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-123">Data type of the local variable representing the parameter.</span></span>  
  
 `defaultvalue`  
 <span data-ttu-id="7fb6c-124">Требуется для `Optional` параметров.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-124">Required for `Optional` parameters.</span></span> <span data-ttu-id="7fb6c-125">Любая константа или константное выражение, результатом которого является тип данных параметра.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-125">Any constant or constant expression that evaluates to the data type of the parameter.</span></span> <span data-ttu-id="7fb6c-126">Если тип является `Object`, или класс, интерфейс, массив или структура, значение по умолчанию можно только `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-126">If the type is `Object`, or a class, interface, array, or structure, the default value can only be `Nothing`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7fb6c-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="7fb6c-127">Remarks</span></span>  
 <span data-ttu-id="7fb6c-128">Параметры заключаются в круглые скобки и разделены запятыми.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-128">Parameters are surrounded by parentheses and separated by commas.</span></span> <span data-ttu-id="7fb6c-129">Параметр может быть объявлен с любым типом данных.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-129">A parameter can be declared with any data type.</span></span> <span data-ttu-id="7fb6c-130">Если вы не укажете `parametertype`, то по умолчанию используется `Object`.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-130">If you do not specify `parametertype`, it defaults to `Object`.</span></span>  
  
 <span data-ttu-id="7fb6c-131">Если вызывающий код вызывает процедуру, то он передает *аргумент* для каждого обязательного параметра.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-131">When the calling code calls the procedure, it passes an *argument* to each required parameter.</span></span> <span data-ttu-id="7fb6c-132">Дополнительные сведения см. в разделе [различия между параметрами и аргументами](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="7fb6c-132">For more information, see [Differences Between Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span></span>  
  
 <span data-ttu-id="7fb6c-133">Аргумент, который передает вызывающий код в каждый параметр является указателем на базовый элемент в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-133">The argument the calling code passes to each parameter is a pointer to an underlying element in the calling code.</span></span> <span data-ttu-id="7fb6c-134">Если этот элемент является *неизменяемым* (константа, литерал, перечисление или выражение), для любого кода изменить его невозможно.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-134">If this element is *nonvariable* (a constant, literal, enumeration, or expression), it is impossible for any code to change it.</span></span> <span data-ttu-id="7fb6c-135">Если это *переменной* элемент (объявленная переменная, поле, свойство, элемент массива или элемент структуры), вызывающий код может изменить его.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-135">If it is a *variable* element (a declared variable, field, property, array element, or structure element), the calling code can change it.</span></span> <span data-ttu-id="7fb6c-136">Дополнительные сведения см. в разделе [различия между изменяемые и неизменяемые аргументы](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="7fb6c-136">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span></span>  
  
 <span data-ttu-id="7fb6c-137">Если элемент переменной передается `ByRef`, процедура он также меняется.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-137">If a variable element is passed `ByRef`, the procedure can change it as well.</span></span> <span data-ttu-id="7fb6c-138">Дополнительные сведения см. в разделе [различия между передачей аргумента по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span><span class="sxs-lookup"><span data-stu-id="7fb6c-138">For more information, see [Differences Between Passing an Argument By Value and By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="7fb6c-139">Правила</span><span class="sxs-lookup"><span data-stu-id="7fb6c-139">Rules</span></span>  
  
-   <span data-ttu-id="7fb6c-140">**Круглые скобки.**</span><span class="sxs-lookup"><span data-stu-id="7fb6c-140">**Parentheses.**</span></span> <span data-ttu-id="7fb6c-141">Если указан список параметров, его необходимо заключить в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-141">If you specify a parameter list, you must enclose it in parentheses.</span></span> <span data-ttu-id="7fb6c-142">Если параметры не указаны, можно по-прежнему использовать скобки, ограничивающие пустой список.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-142">If there are no parameters, you can still use parentheses enclosing an empty list.</span></span> <span data-ttu-id="7fb6c-143">Это повышает удобочитаемость кода, указывая, что элемент является процедурой.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-143">This improves the readability of your code by clarifying that the element is a procedure.</span></span>  
  
-   <span data-ttu-id="7fb6c-144">**Необязательные параметры.**</span><span class="sxs-lookup"><span data-stu-id="7fb6c-144">**Optional Parameters.**</span></span> <span data-ttu-id="7fb6c-145">Если вы используете `Optional` модификатор параметра, все последующие параметры в списке также должен быть необязательным и быть объявлены с помощью `Optional` модификатор.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-145">If you use the `Optional` modifier on a parameter, all subsequent parameters in the list must also be optional and be declared by using the `Optional` modifier.</span></span>  
  
     <span data-ttu-id="7fb6c-146">Каждое объявление необязательного параметра необходимо указать `defaultvalue` предложения.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-146">Every optional parameter declaration must supply the `defaultvalue` clause.</span></span>  
  
     <span data-ttu-id="7fb6c-147">Дополнительные сведения см. в разделе [необязательные параметры](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="7fb6c-147">For more information, see [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span></span>  
  
-   <span data-ttu-id="7fb6c-148">**Массивы параметров.**</span><span class="sxs-lookup"><span data-stu-id="7fb6c-148">**Parameter Arrays.**</span></span> <span data-ttu-id="7fb6c-149">Необходимо указать `ByVal` для `ParamArray` параметра.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-149">You must specify `ByVal` for a `ParamArray` parameter.</span></span>  
  
     <span data-ttu-id="7fb6c-150">Нельзя одновременно указать `Optional` и `ParamArray` в том же списке параметров.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-150">You cannot use both `Optional` and `ParamArray` in the same parameter list.</span></span>  
  
     <span data-ttu-id="7fb6c-151">Дополнительные сведения см. в разделе [массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="7fb6c-151">For more information, see [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
-   <span data-ttu-id="7fb6c-152">**Механизм передачи.**</span><span class="sxs-lookup"><span data-stu-id="7fb6c-152">**Passing Mechanism.**</span></span> <span data-ttu-id="7fb6c-153">По умолчанию механизм для каждого аргумента является `ByVal`, означающее процедуру нельзя изменить элемент базовой переменной.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-153">The default mechanism for every argument is `ByVal`, which means the procedure cannot change the underlying variable element.</span></span> <span data-ttu-id="7fb6c-154">Тем не менее если элемент является ссылочным типом, процедура может изменить содержимое или члены базового объекта, даже в том случае, если оно не может заменить или переназначить сам объект.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-154">However, if the element is a reference type, the procedure can modify the contents or members of the underlying object, even though it cannot replace or reassign the object itself.</span></span>  
  
-   <span data-ttu-id="7fb6c-155">**Имена параметров.**</span><span class="sxs-lookup"><span data-stu-id="7fb6c-155">**Parameter Names.**</span></span> <span data-ttu-id="7fb6c-156">Если тип данных параметра является массивом, выполните `parametername` немедленно круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-156">If the parameter's data type is an array, follow `parametername` immediately by parentheses.</span></span> <span data-ttu-id="7fb6c-157">Дополнительные сведения об именах параметров см. в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="7fb6c-157">For more information on parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fb6c-158">Пример</span><span class="sxs-lookup"><span data-stu-id="7fb6c-158">Example</span></span>  
 <span data-ttu-id="7fb6c-159">В следующем примере показан `Function` процедуру, которая определяет два параметра.</span><span class="sxs-lookup"><span data-stu-id="7fb6c-159">The following example shows a `Function` procedure that defines two parameters.</span></span>  
  
 [!code-vb[VbVbalrStatements#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7fb6c-160">См. также</span><span class="sxs-lookup"><span data-stu-id="7fb6c-160">See Also</span></span>  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [<span data-ttu-id="7fb6c-161">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="7fb6c-161">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="7fb6c-162">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="7fb6c-162">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="7fb6c-163">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="7fb6c-163">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="7fb6c-164">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="7fb6c-164">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="7fb6c-165">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="7fb6c-165">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="7fb6c-166">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="7fb6c-166">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="7fb6c-167">Практическое руководство. Разбиение и объединение инструкций в коде</span><span class="sxs-lookup"><span data-stu-id="7fb6c-167">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
