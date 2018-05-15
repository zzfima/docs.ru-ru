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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 520c21d4df5c340b41a8b1e9055b3fadddfdf6e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ushort-data-type-visual-basic"></a><span data-ttu-id="bcc74-102">Тип данных UShort (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bcc74-102">UShort data type (Visual Basic)</span></span>

<span data-ttu-id="bcc74-103">Содержит 16-разрядное (2-байтовые) целых чисел без знака в диапазоне от 0 до 65 535.</span><span class="sxs-lookup"><span data-stu-id="bcc74-103">Holds unsigned 16-bit (2-byte) integers ranging in value from 0 through 65,535.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcc74-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="bcc74-104">Remarks</span></span>

 <span data-ttu-id="bcc74-105">Используйте `UShort` тип данных для хранения двоичных данных, слишком велик для `Byte`.</span><span class="sxs-lookup"><span data-stu-id="bcc74-105">Use the `UShort` data type to contain binary data too large for `Byte`.</span></span>  
  
 <span data-ttu-id="bcc74-106">Значение по умолчанию для типа `UShort` — 0.</span><span class="sxs-lookup"><span data-stu-id="bcc74-106">The default value of `UShort` is 0.</span></span>  

# <a name="literal-assignments"></a><span data-ttu-id="bcc74-107">Литерал назначения</span><span class="sxs-lookup"><span data-stu-id="bcc74-107">Literal assignments</span></span>

<span data-ttu-id="bcc74-108">Можно объявить и инициализировать `UShort` переменной, назначив его десятичное литералом, Шестнадцатеричный литерал восьмеричного литерала, или (начиная с Visual Basic 2017 г) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="bcc74-108">You can declare and initialize a `UShort` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="bcc74-109">Если целочисленный литерал выходит за пределы диапазона `UShort` (то есть, если он меньше <xref:System.UInt16.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="bcc74-109">If the integer literal is outside the range of `UShort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="bcc74-110">В следующем примере целых чисел, равные 65,034, представленное в десятичном, шестнадцатеричном виде, и двоичные литералы назначены `UShort` значения.</span><span class="sxs-lookup"><span data-stu-id="bcc74-110">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are assigned to `UShort` values.</span></span>
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> <span data-ttu-id="bcc74-111">Используйте префикс `&h` или `&H` для обозначения Шестнадцатеричный литерал префиксом `&b` или `&B` для обозначения двоичный литерал и префикс `&o` или `&O` для обозначения восьмеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="bcc74-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="bcc74-112">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="bcc74-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="bcc74-113">Начиная с Visual Basic 2017 г., можно также использовать знак подчеркивания `_`, как разделитель для повышения удобства чтения, как в следующем примере показано.</span><span class="sxs-lookup"><span data-stu-id="bcc74-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

<span data-ttu-id="bcc74-114">Начиная с Visual Basic 15,5, можно также использовать символ подчеркивания (`_`) в качестве начальных разделителя между префиксом и двоичное, шестнадцатеричное или восьмеричное цифры.</span><span class="sxs-lookup"><span data-stu-id="bcc74-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="bcc74-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="bcc74-115">For example:</span></span>

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="bcc74-116">Можно также включать числовые литералы `US` или `us` [символ типа](../../programming-guide\language-features\data-types/type-characters.md) для обозначения `UShort` тип данных, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bcc74-116">Numeric literals can also include the `US` or `us` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `UShort` data type, as the following example shows.</span></span>

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a><span data-ttu-id="bcc74-117">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="bcc74-117">Programming tips</span></span>
  
-   <span data-ttu-id="bcc74-118">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="bcc74-118">**Negative Numbers.**</span></span> <span data-ttu-id="bcc74-119">Поскольку `UShort` является тип без знака, он не может представлять отрицательное число.</span><span class="sxs-lookup"><span data-stu-id="bcc74-119">Because `UShort` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="bcc74-120">Если вы используете унарного минуса (`-`) оператор в выражении, вычисляется как тип `UShort`, Visual Basic преобразует выражение, `Integer` первой.</span><span class="sxs-lookup"><span data-stu-id="bcc74-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `UShort`, Visual Basic converts the expression to `Integer` first.</span></span>  
  
-   <span data-ttu-id="bcc74-121">**CLS-совместимости.**</span><span class="sxs-lookup"><span data-stu-id="bcc74-121">**CLS Compliance.**</span></span> <span data-ttu-id="bcc74-122">`UShort` Тип данных не является частью [спецификации CLS](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), поэтому CLS-совместимого кода нельзя использовать компонент, который его использует.</span><span class="sxs-lookup"><span data-stu-id="bcc74-122">The `UShort` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
-   <span data-ttu-id="bcc74-123">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="bcc74-123">**Widening.**</span></span> <span data-ttu-id="bcc74-124">`UShort` Тип данных может быть расширен до `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, и `Double`.</span><span class="sxs-lookup"><span data-stu-id="bcc74-124">The `UShort` data type widens to `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="bcc74-125">Это означает, что можно преобразовать `UShort` на любой из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.</span><span class="sxs-lookup"><span data-stu-id="bcc74-125">This means you can convert `UShort` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="bcc74-126">**Символы типов.**</span><span class="sxs-lookup"><span data-stu-id="bcc74-126">**Type Characters.**</span></span> <span data-ttu-id="bcc74-127">Символы типа литерала добавления `US` с литералом приводит к принудительному `UShort` тип данных.</span><span class="sxs-lookup"><span data-stu-id="bcc74-127">Appending the literal type characters `US` to a literal forces it to the `UShort` data type.</span></span> <span data-ttu-id="bcc74-128">`UShort` не имеет типа символа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="bcc74-128">`UShort` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="bcc74-129">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="bcc74-129">**Framework Type.**</span></span> <span data-ttu-id="bcc74-130">В .NET Framework данный тип соответствует структуре <xref:System.UInt16?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bcc74-130">The corresponding type in the .NET Framework is the <xref:System.UInt16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcc74-131">См. также</span><span class="sxs-lookup"><span data-stu-id="bcc74-131">See Also</span></span>  
 <xref:System.UInt16>  
 [<span data-ttu-id="bcc74-132">Типы данных</span><span class="sxs-lookup"><span data-stu-id="bcc74-132">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="bcc74-133">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="bcc74-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="bcc74-134">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="bcc74-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="bcc74-135">Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа</span><span class="sxs-lookup"><span data-stu-id="bcc74-135">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="bcc74-136">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="bcc74-136">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
