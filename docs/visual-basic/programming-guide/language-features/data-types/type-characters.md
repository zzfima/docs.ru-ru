---
title: "Введите символы (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals
- F literal type character
- '& identifier type character'
- type characters
- octal literals
- literals, hexadecimal
- '&O prefix for octal values'
- literals, default types
- defaults, literal types
- C literal type character
- type characters, literal
- $ identifier type character
- L literal type character
- UI literal type characters
- default literal types
- D literal type character
- literals, octal
- S literal type character
- '! identifier type character'
- US literal type characters
- '% identifier type character'
- data types [Visual Basic], type characters
- characters, identifier type
- type characters, identifier
- '# identifier type character'
- identifier type characters
- literal type characters
- I literal type character
- R literal type character
- '@ identifier type character'
- UL literal type characters
- literal types, default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 335306eca12070de456a72e918bcbba1e22ab55b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="type-characters-visual-basic"></a><span data-ttu-id="57976-102">Символы типов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57976-102">Type Characters (Visual Basic)</span></span>
<span data-ttu-id="57976-103">В дополнение к определению типов данных в операторе объявления, можно задать тип данных некоторых элементов программирования с *символ типа*.</span><span class="sxs-lookup"><span data-stu-id="57976-103">In addition to specifying a data type in a declaration statement, you can force the data type of some programming elements with a *type character*.</span></span> <span data-ttu-id="57976-104">Знак типа следует непосредственно за элементом без каких-либо промежуточного знака.</span><span class="sxs-lookup"><span data-stu-id="57976-104">The type character must immediately follow the element, with no intervening characters of any kind.</span></span>  
  
 <span data-ttu-id="57976-105">Знак типа не является частью имени элемента.</span><span class="sxs-lookup"><span data-stu-id="57976-105">The type character is not part of the name of the element.</span></span> <span data-ttu-id="57976-106">Ссылка на элемент с символом типа может не знак типа.</span><span class="sxs-lookup"><span data-stu-id="57976-106">An element defined with a type character can be referenced without the type character.</span></span>  
  
## <a name="identifier-type-characters"></a><span data-ttu-id="57976-107">Символы типа идентификатора</span><span class="sxs-lookup"><span data-stu-id="57976-107">Identifier Type Characters</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="57976-108">предоставляет набор *символы типа идентификатора*, который можно использовать в объявлении для задания типа данных переменной или константы.</span><span class="sxs-lookup"><span data-stu-id="57976-108"> supplies a set of *identifier type characters*, which you can use in a declaration to specify the data type of a variable or constant.</span></span> <span data-ttu-id="57976-109">В следующей таблице показаны допустимые символы типа идентификатора с примерами их использования.</span><span class="sxs-lookup"><span data-stu-id="57976-109">The following table shows the available identifier type characters with examples of usage.</span></span>  
  
|<span data-ttu-id="57976-110">Знак типа идентификатора</span><span class="sxs-lookup"><span data-stu-id="57976-110">Identifier type character</span></span>|<span data-ttu-id="57976-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="57976-111">Data type</span></span>|<span data-ttu-id="57976-112">Пример</span><span class="sxs-lookup"><span data-stu-id="57976-112">Example</span></span>|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 <span data-ttu-id="57976-113">Символов типа идентификатора не существует для `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, или `UShort` типы данных, или для любых составных типов данных, таких как массивы и структуры.</span><span class="sxs-lookup"><span data-stu-id="57976-113">No identifier type characters exist for the `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort` data types, or for any composite data types such as arrays or structures.</span></span>  
  
 <span data-ttu-id="57976-114">В некоторых случаях можно добавить `$` символ [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] функции, например `Left$` вместо `Left`, чтобы получить возвращаемое значение типа `String`.</span><span class="sxs-lookup"><span data-stu-id="57976-114">In some cases, you can append the `$` character to a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] function, for example `Left$` instead of `Left`, to obtain a returned value of type `String`.</span></span>  
  
 <span data-ttu-id="57976-115">Во всех случаях знак типа идентификатора должен следовать непосредственно за имя идентификатора.</span><span class="sxs-lookup"><span data-stu-id="57976-115">In all cases, the identifier type character must immediately follow the identifier name.</span></span>  
  
## <a name="literal-type-characters"></a><span data-ttu-id="57976-116">Символы типа литерала</span><span class="sxs-lookup"><span data-stu-id="57976-116">Literal Type Characters</span></span>  
 <span data-ttu-id="57976-117">Объект *литерала* является текстовым представлением отдельного значения типа данных.</span><span class="sxs-lookup"><span data-stu-id="57976-117">A *literal* is a textual representation of a particular value of a data type.</span></span>  
  
### <a name="default-literal-types"></a><span data-ttu-id="57976-118">Типы литералов по умолчанию</span><span class="sxs-lookup"><span data-stu-id="57976-118">Default Literal Types</span></span>  
 <span data-ttu-id="57976-119">Форма литерала, как он отображается в коде, обычно определяет его тип данных.</span><span class="sxs-lookup"><span data-stu-id="57976-119">The form of a literal as it appears in your code ordinarily determines its data type.</span></span> <span data-ttu-id="57976-120">Ниже приведены эти типы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="57976-120">The following table shows these default types.</span></span>  
  
|<span data-ttu-id="57976-121">Текстовая форма литерала</span><span class="sxs-lookup"><span data-stu-id="57976-121">Textual form of literal</span></span>|<span data-ttu-id="57976-122">Тип данных по умолчанию</span><span class="sxs-lookup"><span data-stu-id="57976-122">Default data type</span></span>|<span data-ttu-id="57976-123">Пример</span><span class="sxs-lookup"><span data-stu-id="57976-123">Example</span></span>|  
|-----------------------------|-----------------------|-------------|  
|<span data-ttu-id="57976-124">Числовые без дробной части</span><span class="sxs-lookup"><span data-stu-id="57976-124">Numeric, no fractional part</span></span>|`Integer`|`2147483647`|  
|<span data-ttu-id="57976-125">Числовые без дробной части, слишком велик для`Integer`</span><span class="sxs-lookup"><span data-stu-id="57976-125">Numeric, no fractional part, too large for `Integer`</span></span>|`Long`|`2147483648`|  
|<span data-ttu-id="57976-126">Числовые дробной части</span><span class="sxs-lookup"><span data-stu-id="57976-126">Numeric, fractional part</span></span>|`Double`|`1.2`|  
|<span data-ttu-id="57976-127">Заключено в двойные кавычки</span><span class="sxs-lookup"><span data-stu-id="57976-127">Enclosed in double quotation marks</span></span>|`String`|`"A"`|  
|<span data-ttu-id="57976-128">Заключенные в решетки</span><span class="sxs-lookup"><span data-stu-id="57976-128">Enclosed within number signs</span></span>|`Date`|`#5/17/1993 9:32 AM#`|  
  
### <a name="forced-literal-types"></a><span data-ttu-id="57976-129">Принудительные типы литерала</span><span class="sxs-lookup"><span data-stu-id="57976-129">Forced Literal Types</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="57976-130">предоставляет набор *символы типа литерала*, указывает, что можно использовать для принудительного присвоения литералу тип данных, отличный от его формы.</span><span class="sxs-lookup"><span data-stu-id="57976-130"> supplies a set of *literal type characters*, which you can use to force a literal to assume a data type other than the one its form indicates.</span></span> <span data-ttu-id="57976-131">Это делается путем добавления символа в конец литерала.</span><span class="sxs-lookup"><span data-stu-id="57976-131">You do this by appending the character to the end of the literal.</span></span> <span data-ttu-id="57976-132">В следующей таблице показаны допустимые символы типа литерала с примерами их использования.</span><span class="sxs-lookup"><span data-stu-id="57976-132">The following table shows the available literal type characters with examples of usage.</span></span>  
  
|<span data-ttu-id="57976-133">Знак типа литерала</span><span class="sxs-lookup"><span data-stu-id="57976-133">Literal type character</span></span>|<span data-ttu-id="57976-134">Тип данных</span><span class="sxs-lookup"><span data-stu-id="57976-134">Data type</span></span>|<span data-ttu-id="57976-135">Пример</span><span class="sxs-lookup"><span data-stu-id="57976-135">Example</span></span>|  
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
  
 <span data-ttu-id="57976-136">Символы типа литерала существуют для `Boolean`, `Byte`, `Date`, `Object`, `SByte`, или `String` типы данных, или для любых составных типов данных, таких как массивы и структуры.</span><span class="sxs-lookup"><span data-stu-id="57976-136">No literal type characters exist for the `Boolean`, `Byte`, `Date`, `Object`, `SByte`, or `String` data types, or for any composite data types such as arrays or structures.</span></span>  
  
 <span data-ttu-id="57976-137">Литералы также могут использовать символы типа идентификатора (`%`, `&`, `@`, `!`, `#`, `$`), как и переменные, константы и выражения.</span><span class="sxs-lookup"><span data-stu-id="57976-137">Literals can also use the identifier type characters (`%`, `&`, `@`, `!`, `#`, `$`), as can variables, constants, and expressions.</span></span> <span data-ttu-id="57976-138">Однако, символы типа литерала (`S`, `I`, `L`, `D`, `F`, `R`, `C`) можно использовать только с литералами.</span><span class="sxs-lookup"><span data-stu-id="57976-138">However, the literal type characters (`S`, `I`, `L`, `D`, `F`, `R`, `C`) can be used only with literals.</span></span>  
  
 <span data-ttu-id="57976-139">Во всех случаях знак типа литерала должен следовать непосредственно за литеральное значение.</span><span class="sxs-lookup"><span data-stu-id="57976-139">In all cases, the literal type character must immediately follow the literal value.</span></span>  
  
## <a name="hexadecimal-and-octal-literals"></a><span data-ttu-id="57976-140">Шестнадцатеричные и восьмеричные литералы</span><span class="sxs-lookup"><span data-stu-id="57976-140">Hexadecimal and Octal Literals</span></span>  
 <span data-ttu-id="57976-141">Компилятор обычно construes целочисленным литералом в системе счисления десятичным (основание 10).</span><span class="sxs-lookup"><span data-stu-id="57976-141">The compiler normally construes an integer literal to be in the decimal (base 10) number system.</span></span> <span data-ttu-id="57976-142">Можно принудительно целое литерала шестнадцатеричным (основание 16) с `&H` префикс и заставить его быть восьмеричным (основание 8) с `&O` префикс.</span><span class="sxs-lookup"><span data-stu-id="57976-142">You can force an integer literal to be hexadecimal (base 16) with the `&H` prefix, and you can force it to be octal (base 8) with the `&O` prefix.</span></span> <span data-ttu-id="57976-143">Цифры, располагающиеся за префиксом, должны соответствовать системе счисления.</span><span class="sxs-lookup"><span data-stu-id="57976-143">The digits that follow the prefix must be appropriate for the number system.</span></span> <span data-ttu-id="57976-144">Это показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="57976-144">The following table illustrates this.</span></span>  
  
|<span data-ttu-id="57976-145">Основание системы счисления</span><span class="sxs-lookup"><span data-stu-id="57976-145">Number base</span></span>|<span data-ttu-id="57976-146">Префикс</span><span class="sxs-lookup"><span data-stu-id="57976-146">Prefix</span></span>|<span data-ttu-id="57976-147">Допустимые числовые значения</span><span class="sxs-lookup"><span data-stu-id="57976-147">Valid digit values</span></span>|<span data-ttu-id="57976-148">Пример</span><span class="sxs-lookup"><span data-stu-id="57976-148">Example</span></span>|  
|-----------------|------------|------------------------|-------------|  
|<span data-ttu-id="57976-149">16 (основание 16)</span><span class="sxs-lookup"><span data-stu-id="57976-149">Hexadecimal (base 16)</span></span>|`&H`|<span data-ttu-id="57976-150">0-9 или A-F</span><span class="sxs-lookup"><span data-stu-id="57976-150">0-9 and A-F</span></span>|`&HFFFF`|  
|<span data-ttu-id="57976-151">8 (основание 8)</span><span class="sxs-lookup"><span data-stu-id="57976-151">Octal (base 8)</span></span>|`&O`|<span data-ttu-id="57976-152">0-7</span><span class="sxs-lookup"><span data-stu-id="57976-152">0-7</span></span>|`&O77`|  
  
 <span data-ttu-id="57976-153">Вы можете следовать после префикса литерала знак типа литерала.</span><span class="sxs-lookup"><span data-stu-id="57976-153">You can follow a prefixed literal with a literal type character.</span></span> <span data-ttu-id="57976-154">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="57976-154">The following example shows this.</span></span>  
  
```  
Dim counter As Short = &H8000S  
Dim flags As UShort = &H8000US  
```  
  
 <span data-ttu-id="57976-155">В предыдущем примере `counter` имеет десятичное значение-32768 и `flags` имеет десятичное значение +&32768;.</span><span class="sxs-lookup"><span data-stu-id="57976-155">In the previous example, `counter` has the decimal value of -32768, and `flags` has the decimal value of +32768.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57976-156">См. также</span><span class="sxs-lookup"><span data-stu-id="57976-156">See Also</span></span>  
 <span data-ttu-id="57976-157">[Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="57976-157">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="57976-158"> [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="57976-158"> [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="57976-159"> [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="57976-159"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="57976-160"> [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="57976-160"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="57976-161"> [Устранение неполадок типы данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="57976-161"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="57976-162"> [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="57976-162"> [Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="57976-163"> [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)</span><span class="sxs-lookup"><span data-stu-id="57976-163"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)</span></span>
