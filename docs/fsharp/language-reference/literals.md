---
title: Литералы
description: Сведения о типах литералов в языке F# программирования.
ms.date: 06/28/2019
ms.openlocfilehash: 9792a24ac28eb402e35e78574cd6a2bf9526734d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73041035"
---
# <a name="literals"></a><span data-ttu-id="b386d-103">Литералы</span><span class="sxs-lookup"><span data-stu-id="b386d-103">Literals</span></span>

> [!NOTE]
> <span data-ttu-id="b386d-104">Справочные материалы по API в этой статье помогут вам перейти на MSDN (сейчас).</span><span class="sxs-lookup"><span data-stu-id="b386d-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="b386d-105">В этом разделе приводится таблица, в которой показано, как указать тип литерала F#в.</span><span class="sxs-lookup"><span data-stu-id="b386d-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="b386d-106">Типы литералов</span><span class="sxs-lookup"><span data-stu-id="b386d-106">Literal Types</span></span>

<span data-ttu-id="b386d-107">В следующей таблице показаны типы литералов в F#.</span><span class="sxs-lookup"><span data-stu-id="b386d-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="b386d-108">Символы, представляющие цифры в шестнадцатеричном формате, не учитывают регистр; символы, которые определяют тип, учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="b386d-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="b386d-109">Type</span><span class="sxs-lookup"><span data-stu-id="b386d-109">Type</span></span>|<span data-ttu-id="b386d-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b386d-110">Description</span></span>|<span data-ttu-id="b386d-111">Суффикс или префикс</span><span class="sxs-lookup"><span data-stu-id="b386d-111">Suffix or prefix</span></span>|<span data-ttu-id="b386d-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="b386d-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="b386d-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="b386d-113">sbyte</span></span>|<span data-ttu-id="b386d-114">8-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="b386d-114">signed 8-bit integer</span></span>|<span data-ttu-id="b386d-115">Y</span><span class="sxs-lookup"><span data-stu-id="b386d-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="b386d-116">byte</span><span class="sxs-lookup"><span data-stu-id="b386d-116">byte</span></span>|<span data-ttu-id="b386d-117">8-разрядное натуральное число без знака</span><span class="sxs-lookup"><span data-stu-id="b386d-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="b386d-118">Uy</span><span class="sxs-lookup"><span data-stu-id="b386d-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="b386d-119">int16</span><span class="sxs-lookup"><span data-stu-id="b386d-119">int16</span></span>|<span data-ttu-id="b386d-120">16-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="b386d-120">signed 16-bit integer</span></span>|<span data-ttu-id="b386d-121">s</span><span class="sxs-lookup"><span data-stu-id="b386d-121">s</span></span>|`86s`|
|<span data-ttu-id="b386d-122">uint16</span><span class="sxs-lookup"><span data-stu-id="b386d-122">uint16</span></span>|<span data-ttu-id="b386d-123">16-разрядное натуральное число без знака</span><span class="sxs-lookup"><span data-stu-id="b386d-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="b386d-124">us</span><span class="sxs-lookup"><span data-stu-id="b386d-124">us</span></span>|`86us`|
|<span data-ttu-id="b386d-125">int</span><span class="sxs-lookup"><span data-stu-id="b386d-125">int</span></span><br /><br /><span data-ttu-id="b386d-126">int32</span><span class="sxs-lookup"><span data-stu-id="b386d-126">int32</span></span>|<span data-ttu-id="b386d-127">32-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="b386d-127">signed 32-bit integer</span></span>|<span data-ttu-id="b386d-128">l или нет</span><span class="sxs-lookup"><span data-stu-id="b386d-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="b386d-129">uint</span><span class="sxs-lookup"><span data-stu-id="b386d-129">uint</span></span><br /><br /><span data-ttu-id="b386d-130">uint32</span><span class="sxs-lookup"><span data-stu-id="b386d-130">uint32</span></span>|<span data-ttu-id="b386d-131">32-разрядное натуральное число без знака</span><span class="sxs-lookup"><span data-stu-id="b386d-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="b386d-132">u или UL</span><span class="sxs-lookup"><span data-stu-id="b386d-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="b386d-133">нативеинт</span><span class="sxs-lookup"><span data-stu-id="b386d-133">nativeint</span></span>|<span data-ttu-id="b386d-134">собственный указатель на натуральное число со знаком</span><span class="sxs-lookup"><span data-stu-id="b386d-134">native pointer to a signed natural number</span></span>|<span data-ttu-id="b386d-135">n</span><span class="sxs-lookup"><span data-stu-id="b386d-135">n</span></span>|`123n`|
|<span data-ttu-id="b386d-136">unativeint</span><span class="sxs-lookup"><span data-stu-id="b386d-136">unativeint</span></span>|<span data-ttu-id="b386d-137">собственный указатель как беззнаковое натуральное число</span><span class="sxs-lookup"><span data-stu-id="b386d-137">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="b386d-138">понижен</span><span class="sxs-lookup"><span data-stu-id="b386d-138">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="b386d-139">int64</span><span class="sxs-lookup"><span data-stu-id="b386d-139">int64</span></span>|<span data-ttu-id="b386d-140">64-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="b386d-140">signed 64-bit integer</span></span>|<span data-ttu-id="b386d-141">L</span><span class="sxs-lookup"><span data-stu-id="b386d-141">L</span></span>|`86L`|
|<span data-ttu-id="b386d-142">uint64</span><span class="sxs-lookup"><span data-stu-id="b386d-142">uint64</span></span>|<span data-ttu-id="b386d-143">64-разрядное натуральное число без знака</span><span class="sxs-lookup"><span data-stu-id="b386d-143">unsigned 64-bit natural number</span></span>|<span data-ttu-id="b386d-144">UL</span><span class="sxs-lookup"><span data-stu-id="b386d-144">UL</span></span>|`86UL`|
|<span data-ttu-id="b386d-145">Single, float32</span><span class="sxs-lookup"><span data-stu-id="b386d-145">single, float32</span></span>|<span data-ttu-id="b386d-146">32-разрядное число с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="b386d-146">32-bit floating point number</span></span>|<span data-ttu-id="b386d-147">F или f</span><span class="sxs-lookup"><span data-stu-id="b386d-147">F or f</span></span>|<span data-ttu-id="b386d-148">`4.14F` или `4.14f`</span><span class="sxs-lookup"><span data-stu-id="b386d-148">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="b386d-149">возврата</span><span class="sxs-lookup"><span data-stu-id="b386d-149">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="b386d-150">сделать Дважды</span><span class="sxs-lookup"><span data-stu-id="b386d-150">float; double</span></span>|<span data-ttu-id="b386d-151">64-разрядное число с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="b386d-151">64-bit floating point number</span></span>|<span data-ttu-id="b386d-152">Нет</span><span class="sxs-lookup"><span data-stu-id="b386d-152">none</span></span>|<span data-ttu-id="b386d-153">`4.14`, `2.3E+32` или `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="b386d-153">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="b386d-154">ВОЗВРАТА</span><span class="sxs-lookup"><span data-stu-id="b386d-154">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="b386d-155">bigint</span><span class="sxs-lookup"><span data-stu-id="b386d-155">bigint</span></span>|<span data-ttu-id="b386d-156">целое число не ограничено 64-разрядным представлением</span><span class="sxs-lookup"><span data-stu-id="b386d-156">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="b386d-157">I</span><span class="sxs-lookup"><span data-stu-id="b386d-157">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="b386d-158">decimal</span><span class="sxs-lookup"><span data-stu-id="b386d-158">decimal</span></span>|<span data-ttu-id="b386d-159">дробное число, представленное в виде фиксированной точки или рационального числа</span><span class="sxs-lookup"><span data-stu-id="b386d-159">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="b386d-160">M или m</span><span class="sxs-lookup"><span data-stu-id="b386d-160">M or m</span></span>|<span data-ttu-id="b386d-161">`0.7833M` или `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="b386d-161">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="b386d-162">Char</span><span class="sxs-lookup"><span data-stu-id="b386d-162">Char</span></span>|<span data-ttu-id="b386d-163">символ Юникода</span><span class="sxs-lookup"><span data-stu-id="b386d-163">Unicode character</span></span>|<span data-ttu-id="b386d-164">Нет</span><span class="sxs-lookup"><span data-stu-id="b386d-164">none</span></span>|<span data-ttu-id="b386d-165">`'a'` или `'\u0061'`</span><span class="sxs-lookup"><span data-stu-id="b386d-165">`'a'` or `'\u0061'`</span></span>|
|<span data-ttu-id="b386d-166">Строковое</span><span class="sxs-lookup"><span data-stu-id="b386d-166">String</span></span>|<span data-ttu-id="b386d-167">Строка Юникода</span><span class="sxs-lookup"><span data-stu-id="b386d-167">Unicode string</span></span>|<span data-ttu-id="b386d-168">Нет</span><span class="sxs-lookup"><span data-stu-id="b386d-168">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="b386d-169">или</span><span class="sxs-lookup"><span data-stu-id="b386d-169">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="b386d-170">или</span><span class="sxs-lookup"><span data-stu-id="b386d-170">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="b386d-171">или</span><span class="sxs-lookup"><span data-stu-id="b386d-171">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="b386d-172">См. также [строки](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="b386d-172">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="b386d-173">byte</span><span class="sxs-lookup"><span data-stu-id="b386d-173">byte</span></span>|<span data-ttu-id="b386d-174">Символ ASCII</span><span class="sxs-lookup"><span data-stu-id="b386d-174">ASCII character</span></span>|<span data-ttu-id="b386d-175">С</span><span class="sxs-lookup"><span data-stu-id="b386d-175">B</span></span>|`'a'B`|
|<span data-ttu-id="b386d-176">byte[]</span><span class="sxs-lookup"><span data-stu-id="b386d-176">byte[]</span></span>|<span data-ttu-id="b386d-177">Строка ASCII</span><span class="sxs-lookup"><span data-stu-id="b386d-177">ASCII string</span></span>|<span data-ttu-id="b386d-178">С</span><span class="sxs-lookup"><span data-stu-id="b386d-178">B</span></span>|`"text"B`|
|<span data-ttu-id="b386d-179">String или Byte []</span><span class="sxs-lookup"><span data-stu-id="b386d-179">String or byte[]</span></span>|<span data-ttu-id="b386d-180">буквальная строка</span><span class="sxs-lookup"><span data-stu-id="b386d-180">verbatim string</span></span>|<span data-ttu-id="b386d-181">префикс @</span><span class="sxs-lookup"><span data-stu-id="b386d-181">@ prefix</span></span>|<span data-ttu-id="b386d-182">`@"\\server\share"` (Юникод)</span><span class="sxs-lookup"><span data-stu-id="b386d-182">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="b386d-183">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="b386d-183">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="b386d-184">Именованные литералы</span><span class="sxs-lookup"><span data-stu-id="b386d-184">Named literals</span></span>

<span data-ttu-id="b386d-185">Значения, которые должны быть константами, могут быть помечены атрибутом [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) .</span><span class="sxs-lookup"><span data-stu-id="b386d-185">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="b386d-186">Этот атрибут приводит к тому, что значение компилируется как константа.</span><span class="sxs-lookup"><span data-stu-id="b386d-186">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="b386d-187">В выражениях сопоставления шаблонов идентификаторы, начинающиеся с символов нижнего регистра, всегда обрабатываются как переменные для привязки, а не как литералы, поэтому при определении литералов обычно следует использовать начальные прописные буквы.</span><span class="sxs-lookup"><span data-stu-id="b386d-187">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="b386d-188">Заметки</span><span class="sxs-lookup"><span data-stu-id="b386d-188">Remarks</span></span>

<span data-ttu-id="b386d-189">Строки в Юникоде могут содержать явные кодировки, которые можно указать с помощью `\u`, за которым следует 16-разрядный шестнадцатеричный код (0000-FFFF) или кодировка UTF-32, которую можно указать с помощью `\U`, за которым следует 32-разрядный шестнадцатеричный код, представляющий любые символы Юникода. кодовая точка (00000000-0010FFFF).</span><span class="sxs-lookup"><span data-stu-id="b386d-189">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="b386d-190">Использование других побитовых операторов, отличных от `|||`, запрещено.</span><span class="sxs-lookup"><span data-stu-id="b386d-190">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="b386d-191">Целые числа в других базовых базах</span><span class="sxs-lookup"><span data-stu-id="b386d-191">Integers in other bases</span></span>

<span data-ttu-id="b386d-192">32-разрядные целые числа со знаком можно также указывать в шестнадцатеричном, восьмеричном или двоичном формате с помощью префикса `0x`, `0o` или `0b` соответственно.</span><span class="sxs-lookup"><span data-stu-id="b386d-192">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="b386d-193">Знаки подчеркивания в числовых литералах</span><span class="sxs-lookup"><span data-stu-id="b386d-193">Underscores in numeric literals</span></span>

<span data-ttu-id="b386d-194">Цифры можно разделять символом подчеркивания (`_`).</span><span class="sxs-lookup"><span data-stu-id="b386d-194">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="b386d-195">См. также</span><span class="sxs-lookup"><span data-stu-id="b386d-195">See also</span></span>

- [<span data-ttu-id="b386d-196">Класс Core. Литералаттрибуте</span><span class="sxs-lookup"><span data-stu-id="b386d-196">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
