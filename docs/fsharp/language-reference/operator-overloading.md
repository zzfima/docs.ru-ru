---
title: Перегрузка операторов (F#)
description: 'Узнайте, как перегрузка арифметических операторов в классе или типе записи, а также на глобальном уровне в F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 6232ebf215289e6a22b9d77fbd5fa67b82460486
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087303"
---
# <a name="operator-overloading"></a><span data-ttu-id="931b4-103">Перегрузка операторов</span><span class="sxs-lookup"><span data-stu-id="931b4-103">Operator Overloading</span></span>

<span data-ttu-id="931b4-104">В этом разделе описывает перегрузку арифметических операторов в классе или типе записи, а также на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="931b4-104">This topic describes how to overload arithmetic operators in a class or record type, and at the global level.</span></span>

## <a name="syntax"></a><span data-ttu-id="931b4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="931b4-105">Syntax</span></span>

```fsharp
// Overloading an operator as a class or record member.
static member (operator-symbols) (parameter-list) =
    method-body
// Overloading an operator at the global level
let [inline] (operator-symbols) parameter-list = function-body
```

## <a name="remarks"></a><span data-ttu-id="931b4-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="931b4-106">Remarks</span></span>

<span data-ttu-id="931b4-107">В приведенном выше синтаксисе *символ оператора* является одним из `+`, `-`, `*`, `/`, `=`, и т. д.</span><span class="sxs-lookup"><span data-stu-id="931b4-107">In the previous syntax, the *operator-symbol* is one of `+`, `-`, `*`, `/`, `=`, and so on.</span></span> <span data-ttu-id="931b4-108">*Список параметров* задает операнды в порядке, они отображаются в обычном синтаксисе данного оператора.</span><span class="sxs-lookup"><span data-stu-id="931b4-108">The *parameter-list* specifies the operands in the order they appear in the usual syntax for that operator.</span></span> <span data-ttu-id="931b4-109">*Тело метода* создает результирующее значение.</span><span class="sxs-lookup"><span data-stu-id="931b4-109">The *method-body* constructs the resulting value.</span></span>

<span data-ttu-id="931b4-110">Перегрузки операторов для операторов должны быть статическими.</span><span class="sxs-lookup"><span data-stu-id="931b4-110">Operator overloads for operators must be static.</span></span> <span data-ttu-id="931b4-111">Оператор перегрузок для унарных операторов, таких как `+` и `-`, необходимо использовать тильду (`~`) в *символ оператора* прошел оператора унарного оператора и бинарного оператора, как показано на следующее объявление.</span><span class="sxs-lookup"><span data-stu-id="931b4-111">Operator overloads for unary operators, such as `+` and `-`, must use a tilde (`~`) in the *operator-symbol* to indicate that the operator is a unary operator and not a binary operator, as shown in the following declaration.</span></span>

```fsharp
static member (~-) (v : Vector)
```

<span data-ttu-id="931b4-112">Следующий код иллюстрирует класс vector, имеет только два оператора: один для "унарный минус", а другой для умножения на скаляр.</span><span class="sxs-lookup"><span data-stu-id="931b4-112">The following code illustrates a vector class that has just two operators, one for unary minus and one for multiplication by a scalar.</span></span> <span data-ttu-id="931b4-113">В примере две перегрузки для скалярного умножения необходимы, так как оператор должен работать независимо от порядка, в котором отображаются вектора и скалярные.</span><span class="sxs-lookup"><span data-stu-id="931b4-113">In the example, two overloads for scalar multiplication are needed because the operator must work regardless of the order in which the vector and scalar appear.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a><span data-ttu-id="931b4-114">Создание новых операторов</span><span class="sxs-lookup"><span data-stu-id="931b4-114">Creating New Operators</span></span>

<span data-ttu-id="931b4-115">Все стандартные операторы можно перегружать, но вы также можете создать новые операторы из последовательностей определенных символов.</span><span class="sxs-lookup"><span data-stu-id="931b4-115">You can overload all the standard operators, but you can also create new operators out of sequences of certain characters.</span></span> <span data-ttu-id="931b4-116">Допустимые знаки операторов `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, и `~`.</span><span class="sxs-lookup"><span data-stu-id="931b4-116">Allowed operator characters are `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, and `~`.</span></span> <span data-ttu-id="931b4-117">`~` Символ имеет особое значение делает оператор унарным и не является частью последовательности символов оператора.</span><span class="sxs-lookup"><span data-stu-id="931b4-117">The `~` character has the special meaning of making an operator unary, and is not part of the operator character sequence.</span></span> <span data-ttu-id="931b4-118">Не все операторы могут выполняться унарный.</span><span class="sxs-lookup"><span data-stu-id="931b4-118">Not all operators can be made unary.</span></span>

<span data-ttu-id="931b4-119">В зависимости от символьной последовательности, используемого ваш оператор будет иметь приоритет и ассоциативность операторов.</span><span class="sxs-lookup"><span data-stu-id="931b4-119">Depending on the exact character sequence you use, your operator will have a certain precedence and associativity.</span></span> <span data-ttu-id="931b4-120">Ассоциативность операторов могут быть либо слева направо или справа налево и используется каждый раз, когда операторы тот же уровень приоритета, отображаются в последовательности без скобок.</span><span class="sxs-lookup"><span data-stu-id="931b4-120">Associativity can be either left to right or right to left and is used whenever operators of the same level of precedence appear in sequence without parentheses.</span></span>

<span data-ttu-id="931b4-121">Символ оператора `.` не влияет на более высокий приоритет, поэтому, например, если вы хотите определить собственную версию умножения, имеющий тот же приоритет и ассоциативность операторов, что и обычное умножение, можно создать операторов, таких как `.*`.</span><span class="sxs-lookup"><span data-stu-id="931b4-121">The operator character `.` does not affect precedence, so that, for example, if you want to define your own version of multiplication that has the same precedence and associativity as ordinary multiplication, you could create operators such as `.*`.</span></span>

<span data-ttu-id="931b4-122">Только операторы `?` и `?<-` может начинаться с `?`.</span><span class="sxs-lookup"><span data-stu-id="931b4-122">Only the operators `?` and `?<-` may start with `?`.</span></span>

<span data-ttu-id="931b4-123">Таблица, показывающая всех операторов в F # можно найти в [Справочник символов и операторов](symbol-and-operator-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="931b4-123">A table that shows the precedence of all operators in F# can be found in [Symbol and Operator Reference](symbol-and-operator-reference/index.md).</span></span>

## <a name="overloaded-operator-names"></a><span data-ttu-id="931b4-124">Имена перегруженных операторов</span><span class="sxs-lookup"><span data-stu-id="931b4-124">Overloaded Operator Names</span></span>

<span data-ttu-id="931b4-125">Когда компилятор F # компилирует выражения оператора, он создает метод, который имеет имя, созданный компилятором, для этого оператора.</span><span class="sxs-lookup"><span data-stu-id="931b4-125">When the F# compiler compiles an operator expression, it generates a method that has a compiler-generated name for that operator.</span></span> <span data-ttu-id="931b4-126">Это имя, отображаемое в промежуточный язык Майкрософт (MSIL) для метода, а также в отражении и IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="931b4-126">This is the name that appears in the Microsoft intermediate language (MSIL) for the method, and also in reflection and IntelliSense.</span></span> <span data-ttu-id="931b4-127">Обычно необходимо использовать эти имена в коде F #.</span><span class="sxs-lookup"><span data-stu-id="931b4-127">You do not normally need to use these names in F# code.</span></span>

<span data-ttu-id="931b4-128">В следующей таблице показаны стандартные операторы и соответствующие им создаются имена.</span><span class="sxs-lookup"><span data-stu-id="931b4-128">The following table shows the standard operators and their corresponding generated names.</span></span>

|<span data-ttu-id="931b4-129">Оператор</span><span class="sxs-lookup"><span data-stu-id="931b4-129">Operator</span></span>|<span data-ttu-id="931b4-130">Созданное имя</span><span class="sxs-lookup"><span data-stu-id="931b4-130">Generated name</span></span>|
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

<span data-ttu-id="931b4-131">Другие сочетания символов операторов, не перечисленные здесь можно использовать в качестве операторов и имеют имена, сформированные путем объединения имена отдельных символов из следующей таблицы.</span><span class="sxs-lookup"><span data-stu-id="931b4-131">Other combinations of operator characters that are not listed here can be used as operators and have names that are made up by concatenating names for the individual characters from the following table.</span></span> <span data-ttu-id="931b4-132">Например +!</span><span class="sxs-lookup"><span data-stu-id="931b4-132">For example, +!</span></span> <span data-ttu-id="931b4-133">становится `op_PlusBang`.</span><span class="sxs-lookup"><span data-stu-id="931b4-133">becomes `op_PlusBang`.</span></span>

|<span data-ttu-id="931b4-134">Символ оператора</span><span class="sxs-lookup"><span data-stu-id="931b4-134">Operator character</span></span>|<span data-ttu-id="931b4-135">name</span><span class="sxs-lookup"><span data-stu-id="931b4-135">Name</span></span>|
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

## <a name="prefix-and-infix-operators"></a><span data-ttu-id="931b4-136">Префикс и инфиксные операторы</span><span class="sxs-lookup"><span data-stu-id="931b4-136">Prefix and Infix Operators</span></span>

<span data-ttu-id="931b4-137">*Префикс* операторы должны размещаться перед операнда или операндов, подобно функции.</span><span class="sxs-lookup"><span data-stu-id="931b4-137">*Prefix* operators are expected to be placed in front of an operand or operands, much like a function.</span></span> <span data-ttu-id="931b4-138">*Инфиксные* операторы должны располагаться между двумя операндами.</span><span class="sxs-lookup"><span data-stu-id="931b4-138">*Infix* operators are expected to be placed between the two operands.</span></span>

<span data-ttu-id="931b4-139">Только определенные операторы можно использовать в качестве префикса операторов.</span><span class="sxs-lookup"><span data-stu-id="931b4-139">Only certain operators can be used as prefix operators.</span></span> <span data-ttu-id="931b4-140">Некоторые операторы всегда являются префиксные операторы, другие могут быть инфиксные или префикс и остальные всегда являются инфиксные операторы.</span><span class="sxs-lookup"><span data-stu-id="931b4-140">Some operators are always prefix operators, others can be infix or prefix, and the rest are always infix operators.</span></span> <span data-ttu-id="931b4-141">Операторы, которые начинаются с `!`, за исключением `!=`и оператор `~`, и не будут повторяться последовательности`~`, всегда являются операторами префикс.</span><span class="sxs-lookup"><span data-stu-id="931b4-141">Operators that begin with `!`, except `!=`, and the operator `~`, or repeated sequences of`~`, are always prefix operators.</span></span> <span data-ttu-id="931b4-142">Операторы `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, и `%%` может быть префиксные операторы или инфиксные операторы.</span><span class="sxs-lookup"><span data-stu-id="931b4-142">The operators `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, and `%%` can be prefix operators or infix operators.</span></span> <span data-ttu-id="931b4-143">Префиксная версия этих операторов было отличить от версии инфиксные путем добавления `~` в начале префиксный оператор, если она определена.</span><span class="sxs-lookup"><span data-stu-id="931b4-143">You distinguish the prefix version of these operators from the infix version by adding a `~` at the beginning of a prefix operator when it is defined.</span></span> <span data-ttu-id="931b4-144">`~` Не используется при использовании оператора, только в том случае, если она определена.</span><span class="sxs-lookup"><span data-stu-id="931b4-144">The `~` is not used when you use the operator, only when it is defined.</span></span>

## <a name="example"></a><span data-ttu-id="931b4-145">Пример</span><span class="sxs-lookup"><span data-stu-id="931b4-145">Example</span></span>

<span data-ttu-id="931b4-146">Следующий код иллюстрирует использование перегрузки операторов для реализации дробного типа.</span><span class="sxs-lookup"><span data-stu-id="931b4-146">The following code illustrates the use of operator overloading to implement a fraction type.</span></span> <span data-ttu-id="931b4-147">Небольшую представляется числителя и знаменателя.</span><span class="sxs-lookup"><span data-stu-id="931b4-147">A fraction is represented by a numerator and a denominator.</span></span> <span data-ttu-id="931b4-148">Функция `hcf` используется для определения наибольшего общего делителя, который используется для сокращения дробей.</span><span class="sxs-lookup"><span data-stu-id="931b4-148">The function `hcf` is used to determine the highest common factor, which is used to reduce fractions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4002.fs)]

<span data-ttu-id="931b4-149">**Выходные данные:**</span><span class="sxs-lookup"><span data-stu-id="931b4-149">**Output:**</span></span>

```
3/4 + 1/2 = 5/4
3/4 - 1/2 = 1/4
3/4 * 1/2 = 3/8
3/4 / 1/2 = 3/2
3/4 + 1 = 7/4
```

## <a name="operators-at-the-global-level"></a><span data-ttu-id="931b4-150">Операторы на глобальном уровне</span><span class="sxs-lookup"><span data-stu-id="931b4-150">Operators at the Global Level</span></span>

<span data-ttu-id="931b4-151">Можно также определить операторы на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="931b4-151">You can also define operators at the global level.</span></span> <span data-ttu-id="931b4-152">В следующем коде определяется оператор `+?`.</span><span class="sxs-lookup"><span data-stu-id="931b4-152">The following code defines an operator `+?`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

<span data-ttu-id="931b4-153">Приведенный выше код является `12`.</span><span class="sxs-lookup"><span data-stu-id="931b4-153">The output of the above code is `12`.</span></span>

<span data-ttu-id="931b4-154">Можно переопределить обычных арифметических операторов таким образом, так как правила области для языка F # диктовать, что новые определенные операторы имеют приоритет над встроенными операторами.</span><span class="sxs-lookup"><span data-stu-id="931b4-154">You can redefine the regular arithmetic operators in this manner because the scoping rules for F# dictate that newly defined operators take precedence over the built-in operators.</span></span>

<span data-ttu-id="931b4-155">Ключевое слово `inline` часто используется с глобальных операторов, которые часто бывают небольших функций, которые лучше всего интегрируются в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="931b4-155">The keyword `inline` is often used with global operators, which are often small functions that are best integrated into the calling code.</span></span> <span data-ttu-id="931b4-156">Встроенные функции оператор решений также позволяет пользователям работать с статически разрешаемые параметры типа для получения статически разрешаемым универсального кода.</span><span class="sxs-lookup"><span data-stu-id="931b4-156">Making operator functions inline also enables them to work with statically resolved type parameters to produce statically resolved generic code.</span></span> <span data-ttu-id="931b4-157">Дополнительные сведения см. в разделе [встраиваемые функции](functions/inline-functions.md) и [статически разрешаемые параметры типов](generics/statically-resolved-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="931b4-157">For more information, see [Inline Functions](functions/inline-functions.md) and [Statically Resolved Type Parameters](generics/statically-resolved-type-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="931b4-158">См. также</span><span class="sxs-lookup"><span data-stu-id="931b4-158">See also</span></span>

- [<span data-ttu-id="931b4-159">Члены</span><span class="sxs-lookup"><span data-stu-id="931b4-159">Members</span></span>](members/index.md)
