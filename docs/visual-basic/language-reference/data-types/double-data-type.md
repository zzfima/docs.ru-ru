---
title: Тип данных Double (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: 701d10a334757a96ffd634204c1e1d5eb5418ce6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824667"
---
# <a name="double-data-type-visual-basic"></a><span data-ttu-id="1fc27-102">Тип данных Double (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1fc27-102">Double Data Type (Visual Basic)</span></span>
<span data-ttu-id="1fc27-103">Содержит знаком IEEE 64-разрядные (8-байтные) числа двойной точности с плавающей запятой числа, в диапазоне от - 1, 79769313486231570E + 308 до - 4, 94065645841246544E-324 для отрицательных значений и от 4.94065645841246544E-324 до 1, 79769313486231570E + 308 положительные значения.</span><span class="sxs-lookup"><span data-stu-id="1fc27-103">Holds signed IEEE 64-bit (8-byte) double-precision floating-point numbers that range in value from -1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values and from 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span> <span data-ttu-id="1fc27-104">Числа двойной точности хранят приближенное значение вещественного числа.</span><span class="sxs-lookup"><span data-stu-id="1fc27-104">Double-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fc27-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="1fc27-105">Remarks</span></span>  
 <span data-ttu-id="1fc27-106">`Double` Тип данных обеспечивает наибольшую и наименьшую возможные значения для нескольких.</span><span class="sxs-lookup"><span data-stu-id="1fc27-106">The `Double` data type provides the largest and smallest possible magnitudes for a number.</span></span>  
  
 <span data-ttu-id="1fc27-107">Значение по умолчанию для типа `Double` — 0.</span><span class="sxs-lookup"><span data-stu-id="1fc27-107">The default value of `Double` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="1fc27-108">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="1fc27-108">Programming Tips</span></span>  
  
-   <span data-ttu-id="1fc27-109">**Точность.**</span><span class="sxs-lookup"><span data-stu-id="1fc27-109">**Precision.**</span></span> <span data-ttu-id="1fc27-110">При работе с числами с плавающей запятой, помните, что они не всегда имеют точное представление в памяти.</span><span class="sxs-lookup"><span data-stu-id="1fc27-110">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="1fc27-111">Это может привести к непредвиденным результатам определенных операций, таких как сравнения значений и `Mod` оператор.</span><span class="sxs-lookup"><span data-stu-id="1fc27-111">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="1fc27-112">Дополнительные сведения см. в разделе [Устранение неполадок типы данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="1fc27-112">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
-   <span data-ttu-id="1fc27-113">**Замыкающие нули.**</span><span class="sxs-lookup"><span data-stu-id="1fc27-113">**Trailing Zeros.**</span></span> <span data-ttu-id="1fc27-114">Типы данных с плавающей запятой не имеют внутреннего представления конечные нули.</span><span class="sxs-lookup"><span data-stu-id="1fc27-114">The floating-point data types do not have any internal representation of trailing zero characters.</span></span> <span data-ttu-id="1fc27-115">Например они не различают 4,2000 и 4.2.</span><span class="sxs-lookup"><span data-stu-id="1fc27-115">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="1fc27-116">Следовательно конечные нули не отображаются при отображении или печати значений с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="1fc27-116">Consequently, trailing zero characters do not appear when you display or print floating-point values.</span></span>  
  
-   <span data-ttu-id="1fc27-117">**Символы типа.**</span><span class="sxs-lookup"><span data-stu-id="1fc27-117">**Type Characters.**</span></span> <span data-ttu-id="1fc27-118">При добавлении к литералу символа типа литерала `R` производится принудительное приведение литерала к типу данных `Double`.</span><span class="sxs-lookup"><span data-stu-id="1fc27-118">Appending the literal type character `R` to a literal forces it to the `Double` data type.</span></span> <span data-ttu-id="1fc27-119">Например, если целочисленное значение сопровождается `R`, значение будет изменено на `Double`.</span><span class="sxs-lookup"><span data-stu-id="1fc27-119">For example, if an integer value is followed by `R`, the value is changed to a `Double`.</span></span>  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     <span data-ttu-id="1fc27-120">При добавлении символа идентификатора типа `#` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Double`.</span><span class="sxs-lookup"><span data-stu-id="1fc27-120">Appending the identifier type character `#` to any identifier forces it to `Double`.</span></span> <span data-ttu-id="1fc27-121">В следующем примере переменная `num` типизируется как `Double`:</span><span class="sxs-lookup"><span data-stu-id="1fc27-121">In the following example, the variable `num` is typed as a `Double`:</span></span>  
  
    ```  
    Dim num# = 3  
    ```  
  
-   <span data-ttu-id="1fc27-122">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="1fc27-122">**Framework Type.**</span></span> <span data-ttu-id="1fc27-123">В .NET Framework данный тип соответствует структуре <xref:System.Double?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1fc27-123">The corresponding type in the .NET Framework is the <xref:System.Double?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fc27-124">См. также</span><span class="sxs-lookup"><span data-stu-id="1fc27-124">See also</span></span>

- <xref:System.Double?displayProperty=nameWithType>
- [<span data-ttu-id="1fc27-125">Типы данных</span><span class="sxs-lookup"><span data-stu-id="1fc27-125">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="1fc27-126">Тип данных Decimal</span><span class="sxs-lookup"><span data-stu-id="1fc27-126">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [<span data-ttu-id="1fc27-127">Тип данных Single</span><span class="sxs-lookup"><span data-stu-id="1fc27-127">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="1fc27-128">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="1fc27-128">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="1fc27-129">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="1fc27-129">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="1fc27-130">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="1fc27-130">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="1fc27-131">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="1fc27-131">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="1fc27-132">Знаки типов</span><span class="sxs-lookup"><span data-stu-id="1fc27-132">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
