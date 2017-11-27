---
title: "Тип данных Short (Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
author: rpetrusha
ms.author: ronpet
f1_keywords: vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: fef948debed69cf9fb7b0e6bb65eb0ddbe497a92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="short-data-type-visual-basic"></a><span data-ttu-id="f986d-102">Тип данных Short (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f986d-102">Short data type (Visual Basic)</span></span>
<span data-ttu-id="f986d-103">Содержит знаком 16-разрядное (2-байтовые) целые числа в диапазоне от-32 768 до 32 767.</span><span class="sxs-lookup"><span data-stu-id="f986d-103">Holds signed 16-bit (2-byte) integers that range in value from -32,768 through 32,767.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f986d-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="f986d-104">Remarks</span></span>  
 <span data-ttu-id="f986d-105">Используйте `Short` тип данных для хранения целых значений, которые не требуют полного размера `Integer`.</span><span class="sxs-lookup"><span data-stu-id="f986d-105">Use the `Short` data type to contain integer values that do not require the full data width of `Integer`.</span></span> <span data-ttu-id="f986d-106">В некоторых случаях можно упаковать общеязыковая среда выполнения вашей `Short` переменные тесном контакте и снизить потребление памяти.</span><span class="sxs-lookup"><span data-stu-id="f986d-106">In some cases, the common language runtime can pack your `Short` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="f986d-107">Значение по умолчанию для типа `Short` — 0.</span><span class="sxs-lookup"><span data-stu-id="f986d-107">The default value of `Short` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="f986d-108">Литерал назначения</span><span class="sxs-lookup"><span data-stu-id="f986d-108">Literal assignments</span></span>

<span data-ttu-id="f986d-109">Можно объявить и инициализировать `Short` переменной, назначив его десятичное литералом, Шестнадцатеричный литерал восьмеричного литерала, или (начиная с Visual Basic 2017 г) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="f986d-109">You can declare and initialize a `Short` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="f986d-110">Если целочисленный литерал выходит за пределы диапазона `Short` (то есть, если он меньше <xref:System.Int16.MinValue?displayProperty=nameWithType> или больше <xref:System.Int16.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="f986d-110">If the integer literal is outside the range of `Short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="f986d-111">В следующем примере целых чисел, равные 1,034, представленное в десятичном, шестнадцатеричном виде, и двоичные литералы производится неявное преобразование из [целое](integer-data-type.md) для `Short` значения.</span><span class="sxs-lookup"><span data-stu-id="f986d-111">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `Short` values.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> <span data-ttu-id="f986d-112">Используйте префикс `&h` или `&H` для обозначения Шестнадцатеричный литерал префиксом `&b` или `&B` для обозначения двоичный литерал и префикс `&o` или `&O` для обозначения восьмеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="f986d-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="f986d-113">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="f986d-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="f986d-114">Начиная с Visual Basic 2017 г., можно также использовать знак подчеркивания `_`, как разделитель для повышения удобства чтения, как в следующем примере показано.</span><span class="sxs-lookup"><span data-stu-id="f986d-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

<span data-ttu-id="f986d-115">Можно также включать числовые литералы `S` [символ типа](../../programming-guide\language-features\data-types/type-characters.md) для обозначения `Short` тип данных, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f986d-115">Numeric literals can also include the `S` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `Short` data type, as the following example shows.</span></span>

```vb
Dim number = &H0326S
```

## <a name="programming-tips"></a><span data-ttu-id="f986d-116">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="f986d-116">Programming tips</span></span>

-   <span data-ttu-id="f986d-117">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="f986d-117">**Widening.**</span></span> <span data-ttu-id="f986d-118">`Short` Тип данных может быть расширен до `Integer`, `Long`, `Decimal`, `Single`, или `Double`.</span><span class="sxs-lookup"><span data-stu-id="f986d-118">The `Short` data type widens to `Integer`, `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="f986d-119">Это означает, что тип `Short` можно преобразовать в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f986d-119">This means you can convert `Short` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="f986d-120">**Символы типов.**</span><span class="sxs-lookup"><span data-stu-id="f986d-120">**Type Characters.**</span></span> <span data-ttu-id="f986d-121">При добавлении к литералу символа типа литерала `S` производится принудительное приведение литерала к типу данных `Short`.</span><span class="sxs-lookup"><span data-stu-id="f986d-121">Appending the literal type character `S` to a literal forces it to the `Short` data type.</span></span> <span data-ttu-id="f986d-122">`Short`не имеет типа символа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="f986d-122">`Short` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="f986d-123">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="f986d-123">**Framework Type.**</span></span> <span data-ttu-id="f986d-124">В .NET Framework данный тип соответствует структуре <xref:System.Int16?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f986d-124">The corresponding type in the .NET Framework is the <xref:System.Int16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f986d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f986d-125">See also</span></span>

 <xref:System.Int16?displayProperty=nameWithType>  
 [<span data-ttu-id="f986d-126">Типы данных</span><span class="sxs-lookup"><span data-stu-id="f986d-126">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="f986d-127">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="f986d-127">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="f986d-128">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="f986d-128">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="f986d-129">Тип данных Integer</span><span class="sxs-lookup"><span data-stu-id="f986d-129">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="f986d-130">Тип данных Long</span><span class="sxs-lookup"><span data-stu-id="f986d-130">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [<span data-ttu-id="f986d-131">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="f986d-131">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
