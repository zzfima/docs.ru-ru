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
ms.openlocfilehash: e672402535215ca30d19cc480e39b42b0364f137
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590820"
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="3aec3-102">Тип данных Char (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3aec3-102">Char Data Type (Visual Basic)</span></span>
<span data-ttu-id="3aec3-103">Содержит точки неподписанный код 16-разрядное (2-байтовое), в диапазоне от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="3aec3-103">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="3aec3-104">Каждый *кодовой*, или код символа, представляет один знак Юникода.</span><span class="sxs-lookup"><span data-stu-id="3aec3-104">Each *code point*, or character code, represents a single Unicode character.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3aec3-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="3aec3-105">Remarks</span></span>  
 <span data-ttu-id="3aec3-106">Используйте `Char` при необходимости хранить только один тип символа и не обязательно издержки, связанные с `String`.</span><span class="sxs-lookup"><span data-stu-id="3aec3-106">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="3aec3-107">В некоторых случаях можно использовать `Char()`, массив `Char` элементов, для хранения нескольких символов.</span><span class="sxs-lookup"><span data-stu-id="3aec3-107">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>  
  
 <span data-ttu-id="3aec3-108">Значение по умолчанию `Char` является символа с кодовой точкой в 0.</span><span class="sxs-lookup"><span data-stu-id="3aec3-108">The default value of `Char` is the character with a code point of 0.</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="3aec3-109">Символы Юникода</span><span class="sxs-lookup"><span data-stu-id="3aec3-109">Unicode Characters</span></span>  
 <span data-ttu-id="3aec3-110">Первые 128 кодовых точек (от 0 до 127) Юникода соответствуют буквы и символы на стандартной клавиатуре США.</span><span class="sxs-lookup"><span data-stu-id="3aec3-110">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="3aec3-111">Эти первые 128 кодовых точек являются такие же, как определяет набор символов ASCII.</span><span class="sxs-lookup"><span data-stu-id="3aec3-111">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="3aec3-112">128 кодовых точек (от 128 до 255) представляют специальные символы, такие как буквы латинского алфавита, диакритические знаки, символы валют и дроби.</span><span class="sxs-lookup"><span data-stu-id="3aec3-112">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="3aec3-113">Юникод использует остальные кодовые точки (от 256 до 65535) для широкого набора символов, включая международные текстовые знаки, математические и технические символы и символы с диакритическими знаками.</span><span class="sxs-lookup"><span data-stu-id="3aec3-113">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="3aec3-114">Можно использовать методы, такие как <xref:System.Char.IsDigit%2A> и <xref:System.Char.IsPunctuation%2A> на `Char` переменную для определения ее классификации Юникода.</span><span class="sxs-lookup"><span data-stu-id="3aec3-114">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="3aec3-115">Преобразования типов</span><span class="sxs-lookup"><span data-stu-id="3aec3-115">Type Conversions</span></span>  
 <span data-ttu-id="3aec3-116">Visual Basic не выполняет преобразование между непосредственно `Char` и числовых типов.</span><span class="sxs-lookup"><span data-stu-id="3aec3-116">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="3aec3-117">Можно использовать <xref:Microsoft.VisualBasic.Strings.Asc%2A> или <xref:Microsoft.VisualBasic.Strings.AscW%2A> функцию для преобразования `Char` значение `Integer` , представляющий его кодовая точка.</span><span class="sxs-lookup"><span data-stu-id="3aec3-117">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="3aec3-118">Можно использовать <xref:Microsoft.VisualBasic.Strings.Chr%2A> или <xref:Microsoft.VisualBasic.Strings.ChrW%2A> функцию для преобразования `Integer` значение `Char` с этой точки кода.</span><span class="sxs-lookup"><span data-stu-id="3aec3-118">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>  
  
 <span data-ttu-id="3aec3-119">Если переключатель проверки типа ([оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)) имеет значение on, необходимо добавить знак типа литерала для строкового литерала в целях идентификации как `Char` тип данных.</span><span class="sxs-lookup"><span data-stu-id="3aec3-119">If the type checking switch ([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="3aec3-120">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3aec3-120">The following example illustrates this.</span></span>  
  
```  
Option Strict On  
Dim charVar As Char  
' The following statement attempts to convert a String literal to Char.  
' Because Option Strict is On, it generates a compiler error.  
charVar = "Z"  
' The following statement succeeds because it specifies a Char literal.  
charVar = "Z"C  
```  
  
## <a name="programming-tips"></a><span data-ttu-id="3aec3-121">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="3aec3-121">Programming Tips</span></span>  
  
-   <span data-ttu-id="3aec3-122">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="3aec3-122">**Negative Numbers.**</span></span> <span data-ttu-id="3aec3-123">`Char` является типом без знака и не может представлять отрицательное значение.</span><span class="sxs-lookup"><span data-stu-id="3aec3-123">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="3aec3-124">В любом случае не следует использовать `Char` для хранения числовых значений.</span><span class="sxs-lookup"><span data-stu-id="3aec3-124">In any case, you should not use `Char` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="3aec3-125">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="3aec3-125">**Interop Considerations.**</span></span> <span data-ttu-id="3aec3-126">Если возможность взаимодействовать с компонентами, которые не написаны для платформы .NET Framework, например, автоматизация или COM-объекты, помните, что символьные типы имеют другой размер (8 бит) в других средах.</span><span class="sxs-lookup"><span data-stu-id="3aec3-126">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="3aec3-127">Если передается 8-разрядного аргумента такому компоненту, объявите ее в качестве `Byte` вместо `Char` в новом коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3aec3-127">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="3aec3-128">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="3aec3-128">**Widening.**</span></span> <span data-ttu-id="3aec3-129">`Char` Тип данных может быть расширен до `String`.</span><span class="sxs-lookup"><span data-stu-id="3aec3-129">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="3aec3-130">Это означает, что можно преобразовать `Char` для `String` и не столкнетесь с <xref:System.OverflowException?displayProperty=nameWithType> ошибки.</span><span class="sxs-lookup"><span data-stu-id="3aec3-130">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="3aec3-131">**Символы типов.**</span><span class="sxs-lookup"><span data-stu-id="3aec3-131">**Type Characters.**</span></span> <span data-ttu-id="3aec3-132">Знак типа литерала добавления `C` для строкового литерала приводит к принудительному `Char` тип данных.</span><span class="sxs-lookup"><span data-stu-id="3aec3-132">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="3aec3-133">`Char` не имеет типа символа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="3aec3-133">`Char` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="3aec3-134">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="3aec3-134">**Framework Type.**</span></span> <span data-ttu-id="3aec3-135">В .NET Framework данный тип соответствует структуре <xref:System.Char?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3aec3-135">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aec3-136">См. также</span><span class="sxs-lookup"><span data-stu-id="3aec3-136">See Also</span></span>  
 <xref:System.Char?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [<span data-ttu-id="3aec3-137">Типы данных</span><span class="sxs-lookup"><span data-stu-id="3aec3-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="3aec3-138">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="3aec3-138">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [<span data-ttu-id="3aec3-139">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="3aec3-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="3aec3-140">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="3aec3-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="3aec3-141">Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа</span><span class="sxs-lookup"><span data-stu-id="3aec3-141">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="3aec3-142">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="3aec3-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
