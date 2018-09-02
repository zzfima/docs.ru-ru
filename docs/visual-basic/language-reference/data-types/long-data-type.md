---
title: Тип данных Long (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Long
helpviewer_keywords:
- identifier type characters [Visual Basic], &
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- '& identifier type character'
- integer numbers
- literal type characters [Visual Basic], L
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- L literal type character [Visual Basic]
- integers [Visual Basic], types
- Long keyword [Visual Basic]
- data types [Visual Basic], integral
- data types [Visual Basic], assigning
- Long data type
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b3970aad08f2be98d175b4175ef06711bcaf609
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43452827"
---
# <a name="long-data-type-visual-basic"></a><span data-ttu-id="01619-102">Тип данных Long (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01619-102">Long data type (Visual Basic)</span></span>

<span data-ttu-id="01619-103">Содержит знаком 64-разрядных целых чисел (8-байтные) в диапазоне от -9223372036854775808 до 9223372036854775807 (9.2 … E + 18).</span><span class="sxs-lookup"><span data-stu-id="01619-103">Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01619-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="01619-104">Remarks</span></span>

 <span data-ttu-id="01619-105">Используйте `Long` тип данных для хранения целых чисел, которые слишком велик для `Integer` тип данных.</span><span class="sxs-lookup"><span data-stu-id="01619-105">Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.</span></span>  
  
 <span data-ttu-id="01619-106">Значение по умолчанию для типа `Long` — 0.</span><span class="sxs-lookup"><span data-stu-id="01619-106">The default value of `Long` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="01619-107">Назначения литералов</span><span class="sxs-lookup"><span data-stu-id="01619-107">Literal assignments</span></span> 

<span data-ttu-id="01619-108">Можно объявить и инициализировать `Long` переменной, назначив ей десятичный литерал, шестнадцатеричный восьмеричный литерал, или (начиная с Visual Basic 2017) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="01619-108">You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="01619-109">Если целочисленный литерал выходит за пределы диапазона `Long` (то есть, если он меньше <xref:System.Int64.MinValue?displayProperty=nameWithType> или больше <xref:System.Int64.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="01619-109">If the integer literal is outside the range of `Long` (that is, if it is less than <xref:System.Int64.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="01619-110">В следующем примере целые числа, равные 4 294 967 296 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `Long`.</span><span class="sxs-lookup"><span data-stu-id="01619-110">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `Long` values.</span></span>
  
[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]  

> [!NOTE]
> <span data-ttu-id="01619-111">Используйте префикс `&h` или `&H` для обозначения шестнадцатеричного литерала, префикс `&b` или `&B` для обозначения двоичного литерала, а также префикс `&o` или `&O` для обозначения восьмеричный литерал.</span><span class="sxs-lookup"><span data-stu-id="01619-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="01619-112">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="01619-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="01619-113">Начиная с Visual Basic 2017, можно также использовать символ подчеркивания, `_`, в качестве разделителя разрядов для повышения удобства чтения, как в примере ниже показан.</span><span class="sxs-lookup"><span data-stu-id="01619-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="01619-114">Начиная с Visual Basic 15.5, можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и двоичное, шестнадцатеричное или восьмеричное цифры.</span><span class="sxs-lookup"><span data-stu-id="01619-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="01619-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="01619-115">For example:</span></span>

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="01619-116">Числовые литералы могут содержать `L` [символ типа](../../programming-guide\language-features\data-types/type-characters.md) для обозначения `Long` тип данных, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="01619-116">Numeric literals can also include the `L` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `Long` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a><span data-ttu-id="01619-117">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="01619-117">Programming tips</span></span>

-   <span data-ttu-id="01619-118">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="01619-118">**Interop Considerations.**</span></span> <span data-ttu-id="01619-119">При взаимодействие с компонентами, которые не написаны для платформы .NET Framework, например, автоматизация или COM-объекты, необходимо помнить, что `Long` имеет другой размер (32 бита) в других средах.</span><span class="sxs-lookup"><span data-stu-id="01619-119">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="01619-120">Если вы передаете 32-разрядного аргумента такому компоненту, объявите его как `Integer` вместо `Long` в новом коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="01619-120">If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="01619-121">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="01619-121">**Widening.**</span></span> <span data-ttu-id="01619-122">`Long` Тип данных можно расширить до `Decimal`, `Single`, или `Double`.</span><span class="sxs-lookup"><span data-stu-id="01619-122">The `Long` data type widens to `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="01619-123">Это означает, что тип `Long` можно преобразовать в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="01619-123">This means you can convert `Long` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="01619-124">**Символы типа.**</span><span class="sxs-lookup"><span data-stu-id="01619-124">**Type Characters.**</span></span> <span data-ttu-id="01619-125">При добавлении к литералу символа типа литерала `L` производится принудительное приведение литерала к типу данных `Long`.</span><span class="sxs-lookup"><span data-stu-id="01619-125">Appending the literal type character `L` to a literal forces it to the `Long` data type.</span></span> <span data-ttu-id="01619-126">При добавлении символа идентификатора типа `&` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Long`.</span><span class="sxs-lookup"><span data-stu-id="01619-126">Appending the identifier type character `&` to any identifier forces it to `Long`.</span></span>  
  
-   <span data-ttu-id="01619-127">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="01619-127">**Framework Type.**</span></span> <span data-ttu-id="01619-128">В .NET Framework данный тип соответствует структуре <xref:System.Int64?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="01619-128">The corresponding type in the .NET Framework is the <xref:System.Int64?displayProperty=nameWithType> structure.</span></span>  

## <a name="see-also"></a><span data-ttu-id="01619-129">См. также</span><span class="sxs-lookup"><span data-stu-id="01619-129">See also</span></span>

<span data-ttu-id="01619-130"><xref:System.Int64>
[Типы данных](../../../visual-basic/language-reference/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="01619-130"><xref:System.Int64>
[Data Types](../../../visual-basic/language-reference/data-types/index.md) </span></span>  
<span data-ttu-id="01619-131">[Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="01619-131">[Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span></span>  
<span data-ttu-id="01619-132">[Тип данных Short](../../../visual-basic/language-reference/data-types/short-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="01619-132">[Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md) </span></span>  
<span data-ttu-id="01619-133">[Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="01619-133">[Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="01619-134">[Общие сведения о преобразовании](../../../visual-basic/language-reference/keywords/conversion-summary.md) </span><span class="sxs-lookup"><span data-stu-id="01619-134">[Conversion Summary](../../../visual-basic/language-reference/keywords/conversion-summary.md) </span></span>  
[<span data-ttu-id="01619-135">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="01619-135">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
