---
title: Символы типов (Visual Basic)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9262c57c5773b947f18fd9e8cf9087bb8e02de7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653511"
---
# <a name="type-characters-visual-basic"></a><span data-ttu-id="6601a-102">Введите символы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6601a-102">Type characters (Visual Basic)</span></span>

<span data-ttu-id="6601a-103">В дополнение к определению типов данных в операторе объявления, можно задать тип данных некоторых элементов программирования с *символ типа*.</span><span class="sxs-lookup"><span data-stu-id="6601a-103">In addition to specifying a data type in a declaration statement, you can force the data type of some programming elements with a *type character*.</span></span> <span data-ttu-id="6601a-104">Символ типа следует непосредственно за элементом без какого-промежуточные знака.</span><span class="sxs-lookup"><span data-stu-id="6601a-104">The type character must immediately follow the element, with no intervening characters of any kind.</span></span>

<span data-ttu-id="6601a-105">Символ типа не является частью имени элемента.</span><span class="sxs-lookup"><span data-stu-id="6601a-105">The type character is not part of the name of the element.</span></span> <span data-ttu-id="6601a-106">Ссылка на элемент с символом типа можно без знака типа.</span><span class="sxs-lookup"><span data-stu-id="6601a-106">An element defined with a type character can be referenced without the type character.</span></span>

## <a name="identifier-type-characters"></a><span data-ttu-id="6601a-107">Символы типа идентификатора</span><span class="sxs-lookup"><span data-stu-id="6601a-107">Identifier type characters</span></span>

<span data-ttu-id="6601a-108">В Visual Basic предусмотрен набор *символы типа идентификатора* , можно использовать в объявлении для указания типа данных переменной или константы.</span><span class="sxs-lookup"><span data-stu-id="6601a-108">Visual Basic supplies a set of *identifier type characters* that you can use in a declaration to specify the data type of a variable or constant.</span></span> <span data-ttu-id="6601a-109">В следующей таблице показаны допустимые символы типа идентификатора с примерами использования.</span><span class="sxs-lookup"><span data-stu-id="6601a-109">The following table shows the available identifier type characters with examples of usage.</span></span>
  
|<span data-ttu-id="6601a-110">Знак типа идентификатора</span><span class="sxs-lookup"><span data-stu-id="6601a-110">Identifier type character</span></span>|<span data-ttu-id="6601a-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6601a-111">Data type</span></span>|<span data-ttu-id="6601a-112">Пример</span><span class="sxs-lookup"><span data-stu-id="6601a-112">Example</span></span>|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 <span data-ttu-id="6601a-113">Для символов типа идентификатора не существует `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, или `UShort` типов данных или других составные типы данных, таких как массивы и структуры.</span><span class="sxs-lookup"><span data-stu-id="6601a-113">No identifier type characters exist for the `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="6601a-114">В некоторых случаях можно добавить `$` символ для функции Visual Basic, например `Left$` вместо `Left`, для получения возвращаемого значения типа `String`.</span><span class="sxs-lookup"><span data-stu-id="6601a-114">In some cases, you can append the `$` character to a Visual Basic function, for example `Left$` instead of `Left`, to obtain a returned value of type `String`.</span></span>

<span data-ttu-id="6601a-115">Во всех случаях знак типа идентификатора должен следовать непосредственно за имя идентификатора.</span><span class="sxs-lookup"><span data-stu-id="6601a-115">In all cases, the identifier type character must immediately follow the identifier name.</span></span>

## <a name="literal-type-characters"></a><span data-ttu-id="6601a-116">Символы типа литерала</span><span class="sxs-lookup"><span data-stu-id="6601a-116">Literal type characters</span></span>

<span data-ttu-id="6601a-117">Объект *литерала* является текстовым представлением отдельного значения типа данных.</span><span class="sxs-lookup"><span data-stu-id="6601a-117">A *literal* is a textual representation of a particular value of a data type.</span></span>  

### <a name="default-literal-types"></a><span data-ttu-id="6601a-118">Типы литералов по умолчанию</span><span class="sxs-lookup"><span data-stu-id="6601a-118">Default literal types</span></span>

<span data-ttu-id="6601a-119">Форма литерала, как оно отображается в коде, обычно определяет его тип данных.</span><span class="sxs-lookup"><span data-stu-id="6601a-119">The form of a literal as it appears in your code ordinarily determines its data type.</span></span> <span data-ttu-id="6601a-120">В следующей таблице показаны эти типы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6601a-120">The following table shows these default types.</span></span>  
  
|<span data-ttu-id="6601a-121">Текстовая форма литерала</span><span class="sxs-lookup"><span data-stu-id="6601a-121">Textual form of literal</span></span>|<span data-ttu-id="6601a-122">Тип данных по умолчанию</span><span class="sxs-lookup"><span data-stu-id="6601a-122">Default data type</span></span>|<span data-ttu-id="6601a-123">Пример</span><span class="sxs-lookup"><span data-stu-id="6601a-123">Example</span></span>|  
|-----------------------------|-----------------------|-------------|  
|<span data-ttu-id="6601a-124">Числовые без дробной части</span><span class="sxs-lookup"><span data-stu-id="6601a-124">Numeric, no fractional part</span></span>|`Integer`|`2147483647`|  
|<span data-ttu-id="6601a-125">Числовые без дробной части, слишком велик для `Integer`</span><span class="sxs-lookup"><span data-stu-id="6601a-125">Numeric, no fractional part, too large for `Integer`</span></span>|`Long`|`2147483648`|  
|<span data-ttu-id="6601a-126">Числовые дробной части</span><span class="sxs-lookup"><span data-stu-id="6601a-126">Numeric, fractional part</span></span>|`Double`|`1.2`|  
|<span data-ttu-id="6601a-127">Заключено в двойные кавычки</span><span class="sxs-lookup"><span data-stu-id="6601a-127">Enclosed in double quotation marks</span></span>|`String`|`"A"`|  
|<span data-ttu-id="6601a-128">Заключенные в решетки</span><span class="sxs-lookup"><span data-stu-id="6601a-128">Enclosed within number signs</span></span>|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a><span data-ttu-id="6601a-129">Принудительные типы литерала</span><span class="sxs-lookup"><span data-stu-id="6601a-129">Forced literal types</span></span>

<span data-ttu-id="6601a-130">В Visual Basic предусмотрен набор *символы типа литерала*, указывает, который можно использовать для принудительного присвоения литералу тип данных, отличной от той, содержащей его формы.</span><span class="sxs-lookup"><span data-stu-id="6601a-130">Visual Basic supplies a set of *literal type characters*, which you can use to force a literal to assume a data type other than the one its form indicates.</span></span> <span data-ttu-id="6601a-131">Это делается путем добавления символа в конец литерала.</span><span class="sxs-lookup"><span data-stu-id="6601a-131">You do this by appending the character to the end of the literal.</span></span> <span data-ttu-id="6601a-132">В следующей таблице показаны допустимые символы типа литерала с примерами использования.</span><span class="sxs-lookup"><span data-stu-id="6601a-132">The following table shows the available literal type characters with examples of usage.</span></span>
  
|<span data-ttu-id="6601a-133">Знак типа литерала</span><span class="sxs-lookup"><span data-stu-id="6601a-133">Literal type character</span></span>|<span data-ttu-id="6601a-134">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6601a-134">Data type</span></span>|<span data-ttu-id="6601a-135">Пример</span><span class="sxs-lookup"><span data-stu-id="6601a-135">Example</span></span>|  
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

<span data-ttu-id="6601a-136">Символы типа литерала существует для `Boolean`, `Byte`, `Date`, `Object`, `SByte`, или `String` типы данных, или для любых составных типов данных, таких как массивы и структуры.</span><span class="sxs-lookup"><span data-stu-id="6601a-136">No literal type characters exist for the `Boolean`, `Byte`, `Date`, `Object`, `SByte`, or `String` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="6601a-137">Литералы также можно использовать символы типа идентификатора (`%`, `&`, `@`, `!`, `#`, `$`), как и переменные, константы и выражения.</span><span class="sxs-lookup"><span data-stu-id="6601a-137">Literals can also use the identifier type characters (`%`, `&`, `@`, `!`, `#`, `$`), as can variables, constants, and expressions.</span></span> <span data-ttu-id="6601a-138">Тем не менее, символы типа литерала (`S`, `I`, `L`, `D`, `F`, `R`, `C`) можно использовать только с литералами.</span><span class="sxs-lookup"><span data-stu-id="6601a-138">However, the literal type characters (`S`, `I`, `L`, `D`, `F`, `R`, `C`) can be used only with literals.</span></span>

<span data-ttu-id="6601a-139">Во всех случаях знак типа литерала должен следовать непосредственно за литеральное значение.</span><span class="sxs-lookup"><span data-stu-id="6601a-139">In all cases, the literal type character must immediately follow the literal value.</span></span>

## <a name="hexadecimal-binary-and-octal-literals"></a><span data-ttu-id="6601a-140">Шестнадцатеричные, двоичные и восьмеричные литералы</span><span class="sxs-lookup"><span data-stu-id="6601a-140">Hexadecimal, binary, and octal literals</span></span>

<span data-ttu-id="6601a-141">Как правило, компилятор интерпретирует целочисленный литерал в системе счисления десятичным (основание 10).</span><span class="sxs-lookup"><span data-stu-id="6601a-141">The compiler normally interprets an integer literal to be in the decimal (base 10) number system.</span></span> <span data-ttu-id="6601a-142">Можно также определить целочисленный литерал в шестнадцатеричном формате (основание 16) число с `&H` префикс как число двоичного файла (по основанию 2) с `&B` префикс и в качестве восьмеричным (основание 8) число с `&O` префикс.</span><span class="sxs-lookup"><span data-stu-id="6601a-142">You can also define an integer literal as a hexadecimal (base 16) number with the `&H` prefix, as a binary (base 2) number with the `&B` prefix, and as an octal (base 8) number with the `&O` prefix.</span></span> <span data-ttu-id="6601a-143">Цифры, выполните префикс должна соответствовать системе счисления.</span><span class="sxs-lookup"><span data-stu-id="6601a-143">The digits that follow the prefix must be appropriate for the number system.</span></span> <span data-ttu-id="6601a-144">Это показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="6601a-144">The following table illustrates this.</span></span>  
  
|<span data-ttu-id="6601a-145">Основание системы счисления</span><span class="sxs-lookup"><span data-stu-id="6601a-145">Number base</span></span>|<span data-ttu-id="6601a-146">Префикс</span><span class="sxs-lookup"><span data-stu-id="6601a-146">Prefix</span></span>|<span data-ttu-id="6601a-147">Допустимые числовые значения</span><span class="sxs-lookup"><span data-stu-id="6601a-147">Valid digit values</span></span>|<span data-ttu-id="6601a-148">Пример</span><span class="sxs-lookup"><span data-stu-id="6601a-148">Example</span></span>|
|-----------------|------------|------------------------|-------------|
|<span data-ttu-id="6601a-149">16 (основание 16)</span><span class="sxs-lookup"><span data-stu-id="6601a-149">Hexadecimal (base 16)</span></span>|`&H`|<span data-ttu-id="6601a-150">0-9 или A-F</span><span class="sxs-lookup"><span data-stu-id="6601a-150">0-9 and A-F</span></span>|`&HFFFF`|
|<span data-ttu-id="6601a-151">Двоичный файл (по основанию 2)</span><span class="sxs-lookup"><span data-stu-id="6601a-151">Binary (base 2)</span></span>|`&B`|<span data-ttu-id="6601a-152">0—1</span><span class="sxs-lookup"><span data-stu-id="6601a-152">0-1</span></span>|`&B01111100`|
|<span data-ttu-id="6601a-153">8 (основание 8)</span><span class="sxs-lookup"><span data-stu-id="6601a-153">Octal (base 8)</span></span>|`&O`|<span data-ttu-id="6601a-154">0-7</span><span class="sxs-lookup"><span data-stu-id="6601a-154">0-7</span></span>|`&O77`|

<span data-ttu-id="6601a-155">Начиная с Visual Basic 2017 г., можно использовать символ подчеркивания (`_`) как разделитель групп, чтобы повысить удобочитаемость используется целочисленный литерал.</span><span class="sxs-lookup"><span data-stu-id="6601a-155">Starting in Visual Basic 2017, you can use the underscore character (`_`) as a group separator to enhance the readability of an integral literal.</span></span> <span data-ttu-id="6601a-156">В следующем примере используется `_` знак, который необходимо объединить двоичный литерал в 8-разрядное группы:</span><span class="sxs-lookup"><span data-stu-id="6601a-156">The following example uses the `_` character to group a binary literal into 8-bit groups:</span></span>

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

<span data-ttu-id="6601a-157">Вы можете использовать литерал с префиксом, знак типа литерала.</span><span class="sxs-lookup"><span data-stu-id="6601a-157">You can follow a prefixed literal with a literal type character.</span></span> <span data-ttu-id="6601a-158">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="6601a-158">The following example shows this.</span></span>

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

<span data-ttu-id="6601a-159">В предыдущем примере `counter` имеет десятичное значение от -32768, и `flags` имеет десятичное значение + 32768.</span><span class="sxs-lookup"><span data-stu-id="6601a-159">In the previous example, `counter` has the decimal value of -32768, and `flags` has the decimal value of +32768.</span></span>

<span data-ttu-id="6601a-160">Начиная с Visual Basic 15,5, можно также использовать символ подчеркивания (`_`) в качестве начальных разделителя между префиксом и двоичное, шестнадцатеричное или восьмеричное цифры.</span><span class="sxs-lookup"><span data-stu-id="6601a-160">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="6601a-161">Пример:</span><span class="sxs-lookup"><span data-stu-id="6601a-161">For example:</span></span>

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a><span data-ttu-id="6601a-162">См. также</span><span class="sxs-lookup"><span data-stu-id="6601a-162">See Also</span></span>

 [<span data-ttu-id="6601a-163">Типы данных</span><span class="sxs-lookup"><span data-stu-id="6601a-163">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="6601a-164">Простые типы данных</span><span class="sxs-lookup"><span data-stu-id="6601a-164">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="6601a-165">Типы значений и ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="6601a-165">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="6601a-166">Преобразования типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6601a-166">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="6601a-167">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="6601a-167">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="6601a-168">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="6601a-168">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="6601a-169">Типы данных</span><span class="sxs-lookup"><span data-stu-id="6601a-169">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
