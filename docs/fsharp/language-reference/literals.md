---
title: Литералы (F#)
description: 'Дополнительные сведения о типах литералов в языке F #.'
ms.date: 05/16/2016
ms.openlocfilehash: f28ca0ae7a0b092bbc039d23625b883faffd241c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="literals"></a><span data-ttu-id="a219c-103">Литералы</span><span class="sxs-lookup"><span data-stu-id="a219c-103">Literals</span></span>

> [!NOTE]
<span data-ttu-id="a219c-104">По ссылкам API в этой статье вы перейдете на MSDN (для сейчас).</span><span class="sxs-lookup"><span data-stu-id="a219c-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="a219c-105">В этом разделе приведена таблица, показано, как указать тип литерала в языке F #.</span><span class="sxs-lookup"><span data-stu-id="a219c-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="a219c-106">Типы литералов</span><span class="sxs-lookup"><span data-stu-id="a219c-106">Literal Types</span></span>
<span data-ttu-id="a219c-107">Ниже приведены типы литералов в языке F #.</span><span class="sxs-lookup"><span data-stu-id="a219c-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="a219c-108">Символов, представляющих цифры в шестнадцатеричном формате, не учитывается; символы, которые определяют тип учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="a219c-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="a219c-109">Тип</span><span class="sxs-lookup"><span data-stu-id="a219c-109">Type</span></span>|<span data-ttu-id="a219c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a219c-110">Description</span></span>|<span data-ttu-id="a219c-111">Суффикс или префикс</span><span class="sxs-lookup"><span data-stu-id="a219c-111">Suffix or prefix</span></span>|<span data-ttu-id="a219c-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="a219c-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="a219c-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="a219c-113">sbyte</span></span>|<span data-ttu-id="a219c-114">8-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="a219c-114">signed 8-bit integer</span></span>|<span data-ttu-id="a219c-115">y</span><span class="sxs-lookup"><span data-stu-id="a219c-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="a219c-116">byte</span><span class="sxs-lookup"><span data-stu-id="a219c-116">byte</span></span>|<span data-ttu-id="a219c-117">натуральное число без знака 8-разрядное</span><span class="sxs-lookup"><span data-stu-id="a219c-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="a219c-118">uy</span><span class="sxs-lookup"><span data-stu-id="a219c-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="a219c-119">int16</span><span class="sxs-lookup"><span data-stu-id="a219c-119">int16</span></span>|<span data-ttu-id="a219c-120">16-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="a219c-120">signed 16-bit integer</span></span>|<span data-ttu-id="a219c-121">s</span><span class="sxs-lookup"><span data-stu-id="a219c-121">s</span></span>|`86s`|
|<span data-ttu-id="a219c-122">uint16</span><span class="sxs-lookup"><span data-stu-id="a219c-122">uint16</span></span>|<span data-ttu-id="a219c-123">натуральное число без знака 16-разрядные</span><span class="sxs-lookup"><span data-stu-id="a219c-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="a219c-124">us</span><span class="sxs-lookup"><span data-stu-id="a219c-124">us</span></span>|`86us`|
|<span data-ttu-id="a219c-125">int</span><span class="sxs-lookup"><span data-stu-id="a219c-125">int</span></span><br /><br /><span data-ttu-id="a219c-126">int32</span><span class="sxs-lookup"><span data-stu-id="a219c-126">int32</span></span>|<span data-ttu-id="a219c-127">32-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="a219c-127">signed 32-bit integer</span></span>|<span data-ttu-id="a219c-128">l или none</span><span class="sxs-lookup"><span data-stu-id="a219c-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="a219c-129">uint</span><span class="sxs-lookup"><span data-stu-id="a219c-129">uint</span></span><br /><br /><span data-ttu-id="a219c-130">uint32</span><span class="sxs-lookup"><span data-stu-id="a219c-130">uint32</span></span>|<span data-ttu-id="a219c-131">натуральное число без знака 32-разрядная</span><span class="sxs-lookup"><span data-stu-id="a219c-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="a219c-132">u или ul</span><span class="sxs-lookup"><span data-stu-id="a219c-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="a219c-133">unativeint</span><span class="sxs-lookup"><span data-stu-id="a219c-133">unativeint</span></span>|<span data-ttu-id="a219c-134">собственный указатель в виде натурального число без знака</span><span class="sxs-lookup"><span data-stu-id="a219c-134">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="a219c-135">Отменить</span><span class="sxs-lookup"><span data-stu-id="a219c-135">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="a219c-136">int64</span><span class="sxs-lookup"><span data-stu-id="a219c-136">int64</span></span>|<span data-ttu-id="a219c-137">64-разрядное знаковое целое число</span><span class="sxs-lookup"><span data-stu-id="a219c-137">signed 64-bit integer</span></span>|<span data-ttu-id="a219c-138">L</span><span class="sxs-lookup"><span data-stu-id="a219c-138">L</span></span>|`86L`|
|<span data-ttu-id="a219c-139">uint64</span><span class="sxs-lookup"><span data-stu-id="a219c-139">uint64</span></span>|<span data-ttu-id="a219c-140">натуральное число без знака x 64</span><span class="sxs-lookup"><span data-stu-id="a219c-140">unsigned 64-bit natural number</span></span>|<span data-ttu-id="a219c-141">UL</span><span class="sxs-lookup"><span data-stu-id="a219c-141">UL</span></span>|`86UL`|
|<span data-ttu-id="a219c-142">одноэлементные, float32</span><span class="sxs-lookup"><span data-stu-id="a219c-142">single, float32</span></span>|<span data-ttu-id="a219c-143">32-разрядное число с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="a219c-143">32-bit floating point number</span></span>|<span data-ttu-id="a219c-144">F или f</span><span class="sxs-lookup"><span data-stu-id="a219c-144">F or f</span></span>|<span data-ttu-id="a219c-145">`4.14F` или `4.14f`</span><span class="sxs-lookup"><span data-stu-id="a219c-145">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="a219c-146">LF</span><span class="sxs-lookup"><span data-stu-id="a219c-146">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="a219c-147">число с плавающей запятой; Double</span><span class="sxs-lookup"><span data-stu-id="a219c-147">float; double</span></span>|<span data-ttu-id="a219c-148">64-разрядное число с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="a219c-148">64-bit floating point number</span></span>|<span data-ttu-id="a219c-149">Нет</span><span class="sxs-lookup"><span data-stu-id="a219c-149">none</span></span>|<span data-ttu-id="a219c-150">`4.14`, `2.3E+32` или `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="a219c-150">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="a219c-151">LF</span><span class="sxs-lookup"><span data-stu-id="a219c-151">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="a219c-152">bigint</span><span class="sxs-lookup"><span data-stu-id="a219c-152">bigint</span></span>|<span data-ttu-id="a219c-153">целое число, не ограничиваясь 64-разрядное представление</span><span class="sxs-lookup"><span data-stu-id="a219c-153">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="a219c-154">I</span><span class="sxs-lookup"><span data-stu-id="a219c-154">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="a219c-155">decimal</span><span class="sxs-lookup"><span data-stu-id="a219c-155">decimal</span></span>|<span data-ttu-id="a219c-156">дробное число, представленное в виде с фиксированной запятой или рациональное число</span><span class="sxs-lookup"><span data-stu-id="a219c-156">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="a219c-157">M или m</span><span class="sxs-lookup"><span data-stu-id="a219c-157">M or m</span></span>|<span data-ttu-id="a219c-158">`0.7833M` или `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="a219c-158">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="a219c-159">Char</span><span class="sxs-lookup"><span data-stu-id="a219c-159">Char</span></span>|<span data-ttu-id="a219c-160">символ Юникода</span><span class="sxs-lookup"><span data-stu-id="a219c-160">Unicode character</span></span>|<span data-ttu-id="a219c-161">Нет</span><span class="sxs-lookup"><span data-stu-id="a219c-161">none</span></span>|`'a'`|
|<span data-ttu-id="a219c-162">String</span><span class="sxs-lookup"><span data-stu-id="a219c-162">String</span></span>|<span data-ttu-id="a219c-163">Строка Юникода</span><span class="sxs-lookup"><span data-stu-id="a219c-163">Unicode string</span></span>|<span data-ttu-id="a219c-164">Нет</span><span class="sxs-lookup"><span data-stu-id="a219c-164">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="a219c-165">или</span><span class="sxs-lookup"><span data-stu-id="a219c-165">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="a219c-166">или</span><span class="sxs-lookup"><span data-stu-id="a219c-166">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="a219c-167">или</span><span class="sxs-lookup"><span data-stu-id="a219c-167">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="a219c-168">См. также [строки](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="a219c-168">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="a219c-169">byte</span><span class="sxs-lookup"><span data-stu-id="a219c-169">byte</span></span>|<span data-ttu-id="a219c-170">Символ ASCII</span><span class="sxs-lookup"><span data-stu-id="a219c-170">ASCII character</span></span>|<span data-ttu-id="a219c-171">С</span><span class="sxs-lookup"><span data-stu-id="a219c-171">B</span></span>|`'a'B`|
|<span data-ttu-id="a219c-172">byte[]</span><span class="sxs-lookup"><span data-stu-id="a219c-172">byte[]</span></span>|<span data-ttu-id="a219c-173">Строка ASCII</span><span class="sxs-lookup"><span data-stu-id="a219c-173">ASCII string</span></span>|<span data-ttu-id="a219c-174">С</span><span class="sxs-lookup"><span data-stu-id="a219c-174">B</span></span>|`"text"B`|
|<span data-ttu-id="a219c-175">String или byte]</span><span class="sxs-lookup"><span data-stu-id="a219c-175">String or byte[]</span></span>|<span data-ttu-id="a219c-176">буквальная строка</span><span class="sxs-lookup"><span data-stu-id="a219c-176">verbatim string</span></span>|<span data-ttu-id="a219c-177">префикс @</span><span class="sxs-lookup"><span data-stu-id="a219c-177">@ prefix</span></span>|<span data-ttu-id="a219c-178">`@"\\server\share"` (Юникод)</span><span class="sxs-lookup"><span data-stu-id="a219c-178">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="a219c-179">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="a219c-179">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="remarks"></a><span data-ttu-id="a219c-180">Примечания</span><span class="sxs-lookup"><span data-stu-id="a219c-180">Remarks</span></span>
<span data-ttu-id="a219c-181">Строки в Юникоде может содержать явные кодировки, которые можно задать с помощью `\u` следуют 16-разрядное шестнадцатеричное или кодировки UTF-32, можно указать с помощью `\U` следуют 32-разрядных шестнадцатеричный код, который представляет строку в Юникоде суррогатная пара.</span><span class="sxs-lookup"><span data-stu-id="a219c-181">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="a219c-182">Начиная с версии 3.1 языка F #, можно использовать `+` входа для объединения строковых литералов.</span><span class="sxs-lookup"><span data-stu-id="a219c-182">As of F# 3.1, you can use the `+` sign to combine string literals.</span></span> <span data-ttu-id="a219c-183">Можно также использовать побитового или (`|||`) оператор для объединения, перечисления флагов.</span><span class="sxs-lookup"><span data-stu-id="a219c-183">You can also use the bitwise or (`|||`) operator to combine enum flags.</span></span> <span data-ttu-id="a219c-184">Например следующий код является допустимым в F # 3.1:</span><span class="sxs-lookup"><span data-stu-id="a219c-184">For example, the following code is legal in F# 3.1:</span></span>

```fsharp
[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

<span data-ttu-id="a219c-185">Использование других побитовых операторов не разрешена.</span><span class="sxs-lookup"><span data-stu-id="a219c-185">The use of other bitwise operators isn't allowed.</span></span>


## <a name="named-literals"></a><span data-ttu-id="a219c-186">Именованных литералов</span><span class="sxs-lookup"><span data-stu-id="a219c-186">Named Literals</span></span>
<span data-ttu-id="a219c-187">Значения, которые должны быть константами могут быть помечены с помощью [литерала](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) атрибута.</span><span class="sxs-lookup"><span data-stu-id="a219c-187">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="a219c-188">Этот атрибут приводит к сбою значение будет компилироваться как константа.</span><span class="sxs-lookup"><span data-stu-id="a219c-188">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="a219c-189">В выражениях сопоставления шаблонов идентификаторы которых начинаются с символов нижнего регистра всегда обрабатываются как переменные для привязки, а не как литералы, поэтому следует использовать прописные буквы при определении литералов.</span><span class="sxs-lookup"><span data-stu-id="a219c-189">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="a219c-190">Целые числа в другую систему исчисления</span><span class="sxs-lookup"><span data-stu-id="a219c-190">Integers In Other Bases</span></span>

<span data-ttu-id="a219c-191">32-разрядных целых чисел со знаком может также быть задан шестнадцатеричные, восьмеричные и двоичные `0x`, `0o` или `0b` префикса соответственно.</span><span class="sxs-lookup"><span data-stu-id="a219c-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="a219c-192">Символ подчеркивания в числовые литералы</span><span class="sxs-lookup"><span data-stu-id="a219c-192">Underscores in Numeric Literals</span></span>

<span data-ttu-id="a219c-193">Начиная с версии 4.1 F #, можно разделить цифр с символа подчеркивания (`_`).</span><span class="sxs-lookup"><span data-stu-id="a219c-193">Starting with F# 4.1, you can separate digits with the underscore character (`_`).</span></span>

```fsharp
let DeadBeef = 0xDEAD_BEEF

let DeadBeefAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let ExampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="a219c-194">См. также</span><span class="sxs-lookup"><span data-stu-id="a219c-194">See Also</span></span>

[<span data-ttu-id="a219c-195">Класс Core.LiteralAttribute</span><span class="sxs-lookup"><span data-stu-id="a219c-195">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
