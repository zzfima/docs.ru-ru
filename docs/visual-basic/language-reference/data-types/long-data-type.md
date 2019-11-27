---
title: Тип данных Long
ms.date: 01/31/2018
f1_keywords:
- vb.Long
helpviewer_keywords:
- identifier type characters [Visual Basic], &
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- '& identifier type character'
- integer numbers
- literal type characters [Visual Basic], L
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- L literal type character [Visual Basic]
- integers [Visual Basic], types
- Long keyword [Visual Basic]
- data types [Visual Basic], integral
- data types [Visual Basic], assigning
- Long data type
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
ms.openlocfilehash: 16d7409c802e97b1f33474d810134db4d9f0ad6c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343978"
---
# <a name="long-data-type-visual-basic"></a><span data-ttu-id="2f5a1-102">Тип данных Long (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f5a1-102">Long data type (Visual Basic)</span></span>

<span data-ttu-id="2f5a1-103">Содержит 64-битные (8-байтные) целые числа со знаком в диапазоне от-9223372036854775808 до 9 223 372 036 854 775 807 (1 – 7... E + 18).</span><span class="sxs-lookup"><span data-stu-id="2f5a1-103">Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).</span></span>

## <a name="remarks"></a><span data-ttu-id="2f5a1-104">Заметки</span><span class="sxs-lookup"><span data-stu-id="2f5a1-104">Remarks</span></span>

<span data-ttu-id="2f5a1-105">Используйте тип данных `Long` для хранения целочисленных чисел, которые слишком велики для `Integer` типа данных.</span><span class="sxs-lookup"><span data-stu-id="2f5a1-105">Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.</span></span>

<span data-ttu-id="2f5a1-106">Значение по умолчанию для типа `Long` — 0.</span><span class="sxs-lookup"><span data-stu-id="2f5a1-106">The default value of `Long` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="2f5a1-107">Присваивания литералов</span><span class="sxs-lookup"><span data-stu-id="2f5a1-107">Literal assignments</span></span>

<span data-ttu-id="2f5a1-108">Можно объявить и инициализировать переменную `Long`, назначив ей десятичный литерал, шестнадцатеричный литерал, Восьмеричный литерал или (начиная с Visual Basic 2017) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="2f5a1-108">You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="2f5a1-109">Если целочисленный литерал выходит за пределы диапазона `Long` (то есть, если он меньше <xref:System.Int64.MinValue?displayProperty=nameWithType> или больше <xref:System.Int64.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="2f5a1-109">If the integer literal is outside the range of `Long` (that is, if it is less than <xref:System.Int64.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="2f5a1-110">В следующем примере целые числа, равные 4 294 967 296 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `Long`.</span><span class="sxs-lookup"><span data-stu-id="2f5a1-110">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `Long` values.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> <span data-ttu-id="2f5a1-111">Префикс `&h` или `&H` можно использовать для обозначения шестнадцатеричного литерала, префикс `&b` или `&B` для обозначения двоичного литерала, а префикс `&o` или `&O` — для обозначения восьмеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="2f5a1-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="2f5a1-112">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="2f5a1-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="2f5a1-113">Начиная с Visual Basic 2017 можно также использовать символ подчеркивания `_`в качестве разделителя цифр для повышения удобочитаемости, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2f5a1-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="2f5a1-114">Начиная с Visual Basic 15,5 можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и шестнадцатеричными, двоичными или восьмеричными цифрами.</span><span class="sxs-lookup"><span data-stu-id="2f5a1-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="2f5a1-115">Пример.</span><span class="sxs-lookup"><span data-stu-id="2f5a1-115">For example:</span></span>

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="2f5a1-116">Числовые литералы также могут включать [символ типа](../../programming-guide/language-features/data-types/type-characters.md) `L`, чтобы обозначить `Long` тип данных, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2f5a1-116">Numeric literals can also include the `L` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Long` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a><span data-ttu-id="2f5a1-117">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="2f5a1-117">Programming tips</span></span>

- <span data-ttu-id="2f5a1-118">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="2f5a1-118">**Interop Considerations.**</span></span> <span data-ttu-id="2f5a1-119">Если вы взаимодействуете с компонентами, которые не написаны для .NET Framework, например автоматизации или COM-объекты, помните, что `Long` имеет разную ширину данных (32 бит) в других средах.</span><span class="sxs-lookup"><span data-stu-id="2f5a1-119">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="2f5a1-120">При передаче аргумента 32-bit в такой компонент объявите его как `Integer` вместо `Long` в новом коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2f5a1-120">If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.</span></span>

- <span data-ttu-id="2f5a1-121">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="2f5a1-121">**Widening.**</span></span> <span data-ttu-id="2f5a1-122">Тип данных `Long` расширяется до `Decimal`, `Single`или `Double`.</span><span class="sxs-lookup"><span data-stu-id="2f5a1-122">The `Long` data type widens to `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="2f5a1-123">Это означает, что тип `Long` можно преобразовать в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2f5a1-123">This means you can convert `Long` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="2f5a1-124">**Символы типа.**</span><span class="sxs-lookup"><span data-stu-id="2f5a1-124">**Type Characters.**</span></span> <span data-ttu-id="2f5a1-125">При добавлении к литералу символа типа литерала `L` производится принудительное приведение литерала к типу данных `Long`.</span><span class="sxs-lookup"><span data-stu-id="2f5a1-125">Appending the literal type character `L` to a literal forces it to the `Long` data type.</span></span> <span data-ttu-id="2f5a1-126">При добавлении символа идентификатора типа `&` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Long`.</span><span class="sxs-lookup"><span data-stu-id="2f5a1-126">Appending the identifier type character `&` to any identifier forces it to `Long`.</span></span>

- <span data-ttu-id="2f5a1-127">**Тип платформы.**</span><span class="sxs-lookup"><span data-stu-id="2f5a1-127">**Framework Type.**</span></span> <span data-ttu-id="2f5a1-128">В .NET Framework данный тип соответствует структуре <xref:System.Int64?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2f5a1-128">The corresponding type in the .NET Framework is the <xref:System.Int64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f5a1-129">См. также</span><span class="sxs-lookup"><span data-stu-id="2f5a1-129">See also</span></span>

- <xref:System.Int64>
- [<span data-ttu-id="2f5a1-130">Типы данных</span><span class="sxs-lookup"><span data-stu-id="2f5a1-130">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="2f5a1-131">Тип данных Integer</span><span class="sxs-lookup"><span data-stu-id="2f5a1-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="2f5a1-132">Тип данных Short</span><span class="sxs-lookup"><span data-stu-id="2f5a1-132">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="2f5a1-133">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="2f5a1-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="2f5a1-134">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="2f5a1-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="2f5a1-135">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="2f5a1-135">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
