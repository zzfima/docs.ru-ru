---
title: Тип данных SByte (Visual Basic)
ms.date: 04/20/2017
f1_keywords:
- vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94ab72b2ac2678640697e3cfab426e5a7d6d889a
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933156"
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="8945d-102">Тип данных SByte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8945d-102">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="8945d-103">Содержит знаком 8-разрядных целых чисел (1-байтовое), которые могут меняться в диапазоне от -128 до 127.</span><span class="sxs-lookup"><span data-stu-id="8945d-103">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8945d-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="8945d-104">Remarks</span></span>

<span data-ttu-id="8945d-105">Используйте `SByte` тип данных для хранения целых значений, которые не требуют полного размера `Integer` или даже половины данных ширину `Short`.</span><span class="sxs-lookup"><span data-stu-id="8945d-105">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="8945d-106">В некоторых случаях среда CLR можно упаковать в `SByte` переменные в тесном контакте и снизить потребление памяти.</span><span class="sxs-lookup"><span data-stu-id="8945d-106">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="8945d-107">Значение по умолчанию для типа `SByte` — 0.</span><span class="sxs-lookup"><span data-stu-id="8945d-107">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="8945d-108">Назначения литералов</span><span class="sxs-lookup"><span data-stu-id="8945d-108">Literal assignments</span></span>
  
<span data-ttu-id="8945d-109">Можно объявить и инициализировать `SByte` переменной, назначив ей десятичный литерал, шестнадцатеричный восьмеричный литерал, или (начиная с Visual Basic 2017) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="8945d-109">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="8945d-110">В следующем примере целые числа, равные 102 представляются в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются `SByte` значения.</span><span class="sxs-lookup"><span data-stu-id="8945d-110">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="8945d-111">В этом примере требуется компилировать с `/removeintchecks` параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="8945d-111">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]  

> [!NOTE] 
> <span data-ttu-id="8945d-112">Используйте префикс `&h` или `&H` для обозначения шестнадцатеричного литерала, префикс `&b` или `&B` для обозначения двоичного литерала, а также префикс `&o` или `&O` для обозначения восьмеричный литерал.</span><span class="sxs-lookup"><span data-stu-id="8945d-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="8945d-113">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="8945d-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="8945d-114">Начиная с Visual Basic 2017, можно также использовать символ подчеркивания, `_`, в качестве разделителя разрядов для повышения удобства чтения, как в примере ниже показан.</span><span class="sxs-lookup"><span data-stu-id="8945d-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]  

<span data-ttu-id="8945d-115">Начиная с Visual Basic 15.5, можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и двоичное, шестнадцатеричное или восьмеричное цифры.</span><span class="sxs-lookup"><span data-stu-id="8945d-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="8945d-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="8945d-116">For example:</span></span>

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="8945d-117">Если целочисленный литерал выходит за пределы диапазона `SByte` (то есть, если он меньше <xref:System.SByte.MinValue?displayProperty=nameWithType> или больше <xref:System.SByte.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="8945d-117">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="8945d-118">Если целочисленный литерал не имеет суффикса, [целое число](integer-data-type.md) выводится.</span><span class="sxs-lookup"><span data-stu-id="8945d-118">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="8945d-119">Если целочисленный литерал выходит за пределы диапазона `Integer` типа, [Long](long-data-type.md) выводится.</span><span class="sxs-lookup"><span data-stu-id="8945d-119">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="8945d-120">Это означает, что в предыдущих примерах, числовые литералы `0x9A` и `0b10011010` интерпретируются как 32-разрядных целых чисел со знаком с имеющие значение 156, превышающее <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8945d-120">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8945d-121">Для успешной компиляции кода, например, присваивает недесятичных целое число для `SByte`, можно выполнить одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="8945d-121">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="8945d-122">Отключение проверки границ для целочисленных значений при компиляции с `/removeintchecks` параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="8945d-122">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="8945d-123">Используйте [символ типа](../../programming-guide\language-features\data-types/type-characters.md) для явного определения литеральное значение, которое вы хотите назначить `SByte`.</span><span class="sxs-lookup"><span data-stu-id="8945d-123">Use a [type character](../../programming-guide\language-features\data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="8945d-124">В следующем примере присваивается отрицательное литерал `Short` значение `SByte`.</span><span class="sxs-lookup"><span data-stu-id="8945d-124">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="8945d-125">Обратите внимание, что для отрицательных чисел, необходимо установить бит высокого порядка из старшего слова числового литерала.</span><span class="sxs-lookup"><span data-stu-id="8945d-125">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="8945d-126">В нашем примере это бит 15 литерала `Short` значение.</span><span class="sxs-lookup"><span data-stu-id="8945d-126">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="8945d-127">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="8945d-127">Programming tips</span></span>
  
-   <span data-ttu-id="8945d-128">**CLS-совместимость.**</span><span class="sxs-lookup"><span data-stu-id="8945d-128">**CLS Compliance.**</span></span> <span data-ttu-id="8945d-129">`SByte` Тип данных не является частью [спецификация CLS](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), поэтому CLS-совместимого кода нельзя использовать компонент, который его использует.</span><span class="sxs-lookup"><span data-stu-id="8945d-129">The `SByte` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

-   <span data-ttu-id="8945d-130">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="8945d-130">**Widening.**</span></span> <span data-ttu-id="8945d-131">`SByte` Тип данных можно расширить до `Short`, `Integer`, `Long`, `Decimal`, `Single`, и `Double`.</span><span class="sxs-lookup"><span data-stu-id="8945d-131">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="8945d-132">Это означает, что вы можете преобразовать `SByte` к любому из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.</span><span class="sxs-lookup"><span data-stu-id="8945d-132">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
-   <span data-ttu-id="8945d-133">**Символы типа.**</span><span class="sxs-lookup"><span data-stu-id="8945d-133">**Type Characters.**</span></span> <span data-ttu-id="8945d-134">`SByte` не имеет знак типа литерала или знак типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="8945d-134">`SByte` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="8945d-135">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="8945d-135">**Framework Type.**</span></span> <span data-ttu-id="8945d-136">В .NET Framework данный тип соответствует структуре <xref:System.SByte?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8945d-136">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8945d-137">См. также</span><span class="sxs-lookup"><span data-stu-id="8945d-137">See also</span></span>

 <xref:System.SByte?displayProperty=nameWithType>  
 [<span data-ttu-id="8945d-138">Типы данных</span><span class="sxs-lookup"><span data-stu-id="8945d-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="8945d-139">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="8945d-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="8945d-140">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="8945d-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="8945d-141">Тип данных Short</span><span class="sxs-lookup"><span data-stu-id="8945d-141">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)  
 [<span data-ttu-id="8945d-142">Тип данных Integer</span><span class="sxs-lookup"><span data-stu-id="8945d-142">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="8945d-143">Тип данных Long</span><span class="sxs-lookup"><span data-stu-id="8945d-143">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [<span data-ttu-id="8945d-144">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="8945d-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
