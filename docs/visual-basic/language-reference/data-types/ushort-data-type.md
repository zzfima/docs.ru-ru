---
title: Тип данных UShort
ms.date: 01/31/2018
f1_keywords:
- vb.ushort
helpviewer_keywords:
- numbers [Visual Basic], whole
- literal type characters [Visual Basic], US
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- UShort data type
- US literal type characters [Visual Basic]
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
ms.openlocfilehash: 7cdbd5fb192fd5cc1be6260dcdcdb1f30cf3f865
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401313"
---
# <a name="ushort-data-type-visual-basic"></a><span data-ttu-id="39f00-102">Тип данных UShort (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39f00-102">UShort data type (Visual Basic)</span></span>

<span data-ttu-id="39f00-103">Держит неподписанные 16-битные (2-байт) многоразовые значения от 0 до 65 535.</span><span class="sxs-lookup"><span data-stu-id="39f00-103">Holds unsigned 16-bit (2-byte) integers ranging in value from 0 through 65,535.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39f00-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="39f00-104">Remarks</span></span>

 <span data-ttu-id="39f00-105">Используйте `UShort` тип данных для хранения `Byte`двоичных данных слишком большой для.</span><span class="sxs-lookup"><span data-stu-id="39f00-105">Use the `UShort` data type to contain binary data too large for `Byte`.</span></span>  
  
 <span data-ttu-id="39f00-106">Значение по умолчанию для типа `UShort` — 0.</span><span class="sxs-lookup"><span data-stu-id="39f00-106">The default value of `UShort` is 0.</span></span>  

## <a name="literal-assignments"></a><span data-ttu-id="39f00-107">Литературные задания</span><span class="sxs-lookup"><span data-stu-id="39f00-107">Literal assignments</span></span>

<span data-ttu-id="39f00-108">Вы можете объявить `UShort` и инициализировать переменную, назначив ей десятичную буквальную, гексадецичную буквальную, октальную буквальную или (начиная с Visual Basic 2017) двоичный буквальный.</span><span class="sxs-lookup"><span data-stu-id="39f00-108">You can declare and initialize a `UShort` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="39f00-109">Если целочисленный литерал выходит за пределы диапазона `UShort` (то есть, если он меньше <xref:System.UInt16.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="39f00-109">If the integer literal is outside the range of `UShort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="39f00-110">В следующем примере значениям присваиваются `UShort` целые 65 034, которые представлены как десятичные, гексадекемальные и бинарные буквы.</span><span class="sxs-lookup"><span data-stu-id="39f00-110">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are assigned to `UShort` values.</span></span>
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> <span data-ttu-id="39f00-111">Вы используете `&h` приставку или `&H` для обозначения гексадецимального буквального, приставки `&b` или `&B` для `&o` `&O` обозначения двоичного буквального, и приставки или для обозначения октал буквального.</span><span class="sxs-lookup"><span data-stu-id="39f00-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="39f00-112">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="39f00-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="39f00-113">Начиная с Visual Basic 2017, вы также `_`можете использовать символ подчеркивания, как цифровой сепаратор для повышения читаемости, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="39f00-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

<span data-ttu-id="39f00-114">Начиная с Visual Basic 15.5, вы также`_`можете использовать символ подчеркивателя ( ) в качестве ведущего сепаратора между приставкой и гексадецичными, бинарными или октальными цифрами.</span><span class="sxs-lookup"><span data-stu-id="39f00-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="39f00-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="39f00-115">For example:</span></span>

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="39f00-116">Число в перечном виде `US` `us` может также включать `UShort` символ или [тип](../../programming-guide/language-features/data-types/type-characters.md) для обозначения типа данных, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="39f00-116">Numeric literals can also include the `US` or `us` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UShort` data type, as the following example shows.</span></span>

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a><span data-ttu-id="39f00-117">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="39f00-117">Programming tips</span></span>
  
- <span data-ttu-id="39f00-118">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="39f00-118">**Negative Numbers.**</span></span> <span data-ttu-id="39f00-119">Поскольку `UShort` он является неподписанным типом, он не может представлять отрицательное число.</span><span class="sxs-lookup"><span data-stu-id="39f00-119">Because `UShort` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="39f00-120">Если вы используете необезыщаемый минус`-` `UShort`() оператора на выражение, которое оценивает вводить, Visual Basic преобразует выражение в `Integer` первое.</span><span class="sxs-lookup"><span data-stu-id="39f00-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `UShort`, Visual Basic converts the expression to `Integer` first.</span></span>  
  
- <span data-ttu-id="39f00-121">**Соответствие требованиям CLS.**</span><span class="sxs-lookup"><span data-stu-id="39f00-121">**CLS Compliance.**</span></span> <span data-ttu-id="39f00-122">Тип `UShort` данных не является частью [спецификации общего языка](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), поэтому код, совместимый с CLS, не может потреблять компонент, который его использует.</span><span class="sxs-lookup"><span data-stu-id="39f00-122">The `UShort` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
- <span data-ttu-id="39f00-123">**Расширение.**</span><span class="sxs-lookup"><span data-stu-id="39f00-123">**Widening.**</span></span> <span data-ttu-id="39f00-124">Тип `UShort` данных расширяется `UInteger` `Long`до `ULong` `Integer` `Decimal`, `Single`, `Double`, , и .</span><span class="sxs-lookup"><span data-stu-id="39f00-124">The `UShort` data type widens to `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="39f00-125">Это означает, `UShort` что вы можете преобразовать <xref:System.OverflowException?displayProperty=nameWithType> в любой из этих типов, не сталкиваясь с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="39f00-125">This means you can convert `UShort` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="39f00-126">**Тип символов.**</span><span class="sxs-lookup"><span data-stu-id="39f00-126">**Type Characters.**</span></span> <span data-ttu-id="39f00-127">Придаток символов `US` буквального типа к буквальному `UShort` заставляет его типа данных.</span><span class="sxs-lookup"><span data-stu-id="39f00-127">Appending the literal type characters `US` to a literal forces it to the `UShort` data type.</span></span> <span data-ttu-id="39f00-128">`UShort`не имеет символа типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="39f00-128">`UShort` has no identifier type character.</span></span>  
  
- <span data-ttu-id="39f00-129">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="39f00-129">**Framework Type.**</span></span> <span data-ttu-id="39f00-130">В .NET Framework данный тип соответствует структуре <xref:System.UInt16?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="39f00-130">The corresponding type in the .NET Framework is the <xref:System.UInt16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39f00-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="39f00-131">See also</span></span>

- <xref:System.UInt16>
- [<span data-ttu-id="39f00-132">Типы данных</span><span class="sxs-lookup"><span data-stu-id="39f00-132">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="39f00-133">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="39f00-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="39f00-134">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="39f00-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="39f00-135">Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа</span><span class="sxs-lookup"><span data-stu-id="39f00-135">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="39f00-136">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="39f00-136">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
