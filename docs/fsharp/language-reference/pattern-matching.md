---
title: Сопоставление шаблонов (F#)
description: 'Узнайте, как шаблоны используются в F # для сравнения данных с логическими структурами, разложения данных на составные части или извлечения информации из данных.'
ms.date: 05/16/2016
ms.openlocfilehash: 5ad3d3e1a78246afdfa2948fd0fb84fa04686d30
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "45991428"
---
# <a name="pattern-matching"></a><span data-ttu-id="cbc5a-103">Сопоставление шаблонов</span><span class="sxs-lookup"><span data-stu-id="cbc5a-103">Pattern Matching</span></span>

<span data-ttu-id="cbc5a-104">Шаблоны — это правила для преобразования входных данных.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-104">Patterns are rules for transforming input data.</span></span> <span data-ttu-id="cbc5a-105">Они используются во всем языке F # для сравнения данных с логической структурой или структурами, разложения данных на составные части или извлечения информации из данных различными способами.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-105">They are used throughout the F# language to compare data with a logical structure or structures, decompose data into constituent parts, or extract information from data in various ways.</span></span>

## <a name="remarks"></a><span data-ttu-id="cbc5a-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="cbc5a-106">Remarks</span></span>

<span data-ttu-id="cbc5a-107">Шаблоны используются во многих конструкциях языка, таких как `match` выражение.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-107">Patterns are used in many language constructs, such as the `match` expression.</span></span> <span data-ttu-id="cbc5a-108">Они используются при обработке аргументов для функций в `let` привязки, лямбда-выражения и в обработчиках исключений, связанных с `try...with` выражение.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-108">They are used when you are processing arguments for functions in `let` bindings, lambda expressions, and in the exception handlers associated with the `try...with` expression.</span></span> <span data-ttu-id="cbc5a-109">Дополнительные сведения см. в разделе [выражения сопоставления](match-expressions.md), [привязки let](functions/let-bindings.md), [лямбда-выражения: `fun` ключевое слово](functions/lambda-expressions-the-fun-keyword.md), и [исключения: `try...with` Выражение](exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="cbc5a-109">For more information, see [Match Expressions](match-expressions.md), [let Bindings](functions/let-bindings.md), [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md), and [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>

<span data-ttu-id="cbc5a-110">Например, в `match` выражения, *шаблон* является то, что следует за символом вертикальной черты.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-110">For example, in the `match` expression, the *pattern* is what follows the pipe symbol.</span></span>

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

<span data-ttu-id="cbc5a-111">Каждый шаблон выступает в качестве правила для преобразования входных данных каким-либо образом.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-111">Each pattern acts as a rule for transforming input in some way.</span></span> <span data-ttu-id="cbc5a-112">В `match` выражения, каждый шаблон поочередно анализируется ли входные данные совместим с шаблоном.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-112">In the `match` expression, each pattern is examined in turn to see if the input data is compatible with the pattern.</span></span> <span data-ttu-id="cbc5a-113">Если соответствие найдено, выполняется результирующего выражения.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-113">If a match is found, the result expression is executed.</span></span> <span data-ttu-id="cbc5a-114">Если совпадение не найден, проверяется следующее правило-шаблон.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-114">If a match is not found, the next pattern rule is tested.</span></span> <span data-ttu-id="cbc5a-115">Обязательно при *условие* часть описан в [выражения сопоставления](match-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="cbc5a-115">The optional when *condition* part is explained in [Match Expressions](match-expressions.md).</span></span>

<span data-ttu-id="cbc5a-116">Поддерживаемые шаблоны приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-116">Supported patterns are shown in the following table.</span></span> <span data-ttu-id="cbc5a-117">Во время выполнения входные данные сравниваются с каждым из следующих шаблонов в порядке, указанном в таблице, и шаблонов применяются рекурсивно из сначала к последнему, как они указаны в коде и слева направо для шаблонов в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-117">At run time, the input is tested against each of the following patterns in the order listed in the table, and patterns are applied recursively, from first to last as they appear in your code, and from left to right for the patterns on each line.</span></span>

|<span data-ttu-id="cbc5a-118">name</span><span class="sxs-lookup"><span data-stu-id="cbc5a-118">Name</span></span>|<span data-ttu-id="cbc5a-119">Описание</span><span class="sxs-lookup"><span data-stu-id="cbc5a-119">Description</span></span>|<span data-ttu-id="cbc5a-120">Пример</span><span class="sxs-lookup"><span data-stu-id="cbc5a-120">Example</span></span>|
|----|-----------|-------|
|<span data-ttu-id="cbc5a-121">Шаблон константы</span><span class="sxs-lookup"><span data-stu-id="cbc5a-121">Constant pattern</span></span>|<span data-ttu-id="cbc5a-122">Любой числовой, символ, или строковый литерал, константа перечисления или определенный литеральный идентификатор</span><span class="sxs-lookup"><span data-stu-id="cbc5a-122">Any numeric, character, or string literal, an enumeration constant, or a defined literal identifier</span></span>|<span data-ttu-id="cbc5a-123">`1.0`, `"test"`, `30`, `Color.Red`</span><span class="sxs-lookup"><span data-stu-id="cbc5a-123">`1.0`, `"test"`, `30`, `Color.Red`</span></span>|
|<span data-ttu-id="cbc5a-124">Шаблон идентификатора</span><span class="sxs-lookup"><span data-stu-id="cbc5a-124">Identifier pattern</span></span>|<span data-ttu-id="cbc5a-125">Значение варианта размеченного объединения, метка исключения или ветвь активного шаблона</span><span class="sxs-lookup"><span data-stu-id="cbc5a-125">A case value of a discriminated union, an exception label, or an active pattern case</span></span>|`Some(x)`<br /><br />`Failure(msg)`|
|<span data-ttu-id="cbc5a-126">Шаблон переменной</span><span class="sxs-lookup"><span data-stu-id="cbc5a-126">Variable pattern</span></span>|<span data-ttu-id="cbc5a-127">*identifier*</span><span class="sxs-lookup"><span data-stu-id="cbc5a-127">*identifier*</span></span>|`a`|
|<span data-ttu-id="cbc5a-128">`as` Шаблон</span><span class="sxs-lookup"><span data-stu-id="cbc5a-128">`as` pattern</span></span>|<span data-ttu-id="cbc5a-129">*шаблон* как *идентификатор*</span><span class="sxs-lookup"><span data-stu-id="cbc5a-129">*pattern* as *identifier*</span></span>|`(a, b) as tuple1`|
|<span data-ttu-id="cbc5a-130">ИЛИ шаблон</span><span class="sxs-lookup"><span data-stu-id="cbc5a-130">OR pattern</span></span>|<span data-ttu-id="cbc5a-131">*шаблон1* &#124; *шаблон2*</span><span class="sxs-lookup"><span data-stu-id="cbc5a-131">*pattern1* &#124; *pattern2*</span></span>|<code>([h] &#124; [h; _])</code>|
|<span data-ttu-id="cbc5a-132">И шаблон</span><span class="sxs-lookup"><span data-stu-id="cbc5a-132">AND pattern</span></span>|<span data-ttu-id="cbc5a-133">*шаблон1* &amp; *шаблон2*</span><span class="sxs-lookup"><span data-stu-id="cbc5a-133">*pattern1* &amp; *pattern2*</span></span>|`(a, b) & (_, "test")`|
|<span data-ttu-id="cbc5a-134">Шаблон cons-списка</span><span class="sxs-lookup"><span data-stu-id="cbc5a-134">Cons pattern</span></span>|<span data-ttu-id="cbc5a-135">*Идентификатор* :: *идентификатор списка*</span><span class="sxs-lookup"><span data-stu-id="cbc5a-135">*identifier* :: *list-identifier*</span></span>|`h :: t`|
|<span data-ttu-id="cbc5a-136">Шаблон списка</span><span class="sxs-lookup"><span data-stu-id="cbc5a-136">List pattern</span></span>|<span data-ttu-id="cbc5a-137">[ *шаблон_1*;...; *pattern_n* ]</span><span class="sxs-lookup"><span data-stu-id="cbc5a-137">[ *pattern_1*; ... ; *pattern_n* ]</span></span>|`[ a; b; c ]`|
|<span data-ttu-id="cbc5a-138">Шаблон массива</span><span class="sxs-lookup"><span data-stu-id="cbc5a-138">Array pattern</span></span>|<span data-ttu-id="cbc5a-139">[&#124; *шаблон_1*;..; *pattern_n* &#124;]</span><span class="sxs-lookup"><span data-stu-id="cbc5a-139">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span></span>|<code>[&#124; a; b; c &#124;]</code>|
|<span data-ttu-id="cbc5a-140">Шаблон в круглых скобках</span><span class="sxs-lookup"><span data-stu-id="cbc5a-140">Parenthesized pattern</span></span>|<span data-ttu-id="cbc5a-141">( *шаблон* )</span><span class="sxs-lookup"><span data-stu-id="cbc5a-141">( *pattern* )</span></span>|`( a )`|
|<span data-ttu-id="cbc5a-142">Шаблон кортежа</span><span class="sxs-lookup"><span data-stu-id="cbc5a-142">Tuple pattern</span></span>|<span data-ttu-id="cbc5a-143">( *шаблон_1*,..., *pattern_n* )</span><span class="sxs-lookup"><span data-stu-id="cbc5a-143">( *pattern_1*, ... , *pattern_n* )</span></span>|`( a, b )`|
|<span data-ttu-id="cbc5a-144">Шаблон записи</span><span class="sxs-lookup"><span data-stu-id="cbc5a-144">Record pattern</span></span>|<span data-ttu-id="cbc5a-145">{ *идентификатор1* = *шаблон_1*;...; *identifier_n* = *pattern_n* }</span><span class="sxs-lookup"><span data-stu-id="cbc5a-145">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span></span>|`{ Name = name; }`|
|<span data-ttu-id="cbc5a-146">Шаблон подстановочного знака</span><span class="sxs-lookup"><span data-stu-id="cbc5a-146">Wildcard pattern</span></span>|<span data-ttu-id="cbc5a-147">_</span><span class="sxs-lookup"><span data-stu-id="cbc5a-147">_</span></span>|`_`|
|<span data-ttu-id="cbc5a-148">Шаблон вместе с аннотацией типа</span><span class="sxs-lookup"><span data-stu-id="cbc5a-148">Pattern together with type annotation</span></span>|<span data-ttu-id="cbc5a-149">*шаблон* : *типа*</span><span class="sxs-lookup"><span data-stu-id="cbc5a-149">*pattern* : *type*</span></span>|`a : int`|
|<span data-ttu-id="cbc5a-150">Шаблон проверки типа</span><span class="sxs-lookup"><span data-stu-id="cbc5a-150">Type test pattern</span></span>|<span data-ttu-id="cbc5a-151">:?</span><span class="sxs-lookup"><span data-stu-id="cbc5a-151">:?</span></span> <span data-ttu-id="cbc5a-152">*Тип* [как *идентификатор* ]</span><span class="sxs-lookup"><span data-stu-id="cbc5a-152">*type* [ as *identifier* ]</span></span>|`:? System.DateTime as dt`|
|<span data-ttu-id="cbc5a-153">Шаблон NULL</span><span class="sxs-lookup"><span data-stu-id="cbc5a-153">Null pattern</span></span>|<span data-ttu-id="cbc5a-154">null</span><span class="sxs-lookup"><span data-stu-id="cbc5a-154">null</span></span>|`null`|

## <a name="constant-patterns"></a><span data-ttu-id="cbc5a-155">Шаблоны констант</span><span class="sxs-lookup"><span data-stu-id="cbc5a-155">Constant Patterns</span></span>

<span data-ttu-id="cbc5a-156">Шаблоны констант — это числовые, символов и строковые литералы, константы перечисления (включая имя типа перечисления).</span><span class="sxs-lookup"><span data-stu-id="cbc5a-156">Constant patterns are numeric, character, and string literals, enumeration constants (with the enumeration type name included).</span></span> <span data-ttu-id="cbc5a-157">Объект `match` выражение, содержащее только шаблоны констант может сравниваться с оператором case в других языках.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-157">A `match` expression that has only constant patterns can be compared to a case statement in other languages.</span></span> <span data-ttu-id="cbc5a-158">Входные данные сравниваются с литеральным значением и шаблон считается соответствующим, если значения равны.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-158">The input is compared with the literal value and the pattern matches if the values are equal.</span></span> <span data-ttu-id="cbc5a-159">Тип литерала должен быть совместим с типом входных данных.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-159">The type of the literal must be compatible with the type of the input.</span></span>

<span data-ttu-id="cbc5a-160">В следующем примере демонстрируется использование литеральных шаблонов и также использует шаблон переменной и шаблон OR.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-160">The following example demonstrates the use of literal patterns, and also uses a variable pattern and an OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

<span data-ttu-id="cbc5a-161">Другой пример литерального шаблона — шаблон, основанный на константах перечисления.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-161">Another example of a literal pattern is a pattern based on enumeration constants.</span></span> <span data-ttu-id="cbc5a-162">При использовании констант перечисления необходимо указать имя типа перечисления.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-162">You must specify the enumeration type name when you use enumeration constants.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a><span data-ttu-id="cbc5a-163">Шаблоны идентификаторов</span><span class="sxs-lookup"><span data-stu-id="cbc5a-163">Identifier Patterns</span></span>

<span data-ttu-id="cbc5a-164">Если шаблон является строкой символов, представляющей допустимый идентификатор, форма идентификатора определяет, как соответствие будет обнаружено.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-164">If the pattern is a string of characters that forms a valid identifier, the form of the identifier determines how the pattern is matched.</span></span> <span data-ttu-id="cbc5a-165">Если идентификатор длиннее одного символа и начинается с символа верхнего регистра, компилятор пытается найти соответствие шаблону идентификатора.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-165">If the identifier is longer than a single character and starts with an uppercase character, the compiler tries to make a match to the identifier pattern.</span></span> <span data-ttu-id="cbc5a-166">Идентификатором для этого шаблона может быть значение, отмеченное литерального атрибута, размеченного объединения, идентификатор исключения или ветвь активного шаблона.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-166">The identifier for this pattern could be a value marked with the Literal attribute, a discriminated union case, an exception identifier, or an active pattern case.</span></span> <span data-ttu-id="cbc5a-167">Если не совпадающий идентификатор не найден, подбор завершается неудачей и входными данными сравнивается следующее правило-шаблон, шаблон переменной.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-167">If no matching identifier is found, the match fails and the next pattern rule, the variable pattern, is compared to the input.</span></span>

<span data-ttu-id="cbc5a-168">Шаблоны размеченных объединений могут представлять собой простые именованные или они могут иметь значение или кортеж, содержащий несколько значений.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-168">Discriminated union patterns can be simple named cases or they can have a value, or a tuple containing multiple values.</span></span> <span data-ttu-id="cbc5a-169">Если значение, необходимо указать идентификатор для значения.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-169">If there is a value, you must specify an identifier for the value.</span></span> <span data-ttu-id="cbc5a-170">В случае кортежа необходимо предоставить шаблон кортежа с идентификатором для каждого элемента кортежа или идентификатор с именем поля для одного или нескольких именованных полей объединения.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-170">In the case of a tuple, you must supply a tuple pattern with an identifier for each element of the tuple or an identifier with a field name for one or more named union fields.</span></span> <span data-ttu-id="cbc5a-171">См. в примерах кода в этом разделе вы найдете примеры.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-171">See the code examples in this section for examples.</span></span>

<span data-ttu-id="cbc5a-172">`option` Тип — это размеченное объединение, имеющее два варианта `Some` и `None`.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-172">The `option` type is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="cbc5a-173">Один случай (`Some`) имеет значение, а вторая (`None`) представляет собой просто именованную ветвь.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-173">One case (`Some`) has a value, but the other (`None`) is just a named case.</span></span> <span data-ttu-id="cbc5a-174">Таким образом `Some` должен иметь переменную для значения, связанного с `Some` , однако `None` должен записываться отдельно.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-174">Therefore, `Some` needs to have a variable for the value associated with the `Some` case, but `None` must appear by itself.</span></span> <span data-ttu-id="cbc5a-175">В следующем коде, переменная `var1` присваивается значение, полученное путем сравнения с `Some` случая.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-175">In the following code, the variable `var1` is given the value that is obtained by matching to the `Some` case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

<span data-ttu-id="cbc5a-176">В следующем примере `PersonName` размеченное объединение содержит смесь строк и символов, представляющих возможные формы имен.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-176">In the following example, the `PersonName` discriminated union contains a mixture of strings and characters that represent possible forms of names.</span></span> <span data-ttu-id="cbc5a-177">Регистр размеченное объединение `FirstOnly`, `LastOnly`, и `FirstLast`.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-177">The cases of the discriminated union are `FirstOnly`, `LastOnly`, and `FirstLast`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

<span data-ttu-id="cbc5a-178">Для размеченных объединений, имеющих именованные поля используйте знак равенства (=) для извлечения значения именованного поля.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-178">For discriminated unions that have named fields, you use the equals sign (=) to extract the value of a named field.</span></span> <span data-ttu-id="cbc5a-179">Например рассмотрим размеченное объединение с объявлением следующим образом.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-179">For example, consider a discriminated union with a declaration like the following.</span></span>

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

<span data-ttu-id="cbc5a-180">Именованные поля в выражении можно использовать следующим образом.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-180">You can use the named fields in a pattern matching expression as follows.</span></span>

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

<span data-ttu-id="cbc5a-181">Использование именованного поля необязательно, поэтому в предыдущем примере, оба `Circle(r)` и `Circle(radius = r)` дают одинаковый результат.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-181">The use of the named field is optional, so in the previous example, both `Circle(r)` and `Circle(radius = r)` have the same effect.</span></span>

<span data-ttu-id="cbc5a-182">При указании нескольких полей используйте точку с запятой (;) в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-182">When you specify multiple fields, use the semicolon (;) as a separator.</span></span>

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

<span data-ttu-id="cbc5a-183">Активные шаблоны позволяют определять более сложный настраиваемый подбор шаблона.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-183">Active patterns enable you to define more complex custom pattern matching.</span></span> <span data-ttu-id="cbc5a-184">Дополнительные сведения об активных шаблонах см. в разделе [активные шаблоны](active-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="cbc5a-184">For more information about active patterns, see [Active Patterns](active-patterns.md).</span></span>

<span data-ttu-id="cbc5a-185">При подборе шаблона в контексте обработчиков исключений используется вариант, в котором идентификатор является исключением.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-185">The case in which the identifier is an exception is used in pattern matching in the context of exception handlers.</span></span> <span data-ttu-id="cbc5a-186">Сведения о подборе шаблона при обработке исключений см. в разделе [исключения: `try...with` выражение](exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="cbc5a-186">For information about pattern matching in exception handling, see [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>

## <a name="variable-patterns"></a><span data-ttu-id="cbc5a-187">Шаблоны переменных</span><span class="sxs-lookup"><span data-stu-id="cbc5a-187">Variable Patterns</span></span>

<span data-ttu-id="cbc5a-188">Шаблон переменной присваивает сравниваемое значение имени переменной, которое становится доступным для использования в выполняемом выражении справа от `->` символов.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-188">The variable pattern assigns the value being matched to a variable name, which is then available for use in the execution expression to the right of the `->` symbol.</span></span> <span data-ttu-id="cbc5a-189">Отдельно, шаблон переменной соответствует любым входным данным, но шаблоны переменных часто используются внутри других шаблонов, что позволяет более сложные структуры, такие как кортежи и массивы позволяет разлагать на переменные.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-189">A variable pattern alone matches any input, but variable patterns often appear within other patterns, therefore enabling more complex structures such as tuples and arrays to be decomposed into variables.</span></span>

<span data-ttu-id="cbc5a-190">В следующем примере шаблон переменной внутри шаблона кортежа.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-190">The following example demonstrates a variable pattern within a tuple pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a><span data-ttu-id="cbc5a-191">как шаблон</span><span class="sxs-lookup"><span data-stu-id="cbc5a-191">as Pattern</span></span>

<span data-ttu-id="cbc5a-192">`as` Шаблон — это шаблон, который имеет `as` предложение, добавленным к нему.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-192">The `as` pattern is a pattern that has an `as` clause appended to it.</span></span> <span data-ttu-id="cbc5a-193">`as` Предложение привязывает подобранное значение к имени, который может использоваться в выполняемом выражении `match` выражения, или, в случае, когда этот шаблон используется в `let` привязки, имя добавляется в качестве привязки в локальную область видимости.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-193">The `as` clause binds the matched value to a name that can be used in the execution expression of a `match` expression, or, in the case where this pattern is used in a `let` binding, the name is added as a binding to the local scope.</span></span>

<span data-ttu-id="cbc5a-194">В следующем примере используется `as` шаблон.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-194">The following example uses an `as` pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a><span data-ttu-id="cbc5a-195">ИЛИ шаблон</span><span class="sxs-lookup"><span data-stu-id="cbc5a-195">OR Pattern</span></span>

<span data-ttu-id="cbc5a-196">Шаблон OR используется в том случае, когда входные данные могут соответствовать нескольким шаблонам и требуется выполнить тот же код, в результате.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-196">The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result.</span></span> <span data-ttu-id="cbc5a-197">Типы обеих сторон шаблона OR должны быть совместимы.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-197">The types of both sides of the OR pattern must be compatible.</span></span>

<span data-ttu-id="cbc5a-198">Ниже приведен пример шаблона OR.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-198">The following example demonstrates the OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a><span data-ttu-id="cbc5a-199">И шаблон</span><span class="sxs-lookup"><span data-stu-id="cbc5a-199">AND Pattern</span></span>

<span data-ttu-id="cbc5a-200">Шаблон AND требует, что входные данные соответствовали двум шаблонам.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-200">The AND pattern requires that the input match two patterns.</span></span> <span data-ttu-id="cbc5a-201">Типы обеих сторон шаблона AND должны быть совместимы.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-201">The types of both sides of the AND pattern must be compatible.</span></span>

<span data-ttu-id="cbc5a-202">Следующий пример аналогичен `detectZeroTuple` показано [шаблон кортежа](https://msdn.microsoft.com/library/#tuple) далее в этой статье, но здесь оба `var1` и `var2` получаются как значения с помощью шаблона.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-202">The following example is like `detectZeroTuple` shown in the [Tuple Pattern](https://msdn.microsoft.com/library/#tuple) section later in this topic, but here both `var1` and `var2` are obtained as values by using the AND pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a><span data-ttu-id="cbc5a-203">Шаблон cons-списка</span><span class="sxs-lookup"><span data-stu-id="cbc5a-203">Cons Pattern</span></span>

<span data-ttu-id="cbc5a-204">Шаблон cons-списка используется для разложения списка на первый элемент, *head*и список, содержащий остальные элементы, *заключительного*.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-204">The cons pattern is used to decompose a list into the first element, the *head*, and a list that contains the remaining elements, the *tail*.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a><span data-ttu-id="cbc5a-205">Шаблон списка</span><span class="sxs-lookup"><span data-stu-id="cbc5a-205">List Pattern</span></span>

<span data-ttu-id="cbc5a-206">Шаблон списка позволяет списков позволяет разлагать на ряд элементов.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-206">The list pattern enables lists to be decomposed into a number of elements.</span></span> <span data-ttu-id="cbc5a-207">Сам по себе шаблон списка может соответствовать только спискам определенным количеством элементов.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-207">The list pattern itself can match only lists of a specific number of elements.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a><span data-ttu-id="cbc5a-208">Шаблон массива</span><span class="sxs-lookup"><span data-stu-id="cbc5a-208">Array Pattern</span></span>

<span data-ttu-id="cbc5a-209">Шаблон массива сходен с шаблоном списка и может использоваться для разложения массивов определенной длины.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-209">The array pattern resembles the list pattern and can be used to decompose arrays of a specific length.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a><span data-ttu-id="cbc5a-210">Шаблон в круглых скобках</span><span class="sxs-lookup"><span data-stu-id="cbc5a-210">Parenthesized Pattern</span></span>

<span data-ttu-id="cbc5a-211">Можно группировать круглые скобки вокруг шаблонов для достижения требуемой ассоциативности.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-211">Parentheses can be grouped around patterns to achieve the desired associativity.</span></span> <span data-ttu-id="cbc5a-212">В следующем примере круглые скобки используются для управления ассоциативностью между шаблоном AND и шаблоном cons-списка.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-212">In the following example, parentheses are used to control associativity between an AND pattern and a cons pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a><span data-ttu-id="cbc5a-213">Шаблон кортежа</span><span class="sxs-lookup"><span data-stu-id="cbc5a-213">Tuple Pattern</span></span>

<span data-ttu-id="cbc5a-214">Шаблон кортежа соответствует входным данным в форме кортежа и позволяет кортежа позволяет разлагать на составляющие его элементы с помощью переменных подбора шаблона для каждой позиции в кортеже.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-214">The tuple pattern matches input in tuple form and enables the tuple to be decomposed into its constituent elements by using pattern matching variables for each position in the tuple.</span></span>

<span data-ttu-id="cbc5a-215">В следующем примере демонстрируется шаблон кортежа и также используются литеральные шаблоны, шаблоны переменных и Шаблон подстановочного знака.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-215">The following example demonstrates the tuple pattern and also uses literal patterns, variable patterns, and the wildcard pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a><span data-ttu-id="cbc5a-216">Шаблон записи</span><span class="sxs-lookup"><span data-stu-id="cbc5a-216">Record Pattern</span></span>

<span data-ttu-id="cbc5a-217">Шаблон записи используется для разложения записей с целью извлечения значений полей.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-217">The record pattern is used to decompose records to extract the values of fields.</span></span> <span data-ttu-id="cbc5a-218">Шаблон не обязательно должен ссылаться на все поля в записи; пропущенные поля просто не участвуют в сравнении и не извлекаются.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-218">The pattern does not have to reference all fields of the record; any omitted fields just do not participate in matching and are not extracted.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a><span data-ttu-id="cbc5a-219">Шаблон подстановочного знака</span><span class="sxs-lookup"><span data-stu-id="cbc5a-219">Wildcard Pattern</span></span>

<span data-ttu-id="cbc5a-220">Шаблон подстановочного знака представляется подчеркиванием (`_`) знака и соответствует любым входным данным, так же, как и шаблон переменной, за исключением того, что входные данные удаляются, а не присваивается переменной.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-220">The wildcard pattern is represented by the underscore (`_`) character and matches any input, just like the variable pattern, except that the input is discarded instead of assigned to a variable.</span></span> <span data-ttu-id="cbc5a-221">Шаблон подстановочного знака части используется внутри других шаблонов как заполнитель для значений, которые не требуются в выражении справа от `->` символов.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-221">The wildcard pattern is often used within other patterns as a placeholder for values that are not needed in the expression to the right of the `->` symbol.</span></span> <span data-ttu-id="cbc5a-222">Шаблон подстановочного знака также часто используется в конце списка шаблонов в соответствии с любой несопоставленных входных данных.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-222">The wildcard pattern is also frequently used at the end of a list of patterns to match any unmatched input.</span></span> <span data-ttu-id="cbc5a-223">Шаблон подстановочного знака демонстрируется во многих примерах кода в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-223">The wildcard pattern is demonstrated in many code examples in this topic.</span></span> <span data-ttu-id="cbc5a-224">См. предыдущий код для примера.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-224">See the preceding code for one example.</span></span>

## <a name="patterns-that-have-type-annotations"></a><span data-ttu-id="cbc5a-225">Шаблоны, имеющие аннотации типов</span><span class="sxs-lookup"><span data-stu-id="cbc5a-225">Patterns That Have Type Annotations</span></span>

<span data-ttu-id="cbc5a-226">Шаблоны могут иметь аннотации типов.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-226">Patterns can have type annotations.</span></span> <span data-ttu-id="cbc5a-227">Они ведут себя как другие аннотации типов и способствуют в определении типа.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-227">These behave like other type annotations and guide inference like other type annotations.</span></span> <span data-ttu-id="cbc5a-228">Круглые скобки необходимы для аннотации типов в шаблонах.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-228">Parentheses are required around type annotations in patterns.</span></span> <span data-ttu-id="cbc5a-229">В следующем коде показано шаблон, имеющий аннотацию типа.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-229">The following code shows a pattern that has a type annotation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a><span data-ttu-id="cbc5a-230">Шаблон проверки типа</span><span class="sxs-lookup"><span data-stu-id="cbc5a-230">Type Test Pattern</span></span>

<span data-ttu-id="cbc5a-231">Шаблон проверки типа используется для сопоставления входных данных с типом.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-231">The type test pattern is used to match the input against a type.</span></span> <span data-ttu-id="cbc5a-232">Если входным типом является сопоставления (или производный тип) типа, указанного в шаблоне, сопоставление выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-232">If the input type is a match to (or a derived type of) the type specified in the pattern, the match succeeds.</span></span>

<span data-ttu-id="cbc5a-233">В следующем примере шаблон проверки типа.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-233">The following example demonstrates the type test pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a><span data-ttu-id="cbc5a-234">Шаблон NULL</span><span class="sxs-lookup"><span data-stu-id="cbc5a-234">Null Pattern</span></span>

<span data-ttu-id="cbc5a-235">Шаблон null соответствует значению null, которое может появиться при работе с типами, допускающими значение null.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-235">The null pattern matches the null value that can appear when you are working with types that allow a null value.</span></span> <span data-ttu-id="cbc5a-236">Шаблоны NULL часто используются при взаимодействии с кодом .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-236">Null patterns are frequently used when interoperating with .NET Framework code.</span></span> <span data-ttu-id="cbc5a-237">Например, значение, возвращаемое .NET API может быть входными данными для `match` выражение.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-237">For example, the return value of a .NET API might be the input to a `match` expression.</span></span> <span data-ttu-id="cbc5a-238">Вы можете управлять выполнением программы на основе ли возвращаемое значение равно null, а также на основе других характеристик возвращенного значения.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-238">You can control program flow based on whether the return value is null, and also on other characteristics of the returned value.</span></span> <span data-ttu-id="cbc5a-239">Шаблон null можно использовать для предотвращения значения null в остальные программы составляющие.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-239">You can use the null pattern to prevent null values from propagating to the rest of your program.</span></span>

<span data-ttu-id="cbc5a-240">В следующем примере используется шаблон null и шаблон переменной.</span><span class="sxs-lookup"><span data-stu-id="cbc5a-240">The following example uses the null pattern and the variable pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a><span data-ttu-id="cbc5a-241">См. также</span><span class="sxs-lookup"><span data-stu-id="cbc5a-241">See also</span></span>

- [<span data-ttu-id="cbc5a-242">Выражения match</span><span class="sxs-lookup"><span data-stu-id="cbc5a-242">Match Expressions</span></span>](match-expressions.md)
- [<span data-ttu-id="cbc5a-243">Активные шаблоны</span><span class="sxs-lookup"><span data-stu-id="cbc5a-243">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="cbc5a-244">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="cbc5a-244">F# Language Reference</span></span>](index.md)
