---
title: "Список параметров (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- parameters, Visual Basic
- parameters, lists
- parameter lists
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures, parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
caps.latest.revision: 19
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: cc56d90db9a732928773fa549cb1456d368e1dbe
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="parameter-list-visual-basic"></a><span data-ttu-id="8d072-102">Список параметров (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d072-102">Parameter List (Visual Basic)</span></span>
<span data-ttu-id="8d072-103">Задает параметры, ожидаемые процедурой при вызове.</span><span class="sxs-lookup"><span data-stu-id="8d072-103">Specifies the parameters a procedure expects when it is called.</span></span> <span data-ttu-id="8d072-104">Несколько параметров разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="8d072-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="8d072-105">Ниже приведен синтаксис для одного параметра.</span><span class="sxs-lookup"><span data-stu-id="8d072-105">The following is the syntax for one parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d072-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d072-106">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a><span data-ttu-id="8d072-107">Части</span><span class="sxs-lookup"><span data-stu-id="8d072-107">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="8d072-108">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="8d072-108">Optional.</span></span> <span data-ttu-id="8d072-109">Список атрибутов, которые применяются к данному параметру.</span><span class="sxs-lookup"><span data-stu-id="8d072-109">List of attributes that apply to this parameter.</span></span> <span data-ttu-id="8d072-110">Необходимо заключить [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) в угловые скобки («`<`«и»`>`»).</span><span class="sxs-lookup"><span data-stu-id="8d072-110">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
 `Optional`  
 <span data-ttu-id="8d072-111">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="8d072-111">Optional.</span></span> <span data-ttu-id="8d072-112">Указывает, что этот параметр не требуется при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="8d072-112">Specifies that this parameter is not required when the procedure is called.</span></span>  
  
 `ByVal`  
 <span data-ttu-id="8d072-113">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="8d072-113">Optional.</span></span> <span data-ttu-id="8d072-114">Указывает, что процедура не может заменить или переназначить основной соответствующего аргумента в вызывающем коде элемент переменной.</span><span class="sxs-lookup"><span data-stu-id="8d072-114">Specifies that the procedure cannot replace or reassign the variable element underlying the corresponding argument in the calling code.</span></span>  
  
 `ByRef`  
 <span data-ttu-id="8d072-115">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="8d072-115">Optional.</span></span> <span data-ttu-id="8d072-116">Указывает, что процедура может изменять основной элемент переменной в вызывающем коде так же, как самим вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="8d072-116">Specifies that the procedure can modify the underlying variable element in the calling code the same way the calling code itself can.</span></span>  
  
 `ParamArray`  
 <span data-ttu-id="8d072-117">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="8d072-117">Optional.</span></span> <span data-ttu-id="8d072-118">Указывает, что последний параметр в списке параметров необязательный массив элементов заданного типа данных.</span><span class="sxs-lookup"><span data-stu-id="8d072-118">Specifies that the last parameter in the parameter list is an optional array of elements of the specified data type.</span></span> <span data-ttu-id="8d072-119">Это позволяет передавать произвольное число аргументов в процедуру.</span><span class="sxs-lookup"><span data-stu-id="8d072-119">This lets the calling code pass an arbitrary number of arguments to the procedure.</span></span>  
  
 `parametername`  
 <span data-ttu-id="8d072-120">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="8d072-120">Required.</span></span> <span data-ttu-id="8d072-121">Имя локальной переменной, представляющей параметр.</span><span class="sxs-lookup"><span data-stu-id="8d072-121">Name of the local variable representing the parameter.</span></span>  
  
 `parametertype`  
 <span data-ttu-id="8d072-122">Обязателен, если `Option Strict` — `On`.</span><span class="sxs-lookup"><span data-stu-id="8d072-122">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="8d072-123">Тип данных локальной переменной, представляющей параметр.</span><span class="sxs-lookup"><span data-stu-id="8d072-123">Data type of the local variable representing the parameter.</span></span>  
  
 `defaultvalue`  
 <span data-ttu-id="8d072-124">Требуется для `Optional` параметров.</span><span class="sxs-lookup"><span data-stu-id="8d072-124">Required for `Optional` parameters.</span></span> <span data-ttu-id="8d072-125">Любая константа или константное выражение, результатом которого является тип данных параметра.</span><span class="sxs-lookup"><span data-stu-id="8d072-125">Any constant or constant expression that evaluates to the data type of the parameter.</span></span> <span data-ttu-id="8d072-126">Если тип является `Object`, или класс, интерфейс, массив или структура, значение по умолчанию может быть только `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="8d072-126">If the type is `Object`, or a class, interface, array, or structure, the default value can only be `Nothing`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d072-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="8d072-127">Remarks</span></span>  
 <span data-ttu-id="8d072-128">Параметры заключаются в круглые скобки и разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="8d072-128">Parameters are surrounded by parentheses and separated by commas.</span></span> <span data-ttu-id="8d072-129">Параметр может быть объявлен с любой тип данных.</span><span class="sxs-lookup"><span data-stu-id="8d072-129">A parameter can be declared with any data type.</span></span> <span data-ttu-id="8d072-130">Если вы не укажете `parametertype`, по умолчанию используется `Object`.</span><span class="sxs-lookup"><span data-stu-id="8d072-130">If you do not specify `parametertype`, it defaults to `Object`.</span></span>  
  
 <span data-ttu-id="8d072-131">Если вызывающий код вызывает процедуру, он передает *аргумент* для каждого обязательного параметра.</span><span class="sxs-lookup"><span data-stu-id="8d072-131">When the calling code calls the procedure, it passes an *argument* to each required parameter.</span></span> <span data-ttu-id="8d072-132">Дополнительные сведения см. в разделе [различия между параметрами и аргументами](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="8d072-132">For more information, see [Differences Between Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span></span>  
  
 <span data-ttu-id="8d072-133">Аргумент, вызывающий код передает в каждый параметр является указателем на базовый элемент в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="8d072-133">The argument the calling code passes to each parameter is a pointer to an underlying element in the calling code.</span></span> <span data-ttu-id="8d072-134">Если этот элемент является *неизменяемым* (константа, литерал, перечисление или выражение), любой код изменить его невозможно.</span><span class="sxs-lookup"><span data-stu-id="8d072-134">If this element is *nonvariable* (a constant, literal, enumeration, or expression), it is impossible for any code to change it.</span></span> <span data-ttu-id="8d072-135">Если это *переменной* элемента (объявленная переменная, поле, свойство, элемент массива или элемент структуры), вызывающий код может изменить его.</span><span class="sxs-lookup"><span data-stu-id="8d072-135">If it is a *variable* element (a declared variable, field, property, array element, or structure element), the calling code can change it.</span></span> <span data-ttu-id="8d072-136">Дополнительные сведения см. в разделе [различия между изменяемые и неизменяемые аргументы](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="8d072-136">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span></span>  
  
 <span data-ttu-id="8d072-137">Если элемент переменной передается `ByRef`, процедура может изменять его тоже.</span><span class="sxs-lookup"><span data-stu-id="8d072-137">If a variable element is passed `ByRef`, the procedure can change it as well.</span></span> <span data-ttu-id="8d072-138">Дополнительные сведения см. в разделе [различия между передачей аргумента по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span><span class="sxs-lookup"><span data-stu-id="8d072-138">For more information, see [Differences Between Passing an Argument By Value and By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="8d072-139">Правила</span><span class="sxs-lookup"><span data-stu-id="8d072-139">Rules</span></span>  
  
-   <span data-ttu-id="8d072-140">**Круглые скобки.**</span><span class="sxs-lookup"><span data-stu-id="8d072-140">**Parentheses.**</span></span> <span data-ttu-id="8d072-141">Если указан список параметров, необходимо заключить его в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="8d072-141">If you specify a parameter list, you must enclose it in parentheses.</span></span> <span data-ttu-id="8d072-142">Если параметры не указаны, по-прежнему можно использовать скобки, ограничивающие пустой список.</span><span class="sxs-lookup"><span data-stu-id="8d072-142">If there are no parameters, you can still use parentheses enclosing an empty list.</span></span> <span data-ttu-id="8d072-143">Это повышает удобочитаемость кода, указывая, что элемент является процедурой.</span><span class="sxs-lookup"><span data-stu-id="8d072-143">This improves the readability of your code by clarifying that the element is a procedure.</span></span>  
  
-   <span data-ttu-id="8d072-144">**Необязательные параметры.**</span><span class="sxs-lookup"><span data-stu-id="8d072-144">**Optional Parameters.**</span></span> <span data-ttu-id="8d072-145">Если вы используете `Optional` модификатора параметра, все последующие параметры в списке также должен быть необязательным и объявляться с помощью `Optional` модификатор.</span><span class="sxs-lookup"><span data-stu-id="8d072-145">If you use the `Optional` modifier on a parameter, all subsequent parameters in the list must also be optional and be declared by using the `Optional` modifier.</span></span>  
  
     <span data-ttu-id="8d072-146">Каждое объявление дополнительного параметра необходимо указать `defaultvalue` предложения.</span><span class="sxs-lookup"><span data-stu-id="8d072-146">Every optional parameter declaration must supply the `defaultvalue` clause.</span></span>  
  
     <span data-ttu-id="8d072-147">Дополнительные сведения см. в разделе [необязательные параметры](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="8d072-147">For more information, see [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span></span>  
  
-   <span data-ttu-id="8d072-148">**Массивы параметров.**</span><span class="sxs-lookup"><span data-stu-id="8d072-148">**Parameter Arrays.**</span></span> <span data-ttu-id="8d072-149">Необходимо указать `ByVal` для `ParamArray` параметр.</span><span class="sxs-lookup"><span data-stu-id="8d072-149">You must specify `ByVal` for a `ParamArray` parameter.</span></span>  
  
     <span data-ttu-id="8d072-150">Нельзя одновременно указать `Optional` и `ParamArray` в такой же список параметров.</span><span class="sxs-lookup"><span data-stu-id="8d072-150">You cannot use both `Optional` and `ParamArray` in the same parameter list.</span></span>  
  
     <span data-ttu-id="8d072-151">Дополнительные сведения см. в разделе [массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="8d072-151">For more information, see [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
-   <span data-ttu-id="8d072-152">**Механизм передачи.**</span><span class="sxs-lookup"><span data-stu-id="8d072-152">**Passing Mechanism.**</span></span> <span data-ttu-id="8d072-153">Механизм по умолчанию для каждого аргумента является `ByVal`, означающее процедуру нельзя изменить элемент базовой переменной.</span><span class="sxs-lookup"><span data-stu-id="8d072-153">The default mechanism for every argument is `ByVal`, which means the procedure cannot change the underlying variable element.</span></span> <span data-ttu-id="8d072-154">Тем не менее если элемент является ссылочным типом, процедура может изменить содержимое или члены базового объекта, даже если она не может заменить или переназначить сам объект.</span><span class="sxs-lookup"><span data-stu-id="8d072-154">However, if the element is a reference type, the procedure can modify the contents or members of the underlying object, even though it cannot replace or reassign the object itself.</span></span>  
  
-   <span data-ttu-id="8d072-155">**Имена параметров.**</span><span class="sxs-lookup"><span data-stu-id="8d072-155">**Parameter Names.**</span></span> <span data-ttu-id="8d072-156">Если тип данных параметра является массивом, выполните `parametername` немедленно круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="8d072-156">If the parameter's data type is an array, follow `parametername` immediately by parentheses.</span></span> <span data-ttu-id="8d072-157">Дополнительные сведения об именах параметра см. в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="8d072-157">For more information on parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d072-158">Пример</span><span class="sxs-lookup"><span data-stu-id="8d072-158">Example</span></span>  
 <span data-ttu-id="8d072-159">В следующем примере показан `Function` процедуры, определяющей два параметра.</span><span class="sxs-lookup"><span data-stu-id="8d072-159">The following example shows a `Function` procedure that defines two parameters.</span></span>  
  
 <span data-ttu-id="8d072-160">[!code-vb[VbVbalrStatements&#2;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d072-160">[!code-vb[VbVbalrStatements#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d072-161">См. также</span><span class="sxs-lookup"><span data-stu-id="8d072-161">See Also</span></span>  
 <span data-ttu-id="8d072-162"><xref:System.Runtime.InteropServices.DllImportAttribute></xref:System.Runtime.InteropServices.DllImportAttribute></span><span class="sxs-lookup"><span data-stu-id="8d072-162"><xref:System.Runtime.InteropServices.DllImportAttribute></span></span>   
<span data-ttu-id="8d072-163"> [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8d072-163"> [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="8d072-164"> [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8d072-164"> [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="8d072-165"> [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8d072-165"> [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) </span></span>  
<span data-ttu-id="8d072-166"> [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8d072-166"> [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="8d072-167"> [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8d072-167"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="8d072-168"> [Общие сведения об атрибутах](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="8d072-168"> [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span></span>  
<span data-ttu-id="8d072-169"> [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)</span><span class="sxs-lookup"><span data-stu-id="8d072-169"> [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)</span></span>
