---
title: "Сопоставление шаблонов (F#)"
description: "Узнайте, как шаблоны используются в языке F # для сравнения данных с логическими структурами, разложения данных на составные части или извлечения информации из данных."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 5562ee98-e2f1-4dcd-8e2f-16ae27baaade
ms.openlocfilehash: 7c7a3110a8f34c0c96c12d4584010a9ac4b485fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="pattern-matching"></a><span data-ttu-id="5323f-104">Сопоставление шаблонов</span><span class="sxs-lookup"><span data-stu-id="5323f-104">Pattern Matching</span></span>

<span data-ttu-id="5323f-105">Шаблоны — это правила для преобразования входных данных.</span><span class="sxs-lookup"><span data-stu-id="5323f-105">Patterns are rules for transforming input data.</span></span> <span data-ttu-id="5323f-106">Они используются в языке F # для сравнения данных с логической структурой или структурами, разложения данных на составные части или извлечения информации из данных различными способами.</span><span class="sxs-lookup"><span data-stu-id="5323f-106">They are used throughout the F# language to compare data with a logical structure or structures, decompose data into constituent parts, or extract information from data in various ways.</span></span>


## <a name="remarks"></a><span data-ttu-id="5323f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="5323f-107">Remarks</span></span>
<span data-ttu-id="5323f-108">Шаблоны используются во многих языковых конструкций, таких как `match` выражение.</span><span class="sxs-lookup"><span data-stu-id="5323f-108">Patterns are used in many language constructs, such as the `match` expression.</span></span> <span data-ttu-id="5323f-109">Они используются при обработке аргументов для функций в `let` привязок, лямбда-выражения и в обработчиках исключений, связанных с `try...with` выражения.</span><span class="sxs-lookup"><span data-stu-id="5323f-109">They are used when you are processing arguments for functions in `let` bindings, lambda expressions, and in the exception handlers associated with the `try...with` expression.</span></span> <span data-ttu-id="5323f-110">Дополнительные сведения см. в разделе [выражениях сопоставления](match-expressions.md), [привязки let](functions/let-bindings.md), [лямбда-выражения: `fun` ключевое слово](functions/lambda-expressions-the-fun-keyword.md), и [исключения: `try...with` Выражение](exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="5323f-110">For more information, see [Match Expressions](match-expressions.md), [let Bindings](functions/let-bindings.md), [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md), and [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>

<span data-ttu-id="5323f-111">Например, в `match` выражение, *шаблон* является то, что следует за символом вертикальной черты.</span><span class="sxs-lookup"><span data-stu-id="5323f-111">For example, in the `match` expression, the *pattern* is what follows the pipe symbol.</span></span>

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

<span data-ttu-id="5323f-112">Каждый шаблон выступает в качестве правила для преобразования входных данных каким-либо образом.</span><span class="sxs-lookup"><span data-stu-id="5323f-112">Each pattern acts as a rule for transforming input in some way.</span></span> <span data-ttu-id="5323f-113">В `match` выражение каждого шаблона в свою очередь исследуется на предмет того, если входные данные — совместим с шаблоном.</span><span class="sxs-lookup"><span data-stu-id="5323f-113">In the `match` expression, each pattern is examined in turn to see if the input data is compatible with the pattern.</span></span> <span data-ttu-id="5323f-114">Если найдено совпадение, выполняется результирующее выражение.</span><span class="sxs-lookup"><span data-stu-id="5323f-114">If a match is found, the result expression is executed.</span></span> <span data-ttu-id="5323f-115">Если совпадение не найдено, проверяется следующее правило-шаблон.</span><span class="sxs-lookup"><span data-stu-id="5323f-115">If a match is not found, the next pattern rule is tested.</span></span> <span data-ttu-id="5323f-116">Обязательно при *условие* часть описан в [выражениях сопоставления](match-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="5323f-116">The optional when *condition* part is explained in [Match Expressions](match-expressions.md).</span></span>

<span data-ttu-id="5323f-117">Поддерживаемые шаблоны приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="5323f-117">Supported patterns are shown in the following table.</span></span> <span data-ttu-id="5323f-118">Во время выполнения входных данных сравниваются с каждым из следующих шаблонов в порядке, указанном в таблице и шаблоны применяются рекурсивно из сначала осуществляется до места последнего появления в коде и слева направо для шаблонов в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="5323f-118">At run time, the input is tested against each of the following patterns in the order listed in the table, and patterns are applied recursively, from first to last as they appear in your code, and from left to right for the patterns on each line.</span></span>

|<span data-ttu-id="5323f-119">Имя</span><span class="sxs-lookup"><span data-stu-id="5323f-119">Name</span></span>|<span data-ttu-id="5323f-120">Описание</span><span class="sxs-lookup"><span data-stu-id="5323f-120">Description</span></span>|<span data-ttu-id="5323f-121">Пример</span><span class="sxs-lookup"><span data-stu-id="5323f-121">Example</span></span>|
|----|-----------|-------|
|<span data-ttu-id="5323f-122">Шаблон константы</span><span class="sxs-lookup"><span data-stu-id="5323f-122">Constant pattern</span></span>|<span data-ttu-id="5323f-123">Любой числовой, символ, или строковый литерал, константа перечисления или определенный литеральный идентификатор</span><span class="sxs-lookup"><span data-stu-id="5323f-123">Any numeric, character, or string literal, an enumeration constant, or a defined literal identifier</span></span>|<span data-ttu-id="5323f-124">`1.0`, `"test"`, `30`, `Color.Red`</span><span class="sxs-lookup"><span data-stu-id="5323f-124">`1.0`, `"test"`, `30`, `Color.Red`</span></span>|
|<span data-ttu-id="5323f-125">Шаблон идентификатора</span><span class="sxs-lookup"><span data-stu-id="5323f-125">Identifier pattern</span></span>|<span data-ttu-id="5323f-126">Значение варианта размеченного объединения, метка исключения или ветвь активного шаблона</span><span class="sxs-lookup"><span data-stu-id="5323f-126">A case value of a discriminated union, an exception label, or an active pattern case</span></span>|`Some(x)`<br /><br />`Failure(msg)`|
|<span data-ttu-id="5323f-127">Шаблон переменной</span><span class="sxs-lookup"><span data-stu-id="5323f-127">Variable pattern</span></span>|<span data-ttu-id="5323f-128">*identifier*</span><span class="sxs-lookup"><span data-stu-id="5323f-128">*identifier*</span></span>|`a`|
|<span data-ttu-id="5323f-129">`as`шаблон</span><span class="sxs-lookup"><span data-stu-id="5323f-129">`as` pattern</span></span>|<span data-ttu-id="5323f-130">*шаблон* как *идентификатор*</span><span class="sxs-lookup"><span data-stu-id="5323f-130">*pattern* as *identifier*</span></span>|`(a, b) as tuple1`|
|<span data-ttu-id="5323f-131">ИЛИ шаблон</span><span class="sxs-lookup"><span data-stu-id="5323f-131">OR pattern</span></span>|<span data-ttu-id="5323f-132">*pattern1* &#124; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="5323f-132">*pattern1* &#124; *pattern2*</span></span>|<code>([h] &#124; [h; _])</code>|
|<span data-ttu-id="5323f-133">И шаблон</span><span class="sxs-lookup"><span data-stu-id="5323f-133">AND pattern</span></span>|<span data-ttu-id="5323f-134">*pattern1* &amp; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="5323f-134">*pattern1* &amp; *pattern2*</span></span>|`(a, b) & (_, "test")`|
|<span data-ttu-id="5323f-135">Шаблон cons-списка</span><span class="sxs-lookup"><span data-stu-id="5323f-135">Cons pattern</span></span>|<span data-ttu-id="5323f-136">*Идентификатор* :: *идентификатор списка*</span><span class="sxs-lookup"><span data-stu-id="5323f-136">*identifier* :: *list-identifier*</span></span>|`h :: t`|
|<span data-ttu-id="5323f-137">Шаблон списка</span><span class="sxs-lookup"><span data-stu-id="5323f-137">List pattern</span></span>|<span data-ttu-id="5323f-138">[ *шаблон_1*;...; *pattern_n* ]</span><span class="sxs-lookup"><span data-stu-id="5323f-138">[ *pattern_1*; ... ; *pattern_n* ]</span></span>|`[ a; b; c ]`|
|<span data-ttu-id="5323f-139">Шаблон массива</span><span class="sxs-lookup"><span data-stu-id="5323f-139">Array pattern</span></span>|<span data-ttu-id="5323f-140">[&#124; *шаблон_1*;..; *pattern_n* &#124;]</span><span class="sxs-lookup"><span data-stu-id="5323f-140">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span></span>|<code>[&#124; a; b; c &#124;]</code>|
|<span data-ttu-id="5323f-141">Шаблон в круглых скобках</span><span class="sxs-lookup"><span data-stu-id="5323f-141">Parenthesized pattern</span></span>|<span data-ttu-id="5323f-142">( *шаблон* )</span><span class="sxs-lookup"><span data-stu-id="5323f-142">( *pattern* )</span></span>|`( a )`|
|<span data-ttu-id="5323f-143">Шаблон кортежа</span><span class="sxs-lookup"><span data-stu-id="5323f-143">Tuple pattern</span></span>|<span data-ttu-id="5323f-144">( *шаблон_1*,..., *pattern_n* )</span><span class="sxs-lookup"><span data-stu-id="5323f-144">( *pattern_1*, ... , *pattern_n* )</span></span>|`( a, b )`|
|<span data-ttu-id="5323f-145">Шаблон записи</span><span class="sxs-lookup"><span data-stu-id="5323f-145">Record pattern</span></span>|<span data-ttu-id="5323f-146">{ *идентификатор1* = *шаблон_1*;...; *identifier_n* = *pattern_n* }</span><span class="sxs-lookup"><span data-stu-id="5323f-146">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span></span>|`{ Name = name; }`|
|<span data-ttu-id="5323f-147">Шаблон подстановочного знака</span><span class="sxs-lookup"><span data-stu-id="5323f-147">Wildcard pattern</span></span>|<span data-ttu-id="5323f-148">_</span><span class="sxs-lookup"><span data-stu-id="5323f-148">_</span></span>|`_`|
|<span data-ttu-id="5323f-149">Шаблон вместе с аннотацией типа</span><span class="sxs-lookup"><span data-stu-id="5323f-149">Pattern together with type annotation</span></span>|<span data-ttu-id="5323f-150">*шаблон* : *типа*</span><span class="sxs-lookup"><span data-stu-id="5323f-150">*pattern* : *type*</span></span>|`a : int`|
|<span data-ttu-id="5323f-151">Шаблон проверки типа</span><span class="sxs-lookup"><span data-stu-id="5323f-151">Type test pattern</span></span>|<span data-ttu-id="5323f-152">:?</span><span class="sxs-lookup"><span data-stu-id="5323f-152">:?</span></span> <span data-ttu-id="5323f-153">*Тип* [как *идентификатор* ]</span><span class="sxs-lookup"><span data-stu-id="5323f-153">*type* [ as *identifier* ]</span></span>|`:? System.DateTime as dt`|
|<span data-ttu-id="5323f-154">Шаблон NULL</span><span class="sxs-lookup"><span data-stu-id="5323f-154">Null pattern</span></span>|<span data-ttu-id="5323f-155">null</span><span class="sxs-lookup"><span data-stu-id="5323f-155">null</span></span>|`null`|

## <a name="constant-patterns"></a><span data-ttu-id="5323f-156">Шаблоны констант</span><span class="sxs-lookup"><span data-stu-id="5323f-156">Constant Patterns</span></span>
<span data-ttu-id="5323f-157">Шаблоны констант — это числовые, символов и строковых литералов, констант перечисления (включая имя типа перечисления).</span><span class="sxs-lookup"><span data-stu-id="5323f-157">Constant patterns are numeric, character, and string literals, enumeration constants (with the enumeration type name included).</span></span> <span data-ttu-id="5323f-158">Объект `match` выражение, содержащее только шаблоны констант могут сравниваться с оператором case в других языках.</span><span class="sxs-lookup"><span data-stu-id="5323f-158">A `match` expression that has only constant patterns can be compared to a case statement in other languages.</span></span> <span data-ttu-id="5323f-159">Входные данные сравниваются с литеральным значением и соответствует шаблону, если значения равны.</span><span class="sxs-lookup"><span data-stu-id="5323f-159">The input is compared with the literal value and the pattern matches if the values are equal.</span></span> <span data-ttu-id="5323f-160">Тип литерала должен быть совместим с типом входных данных.</span><span class="sxs-lookup"><span data-stu-id="5323f-160">The type of the literal must be compatible with the type of the input.</span></span>

<span data-ttu-id="5323f-161">В следующем примере демонстрируется использование литеральных шаблонов и также использует шаблон переменной и или модели.</span><span class="sxs-lookup"><span data-stu-id="5323f-161">The following example demonstrates the use of literal patterns, and also uses a variable pattern and an OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

<span data-ttu-id="5323f-162">Другой пример литерального шаблона — шаблон, основанный на константы перечисления.</span><span class="sxs-lookup"><span data-stu-id="5323f-162">Another example of a literal pattern is a pattern based on enumeration constants.</span></span> <span data-ttu-id="5323f-163">Необходимо указать имя типа перечисления, при использовании константы перечисления.</span><span class="sxs-lookup"><span data-stu-id="5323f-163">You must specify the enumeration type name when you use enumeration constants.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a><span data-ttu-id="5323f-164">Шаблоны идентификаторов</span><span class="sxs-lookup"><span data-stu-id="5323f-164">Identifier Patterns</span></span>
<span data-ttu-id="5323f-165">Если шаблон строку символов, которая формирует является допустимым идентификатором, форма идентификатора определяет, как сравнивается шаблон.</span><span class="sxs-lookup"><span data-stu-id="5323f-165">If the pattern is a string of characters that forms a valid identifier, the form of the identifier determines how the pattern is matched.</span></span> <span data-ttu-id="5323f-166">Если идентификатор длиннее одного символа и начинается с символа верхнего регистра, компилятор пытается найти соответствие шаблону идентификатора.</span><span class="sxs-lookup"><span data-stu-id="5323f-166">If the identifier is longer than a single character and starts with an uppercase character, the compiler tries to make a match to the identifier pattern.</span></span> <span data-ttu-id="5323f-167">Идентификатор для этого шаблона может быть помечена как атрибут-литерал, размеченного объединения, идентификатор исключения или ветвь активного шаблона значение.</span><span class="sxs-lookup"><span data-stu-id="5323f-167">The identifier for this pattern could be a value marked with the Literal attribute, a discriminated union case, an exception identifier, or an active pattern case.</span></span> <span data-ttu-id="5323f-168">Если нет совпадающий идентификатор не найден, проверка оказывается неудачной и следующее правило-шаблон, шаблон переменной, сравнивается с входных данных.</span><span class="sxs-lookup"><span data-stu-id="5323f-168">If no matching identifier is found, the match fails and the next pattern rule, the variable pattern, is compared to the input.</span></span>

<span data-ttu-id="5323f-169">Шаблоны размеченных объединений могут быть простыми именованные классы либо могут иметь значение или кортеж, содержащий несколько значений.</span><span class="sxs-lookup"><span data-stu-id="5323f-169">Discriminated union patterns can be simple named cases or they can have a value, or a tuple containing multiple values.</span></span> <span data-ttu-id="5323f-170">Если имеется значение, необходимо указать идентификатор для значения.</span><span class="sxs-lookup"><span data-stu-id="5323f-170">If there is a value, you must specify an identifier for the value.</span></span> <span data-ttu-id="5323f-171">В случае кортежа вы должны предоставить шаблон кортежа с идентификатором для каждого элемента кортежа или идентификатор с именем поля для одного или нескольких именованных полей в объединении.</span><span class="sxs-lookup"><span data-stu-id="5323f-171">In the case of a tuple, you must supply a tuple pattern with an identifier for each element of the tuple or an identifier with a field name for one or more named union fields.</span></span> <span data-ttu-id="5323f-172">См. в примерах кода в этом разделе примеры.</span><span class="sxs-lookup"><span data-stu-id="5323f-172">See the code examples in this section for examples.</span></span>

<span data-ttu-id="5323f-173">`option` Тип — размеченного объединения, имеющее два варианта `Some` и `None`.</span><span class="sxs-lookup"><span data-stu-id="5323f-173">The `option` type is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="5323f-174">Один вариант (`Some`) имеет значение, а другой (`None`) представляет собой просто именованные ветвь.</span><span class="sxs-lookup"><span data-stu-id="5323f-174">One case (`Some`) has a value, but the other (`None`) is just a named case.</span></span> <span data-ttu-id="5323f-175">Таким образом `Some` должен иметь переменную для значения, связанного с `Some` , однако `None` должен отображаться самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="5323f-175">Therefore, `Some` needs to have a variable for the value associated with the `Some` case, but `None` must appear by itself.</span></span> <span data-ttu-id="5323f-176">В следующем коде переменной `var1` присваивается значение, полученное путем сравнения с `Some` регистр.</span><span class="sxs-lookup"><span data-stu-id="5323f-176">In the following code, the variable `var1` is given the value that is obtained by matching to the `Some` case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

<span data-ttu-id="5323f-177">В следующем примере `PersonName` размеченного объединения содержит смесь строк и символов, представляющих возможные формы имен.</span><span class="sxs-lookup"><span data-stu-id="5323f-177">In the following example, the `PersonName` discriminated union contains a mixture of strings and characters that represent possible forms of names.</span></span> <span data-ttu-id="5323f-178">Приведены случаи размеченного объединения `FirstOnly`, `LastOnly`, и `FirstLast`.</span><span class="sxs-lookup"><span data-stu-id="5323f-178">The cases of the discriminated union are `FirstOnly`, `LastOnly`, and `FirstLast`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

<span data-ttu-id="5323f-179">Размеченные объединения, которые имена полей можно использовать знак равенства (=) для извлечения значение именованного поля.</span><span class="sxs-lookup"><span data-stu-id="5323f-179">For discriminated unions that have named fields, you use the equals sign (=) to extract the value of a named field.</span></span> <span data-ttu-id="5323f-180">Например рассмотрим размеченного объединения с объявлением следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5323f-180">For example, consider a discriminated union with a declaration like the following.</span></span>

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

<span data-ttu-id="5323f-181">Указанных полей в выражении можно использовать следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5323f-181">You can use the named fields in a pattern matching expression as follows.</span></span>

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

<span data-ttu-id="5323f-182">Использование именованного поля необязательно, поэтому в предыдущем примере оба `Circle(r)` и `Circle(radius = r)` действуют одинаково.</span><span class="sxs-lookup"><span data-stu-id="5323f-182">The use of the named field is optional, so in the previous example, both `Circle(r)` and `Circle(radius = r)` have the same effect.</span></span>

<span data-ttu-id="5323f-183">При указании нескольких полей, используйте точку с запятой (;) в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="5323f-183">When you specify multiple fields, use the semicolon (;) as a separator.</span></span>

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

<span data-ttu-id="5323f-184">Активные шаблоны позволяют определять более сложные сопоставления пользовательских шаблонов.</span><span class="sxs-lookup"><span data-stu-id="5323f-184">Active patterns enable you to define more complex custom pattern matching.</span></span> <span data-ttu-id="5323f-185">Дополнительные сведения об активных шаблонах см. в разделе [активные шаблоны](active-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="5323f-185">For more information about active patterns, see [Active Patterns](active-patterns.md).</span></span>

<span data-ttu-id="5323f-186">Так, в которой идентификатор является исключением используется в шаблона в контексте обработчиков исключений.</span><span class="sxs-lookup"><span data-stu-id="5323f-186">The case in which the identifier is an exception is used in pattern matching in the context of exception handlers.</span></span> <span data-ttu-id="5323f-187">Сведения о подборе шаблона при обработке исключений см. в разделе [исключения: `try...with` выражение](exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="5323f-187">For information about pattern matching in exception handling, see [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>


## <a name="variable-patterns"></a><span data-ttu-id="5323f-188">Шаблоны переменных</span><span class="sxs-lookup"><span data-stu-id="5323f-188">Variable Patterns</span></span>
<span data-ttu-id="5323f-189">Шаблон переменной присваивает сравниваемое значение имени переменной, которое затем становится доступным для использования в выражении справа от выполнения `->` символов.</span><span class="sxs-lookup"><span data-stu-id="5323f-189">The variable pattern assigns the value being matched to a variable name, which is then available for use in the execution expression to the right of the `->` symbol.</span></span> <span data-ttu-id="5323f-190">Сама по себе шаблон переменной соответствует любым входным данным, однако шаблоны переменных часто используются внутри других шаблонов, что более сложные структуры, таких как кортежи и массивы, чтобы разложить на переменные.</span><span class="sxs-lookup"><span data-stu-id="5323f-190">A variable pattern alone matches any input, but variable patterns often appear within other patterns, therefore enabling more complex structures such as tuples and arrays to be decomposed into variables.</span></span>

<span data-ttu-id="5323f-191">В следующем примере показано шаблон переменной внутри шаблона кортежа.</span><span class="sxs-lookup"><span data-stu-id="5323f-191">The following example demonstrates a variable pattern within a tuple pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a><span data-ttu-id="5323f-192">AS-шаблон</span><span class="sxs-lookup"><span data-stu-id="5323f-192">as Pattern</span></span>
<span data-ttu-id="5323f-193">`as` Шаблон — это шаблон, который имеет `as` предложение, добавленным к нему.</span><span class="sxs-lookup"><span data-stu-id="5323f-193">The `as` pattern is a pattern that has an `as` clause appended to it.</span></span> <span data-ttu-id="5323f-194">`as` Предложение привязывает совпадающее значение имени, которое может использоваться в выражении выполнения `match` выражения, или в случае, когда этот шаблон используется в `let` привязки, имя добавляется в качестве привязки в локальную область видимости.</span><span class="sxs-lookup"><span data-stu-id="5323f-194">The `as` clause binds the matched value to a name that can be used in the execution expression of a `match` expression, or, in the case where this pattern is used in a `let` binding, the name is added as a binding to the local scope.</span></span>

<span data-ttu-id="5323f-195">В следующем примере используется `as` шаблон.</span><span class="sxs-lookup"><span data-stu-id="5323f-195">The following example uses an `as` pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a><span data-ttu-id="5323f-196">ИЛИ шаблон</span><span class="sxs-lookup"><span data-stu-id="5323f-196">OR Pattern</span></span>
<span data-ttu-id="5323f-197">Шаблон OR используется в том случае, когда входные данные могут соответствовать нескольким шаблонам, необходимо выполнить в результате тот же код.</span><span class="sxs-lookup"><span data-stu-id="5323f-197">The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result.</span></span> <span data-ttu-id="5323f-198">Типы обеих сторон шаблона OR должны быть совместимыми.</span><span class="sxs-lookup"><span data-stu-id="5323f-198">The types of both sides of the OR pattern must be compatible.</span></span>

<span data-ttu-id="5323f-199">Ниже приведен пример шаблона OR.</span><span class="sxs-lookup"><span data-stu-id="5323f-199">The following example demonstrates the OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a><span data-ttu-id="5323f-200">И шаблон</span><span class="sxs-lookup"><span data-stu-id="5323f-200">AND Pattern</span></span>
<span data-ttu-id="5323f-201">Шаблон AND требует, что входные данные соответствовали двум шаблонам.</span><span class="sxs-lookup"><span data-stu-id="5323f-201">The AND pattern requires that the input match two patterns.</span></span> <span data-ttu-id="5323f-202">Типы обеих сторон шаблона должны быть совместимыми.</span><span class="sxs-lookup"><span data-stu-id="5323f-202">The types of both sides of the AND pattern must be compatible.</span></span>

<span data-ttu-id="5323f-203">Следующий пример аналогичен `detectZeroTuple` показано [шаблон кортежа](https://msdn.microsoft.com/library/#tuple) далее в этом разделе, но здесь одновременно `var1` и `var2` получаются как значения с помощью шаблона.</span><span class="sxs-lookup"><span data-stu-id="5323f-203">The following example is like `detectZeroTuple` shown in the [Tuple Pattern](https://msdn.microsoft.com/library/#tuple) section later in this topic, but here both `var1` and `var2` are obtained as values by using the AND pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a><span data-ttu-id="5323f-204">Шаблон cons-списка</span><span class="sxs-lookup"><span data-stu-id="5323f-204">Cons Pattern</span></span>
<span data-ttu-id="5323f-205">Шаблон cons-списка используется для разложения списка на первый элемент, *head*и список, содержащий остальные элементы *заключительного*.</span><span class="sxs-lookup"><span data-stu-id="5323f-205">The cons pattern is used to decompose a list into the first element, the *head*, and a list that contains the remaining elements, the *tail*.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a><span data-ttu-id="5323f-206">Шаблон списка</span><span class="sxs-lookup"><span data-stu-id="5323f-206">List Pattern</span></span>
<span data-ttu-id="5323f-207">Шаблон списка позволяет списки, чтобы разложить на количество элементов.</span><span class="sxs-lookup"><span data-stu-id="5323f-207">The list pattern enables lists to be decomposed into a number of elements.</span></span> <span data-ttu-id="5323f-208">Сам по себе шаблон списка может соответствовать только списки ряд элементов.</span><span class="sxs-lookup"><span data-stu-id="5323f-208">The list pattern itself can match only lists of a specific number of elements.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a><span data-ttu-id="5323f-209">Шаблон массива</span><span class="sxs-lookup"><span data-stu-id="5323f-209">Array Pattern</span></span>
<span data-ttu-id="5323f-210">Шаблон массива сходен с шаблоном списка и может использоваться для разложения массивов определенной длины.</span><span class="sxs-lookup"><span data-stu-id="5323f-210">The array pattern resembles the list pattern and can be used to decompose arrays of a specific length.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a><span data-ttu-id="5323f-211">Шаблон в круглых скобках</span><span class="sxs-lookup"><span data-stu-id="5323f-211">Parenthesized Pattern</span></span>
<span data-ttu-id="5323f-212">Можно группировать круглые скобки вокруг шаблонов для достижения требуемой ассоциативности.</span><span class="sxs-lookup"><span data-stu-id="5323f-212">Parentheses can be grouped around patterns to achieve the desired associativity.</span></span> <span data-ttu-id="5323f-213">В следующем примере круглые скобки используются для управления ассоциативностью между шаблоном AND и шаблоном cons-списка.</span><span class="sxs-lookup"><span data-stu-id="5323f-213">In the following example, parentheses are used to control associativity between an AND pattern and a cons pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a><span data-ttu-id="5323f-214">Шаблон кортежа</span><span class="sxs-lookup"><span data-stu-id="5323f-214">Tuple Pattern</span></span>
<span data-ttu-id="5323f-215">Шаблон кортежа соответствует входным данным в форме кортежа и позволяет разложить на его составляющие элементы с помощью сопоставления переменных для каждой позиции в кортеже шаблона кортеж.</span><span class="sxs-lookup"><span data-stu-id="5323f-215">The tuple pattern matches input in tuple form and enables the tuple to be decomposed into its constituent elements by using pattern matching variables for each position in the tuple.</span></span>

<span data-ttu-id="5323f-216">В следующем примере демонстрируется шаблон кортежа и также использует литеральных шаблонов, шаблоны переменных и Шаблон подстановочного знака.</span><span class="sxs-lookup"><span data-stu-id="5323f-216">The following example demonstrates the tuple pattern and also uses literal patterns, variable patterns, and the wildcard pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a><span data-ttu-id="5323f-217">Шаблон записи</span><span class="sxs-lookup"><span data-stu-id="5323f-217">Record Pattern</span></span>
<span data-ttu-id="5323f-218">Шаблон записи используется для разложения записей с целью извлечения значения полей.</span><span class="sxs-lookup"><span data-stu-id="5323f-218">The record pattern is used to decompose records to extract the values of fields.</span></span> <span data-ttu-id="5323f-219">Шаблон не должен ссылаться на все поля в записи; пропущенные поля просто не участвуют в сравнении и не извлекаются.</span><span class="sxs-lookup"><span data-stu-id="5323f-219">The pattern does not have to reference all fields of the record; any omitted fields just do not participate in matching and are not extracted.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a><span data-ttu-id="5323f-220">Шаблон подстановочного знака</span><span class="sxs-lookup"><span data-stu-id="5323f-220">Wildcard Pattern</span></span>
<span data-ttu-id="5323f-221">Шаблон подстановочного знака представляется символ подчеркивания (`_`) символов и соответствует любым входным данным, так же, как шаблон переменной, за исключением того, что входные данные удаляются, а не присваивается переменной.</span><span class="sxs-lookup"><span data-stu-id="5323f-221">The wildcard pattern is represented by the underscore (`_`) character and matches any input, just like the variable pattern, except that the input is discarded instead of assigned to a variable.</span></span> <span data-ttu-id="5323f-222">Шаблон подстановочного знака часто используется внутри других шаблонов в качестве заполнителя для значений, которые не требуются в выражении справа от `->` символов.</span><span class="sxs-lookup"><span data-stu-id="5323f-222">The wildcard pattern is often used within other patterns as a placeholder for values that are not needed in the expression to the right of the `->` symbol.</span></span> <span data-ttu-id="5323f-223">Шаблон подстановочного знака также часто используются для сопоставления всех несопоставленных входных данных в конце списка шаблонов.</span><span class="sxs-lookup"><span data-stu-id="5323f-223">The wildcard pattern is also frequently used at the end of a list of patterns to match any unmatched input.</span></span> <span data-ttu-id="5323f-224">Многие примеры кода в этом разделе демонстрируется шаблон подстановочного знака.</span><span class="sxs-lookup"><span data-stu-id="5323f-224">The wildcard pattern is demonstrated in many code examples in this topic.</span></span> <span data-ttu-id="5323f-225">См. предыдущий код для примера.</span><span class="sxs-lookup"><span data-stu-id="5323f-225">See the preceding code for one example.</span></span>


## <a name="patterns-that-have-type-annotations"></a><span data-ttu-id="5323f-226">Шаблоны, имеющие аннотации типов</span><span class="sxs-lookup"><span data-stu-id="5323f-226">Patterns That Have Type Annotations</span></span>
<span data-ttu-id="5323f-227">Шаблоны могут иметь аннотации типа.</span><span class="sxs-lookup"><span data-stu-id="5323f-227">Patterns can have type annotations.</span></span> <span data-ttu-id="5323f-228">Они ведут себя как другие аннотации типов и способствуют в определении типа.</span><span class="sxs-lookup"><span data-stu-id="5323f-228">These behave like other type annotations and guide inference like other type annotations.</span></span> <span data-ttu-id="5323f-229">Круглые скобки необходимы для аннотации типов в шаблонах.</span><span class="sxs-lookup"><span data-stu-id="5323f-229">Parentheses are required around type annotations in patterns.</span></span> <span data-ttu-id="5323f-230">Ниже приведен шаблон, имеющий аннотацию типа.</span><span class="sxs-lookup"><span data-stu-id="5323f-230">The following code shows a pattern that has a type annotation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a><span data-ttu-id="5323f-231">Шаблон проверки типа</span><span class="sxs-lookup"><span data-stu-id="5323f-231">Type Test Pattern</span></span>
<span data-ttu-id="5323f-232">Шаблон проверки типа используется для сопоставления входных данных с типом.</span><span class="sxs-lookup"><span data-stu-id="5323f-232">The type test pattern is used to match the input against a type.</span></span> <span data-ttu-id="5323f-233">Если входным типом является сопоставления (или производный тип) типа, указанного в шаблоне, сопоставление выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="5323f-233">If the input type is a match to (or a derived type of) the type specified in the pattern, the match succeeds.</span></span>

<span data-ttu-id="5323f-234">В следующем примере показано шаблон проверки типа.</span><span class="sxs-lookup"><span data-stu-id="5323f-234">The following example demonstrates the type test pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a><span data-ttu-id="5323f-235">Шаблон NULL</span><span class="sxs-lookup"><span data-stu-id="5323f-235">Null Pattern</span></span>
<span data-ttu-id="5323f-236">Шаблон null соответствует значению null, которое может появиться при работе с типами, допускающими значение null.</span><span class="sxs-lookup"><span data-stu-id="5323f-236">The null pattern matches the null value that can appear when you are working with types that allow a null value.</span></span> <span data-ttu-id="5323f-237">Шаблоны NULL часто используются при взаимодействии с кодом .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5323f-237">Null patterns are frequently used when interoperating with .NET Framework code.</span></span> <span data-ttu-id="5323f-238">Например, значение, возвращаемое .NET API может быть входными данными для `match` выражение.</span><span class="sxs-lookup"><span data-stu-id="5323f-238">For example, the return value of a .NET API might be the input to a `match` expression.</span></span> <span data-ttu-id="5323f-239">Можно управлять выполнением программы на основе ли возвращаемое значение равно null, а также другие характеристики возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="5323f-239">You can control program flow based on whether the return value is null, and also on other characteristics of the returned value.</span></span> <span data-ttu-id="5323f-240">Шаблон null можно использовать для предотвращения распространения для остальной части программы значения null.</span><span class="sxs-lookup"><span data-stu-id="5323f-240">You can use the null pattern to prevent null values from propagating to the rest of your program.</span></span>

<span data-ttu-id="5323f-241">В следующем примере используется шаблон null и шаблон переменной.</span><span class="sxs-lookup"><span data-stu-id="5323f-241">The following example uses the null pattern and the variable pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a><span data-ttu-id="5323f-242">См. также</span><span class="sxs-lookup"><span data-stu-id="5323f-242">See Also</span></span>
[<span data-ttu-id="5323f-243">Выражения match</span><span class="sxs-lookup"><span data-stu-id="5323f-243">Match Expressions</span></span>](match-expressions.md)

[<span data-ttu-id="5323f-244">Активные шаблоны</span><span class="sxs-lookup"><span data-stu-id="5323f-244">Active Patterns</span></span>](active-patterns.md)

[<span data-ttu-id="5323f-245">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="5323f-245">F# Language Reference</span></span>](index.md)
