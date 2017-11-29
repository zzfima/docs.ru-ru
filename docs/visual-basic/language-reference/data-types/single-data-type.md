---
title: "Тип данных Single (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Single
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c91dbdf73ed1e26393518001ec8651557e5b780f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="single-data-type-visual-basic"></a><span data-ttu-id="6fef9-102">Тип данных Single (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fef9-102">Single Data Type (Visual Basic)</span></span>
<span data-ttu-id="6fef9-103">Содержит знаком IEEE 32 бита (4-байтовое) число одинарной точности числа с плавающей запятой в диапазоне от - 3, 4028235E + 38 до - 1, 401298E-45 для отрицательных значений и от 1, 401298E-45 до 3, 4028235E + 38 для положительных значений.</span><span class="sxs-lookup"><span data-stu-id="6fef9-103">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span></span> <span data-ttu-id="6fef9-104">Числа одинарной точности сохраняют приближенные значения вещественным числом.</span><span class="sxs-lookup"><span data-stu-id="6fef9-104">Single-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fef9-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="6fef9-105">Remarks</span></span>  
 <span data-ttu-id="6fef9-106">Используйте `Single` тип данных для хранения значений с плавающей запятой, которые не требуют полного размера `Double`.</span><span class="sxs-lookup"><span data-stu-id="6fef9-106">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span></span> <span data-ttu-id="6fef9-107">В некоторых случаях среда можно упаковать вашей `Single` переменные тесном контакте и снизить потребление памяти.</span><span class="sxs-lookup"><span data-stu-id="6fef9-107">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="6fef9-108">Значение по умолчанию для типа `Single` — 0.</span><span class="sxs-lookup"><span data-stu-id="6fef9-108">The default value of `Single` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="6fef9-109">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="6fef9-109">Programming Tips</span></span>  
  
-   <span data-ttu-id="6fef9-110">**Точность.**</span><span class="sxs-lookup"><span data-stu-id="6fef9-110">**Precision.**</span></span> <span data-ttu-id="6fef9-111">При работе с числами с плавающей запятой, имейте в виду, что они не всегда имеют точное представление в памяти.</span><span class="sxs-lookup"><span data-stu-id="6fef9-111">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="6fef9-112">Это может привести к непредвиденным результатам определенных операций, таких как значение сравнения и `Mod` оператор.</span><span class="sxs-lookup"><span data-stu-id="6fef9-112">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="6fef9-113">Дополнительные сведения см. в разделе [Устранение неполадок типы данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="6fef9-113">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
-   <span data-ttu-id="6fef9-114">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="6fef9-114">**Widening.**</span></span> <span data-ttu-id="6fef9-115">`Single` Тип данных может быть расширен до `Double`.</span><span class="sxs-lookup"><span data-stu-id="6fef9-115">The `Single` data type widens to `Double`.</span></span> <span data-ttu-id="6fef9-116">Это означает, что можно преобразовать `Single` для `Double` без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.</span><span class="sxs-lookup"><span data-stu-id="6fef9-116">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="6fef9-117">**Замыкающие нули.**</span><span class="sxs-lookup"><span data-stu-id="6fef9-117">**Trailing Zeros.**</span></span> <span data-ttu-id="6fef9-118">Типы данных с плавающей запятой не имеют внутреннего представления символов конечных нулей.</span><span class="sxs-lookup"><span data-stu-id="6fef9-118">The floating-point data types do not have any internal representation of trailing 0 characters.</span></span> <span data-ttu-id="6fef9-119">Например они не различают 4,2000 и 4,2.</span><span class="sxs-lookup"><span data-stu-id="6fef9-119">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="6fef9-120">Следовательно символы 0 не появляются при отображении или печати значений с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="6fef9-120">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span></span>  
  
-   <span data-ttu-id="6fef9-121">**Символы типов.**</span><span class="sxs-lookup"><span data-stu-id="6fef9-121">**Type Characters.**</span></span> <span data-ttu-id="6fef9-122">При добавлении к литералу символа типа литерала `F` производится принудительное приведение литерала к типу данных `Single`.</span><span class="sxs-lookup"><span data-stu-id="6fef9-122">Appending the literal type character `F` to a literal forces it to the `Single` data type.</span></span> <span data-ttu-id="6fef9-123">При добавлении символа идентификатора типа `!` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Single`.</span><span class="sxs-lookup"><span data-stu-id="6fef9-123">Appending the identifier type character `!` to any identifier forces it to `Single`.</span></span>  
  
-   <span data-ttu-id="6fef9-124">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="6fef9-124">**Framework Type.**</span></span> <span data-ttu-id="6fef9-125">В .NET Framework данный тип соответствует структуре <xref:System.Single?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6fef9-125">The corresponding type in the .NET Framework is the <xref:System.Single?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fef9-126">См. также</span><span class="sxs-lookup"><span data-stu-id="6fef9-126">See Also</span></span>  
 <xref:System.Single?displayProperty=nameWithType>  
 [<span data-ttu-id="6fef9-127">Типы данных</span><span class="sxs-lookup"><span data-stu-id="6fef9-127">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="6fef9-128">Тип данных Decimal</span><span class="sxs-lookup"><span data-stu-id="6fef9-128">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [<span data-ttu-id="6fef9-129">Тип данных Double</span><span class="sxs-lookup"><span data-stu-id="6fef9-129">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [<span data-ttu-id="6fef9-130">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="6fef9-130">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="6fef9-131">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="6fef9-131">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="6fef9-132">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="6fef9-132">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="6fef9-133">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="6fef9-133">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
