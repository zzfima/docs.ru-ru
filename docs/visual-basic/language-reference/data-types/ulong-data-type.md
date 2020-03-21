---
title: Тип данных ULong
ms.date: 01/31/2018
f1_keywords:
- vb.ulong
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- literal type characters [Visual Basic], UL
- ULong data type
- UL literal type characters [Visual Basic]
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
ms.openlocfilehash: 3c6cd4086e08b808c158948756b4806f098196b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401319"
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="269cd-102">ULong тип данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="269cd-102">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="269cd-103">Держит неподписанные 64-разрядные (8-байт) бесых в диапазоне от 0 до 18 446 744 073 709 551 615 (более 1,84 раза 10 и 19).</span><span class="sxs-lookup"><span data-stu-id="269cd-103">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>

## <a name="remarks"></a><span data-ttu-id="269cd-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="269cd-104">Remarks</span></span>

<span data-ttu-id="269cd-105">Используйте `ULong` тип данных для хранения `UInteger`двоичных данных слишком большой для, или максимально возможных неподписанных значения бесчисленности.</span><span class="sxs-lookup"><span data-stu-id="269cd-105">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>

<span data-ttu-id="269cd-106">Значение по умолчанию для типа `ULong` — 0.</span><span class="sxs-lookup"><span data-stu-id="269cd-106">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="269cd-107">Литературные задания</span><span class="sxs-lookup"><span data-stu-id="269cd-107">Literal assignments</span></span>

<span data-ttu-id="269cd-108">Вы можете объявить `ULong` и инициализировать переменную, назначив ей десятичную буквальную, гексадецичную буквальную, октальную буквальную или (начиная с Visual Basic 2017) двоичный буквальный.</span><span class="sxs-lookup"><span data-stu-id="269cd-108">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="269cd-109">Если целочисленный литерал выходит за пределы диапазона `ULong` (то есть, если он меньше <xref:System.UInt64.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="269cd-109">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="269cd-110">В следующем примере целые числа, равные 7 934 076 125 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `ULong`.</span><span class="sxs-lookup"><span data-stu-id="269cd-110">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> <span data-ttu-id="269cd-111">Вы используете `&h` приставку или `&H` для обозначения гексадецимального буквального, приставки `&b` или `&B` для `&o` `&O` обозначения двоичного буквального, и приставки или для обозначения октал буквального.</span><span class="sxs-lookup"><span data-stu-id="269cd-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="269cd-112">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="269cd-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="269cd-113">Начиная с Visual Basic 2017, вы также `_`можете использовать символ подчеркивания, как цифровой сепаратор для повышения читаемости, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="269cd-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="269cd-114">Начиная с Visual Basic 15.5, вы также`_`можете использовать символ подчеркивателя ( ) в качестве ведущего сепаратора между приставкой и гексадецичными, бинарными или октальными цифрами.</span><span class="sxs-lookup"><span data-stu-id="269cd-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="269cd-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="269cd-115">For example:</span></span>

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="269cd-116">Число в перечном виде `UL` `ul` может также включать `ULong` символ или [тип](../../programming-guide/language-features/data-types/type-characters.md) для обозначения типа данных, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="269cd-116">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="269cd-117">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="269cd-117">Programming tips</span></span>

- <span data-ttu-id="269cd-118">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="269cd-118">**Negative Numbers.**</span></span> <span data-ttu-id="269cd-119">Поскольку `ULong` он является неподписанным типом, он не может представлять отрицательное число.</span><span class="sxs-lookup"><span data-stu-id="269cd-119">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="269cd-120">Если вы используете необезыщаемый минус`-` `ULong`() оператора на выражение, которое оценивает вводить, Visual Basic преобразует выражение в `Decimal` первое.</span><span class="sxs-lookup"><span data-stu-id="269cd-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>

- <span data-ttu-id="269cd-121">**Соответствие требованиям CLS.**</span><span class="sxs-lookup"><span data-stu-id="269cd-121">**CLS Compliance.**</span></span> <span data-ttu-id="269cd-122">Тип `ULong` данных не является частью [спецификации общего языка](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), поэтому код, совместимый с CLS, не может потреблять компонент, который его использует.</span><span class="sxs-lookup"><span data-stu-id="269cd-122">The `ULong` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="269cd-123">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="269cd-123">**Interop Considerations.**</span></span> <span data-ttu-id="269cd-124">Если вы взаимосвязаны с компонентами, не записанными для рамочного соглашения .NET, например объектами Automation или COM, имейте в виду, что такие типы, как, `ulong` могут иметь различную ширину данных (32 бита) в других средах.</span><span class="sxs-lookup"><span data-stu-id="269cd-124">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="269cd-125">Если вы передаете 32-битный аргумент такому `UInteger` компоненту, объявите его, а не `ULong` в управляемом коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="269cd-125">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>

  <span data-ttu-id="269cd-126">Кроме того, Automation не поддерживает 64-разрядные пакеты на Windows 95, Windows 98, Windows ME или Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="269cd-126">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="269cd-127">На этих платформах `ULong` невозможно передать элемент Visual Basic компоненту автоматизации.</span><span class="sxs-lookup"><span data-stu-id="269cd-127">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>

- <span data-ttu-id="269cd-128">**Расширение.**</span><span class="sxs-lookup"><span data-stu-id="269cd-128">**Widening.**</span></span> <span data-ttu-id="269cd-129">Тип `ULong` данных расширяется `Single`до `Double` `Decimal`, и .</span><span class="sxs-lookup"><span data-stu-id="269cd-129">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="269cd-130">Это означает, `ULong` что вы можете преобразовать <xref:System.OverflowException?displayProperty=nameWithType> в любой из этих типов, не сталкиваясь с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="269cd-130">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="269cd-131">**Тип символов.**</span><span class="sxs-lookup"><span data-stu-id="269cd-131">**Type Characters.**</span></span> <span data-ttu-id="269cd-132">Придаток символов `UL` буквального типа к буквальному `ULong` заставляет его типа данных.</span><span class="sxs-lookup"><span data-stu-id="269cd-132">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="269cd-133">`ULong`не имеет символа типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="269cd-133">`ULong` has no identifier type character.</span></span>

- <span data-ttu-id="269cd-134">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="269cd-134">**Framework Type.**</span></span> <span data-ttu-id="269cd-135">В .NET Framework данный тип соответствует структуре <xref:System.UInt64?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="269cd-135">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="269cd-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="269cd-136">See also</span></span>

- <xref:System.UInt64>
- [<span data-ttu-id="269cd-137">Типы данных</span><span class="sxs-lookup"><span data-stu-id="269cd-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="269cd-138">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="269cd-138">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="269cd-139">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="269cd-139">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="269cd-140">Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа</span><span class="sxs-lookup"><span data-stu-id="269cd-140">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="269cd-141">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="269cd-141">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
