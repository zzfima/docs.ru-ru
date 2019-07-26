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
ms.openlocfilehash: ca40e6c8dcba3da29bdb68b29c91c852e477f8f7
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512790"
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="56b4b-102">Тип данных Char (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56b4b-102">Char Data Type (Visual Basic)</span></span>

<span data-ttu-id="56b4b-103">Содержит 16-разрядные (2-байтовые) кодовые точки без знака в диапазоне от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="56b4b-103">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="56b4b-104">Каждая кодовая *точка*, или код символа, представляет один символ Юникода.</span><span class="sxs-lookup"><span data-stu-id="56b4b-104">Each *code point*, or character code, represents a single Unicode character.</span></span>

## <a name="remarks"></a><span data-ttu-id="56b4b-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="56b4b-105">Remarks</span></span>

<span data-ttu-id="56b4b-106">Используйте тип `String`данных, если необходимо хранить только один символ и не требуется дополнительная нагрузка. `Char`</span><span class="sxs-lookup"><span data-stu-id="56b4b-106">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="56b4b-107">В некоторых случаях для хранения нескольких `Char()`символов можно использовать `Char` массив элементов.</span><span class="sxs-lookup"><span data-stu-id="56b4b-107">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>

<span data-ttu-id="56b4b-108">Значение по умолчанию `Char` — символ с кодовой точкой 0.</span><span class="sxs-lookup"><span data-stu-id="56b4b-108">The default value of `Char` is the character with a code point of 0.</span></span>

## <a name="unicode-characters"></a><span data-ttu-id="56b4b-109">Символы Юникода</span><span class="sxs-lookup"><span data-stu-id="56b4b-109">Unicode Characters</span></span>

<span data-ttu-id="56b4b-110">Первая 128 кодовых позиций (0 – 127) Юникода соответствует буквам и символам стандартной клавиатуры США.</span><span class="sxs-lookup"><span data-stu-id="56b4b-110">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="56b4b-111">Первые 128 кодовые точки те же, что и кодировка ASCII.</span><span class="sxs-lookup"><span data-stu-id="56b4b-111">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="56b4b-112">Вторая 128 кодовых позиций (128 – 255) представляет специальные символы, такие как буквы латинского алфавита, диакритические знаки, символы валют и дроби.</span><span class="sxs-lookup"><span data-stu-id="56b4b-112">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="56b4b-113">В Юникоде используются оставшиеся кодовые точки (256-65535) для широкого спектра символов, включая международные текстовые символы, диакритические знаки, математические и технические символы.</span><span class="sxs-lookup"><span data-stu-id="56b4b-113">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>

<span data-ttu-id="56b4b-114">Для определения своей классификации в <xref:System.Char.IsDigit%2A> Юникоде <xref:System.Char.IsPunctuation%2A> можно использовать `Char` методы, такие как и, для переменной.</span><span class="sxs-lookup"><span data-stu-id="56b4b-114">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>

## <a name="type-conversions"></a><span data-ttu-id="56b4b-115">Преобразования типов</span><span class="sxs-lookup"><span data-stu-id="56b4b-115">Type Conversions</span></span>

<span data-ttu-id="56b4b-116">Visual Basic не выполняет прямое преобразование между `Char` и числовыми типами.</span><span class="sxs-lookup"><span data-stu-id="56b4b-116">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="56b4b-117">Можно использовать <xref:Microsoft.VisualBasic.Strings.Asc%2A> функцию или <xref:Microsoft.VisualBasic.Strings.AscW%2A> `Char` для`Integer` преобразования значения в, представляющего ее кодовую точку.</span><span class="sxs-lookup"><span data-stu-id="56b4b-117">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="56b4b-118"><xref:Microsoft.VisualBasic.Strings.Chr%2A> <xref:Microsoft.VisualBasic.Strings.ChrW%2A> Для преобразования`Integer` значения в ,котороеимеетэтукодовуюточку,можноиспользоватьфункциюили.`Char`</span><span class="sxs-lookup"><span data-stu-id="56b4b-118">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>

<span data-ttu-id="56b4b-119">Если включен параметр проверки типов ([оператор Option строго](../../../visual-basic/language-reference/statements/option-strict-statement.md)), необходимо добавить символ типа литерала в односимвольный строковый литерал, чтобы его можно было обозначить `Char` как тип данных.</span><span class="sxs-lookup"><span data-stu-id="56b4b-119">If the type checking switch ([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="56b4b-120">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="56b4b-120">The following example illustrates this.</span></span>

```vb
Option Strict On
Dim charVar As Char
' The following statement attempts to convert a String literal to Char.
' Because Option Strict is On, it generates a compiler error.
charVar = "Z"
' The following statement succeeds because it specifies a Char literal.
charVar = "Z"C
```

## <a name="programming-tips"></a><span data-ttu-id="56b4b-121">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="56b4b-121">Programming Tips</span></span>

- <span data-ttu-id="56b4b-122">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="56b4b-122">**Negative Numbers.**</span></span> <span data-ttu-id="56b4b-123">`Char`является неподписанным типом и не может представлять отрицательное значение.</span><span class="sxs-lookup"><span data-stu-id="56b4b-123">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="56b4b-124">В любом случае не следует использовать `Char` для хранения числовых значений.</span><span class="sxs-lookup"><span data-stu-id="56b4b-124">In any case, you should not use `Char` to hold numeric values.</span></span>

- <span data-ttu-id="56b4b-125">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="56b4b-125">**Interop Considerations.**</span></span> <span data-ttu-id="56b4b-126">Если вы используете компоненты, не написанные для .NET Framework, например автоматизацию или COM-объекты, помните, что в других средах символьные типы имеют разную ширину данных (8 бит).</span><span class="sxs-lookup"><span data-stu-id="56b4b-126">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="56b4b-127">При передаче 8-разрядного аргумента в такой компонент объявите его как `Byte` `Char` вместо в новом коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="56b4b-127">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>

- <span data-ttu-id="56b4b-128">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="56b4b-128">**Widening.**</span></span> <span data-ttu-id="56b4b-129">Тип данных расширяется до `String`. `Char`</span><span class="sxs-lookup"><span data-stu-id="56b4b-129">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="56b4b-130">Это означает, что вы `Char` можете `String` преобразовать в <xref:System.OverflowException?displayProperty=nameWithType> и не получит ошибку.</span><span class="sxs-lookup"><span data-stu-id="56b4b-130">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="56b4b-131">**Символы типа.**</span><span class="sxs-lookup"><span data-stu-id="56b4b-131">**Type Characters.**</span></span> <span data-ttu-id="56b4b-132">Добавление символа `C` типа литерала к строковому литералу с одним символом приводит к тому `Char` , что он применяет его к типу данных.</span><span class="sxs-lookup"><span data-stu-id="56b4b-132">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="56b4b-133">`Char`не имеет символа типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="56b4b-133">`Char` has no identifier type character.</span></span>

- <span data-ttu-id="56b4b-134">**Тип платформы.**</span><span class="sxs-lookup"><span data-stu-id="56b4b-134">**Framework Type.**</span></span> <span data-ttu-id="56b4b-135">В .NET Framework данный тип соответствует структуре <xref:System.Char?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="56b4b-135">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="56b4b-136">См. также</span><span class="sxs-lookup"><span data-stu-id="56b4b-136">See also</span></span>

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="56b4b-137">Типы данных</span><span class="sxs-lookup"><span data-stu-id="56b4b-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="56b4b-138">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="56b4b-138">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="56b4b-139">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="56b4b-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="56b4b-140">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="56b4b-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="56b4b-141">Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа</span><span class="sxs-lookup"><span data-stu-id="56b4b-141">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="56b4b-142">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="56b4b-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
