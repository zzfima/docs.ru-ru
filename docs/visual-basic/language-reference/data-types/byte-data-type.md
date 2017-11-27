---
title: "Тип данных Byte (Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6475ff3ed905abb022a9ef60204c04b45130ae22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="894f5-102">Тип данных Byte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="894f5-102">Byte data type (Visual Basic)</span></span>
<span data-ttu-id="894f5-103">Содержит 8-разрядное (1-байтовые) целых чисел без знака, в диапазоне от 0 до 255.</span><span class="sxs-lookup"><span data-stu-id="894f5-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="894f5-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="894f5-104">Remarks</span></span>

<span data-ttu-id="894f5-105">Используйте `Byte` тип данных для хранения двоичных данных.</span><span class="sxs-lookup"><span data-stu-id="894f5-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="894f5-106">Значение по умолчанию для типа `Byte` — 0.</span><span class="sxs-lookup"><span data-stu-id="894f5-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="894f5-107">Литерал назначения</span><span class="sxs-lookup"><span data-stu-id="894f5-107">Literal assignments</span></span>

<span data-ttu-id="894f5-108">Можно объявить и инициализировать `Byte` переменной, назначив его десятичное литералом, Шестнадцатеричный литерал восьмеричного литерала, или (начиная с Visual Basic 2017 г) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="894f5-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="894f5-109">Если целочисленный литерал находится за пределами диапазона `Byte` (то есть, в том случае, если это меньше, чем <xref:System.Byte.MinValue?displayProperty=nameWithType> или больше, чем <xref:System.Byte.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="894f5-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="894f5-110">В следующем примере целых чисел, равные 201, представленное в десятичном, шестнадцатеричном виде, и двоичные литералы производится неявное преобразование из [целое](integer-data-type.md) для `byte` значения.</span><span class="sxs-lookup"><span data-stu-id="894f5-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="894f5-111">Используйте префикс `&h` или `&H` для обозначения Шестнадцатеричный литерал префиксом `&b` или `&B` для обозначения двоичный литерал и префикс `&o` или `&O` для обозначения восьмеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="894f5-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="894f5-112">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="894f5-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="894f5-113">Начиная с Visual Basic 2017 г., можно также использовать знак подчеркивания `_`, как разделитель для повышения удобства чтения, как в следующем примере показано.</span><span class="sxs-lookup"><span data-stu-id="894f5-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

## <a name="programming-tips"></a><span data-ttu-id="894f5-114">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="894f5-114">Programming tips</span></span>

-   <span data-ttu-id="894f5-115">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="894f5-115">**Negative Numbers.**</span></span> <span data-ttu-id="894f5-116">Поскольку `Byte` является тип без знака, он не может представлять отрицательное число.</span><span class="sxs-lookup"><span data-stu-id="894f5-116">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="894f5-117">Если вы используете унарного минуса (`-`) оператор в выражении, вычисляется как тип `Byte`, Visual Basic преобразует выражение, `Short` первой.</span><span class="sxs-lookup"><span data-stu-id="894f5-117">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
-   <span data-ttu-id="894f5-118">**Преобразование форматов.**</span><span class="sxs-lookup"><span data-stu-id="894f5-118">**Format Conversions.**</span></span> <span data-ttu-id="894f5-119">Когда Visual Basic считывает или записывает файлы или вызывает библиотеки DLL, методы и свойства, он автоматически выполняет преобразование между форматами данных.</span><span class="sxs-lookup"><span data-stu-id="894f5-119">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="894f5-120">Двоичные данные, хранящиеся в `Byte` переменных и массивов сохраняется во время преобразования формата.</span><span class="sxs-lookup"><span data-stu-id="894f5-120">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="894f5-121">Не следует использовать `String` переменной для двоичных данных, так как его содержимое может быть повреждено при преобразовании между форматами ANSI и Юникод.</span><span class="sxs-lookup"><span data-stu-id="894f5-121">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

-   <span data-ttu-id="894f5-122">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="894f5-122">**Widening.**</span></span> <span data-ttu-id="894f5-123">`Byte` Тип данных может быть расширен до `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, или `Double`.</span><span class="sxs-lookup"><span data-stu-id="894f5-123">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="894f5-124">Это означает, что можно преобразовать `Byte` на любой из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.</span><span class="sxs-lookup"><span data-stu-id="894f5-124">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
-   <span data-ttu-id="894f5-125">**Символы типов.**</span><span class="sxs-lookup"><span data-stu-id="894f5-125">**Type Characters.**</span></span> <span data-ttu-id="894f5-126">`Byte`не имеет знак типа литерала или знак типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="894f5-126">`Byte` has no literal type character or identifier type character.</span></span>

-   <span data-ttu-id="894f5-127">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="894f5-127">**Framework Type.**</span></span> <span data-ttu-id="894f5-128">В .NET Framework данный тип соответствует структуре <xref:System.Byte?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="894f5-128">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="894f5-129">Пример</span><span class="sxs-lookup"><span data-stu-id="894f5-129">Example</span></span>

 <span data-ttu-id="894f5-130">В следующем примере `b` — `Byte` переменной.</span><span class="sxs-lookup"><span data-stu-id="894f5-130">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="894f5-131">Инструкции показывают диапазон значений переменной и приложение операторы сдвига разряда на него.</span><span class="sxs-lookup"><span data-stu-id="894f5-131">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

[!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/byte-data-type_1.vb)]  

## <a name="see-also"></a><span data-ttu-id="894f5-132">См. также</span><span class="sxs-lookup"><span data-stu-id="894f5-132">See Also</span></span>

 <xref:System.Byte?displayProperty=nameWithType>  
 [<span data-ttu-id="894f5-133">Типы данных</span><span class="sxs-lookup"><span data-stu-id="894f5-133">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="894f5-134">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="894f5-134">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="894f5-135">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="894f5-135">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="894f5-136">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="894f5-136">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
