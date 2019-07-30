---
title: Тип данных Char (Visual Basic)
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
ms.openlocfilehash: 8313c2282a3b4b7b035f9f3b685a786c4471f53a
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630142"
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="23fdf-102">Тип данных Char (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23fdf-102">Char Data Type (Visual Basic)</span></span>

<span data-ttu-id="23fdf-103">Содержит 16-разрядные (2-байтовые) кодовые точки без знака в диапазоне от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="23fdf-103">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="23fdf-104">Каждая кодовая *точка*, или код символа, представляет один символ Юникода.</span><span class="sxs-lookup"><span data-stu-id="23fdf-104">Each *code point*, or character code, represents a single Unicode character.</span></span>

## <a name="remarks"></a><span data-ttu-id="23fdf-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="23fdf-105">Remarks</span></span>

<span data-ttu-id="23fdf-106">Используйте тип `String`данных, если необходимо хранить только один символ и не требуется дополнительная нагрузка. `Char`</span><span class="sxs-lookup"><span data-stu-id="23fdf-106">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="23fdf-107">В некоторых случаях для хранения нескольких `Char()`символов можно использовать `Char` массив элементов.</span><span class="sxs-lookup"><span data-stu-id="23fdf-107">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>

<span data-ttu-id="23fdf-108">Значение по умолчанию `Char` — символ с кодовой точкой 0.</span><span class="sxs-lookup"><span data-stu-id="23fdf-108">The default value of `Char` is the character with a code point of 0.</span></span>

## <a name="unicode-characters"></a><span data-ttu-id="23fdf-109">Символы Юникода</span><span class="sxs-lookup"><span data-stu-id="23fdf-109">Unicode Characters</span></span>

<span data-ttu-id="23fdf-110">Первая 128 кодовых позиций (0 – 127) Юникода соответствует буквам и символам стандартной клавиатуры США.</span><span class="sxs-lookup"><span data-stu-id="23fdf-110">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="23fdf-111">Первые 128 кодовые точки те же, что и кодировка ASCII.</span><span class="sxs-lookup"><span data-stu-id="23fdf-111">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="23fdf-112">Вторая 128 кодовых позиций (128 – 255) представляет специальные символы, такие как буквы латинского алфавита, диакритические знаки, символы валют и дроби.</span><span class="sxs-lookup"><span data-stu-id="23fdf-112">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="23fdf-113">В Юникоде используются оставшиеся кодовые точки (256-65535) для широкого спектра символов, включая международные текстовые символы, диакритические знаки, математические и технические символы.</span><span class="sxs-lookup"><span data-stu-id="23fdf-113">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>

<span data-ttu-id="23fdf-114">Для определения своей классификации в <xref:System.Char.IsDigit%2A> Юникоде <xref:System.Char.IsPunctuation%2A> можно использовать `Char` методы, такие как и, для переменной.</span><span class="sxs-lookup"><span data-stu-id="23fdf-114">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>

## <a name="type-conversions"></a><span data-ttu-id="23fdf-115">Преобразования типов</span><span class="sxs-lookup"><span data-stu-id="23fdf-115">Type Conversions</span></span>

<span data-ttu-id="23fdf-116">Visual Basic не выполняет прямое преобразование между `Char` и числовыми типами.</span><span class="sxs-lookup"><span data-stu-id="23fdf-116">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="23fdf-117">Можно использовать <xref:Microsoft.VisualBasic.Strings.Asc%2A> функцию или <xref:Microsoft.VisualBasic.Strings.AscW%2A> `Char` для`Integer` преобразования значения в, представляющего ее кодовую точку.</span><span class="sxs-lookup"><span data-stu-id="23fdf-117">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="23fdf-118"><xref:Microsoft.VisualBasic.Strings.Chr%2A> <xref:Microsoft.VisualBasic.Strings.ChrW%2A> Для преобразования`Integer` значения в ,котороеимеетэтукодовуюточку,можноиспользоватьфункциюили.`Char`</span><span class="sxs-lookup"><span data-stu-id="23fdf-118">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>

<span data-ttu-id="23fdf-119">Если параметр проверки типов ( [оператор Option строго](../../../visual-basic/language-reference/statements/option-strict-statement.md)) включен, необходимо добавить символ типа литерала в односимвольный строковый литерал, чтобы его можно было обозначить как `Char` тип данных.</span><span class="sxs-lookup"><span data-stu-id="23fdf-119">If the type checking switch (the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="23fdf-120">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="23fdf-120">The following example illustrates this.</span></span> <span data-ttu-id="23fdf-121">Первое присваивание `charVar` переменной приводит к ошибке компилятора [BC30512](../../misc/bc30512.md) , `Option Strict` так как имеет значение ON.</span><span class="sxs-lookup"><span data-stu-id="23fdf-121">The first assignment to the `charVar` variable generates compiler error [BC30512](../../misc/bc30512.md) because `Option Strict` is on.</span></span> <span data-ttu-id="23fdf-122">Вторая компилируется успешно, так как `c` символ типа литерала определяет литерал `Char` как значение.</span><span class="sxs-lookup"><span data-stu-id="23fdf-122">The second compiles successfully because the `c` literal type character identifies the literal as a `Char` value.</span></span>

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

## <a name="programming-tips"></a><span data-ttu-id="23fdf-123">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="23fdf-123">Programming Tips</span></span>

- <span data-ttu-id="23fdf-124">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="23fdf-124">**Negative Numbers.**</span></span> <span data-ttu-id="23fdf-125">`Char`является неподписанным типом и не может представлять отрицательное значение.</span><span class="sxs-lookup"><span data-stu-id="23fdf-125">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="23fdf-126">В любом случае не следует использовать `Char` для хранения числовых значений.</span><span class="sxs-lookup"><span data-stu-id="23fdf-126">In any case, you should not use `Char` to hold numeric values.</span></span>

- <span data-ttu-id="23fdf-127">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="23fdf-127">**Interop Considerations.**</span></span> <span data-ttu-id="23fdf-128">Если вы используете компоненты, не написанные для .NET Framework, например автоматизацию или COM-объекты, помните, что в других средах символьные типы имеют разную ширину данных (8 бит).</span><span class="sxs-lookup"><span data-stu-id="23fdf-128">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="23fdf-129">При передаче 8-разрядного аргумента в такой компонент объявите его как `Byte` `Char` вместо в новом коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="23fdf-129">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>

- <span data-ttu-id="23fdf-130">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="23fdf-130">**Widening.**</span></span> <span data-ttu-id="23fdf-131">Тип данных расширяется до `String`. `Char`</span><span class="sxs-lookup"><span data-stu-id="23fdf-131">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="23fdf-132">Это означает, что можно `Char` выполнить `String` преобразование в <xref:System.OverflowException?displayProperty=nameWithType>и не будет возникать.</span><span class="sxs-lookup"><span data-stu-id="23fdf-132">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="23fdf-133">**Символы типа.**</span><span class="sxs-lookup"><span data-stu-id="23fdf-133">**Type Characters.**</span></span> <span data-ttu-id="23fdf-134">Добавление символа `C` типа литерала к строковому литералу с одним символом приводит к тому `Char` , что он применяет его к типу данных.</span><span class="sxs-lookup"><span data-stu-id="23fdf-134">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="23fdf-135">`Char`не имеет символа типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="23fdf-135">`Char` has no identifier type character.</span></span>

- <span data-ttu-id="23fdf-136">**Тип платформы.**</span><span class="sxs-lookup"><span data-stu-id="23fdf-136">**Framework Type.**</span></span> <span data-ttu-id="23fdf-137">В .NET Framework данный тип соответствует структуре <xref:System.Char?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="23fdf-137">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="23fdf-138">См. также</span><span class="sxs-lookup"><span data-stu-id="23fdf-138">See also</span></span>

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="23fdf-139">Типы данных</span><span class="sxs-lookup"><span data-stu-id="23fdf-139">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="23fdf-140">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="23fdf-140">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="23fdf-141">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="23fdf-141">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="23fdf-142">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="23fdf-142">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="23fdf-143">Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа</span><span class="sxs-lookup"><span data-stu-id="23fdf-143">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="23fdf-144">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="23fdf-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
