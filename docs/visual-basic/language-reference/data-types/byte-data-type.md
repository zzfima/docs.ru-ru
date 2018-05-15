---
title: Тип данных Byte (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28189ab4ab1a9be9265d1cca020039b5302fb5d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="9d499-102">Тип данных Byte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d499-102">Byte data type (Visual Basic)</span></span>
<span data-ttu-id="9d499-103">Содержит 8-разрядное (1-байтовые) целых чисел без знака, в диапазоне от 0 до 255.</span><span class="sxs-lookup"><span data-stu-id="9d499-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="9d499-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="9d499-104">Remarks</span></span>

<span data-ttu-id="9d499-105">Используйте `Byte` тип данных для хранения двоичных данных.</span><span class="sxs-lookup"><span data-stu-id="9d499-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="9d499-106">Значение по умолчанию для типа `Byte` — 0.</span><span class="sxs-lookup"><span data-stu-id="9d499-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="9d499-107">Литерал назначения</span><span class="sxs-lookup"><span data-stu-id="9d499-107">Literal assignments</span></span>

<span data-ttu-id="9d499-108">Можно объявить и инициализировать `Byte` переменной, назначив его десятичное литералом, Шестнадцатеричный литерал восьмеричного литерала, или (начиная с Visual Basic 2017 г) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="9d499-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="9d499-109">Если целочисленный литерал находится за пределами диапазона `Byte` (то есть, в том случае, если это меньше, чем <xref:System.Byte.MinValue?displayProperty=nameWithType> или больше, чем <xref:System.Byte.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="9d499-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="9d499-110">В следующем примере целых чисел, равные 201, представленное в десятичном, шестнадцатеричном виде, и двоичные литералы производится неявное преобразование из [целое](integer-data-type.md) для `byte` значения.</span><span class="sxs-lookup"><span data-stu-id="9d499-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="9d499-111">Используйте префикс `&h` или `&H` для обозначения Шестнадцатеричный литерал префиксом `&b` или `&B` для обозначения двоичный литерал и префикс `&o` или `&O` для обозначения восьмеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="9d499-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="9d499-112">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="9d499-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="9d499-113">Начиная с Visual Basic 2017 г., можно также использовать знак подчеркивания `_`, как разделитель для повышения удобства чтения, как в следующем примере показано.</span><span class="sxs-lookup"><span data-stu-id="9d499-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="9d499-114">Начиная с Visual Basic 15,5, можно также использовать символ подчеркивания (`_`) в качестве начальных разделителя между префиксом и двоичное, шестнадцатеричное или восьмеричное цифры.</span><span class="sxs-lookup"><span data-stu-id="9d499-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="9d499-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="9d499-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="9d499-116">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="9d499-116">Programming tips</span></span>

-   <span data-ttu-id="9d499-117">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="9d499-117">**Negative Numbers.**</span></span> <span data-ttu-id="9d499-118">Поскольку `Byte` является тип без знака, он не может представлять отрицательное число.</span><span class="sxs-lookup"><span data-stu-id="9d499-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="9d499-119">Если вы используете унарного минуса (`-`) оператор в выражении, вычисляется как тип `Byte`, Visual Basic преобразует выражение, `Short` первой.</span><span class="sxs-lookup"><span data-stu-id="9d499-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
-   <span data-ttu-id="9d499-120">**Преобразование форматов.**</span><span class="sxs-lookup"><span data-stu-id="9d499-120">**Format Conversions.**</span></span> <span data-ttu-id="9d499-121">Когда Visual Basic считывает или записывает файлы или вызывает библиотеки DLL, методы и свойства, он автоматически выполняет преобразование между форматами данных.</span><span class="sxs-lookup"><span data-stu-id="9d499-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="9d499-122">Двоичные данные, хранящиеся в `Byte` переменных и массивов сохраняется во время преобразования формата.</span><span class="sxs-lookup"><span data-stu-id="9d499-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="9d499-123">Не следует использовать `String` переменной для двоичных данных, так как его содержимое может быть повреждено при преобразовании между форматами ANSI и Юникод.</span><span class="sxs-lookup"><span data-stu-id="9d499-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

-   <span data-ttu-id="9d499-124">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="9d499-124">**Widening.**</span></span> <span data-ttu-id="9d499-125">`Byte` Тип данных может быть расширен до `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, или `Double`.</span><span class="sxs-lookup"><span data-stu-id="9d499-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="9d499-126">Это означает, что можно преобразовать `Byte` на любой из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.</span><span class="sxs-lookup"><span data-stu-id="9d499-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
-   <span data-ttu-id="9d499-127">**Символы типов.**</span><span class="sxs-lookup"><span data-stu-id="9d499-127">**Type Characters.**</span></span> <span data-ttu-id="9d499-128">`Byte` не имеет знак типа литерала или знак типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="9d499-128">`Byte` has no literal type character or identifier type character.</span></span>

-   <span data-ttu-id="9d499-129">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="9d499-129">**Framework Type.**</span></span> <span data-ttu-id="9d499-130">В .NET Framework данный тип соответствует структуре <xref:System.Byte?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9d499-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="9d499-131">Пример</span><span class="sxs-lookup"><span data-stu-id="9d499-131">Example</span></span>

 <span data-ttu-id="9d499-132">В следующем примере `b` — `Byte` переменной.</span><span class="sxs-lookup"><span data-stu-id="9d499-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="9d499-133">Инструкции показывают диапазон значений переменной и приложение операторы сдвига разряда на него.</span><span class="sxs-lookup"><span data-stu-id="9d499-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

[!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/byte-data-type_1.vb)]  

## <a name="see-also"></a><span data-ttu-id="9d499-134">См. также</span><span class="sxs-lookup"><span data-stu-id="9d499-134">See Also</span></span>

 <xref:System.Byte?displayProperty=nameWithType>  
 [<span data-ttu-id="9d499-135">Типы данных</span><span class="sxs-lookup"><span data-stu-id="9d499-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="9d499-136">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="9d499-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="9d499-137">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="9d499-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="9d499-138">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="9d499-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
