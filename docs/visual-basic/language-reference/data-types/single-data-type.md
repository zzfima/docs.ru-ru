---
title: Тип данных Single
ms.date: 07/20/2015
f1_keywords:
- vb.Single
helpviewer_keywords:
- Single data type
- F literal type character [Visual Basic]
- trailing zeros
- real numbers
- literal type characters [Visual Basic], F
- trailing 0 characters [Visual Basic]
- identifier type characters [Visual Basic], !
- single-precision numbers
- '! identifier type character'
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- floating-point numbers [Visual Basic], Single data type
- numbers [Visual Basic], real
- zeros, trailing
- numbers [Visual Basic], floating point
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
ms.openlocfilehash: 60a688c510f6e36dca5809566b37a388429e18c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343920"
---
# <a name="single-data-type-visual-basic"></a><span data-ttu-id="ec847-102">Тип данных Single (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec847-102">Single Data Type (Visual Basic)</span></span>

<span data-ttu-id="ec847-103">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span><span class="sxs-lookup"><span data-stu-id="ec847-103">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span></span> <span data-ttu-id="ec847-104">Single-precision numbers store an approximation of a real number.</span><span class="sxs-lookup"><span data-stu-id="ec847-104">Single-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec847-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="ec847-105">Remarks</span></span>  

 <span data-ttu-id="ec847-106">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span><span class="sxs-lookup"><span data-stu-id="ec847-106">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span></span> <span data-ttu-id="ec847-107">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span><span class="sxs-lookup"><span data-stu-id="ec847-107">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="ec847-108">Значение по умолчанию для типа `Single` — 0.</span><span class="sxs-lookup"><span data-stu-id="ec847-108">The default value of `Single` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="ec847-109">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="ec847-109">Programming Tips</span></span>  
  
- <span data-ttu-id="ec847-110">**Precision.**</span><span class="sxs-lookup"><span data-stu-id="ec847-110">**Precision.**</span></span> <span data-ttu-id="ec847-111">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span><span class="sxs-lookup"><span data-stu-id="ec847-111">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="ec847-112">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span><span class="sxs-lookup"><span data-stu-id="ec847-112">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="ec847-113">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ec847-113">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
- <span data-ttu-id="ec847-114">**Widening.**</span><span class="sxs-lookup"><span data-stu-id="ec847-114">**Widening.**</span></span> <span data-ttu-id="ec847-115">The `Single` data type widens to `Double`.</span><span class="sxs-lookup"><span data-stu-id="ec847-115">The `Single` data type widens to `Double`.</span></span> <span data-ttu-id="ec847-116">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="ec847-116">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="ec847-117">**Trailing Zeros.**</span><span class="sxs-lookup"><span data-stu-id="ec847-117">**Trailing Zeros.**</span></span> <span data-ttu-id="ec847-118">The floating-point data types do not have any internal representation of trailing 0 characters.</span><span class="sxs-lookup"><span data-stu-id="ec847-118">The floating-point data types do not have any internal representation of trailing 0 characters.</span></span> <span data-ttu-id="ec847-119">For example, they do not distinguish between 4.2000 and 4.2.</span><span class="sxs-lookup"><span data-stu-id="ec847-119">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="ec847-120">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span><span class="sxs-lookup"><span data-stu-id="ec847-120">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span></span>  
  
- <span data-ttu-id="ec847-121">**Type Characters.**</span><span class="sxs-lookup"><span data-stu-id="ec847-121">**Type Characters.**</span></span> <span data-ttu-id="ec847-122">При добавлении к литералу символа типа литерала `F` производится принудительное приведение литерала к типу данных `Single`.</span><span class="sxs-lookup"><span data-stu-id="ec847-122">Appending the literal type character `F` to a literal forces it to the `Single` data type.</span></span> <span data-ttu-id="ec847-123">При добавлении символа идентификатора типа `!` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Single`.</span><span class="sxs-lookup"><span data-stu-id="ec847-123">Appending the identifier type character `!` to any identifier forces it to `Single`.</span></span>  
  
- <span data-ttu-id="ec847-124">**Framework Type.**</span><span class="sxs-lookup"><span data-stu-id="ec847-124">**Framework Type.**</span></span> <span data-ttu-id="ec847-125">В .NET Framework данный тип соответствует структуре <xref:System.Single?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ec847-125">The corresponding type in the .NET Framework is the <xref:System.Single?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec847-126">См. также</span><span class="sxs-lookup"><span data-stu-id="ec847-126">See also</span></span>

- <xref:System.Single?displayProperty=nameWithType>
- [<span data-ttu-id="ec847-127">Типы данных</span><span class="sxs-lookup"><span data-stu-id="ec847-127">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="ec847-128">Тип данных Decimal</span><span class="sxs-lookup"><span data-stu-id="ec847-128">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [<span data-ttu-id="ec847-129">Тип данных Double</span><span class="sxs-lookup"><span data-stu-id="ec847-129">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="ec847-130">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="ec847-130">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="ec847-131">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="ec847-131">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="ec847-132">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="ec847-132">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="ec847-133">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="ec847-133">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
