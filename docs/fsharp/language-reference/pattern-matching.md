---
title: Сопоставление шаблонов
description: Сведения о том, как шаблоны F# используются для сравнения данных с логическими структурами, разложения данных на составляющие части или извлечения информации из данных.
ms.date: 10/27/2019
ms.openlocfilehash: 1acb795cbe5581898ae5e1439098f906a8a16b93
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73041012"
---
# <a name="pattern-matching"></a><span data-ttu-id="a77a8-103">Сопоставление шаблонов</span><span class="sxs-lookup"><span data-stu-id="a77a8-103">Pattern Matching</span></span>

<span data-ttu-id="a77a8-104">Шаблоны — это правила для преобразования входных данных.</span><span class="sxs-lookup"><span data-stu-id="a77a8-104">Patterns are rules for transforming input data.</span></span> <span data-ttu-id="a77a8-105">Они используются на всех F# языках для сравнения данных с логической структурой или структурами, разложения данных в составные части или извлечения информации из данных различными способами.</span><span class="sxs-lookup"><span data-stu-id="a77a8-105">They are used throughout the F# language to compare data with a logical structure or structures, decompose data into constituent parts, or extract information from data in various ways.</span></span>

## <a name="remarks"></a><span data-ttu-id="a77a8-106">Заметки</span><span class="sxs-lookup"><span data-stu-id="a77a8-106">Remarks</span></span>

<span data-ttu-id="a77a8-107">Шаблоны используются во многих языковых конструкциях, например в `match` выражении.</span><span class="sxs-lookup"><span data-stu-id="a77a8-107">Patterns are used in many language constructs, such as the `match` expression.</span></span> <span data-ttu-id="a77a8-108">Они используются при обработке аргументов для функций в `let` привязках, лямбда-выражениях и в обработчиках исключений, связанных с выражением `try...with`.</span><span class="sxs-lookup"><span data-stu-id="a77a8-108">They are used when you are processing arguments for functions in `let` bindings, lambda expressions, and in the exception handlers associated with the `try...with` expression.</span></span> <span data-ttu-id="a77a8-109">Дополнительные сведения см. в разделе [выражения Match](match-expressions.md), [Привязка let](./functions/let-bindings.md), [лямбда-выражения: ключевое слово `fun`](./functions/lambda-expressions-the-fun-keyword.md)и [исключения: выражение `try...with`](./exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="a77a8-109">For more information, see [Match Expressions](match-expressions.md), [let Bindings](./functions/let-bindings.md), [Lambda Expressions: The `fun` Keyword](./functions/lambda-expressions-the-fun-keyword.md), and [Exceptions: The `try...with` Expression](./exception-handling/the-try-with-expression.md).</span></span>

<span data-ttu-id="a77a8-110">Например, в выражении `match` *шаблон* соответствует символу вертикальной черты.</span><span class="sxs-lookup"><span data-stu-id="a77a8-110">For example, in the `match` expression, the *pattern* is what follows the pipe symbol.</span></span>

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

<span data-ttu-id="a77a8-111">Каждый шаблон выступает в качестве правила для преобразования входных данных каким-либо образом.</span><span class="sxs-lookup"><span data-stu-id="a77a8-111">Each pattern acts as a rule for transforming input in some way.</span></span> <span data-ttu-id="a77a8-112">В `match` выражении каждый шаблон просматривается, в свою очередь, чтобы проверить, совместимы ли входные данные с шаблоном.</span><span class="sxs-lookup"><span data-stu-id="a77a8-112">In the `match` expression, each pattern is examined in turn to see if the input data is compatible with the pattern.</span></span> <span data-ttu-id="a77a8-113">При обнаружении совпадения выполняется результирующее выражение.</span><span class="sxs-lookup"><span data-stu-id="a77a8-113">If a match is found, the result expression is executed.</span></span> <span data-ttu-id="a77a8-114">Если совпадение не найдено, проверяется следующее правило шаблона.</span><span class="sxs-lookup"><span data-stu-id="a77a8-114">If a match is not found, the next pattern rule is tested.</span></span> <span data-ttu-id="a77a8-115">Необязательная часть *условия* when объясняется в [выражениях Match](match-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a77a8-115">The optional when *condition* part is explained in [Match Expressions](match-expressions.md).</span></span>

<span data-ttu-id="a77a8-116">Поддерживаемые шаблоны показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a77a8-116">Supported patterns are shown in the following table.</span></span> <span data-ttu-id="a77a8-117">Во время выполнения входные данные тестируются по каждому из следующих шаблонов в порядке, указанном в таблице, а шаблоны применяются рекурсивно, от первого до последнего, как они отображаются в коде, и слева направо для шаблонов в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="a77a8-117">At run time, the input is tested against each of the following patterns in the order listed in the table, and patterns are applied recursively, from first to last as they appear in your code, and from left to right for the patterns on each line.</span></span>

|<span data-ttu-id="a77a8-118">Название</span><span class="sxs-lookup"><span data-stu-id="a77a8-118">Name</span></span>|<span data-ttu-id="a77a8-119">Описание</span><span class="sxs-lookup"><span data-stu-id="a77a8-119">Description</span></span>|<span data-ttu-id="a77a8-120">Пример</span><span class="sxs-lookup"><span data-stu-id="a77a8-120">Example</span></span>|
|----|-----------|-------|
|<span data-ttu-id="a77a8-121">Шаблон константы</span><span class="sxs-lookup"><span data-stu-id="a77a8-121">Constant pattern</span></span>|<span data-ttu-id="a77a8-122">Любой числовой, символьный или строковый литерал, константа перечисления или определенный литеральный идентификатор</span><span class="sxs-lookup"><span data-stu-id="a77a8-122">Any numeric, character, or string literal, an enumeration constant, or a defined literal identifier</span></span>|<span data-ttu-id="a77a8-123">`1.0`, `"test"`, `30`, `Color.Red`</span><span class="sxs-lookup"><span data-stu-id="a77a8-123">`1.0`, `"test"`, `30`, `Color.Red`</span></span>|
|<span data-ttu-id="a77a8-124">Шаблон идентификатора</span><span class="sxs-lookup"><span data-stu-id="a77a8-124">Identifier pattern</span></span>|<span data-ttu-id="a77a8-125">Значение варианта для размеченного объединения, метки исключения или активного варианта шаблона</span><span class="sxs-lookup"><span data-stu-id="a77a8-125">A case value of a discriminated union, an exception label, or an active pattern case</span></span>|`Some(x)`<br /><br />`Failure(msg)`|
|<span data-ttu-id="a77a8-126">Шаблон переменной</span><span class="sxs-lookup"><span data-stu-id="a77a8-126">Variable pattern</span></span>|<span data-ttu-id="a77a8-127">*identifier*</span><span class="sxs-lookup"><span data-stu-id="a77a8-127">*identifier*</span></span>|`a`|
|<span data-ttu-id="a77a8-128">шаблон `as`</span><span class="sxs-lookup"><span data-stu-id="a77a8-128">`as` pattern</span></span>|<span data-ttu-id="a77a8-129">*шаблон* в качестве *идентификатора*</span><span class="sxs-lookup"><span data-stu-id="a77a8-129">*pattern* as *identifier*</span></span>|`(a, b) as tuple1`|
|<span data-ttu-id="a77a8-130">ИЛИ шаблон</span><span class="sxs-lookup"><span data-stu-id="a77a8-130">OR pattern</span></span>|<span data-ttu-id="a77a8-131">*pattern1* &#124; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="a77a8-131">*pattern1* &#124; *pattern2*</span></span>|<code>([h] &#124; [h; _])</code>|
|<span data-ttu-id="a77a8-132">И шаблон</span><span class="sxs-lookup"><span data-stu-id="a77a8-132">AND pattern</span></span>|<span data-ttu-id="a77a8-133">*pattern1* &amp; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="a77a8-133">*pattern1* &amp; *pattern2*</span></span>|`(a, b) & (_, "test")`|
|<span data-ttu-id="a77a8-134">Шаблон «против»</span><span class="sxs-lookup"><span data-stu-id="a77a8-134">Cons pattern</span></span>|<span data-ttu-id="a77a8-135">*идентификатор* :: *List-identifier*</span><span class="sxs-lookup"><span data-stu-id="a77a8-135">*identifier* :: *list-identifier*</span></span>|`h :: t`|
|<span data-ttu-id="a77a8-136">Шаблон списка</span><span class="sxs-lookup"><span data-stu-id="a77a8-136">List pattern</span></span>|<span data-ttu-id="a77a8-137">[ *pattern_1*;...; *pattern_n* ]</span><span class="sxs-lookup"><span data-stu-id="a77a8-137">[ *pattern_1*; ... ; *pattern_n* ]</span></span>|`[ a; b; c ]`|
|<span data-ttu-id="a77a8-138">Шаблон массива</span><span class="sxs-lookup"><span data-stu-id="a77a8-138">Array pattern</span></span>|<span data-ttu-id="a77a8-139">[&#124; *pattern_1*;..; *pattern_n* &#124;]</span><span class="sxs-lookup"><span data-stu-id="a77a8-139">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span></span>|<code>[&#124; a; b; c &#124;]</code>|
|<span data-ttu-id="a77a8-140">Шаблон в круглых скобках</span><span class="sxs-lookup"><span data-stu-id="a77a8-140">Parenthesized pattern</span></span>|<span data-ttu-id="a77a8-141">( *шаблон* )</span><span class="sxs-lookup"><span data-stu-id="a77a8-141">( *pattern* )</span></span>|`( a )`|
|<span data-ttu-id="a77a8-142">Шаблон кортежа</span><span class="sxs-lookup"><span data-stu-id="a77a8-142">Tuple pattern</span></span>|<span data-ttu-id="a77a8-143">( *pattern_1*,..., *pattern_n* )</span><span class="sxs-lookup"><span data-stu-id="a77a8-143">( *pattern_1*, ... , *pattern_n* )</span></span>|`( a, b )`|
|<span data-ttu-id="a77a8-144">Шаблон записи</span><span class="sxs-lookup"><span data-stu-id="a77a8-144">Record pattern</span></span>|<span data-ttu-id="a77a8-145">{ *идентификатор1* = *pattern_1*;...; *identifier_n* = *pattern_n* }</span><span class="sxs-lookup"><span data-stu-id="a77a8-145">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span></span>|`{ Name = name; }`|
|<span data-ttu-id="a77a8-146">Шаблон подстановочного знака</span><span class="sxs-lookup"><span data-stu-id="a77a8-146">Wildcard pattern</span></span>|<span data-ttu-id="a77a8-147">_</span><span class="sxs-lookup"><span data-stu-id="a77a8-147">_</span></span>|`_`|
|<span data-ttu-id="a77a8-148">Шаблон вместе с аннотацией типа</span><span class="sxs-lookup"><span data-stu-id="a77a8-148">Pattern together with type annotation</span></span>|<span data-ttu-id="a77a8-149">*шаблон* : *тип*</span><span class="sxs-lookup"><span data-stu-id="a77a8-149">*pattern* : *type*</span></span>|`a : int`|
|<span data-ttu-id="a77a8-150">Шаблон проверки типа</span><span class="sxs-lookup"><span data-stu-id="a77a8-150">Type test pattern</span></span>|<span data-ttu-id="a77a8-151">:?</span><span class="sxs-lookup"><span data-stu-id="a77a8-151">:?</span></span> <span data-ttu-id="a77a8-152">*введите* [как *идентификатор* ]</span><span class="sxs-lookup"><span data-stu-id="a77a8-152">*type* [ as *identifier* ]</span></span>|`:? System.DateTime as dt`|
|<span data-ttu-id="a77a8-153">Шаблон NULL</span><span class="sxs-lookup"><span data-stu-id="a77a8-153">Null pattern</span></span>|<span data-ttu-id="a77a8-154">null</span><span class="sxs-lookup"><span data-stu-id="a77a8-154">null</span></span>|`null`|

## <a name="constant-patterns"></a><span data-ttu-id="a77a8-155">Шаблоны констант</span><span class="sxs-lookup"><span data-stu-id="a77a8-155">Constant Patterns</span></span>

<span data-ttu-id="a77a8-156">Шаблоны констант — это числовые, символьные и строковые литералы, константы перечисления (с включаемым именем типа перечисления).</span><span class="sxs-lookup"><span data-stu-id="a77a8-156">Constant patterns are numeric, character, and string literals, enumeration constants (with the enumeration type name included).</span></span> <span data-ttu-id="a77a8-157">Выражение `match`, имеющее только постоянные шаблоны, можно сравнивать с оператором case на других языках.</span><span class="sxs-lookup"><span data-stu-id="a77a8-157">A `match` expression that has only constant patterns can be compared to a case statement in other languages.</span></span> <span data-ttu-id="a77a8-158">Входные данные сравниваются с литеральным значением, а шаблон соответствует, если значения равны.</span><span class="sxs-lookup"><span data-stu-id="a77a8-158">The input is compared with the literal value and the pattern matches if the values are equal.</span></span> <span data-ttu-id="a77a8-159">Тип литерала должен быть совместим с типом входных данных.</span><span class="sxs-lookup"><span data-stu-id="a77a8-159">The type of the literal must be compatible with the type of the input.</span></span>

<span data-ttu-id="a77a8-160">В следующем примере демонстрируется использование литеральных шаблонов, а также используется шаблон переменной и шаблон или.</span><span class="sxs-lookup"><span data-stu-id="a77a8-160">The following example demonstrates the use of literal patterns, and also uses a variable pattern and an OR pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

<span data-ttu-id="a77a8-161">Еще один пример литерального шаблона — это шаблон, основанный на константах перечисления.</span><span class="sxs-lookup"><span data-stu-id="a77a8-161">Another example of a literal pattern is a pattern based on enumeration constants.</span></span> <span data-ttu-id="a77a8-162">При использовании констант перечисления необходимо указать имя типа перечисления.</span><span class="sxs-lookup"><span data-stu-id="a77a8-162">You must specify the enumeration type name when you use enumeration constants.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a><span data-ttu-id="a77a8-163">Шаблоны идентификаторов</span><span class="sxs-lookup"><span data-stu-id="a77a8-163">Identifier Patterns</span></span>

<span data-ttu-id="a77a8-164">Если шаблон представляет собой строку символов, образующих допустимый идентификатор, форма идентификатора определяет способ сопоставления шаблона.</span><span class="sxs-lookup"><span data-stu-id="a77a8-164">If the pattern is a string of characters that forms a valid identifier, the form of the identifier determines how the pattern is matched.</span></span> <span data-ttu-id="a77a8-165">Если идентификатор длиннее одного символа и начинается с символа верхнего регистра, компилятор пытается выполнить сопоставление с шаблоном идентификатора.</span><span class="sxs-lookup"><span data-stu-id="a77a8-165">If the identifier is longer than a single character and starts with an uppercase character, the compiler tries to make a match to the identifier pattern.</span></span> <span data-ttu-id="a77a8-166">Идентификатором для этого шаблона может быть значение, помеченное атрибутом Literal, вариантом размеченного объединения, идентификатором исключения или активным шаблоном.</span><span class="sxs-lookup"><span data-stu-id="a77a8-166">The identifier for this pattern could be a value marked with the Literal attribute, a discriminated union case, an exception identifier, or an active pattern case.</span></span> <span data-ttu-id="a77a8-167">Если соответствующий идентификатор не найден, сопоставление завершается ошибкой, а следующее правило шаблона, шаблон переменной, сравнивается с входными данными.</span><span class="sxs-lookup"><span data-stu-id="a77a8-167">If no matching identifier is found, the match fails and the next pattern rule, the variable pattern, is compared to the input.</span></span>

<span data-ttu-id="a77a8-168">Шаблоны размеченного объединения могут быть простыми именованными вариантами или иметь значение или кортеж, содержащий несколько значений.</span><span class="sxs-lookup"><span data-stu-id="a77a8-168">Discriminated union patterns can be simple named cases or they can have a value, or a tuple containing multiple values.</span></span> <span data-ttu-id="a77a8-169">Если имеется значение, необходимо указать идентификатор для этого значения.</span><span class="sxs-lookup"><span data-stu-id="a77a8-169">If there is a value, you must specify an identifier for the value.</span></span> <span data-ttu-id="a77a8-170">В случае кортежа необходимо предоставить шаблон кортежа с идентификатором для каждого элемента кортежа или идентификатором с именем поля для одного или нескольких именованных полей объединения.</span><span class="sxs-lookup"><span data-stu-id="a77a8-170">In the case of a tuple, you must supply a tuple pattern with an identifier for each element of the tuple or an identifier with a field name for one or more named union fields.</span></span> <span data-ttu-id="a77a8-171">Примеры см. в примерах кода в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="a77a8-171">See the code examples in this section for examples.</span></span>

<span data-ttu-id="a77a8-172">Тип `option` — это размеченное объединение, которое имеет два варианта: `Some` и `None`.</span><span class="sxs-lookup"><span data-stu-id="a77a8-172">The `option` type is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="a77a8-173">Один вариант (`Some`) имеет значение, а другое (`None`) — только именованный вариант.</span><span class="sxs-lookup"><span data-stu-id="a77a8-173">One case (`Some`) has a value, but the other (`None`) is just a named case.</span></span> <span data-ttu-id="a77a8-174">Таким образом, `Some` должен иметь переменную для значения, связанного с `Some`ным вариантом, но `None` должен быть сам по себе.</span><span class="sxs-lookup"><span data-stu-id="a77a8-174">Therefore, `Some` needs to have a variable for the value associated with the `Some` case, but `None` must appear by itself.</span></span> <span data-ttu-id="a77a8-175">В следующем коде переменной `var1` присваивается значение, полученное путем сопоставления с `Some`ным вариантом.</span><span class="sxs-lookup"><span data-stu-id="a77a8-175">In the following code, the variable `var1` is given the value that is obtained by matching to the `Some` case.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

<span data-ttu-id="a77a8-176">В следующем примере `PersonName` размеченное объединение содержит сочетание строк и символов, представляющих возможные формы имен.</span><span class="sxs-lookup"><span data-stu-id="a77a8-176">In the following example, the `PersonName` discriminated union contains a mixture of strings and characters that represent possible forms of names.</span></span> <span data-ttu-id="a77a8-177">Варианты размеченного объединения: `FirstOnly`, `LastOnly`и `FirstLast`.</span><span class="sxs-lookup"><span data-stu-id="a77a8-177">The cases of the discriminated union are `FirstOnly`, `LastOnly`, and `FirstLast`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

<span data-ttu-id="a77a8-178">Для размеченных объединений с именованными полями используется знак равенства (=) для извлечения значения именованного поля.</span><span class="sxs-lookup"><span data-stu-id="a77a8-178">For discriminated unions that have named fields, you use the equals sign (=) to extract the value of a named field.</span></span> <span data-ttu-id="a77a8-179">Например, рассмотрим размеченное объединение с объявлением, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="a77a8-179">For example, consider a discriminated union with a declaration like the following.</span></span>

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

<span data-ttu-id="a77a8-180">Именованные поля можно использовать в выражении сопоставления шаблонов следующим образом.</span><span class="sxs-lookup"><span data-stu-id="a77a8-180">You can use the named fields in a pattern matching expression as follows.</span></span>

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

<span data-ttu-id="a77a8-181">Использование именованного поля является необязательным, поэтому в предыдущем примере оба `Circle(r)` и `Circle(radius = r)` имеют одинаковый результат.</span><span class="sxs-lookup"><span data-stu-id="a77a8-181">The use of the named field is optional, so in the previous example, both `Circle(r)` and `Circle(radius = r)` have the same effect.</span></span>

<span data-ttu-id="a77a8-182">При указании нескольких полей используйте точку с запятой (;) в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="a77a8-182">When you specify multiple fields, use the semicolon (;) as a separator.</span></span>

```fsharp
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

<span data-ttu-id="a77a8-183">Активные шаблоны позволяют определить более сложное сопоставление пользовательских шаблонов.</span><span class="sxs-lookup"><span data-stu-id="a77a8-183">Active patterns enable you to define more complex custom pattern matching.</span></span> <span data-ttu-id="a77a8-184">Дополнительные сведения об активных шаблонах см. в разделе [Активные закономерности](active-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="a77a8-184">For more information about active patterns, see [Active Patterns](active-patterns.md).</span></span>

<span data-ttu-id="a77a8-185">Случай, когда идентификатор является исключением, используется в сопоставлении шаблонов в контексте обработчиков исключений.</span><span class="sxs-lookup"><span data-stu-id="a77a8-185">The case in which the identifier is an exception is used in pattern matching in the context of exception handlers.</span></span> <span data-ttu-id="a77a8-186">Сведения о сопоставлении шаблонов в обработке исключений см. [в разделе Exceptions: the `try...with` выражение](./exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="a77a8-186">For information about pattern matching in exception handling, see [Exceptions: The `try...with` Expression](./exception-handling/the-try-with-expression.md).</span></span>

## <a name="variable-patterns"></a><span data-ttu-id="a77a8-187">Шаблоны переменных</span><span class="sxs-lookup"><span data-stu-id="a77a8-187">Variable Patterns</span></span>

<span data-ttu-id="a77a8-188">Шаблон переменной присваивает значение, совпадающее с именем переменной, которое затем можно использовать в выражении выполнения справа от символа `->`.</span><span class="sxs-lookup"><span data-stu-id="a77a8-188">The variable pattern assigns the value being matched to a variable name, which is then available for use in the execution expression to the right of the `->` symbol.</span></span> <span data-ttu-id="a77a8-189">Только шаблон переменной соответствует любым входным данным, но шаблоны переменных часто появляются в других шаблонах, поэтому для реализации более сложных структур, таких как кортежи и массивы, следует разложить их на переменные.</span><span class="sxs-lookup"><span data-stu-id="a77a8-189">A variable pattern alone matches any input, but variable patterns often appear within other patterns, therefore enabling more complex structures such as tuples and arrays to be decomposed into variables.</span></span>

<span data-ttu-id="a77a8-190">В следующем примере демонстрируется шаблон переменной в шаблоне кортежа.</span><span class="sxs-lookup"><span data-stu-id="a77a8-190">The following example demonstrates a variable pattern within a tuple pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a><span data-ttu-id="a77a8-191">Шаблон as</span><span class="sxs-lookup"><span data-stu-id="a77a8-191">as Pattern</span></span>

<span data-ttu-id="a77a8-192">Шаблон `as` — это шаблон, к которому добавляется предложение `as`.</span><span class="sxs-lookup"><span data-stu-id="a77a8-192">The `as` pattern is a pattern that has an `as` clause appended to it.</span></span> <span data-ttu-id="a77a8-193">Предложение `as` привязывает сопоставленное значение к имени, которое может использоваться в выражении выполнения выражения `match`, или, если этот шаблон используется в привязке `let`, имя добавляется в качестве привязки в локальную область.</span><span class="sxs-lookup"><span data-stu-id="a77a8-193">The `as` clause binds the matched value to a name that can be used in the execution expression of a `match` expression, or, in the case where this pattern is used in a `let` binding, the name is added as a binding to the local scope.</span></span>

<span data-ttu-id="a77a8-194">В следующем примере используется шаблон `as`.</span><span class="sxs-lookup"><span data-stu-id="a77a8-194">The following example uses an `as` pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a><span data-ttu-id="a77a8-195">ИЛИ шаблон</span><span class="sxs-lookup"><span data-stu-id="a77a8-195">OR Pattern</span></span>

<span data-ttu-id="a77a8-196">Шаблон или используется, если входные данные могут соответствовать нескольким шаблонам и вы хотите выполнить тот же код в результате.</span><span class="sxs-lookup"><span data-stu-id="a77a8-196">The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result.</span></span> <span data-ttu-id="a77a8-197">Типы обеих сторон шаблона или должны быть совместимы.</span><span class="sxs-lookup"><span data-stu-id="a77a8-197">The types of both sides of the OR pattern must be compatible.</span></span>

<span data-ttu-id="a77a8-198">В следующем примере демонстрируется шаблон или.</span><span class="sxs-lookup"><span data-stu-id="a77a8-198">The following example demonstrates the OR pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a><span data-ttu-id="a77a8-199">И шаблон</span><span class="sxs-lookup"><span data-stu-id="a77a8-199">AND Pattern</span></span>

<span data-ttu-id="a77a8-200">Шаблон и требует, чтобы входные данные соответствовали двум шаблонам.</span><span class="sxs-lookup"><span data-stu-id="a77a8-200">The AND pattern requires that the input match two patterns.</span></span> <span data-ttu-id="a77a8-201">Типы обеих сторон шаблона и должны быть совместимы.</span><span class="sxs-lookup"><span data-stu-id="a77a8-201">The types of both sides of the AND pattern must be compatible.</span></span>

<span data-ttu-id="a77a8-202">Следующий пример похож на `detectZeroTuple`, показанный в разделе [шаблон кортежа](https://msdn.microsoft.com/library/#tuple) далее в этом разделе, но в данном случае `var1` и `var2` получаются в виде значений с помощью шаблона и.</span><span class="sxs-lookup"><span data-stu-id="a77a8-202">The following example is like `detectZeroTuple` shown in the [Tuple Pattern](https://msdn.microsoft.com/library/#tuple) section later in this topic, but here both `var1` and `var2` are obtained as values by using the AND pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a><span data-ttu-id="a77a8-203">Шаблон «против»</span><span class="sxs-lookup"><span data-stu-id="a77a8-203">Cons Pattern</span></span>

<span data-ttu-id="a77a8-204">Шаблон недостатков используется для разбиения списка на первый элемент, *заголовок*и список, содержащий остальные элементы, *хвост*.</span><span class="sxs-lookup"><span data-stu-id="a77a8-204">The cons pattern is used to decompose a list into the first element, the *head*, and a list that contains the remaining elements, the *tail*.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a><span data-ttu-id="a77a8-205">Шаблон списка</span><span class="sxs-lookup"><span data-stu-id="a77a8-205">List Pattern</span></span>

<span data-ttu-id="a77a8-206">Шаблон списка позволяет разложить списки на несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="a77a8-206">The list pattern enables lists to be decomposed into a number of elements.</span></span> <span data-ttu-id="a77a8-207">Сам шаблон списка может сопоставлять только списки определенного числа элементов.</span><span class="sxs-lookup"><span data-stu-id="a77a8-207">The list pattern itself can match only lists of a specific number of elements.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a><span data-ttu-id="a77a8-208">Шаблон массива</span><span class="sxs-lookup"><span data-stu-id="a77a8-208">Array Pattern</span></span>

<span data-ttu-id="a77a8-209">Шаблон массива напоминает шаблон списка и может использоваться для разложения массивов определенной длины.</span><span class="sxs-lookup"><span data-stu-id="a77a8-209">The array pattern resembles the list pattern and can be used to decompose arrays of a specific length.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a><span data-ttu-id="a77a8-210">Шаблон в круглых скобках</span><span class="sxs-lookup"><span data-stu-id="a77a8-210">Parenthesized Pattern</span></span>

<span data-ttu-id="a77a8-211">Круглые скобки могут быть сгруппированы вокруг шаблонов для достижения требуемой ассоциативности.</span><span class="sxs-lookup"><span data-stu-id="a77a8-211">Parentheses can be grouped around patterns to achieve the desired associativity.</span></span> <span data-ttu-id="a77a8-212">В следующем примере круглые скобки используются для управления ассоциативностью между шаблоном и и шаблоном недостатка.</span><span class="sxs-lookup"><span data-stu-id="a77a8-212">In the following example, parentheses are used to control associativity between an AND pattern and a cons pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a><span data-ttu-id="a77a8-213">Шаблон кортежа</span><span class="sxs-lookup"><span data-stu-id="a77a8-213">Tuple Pattern</span></span>

<span data-ttu-id="a77a8-214">Шаблон кортежа соответствует входным данным в форме кортежа и позволяет разложить кортеж в составные элементы с помощью переменных сопоставления шаблонов для каждой из позиций в кортеже.</span><span class="sxs-lookup"><span data-stu-id="a77a8-214">The tuple pattern matches input in tuple form and enables the tuple to be decomposed into its constituent elements by using pattern matching variables for each position in the tuple.</span></span>

<span data-ttu-id="a77a8-215">В следующем примере демонстрируется шаблон кортежа, а также используются литеральные шаблоны, шаблоны переменных и шаблон с подстановочными знаками.</span><span class="sxs-lookup"><span data-stu-id="a77a8-215">The following example demonstrates the tuple pattern and also uses literal patterns, variable patterns, and the wildcard pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a><span data-ttu-id="a77a8-216">Шаблон записи</span><span class="sxs-lookup"><span data-stu-id="a77a8-216">Record Pattern</span></span>

<span data-ttu-id="a77a8-217">Шаблон записи используется для разложения записей, чтобы извлечь значения полей.</span><span class="sxs-lookup"><span data-stu-id="a77a8-217">The record pattern is used to decompose records to extract the values of fields.</span></span> <span data-ttu-id="a77a8-218">Шаблон не должен ссылаться на все поля записи; все пропущенные поля просто не участвуют в сопоставлении и не извлекаются.</span><span class="sxs-lookup"><span data-stu-id="a77a8-218">The pattern does not have to reference all fields of the record; any omitted fields just do not participate in matching and are not extracted.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a><span data-ttu-id="a77a8-219">Шаблон подстановочного знака</span><span class="sxs-lookup"><span data-stu-id="a77a8-219">Wildcard Pattern</span></span>

<span data-ttu-id="a77a8-220">Шаблон подстановочного знака представлен символом подчеркивания (`_`) и соответствует любым входным данным, как и шаблону переменной, за исключением того, что входные данные удаляются, а не присваиваются переменной.</span><span class="sxs-lookup"><span data-stu-id="a77a8-220">The wildcard pattern is represented by the underscore (`_`) character and matches any input, just like the variable pattern, except that the input is discarded instead of assigned to a variable.</span></span> <span data-ttu-id="a77a8-221">Шаблон шаблона часто используется в других шаблонах в качестве заполнителя для значений, которые не требуются в выражении справа от символа `->`.</span><span class="sxs-lookup"><span data-stu-id="a77a8-221">The wildcard pattern is often used within other patterns as a placeholder for values that are not needed in the expression to the right of the `->` symbol.</span></span> <span data-ttu-id="a77a8-222">Шаблон с подстановочным знаком также часто используется в конце списка шаблонов для сопоставления с любыми несоответствующими входными данными.</span><span class="sxs-lookup"><span data-stu-id="a77a8-222">The wildcard pattern is also frequently used at the end of a list of patterns to match any unmatched input.</span></span> <span data-ttu-id="a77a8-223">Шаблон с подстановочными знаками демонстрируется во многих примерах кода в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="a77a8-223">The wildcard pattern is demonstrated in many code examples in this topic.</span></span> <span data-ttu-id="a77a8-224">См. Приведенный выше код для одного примера.</span><span class="sxs-lookup"><span data-stu-id="a77a8-224">See the preceding code for one example.</span></span>

## <a name="patterns-that-have-type-annotations"></a><span data-ttu-id="a77a8-225">Шаблоны с аннотациями типов</span><span class="sxs-lookup"><span data-stu-id="a77a8-225">Patterns That Have Type Annotations</span></span>

<span data-ttu-id="a77a8-226">Шаблоны могут иметь аннотации типов.</span><span class="sxs-lookup"><span data-stu-id="a77a8-226">Patterns can have type annotations.</span></span> <span data-ttu-id="a77a8-227">Они ведут себя так же, как и другие аннотации типа и пошаговое определение, как и другие заметки типа.</span><span class="sxs-lookup"><span data-stu-id="a77a8-227">These behave like other type annotations and guide inference like other type annotations.</span></span> <span data-ttu-id="a77a8-228">Для заметок типа в шаблонах требуются круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="a77a8-228">Parentheses are required around type annotations in patterns.</span></span> <span data-ttu-id="a77a8-229">В следующем коде показан шаблон с аннотацией типа.</span><span class="sxs-lookup"><span data-stu-id="a77a8-229">The following code shows a pattern that has a type annotation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a><span data-ttu-id="a77a8-230">Шаблон проверки типа</span><span class="sxs-lookup"><span data-stu-id="a77a8-230">Type Test Pattern</span></span>

<span data-ttu-id="a77a8-231">Шаблон проверки типа используется для сопоставления входных данных с типом.</span><span class="sxs-lookup"><span data-stu-id="a77a8-231">The type test pattern is used to match the input against a type.</span></span> <span data-ttu-id="a77a8-232">Если тип входных данных соответствует типу (или производному типу) типа, указанного в шаблоне, сопоставление выполняется с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a77a8-232">If the input type is a match to (or a derived type of) the type specified in the pattern, the match succeeds.</span></span>

<span data-ttu-id="a77a8-233">В следующем примере показан шаблон проверки типа.</span><span class="sxs-lookup"><span data-stu-id="a77a8-233">The following example demonstrates the type test pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

<span data-ttu-id="a77a8-234">Если проверяется только идентификатор определенного производного типа, `as identifier` часть шаблона не требуется, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a77a8-234">If you're only checking if an identifier is of a particular derived type, you don't need the `as identifier` part of the pattern, as shown in the following example:</span></span>

```fsharp
type A() = class end
type B() = inherit A()
type C() = inherit A()

let m (a: A) =
    match a with
    | :? B -> printfn "It's a B"
    | :? C -> printfn "It's a C"
    | _ -> ()
```

## <a name="null-pattern"></a><span data-ttu-id="a77a8-235">Шаблон NULL</span><span class="sxs-lookup"><span data-stu-id="a77a8-235">Null Pattern</span></span>

<span data-ttu-id="a77a8-236">Шаблон NULL соответствует значению NULL, которое может появиться при работе с типами, допускающими значение null.</span><span class="sxs-lookup"><span data-stu-id="a77a8-236">The null pattern matches the null value that can appear when you are working with types that allow a null value.</span></span> <span data-ttu-id="a77a8-237">Шаблоны NULL часто используются при взаимодействии с .NET Frameworkным кодом.</span><span class="sxs-lookup"><span data-stu-id="a77a8-237">Null patterns are frequently used when interoperating with .NET Framework code.</span></span> <span data-ttu-id="a77a8-238">Например, возвращаемое значение API .NET может быть входными данными для `match` выражения.</span><span class="sxs-lookup"><span data-stu-id="a77a8-238">For example, the return value of a .NET API might be the input to a `match` expression.</span></span> <span data-ttu-id="a77a8-239">Можно управлять выполнением программы в зависимости от того, имеет ли возвращаемое значение значение null, а также другие характеристики возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="a77a8-239">You can control program flow based on whether the return value is null, and also on other characteristics of the returned value.</span></span> <span data-ttu-id="a77a8-240">Можно использовать шаблон NULL, чтобы предотвратить распространение значений NULL на остальную часть программы.</span><span class="sxs-lookup"><span data-stu-id="a77a8-240">You can use the null pattern to prevent null values from propagating to the rest of your program.</span></span>

<span data-ttu-id="a77a8-241">В следующем примере используется шаблон NULL и шаблон переменной.</span><span class="sxs-lookup"><span data-stu-id="a77a8-241">The following example uses the null pattern and the variable pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a><span data-ttu-id="a77a8-242">См. также</span><span class="sxs-lookup"><span data-stu-id="a77a8-242">See also</span></span>

- [<span data-ttu-id="a77a8-243">Выражения match</span><span class="sxs-lookup"><span data-stu-id="a77a8-243">Match Expressions</span></span>](match-expressions.md)
- [<span data-ttu-id="a77a8-244">Активные шаблоны</span><span class="sxs-lookup"><span data-stu-id="a77a8-244">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="a77a8-245">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="a77a8-245">F# Language Reference</span></span>](index.md)
