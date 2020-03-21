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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401403"
---
# <a name="long-data-type-visual-basic"></a><span data-ttu-id="06ff9-102">Длинный тип данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06ff9-102">Long data type (Visual Basic)</span></span>

<span data-ttu-id="06ff9-103">Держит подписанный 64-битный (8-байт) integers колеи в диапазоне от -9,223,372,036,854,775,808 до 9,223,372,036,854,775,807 (9.2...E-18).</span><span class="sxs-lookup"><span data-stu-id="06ff9-103">Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).</span></span>

## <a name="remarks"></a><span data-ttu-id="06ff9-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="06ff9-104">Remarks</span></span>

<span data-ttu-id="06ff9-105">Используйте `Long` тип данных, чтобы содержать несколько чисел, которые слишком велики, чтобы поместиться в тип `Integer` данных.</span><span class="sxs-lookup"><span data-stu-id="06ff9-105">Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.</span></span>

<span data-ttu-id="06ff9-106">Значение по умолчанию для типа `Long` — 0.</span><span class="sxs-lookup"><span data-stu-id="06ff9-106">The default value of `Long` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="06ff9-107">Литературные задания</span><span class="sxs-lookup"><span data-stu-id="06ff9-107">Literal assignments</span></span>

<span data-ttu-id="06ff9-108">Вы можете объявить `Long` и инициализировать переменную, назначив ей десятичную буквальную, гексадецичную буквальную, октальную буквальную или (начиная с Visual Basic 2017) двоичный буквальный.</span><span class="sxs-lookup"><span data-stu-id="06ff9-108">You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="06ff9-109">Если целочисленный литерал выходит за пределы диапазона `Long` (то есть, если он меньше <xref:System.Int64.MinValue?displayProperty=nameWithType> или больше <xref:System.Int64.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="06ff9-109">If the integer literal is outside the range of `Long` (that is, if it is less than <xref:System.Int64.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="06ff9-110">В следующем примере целые числа, равные 4 294 967 296 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `Long`.</span><span class="sxs-lookup"><span data-stu-id="06ff9-110">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `Long` values.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> <span data-ttu-id="06ff9-111">Вы используете `&h` приставку или `&H` для обозначения гексадецимального буквального, приставки `&b` или `&B` для `&o` `&O` обозначения двоичного буквального, и приставки или для обозначения октал буквального.</span><span class="sxs-lookup"><span data-stu-id="06ff9-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="06ff9-112">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="06ff9-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="06ff9-113">Начиная с Visual Basic 2017, вы также `_`можете использовать символ подчеркивания, как цифровой сепаратор для повышения читаемости, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="06ff9-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="06ff9-114">Начиная с Visual Basic 15.5, вы также`_`можете использовать символ подчеркивателя ( ) в качестве ведущего сепаратора между приставкой и гексадецичными, бинарными или октальными цифрами.</span><span class="sxs-lookup"><span data-stu-id="06ff9-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="06ff9-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="06ff9-115">For example:</span></span>

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="06ff9-116">Число в цифрах может `L` также включать [символ](../../programming-guide/language-features/data-types/type-characters.md) `Long` типа для обозначения типа данных, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="06ff9-116">Numeric literals can also include the `L` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Long` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a><span data-ttu-id="06ff9-117">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="06ff9-117">Programming tips</span></span>

- <span data-ttu-id="06ff9-118">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="06ff9-118">**Interop Considerations.**</span></span> <span data-ttu-id="06ff9-119">Если вы взаимосвязаны с компонентами, не записанными для рамочного .NET, например объектами Automation или COM, помните, что `Long` в других средах имеется другая ширина данных (32 бита).</span><span class="sxs-lookup"><span data-stu-id="06ff9-119">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="06ff9-120">Если вы передаете 32-битный аргумент такому `Integer` компоненту, объявите его вместо вашего `Long` нового кода Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="06ff9-120">If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.</span></span>

- <span data-ttu-id="06ff9-121">**Расширение.**</span><span class="sxs-lookup"><span data-stu-id="06ff9-121">**Widening.**</span></span> <span data-ttu-id="06ff9-122">Тип `Long` данных расширяется `Single`до `Double` `Decimal`, или .</span><span class="sxs-lookup"><span data-stu-id="06ff9-122">The `Long` data type widens to `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="06ff9-123">Это означает, что тип `Long` можно преобразовать в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="06ff9-123">This means you can convert `Long` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="06ff9-124">**Тип символов.**</span><span class="sxs-lookup"><span data-stu-id="06ff9-124">**Type Characters.**</span></span> <span data-ttu-id="06ff9-125">При добавлении к литералу символа типа литерала `L` производится принудительное приведение литерала к типу данных `Long`.</span><span class="sxs-lookup"><span data-stu-id="06ff9-125">Appending the literal type character `L` to a literal forces it to the `Long` data type.</span></span> <span data-ttu-id="06ff9-126">При добавлении символа идентификатора типа `&` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Long`.</span><span class="sxs-lookup"><span data-stu-id="06ff9-126">Appending the identifier type character `&` to any identifier forces it to `Long`.</span></span>

- <span data-ttu-id="06ff9-127">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="06ff9-127">**Framework Type.**</span></span> <span data-ttu-id="06ff9-128">В .NET Framework данный тип соответствует структуре <xref:System.Int64?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="06ff9-128">The corresponding type in the .NET Framework is the <xref:System.Int64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="06ff9-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="06ff9-129">See also</span></span>

- <xref:System.Int64>
- [<span data-ttu-id="06ff9-130">Типы данных</span><span class="sxs-lookup"><span data-stu-id="06ff9-130">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="06ff9-131">Тип данных негров</span><span class="sxs-lookup"><span data-stu-id="06ff9-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="06ff9-132">Тип данных Short</span><span class="sxs-lookup"><span data-stu-id="06ff9-132">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="06ff9-133">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="06ff9-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="06ff9-134">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="06ff9-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="06ff9-135">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="06ff9-135">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
