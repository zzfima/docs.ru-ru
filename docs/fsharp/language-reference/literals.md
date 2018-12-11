---
title: Литералы (F#)
description: Дополнительные сведения о типах литералов в F# языка программирования.
ms.date: 05/16/2016
ms.openlocfilehash: 7a531cd63c5a4dc1123834d481fc998216b0d82d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131343"
---
# <a name="literals"></a><span data-ttu-id="71f4a-103">Литералы</span><span class="sxs-lookup"><span data-stu-id="71f4a-103">Literals</span></span>

> [!NOTE]
> <span data-ttu-id="71f4a-104">Ссылки на API в этой статье вы перейдете на сайт MSDN (для сейчас).</span><span class="sxs-lookup"><span data-stu-id="71f4a-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="71f4a-105">Таблица в этом разделе показано, как указать тип литерала в F#.</span><span class="sxs-lookup"><span data-stu-id="71f4a-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="71f4a-106">Типы литералов</span><span class="sxs-lookup"><span data-stu-id="71f4a-106">Literal Types</span></span>

<span data-ttu-id="71f4a-107">В следующей таблице показаны типы литералов в F#.</span><span class="sxs-lookup"><span data-stu-id="71f4a-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="71f4a-108">Символов, представляющих цифры в шестнадцатеричном формате, не учитывается; символы, которые идентифицируют тип учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="71f4a-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="71f4a-109">Тип</span><span class="sxs-lookup"><span data-stu-id="71f4a-109">Type</span></span>|<span data-ttu-id="71f4a-110">Описание</span><span class="sxs-lookup"><span data-stu-id="71f4a-110">Description</span></span>|<span data-ttu-id="71f4a-111">Суффикс или префикс</span><span class="sxs-lookup"><span data-stu-id="71f4a-111">Suffix or prefix</span></span>|<span data-ttu-id="71f4a-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="71f4a-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="71f4a-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="71f4a-113">sbyte</span></span>|<span data-ttu-id="71f4a-114">8-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="71f4a-114">signed 8-bit integer</span></span>|<span data-ttu-id="71f4a-115">y</span><span class="sxs-lookup"><span data-stu-id="71f4a-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="71f4a-116">byte</span><span class="sxs-lookup"><span data-stu-id="71f4a-116">byte</span></span>|<span data-ttu-id="71f4a-117">без знака 8-разрядное натуральное число</span><span class="sxs-lookup"><span data-stu-id="71f4a-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="71f4a-118">uy</span><span class="sxs-lookup"><span data-stu-id="71f4a-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="71f4a-119">int16</span><span class="sxs-lookup"><span data-stu-id="71f4a-119">int16</span></span>|<span data-ttu-id="71f4a-120">16-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="71f4a-120">signed 16-bit integer</span></span>|<span data-ttu-id="71f4a-121">s</span><span class="sxs-lookup"><span data-stu-id="71f4a-121">s</span></span>|`86s`|
|<span data-ttu-id="71f4a-122">uint16</span><span class="sxs-lookup"><span data-stu-id="71f4a-122">uint16</span></span>|<span data-ttu-id="71f4a-123">без знака 16-разрядное натуральное число</span><span class="sxs-lookup"><span data-stu-id="71f4a-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="71f4a-124">us</span><span class="sxs-lookup"><span data-stu-id="71f4a-124">us</span></span>|`86us`|
|<span data-ttu-id="71f4a-125">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-125">int</span></span><br /><br /><span data-ttu-id="71f4a-126">int32</span><span class="sxs-lookup"><span data-stu-id="71f4a-126">int32</span></span>|<span data-ttu-id="71f4a-127">32-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="71f4a-127">signed 32-bit integer</span></span>|<span data-ttu-id="71f4a-128">l или none</span><span class="sxs-lookup"><span data-stu-id="71f4a-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="71f4a-129">uint</span><span class="sxs-lookup"><span data-stu-id="71f4a-129">uint</span></span><br /><br /><span data-ttu-id="71f4a-130">uint32</span><span class="sxs-lookup"><span data-stu-id="71f4a-130">uint32</span></span>|<span data-ttu-id="71f4a-131">неподписанные 32-разрядное натуральное число</span><span class="sxs-lookup"><span data-stu-id="71f4a-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="71f4a-132">u или ul</span><span class="sxs-lookup"><span data-stu-id="71f4a-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="71f4a-133">unativeint</span><span class="sxs-lookup"><span data-stu-id="71f4a-133">unativeint</span></span>|<span data-ttu-id="71f4a-134">собственный указатель в виде натурального числа без знака</span><span class="sxs-lookup"><span data-stu-id="71f4a-134">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="71f4a-135">Отменить</span><span class="sxs-lookup"><span data-stu-id="71f4a-135">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="71f4a-136">int64</span><span class="sxs-lookup"><span data-stu-id="71f4a-136">int64</span></span>|<span data-ttu-id="71f4a-137">64-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="71f4a-137">signed 64-bit integer</span></span>|<span data-ttu-id="71f4a-138">L</span><span class="sxs-lookup"><span data-stu-id="71f4a-138">L</span></span>|`86L`|
|<span data-ttu-id="71f4a-139">uint64</span><span class="sxs-lookup"><span data-stu-id="71f4a-139">uint64</span></span>|<span data-ttu-id="71f4a-140">без знака 64-разрядное натуральное число</span><span class="sxs-lookup"><span data-stu-id="71f4a-140">unsigned 64-bit natural number</span></span>|<span data-ttu-id="71f4a-141">UL</span><span class="sxs-lookup"><span data-stu-id="71f4a-141">UL</span></span>|`86UL`|
|<span data-ttu-id="71f4a-142">единый, float32</span><span class="sxs-lookup"><span data-stu-id="71f4a-142">single, float32</span></span>|<span data-ttu-id="71f4a-143">32-разрядное число с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="71f4a-143">32-bit floating point number</span></span>|<span data-ttu-id="71f4a-144">F или f</span><span class="sxs-lookup"><span data-stu-id="71f4a-144">F or f</span></span>|<span data-ttu-id="71f4a-145">`4.14F` или `4.14f`</span><span class="sxs-lookup"><span data-stu-id="71f4a-145">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="71f4a-146">LF</span><span class="sxs-lookup"><span data-stu-id="71f4a-146">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="71f4a-147">в число с плавающей запятой; Double</span><span class="sxs-lookup"><span data-stu-id="71f4a-147">float; double</span></span>|<span data-ttu-id="71f4a-148">64-разрядное число с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="71f4a-148">64-bit floating point number</span></span>|<span data-ttu-id="71f4a-149">Нет</span><span class="sxs-lookup"><span data-stu-id="71f4a-149">none</span></span>|<span data-ttu-id="71f4a-150">`4.14`, `2.3E+32` или `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="71f4a-150">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="71f4a-151">LF</span><span class="sxs-lookup"><span data-stu-id="71f4a-151">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="71f4a-152">bigint</span><span class="sxs-lookup"><span data-stu-id="71f4a-152">bigint</span></span>|<span data-ttu-id="71f4a-153">целое число, не ограничиваясь 64-разрядным представлением</span><span class="sxs-lookup"><span data-stu-id="71f4a-153">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="71f4a-154">I</span><span class="sxs-lookup"><span data-stu-id="71f4a-154">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="71f4a-155">decimal</span><span class="sxs-lookup"><span data-stu-id="71f4a-155">decimal</span></span>|<span data-ttu-id="71f4a-156">дробное число, представленное в виде с фиксированной запятой или рационального числа</span><span class="sxs-lookup"><span data-stu-id="71f4a-156">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="71f4a-157">M или m</span><span class="sxs-lookup"><span data-stu-id="71f4a-157">M or m</span></span>|<span data-ttu-id="71f4a-158">`0.7833M` или `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="71f4a-158">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="71f4a-159">Char</span><span class="sxs-lookup"><span data-stu-id="71f4a-159">Char</span></span>|<span data-ttu-id="71f4a-160">символ Юникода</span><span class="sxs-lookup"><span data-stu-id="71f4a-160">Unicode character</span></span>|<span data-ttu-id="71f4a-161">Нет</span><span class="sxs-lookup"><span data-stu-id="71f4a-161">none</span></span>|`'a'`|
|<span data-ttu-id="71f4a-162">String</span><span class="sxs-lookup"><span data-stu-id="71f4a-162">String</span></span>|<span data-ttu-id="71f4a-163">Строка Юникода</span><span class="sxs-lookup"><span data-stu-id="71f4a-163">Unicode string</span></span>|<span data-ttu-id="71f4a-164">Нет</span><span class="sxs-lookup"><span data-stu-id="71f4a-164">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="71f4a-165">или</span><span class="sxs-lookup"><span data-stu-id="71f4a-165">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="71f4a-166">или</span><span class="sxs-lookup"><span data-stu-id="71f4a-166">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="71f4a-167">или</span><span class="sxs-lookup"><span data-stu-id="71f4a-167">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="71f4a-168">См. также [строки](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="71f4a-168">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="71f4a-169">byte</span><span class="sxs-lookup"><span data-stu-id="71f4a-169">byte</span></span>|<span data-ttu-id="71f4a-170">Символ ASCII</span><span class="sxs-lookup"><span data-stu-id="71f4a-170">ASCII character</span></span>|<span data-ttu-id="71f4a-171">С</span><span class="sxs-lookup"><span data-stu-id="71f4a-171">B</span></span>|`'a'B`|
|<span data-ttu-id="71f4a-172">byte[]</span><span class="sxs-lookup"><span data-stu-id="71f4a-172">byte[]</span></span>|<span data-ttu-id="71f4a-173">Строка ASCII</span><span class="sxs-lookup"><span data-stu-id="71f4a-173">ASCII string</span></span>|<span data-ttu-id="71f4a-174">С</span><span class="sxs-lookup"><span data-stu-id="71f4a-174">B</span></span>|`"text"B`|
|<span data-ttu-id="71f4a-175">String или byte]</span><span class="sxs-lookup"><span data-stu-id="71f4a-175">String or byte[]</span></span>|<span data-ttu-id="71f4a-176">буквальная строка</span><span class="sxs-lookup"><span data-stu-id="71f4a-176">verbatim string</span></span>|<span data-ttu-id="71f4a-177">префикс @</span><span class="sxs-lookup"><span data-stu-id="71f4a-177">@ prefix</span></span>|<span data-ttu-id="71f4a-178">`@"\\server\share"` (Юникод)</span><span class="sxs-lookup"><span data-stu-id="71f4a-178">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="71f4a-179">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="71f4a-179">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="remarks"></a><span data-ttu-id="71f4a-180">Примечания</span><span class="sxs-lookup"><span data-stu-id="71f4a-180">Remarks</span></span>

<span data-ttu-id="71f4a-181">Строки Юникода могут содержать явные кодировки, которые можно указать с помощью `\u` следуют 16-разрядный шестнадцатеричный код или кодировки UTF-32, можно указать с помощью `\U` следуют 32-разрядных шестнадцатеричный код, который представляет Юникода пары символов-заместителей.</span><span class="sxs-lookup"><span data-stu-id="71f4a-181">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="71f4a-182">Начиная с версии F# 3.1, можно использовать `+` входа для объединения строковых литералов.</span><span class="sxs-lookup"><span data-stu-id="71f4a-182">As of F# 3.1, you can use the `+` sign to combine string literals.</span></span> <span data-ttu-id="71f4a-183">Можно также использовать побитового или (`|||`) оператор, чтобы объединить флаги перечисления.</span><span class="sxs-lookup"><span data-stu-id="71f4a-183">You can also use the bitwise or (`|||`) operator to combine enum flags.</span></span> <span data-ttu-id="71f4a-184">Например, следующий код является допустимым в F# 3.1:</span><span class="sxs-lookup"><span data-stu-id="71f4a-184">For example, the following code is legal in F# 3.1:</span></span>

```fsharp
[<Literal>]
let literal1 = "a" + "b"

[<Literal>]
let fileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let literal2 = 1 ||| 64

[<Literal>]
let literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

<span data-ttu-id="71f4a-185">Использование других побитовых операторов запрещено.</span><span class="sxs-lookup"><span data-stu-id="71f4a-185">The use of other bitwise operators isn't allowed.</span></span>

## <a name="named-literals"></a><span data-ttu-id="71f4a-186">Именованные литералы</span><span class="sxs-lookup"><span data-stu-id="71f4a-186">Named Literals</span></span>

<span data-ttu-id="71f4a-187">Значения, которые предназначены быть константами могут маркироваться [литерала](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) атрибута.</span><span class="sxs-lookup"><span data-stu-id="71f4a-187">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="71f4a-188">Этот атрибут имеет вследствие значение компилируется как константа.</span><span class="sxs-lookup"><span data-stu-id="71f4a-188">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="71f4a-189">В регулярных выражениях идентификаторов, начинающихся с символов нижнего регистра всегда обрабатываются как переменные для привязки, а не как литералы, поэтому следует использовать прописные буквы при определении литералов.</span><span class="sxs-lookup"><span data-stu-id="71f4a-189">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="71f4a-190">Целые числа в других базовых классов</span><span class="sxs-lookup"><span data-stu-id="71f4a-190">Integers In Other Bases</span></span>

<span data-ttu-id="71f4a-191">32-разрядных целых чисел со знаком, также может быть указан при шестнадцатеричные, восьмеричные и двоичные `0x`, `0o` или `0b` префикса соответственно.</span><span class="sxs-lookup"><span data-stu-id="71f4a-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="71f4a-192">Символы подчеркивания в числовых литералах</span><span class="sxs-lookup"><span data-stu-id="71f4a-192">Underscores in Numeric Literals</span></span>

<span data-ttu-id="71f4a-193">Начиная с F# 4.1, можно отделить цифр с символа подчеркивания (`_`).</span><span class="sxs-lookup"><span data-stu-id="71f4a-193">Starting with F# 4.1, you can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="71f4a-194">См. также</span><span class="sxs-lookup"><span data-stu-id="71f4a-194">See also</span></span>

- [<span data-ttu-id="71f4a-195">Класс Core.LiteralAttribute</span><span class="sxs-lookup"><span data-stu-id="71f4a-195">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
