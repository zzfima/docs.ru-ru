---
title: Символы типов
ms.date: 01/31/2018
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals [Visual Basic]
- F literal type character [Visual Basic]
- '& identifier type character'
- type characters [Visual Basic]
- octal literals [Visual Basic]
- literals [Visual Basic], hexadecimal
- '&O prefix for octal values'
- literals [Visual Basic], default types
- defaults, literal types
- C literal type character [Visual Basic]
- type characters [Visual Basic], literal
- $ identifier type character
- L literal type character [Visual Basic]
- UI literal type characters [Visual Basic]
- default literal types [Visual Basic]
- D literal type character [Visual Basic]
- literals [Visual Basic], octal
- S literal type character [Visual Basic]
- '! identifier type character'
- US literal type characters [Visual Basic]
- '% identifier type character'
- data types [Visual Basic], type characters
- characters [Visual Basic], identifier type
- type characters [Visual Basic], identifier
- '# identifier type character'
- identifier type characters [Visual Basic]
- literal type characters [Visual Basic]
- I literal type character [Visual Basic]
- R literal type character [Visual Basic]
- '@ identifier type character'
- UL literal type characters [Visual Basic]
- literal types [Visual Basic], default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
ms.openlocfilehash: 628461c8136946dd902c0a52048eee7c516c52cd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352929"
---
# <a name="type-characters-visual-basic"></a><span data-ttu-id="29dd6-102">Символы типов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="29dd6-102">Type characters (Visual Basic)</span></span>

<span data-ttu-id="29dd6-103">Помимо указания типа данных в операторе объявления, можно принудительно указать тип данных некоторых программных элементов с помощью *символа типа*.</span><span class="sxs-lookup"><span data-stu-id="29dd6-103">In addition to specifying a data type in a declaration statement, you can force the data type of some programming elements with a *type character*.</span></span> <span data-ttu-id="29dd6-104">Символ типа должен следовать непосредственно за элементом, не имеющим промежуточных символов любого вида.</span><span class="sxs-lookup"><span data-stu-id="29dd6-104">The type character must immediately follow the element, with no intervening characters of any kind.</span></span>

<span data-ttu-id="29dd6-105">Символ типа не является частью имени элемента.</span><span class="sxs-lookup"><span data-stu-id="29dd6-105">The type character is not part of the name of the element.</span></span> <span data-ttu-id="29dd6-106">На элемент, определенный с помощью символа типа, можно ссылаться без символа типа.</span><span class="sxs-lookup"><span data-stu-id="29dd6-106">An element defined with a type character can be referenced without the type character.</span></span>

## <a name="identifier-type-characters"></a><span data-ttu-id="29dd6-107">Символы типа идентификатора</span><span class="sxs-lookup"><span data-stu-id="29dd6-107">Identifier type characters</span></span>

<span data-ttu-id="29dd6-108">Visual Basic предоставляет набор *символов типа идентификатора* , которые можно использовать в объявлении для указания типа данных переменной или константы.</span><span class="sxs-lookup"><span data-stu-id="29dd6-108">Visual Basic supplies a set of *identifier type characters* that you can use in a declaration to specify the data type of a variable or constant.</span></span> <span data-ttu-id="29dd6-109">В следующей таблице приведены доступные символы типа идентификатора с примерами использования.</span><span class="sxs-lookup"><span data-stu-id="29dd6-109">The following table shows the available identifier type characters with examples of usage.</span></span>
  
|<span data-ttu-id="29dd6-110">Символ типа идентификатора</span><span class="sxs-lookup"><span data-stu-id="29dd6-110">Identifier type character</span></span>|<span data-ttu-id="29dd6-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="29dd6-111">Data type</span></span>|<span data-ttu-id="29dd6-112">Пример</span><span class="sxs-lookup"><span data-stu-id="29dd6-112">Example</span></span>|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 <span data-ttu-id="29dd6-113">Не существует символов типа идентификатора для `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`или `ULong`типов данных, а также для любых составных типов данных, таких как массивы или структуры.`UShort`</span><span class="sxs-lookup"><span data-stu-id="29dd6-113">No identifier type characters exist for the `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="29dd6-114">В некоторых случаях можно добавить `$`ный символ в функцию Visual Basic, например `Left$` вместо `Left`, чтобы получить возвращаемое значение типа `String`.</span><span class="sxs-lookup"><span data-stu-id="29dd6-114">In some cases, you can append the `$` character to a Visual Basic function, for example `Left$` instead of `Left`, to obtain a returned value of type `String`.</span></span>

<span data-ttu-id="29dd6-115">Во всех случаях символ типа идентификатора должен следовать непосредственно за именем идентификатора.</span><span class="sxs-lookup"><span data-stu-id="29dd6-115">In all cases, the identifier type character must immediately follow the identifier name.</span></span>

## <a name="literal-type-characters"></a><span data-ttu-id="29dd6-116">Символы типа литерала</span><span class="sxs-lookup"><span data-stu-id="29dd6-116">Literal type characters</span></span>

<span data-ttu-id="29dd6-117">*Литерал* — это текстовое представление конкретного значения типа данных.</span><span class="sxs-lookup"><span data-stu-id="29dd6-117">A *literal* is a textual representation of a particular value of a data type.</span></span>  

### <a name="default-literal-types"></a><span data-ttu-id="29dd6-118">Типы литералов по умолчанию</span><span class="sxs-lookup"><span data-stu-id="29dd6-118">Default literal types</span></span>

<span data-ttu-id="29dd6-119">Форма литерала в том виде, в котором она отображается в коде, обычно определяет его тип данных.</span><span class="sxs-lookup"><span data-stu-id="29dd6-119">The form of a literal as it appears in your code ordinarily determines its data type.</span></span> <span data-ttu-id="29dd6-120">В следующей таблице показаны эти типы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="29dd6-120">The following table shows these default types.</span></span>  
  
|<span data-ttu-id="29dd6-121">Текстовая форма литерала</span><span class="sxs-lookup"><span data-stu-id="29dd6-121">Textual form of literal</span></span>|<span data-ttu-id="29dd6-122">Тип данных по умолчанию</span><span class="sxs-lookup"><span data-stu-id="29dd6-122">Default data type</span></span>|<span data-ttu-id="29dd6-123">Пример</span><span class="sxs-lookup"><span data-stu-id="29dd6-123">Example</span></span>|  
|-----------------------------|-----------------------|-------------|  
|<span data-ttu-id="29dd6-124">Numeric, без дробной части</span><span class="sxs-lookup"><span data-stu-id="29dd6-124">Numeric, no fractional part</span></span>|`Integer`|`2147483647`|  
|<span data-ttu-id="29dd6-125">Numeric, без дробной части, слишком велика для `Integer`</span><span class="sxs-lookup"><span data-stu-id="29dd6-125">Numeric, no fractional part, too large for `Integer`</span></span>|`Long`|`2147483648`|  
|<span data-ttu-id="29dd6-126">Числовая, дробная часть</span><span class="sxs-lookup"><span data-stu-id="29dd6-126">Numeric, fractional part</span></span>|`Double`|`1.2`|  
|<span data-ttu-id="29dd6-127">Заключено в двойные кавычки</span><span class="sxs-lookup"><span data-stu-id="29dd6-127">Enclosed in double quotation marks</span></span>|`String`|`"A"`|  
|<span data-ttu-id="29dd6-128">Заключено в знаки решетки</span><span class="sxs-lookup"><span data-stu-id="29dd6-128">Enclosed within number signs</span></span>|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a><span data-ttu-id="29dd6-129">Принудительные типы литералов</span><span class="sxs-lookup"><span data-stu-id="29dd6-129">Forced literal types</span></span>

<span data-ttu-id="29dd6-130">Visual Basic предоставляет набор *символов типа литерала*, который можно использовать для принудительного применения литерала к типу данных, отличному от того, который указывает его форма.</span><span class="sxs-lookup"><span data-stu-id="29dd6-130">Visual Basic supplies a set of *literal type characters*, which you can use to force a literal to assume a data type other than the one its form indicates.</span></span> <span data-ttu-id="29dd6-131">Это можно сделать, добавив символ в конец литерала.</span><span class="sxs-lookup"><span data-stu-id="29dd6-131">You do this by appending the character to the end of the literal.</span></span> <span data-ttu-id="29dd6-132">В следующей таблице показаны доступные символы типа литерала с примерами использования.</span><span class="sxs-lookup"><span data-stu-id="29dd6-132">The following table shows the available literal type characters with examples of usage.</span></span>
  
|<span data-ttu-id="29dd6-133">Символ типа литерала</span><span class="sxs-lookup"><span data-stu-id="29dd6-133">Literal type character</span></span>|<span data-ttu-id="29dd6-134">Тип данных</span><span class="sxs-lookup"><span data-stu-id="29dd6-134">Data type</span></span>|<span data-ttu-id="29dd6-135">Пример</span><span class="sxs-lookup"><span data-stu-id="29dd6-135">Example</span></span>|  
|----------------------------|---------------|-------------|  
|`S`|`Short`|`I = 347S`|
|`I`|`Integer`|`J = 347I`|
|`L`|`Long`|`K = 347L`|
|`D`|`Decimal`|`X = 347D`|
|`F`|`Single`|`Y = 347F`|
|`R`|`Double`|`Z = 347R`|
|`US`|`UShort`|`L = 347US`|
|`UI`|`UInteger`|`M = 347UI`|
|`UL`|`ULong`|`N = 347UL`|
|`C`|`Char`|`Q = "."C`|

<span data-ttu-id="29dd6-136">Для типов данных `Boolean`, `Byte`, `Date`, `Object`, `SByte`или `String` не существует символов типа литерала или для любых составных типов данных, таких как массивы или структуры.</span><span class="sxs-lookup"><span data-stu-id="29dd6-136">No literal type characters exist for the `Boolean`, `Byte`, `Date`, `Object`, `SByte`, or `String` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="29dd6-137">Литералы также могут использовать символы типа идентификатора (`%`, `&`, `@`, `!`, `#`, `$`), как это могут быть переменные, константы и выражения.</span><span class="sxs-lookup"><span data-stu-id="29dd6-137">Literals can also use the identifier type characters (`%`, `&`, `@`, `!`, `#`, `$`), as can variables, constants, and expressions.</span></span> <span data-ttu-id="29dd6-138">Однако символы типа литерала (`S`, `I`, `L`, `D`, `F`, `R`, `C`) можно использовать только с литералами.</span><span class="sxs-lookup"><span data-stu-id="29dd6-138">However, the literal type characters (`S`, `I`, `L`, `D`, `F`, `R`, `C`) can be used only with literals.</span></span>

<span data-ttu-id="29dd6-139">Во всех случаях символ типа литерала должен следовать непосредственно за литеральным значением.</span><span class="sxs-lookup"><span data-stu-id="29dd6-139">In all cases, the literal type character must immediately follow the literal value.</span></span>

## <a name="hexadecimal-binary-and-octal-literals"></a><span data-ttu-id="29dd6-140">Шестнадцатеричные, двоичные и восьмеричные литералы</span><span class="sxs-lookup"><span data-stu-id="29dd6-140">Hexadecimal, binary, and octal literals</span></span>

<span data-ttu-id="29dd6-141">Компилятор обычно интерпретирует целочисленный литерал в десятичной системе счисления (с основанием 10).</span><span class="sxs-lookup"><span data-stu-id="29dd6-141">The compiler normally interprets an integer literal to be in the decimal (base 10) number system.</span></span> <span data-ttu-id="29dd6-142">Можно также определить целочисленный литерал как шестнадцатеричное (с основанием 16) значением префикса `&H`, в виде двоичного номера (основание 2) с префиксом `&B`, а также как восьмеричное (основание 8) число с префиксом `&O`.</span><span class="sxs-lookup"><span data-stu-id="29dd6-142">You can also define an integer literal as a hexadecimal (base 16) number with the `&H` prefix, as a binary (base 2) number with the `&B` prefix, and as an octal (base 8) number with the `&O` prefix.</span></span> <span data-ttu-id="29dd6-143">Цифры, которые следуют за префиксом, должны соответствовать системе счисления.</span><span class="sxs-lookup"><span data-stu-id="29dd6-143">The digits that follow the prefix must be appropriate for the number system.</span></span> <span data-ttu-id="29dd6-144">Это показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="29dd6-144">The following table illustrates this.</span></span>  
  
|<span data-ttu-id="29dd6-145">Базовый номер</span><span class="sxs-lookup"><span data-stu-id="29dd6-145">Number base</span></span>|<span data-ttu-id="29dd6-146">Префикс</span><span class="sxs-lookup"><span data-stu-id="29dd6-146">Prefix</span></span>|<span data-ttu-id="29dd6-147">Допустимые разрядные значения</span><span class="sxs-lookup"><span data-stu-id="29dd6-147">Valid digit values</span></span>|<span data-ttu-id="29dd6-148">Пример</span><span class="sxs-lookup"><span data-stu-id="29dd6-148">Example</span></span>|
|-----------------|------------|------------------------|-------------|
|<span data-ttu-id="29dd6-149">16 (основание 16)</span><span class="sxs-lookup"><span data-stu-id="29dd6-149">Hexadecimal (base 16)</span></span>|`&H`|<span data-ttu-id="29dd6-150">0-9 и A-F</span><span class="sxs-lookup"><span data-stu-id="29dd6-150">0-9 and A-F</span></span>|`&HFFFF`|
|<span data-ttu-id="29dd6-151">Двоичный (основание 2)</span><span class="sxs-lookup"><span data-stu-id="29dd6-151">Binary (base 2)</span></span>|`&B`|<span data-ttu-id="29dd6-152">0—1</span><span class="sxs-lookup"><span data-stu-id="29dd6-152">0-1</span></span>|`&B01111100`|
|<span data-ttu-id="29dd6-153">8 (основание 8)</span><span class="sxs-lookup"><span data-stu-id="29dd6-153">Octal (base 8)</span></span>|`&O`|<span data-ttu-id="29dd6-154">0-7</span><span class="sxs-lookup"><span data-stu-id="29dd6-154">0-7</span></span>|`&O77`|

<span data-ttu-id="29dd6-155">Начиная с Visual Basic 2017 можно использовать символ подчеркивания (`_`) в качестве разделителя групп, чтобы повысить удобочитаемость целочисленного литерала.</span><span class="sxs-lookup"><span data-stu-id="29dd6-155">Starting in Visual Basic 2017, you can use the underscore character (`_`) as a group separator to enhance the readability of an integral literal.</span></span> <span data-ttu-id="29dd6-156">В следующем примере используется символ `_` для группирования двоичного литерала в 8-разрядные группы:</span><span class="sxs-lookup"><span data-stu-id="29dd6-156">The following example uses the `_` character to group a binary literal into 8-bit groups:</span></span>

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

<span data-ttu-id="29dd6-157">Можно следовать предопределенному литералу с символом типа литерала.</span><span class="sxs-lookup"><span data-stu-id="29dd6-157">You can follow a prefixed literal with a literal type character.</span></span> <span data-ttu-id="29dd6-158">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="29dd6-158">The following example shows this.</span></span>

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

<span data-ttu-id="29dd6-159">В предыдущем примере `counter` имеет десятичное значение-32768, а `flags` имеет десятичное значение + 32768.</span><span class="sxs-lookup"><span data-stu-id="29dd6-159">In the previous example, `counter` has the decimal value of -32768, and `flags` has the decimal value of +32768.</span></span>

<span data-ttu-id="29dd6-160">Начиная с Visual Basic 15,5 можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и шестнадцатеричными, двоичными или восьмеричными цифрами.</span><span class="sxs-lookup"><span data-stu-id="29dd6-160">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="29dd6-161">Пример.</span><span class="sxs-lookup"><span data-stu-id="29dd6-161">For example:</span></span>

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a><span data-ttu-id="29dd6-162">См. также</span><span class="sxs-lookup"><span data-stu-id="29dd6-162">See also</span></span>

- [<span data-ttu-id="29dd6-163">Типы данных</span><span class="sxs-lookup"><span data-stu-id="29dd6-163">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="29dd6-164">Простые типы данных</span><span class="sxs-lookup"><span data-stu-id="29dd6-164">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="29dd6-165">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="29dd6-165">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="29dd6-166">Преобразования типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="29dd6-166">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="29dd6-167">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="29dd6-167">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="29dd6-168">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="29dd6-168">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="29dd6-169">Типы данных</span><span class="sxs-lookup"><span data-stu-id="29dd6-169">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
