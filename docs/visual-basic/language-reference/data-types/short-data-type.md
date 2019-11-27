---
title: Тип данных Short
ms.date: 01/31/2018
f1_keywords:
- vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: 8dfdfb56de32e4b3a96729b09ccf46a6fee9a424
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343938"
---
# <a name="short-data-type-visual-basic"></a><span data-ttu-id="0ef9c-102">Короткий тип данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ef9c-102">Short data type (Visual Basic)</span></span>

<span data-ttu-id="0ef9c-103">Содержит 16-битные (2-байтные) целые числа со знаком в диапазоне от-32 768 до 32 767.</span><span class="sxs-lookup"><span data-stu-id="0ef9c-103">Holds signed 16-bit (2-byte) integers that range in value from -32,768 through 32,767.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ef9c-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="0ef9c-104">Remarks</span></span>  

 <span data-ttu-id="0ef9c-105">Используйте тип данных `Short` для хранения целочисленных значений, не требующих полной ширины данных `Integer`.</span><span class="sxs-lookup"><span data-stu-id="0ef9c-105">Use the `Short` data type to contain integer values that do not require the full data width of `Integer`.</span></span> <span data-ttu-id="0ef9c-106">В некоторых случаях среда CLR может объединять переменные `Short` и экономить потребление памяти.</span><span class="sxs-lookup"><span data-stu-id="0ef9c-106">In some cases, the common language runtime can pack your `Short` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="0ef9c-107">Значение по умолчанию для типа `Short` — 0.</span><span class="sxs-lookup"><span data-stu-id="0ef9c-107">The default value of `Short` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="0ef9c-108">Присваивания литералов</span><span class="sxs-lookup"><span data-stu-id="0ef9c-108">Literal assignments</span></span>

<span data-ttu-id="0ef9c-109">Можно объявить и инициализировать переменную `Short`, назначив ей десятичный литерал, шестнадцатеричный литерал, Восьмеричный литерал или (начиная с Visual Basic 2017) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="0ef9c-109">You can declare and initialize a `Short` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="0ef9c-110">Если целочисленный литерал выходит за пределы диапазона `Short` (то есть, если он меньше <xref:System.Int16.MinValue?displayProperty=nameWithType> или больше <xref:System.Int16.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="0ef9c-110">If the integer literal is outside the range of `Short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="0ef9c-111">В следующем примере целые числа, равные 1 034, представленные в виде десятичного, шестнадцатеричного и двоичного литерала, неявно преобразуются из [целого числа](integer-data-type.md) в `Short` значения.</span><span class="sxs-lookup"><span data-stu-id="0ef9c-111">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `Short` values.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> <span data-ttu-id="0ef9c-112">Префикс `&h` или `&H` можно использовать для обозначения шестнадцатеричного литерала, префикс `&b` или `&B` для обозначения двоичного литерала, а префикс `&o` или `&O` — для обозначения восьмеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="0ef9c-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="0ef9c-113">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="0ef9c-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="0ef9c-114">Начиная с Visual Basic 2017 можно также использовать символ подчеркивания `_`в качестве разделителя цифр для повышения удобочитаемости, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0ef9c-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

<span data-ttu-id="0ef9c-115">Начиная с Visual Basic 15,5 можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и шестнадцатеричными, двоичными или восьмеричными цифрами.</span><span class="sxs-lookup"><span data-stu-id="0ef9c-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="0ef9c-116">Пример.</span><span class="sxs-lookup"><span data-stu-id="0ef9c-116">For example:</span></span>

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="0ef9c-117">Числовые литералы также могут включать [символ типа](../../programming-guide/language-features/data-types/type-characters.md) `S`, чтобы обозначить `Short` тип данных, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0ef9c-117">Numeric literals can also include the `S` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Short` data type, as the following example shows.</span></span>

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a><span data-ttu-id="0ef9c-118">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="0ef9c-118">Programming tips</span></span>

- <span data-ttu-id="0ef9c-119">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="0ef9c-119">**Widening.**</span></span> <span data-ttu-id="0ef9c-120">Тип данных `Short` расширяется до `Integer`, `Long`, `Decimal`, `Single`или `Double`.</span><span class="sxs-lookup"><span data-stu-id="0ef9c-120">The `Short` data type widens to `Integer`, `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="0ef9c-121">Это означает, что тип `Short` можно преобразовать в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0ef9c-121">This means you can convert `Short` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="0ef9c-122">**Символы типа.**</span><span class="sxs-lookup"><span data-stu-id="0ef9c-122">**Type Characters.**</span></span> <span data-ttu-id="0ef9c-123">При добавлении к литералу символа типа литерала `S` производится принудительное приведение литерала к типу данных `Short`.</span><span class="sxs-lookup"><span data-stu-id="0ef9c-123">Appending the literal type character `S` to a literal forces it to the `Short` data type.</span></span> <span data-ttu-id="0ef9c-124">`Short` не имеет символа типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="0ef9c-124">`Short` has no identifier type character.</span></span>  
  
- <span data-ttu-id="0ef9c-125">**Тип платформы.**</span><span class="sxs-lookup"><span data-stu-id="0ef9c-125">**Framework Type.**</span></span> <span data-ttu-id="0ef9c-126">В .NET Framework данный тип соответствует структуре <xref:System.Int16?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0ef9c-126">The corresponding type in the .NET Framework is the <xref:System.Int16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ef9c-127">См. также</span><span class="sxs-lookup"><span data-stu-id="0ef9c-127">See also</span></span>

- <xref:System.Int16?displayProperty=nameWithType>
- [<span data-ttu-id="0ef9c-128">Типы данных</span><span class="sxs-lookup"><span data-stu-id="0ef9c-128">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="0ef9c-129">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="0ef9c-129">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="0ef9c-130">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="0ef9c-130">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="0ef9c-131">Тип данных Integer</span><span class="sxs-lookup"><span data-stu-id="0ef9c-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="0ef9c-132">Тип данных Long</span><span class="sxs-lookup"><span data-stu-id="0ef9c-132">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [<span data-ttu-id="0ef9c-133">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="0ef9c-133">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
