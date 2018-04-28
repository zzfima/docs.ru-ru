---
title: Литералы (F#)
description: 'Дополнительные сведения о типах литералов в языке F #.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 961d6a10122c5d5c691d394efa8d2b7b31a80453
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="literals"></a><span data-ttu-id="90feb-103">Литералы</span><span class="sxs-lookup"><span data-stu-id="90feb-103">Literals</span></span>

> [!NOTE]
<span data-ttu-id="90feb-104">По ссылкам API в этой статье вы перейдете на MSDN (для сейчас).</span><span class="sxs-lookup"><span data-stu-id="90feb-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="90feb-105">В этом разделе приведена таблица, показано, как указать тип литерала в языке F #.</span><span class="sxs-lookup"><span data-stu-id="90feb-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="90feb-106">Типы литералов</span><span class="sxs-lookup"><span data-stu-id="90feb-106">Literal Types</span></span>
<span data-ttu-id="90feb-107">Ниже приведены типы литералов в языке F #.</span><span class="sxs-lookup"><span data-stu-id="90feb-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="90feb-108">Символов, представляющих цифры в шестнадцатеричном формате, не учитывается; символы, которые определяют тип учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="90feb-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="90feb-109">Тип</span><span class="sxs-lookup"><span data-stu-id="90feb-109">Type</span></span>|<span data-ttu-id="90feb-110">Описание</span><span class="sxs-lookup"><span data-stu-id="90feb-110">Description</span></span>|<span data-ttu-id="90feb-111">Суффикс или префикс</span><span class="sxs-lookup"><span data-stu-id="90feb-111">Suffix or prefix</span></span>|<span data-ttu-id="90feb-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="90feb-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="90feb-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="90feb-113">sbyte</span></span>|<span data-ttu-id="90feb-114">8-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="90feb-114">signed 8-bit integer</span></span>|<span data-ttu-id="90feb-115">y</span><span class="sxs-lookup"><span data-stu-id="90feb-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="90feb-116">byte</span><span class="sxs-lookup"><span data-stu-id="90feb-116">byte</span></span>|<span data-ttu-id="90feb-117">натуральное число без знака 8-разрядное</span><span class="sxs-lookup"><span data-stu-id="90feb-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="90feb-118">uy</span><span class="sxs-lookup"><span data-stu-id="90feb-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="90feb-119">int16</span><span class="sxs-lookup"><span data-stu-id="90feb-119">int16</span></span>|<span data-ttu-id="90feb-120">16-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="90feb-120">signed 16-bit integer</span></span>|<span data-ttu-id="90feb-121">s</span><span class="sxs-lookup"><span data-stu-id="90feb-121">s</span></span>|`86s`|
|<span data-ttu-id="90feb-122">uint16</span><span class="sxs-lookup"><span data-stu-id="90feb-122">uint16</span></span>|<span data-ttu-id="90feb-123">натуральное число без знака 16-разрядные</span><span class="sxs-lookup"><span data-stu-id="90feb-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="90feb-124">us</span><span class="sxs-lookup"><span data-stu-id="90feb-124">us</span></span>|`86us`|
|<span data-ttu-id="90feb-125">int</span><span class="sxs-lookup"><span data-stu-id="90feb-125">int</span></span><br /><br /><span data-ttu-id="90feb-126">int32</span><span class="sxs-lookup"><span data-stu-id="90feb-126">int32</span></span>|<span data-ttu-id="90feb-127">32-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="90feb-127">signed 32-bit integer</span></span>|<span data-ttu-id="90feb-128">l или none</span><span class="sxs-lookup"><span data-stu-id="90feb-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="90feb-129">uint</span><span class="sxs-lookup"><span data-stu-id="90feb-129">uint</span></span><br /><br /><span data-ttu-id="90feb-130">uint32</span><span class="sxs-lookup"><span data-stu-id="90feb-130">uint32</span></span>|<span data-ttu-id="90feb-131">натуральное число без знака 32-разрядная</span><span class="sxs-lookup"><span data-stu-id="90feb-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="90feb-132">u или ul</span><span class="sxs-lookup"><span data-stu-id="90feb-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="90feb-133">unativeint</span><span class="sxs-lookup"><span data-stu-id="90feb-133">unativeint</span></span>|<span data-ttu-id="90feb-134">собственный указатель в виде натурального число без знака</span><span class="sxs-lookup"><span data-stu-id="90feb-134">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="90feb-135">Отменить</span><span class="sxs-lookup"><span data-stu-id="90feb-135">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="90feb-136">int64</span><span class="sxs-lookup"><span data-stu-id="90feb-136">int64</span></span>|<span data-ttu-id="90feb-137">64-разрядное знаковое целое число</span><span class="sxs-lookup"><span data-stu-id="90feb-137">signed 64-bit integer</span></span>|<span data-ttu-id="90feb-138">L</span><span class="sxs-lookup"><span data-stu-id="90feb-138">L</span></span>|`86L`|
|<span data-ttu-id="90feb-139">uint64</span><span class="sxs-lookup"><span data-stu-id="90feb-139">uint64</span></span>|<span data-ttu-id="90feb-140">натуральное число без знака x 64</span><span class="sxs-lookup"><span data-stu-id="90feb-140">unsigned 64-bit natural number</span></span>|<span data-ttu-id="90feb-141">UL</span><span class="sxs-lookup"><span data-stu-id="90feb-141">UL</span></span>|`86UL`|
|<span data-ttu-id="90feb-142">одноэлементные, float32</span><span class="sxs-lookup"><span data-stu-id="90feb-142">single, float32</span></span>|<span data-ttu-id="90feb-143">32-разрядное число с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="90feb-143">32-bit floating point number</span></span>|<span data-ttu-id="90feb-144">F или f</span><span class="sxs-lookup"><span data-stu-id="90feb-144">F or f</span></span>|<span data-ttu-id="90feb-145">`4.14F` или `4.14f`</span><span class="sxs-lookup"><span data-stu-id="90feb-145">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="90feb-146">LF</span><span class="sxs-lookup"><span data-stu-id="90feb-146">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="90feb-147">число с плавающей запятой; Double</span><span class="sxs-lookup"><span data-stu-id="90feb-147">float; double</span></span>|<span data-ttu-id="90feb-148">64-разрядное число с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="90feb-148">64-bit floating point number</span></span>|<span data-ttu-id="90feb-149">Нет</span><span class="sxs-lookup"><span data-stu-id="90feb-149">none</span></span>|<span data-ttu-id="90feb-150">`4.14`, `2.3E+32` или `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="90feb-150">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="90feb-151">LF</span><span class="sxs-lookup"><span data-stu-id="90feb-151">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="90feb-152">bigint</span><span class="sxs-lookup"><span data-stu-id="90feb-152">bigint</span></span>|<span data-ttu-id="90feb-153">целое число, не ограничиваясь 64-разрядное представление</span><span class="sxs-lookup"><span data-stu-id="90feb-153">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="90feb-154">I</span><span class="sxs-lookup"><span data-stu-id="90feb-154">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="90feb-155">decimal</span><span class="sxs-lookup"><span data-stu-id="90feb-155">decimal</span></span>|<span data-ttu-id="90feb-156">дробное число, представленное в виде с фиксированной запятой или рациональное число</span><span class="sxs-lookup"><span data-stu-id="90feb-156">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="90feb-157">M или m</span><span class="sxs-lookup"><span data-stu-id="90feb-157">M or m</span></span>|<span data-ttu-id="90feb-158">`0.7833M` или `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="90feb-158">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="90feb-159">Char</span><span class="sxs-lookup"><span data-stu-id="90feb-159">Char</span></span>|<span data-ttu-id="90feb-160">символ Юникода</span><span class="sxs-lookup"><span data-stu-id="90feb-160">Unicode character</span></span>|<span data-ttu-id="90feb-161">Нет</span><span class="sxs-lookup"><span data-stu-id="90feb-161">none</span></span>|`'a'`|
|<span data-ttu-id="90feb-162">String</span><span class="sxs-lookup"><span data-stu-id="90feb-162">String</span></span>|<span data-ttu-id="90feb-163">Строка Юникода</span><span class="sxs-lookup"><span data-stu-id="90feb-163">Unicode string</span></span>|<span data-ttu-id="90feb-164">Нет</span><span class="sxs-lookup"><span data-stu-id="90feb-164">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="90feb-165">или</span><span class="sxs-lookup"><span data-stu-id="90feb-165">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="90feb-166">или</span><span class="sxs-lookup"><span data-stu-id="90feb-166">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="90feb-167">или</span><span class="sxs-lookup"><span data-stu-id="90feb-167">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="90feb-168">См. также [строки](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="90feb-168">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="90feb-169">byte</span><span class="sxs-lookup"><span data-stu-id="90feb-169">byte</span></span>|<span data-ttu-id="90feb-170">Символ ASCII</span><span class="sxs-lookup"><span data-stu-id="90feb-170">ASCII character</span></span>|<span data-ttu-id="90feb-171">С</span><span class="sxs-lookup"><span data-stu-id="90feb-171">B</span></span>|`'a'B`|
|<span data-ttu-id="90feb-172">byte[]</span><span class="sxs-lookup"><span data-stu-id="90feb-172">byte[]</span></span>|<span data-ttu-id="90feb-173">Строка ASCII</span><span class="sxs-lookup"><span data-stu-id="90feb-173">ASCII string</span></span>|<span data-ttu-id="90feb-174">С</span><span class="sxs-lookup"><span data-stu-id="90feb-174">B</span></span>|`"text"B`|
|<span data-ttu-id="90feb-175">String или byte]</span><span class="sxs-lookup"><span data-stu-id="90feb-175">String or byte[]</span></span>|<span data-ttu-id="90feb-176">буквальная строка</span><span class="sxs-lookup"><span data-stu-id="90feb-176">verbatim string</span></span>|<span data-ttu-id="90feb-177">префикс @</span><span class="sxs-lookup"><span data-stu-id="90feb-177">@ prefix</span></span>|<span data-ttu-id="90feb-178">`@"\\server\share"` (Юникод)</span><span class="sxs-lookup"><span data-stu-id="90feb-178">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="90feb-179">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="90feb-179">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="remarks"></a><span data-ttu-id="90feb-180">Примечания</span><span class="sxs-lookup"><span data-stu-id="90feb-180">Remarks</span></span>
<span data-ttu-id="90feb-181">Строки в Юникоде может содержать явные кодировки, которые можно задать с помощью `\u` следуют 16-разрядное шестнадцатеричное или кодировки UTF-32, можно указать с помощью `\U` следуют 32-разрядных шестнадцатеричный код, который представляет строку в Юникоде суррогатная пара.</span><span class="sxs-lookup"><span data-stu-id="90feb-181">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="90feb-182">Начиная с версии 3.1 языка F #, можно использовать `+` входа для объединения строковых литералов.</span><span class="sxs-lookup"><span data-stu-id="90feb-182">As of F# 3.1, you can use the `+` sign to combine string literals.</span></span> <span data-ttu-id="90feb-183">Можно также использовать побитового или (`|||`) оператор для объединения, перечисления флагов.</span><span class="sxs-lookup"><span data-stu-id="90feb-183">You can also use the bitwise or (`|||`) operator to combine enum flags.</span></span> <span data-ttu-id="90feb-184">Например следующий код является допустимым в F # 3.1:</span><span class="sxs-lookup"><span data-stu-id="90feb-184">For example, the following code is legal in F# 3.1:</span></span>

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

<span data-ttu-id="90feb-185">Использование других побитовых операторов не разрешена.</span><span class="sxs-lookup"><span data-stu-id="90feb-185">The use of other bitwise operators isn't allowed.</span></span>


## <a name="named-literals"></a><span data-ttu-id="90feb-186">Именованных литералов</span><span class="sxs-lookup"><span data-stu-id="90feb-186">Named Literals</span></span>
<span data-ttu-id="90feb-187">Значения, которые должны быть константами могут быть помечены с помощью [литерала](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) атрибута.</span><span class="sxs-lookup"><span data-stu-id="90feb-187">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="90feb-188">Этот атрибут приводит к сбою значение будет компилироваться как константа.</span><span class="sxs-lookup"><span data-stu-id="90feb-188">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="90feb-189">В выражениях сопоставления шаблонов идентификаторы которых начинаются с символов нижнего регистра всегда обрабатываются как переменные для привязки, а не как литералы, поэтому следует использовать прописные буквы при определении литералов.</span><span class="sxs-lookup"><span data-stu-id="90feb-189">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="90feb-190">Целые числа в другую систему исчисления</span><span class="sxs-lookup"><span data-stu-id="90feb-190">Integers In Other Bases</span></span>

<span data-ttu-id="90feb-191">32-разрядных целых чисел со знаком может также быть задан шестнадцатеричные, восьмеричные и двоичные `0x`, `0o` или `0b` префикса соответственно.</span><span class="sxs-lookup"><span data-stu-id="90feb-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="90feb-192">Символ подчеркивания в числовые литералы</span><span class="sxs-lookup"><span data-stu-id="90feb-192">Underscores in Numeric Literals</span></span>

<span data-ttu-id="90feb-193">Начиная с версии 4.1 F #, можно разделить цифр с символа подчеркивания (`_`).</span><span class="sxs-lookup"><span data-stu-id="90feb-193">Starting with F# 4.1, you can separate digits with the underscore character (`_`).</span></span>

```fsharp
let DeadBeef = 0xDEAD_BEEF

let DeadBeefAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let ExampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="90feb-194">См. также</span><span class="sxs-lookup"><span data-stu-id="90feb-194">See Also</span></span>

[<span data-ttu-id="90feb-195">Класс Core.LiteralAttribute</span><span class="sxs-lookup"><span data-stu-id="90feb-195">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
