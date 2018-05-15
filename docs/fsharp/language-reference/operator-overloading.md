---
title: Перегрузка операторов (F#)
description: 'Дополнительные сведения о перегрузка арифметических операторов в классе или тип записи, а также на глобальном уровне в языке F #.'
ms.date: 05/16/2016
ms.openlocfilehash: fc9b7311aa746fd758930365972a187ffdfff0d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="operator-overloading"></a><span data-ttu-id="f5def-103">Перегрузка операторов</span><span class="sxs-lookup"><span data-stu-id="f5def-103">Operator Overloading</span></span>

<span data-ttu-id="f5def-104">В этом разделе описывается перегрузка арифметических операторов в классе или тип записи, а также на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="f5def-104">This topic describes how to overload arithmetic operators in a class or record type, and at the global level.</span></span>


## <a name="syntax"></a><span data-ttu-id="f5def-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5def-105">Syntax</span></span>

```fsharp
// Overloading an operator as a class or record member.
static member (operator-symbols) (parameter-list) =
    method-body
// Overloading an operator at the global level
let [inline] (operator-symbols) parameter-list = function-body
```

## <a name="remarks"></a><span data-ttu-id="f5def-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="f5def-106">Remarks</span></span>
<span data-ttu-id="f5def-107">В предыдущем синтаксисе *символ оператора* является одним из `+`, `-`, `*`, `/`, `=`, и т. д.</span><span class="sxs-lookup"><span data-stu-id="f5def-107">In the previous syntax, the *operator-symbol* is one of `+`, `-`, `*`, `/`, `=`, and so on.</span></span> <span data-ttu-id="f5def-108">*Список параметров* задает операнды в том порядке, они отображаются в обычный синтаксис для этого оператора.</span><span class="sxs-lookup"><span data-stu-id="f5def-108">The *parameter-list* specifies the operands in the order they appear in the usual syntax for that operator.</span></span> <span data-ttu-id="f5def-109">*Тело метода* создает результирующее значение.</span><span class="sxs-lookup"><span data-stu-id="f5def-109">The *method-body* constructs the resulting value.</span></span>

<span data-ttu-id="f5def-110">Перегрузки операторов для операторов должны быть статическими.</span><span class="sxs-lookup"><span data-stu-id="f5def-110">Operator overloads for operators must be static.</span></span> <span data-ttu-id="f5def-111">Оператор перегрузки для унарных операторов, таких как `+` и `-`, необходимо использовать тильду (`~`) в *символ оператора* для указания, что оператор является унарным, а бинарного оператора, как показано в следующее объявление.</span><span class="sxs-lookup"><span data-stu-id="f5def-111">Operator overloads for unary operators, such as `+` and `-`, must use a tilde (`~`) in the *operator-symbol* to indicate that the operator is a unary operator and not a binary operator, as shown in the following declaration.</span></span>

```fsharp
static member (~-) (v : Vector)
```

<span data-ttu-id="f5def-112">Следующий код иллюстрирует векторный класс, имеющий только два оператора унарного минуса и умножения на скаляр.</span><span class="sxs-lookup"><span data-stu-id="f5def-112">The following code illustrates a vector class that has just two operators, one for unary minus and one for multiplication by a scalar.</span></span> <span data-ttu-id="f5def-113">В примере две перегрузки для скалярного умножения нужны, поскольку оператор должен работать независимо от порядка, в котором отображаются вектор и скаляр.</span><span class="sxs-lookup"><span data-stu-id="f5def-113">In the example, two overloads for scalar multiplication are needed because the operator must work regardless of the order in which the vector and scalar appear.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a><span data-ttu-id="f5def-114">Создание новых операторов</span><span class="sxs-lookup"><span data-stu-id="f5def-114">Creating New Operators</span></span>
<span data-ttu-id="f5def-115">Все стандартные операторы можно перегрузить, но можно также создавать новые операторы из последовательностей определенных символов.</span><span class="sxs-lookup"><span data-stu-id="f5def-115">You can overload all the standard operators, but you can also create new operators out of sequences of certain characters.</span></span> <span data-ttu-id="f5def-116">Допустимые знаки операторов: `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, и `~`.</span><span class="sxs-lookup"><span data-stu-id="f5def-116">Allowed operator characters are `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, and `~`.</span></span> <span data-ttu-id="f5def-117">`~` Символ имеет особое значение делает оператор унарным и не является частью последовательности символов оператора.</span><span class="sxs-lookup"><span data-stu-id="f5def-117">The `~` character has the special meaning of making an operator unary, and is not part of the operator character sequence.</span></span> <span data-ttu-id="f5def-118">Не все операторы могут выполняться унарный.</span><span class="sxs-lookup"><span data-stu-id="f5def-118">Not all operators can be made unary.</span></span>

<span data-ttu-id="f5def-119">В зависимости от символьной последовательность, в которой используется ваш оператор будет иметь приоритет и ассоциативность операторов.</span><span class="sxs-lookup"><span data-stu-id="f5def-119">Depending on the exact character sequence you use, your operator will have a certain precedence and associativity.</span></span> <span data-ttu-id="f5def-120">Ассоциативность может быть либо слева направо или справа налево и будет использоваться при каждом операторы одного уровня приоритета появляются в последовательности без скобок.</span><span class="sxs-lookup"><span data-stu-id="f5def-120">Associativity can be either left to right or right to left and is used whenever operators of the same level of precedence appear in sequence without parentheses.</span></span>

<span data-ttu-id="f5def-121">Символ оператора `.` не влияет на более высокий приоритет, поэтому, например, если вы хотите определить собственную версию умножения, имеет тот же приоритет и ассоциативность, что и обычное умножение, можно создать операторов, таких как `.*`.</span><span class="sxs-lookup"><span data-stu-id="f5def-121">The operator character `.` does not affect precedence, so that, for example, if you want to define your own version of multiplication that has the same precedence and associativity as ordinary multiplication, you could create operators such as `.*`.</span></span>

<span data-ttu-id="f5def-122">Только операторы `?` и `?<-` может начинаться с `?`.</span><span class="sxs-lookup"><span data-stu-id="f5def-122">Only the operators `?` and `?<-` may start with `?`.</span></span>

<span data-ttu-id="f5def-123">Таблицу, описывающую приоритет всех операторов в языке F # можно найти в [Справочник символов и операторов](symbol-and-operator-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="f5def-123">A table that shows the precedence of all operators in F# can be found in [Symbol and Operator Reference](symbol-and-operator-reference/index.md).</span></span>


## <a name="overloaded-operator-names"></a><span data-ttu-id="f5def-124">Имена перегруженных операторов</span><span class="sxs-lookup"><span data-stu-id="f5def-124">Overloaded Operator Names</span></span>
<span data-ttu-id="f5def-125">Когда компилятор F # компилирует выражение с оператором, он создает метод, который имеет имя, созданный компилятором, для этого оператора.</span><span class="sxs-lookup"><span data-stu-id="f5def-125">When the F# compiler compiles an operator expression, it generates a method that has a compiler-generated name for that operator.</span></span> <span data-ttu-id="f5def-126">Это имя, которое отображается в промежуточный язык Microsoft (MSIL) для метода, а также в отражении и IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="f5def-126">This is the name that appears in the Microsoft intermediate language (MSIL) for the method, and also in reflection and IntelliSense.</span></span> <span data-ttu-id="f5def-127">Обычно необходимо использовать эти имена в коде F #.</span><span class="sxs-lookup"><span data-stu-id="f5def-127">You do not normally need to use these names in F# code.</span></span>

<span data-ttu-id="f5def-128">В следующей таблице приведены стандартные операторы и соответствующие им генерируемые имена.</span><span class="sxs-lookup"><span data-stu-id="f5def-128">The following table shows the standard operators and their corresponding generated names.</span></span>



|<span data-ttu-id="f5def-129">Оператор</span><span class="sxs-lookup"><span data-stu-id="f5def-129">Operator</span></span>|<span data-ttu-id="f5def-130">Созданное имя</span><span class="sxs-lookup"><span data-stu-id="f5def-130">Generated name</span></span>|
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
<span data-ttu-id="f5def-131">Другие сочетания символов операторов, не перечисленных здесь можно использовать в качестве операторов и иметь имена, которые создаются путем объединения имена отдельных символов из следующей таблицы.</span><span class="sxs-lookup"><span data-stu-id="f5def-131">Other combinations of operator characters that are not listed here can be used as operators and have names that are made up by concatenating names for the individual characters from the following table.</span></span> <span data-ttu-id="f5def-132">Например +!</span><span class="sxs-lookup"><span data-stu-id="f5def-132">For example, +!</span></span> <span data-ttu-id="f5def-133">становится `op_PlusBang`.</span><span class="sxs-lookup"><span data-stu-id="f5def-133">becomes `op_PlusBang`.</span></span>



|<span data-ttu-id="f5def-134">Символ оператора</span><span class="sxs-lookup"><span data-stu-id="f5def-134">Operator character</span></span>|<span data-ttu-id="f5def-135">name</span><span class="sxs-lookup"><span data-stu-id="f5def-135">Name</span></span>|
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

## <a name="prefix-and-infix-operators"></a><span data-ttu-id="f5def-136">Префикс и инфиксные операторы</span><span class="sxs-lookup"><span data-stu-id="f5def-136">Prefix and Infix Operators</span></span>
<span data-ttu-id="f5def-137">*Префикс* операторы должны размещаться перед операндом или операндами, подобно функции.</span><span class="sxs-lookup"><span data-stu-id="f5def-137">*Prefix* operators are expected to be placed in front of an operand or operands, much like a function.</span></span> <span data-ttu-id="f5def-138">*Инфиксные* операторы должны размещаться между двумя операндами.</span><span class="sxs-lookup"><span data-stu-id="f5def-138">*Infix* operators are expected to be placed between the two operands.</span></span>

<span data-ttu-id="f5def-139">Только определенные операторы могут использоваться как префиксные операторы.</span><span class="sxs-lookup"><span data-stu-id="f5def-139">Only certain operators can be used as prefix operators.</span></span> <span data-ttu-id="f5def-140">Некоторые операторы всегда являются префиксные операторы, другие могут быть инфиксные или префикс и остальные всегда являются инфиксные операторы.</span><span class="sxs-lookup"><span data-stu-id="f5def-140">Some operators are always prefix operators, others can be infix or prefix, and the rest are always infix operators.</span></span> <span data-ttu-id="f5def-141">Операторы, которые начинаются с `!`, за исключением `!=`и оператор `~`, и не будут повторяться последовательности`~`, всегда являются префиксные операторы.</span><span class="sxs-lookup"><span data-stu-id="f5def-141">Operators that begin with `!`, except `!=`, and the operator `~`, or repeated sequences of`~`, are always prefix operators.</span></span> <span data-ttu-id="f5def-142">Операторы `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, и `%%` может быть операторы префиксом или инфиксные операторы.</span><span class="sxs-lookup"><span data-stu-id="f5def-142">The operators `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, and `%%` can be prefix operators or infix operators.</span></span> <span data-ttu-id="f5def-143">Префиксная версия этих операторов было отличить от версии инфиксные путем добавления `~` в начале префиксный оператор, если она определена.</span><span class="sxs-lookup"><span data-stu-id="f5def-143">You distinguish the prefix version of these operators from the infix version by adding a `~` at the beginning of a prefix operator when it is defined.</span></span> <span data-ttu-id="f5def-144">`~` Не используется при использовании оператора, только в том случае, если она определена.</span><span class="sxs-lookup"><span data-stu-id="f5def-144">The `~` is not used when you use the operator, only when it is defined.</span></span>

## <a name="example"></a><span data-ttu-id="f5def-145">Пример</span><span class="sxs-lookup"><span data-stu-id="f5def-145">Example</span></span>

<span data-ttu-id="f5def-146">Следующий код иллюстрирует использование перегрузки операторов для реализации дробного типа.</span><span class="sxs-lookup"><span data-stu-id="f5def-146">The following code illustrates the use of operator overloading to implement a fraction type.</span></span> <span data-ttu-id="f5def-147">Дробь представляется числителем и знаменателем.</span><span class="sxs-lookup"><span data-stu-id="f5def-147">A fraction is represented by a numerator and a denominator.</span></span> <span data-ttu-id="f5def-148">Функция `hcf` используется для определения наибольшего общего делителя, который используется для сокращения доли секунды.</span><span class="sxs-lookup"><span data-stu-id="f5def-148">The function `hcf` is used to determine the highest common factor, which is used to reduce fractions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4002.fs)]

<span data-ttu-id="f5def-149">**Выходные данные:**</span><span class="sxs-lookup"><span data-stu-id="f5def-149">**Output:**</span></span>

```
3/4 + 1/2 = 5/4
3/4 - 1/2 = 1/4
3/4 * 1/2 = 3/8
3/4 / 1/2 = 3/2
3/4 + 1 = 7/4
```

## <a name="operators-at-the-global-level"></a><span data-ttu-id="f5def-150">Операторы на глобальном уровне</span><span class="sxs-lookup"><span data-stu-id="f5def-150">Operators at the Global Level</span></span>
<span data-ttu-id="f5def-151">Можно также определить операторы на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="f5def-151">You can also define operators at the global level.</span></span> <span data-ttu-id="f5def-152">В следующем коде определяется оператор `+?`.</span><span class="sxs-lookup"><span data-stu-id="f5def-152">The following code defines an operator `+?`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

<span data-ttu-id="f5def-153">Результат выполнения приведенного выше кода `12`.</span><span class="sxs-lookup"><span data-stu-id="f5def-153">The output of the above code is `12`.</span></span>

<span data-ttu-id="f5def-154">Регулярные арифметические операторы, таким образом можно переопределить, поскольку правила выбора области для F # определяют, что новые определенные операторы имеют приоритет над встроенными операторами.</span><span class="sxs-lookup"><span data-stu-id="f5def-154">You can redefine the regular arithmetic operators in this manner because the scoping rules for F# dictate that newly defined operators take precedence over the built-in operators.</span></span>

<span data-ttu-id="f5def-155">Ключевое слово `inline` часто используется с глобальными операторами, которые часто оказываются небольшие функции, которые лучше всего интегрируются в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="f5def-155">The keyword `inline` is often used with global operators, which are often small functions that are best integrated into the calling code.</span></span> <span data-ttu-id="f5def-156">Встроенные функции оператор внесения также позволяет им для работы с статически разрешаемые параметры типа для получения статически разрешаемые универсального кода.</span><span class="sxs-lookup"><span data-stu-id="f5def-156">Making operator functions inline also enables them to work with statically resolved type parameters to produce statically resolved generic code.</span></span> <span data-ttu-id="f5def-157">Дополнительные сведения см. в разделе [встроенные функции](functions/inline-functions.md) и [статически Разрешить параметры типа](generics/statically-resolved-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="f5def-157">For more information, see [Inline Functions](functions/inline-functions.md) and [Statically Resolved Type Parameters](generics/statically-resolved-type-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f5def-158">См. также</span><span class="sxs-lookup"><span data-stu-id="f5def-158">See Also</span></span>
[<span data-ttu-id="f5def-159">Члены</span><span class="sxs-lookup"><span data-stu-id="f5def-159">Members</span></span>](members/index.md)
