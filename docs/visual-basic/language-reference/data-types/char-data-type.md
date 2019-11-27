---
title: Тип данных Char
ms.date: 07/20/2015
f1_keywords:
- vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
ms.openlocfilehash: 1ed5b19a307d094fc1d5a6bb0251c57052dc9bc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344047"
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="155a3-102">Тип данных Char (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="155a3-102">Char Data Type (Visual Basic)</span></span>

<span data-ttu-id="155a3-103">Содержит 16-разрядные (2-байтовые) кодовые точки без знака в диапазоне от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="155a3-103">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="155a3-104">Каждая кодовая *точка*, или код символа, представляет один символ Юникода.</span><span class="sxs-lookup"><span data-stu-id="155a3-104">Each *code point*, or character code, represents a single Unicode character.</span></span>

## <a name="remarks"></a><span data-ttu-id="155a3-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="155a3-105">Remarks</span></span>

<span data-ttu-id="155a3-106">Используйте тип данных `Char`, если необходимо удерживать только один символ и не требуется издержки `String`.</span><span class="sxs-lookup"><span data-stu-id="155a3-106">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="155a3-107">В некоторых случаях для хранения нескольких символов можно использовать `Char()`, массив элементов `Char`.</span><span class="sxs-lookup"><span data-stu-id="155a3-107">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>

<span data-ttu-id="155a3-108">Значением по умолчанию для `Char` является символ с кодовой точкой 0.</span><span class="sxs-lookup"><span data-stu-id="155a3-108">The default value of `Char` is the character with a code point of 0.</span></span>

## <a name="unicode-characters"></a><span data-ttu-id="155a3-109">Символы Юникода</span><span class="sxs-lookup"><span data-stu-id="155a3-109">Unicode Characters</span></span>

<span data-ttu-id="155a3-110">Первая 128 кодовых позиций (0 – 127) Юникода соответствует буквам и символам стандартной клавиатуры США.</span><span class="sxs-lookup"><span data-stu-id="155a3-110">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="155a3-111">Первые 128 кодовые точки те же, что и кодировка ASCII.</span><span class="sxs-lookup"><span data-stu-id="155a3-111">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="155a3-112">Вторая 128 кодовых позиций (128 – 255) представляет специальные символы, такие как буквы латинского алфавита, диакритические знаки, символы валют и дроби.</span><span class="sxs-lookup"><span data-stu-id="155a3-112">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="155a3-113">В Юникоде используются оставшиеся кодовые точки (256-65535) для широкого спектра символов, включая международные текстовые символы, диакритические знаки, математические и технические символы.</span><span class="sxs-lookup"><span data-stu-id="155a3-113">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>

<span data-ttu-id="155a3-114">Для определения своей классификации Юникода можно использовать методы, такие как <xref:System.Char.IsDigit%2A> и <xref:System.Char.IsPunctuation%2A> в переменной `Char`.</span><span class="sxs-lookup"><span data-stu-id="155a3-114">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>

## <a name="type-conversions"></a><span data-ttu-id="155a3-115">Преобразования типов</span><span class="sxs-lookup"><span data-stu-id="155a3-115">Type Conversions</span></span>

<span data-ttu-id="155a3-116">Visual Basic не преобразует непосредственно между `Char` и числовыми типами.</span><span class="sxs-lookup"><span data-stu-id="155a3-116">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="155a3-117">Для преобразования `Char` значения в `Integer`, представляющее его кодовую точку, можно использовать функцию <xref:Microsoft.VisualBasic.Strings.Asc%2A> или <xref:Microsoft.VisualBasic.Strings.AscW%2A>.</span><span class="sxs-lookup"><span data-stu-id="155a3-117">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="155a3-118">Для преобразования `Integer` значения в `Char` с этой кодовой точкой можно использовать функцию <xref:Microsoft.VisualBasic.Strings.Chr%2A> или <xref:Microsoft.VisualBasic.Strings.ChrW%2A>.</span><span class="sxs-lookup"><span data-stu-id="155a3-118">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>

<span data-ttu-id="155a3-119">Если параметр проверки типов ( [оператор Option строго](../../../visual-basic/language-reference/statements/option-strict-statement.md)) включен, необходимо добавить символ типа литерала в односимвольный строковый литерал, чтобы он определялся как тип данных `Char`.</span><span class="sxs-lookup"><span data-stu-id="155a3-119">If the type checking switch (the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="155a3-120">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="155a3-120">The following example illustrates this.</span></span> <span data-ttu-id="155a3-121">Первое Присваивание переменной `charVar` приводит к ошибке компилятора [BC30512](../../misc/bc30512.md) , так как `Option Strict` находится в on.</span><span class="sxs-lookup"><span data-stu-id="155a3-121">The first assignment to the `charVar` variable generates compiler error [BC30512](../../misc/bc30512.md) because `Option Strict` is on.</span></span> <span data-ttu-id="155a3-122">Второй компилируется успешно, так как символ типа литерала `c` идентифицирует литерал как `Char` значение.</span><span class="sxs-lookup"><span data-stu-id="155a3-122">The second compiles successfully because the `c` literal type character identifies the literal as a `Char` value.</span></span>

```vb
Option Strict On

Module CharType
    Public Sub Main()
        Dim charVar As Char

        ' This statement generates compiler error BC30512 because Option Strict is On.  
        charVar = "Z"  

        ' The following statement succeeds because it specifies a Char literal.  
        charVar = "Z"c
    End Sub
End Module
```

## <a name="programming-tips"></a><span data-ttu-id="155a3-123">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="155a3-123">Programming Tips</span></span>

- <span data-ttu-id="155a3-124">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="155a3-124">**Negative Numbers.**</span></span> <span data-ttu-id="155a3-125">`Char` является неподписанным типом и не может представлять отрицательное значение.</span><span class="sxs-lookup"><span data-stu-id="155a3-125">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="155a3-126">В любом случае не следует использовать `Char` для хранения числовых значений.</span><span class="sxs-lookup"><span data-stu-id="155a3-126">In any case, you should not use `Char` to hold numeric values.</span></span>

- <span data-ttu-id="155a3-127">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="155a3-127">**Interop Considerations.**</span></span> <span data-ttu-id="155a3-128">Если вы используете компоненты, не написанные для .NET Framework, например автоматизацию или COM-объекты, помните, что в других средах символьные типы имеют разную ширину данных (8 бит).</span><span class="sxs-lookup"><span data-stu-id="155a3-128">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="155a3-129">При передаче 8-разрядного аргумента в такой компонент объявите его как `Byte` вместо `Char` в новом коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="155a3-129">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>

- <span data-ttu-id="155a3-130">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="155a3-130">**Widening.**</span></span> <span data-ttu-id="155a3-131">Тип данных `Char` расширяется до `String`.</span><span class="sxs-lookup"><span data-stu-id="155a3-131">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="155a3-132">Это означает, что вы можете преобразовать `Char` в `String` и не встретит <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="155a3-132">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="155a3-133">**Символы типа.**</span><span class="sxs-lookup"><span data-stu-id="155a3-133">**Type Characters.**</span></span> <span data-ttu-id="155a3-134">Присоединение символьного типа литерала `C` к строковому литералу с одним символом принуждает его к `Char` типу данных.</span><span class="sxs-lookup"><span data-stu-id="155a3-134">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="155a3-135">`Char` не имеет символа типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="155a3-135">`Char` has no identifier type character.</span></span>

- <span data-ttu-id="155a3-136">**Тип платформы.**</span><span class="sxs-lookup"><span data-stu-id="155a3-136">**Framework Type.**</span></span> <span data-ttu-id="155a3-137">В .NET Framework данный тип соответствует структуре <xref:System.Char?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="155a3-137">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="155a3-138">См. также</span><span class="sxs-lookup"><span data-stu-id="155a3-138">See also</span></span>

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="155a3-139">Типы данных</span><span class="sxs-lookup"><span data-stu-id="155a3-139">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="155a3-140">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="155a3-140">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="155a3-141">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="155a3-141">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="155a3-142">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="155a3-142">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="155a3-143">Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа</span><span class="sxs-lookup"><span data-stu-id="155a3-143">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="155a3-144">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="155a3-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
