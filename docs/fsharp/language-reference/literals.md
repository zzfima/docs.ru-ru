---
title: "Литералы (F#)"
description: "Дополнительные сведения о типах литералов в языке F #."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4b1d6e9d-f933-4cd4-966d-d643152c27e4
ms.openlocfilehash: 6bb1f233b6846e226c4e73aee00b8cf77735fe2d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="literals"></a><span data-ttu-id="09c21-104">Литералы</span><span class="sxs-lookup"><span data-stu-id="09c21-104">Literals</span></span>

> [!NOTE]
<span data-ttu-id="09c21-105">По ссылкам API в этой статье вы перейдете на MSDN (для сейчас).</span><span class="sxs-lookup"><span data-stu-id="09c21-105">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="09c21-106">В этом разделе приведена таблица, показано, как указать тип литерала в языке F #.</span><span class="sxs-lookup"><span data-stu-id="09c21-106">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="09c21-107">Типы литералов</span><span class="sxs-lookup"><span data-stu-id="09c21-107">Literal Types</span></span>
<span data-ttu-id="09c21-108">Ниже приведены типы литералов в языке F #.</span><span class="sxs-lookup"><span data-stu-id="09c21-108">The following table shows the literal types in F#.</span></span> <span data-ttu-id="09c21-109">Символов, представляющих цифры в шестнадцатеричном формате, не учитывается; символы, которые определяют тип учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="09c21-109">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="09c21-110">Тип</span><span class="sxs-lookup"><span data-stu-id="09c21-110">Type</span></span>|<span data-ttu-id="09c21-111">Описание</span><span class="sxs-lookup"><span data-stu-id="09c21-111">Description</span></span>|<span data-ttu-id="09c21-112">Суффикс или префикс</span><span class="sxs-lookup"><span data-stu-id="09c21-112">Suffix or prefix</span></span>|<span data-ttu-id="09c21-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="09c21-113">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="09c21-114">sbyte</span><span class="sxs-lookup"><span data-stu-id="09c21-114">sbyte</span></span>|<span data-ttu-id="09c21-115">8-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="09c21-115">signed 8-bit integer</span></span>|<span data-ttu-id="09c21-116">y</span><span class="sxs-lookup"><span data-stu-id="09c21-116">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="09c21-117">byte</span><span class="sxs-lookup"><span data-stu-id="09c21-117">byte</span></span>|<span data-ttu-id="09c21-118">натуральное число без знака 8-разрядное</span><span class="sxs-lookup"><span data-stu-id="09c21-118">unsigned 8-bit natural number</span></span>|<span data-ttu-id="09c21-119">uy</span><span class="sxs-lookup"><span data-stu-id="09c21-119">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="09c21-120">int16</span><span class="sxs-lookup"><span data-stu-id="09c21-120">int16</span></span>|<span data-ttu-id="09c21-121">16-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="09c21-121">signed 16-bit integer</span></span>|<span data-ttu-id="09c21-122">s</span><span class="sxs-lookup"><span data-stu-id="09c21-122">s</span></span>|`86s`|
|<span data-ttu-id="09c21-123">uint16</span><span class="sxs-lookup"><span data-stu-id="09c21-123">uint16</span></span>|<span data-ttu-id="09c21-124">натуральное число без знака 16-разрядные</span><span class="sxs-lookup"><span data-stu-id="09c21-124">unsigned 16-bit natural number</span></span>|<span data-ttu-id="09c21-125">us</span><span class="sxs-lookup"><span data-stu-id="09c21-125">us</span></span>|`86us`|
|<span data-ttu-id="09c21-126">int</span><span class="sxs-lookup"><span data-stu-id="09c21-126">int</span></span><br /><br /><span data-ttu-id="09c21-127">int32</span><span class="sxs-lookup"><span data-stu-id="09c21-127">int32</span></span>|<span data-ttu-id="09c21-128">32-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="09c21-128">signed 32-bit integer</span></span>|<span data-ttu-id="09c21-129">l или none</span><span class="sxs-lookup"><span data-stu-id="09c21-129">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="09c21-130">uint</span><span class="sxs-lookup"><span data-stu-id="09c21-130">uint</span></span><br /><br /><span data-ttu-id="09c21-131">uint32</span><span class="sxs-lookup"><span data-stu-id="09c21-131">uint32</span></span>|<span data-ttu-id="09c21-132">натуральное число без знака 32-разрядная</span><span class="sxs-lookup"><span data-stu-id="09c21-132">unsigned 32-bit natural number</span></span>|<span data-ttu-id="09c21-133">u или ul</span><span class="sxs-lookup"><span data-stu-id="09c21-133">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="09c21-134">unativeint</span><span class="sxs-lookup"><span data-stu-id="09c21-134">unativeint</span></span>|<span data-ttu-id="09c21-135">собственный указатель в виде натурального число без знака</span><span class="sxs-lookup"><span data-stu-id="09c21-135">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="09c21-136">Отменить</span><span class="sxs-lookup"><span data-stu-id="09c21-136">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="09c21-137">int64</span><span class="sxs-lookup"><span data-stu-id="09c21-137">int64</span></span>|<span data-ttu-id="09c21-138">64-разрядное знаковое целое число</span><span class="sxs-lookup"><span data-stu-id="09c21-138">signed 64-bit integer</span></span>|<span data-ttu-id="09c21-139">L</span><span class="sxs-lookup"><span data-stu-id="09c21-139">L</span></span>|`86L`|
|<span data-ttu-id="09c21-140">uint64</span><span class="sxs-lookup"><span data-stu-id="09c21-140">uint64</span></span>|<span data-ttu-id="09c21-141">натуральное число без знака x 64</span><span class="sxs-lookup"><span data-stu-id="09c21-141">unsigned 64-bit natural number</span></span>|<span data-ttu-id="09c21-142">UL</span><span class="sxs-lookup"><span data-stu-id="09c21-142">UL</span></span>|`86UL`|
|<span data-ttu-id="09c21-143">одноэлементные, float32</span><span class="sxs-lookup"><span data-stu-id="09c21-143">single, float32</span></span>|<span data-ttu-id="09c21-144">32-разрядное число с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="09c21-144">32-bit floating point number</span></span>|<span data-ttu-id="09c21-145">F или f</span><span class="sxs-lookup"><span data-stu-id="09c21-145">F or f</span></span>|<span data-ttu-id="09c21-146">`4.14F` или `4.14f`</span><span class="sxs-lookup"><span data-stu-id="09c21-146">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="09c21-147">LF</span><span class="sxs-lookup"><span data-stu-id="09c21-147">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="09c21-148">число с плавающей запятой; Double</span><span class="sxs-lookup"><span data-stu-id="09c21-148">float; double</span></span>|<span data-ttu-id="09c21-149">64-разрядное число с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="09c21-149">64-bit floating point number</span></span>|<span data-ttu-id="09c21-150">Нет</span><span class="sxs-lookup"><span data-stu-id="09c21-150">none</span></span>|<span data-ttu-id="09c21-151">`4.14`, `2.3E+32` или `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="09c21-151">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="09c21-152">LF</span><span class="sxs-lookup"><span data-stu-id="09c21-152">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="09c21-153">bigint</span><span class="sxs-lookup"><span data-stu-id="09c21-153">bigint</span></span>|<span data-ttu-id="09c21-154">целое число, не ограничиваясь 64-разрядное представление</span><span class="sxs-lookup"><span data-stu-id="09c21-154">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="09c21-155">I</span><span class="sxs-lookup"><span data-stu-id="09c21-155">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="09c21-156">decimal</span><span class="sxs-lookup"><span data-stu-id="09c21-156">decimal</span></span>|<span data-ttu-id="09c21-157">дробное число, представленное в виде с фиксированной запятой или рациональное число</span><span class="sxs-lookup"><span data-stu-id="09c21-157">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="09c21-158">M или m</span><span class="sxs-lookup"><span data-stu-id="09c21-158">M or m</span></span>|<span data-ttu-id="09c21-159">`0.7833M` или `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="09c21-159">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="09c21-160">Char</span><span class="sxs-lookup"><span data-stu-id="09c21-160">Char</span></span>|<span data-ttu-id="09c21-161">символ Юникода</span><span class="sxs-lookup"><span data-stu-id="09c21-161">Unicode character</span></span>|<span data-ttu-id="09c21-162">Нет</span><span class="sxs-lookup"><span data-stu-id="09c21-162">none</span></span>|`'a'`|
|<span data-ttu-id="09c21-163">Строка</span><span class="sxs-lookup"><span data-stu-id="09c21-163">String</span></span>|<span data-ttu-id="09c21-164">Строка Юникода</span><span class="sxs-lookup"><span data-stu-id="09c21-164">Unicode string</span></span>|<span data-ttu-id="09c21-165">Нет</span><span class="sxs-lookup"><span data-stu-id="09c21-165">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="09c21-166">или</span><span class="sxs-lookup"><span data-stu-id="09c21-166">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="09c21-167">или</span><span class="sxs-lookup"><span data-stu-id="09c21-167">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="09c21-168">или</span><span class="sxs-lookup"><span data-stu-id="09c21-168">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="09c21-169">См. также [строки](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="09c21-169">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="09c21-170">byte</span><span class="sxs-lookup"><span data-stu-id="09c21-170">byte</span></span>|<span data-ttu-id="09c21-171">Символ ASCII</span><span class="sxs-lookup"><span data-stu-id="09c21-171">ASCII character</span></span>|<span data-ttu-id="09c21-172">B</span><span class="sxs-lookup"><span data-stu-id="09c21-172">B</span></span>|`'a'B`|
|<span data-ttu-id="09c21-173">byte[]</span><span class="sxs-lookup"><span data-stu-id="09c21-173">byte[]</span></span>|<span data-ttu-id="09c21-174">Строка ASCII</span><span class="sxs-lookup"><span data-stu-id="09c21-174">ASCII string</span></span>|<span data-ttu-id="09c21-175">B</span><span class="sxs-lookup"><span data-stu-id="09c21-175">B</span></span>|`"text"B`|
|<span data-ttu-id="09c21-176">String или byte]</span><span class="sxs-lookup"><span data-stu-id="09c21-176">String or byte[]</span></span>|<span data-ttu-id="09c21-177">буквальная строка</span><span class="sxs-lookup"><span data-stu-id="09c21-177">verbatim string</span></span>|<span data-ttu-id="09c21-178">префикс @</span><span class="sxs-lookup"><span data-stu-id="09c21-178">@ prefix</span></span>|<span data-ttu-id="09c21-179">`@"\\server\share"`(Юникод)</span><span class="sxs-lookup"><span data-stu-id="09c21-179">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="09c21-180">`@"\\server\share"B`(ASCII)</span><span class="sxs-lookup"><span data-stu-id="09c21-180">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="remarks"></a><span data-ttu-id="09c21-181">Примечания</span><span class="sxs-lookup"><span data-stu-id="09c21-181">Remarks</span></span>
<span data-ttu-id="09c21-182">Строки в Юникоде может содержать явные кодировки, которые можно задать с помощью `\u` следуют 16-разрядное шестнадцатеричное или кодировки UTF-32, можно указать с помощью `\U` следуют 32-разрядных шестнадцатеричный код, который представляет строку в Юникоде суррогатная пара.</span><span class="sxs-lookup"><span data-stu-id="09c21-182">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="09c21-183">Начиная с версии 3.1 языка F #, можно использовать `+` входа для объединения строковых литералов.</span><span class="sxs-lookup"><span data-stu-id="09c21-183">As of F# 3.1, you can use the `+` sign to combine string literals.</span></span> <span data-ttu-id="09c21-184">Можно также использовать побитового или (`|||`) оператор для объединения, перечисления флагов.</span><span class="sxs-lookup"><span data-stu-id="09c21-184">You can also use the bitwise or (`|||`) operator to combine enum flags.</span></span> <span data-ttu-id="09c21-185">Например следующий код является допустимым в F # 3.1:</span><span class="sxs-lookup"><span data-stu-id="09c21-185">For example, the following code is legal in F# 3.1:</span></span>

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

<span data-ttu-id="09c21-186">Использование других побитовых операторов не разрешена.</span><span class="sxs-lookup"><span data-stu-id="09c21-186">The use of other bitwise operators isn't allowed.</span></span>


## <a name="named-literals"></a><span data-ttu-id="09c21-187">Именованных литералов</span><span class="sxs-lookup"><span data-stu-id="09c21-187">Named Literals</span></span>
<span data-ttu-id="09c21-188">Значения, которые должны быть константами могут быть помечены с помощью [литерала](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) атрибута.</span><span class="sxs-lookup"><span data-stu-id="09c21-188">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="09c21-189">Этот атрибут приводит к сбою значение будет компилироваться как константа.</span><span class="sxs-lookup"><span data-stu-id="09c21-189">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="09c21-190">В выражениях сопоставления шаблонов идентификаторы которых начинаются с символов нижнего регистра всегда обрабатываются как переменные для привязки, а не как литералы, поэтому следует использовать прописные буквы при определении литералов.</span><span class="sxs-lookup"><span data-stu-id="09c21-190">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="09c21-191">Целые числа в другую систему исчисления</span><span class="sxs-lookup"><span data-stu-id="09c21-191">Integers In Other Bases</span></span>

<span data-ttu-id="09c21-192">32-разрядных целых чисел со знаком может также быть задан шестнадцатеричные, восьмеричные и двоичные `0x`, `0o` или `0b` префикса соответственно.</span><span class="sxs-lookup"><span data-stu-id="09c21-192">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="09c21-193">Символ подчеркивания в числовые литералы</span><span class="sxs-lookup"><span data-stu-id="09c21-193">Underscores in Numeric Literals</span></span>

<span data-ttu-id="09c21-194">Начиная с версии 4.1 F #, можно разделить цифр с символа подчеркивания (`_`).</span><span class="sxs-lookup"><span data-stu-id="09c21-194">Starting with F# 4.1, you can separate digits with the underscore character (`_`).</span></span>

```fsharp
let DeadBeef = 0xDEAD_BEEF

let DeadBeefAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let ExampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="09c21-195">См. также</span><span class="sxs-lookup"><span data-stu-id="09c21-195">See Also</span></span>

[<span data-ttu-id="09c21-196">Класс Core.LiteralAttribute</span><span class="sxs-lookup"><span data-stu-id="09c21-196">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
