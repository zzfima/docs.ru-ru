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
ms.openlocfilehash: 6600b3b2945120f2f24e14d4cc898cd814366045
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647062"
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="0ef3a-102">Тип данных Char (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ef3a-102">Char Data Type (Visual Basic)</span></span>
<span data-ttu-id="0ef3a-103">Содержит число без знака 16-разрядное (2-байтовые) кодовые в диапазоне от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-103">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="0ef3a-104">Каждый *кодовую точку*, или код символа, представляющего отдельный символ Юникода.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-104">Each *code point*, or character code, represents a single Unicode character.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ef3a-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="0ef3a-105">Remarks</span></span>  
 <span data-ttu-id="0ef3a-106">Используйте `Char` тип данных, если вам нужно хранить только один символ и не обязательно затраты на `String`.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-106">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="0ef3a-107">В некоторых случаях можно использовать `Char()`, массив `Char` элементов, для хранения нескольких символов.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-107">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>  
  
 <span data-ttu-id="0ef3a-108">Значение по умолчанию `Char` — это символ, с помощью кодовых позиций 0.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-108">The default value of `Char` is the character with a code point of 0.</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="0ef3a-109">Символы Юникода</span><span class="sxs-lookup"><span data-stu-id="0ef3a-109">Unicode Characters</span></span>  
 <span data-ttu-id="0ef3a-110">Первые 128 кодовых точек (от 0 до 127) Юникода соответствуют буквы и символы на стандартной клавиатуре США.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-110">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="0ef3a-111">Эти первые 128 кодовых точек являются те же определяет набор символов ASCII.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-111">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="0ef3a-112">128 кодовых точек (128-255) представляют специальные символы, такие как буквы латинского алфавита, диакритические знаки, символы валют и дроби.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-112">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="0ef3a-113">Юникод использует остальные кодовые точки (от 256 до 65535) для широкого набора символов, включая международные текстовые знаки, математические и технические символы и диакритические знаки.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-113">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="0ef3a-114">Можно использовать методы, такие как <xref:System.Char.IsDigit%2A> и <xref:System.Char.IsPunctuation%2A> на `Char` переменной, можно определить ее классификации Юникода.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-114">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="0ef3a-115">Преобразования типов</span><span class="sxs-lookup"><span data-stu-id="0ef3a-115">Type Conversions</span></span>  
 <span data-ttu-id="0ef3a-116">Visual Basic не выполняет преобразование между непосредственно `Char` числовые типы.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-116">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="0ef3a-117">Можно использовать <xref:Microsoft.VisualBasic.Strings.Asc%2A> или <xref:Microsoft.VisualBasic.Strings.AscW%2A> функцию для преобразования `Char` значение `Integer` , представляющий его кодовая точка.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-117">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="0ef3a-118">Можно использовать <xref:Microsoft.VisualBasic.Strings.Chr%2A> или <xref:Microsoft.VisualBasic.Strings.ChrW%2A> функцию для преобразования `Integer` значение `Char` с кодовой точки.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-118">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>  
  
 <span data-ttu-id="0ef3a-119">Если переключатель проверки типа ([оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)) имеет значение on, необходимо добавить знак типа литерала для строкового литерала в целях идентификации как `Char` тип данных.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-119">If the type checking switch ([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="0ef3a-120">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-120">The following example illustrates this.</span></span>  
  
```  
Option Strict On  
Dim charVar As Char  
' The following statement attempts to convert a String literal to Char.  
' Because Option Strict is On, it generates a compiler error.  
charVar = "Z"  
' The following statement succeeds because it specifies a Char literal.  
charVar = "Z"C  
```  
  
## <a name="programming-tips"></a><span data-ttu-id="0ef3a-121">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="0ef3a-121">Programming Tips</span></span>  
  
- <span data-ttu-id="0ef3a-122">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="0ef3a-122">**Negative Numbers.**</span></span> <span data-ttu-id="0ef3a-123">`Char` является типом без знака и не может представлять отрицательное значение.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-123">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="0ef3a-124">В любом случае не следует использовать `Char` для хранения числовых значений.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-124">In any case, you should not use `Char` to hold numeric values.</span></span>  
  
- <span data-ttu-id="0ef3a-125">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="0ef3a-125">**Interop Considerations.**</span></span> <span data-ttu-id="0ef3a-126">Если возможность взаимодействовать с компонентами, которые не написаны для платформы .NET Framework, например, автоматизация или COM-объекты, следует помните, что символьные типы имеют другой размер (8 бит) в других средах.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-126">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="0ef3a-127">Если при передаче 8-разрядного аргумента такому компоненту, объявите его как `Byte` вместо `Char` в новом коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-127">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>  
  
- <span data-ttu-id="0ef3a-128">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="0ef3a-128">**Widening.**</span></span> <span data-ttu-id="0ef3a-129">`Char` Тип данных можно расширить до `String`.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-129">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="0ef3a-130">Это означает, что вы можете преобразовать `Char` для `String` и не столкнетесь с <xref:System.OverflowException?displayProperty=nameWithType> ошибки.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-130">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="0ef3a-131">**Символы типа.**</span><span class="sxs-lookup"><span data-stu-id="0ef3a-131">**Type Characters.**</span></span> <span data-ttu-id="0ef3a-132">Добавляется знак типа литерала `C` в строку односимвольный литерал приводит к принудительному `Char` тип данных.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-132">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="0ef3a-133">`Char` не имеет тип символа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-133">`Char` has no identifier type character.</span></span>  
  
- <span data-ttu-id="0ef3a-134">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="0ef3a-134">**Framework Type.**</span></span> <span data-ttu-id="0ef3a-135">В .NET Framework данный тип соответствует структуре <xref:System.Char?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0ef3a-135">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ef3a-136">См. также</span><span class="sxs-lookup"><span data-stu-id="0ef3a-136">See also</span></span>

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="0ef3a-137">Типы данных</span><span class="sxs-lookup"><span data-stu-id="0ef3a-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="0ef3a-138">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="0ef3a-138">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="0ef3a-139">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="0ef3a-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="0ef3a-140">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="0ef3a-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="0ef3a-141">Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа</span><span class="sxs-lookup"><span data-stu-id="0ef3a-141">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="0ef3a-142">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="0ef3a-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
