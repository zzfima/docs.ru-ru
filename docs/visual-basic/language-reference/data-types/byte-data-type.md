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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401355"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="ca46e-102">Тип данных Байта (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca46e-102">Byte data type (Visual Basic)</span></span>

<span data-ttu-id="ca46e-103">Держит неподписанные 8-битные (1-байт) целые столбики, которые варьируются в значении от 0 до 255.</span><span class="sxs-lookup"><span data-stu-id="ca46e-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="ca46e-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="ca46e-104">Remarks</span></span>

<span data-ttu-id="ca46e-105">Используйте `Byte` тип данных для хранения двоичных данных.</span><span class="sxs-lookup"><span data-stu-id="ca46e-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="ca46e-106">Значение по умолчанию для типа `Byte` — 0.</span><span class="sxs-lookup"><span data-stu-id="ca46e-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="ca46e-107">Литературные задания</span><span class="sxs-lookup"><span data-stu-id="ca46e-107">Literal assignments</span></span>

<span data-ttu-id="ca46e-108">Вы можете объявить `Byte` и инициализировать переменную, назначив ей десятичную буквальную, гексадецичную буквальную, октальную буквальную или (начиная с Visual Basic 2017) двоичный буквальный.</span><span class="sxs-lookup"><span data-stu-id="ca46e-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="ca46e-109">Если интегральный буквальный находится за `Byte` пределами диапазона (т.е. если он меньше <xref:System.Byte.MinValue?displayProperty=nameWithType> или <xref:System.Byte.MaxValue?displayProperty=nameWithType>больше), происходит ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="ca46e-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="ca46e-110">В следующем примере целые штаты, равные 201, которые представлены как десятичные, гексадецимальные и `byte` двоичные буквальные, неявно преобразуются из [Integer](integer-data-type.md) в значения.</span><span class="sxs-lookup"><span data-stu-id="ca46e-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="ca46e-111">Вы используете `&h` приставку или `&H` для обозначения гексадецимального буквального, приставки `&b` или `&B` для `&o` `&O` обозначения двоичного буквального, и приставки или для обозначения октал буквального.</span><span class="sxs-lookup"><span data-stu-id="ca46e-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="ca46e-112">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="ca46e-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="ca46e-113">Начиная с Visual Basic 2017, вы также `_`можете использовать символ подчеркивания, как цифровой сепаратор для повышения читаемости, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ca46e-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="ca46e-114">Начиная с Visual Basic 15.5, вы также`_`можете использовать символ подчеркивателя ( ) в качестве ведущего сепаратора между приставкой и гексадецичными, бинарными или октальными цифрами.</span><span class="sxs-lookup"><span data-stu-id="ca46e-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="ca46e-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="ca46e-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="ca46e-116">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="ca46e-116">Programming tips</span></span>

- <span data-ttu-id="ca46e-117">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="ca46e-117">**Negative Numbers.**</span></span> <span data-ttu-id="ca46e-118">Поскольку `Byte` он является неподписанным типом, он не может представлять отрицательное число.</span><span class="sxs-lookup"><span data-stu-id="ca46e-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="ca46e-119">Если вы используете необезыщаемый минус`-` `Byte`() оператора на выражение, которое оценивает вводить, Visual Basic преобразует выражение в `Short` первое.</span><span class="sxs-lookup"><span data-stu-id="ca46e-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
- <span data-ttu-id="ca46e-120">**Преобразование формата.**</span><span class="sxs-lookup"><span data-stu-id="ca46e-120">**Format Conversions.**</span></span> <span data-ttu-id="ca46e-121">Когда Visual Basic читает или пишет файлы, или когда он вызывает DLLs, методы и свойства, он может автоматически конвертировать между форматами данных.</span><span class="sxs-lookup"><span data-stu-id="ca46e-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="ca46e-122">Двоичные `Byte` данные, хранящиеся в переменных и массивах, сохраняются во время таких преобразований формата.</span><span class="sxs-lookup"><span data-stu-id="ca46e-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="ca46e-123">Не следует использовать `String` переменную для двоичных данных, так как ее содержимое может быть повреждено при преобразовании между форматами ANSI и Unicode.</span><span class="sxs-lookup"><span data-stu-id="ca46e-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

- <span data-ttu-id="ca46e-124">**Расширение.**</span><span class="sxs-lookup"><span data-stu-id="ca46e-124">**Widening.**</span></span> <span data-ttu-id="ca46e-125">Тип `Byte` данных расширяется `UShort` `Integer`до `UInteger` `Short`, `ULong` `Decimal`, `Single`, `Double` `Long`, , , или .</span><span class="sxs-lookup"><span data-stu-id="ca46e-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="ca46e-126">Это означает, `Byte` что вы можете преобразовать <xref:System.OverflowException?displayProperty=nameWithType> в любой из этих типов, не сталкиваясь с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ca46e-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
- <span data-ttu-id="ca46e-127">**Тип символов.**</span><span class="sxs-lookup"><span data-stu-id="ca46e-127">**Type Characters.**</span></span> <span data-ttu-id="ca46e-128">`Byte`не имеет буквального символа типа или символа типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="ca46e-128">`Byte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="ca46e-129">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="ca46e-129">**Framework Type.**</span></span> <span data-ttu-id="ca46e-130">В .NET Framework данный тип соответствует структуре <xref:System.Byte?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ca46e-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="ca46e-131">Пример</span><span class="sxs-lookup"><span data-stu-id="ca46e-131">Example</span></span>

 <span data-ttu-id="ca46e-132">В следующем примере `b` `Byte` является переменной.</span><span class="sxs-lookup"><span data-stu-id="ca46e-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="ca46e-133">Заявления демонстрируют диапазон переменной и применение к ней операторов бит-сдвига.</span><span class="sxs-lookup"><span data-stu-id="ca46e-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a><span data-ttu-id="ca46e-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ca46e-134">See also</span></span>

- <xref:System.Byte?displayProperty=nameWithType>
- [<span data-ttu-id="ca46e-135">Типы данных</span><span class="sxs-lookup"><span data-stu-id="ca46e-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="ca46e-136">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="ca46e-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="ca46e-137">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="ca46e-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="ca46e-138">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="ca46e-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
