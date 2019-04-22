---
title: Тип данных UShort (Visual Basic)
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
ms.openlocfilehash: 8845a6bde4e1a701b5420029788259724cd0f8d9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58829958"
---
# <a name="ushort-data-type-visual-basic"></a><span data-ttu-id="0e849-102">Тип данных UShort (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e849-102">UShort data type (Visual Basic)</span></span>

<span data-ttu-id="0e849-103">Содержит 16-разрядное (2-байтовое) целых чисел без знака в диапазоне от 0 до 65 535.</span><span class="sxs-lookup"><span data-stu-id="0e849-103">Holds unsigned 16-bit (2-byte) integers ranging in value from 0 through 65,535.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e849-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="0e849-104">Remarks</span></span>

 <span data-ttu-id="0e849-105">Используйте `UShort` тип данных для хранения двоичных данных, слишком велик для `Byte`.</span><span class="sxs-lookup"><span data-stu-id="0e849-105">Use the `UShort` data type to contain binary data too large for `Byte`.</span></span>  
  
 <span data-ttu-id="0e849-106">Значение по умолчанию для типа `UShort` — 0.</span><span class="sxs-lookup"><span data-stu-id="0e849-106">The default value of `UShort` is 0.</span></span>  

## <a name="literal-assignments"></a><span data-ttu-id="0e849-107">Назначения литералов</span><span class="sxs-lookup"><span data-stu-id="0e849-107">Literal assignments</span></span>

<span data-ttu-id="0e849-108">Можно объявить и инициализировать `UShort` переменной, назначив ей десятичный литерал, шестнадцатеричный восьмеричный литерал, или (начиная с Visual Basic 2017) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="0e849-108">You can declare and initialize a `UShort` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="0e849-109">Если целочисленный литерал выходит за пределы диапазона `UShort` (то есть, если он меньше <xref:System.UInt16.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="0e849-109">If the integer literal is outside the range of `UShort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="0e849-110">В следующем примере целые числа, равные 65 034 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются `UShort` значения.</span><span class="sxs-lookup"><span data-stu-id="0e849-110">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are assigned to `UShort` values.</span></span>
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> <span data-ttu-id="0e849-111">Используйте префикс `&h` или `&H` для обозначения шестнадцатеричного литерала, префикс `&b` или `&B` для обозначения двоичного литерала, а также префикс `&o` или `&O` для обозначения восьмеричный литерал.</span><span class="sxs-lookup"><span data-stu-id="0e849-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="0e849-112">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="0e849-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="0e849-113">Начиная с Visual Basic 2017, можно также использовать символ подчеркивания, `_`, в качестве разделителя разрядов для повышения удобства чтения, как в примере ниже показан.</span><span class="sxs-lookup"><span data-stu-id="0e849-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

<span data-ttu-id="0e849-114">Начиная с Visual Basic 15.5, можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и двоичное, шестнадцатеричное или восьмеричное цифры.</span><span class="sxs-lookup"><span data-stu-id="0e849-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="0e849-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="0e849-115">For example:</span></span>

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="0e849-116">Числовые литералы могут содержать `US` или `us` [символ типа](../../programming-guide/language-features/data-types/type-characters.md) для обозначения `UShort` тип данных, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0e849-116">Numeric literals can also include the `US` or `us` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UShort` data type, as the following example shows.</span></span>

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a><span data-ttu-id="0e849-117">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="0e849-117">Programming tips</span></span>
  
-   <span data-ttu-id="0e849-118">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="0e849-118">**Negative Numbers.**</span></span> <span data-ttu-id="0e849-119">Так как `UShort` — это тип без знака, он не может представлять отрицательное число.</span><span class="sxs-lookup"><span data-stu-id="0e849-119">Because `UShort` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="0e849-120">При использовании унарного минуса (`-`) оператор на выражение, результатом вычисления которого введите `UShort`, Visual Basic преобразует выражение `Integer` первого.</span><span class="sxs-lookup"><span data-stu-id="0e849-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `UShort`, Visual Basic converts the expression to `Integer` first.</span></span>  
  
-   <span data-ttu-id="0e849-121">**CLS-совместимость.**</span><span class="sxs-lookup"><span data-stu-id="0e849-121">**CLS Compliance.**</span></span> <span data-ttu-id="0e849-122">`UShort` Тип данных не является частью [спецификация CLS](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), поэтому CLS-совместимого кода нельзя использовать компонент, который его использует.</span><span class="sxs-lookup"><span data-stu-id="0e849-122">The `UShort` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
-   <span data-ttu-id="0e849-123">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="0e849-123">**Widening.**</span></span> <span data-ttu-id="0e849-124">`UShort` Тип данных можно расширить до `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, и `Double`.</span><span class="sxs-lookup"><span data-stu-id="0e849-124">The `UShort` data type widens to `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="0e849-125">Это означает, что вы можете преобразовать `UShort` к любому из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.</span><span class="sxs-lookup"><span data-stu-id="0e849-125">This means you can convert `UShort` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="0e849-126">**Символы типа.**</span><span class="sxs-lookup"><span data-stu-id="0e849-126">**Type Characters.**</span></span> <span data-ttu-id="0e849-127">Добавление символы типа литерала `US` в литерал приводит к принудительному `UShort` тип данных.</span><span class="sxs-lookup"><span data-stu-id="0e849-127">Appending the literal type characters `US` to a literal forces it to the `UShort` data type.</span></span> <span data-ttu-id="0e849-128">`UShort` не имеет тип символа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="0e849-128">`UShort` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="0e849-129">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="0e849-129">**Framework Type.**</span></span> <span data-ttu-id="0e849-130">В .NET Framework данный тип соответствует структуре <xref:System.UInt16?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0e849-130">The corresponding type in the .NET Framework is the <xref:System.UInt16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e849-131">См. также</span><span class="sxs-lookup"><span data-stu-id="0e849-131">See also</span></span>

- <xref:System.UInt16>
- [<span data-ttu-id="0e849-132">Типы данных</span><span class="sxs-lookup"><span data-stu-id="0e849-132">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="0e849-133">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="0e849-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="0e849-134">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="0e849-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="0e849-135">Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа</span><span class="sxs-lookup"><span data-stu-id="0e849-135">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="0e849-136">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="0e849-136">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
