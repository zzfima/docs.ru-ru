---
title: Тип данных Integer
ms.date: 01/31/2018
f1_keywords:
- vb.Integer
- Integer
helpviewer_keywords:
- numbers [Visual Basic], whole
- enumerated values [Visual Basic]
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- literal type characters [Visual Basic], I
- integers [Visual Basic], types
- data types [Visual Basic], integral
- '% identifier type character'
- data types [Visual Basic], assigning
- identifier type characters [Visual Basic], %
- I literal type character [Visual Basic]
- Integer data type
ms.assetid: a8f233b4-4be3-455c-861b-05af2fbb6c60
ms.openlocfilehash: c5b1041b8ef0ca9898a846fea03888537bb4abbf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401349"
---
# <a name="integer-data-type-visual-basic"></a><span data-ttu-id="2d3eb-102">Тип данных Integer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d3eb-102">Integer data type (Visual Basic)</span></span>

<span data-ttu-id="2d3eb-103">Содержит 32-разрядные (4-байтовые) целые числа со знаком в диапазоне от -2 147 483 648 до 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-103">Holds signed 32-bit (4-byte) integers that range in value from -2,147,483,648 through 2,147,483,647.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d3eb-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="2d3eb-104">Remarks</span></span>

 <span data-ttu-id="2d3eb-105">Тип данных `Integer` обеспечивает оптимальную производительность на 32-разрядных процессорах.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-105">The `Integer` data type provides optimal performance on a 32-bit processor.</span></span> <span data-ttu-id="2d3eb-106">Другие целочисленные типы загружаются в память и сохраняются в памяти с более низкой скоростью.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-106">The other integral types are slower to load and store from and to memory.</span></span>  
  
 <span data-ttu-id="2d3eb-107">Значение по умолчанию для типа `Integer` — 0.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-107">The default value of `Integer` is 0.</span></span>  

## <a name="literal-assignments"></a><span data-ttu-id="2d3eb-108">Литературные задания</span><span class="sxs-lookup"><span data-stu-id="2d3eb-108">Literal assignments</span></span>

<span data-ttu-id="2d3eb-109">Вы можете объявить `Integer` и инициализировать переменную, назначив ей десятичную буквальную, гексадецичную буквальную, октальную буквальную или (начиная с Visual Basic 2017) двоичный буквальный.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-109">You can declare and initialize an `Integer` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="2d3eb-110">Если целочисленный литерал выходит за пределы диапазона `Integer` (то есть, если он меньше <xref:System.Int32.MinValue?displayProperty=nameWithType> или больше <xref:System.Int32.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-110">If the integer literal is outside the range of `Integer` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="2d3eb-111">В следующем примере целые числа, равные 90 946 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `Integer`.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-111">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `Integer` values.</span></span>

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Int)]  

> [!NOTE]
> <span data-ttu-id="2d3eb-112">Вы используете `&h` приставку или `&H` для обозначения гексадецимального буквального, приставки `&b` или `&B` для `&o` `&O` обозначения двоичного буквального, и приставки или для обозначения октал буквального.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="2d3eb-113">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="2d3eb-114">Начиная с Visual Basic 2017, вы также `_`можете использовать символ подчеркивания, как цифровой сепаратор для повышения читаемости, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#IntS)]  

<span data-ttu-id="2d3eb-115">Начиная с Visual Basic 15.5, вы также`_`можете использовать символ подчеркивателя ( ) в качестве ведущего сепаратора между приставкой и гексадецичными, бинарными или октальными цифрами.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="2d3eb-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="2d3eb-116">For example:</span></span>

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="2d3eb-117">Число в цифрах может `I` также включать [символ](../../programming-guide/language-features/data-types/type-characters.md) `Integer` типа для обозначения типа данных, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-117">Numeric literals can also include the `I` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Integer` data type, as the following example shows.</span></span>

```vb
Dim number = &H_035826I
```

## <a name="programming-tips"></a><span data-ttu-id="2d3eb-118">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="2d3eb-118">Programming tips</span></span>

- <span data-ttu-id="2d3eb-119">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="2d3eb-119">**Interop Considerations.**</span></span> <span data-ttu-id="2d3eb-120">Если вы взаимосвязаны с компонентами, не записанными для рамочки .NET, такими как объекты Automation или COM, помните, что `Integer` в других средах имеется различная ширина данных (16 битов).</span><span class="sxs-lookup"><span data-stu-id="2d3eb-120">If you are interfacing with components not written for the .NET Framework, such as Automation or COM objects, remember that `Integer` has a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="2d3eb-121">При передаче 16-разрядного аргумента такому компоненту в новом коде Visual Basic следует объявить его как `Short`, а не как `Integer`.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-121">If you are passing a 16-bit argument to such a component, declare it as `Short` instead of `Integer` in your new Visual Basic code.</span></span>  
  
- <span data-ttu-id="2d3eb-122">**Расширение.**</span><span class="sxs-lookup"><span data-stu-id="2d3eb-122">**Widening.**</span></span> <span data-ttu-id="2d3eb-123">Тип данных `Integer` можно расширить до `Long`, `Decimal`, `Single` или `Double`.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-123">The `Integer` data type widens to `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="2d3eb-124">Это означает, что тип `Integer` можно преобразовать в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-124">This means you can convert `Integer` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="2d3eb-125">**Тип символов.**</span><span class="sxs-lookup"><span data-stu-id="2d3eb-125">**Type Characters.**</span></span> <span data-ttu-id="2d3eb-126">При добавлении к литералу символа типа литерала `I` производится принудительное приведение литерала к типу данных `Integer`.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-126">Appending the literal type character `I` to a literal forces it to the `Integer` data type.</span></span> <span data-ttu-id="2d3eb-127">При добавлении символа идентификатора типа `%` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Integer`.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-127">Appending the identifier type character `%` to any identifier forces it to `Integer`.</span></span>  
  
- <span data-ttu-id="2d3eb-128">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="2d3eb-128">**Framework Type.**</span></span> <span data-ttu-id="2d3eb-129">В .NET Framework данный тип соответствует структуре <xref:System.Int32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-129">The corresponding type in the .NET Framework is the <xref:System.Int32?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="range"></a><span data-ttu-id="2d3eb-130">Диапазон</span><span class="sxs-lookup"><span data-stu-id="2d3eb-130">Range</span></span>

<span data-ttu-id="2d3eb-131">При попытке присвоить целочисленной переменной значение, лежащее за пределами диапазона данного типа, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-131">If you try to set a variable of an integral type to a number outside the range for that type, an error occurs.</span></span> <span data-ttu-id="2d3eb-132">При попытке задать дробное значение оно округляется вверх или вниз до ближайшего целого значения.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-132">If you try to set it to a fraction, the number is rounded up or down to the nearest integer value.</span></span> <span data-ttu-id="2d3eb-133">Если число находится точно посередине между двумя целыми числами, значение округляется до ближайшего четного целого.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-133">If the number is equally close to two integer values, the value is rounded to the nearest even integer.</span></span> <span data-ttu-id="2d3eb-134">Такое поведение минимизирует ошибки округления, происходящие от постоянного округления среднего значения в одном направлении.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-134">This behavior minimizes rounding errors that result from consistently rounding a midpoint value in a single direction.</span></span> <span data-ttu-id="2d3eb-135">В следующем коде приведены примеры округления.</span><span class="sxs-lookup"><span data-stu-id="2d3eb-135">The following code shows examples of rounding.</span></span>  

```vb  
' The valid range of an Integer variable is -2147483648 through +2147483647.  
Dim k As Integer  
' The following statement causes an error because the value is too large.  
k = 2147483648  
' The following statement sets k to 6.  
k = 5.9  
' The following statement sets k to 4  
k = 4.5  
' The following statement sets k to 6  
' Note, Visual Basic uses banker’s rounding (toward nearest even number)  
k = 5.5  
```

## <a name="see-also"></a><span data-ttu-id="2d3eb-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2d3eb-136">See also</span></span>

- <xref:System.Int32?displayProperty=nameWithType>
- [<span data-ttu-id="2d3eb-137">Типы данных</span><span class="sxs-lookup"><span data-stu-id="2d3eb-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="2d3eb-138">Тип данных Long</span><span class="sxs-lookup"><span data-stu-id="2d3eb-138">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [<span data-ttu-id="2d3eb-139">Тип данных Short</span><span class="sxs-lookup"><span data-stu-id="2d3eb-139">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="2d3eb-140">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="2d3eb-140">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="2d3eb-141">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="2d3eb-141">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="2d3eb-142">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="2d3eb-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
