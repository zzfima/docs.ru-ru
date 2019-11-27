---
title: Тип данных Byte
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 347d7e7d0f09e089886bc81bd0be659deaca9b46
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344082"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="1a17c-102">Тип данных Byte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a17c-102">Byte data type (Visual Basic)</span></span>

<span data-ttu-id="1a17c-103">Содержит 8-битные (1-байтные) целые числа без знака в диапазоне от 0 до 255.</span><span class="sxs-lookup"><span data-stu-id="1a17c-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="1a17c-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="1a17c-104">Remarks</span></span>

<span data-ttu-id="1a17c-105">Используйте `Byte` тип данных для хранения двоичных данных.</span><span class="sxs-lookup"><span data-stu-id="1a17c-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="1a17c-106">Значение по умолчанию для типа `Byte` — 0.</span><span class="sxs-lookup"><span data-stu-id="1a17c-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="1a17c-107">Присваивания литералов</span><span class="sxs-lookup"><span data-stu-id="1a17c-107">Literal assignments</span></span>

<span data-ttu-id="1a17c-108">Можно объявить и инициализировать переменную `Byte`, назначив ей десятичный литерал, шестнадцатеричный литерал, Восьмеричный литерал или (начиная с Visual Basic 2017) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="1a17c-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="1a17c-109">Если целочисленный литерал выходит за пределы диапазона `Byte` (то есть если он меньше <xref:System.Byte.MinValue?displayProperty=nameWithType> или больше <xref:System.Byte.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="1a17c-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="1a17c-110">В следующем примере целые числа, равные 201, представленные в виде десятичного, шестнадцатеричного и двоичного литерала, неявно преобразуются из [целого числа](integer-data-type.md) в `byte` значения.</span><span class="sxs-lookup"><span data-stu-id="1a17c-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="1a17c-111">Префикс `&h` или `&H` можно использовать для обозначения шестнадцатеричного литерала, префикс `&b` или `&B` для обозначения двоичного литерала, а префикс `&o` или `&O` — для обозначения восьмеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="1a17c-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="1a17c-112">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="1a17c-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="1a17c-113">Начиная с Visual Basic 2017 можно также использовать символ подчеркивания `_`в качестве разделителя цифр для повышения удобочитаемости, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1a17c-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="1a17c-114">Начиная с Visual Basic 15,5 можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и шестнадцатеричными, двоичными или восьмеричными цифрами.</span><span class="sxs-lookup"><span data-stu-id="1a17c-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="1a17c-115">Пример.</span><span class="sxs-lookup"><span data-stu-id="1a17c-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="1a17c-116">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="1a17c-116">Programming tips</span></span>

- <span data-ttu-id="1a17c-117">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="1a17c-117">**Negative Numbers.**</span></span> <span data-ttu-id="1a17c-118">Поскольку `Byte` является неподписанным типом, он не может представлять отрицательное число.</span><span class="sxs-lookup"><span data-stu-id="1a17c-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="1a17c-119">При использовании оператора унарного минуса (`-`) в выражении, результатом которого является тип `Byte`, Visual Basic сначала преобразует выражение в `Short`.</span><span class="sxs-lookup"><span data-stu-id="1a17c-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
- <span data-ttu-id="1a17c-120">**Преобразования формата.**</span><span class="sxs-lookup"><span data-stu-id="1a17c-120">**Format Conversions.**</span></span> <span data-ttu-id="1a17c-121">Когда Visual Basic считывает или записывает файлы или вызывает библиотеки DLL, методы и свойства, он может автоматически выполнять преобразование между форматами данных.</span><span class="sxs-lookup"><span data-stu-id="1a17c-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="1a17c-122">Двоичные данные, хранящиеся в переменных `Byte` и массивах, сохраняются во время таких преобразований формата.</span><span class="sxs-lookup"><span data-stu-id="1a17c-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="1a17c-123">Не следует использовать переменную `String` для двоичных данных, так как ее содержимое может быть повреждено во время преобразования между форматами ANSI и Юникод.</span><span class="sxs-lookup"><span data-stu-id="1a17c-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

- <span data-ttu-id="1a17c-124">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="1a17c-124">**Widening.**</span></span> <span data-ttu-id="1a17c-125">Тип данных `Byte` расширяется на `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`или `Double`.</span><span class="sxs-lookup"><span data-stu-id="1a17c-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="1a17c-126">Это означает, что можно преобразовать `Byte` в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1a17c-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
- <span data-ttu-id="1a17c-127">**Символы типа.**</span><span class="sxs-lookup"><span data-stu-id="1a17c-127">**Type Characters.**</span></span> <span data-ttu-id="1a17c-128">`Byte` не имеет символа типа литерала или символа типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="1a17c-128">`Byte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="1a17c-129">**Тип платформы.**</span><span class="sxs-lookup"><span data-stu-id="1a17c-129">**Framework Type.**</span></span> <span data-ttu-id="1a17c-130">В .NET Framework данный тип соответствует структуре <xref:System.Byte?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1a17c-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="1a17c-131">Пример</span><span class="sxs-lookup"><span data-stu-id="1a17c-131">Example</span></span>

 <span data-ttu-id="1a17c-132">В следующем примере `b` является переменной `Byte`.</span><span class="sxs-lookup"><span data-stu-id="1a17c-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="1a17c-133">Инструкции демонстрируют диапазон переменных и применение к нему операторов побитового сдвига.</span><span class="sxs-lookup"><span data-stu-id="1a17c-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a><span data-ttu-id="1a17c-134">См. также</span><span class="sxs-lookup"><span data-stu-id="1a17c-134">See also</span></span>

- <xref:System.Byte?displayProperty=nameWithType>
- [<span data-ttu-id="1a17c-135">Типы данных</span><span class="sxs-lookup"><span data-stu-id="1a17c-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="1a17c-136">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="1a17c-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="1a17c-137">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="1a17c-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="1a17c-138">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="1a17c-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
