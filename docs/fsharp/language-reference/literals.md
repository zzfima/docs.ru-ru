---
title: Литералы
description: Дополнительные сведения о типах литералов в F# языка программирования.
ms.date: 06/28/2019
ms.openlocfilehash: 53647d8cbc2a59527a50e122bc1abc6055c1fce5
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2019
ms.locfileid: "67487786"
---
# <a name="literals"></a><span data-ttu-id="67c62-103">Литералы</span><span class="sxs-lookup"><span data-stu-id="67c62-103">Literals</span></span>

> [!NOTE]
> <span data-ttu-id="67c62-104">Ссылки на API в этой статье вы перейдете на сайт MSDN (для сейчас).</span><span class="sxs-lookup"><span data-stu-id="67c62-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="67c62-105">Таблица в этом разделе показано, как указать тип литерала в F#.</span><span class="sxs-lookup"><span data-stu-id="67c62-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="67c62-106">Типы литералов</span><span class="sxs-lookup"><span data-stu-id="67c62-106">Literal Types</span></span>

<span data-ttu-id="67c62-107">В следующей таблице показаны типы литералов в F#.</span><span class="sxs-lookup"><span data-stu-id="67c62-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="67c62-108">Символов, представляющих цифры в шестнадцатеричном формате, не учитывается; символы, которые идентифицируют тип учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="67c62-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="67c62-109">Тип</span><span class="sxs-lookup"><span data-stu-id="67c62-109">Type</span></span>|<span data-ttu-id="67c62-110">Описание</span><span class="sxs-lookup"><span data-stu-id="67c62-110">Description</span></span>|<span data-ttu-id="67c62-111">Суффикс или префикс</span><span class="sxs-lookup"><span data-stu-id="67c62-111">Suffix or prefix</span></span>|<span data-ttu-id="67c62-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="67c62-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="67c62-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="67c62-113">sbyte</span></span>|<span data-ttu-id="67c62-114">8-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="67c62-114">signed 8-bit integer</span></span>|<span data-ttu-id="67c62-115">y</span><span class="sxs-lookup"><span data-stu-id="67c62-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="67c62-116">byte</span><span class="sxs-lookup"><span data-stu-id="67c62-116">byte</span></span>|<span data-ttu-id="67c62-117">без знака 8-разрядное натуральное число</span><span class="sxs-lookup"><span data-stu-id="67c62-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="67c62-118">uy</span><span class="sxs-lookup"><span data-stu-id="67c62-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="67c62-119">int16</span><span class="sxs-lookup"><span data-stu-id="67c62-119">int16</span></span>|<span data-ttu-id="67c62-120">16-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="67c62-120">signed 16-bit integer</span></span>|<span data-ttu-id="67c62-121">s</span><span class="sxs-lookup"><span data-stu-id="67c62-121">s</span></span>|`86s`|
|<span data-ttu-id="67c62-122">uint16</span><span class="sxs-lookup"><span data-stu-id="67c62-122">uint16</span></span>|<span data-ttu-id="67c62-123">без знака 16-разрядное натуральное число</span><span class="sxs-lookup"><span data-stu-id="67c62-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="67c62-124">us</span><span class="sxs-lookup"><span data-stu-id="67c62-124">us</span></span>|`86us`|
|<span data-ttu-id="67c62-125">int</span><span class="sxs-lookup"><span data-stu-id="67c62-125">int</span></span><br /><br /><span data-ttu-id="67c62-126">int32</span><span class="sxs-lookup"><span data-stu-id="67c62-126">int32</span></span>|<span data-ttu-id="67c62-127">32-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="67c62-127">signed 32-bit integer</span></span>|<span data-ttu-id="67c62-128">l или none</span><span class="sxs-lookup"><span data-stu-id="67c62-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="67c62-129">uint</span><span class="sxs-lookup"><span data-stu-id="67c62-129">uint</span></span><br /><br /><span data-ttu-id="67c62-130">uint32</span><span class="sxs-lookup"><span data-stu-id="67c62-130">uint32</span></span>|<span data-ttu-id="67c62-131">неподписанные 32-разрядное натуральное число</span><span class="sxs-lookup"><span data-stu-id="67c62-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="67c62-132">u или ul</span><span class="sxs-lookup"><span data-stu-id="67c62-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="67c62-133">nativeint</span><span class="sxs-lookup"><span data-stu-id="67c62-133">nativeint</span></span>|<span data-ttu-id="67c62-134">собственный указатель на число со знаком естественного</span><span class="sxs-lookup"><span data-stu-id="67c62-134">native pointer to a signed natural number</span></span>|<span data-ttu-id="67c62-135">n</span><span class="sxs-lookup"><span data-stu-id="67c62-135">n</span></span>|`123n`|
|<span data-ttu-id="67c62-136">unativeint</span><span class="sxs-lookup"><span data-stu-id="67c62-136">unativeint</span></span>|<span data-ttu-id="67c62-137">собственный указатель в виде натурального числа без знака</span><span class="sxs-lookup"><span data-stu-id="67c62-137">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="67c62-138">Отменить</span><span class="sxs-lookup"><span data-stu-id="67c62-138">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="67c62-139">int64</span><span class="sxs-lookup"><span data-stu-id="67c62-139">int64</span></span>|<span data-ttu-id="67c62-140">64-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="67c62-140">signed 64-bit integer</span></span>|<span data-ttu-id="67c62-141">L</span><span class="sxs-lookup"><span data-stu-id="67c62-141">L</span></span>|`86L`|
|<span data-ttu-id="67c62-142">uint64</span><span class="sxs-lookup"><span data-stu-id="67c62-142">uint64</span></span>|<span data-ttu-id="67c62-143">без знака 64-разрядное натуральное число</span><span class="sxs-lookup"><span data-stu-id="67c62-143">unsigned 64-bit natural number</span></span>|<span data-ttu-id="67c62-144">UL</span><span class="sxs-lookup"><span data-stu-id="67c62-144">UL</span></span>|`86UL`|
|<span data-ttu-id="67c62-145">единый, float32</span><span class="sxs-lookup"><span data-stu-id="67c62-145">single, float32</span></span>|<span data-ttu-id="67c62-146">32-разрядное число с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="67c62-146">32-bit floating point number</span></span>|<span data-ttu-id="67c62-147">F или f</span><span class="sxs-lookup"><span data-stu-id="67c62-147">F or f</span></span>|<span data-ttu-id="67c62-148">`4.14F` или `4.14f`</span><span class="sxs-lookup"><span data-stu-id="67c62-148">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="67c62-149">LF</span><span class="sxs-lookup"><span data-stu-id="67c62-149">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="67c62-150">в число с плавающей запятой; Double</span><span class="sxs-lookup"><span data-stu-id="67c62-150">float; double</span></span>|<span data-ttu-id="67c62-151">64-разрядное число с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="67c62-151">64-bit floating point number</span></span>|<span data-ttu-id="67c62-152">Нет</span><span class="sxs-lookup"><span data-stu-id="67c62-152">none</span></span>|<span data-ttu-id="67c62-153">`4.14`, `2.3E+32` или `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="67c62-153">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="67c62-154">LF</span><span class="sxs-lookup"><span data-stu-id="67c62-154">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="67c62-155">bigint</span><span class="sxs-lookup"><span data-stu-id="67c62-155">bigint</span></span>|<span data-ttu-id="67c62-156">целое число, не ограничиваясь 64-разрядным представлением</span><span class="sxs-lookup"><span data-stu-id="67c62-156">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="67c62-157">I</span><span class="sxs-lookup"><span data-stu-id="67c62-157">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="67c62-158">decimal</span><span class="sxs-lookup"><span data-stu-id="67c62-158">decimal</span></span>|<span data-ttu-id="67c62-159">дробное число, представленное в виде с фиксированной запятой или рационального числа</span><span class="sxs-lookup"><span data-stu-id="67c62-159">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="67c62-160">M или m</span><span class="sxs-lookup"><span data-stu-id="67c62-160">M or m</span></span>|<span data-ttu-id="67c62-161">`0.7833M` или `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="67c62-161">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="67c62-162">Char</span><span class="sxs-lookup"><span data-stu-id="67c62-162">Char</span></span>|<span data-ttu-id="67c62-163">символ Юникода</span><span class="sxs-lookup"><span data-stu-id="67c62-163">Unicode character</span></span>|<span data-ttu-id="67c62-164">Нет</span><span class="sxs-lookup"><span data-stu-id="67c62-164">none</span></span>|`'a'`|
|<span data-ttu-id="67c62-165">String</span><span class="sxs-lookup"><span data-stu-id="67c62-165">String</span></span>|<span data-ttu-id="67c62-166">Строка Юникода</span><span class="sxs-lookup"><span data-stu-id="67c62-166">Unicode string</span></span>|<span data-ttu-id="67c62-167">Нет</span><span class="sxs-lookup"><span data-stu-id="67c62-167">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="67c62-168">или</span><span class="sxs-lookup"><span data-stu-id="67c62-168">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="67c62-169">или</span><span class="sxs-lookup"><span data-stu-id="67c62-169">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="67c62-170">или</span><span class="sxs-lookup"><span data-stu-id="67c62-170">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="67c62-171">См. также [строки](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="67c62-171">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="67c62-172">byte</span><span class="sxs-lookup"><span data-stu-id="67c62-172">byte</span></span>|<span data-ttu-id="67c62-173">Символ ASCII</span><span class="sxs-lookup"><span data-stu-id="67c62-173">ASCII character</span></span>|<span data-ttu-id="67c62-174">С</span><span class="sxs-lookup"><span data-stu-id="67c62-174">B</span></span>|`'a'B`|
|<span data-ttu-id="67c62-175">byte[]</span><span class="sxs-lookup"><span data-stu-id="67c62-175">byte[]</span></span>|<span data-ttu-id="67c62-176">Строка ASCII</span><span class="sxs-lookup"><span data-stu-id="67c62-176">ASCII string</span></span>|<span data-ttu-id="67c62-177">С</span><span class="sxs-lookup"><span data-stu-id="67c62-177">B</span></span>|`"text"B`|
|<span data-ttu-id="67c62-178">String или byte]</span><span class="sxs-lookup"><span data-stu-id="67c62-178">String or byte[]</span></span>|<span data-ttu-id="67c62-179">буквальная строка</span><span class="sxs-lookup"><span data-stu-id="67c62-179">verbatim string</span></span>|<span data-ttu-id="67c62-180">префикс @</span><span class="sxs-lookup"><span data-stu-id="67c62-180">@ prefix</span></span>|<span data-ttu-id="67c62-181">`@"\\server\share"` (Юникод)</span><span class="sxs-lookup"><span data-stu-id="67c62-181">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="67c62-182">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="67c62-182">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="67c62-183">Именованные литералы</span><span class="sxs-lookup"><span data-stu-id="67c62-183">Named literals</span></span>

<span data-ttu-id="67c62-184">Значения, которые предназначены быть константами могут маркироваться [литерала](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) атрибута.</span><span class="sxs-lookup"><span data-stu-id="67c62-184">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="67c62-185">Этот атрибут имеет вследствие значение компилируется как константа.</span><span class="sxs-lookup"><span data-stu-id="67c62-185">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="67c62-186">В регулярных выражениях идентификаторов, начинающихся с символов нижнего регистра всегда обрабатываются как переменные для привязки, а не как литералы, поэтому следует использовать прописные буквы при определении литералов.</span><span class="sxs-lookup"><span data-stu-id="67c62-186">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

```fsharp
[<Literal>]
let SomeJson = """{"numbers":[1,2,3,4,5]}"""

[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

## <a name="remarks"></a><span data-ttu-id="67c62-187">Примечания</span><span class="sxs-lookup"><span data-stu-id="67c62-187">Remarks</span></span>

<span data-ttu-id="67c62-188">Строки Юникода могут содержать явные кодировки, которые можно указать с помощью `\u` следуют 16-разрядный шестнадцатеричный код (0000 - FFFF), или кодировки UTF-32, можно указать с помощью `\U` следуют 32-разрядных шестнадцатеричный код, который представляет любой кодовую точку Юникода (00000000 - 00010FFFF).</span><span class="sxs-lookup"><span data-stu-id="67c62-188">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 00010FFFF).</span></span>

<span data-ttu-id="67c62-189">Использование других побитовых операторов, отличных от `|||` не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="67c62-189">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="67c62-190">Целые числа в других базовых классов</span><span class="sxs-lookup"><span data-stu-id="67c62-190">Integers in other bases</span></span>

<span data-ttu-id="67c62-191">32-разрядных целых чисел со знаком, также может быть указан при шестнадцатеричные, восьмеричные и двоичные `0x`, `0o` или `0b` префикса соответственно.</span><span class="sxs-lookup"><span data-stu-id="67c62-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="67c62-192">Символы подчеркивания в числовых литералах</span><span class="sxs-lookup"><span data-stu-id="67c62-192">Underscores in numeric literals</span></span>

<span data-ttu-id="67c62-193">Можно разделить цифр с символа подчеркивания (`_`).</span><span class="sxs-lookup"><span data-stu-id="67c62-193">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="67c62-194">См. также</span><span class="sxs-lookup"><span data-stu-id="67c62-194">See also</span></span>

- [<span data-ttu-id="67c62-195">Класс Core.LiteralAttribute</span><span class="sxs-lookup"><span data-stu-id="67c62-195">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
