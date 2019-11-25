---
title: Тип данных UInteger
ms.date: 01/31/2018
f1_keywords:
- vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
ms.openlocfilehash: ccff61608aed797734cb4f5ca0571d7ed73ba98b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343889"
---
# <a name="uinteger-data-type"></a><span data-ttu-id="35d7a-102">UInteger - тип данных</span><span class="sxs-lookup"><span data-stu-id="35d7a-102">UInteger data type</span></span>

<span data-ttu-id="35d7a-103">Holds unsigned 32-bit (4-byte) integers ranging in value from 0 through 4,294,967,295.</span><span class="sxs-lookup"><span data-stu-id="35d7a-103">Holds unsigned 32-bit (4-byte) integers ranging in value from 0 through 4,294,967,295.</span></span>

## <a name="remarks"></a><span data-ttu-id="35d7a-104">Заметки</span><span class="sxs-lookup"><span data-stu-id="35d7a-104">Remarks</span></span>

<span data-ttu-id="35d7a-105">The `UInteger` data type provides the largest unsigned value in the most efficient data width.</span><span class="sxs-lookup"><span data-stu-id="35d7a-105">The `UInteger` data type provides the largest unsigned value in the most efficient data width.</span></span>

<span data-ttu-id="35d7a-106">Значение по умолчанию для типа `UInteger` — 0.</span><span class="sxs-lookup"><span data-stu-id="35d7a-106">The default value of `UInteger` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="35d7a-107">Literal assignments</span><span class="sxs-lookup"><span data-stu-id="35d7a-107">Literal assignments</span></span>

<span data-ttu-id="35d7a-108">You can declare and initialize a `UInteger` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span><span class="sxs-lookup"><span data-stu-id="35d7a-108">You can declare and initialize a `UInteger` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="35d7a-109">Если целочисленный литерал выходит за пределы диапазона `UInteger` (то есть, если он меньше <xref:System.UInt32.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="35d7a-109">If the integer literal is outside the range of `UInteger` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="35d7a-110">В следующем примере целые числа, равные 3 000 000 000 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `UInteger`.</span><span class="sxs-lookup"><span data-stu-id="35d7a-110">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `UInteger` values.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]

> [!NOTE]
> <span data-ttu-id="35d7a-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span><span class="sxs-lookup"><span data-stu-id="35d7a-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="35d7a-112">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="35d7a-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="35d7a-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span><span class="sxs-lookup"><span data-stu-id="35d7a-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]

<span data-ttu-id="35d7a-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span><span class="sxs-lookup"><span data-stu-id="35d7a-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="35d7a-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="35d7a-115">For example:</span></span>

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="35d7a-116">Numeric literals can also include the `UI` or `ui` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UInteger` data type, as the following example shows.</span><span class="sxs-lookup"><span data-stu-id="35d7a-116">Numeric literals can also include the `UI` or `ui` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UInteger` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a><span data-ttu-id="35d7a-117">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="35d7a-117">Programming tips</span></span>

<span data-ttu-id="35d7a-118">The `UInteger` and `Integer` data types provide optimal performance on a 32-bit processor, because the smaller integer types (`UShort`, `Short`, `Byte`, and `SByte`), even though they use fewer bits, take more time to load, store, and fetch.</span><span class="sxs-lookup"><span data-stu-id="35d7a-118">The `UInteger` and `Integer` data types provide optimal performance on a 32-bit processor, because the smaller integer types (`UShort`, `Short`, `Byte`, and `SByte`), even though they use fewer bits, take more time to load, store, and fetch.</span></span>

- <span data-ttu-id="35d7a-119">**Negative Numbers.**</span><span class="sxs-lookup"><span data-stu-id="35d7a-119">**Negative Numbers.**</span></span> <span data-ttu-id="35d7a-120">Because `UInteger` is an unsigned type, it cannot represent a negative number.</span><span class="sxs-lookup"><span data-stu-id="35d7a-120">Because `UInteger` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="35d7a-121">If you use the unary minus (`-`) operator on an expression that evaluates to type `UInteger`, Visual Basic converts the expression to `Long` first.</span><span class="sxs-lookup"><span data-stu-id="35d7a-121">If you use the unary minus (`-`) operator on an expression that evaluates to type `UInteger`, Visual Basic converts the expression to `Long` first.</span></span>

- <span data-ttu-id="35d7a-122">**CLS Compliance.**</span><span class="sxs-lookup"><span data-stu-id="35d7a-122">**CLS Compliance.**</span></span> <span data-ttu-id="35d7a-123">The `UInteger` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span><span class="sxs-lookup"><span data-stu-id="35d7a-123">The `UInteger` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="35d7a-124">**Interop Considerations.**</span><span class="sxs-lookup"><span data-stu-id="35d7a-124">**Interop Considerations.**</span></span> <span data-ttu-id="35d7a-125">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `uint` can have a different data width (16 bits) in other environments.</span><span class="sxs-lookup"><span data-stu-id="35d7a-125">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `uint` can have a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="35d7a-126">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span><span class="sxs-lookup"><span data-stu-id="35d7a-126">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>

- <span data-ttu-id="35d7a-127">**Widening.**</span><span class="sxs-lookup"><span data-stu-id="35d7a-127">**Widening.**</span></span> <span data-ttu-id="35d7a-128">The `UInteger` data type widens to `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span><span class="sxs-lookup"><span data-stu-id="35d7a-128">The `UInteger` data type widens to `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="35d7a-129">This means you can convert `UInteger` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="35d7a-129">This means you can convert `UInteger` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="35d7a-130">**Type Characters.**</span><span class="sxs-lookup"><span data-stu-id="35d7a-130">**Type Characters.**</span></span> <span data-ttu-id="35d7a-131">Appending the literal type characters `UI` to a literal forces it to the `UInteger` data type.</span><span class="sxs-lookup"><span data-stu-id="35d7a-131">Appending the literal type characters `UI` to a literal forces it to the `UInteger` data type.</span></span> <span data-ttu-id="35d7a-132">`UInteger` has no identifier type character.</span><span class="sxs-lookup"><span data-stu-id="35d7a-132">`UInteger` has no identifier type character.</span></span>

- <span data-ttu-id="35d7a-133">**Framework Type.**</span><span class="sxs-lookup"><span data-stu-id="35d7a-133">**Framework Type.**</span></span> <span data-ttu-id="35d7a-134">В .NET Framework данный тип соответствует структуре <xref:System.UInt32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="35d7a-134">The corresponding type in the .NET Framework is the <xref:System.UInt32?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="35d7a-135">См. также</span><span class="sxs-lookup"><span data-stu-id="35d7a-135">See also</span></span>

- <xref:System.UInt32>
- [<span data-ttu-id="35d7a-136">Типы данных</span><span class="sxs-lookup"><span data-stu-id="35d7a-136">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="35d7a-137">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="35d7a-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="35d7a-138">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="35d7a-138">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="35d7a-139">Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа</span><span class="sxs-lookup"><span data-stu-id="35d7a-139">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="35d7a-140">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="35d7a-140">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
