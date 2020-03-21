---
title: Тип данных SByte
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
ms.openlocfilehash: 01a0a4a261213d7e6e2016bf49128092e5b22308
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401385"
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="0687b-102">Тип данных SByte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0687b-102">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="0687b-103">Держит подписанные 8-битные (1-байт) целые столбы, которые варьируются в цене от -128 до 127.</span><span class="sxs-lookup"><span data-stu-id="0687b-103">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>

## <a name="remarks"></a><span data-ttu-id="0687b-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="0687b-104">Remarks</span></span>

<span data-ttu-id="0687b-105">Используйте `SByte` тип данных, чтобы содержать целые значения, которые `Integer` не требуют полной `Short`ширины данных или даже половины ширины данных.</span><span class="sxs-lookup"><span data-stu-id="0687b-105">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="0687b-106">В некоторых случаях время выполнения общего языка `SByte` может быть в состоянии упаковать переменные близко друг к другу и сохранить потребление памяти.</span><span class="sxs-lookup"><span data-stu-id="0687b-106">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="0687b-107">Значение по умолчанию для типа `SByte` — 0.</span><span class="sxs-lookup"><span data-stu-id="0687b-107">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="0687b-108">Литературные задания</span><span class="sxs-lookup"><span data-stu-id="0687b-108">Literal assignments</span></span>

<span data-ttu-id="0687b-109">Вы можете объявить `SByte` и инициализировать переменную, назначив ей десятичную буквальную, гексадецичную буквальную, октальную буквальную или (начиная с Visual Basic 2017) двоичный буквальный.</span><span class="sxs-lookup"><span data-stu-id="0687b-109">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="0687b-110">В следующем примере значениям присваиваются `SByte` целые столбы, равные -102, которые представлены как десятичные, гексадецимальные и бинарные буквальные значения.</span><span class="sxs-lookup"><span data-stu-id="0687b-110">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="0687b-111">Этот пример требует компиляции с коммутатором компилятора. `/removeintchecks`</span><span class="sxs-lookup"><span data-stu-id="0687b-111">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> <span data-ttu-id="0687b-112">Вы используете `&h` приставку или `&H` для обозначения гексадецимального буквального, приставки `&b` или `&B` для `&o` `&O` обозначения двоичного буквального, и приставки или для обозначения октал буквального.</span><span class="sxs-lookup"><span data-stu-id="0687b-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="0687b-113">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="0687b-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="0687b-114">Начиная с Visual Basic 2017, вы также `_`можете использовать символ подчеркивания, как цифровой сепаратор для повышения читаемости, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0687b-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

<span data-ttu-id="0687b-115">Начиная с Visual Basic 15.5, вы также`_`можете использовать символ подчеркивателя ( ) в качестве ведущего сепаратора между приставкой и гексадецичными, бинарными или октальными цифрами.</span><span class="sxs-lookup"><span data-stu-id="0687b-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="0687b-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="0687b-116">For example:</span></span>

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="0687b-117">Если целочисленный литерал выходит за пределы диапазона `SByte` (то есть, если он меньше <xref:System.SByte.MinValue?displayProperty=nameWithType> или больше <xref:System.SByte.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="0687b-117">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="0687b-118">Когда в буквальном смысле нет суффикса, выводит [integer.](integer-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="0687b-118">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="0687b-119">Если целый буквальный находится за пределами диапазона `Integer` типа, [Лонг](long-data-type.md) выводит.</span><span class="sxs-lookup"><span data-stu-id="0687b-119">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="0687b-120">Это означает, что в предыдущих примерах, `0x9A` `0b10011010` числовы и интерпретируются как 32-битные подписанные целые числа со значением 156, что превышает <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0687b-120">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0687b-121">Для успешной компиляции кода, как это, что присваивает не-десятичной целый `SByte`ряд, вы можете сделать любой из следующих:</span><span class="sxs-lookup"><span data-stu-id="0687b-121">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="0687b-122">Отключение рядовых границ проверяется путем `/removeintchecks` компиляции с компилятором.</span><span class="sxs-lookup"><span data-stu-id="0687b-122">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="0687b-123">Используйте [символ типа,](../../programming-guide/language-features/data-types/type-characters.md) чтобы точно определить буквальное значение, `SByte`которое вы хотите присвоить .</span><span class="sxs-lookup"><span data-stu-id="0687b-123">Use a [type character](../../programming-guide/language-features/data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="0687b-124">Следующий пример присваивает отрицательное буквальное `Short` значение . `SByte`</span><span class="sxs-lookup"><span data-stu-id="0687b-124">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="0687b-125">Обратите внимание, что для отрицательных чисел необходимо установить бит высокого порядка слова в цифровом букве.</span><span class="sxs-lookup"><span data-stu-id="0687b-125">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="0687b-126">В случае нашего примера, это бит 15 `Short` буквального значения.</span><span class="sxs-lookup"><span data-stu-id="0687b-126">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="0687b-127">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="0687b-127">Programming tips</span></span>

- <span data-ttu-id="0687b-128">**Соответствие требованиям CLS.**</span><span class="sxs-lookup"><span data-stu-id="0687b-128">**CLS Compliance.**</span></span> <span data-ttu-id="0687b-129">Тип `SByte` данных не является частью [спецификации общего языка](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), поэтому код, совместимый с CLS, не может потреблять компонент, который его использует.</span><span class="sxs-lookup"><span data-stu-id="0687b-129">The `SByte` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="0687b-130">**Расширение.**</span><span class="sxs-lookup"><span data-stu-id="0687b-130">**Widening.**</span></span> <span data-ttu-id="0687b-131">Тип `SByte` данных расширяется `Integer` `Long`до `Decimal` `Short` `Single`, `Double`, , и .</span><span class="sxs-lookup"><span data-stu-id="0687b-131">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="0687b-132">Это означает, `SByte` что вы можете преобразовать <xref:System.OverflowException?displayProperty=nameWithType> в любой из этих типов, не сталкиваясь с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="0687b-132">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="0687b-133">**Тип символов.**</span><span class="sxs-lookup"><span data-stu-id="0687b-133">**Type Characters.**</span></span> <span data-ttu-id="0687b-134">`SByte`не имеет буквального символа типа или символа типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="0687b-134">`SByte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="0687b-135">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="0687b-135">**Framework Type.**</span></span> <span data-ttu-id="0687b-136">В .NET Framework данный тип соответствует структуре <xref:System.SByte?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0687b-136">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="0687b-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0687b-137">See also</span></span>

- <xref:System.SByte?displayProperty=nameWithType>
- [<span data-ttu-id="0687b-138">Типы данных</span><span class="sxs-lookup"><span data-stu-id="0687b-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="0687b-139">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="0687b-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="0687b-140">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="0687b-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="0687b-141">Тип данных Short</span><span class="sxs-lookup"><span data-stu-id="0687b-141">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="0687b-142">Тип данных негров</span><span class="sxs-lookup"><span data-stu-id="0687b-142">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="0687b-143">Тип данных Long</span><span class="sxs-lookup"><span data-stu-id="0687b-143">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [<span data-ttu-id="0687b-144">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="0687b-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
