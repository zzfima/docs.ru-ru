---
title: Перегрузка операторов
description: Узнайте, как перегружать арифметические операторы в классе или типе записи и на глобальном уровне F#в.
ms.date: 05/16/2016
ms.openlocfilehash: d902a06193481ed87131b3336cd8a2ff54b811b4
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216845"
---
# <a name="operator-overloading"></a><span data-ttu-id="e6690-103">Перегрузка операторов</span><span class="sxs-lookup"><span data-stu-id="e6690-103">Operator Overloading</span></span>

<span data-ttu-id="e6690-104">В этом разделе описывается перегрузка арифметических операторов в классе или типе записи, а также на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="e6690-104">This topic describes how to overload arithmetic operators in a class or record type, and at the global level.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6690-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6690-105">Syntax</span></span>

```fsharp
// Overloading an operator as a class or record member.
static member (operator-symbols) (parameter-list) =
    method-body
// Overloading an operator at the global level
let [inline] (operator-symbols) parameter-list = function-body
```

## <a name="remarks"></a><span data-ttu-id="e6690-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="e6690-106">Remarks</span></span>

<span data-ttu-id="e6690-107">В предыдущем синтаксисе *оператор-Symbol* является одним из `+`, `*` `-`, `/`,, `=`и т. д.</span><span class="sxs-lookup"><span data-stu-id="e6690-107">In the previous syntax, the *operator-symbol* is one of `+`, `-`, `*`, `/`, `=`, and so on.</span></span> <span data-ttu-id="e6690-108">*Параметр-List* задает операнды в том порядке, в котором они отображаются в обычном синтаксисе для этого оператора.</span><span class="sxs-lookup"><span data-stu-id="e6690-108">The *parameter-list* specifies the operands in the order they appear in the usual syntax for that operator.</span></span> <span data-ttu-id="e6690-109">*Метод-Body* конструирует результирующее значение.</span><span class="sxs-lookup"><span data-stu-id="e6690-109">The *method-body* constructs the resulting value.</span></span>

<span data-ttu-id="e6690-110">Перегрузки операторов для операторов должны быть статическими.</span><span class="sxs-lookup"><span data-stu-id="e6690-110">Operator overloads for operators must be static.</span></span> <span data-ttu-id="e6690-111">Перегрузки операторов для унарных операторов, таких `+` как `-`и, должны использовать символ тильды (`~`) в *операторе-Symbol* , чтобы указать, что оператор является унарным оператором, а не бинарным оператором, как показано ниже. повторно.</span><span class="sxs-lookup"><span data-stu-id="e6690-111">Operator overloads for unary operators, such as `+` and `-`, must use a tilde (`~`) in the *operator-symbol* to indicate that the operator is a unary operator and not a binary operator, as shown in the following declaration.</span></span>

```fsharp
static member (~-) (v : Vector)
```

<span data-ttu-id="e6690-112">В следующем коде показан класс Vector, имеющий только два оператора: один для унарного минуса и один для умножения скаляром.</span><span class="sxs-lookup"><span data-stu-id="e6690-112">The following code illustrates a vector class that has just two operators, one for unary minus and one for multiplication by a scalar.</span></span> <span data-ttu-id="e6690-113">В этом примере требуется две перегрузки для скалярного умножения, так как оператор должен работать независимо от порядка, в котором отображаются Vector и scalar.</span><span class="sxs-lookup"><span data-stu-id="e6690-113">In the example, two overloads for scalar multiplication are needed because the operator must work regardless of the order in which the vector and scalar appear.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a><span data-ttu-id="e6690-114">Создание новых операторов</span><span class="sxs-lookup"><span data-stu-id="e6690-114">Creating New Operators</span></span>

<span data-ttu-id="e6690-115">Можно перегружать все стандартные операторы, но можно также создавать новые операторы из последовательностей определенных символов.</span><span class="sxs-lookup"><span data-stu-id="e6690-115">You can overload all the standard operators, but you can also create new operators out of sequences of certain characters.</span></span> <span data-ttu-id="e6690-116">Допустимые символы оператора `!`: `%`, `&`, `*`, `+`,, `-`, ,`/`,,, ,`>` `=` `<` `.` `?` ,`@`, `^` ,и`~`. `|`</span><span class="sxs-lookup"><span data-stu-id="e6690-116">Allowed operator characters are `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, and `~`.</span></span> <span data-ttu-id="e6690-117">`~` Символ имеет особое значение, что делает оператор унарным и не является частью последовательности символов оператора.</span><span class="sxs-lookup"><span data-stu-id="e6690-117">The `~` character has the special meaning of making an operator unary, and is not part of the operator character sequence.</span></span> <span data-ttu-id="e6690-118">Не все операторы можно сделать унарными.</span><span class="sxs-lookup"><span data-stu-id="e6690-118">Not all operators can be made unary.</span></span>

<span data-ttu-id="e6690-119">В зависимости от того, какая последовательность символов используется, оператор будет иметь определенный приоритет и ассоциативность.</span><span class="sxs-lookup"><span data-stu-id="e6690-119">Depending on the exact character sequence you use, your operator will have a certain precedence and associativity.</span></span> <span data-ttu-id="e6690-120">Ассоциативность может быть либо слева направо, либо справа налево, и используется всякий раз, когда операторы одного и того же уровня приоритета отображаются в последовательности без скобок.</span><span class="sxs-lookup"><span data-stu-id="e6690-120">Associativity can be either left to right or right to left and is used whenever operators of the same level of precedence appear in sequence without parentheses.</span></span>

<span data-ttu-id="e6690-121">Символ `.` оператора не влияет на приоритет, поэтому, например, если необходимо определить собственную версию умножения, имеющую тот же приоритет и ассоциативность, что и обычное умножение, можно создать такие операторы, как `.*`.</span><span class="sxs-lookup"><span data-stu-id="e6690-121">The operator character `.` does not affect precedence, so that, for example, if you want to define your own version of multiplication that has the same precedence and associativity as ordinary multiplication, you could create operators such as `.*`.</span></span>

<span data-ttu-id="e6690-122">Только операторы `?` и `?<-` могут начинаться с `?`.</span><span class="sxs-lookup"><span data-stu-id="e6690-122">Only the operators `?` and `?<-` may start with `?`.</span></span>

<span data-ttu-id="e6690-123">Таблица, в которой показан приоритет всех операторов в F# , можно найти в [справочнике по символам и операторам](./symbol-and-operator-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="e6690-123">A table that shows the precedence of all operators in F# can be found in [Symbol and Operator Reference](./symbol-and-operator-reference/index.md).</span></span>

## <a name="overloaded-operator-names"></a><span data-ttu-id="e6690-124">Имена перегруженных операторов</span><span class="sxs-lookup"><span data-stu-id="e6690-124">Overloaded Operator Names</span></span>

<span data-ttu-id="e6690-125">Когда F# компилятор компилирует выражение оператора, он создает метод с именем, созданным компилятором для этого оператора.</span><span class="sxs-lookup"><span data-stu-id="e6690-125">When the F# compiler compiles an operator expression, it generates a method that has a compiler-generated name for that operator.</span></span> <span data-ttu-id="e6690-126">Это имя, которое отображается на языке MSIL для метода, а также в отражении и IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="e6690-126">This is the name that appears in the Microsoft intermediate language (MSIL) for the method, and also in reflection and IntelliSense.</span></span> <span data-ttu-id="e6690-127">Обычно вам не нужно использовать эти имена в F# коде.</span><span class="sxs-lookup"><span data-stu-id="e6690-127">You do not normally need to use these names in F# code.</span></span>

<span data-ttu-id="e6690-128">В следующей таблице показаны стандартные операторы и соответствующие им созданные имена.</span><span class="sxs-lookup"><span data-stu-id="e6690-128">The following table shows the standard operators and their corresponding generated names.</span></span>

|<span data-ttu-id="e6690-129">Оператор</span><span class="sxs-lookup"><span data-stu-id="e6690-129">Operator</span></span>|<span data-ttu-id="e6690-130">Созданное имя</span><span class="sxs-lookup"><span data-stu-id="e6690-130">Generated name</span></span>|
|--------|--------------|
|`[]`|`op_Nil`|
|`::`|`op_Cons`|
|`+`|`op_Addition`|
|`-`|`op_Subtraction`|
|`*`|`op_Multiply`|
|`/`|`op_Division`|
|`@`|`op_Append`|
|`^`|`op_Concatenate`|
|`%`|`op_Modulus`|
|`&&&`|`op_BitwiseAnd`|
|<code>&#124;&#124;&#124;</code>|`op_BitwiseOr`|
|`^^^`|`op_ExclusiveOr`|
|`<<<`|`op_LeftShift`|
|`~~~`|`op_LogicalNot`|
|`>>>`|`op_RightShift`|
|`~+`|`op_UnaryPlus`|
|`~-`|`op_UnaryNegation`|
|`=`|`op_Equality`|
|`<=`|`op_LessThanOrEqual`|
|`>=`|`op_GreaterThanOrEqual`|
|`<`|`op_LessThan`|
|`>`|`op_GreaterThan`|
|`?`|`op_Dynamic`|
|`?<-`|`op_DynamicAssignment`|
|<code>&#124;></code>|`op_PipeRight`|
|<code><&#124;</code>|`op_PipeLeft`|
|`!`|`op_Dereference`|
|`>>`|`op_ComposeRight`|
|`<<`|`op_ComposeLeft`|
|`<@ @>`|`op_Quotation`|
|`<@@ @@>`|`op_QuotationUntyped`|
|`+=`|`op_AdditionAssignment`|
|`-=`|`op_SubtractionAssignment`|
|`*=`|`op_MultiplyAssignment`|
|`/=`|`op_DivisionAssignment`|
|`..`|`op_Range`|
|`.. ..`|`op_RangeStep`|

<span data-ttu-id="e6690-131">Другие сочетания символов операторов, которые не перечислены здесь, могут использоваться в качестве операторов и иметь имена, которые объединяются путем объединения имен для отдельных символов из следующей таблицы.</span><span class="sxs-lookup"><span data-stu-id="e6690-131">Other combinations of operator characters that are not listed here can be used as operators and have names that are made up by concatenating names for the individual characters from the following table.</span></span> <span data-ttu-id="e6690-132">Например, +!</span><span class="sxs-lookup"><span data-stu-id="e6690-132">For example, +!</span></span> <span data-ttu-id="e6690-133">будет `op_PlusBang`.</span><span class="sxs-lookup"><span data-stu-id="e6690-133">becomes `op_PlusBang`.</span></span>

|<span data-ttu-id="e6690-134">Символ оператора</span><span class="sxs-lookup"><span data-stu-id="e6690-134">Operator character</span></span>|<span data-ttu-id="e6690-135">name</span><span class="sxs-lookup"><span data-stu-id="e6690-135">Name</span></span>|
|------------------|----|
|`>`|`Greater`|
|`<`|`Less`|
|`+`|`Plus`|
|`-`|`Minus`|
|`*`|`Multiply`|
|`/`|`Divide`|
|`=`|`Equals`|
|`~`|`Twiddle`|
|`%`|`Percent`|
|`.`|`Dot`|
|`&`|`Amp`|
|<code>&#124;</code>|`Bar`|
|`@`|`At`|
|`^`|`Hat`|
|`!`|`Bang`|
|`?`|`Qmark`|
|`(`|`LParen`|
|`,`|`Comma`|
|`)`|`RParen`|
|`[`|`LBrack`|
|`]`|`RBrack`|

## <a name="prefix-and-infix-operators"></a><span data-ttu-id="e6690-136">Операторы prefix и инфиксные</span><span class="sxs-lookup"><span data-stu-id="e6690-136">Prefix and Infix Operators</span></span>

<span data-ttu-id="e6690-137">Операторы *префикса* должны размещаться перед операндом или операндами, во многом подобно функции.</span><span class="sxs-lookup"><span data-stu-id="e6690-137">*Prefix* operators are expected to be placed in front of an operand or operands, much like a function.</span></span> <span data-ttu-id="e6690-138">Операторы *инфиксные* должны располагаться между двумя операндами.</span><span class="sxs-lookup"><span data-stu-id="e6690-138">*Infix* operators are expected to be placed between the two operands.</span></span>

<span data-ttu-id="e6690-139">В качестве префиксных операторов можно использовать только определенные операторы.</span><span class="sxs-lookup"><span data-stu-id="e6690-139">Only certain operators can be used as prefix operators.</span></span> <span data-ttu-id="e6690-140">Некоторые операторы всегда являются префиксными операторами, другие могут быть инфиксные или префиксом, а остальные всегда инфиксные операторами.</span><span class="sxs-lookup"><span data-stu-id="e6690-140">Some operators are always prefix operators, others can be infix or prefix, and the rest are always infix operators.</span></span> <span data-ttu-id="e6690-141">Операторы, которые начинаются `!`с оператора `!=` `~`, за исключением and, или повторяющихся последовательностей`~`, всегда являются префиксными операторами.</span><span class="sxs-lookup"><span data-stu-id="e6690-141">Operators that begin with `!`, except `!=`, and the operator `~`, or repeated sequences of`~`, are always prefix operators.</span></span> <span data-ttu-id="e6690-142">`+`Операторы ,,`&&`,,,, и`%%` могут быть префиксными операторами или операторами инфиксные. `-` `+.` `-.` `&` `%`</span><span class="sxs-lookup"><span data-stu-id="e6690-142">The operators `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, and `%%` can be prefix operators or infix operators.</span></span> <span data-ttu-id="e6690-143">Префиксную версию этих операторов можно отличить от версии инфиксные, добавляя в `~` начале префиксного оператора, когда он определен.</span><span class="sxs-lookup"><span data-stu-id="e6690-143">You distinguish the prefix version of these operators from the infix version by adding a `~` at the beginning of a prefix operator when it is defined.</span></span> <span data-ttu-id="e6690-144">`~` Не используется при использовании оператора, только если он определен.</span><span class="sxs-lookup"><span data-stu-id="e6690-144">The `~` is not used when you use the operator, only when it is defined.</span></span>

## <a name="example"></a><span data-ttu-id="e6690-145">Пример</span><span class="sxs-lookup"><span data-stu-id="e6690-145">Example</span></span>

<span data-ttu-id="e6690-146">В следующем коде показано использование перегрузки операторов для реализации типа дробной части.</span><span class="sxs-lookup"><span data-stu-id="e6690-146">The following code illustrates the use of operator overloading to implement a fraction type.</span></span> <span data-ttu-id="e6690-147">Дробная часть представляется числителем и знаменателем.</span><span class="sxs-lookup"><span data-stu-id="e6690-147">A fraction is represented by a numerator and a denominator.</span></span> <span data-ttu-id="e6690-148">Функция `hcf` используется для определения самого высокого общего фактора, который используется для сокращения дробей.</span><span class="sxs-lookup"><span data-stu-id="e6690-148">The function `hcf` is used to determine the highest common factor, which is used to reduce fractions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4002.fs)]

<span data-ttu-id="e6690-149">**Выходные данные:**</span><span class="sxs-lookup"><span data-stu-id="e6690-149">**Output:**</span></span>

```console
3/4 + 1/2 = 5/4
3/4 - 1/2 = 1/4
3/4 * 1/2 = 3/8
3/4 / 1/2 = 3/2
3/4 + 1 = 7/4
```

## <a name="operators-at-the-global-level"></a><span data-ttu-id="e6690-150">Операторы на глобальном уровне</span><span class="sxs-lookup"><span data-stu-id="e6690-150">Operators at the Global Level</span></span>

<span data-ttu-id="e6690-151">Операторы также можно определять на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="e6690-151">You can also define operators at the global level.</span></span> <span data-ttu-id="e6690-152">В следующем коде определяется оператор `+?`.</span><span class="sxs-lookup"><span data-stu-id="e6690-152">The following code defines an operator `+?`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

<span data-ttu-id="e6690-153">Выходные данные приведенного выше кода имеют `12`значение.</span><span class="sxs-lookup"><span data-stu-id="e6690-153">The output of the above code is `12`.</span></span>

<span data-ttu-id="e6690-154">Таким образом можно переопределить обычные арифметические операторы, так как правила определения области F# определяют, что новые определенные операторы имеют приоритет над встроенными операторами.</span><span class="sxs-lookup"><span data-stu-id="e6690-154">You can redefine the regular arithmetic operators in this manner because the scoping rules for F# dictate that newly defined operators take precedence over the built-in operators.</span></span>

<span data-ttu-id="e6690-155">Ключевое `inline` слово часто используется с глобальными операторами, которые часто являются маленькими функциями, которые лучше всего интегрируются в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="e6690-155">The keyword `inline` is often used with global operators, which are often small functions that are best integrated into the calling code.</span></span> <span data-ttu-id="e6690-156">Использование встроенных функций операторов также позволяет им работать с статически разрешаемыми параметрами типов для формирования статически разрешаемого универсального кода.</span><span class="sxs-lookup"><span data-stu-id="e6690-156">Making operator functions inline also enables them to work with statically resolved type parameters to produce statically resolved generic code.</span></span> <span data-ttu-id="e6690-157">Дополнительные сведения см. в разделе [встроенные функции](./functions/inline-functions.md) и [статически разрешаемые параметры типа](./generics/statically-resolved-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="e6690-157">For more information, see [Inline Functions](./functions/inline-functions.md) and [Statically Resolved Type Parameters](./generics/statically-resolved-type-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e6690-158">См. также</span><span class="sxs-lookup"><span data-stu-id="e6690-158">See also</span></span>

- [<span data-ttu-id="e6690-159">Члены</span><span class="sxs-lookup"><span data-stu-id="e6690-159">Members</span></span>](./members/index.md)
