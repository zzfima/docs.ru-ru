---
title: Тип данных Short
ms.date: 01/31/2018
f1_keywords:
- vb.Short
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
ms.openlocfilehash: 8dfdfb56de32e4b3a96729b09ccf46a6fee9a424
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401343"
---
# <a name="short-data-type-visual-basic"></a><span data-ttu-id="0e873-102">Короткий тип данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e873-102">Short data type (Visual Basic)</span></span>

<span data-ttu-id="0e873-103">Держит подписанные 16-битные (2-байт) целые столбы, которые варьируются в цене от -32,768 до 32,767.</span><span class="sxs-lookup"><span data-stu-id="0e873-103">Holds signed 16-bit (2-byte) integers that range in value from -32,768 through 32,767.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e873-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="0e873-104">Remarks</span></span>  

 <span data-ttu-id="0e873-105">Используйте `Short` тип данных для содержащих целые значения, которые `Integer`не требуют полной ширины данных.</span><span class="sxs-lookup"><span data-stu-id="0e873-105">Use the `Short` data type to contain integer values that do not require the full data width of `Integer`.</span></span> <span data-ttu-id="0e873-106">В некоторых случаях время выполнения общего `Short` языка может упаковать переменные близко друг к другу и сохранить потребление памяти.</span><span class="sxs-lookup"><span data-stu-id="0e873-106">In some cases, the common language runtime can pack your `Short` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="0e873-107">Значение по умолчанию для типа `Short` — 0.</span><span class="sxs-lookup"><span data-stu-id="0e873-107">The default value of `Short` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="0e873-108">Литературные задания</span><span class="sxs-lookup"><span data-stu-id="0e873-108">Literal assignments</span></span>

<span data-ttu-id="0e873-109">Вы можете объявить `Short` и инициализировать переменную, назначив ей десятичную буквальную, гексадецичную буквальную, октальную буквальную или (начиная с Visual Basic 2017) двоичный буквальный.</span><span class="sxs-lookup"><span data-stu-id="0e873-109">You can declare and initialize a `Short` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="0e873-110">Если целочисленный литерал выходит за пределы диапазона `Short` (то есть, если он меньше <xref:System.Int16.MinValue?displayProperty=nameWithType> или больше <xref:System.Int16.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="0e873-110">If the integer literal is outside the range of `Short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="0e873-111">В следующем примере целые 1034, которые представлены как десятичные, гексадецимальные и бинарные буквальные, `Short` неявно преобразуются из [Integer](integer-data-type.md) в значения.</span><span class="sxs-lookup"><span data-stu-id="0e873-111">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `Short` values.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> <span data-ttu-id="0e873-112">Вы используете `&h` приставку или `&H` для обозначения гексадецимального буквального, приставки `&b` или `&B` для `&o` `&O` обозначения двоичного буквального, и приставки или для обозначения октал буквального.</span><span class="sxs-lookup"><span data-stu-id="0e873-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="0e873-113">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="0e873-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="0e873-114">Начиная с Visual Basic 2017, вы также `_`можете использовать символ подчеркивания, как цифровой сепаратор для повышения читаемости, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0e873-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

<span data-ttu-id="0e873-115">Начиная с Visual Basic 15.5, вы также`_`можете использовать символ подчеркивателя ( ) в качестве ведущего сепаратора между приставкой и гексадецичными, бинарными или октальными цифрами.</span><span class="sxs-lookup"><span data-stu-id="0e873-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="0e873-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="0e873-116">For example:</span></span>

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="0e873-117">Число в цифрах может `S` также включать [символ](../../programming-guide/language-features/data-types/type-characters.md) `Short` типа для обозначения типа данных, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0e873-117">Numeric literals can also include the `S` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Short` data type, as the following example shows.</span></span>

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a><span data-ttu-id="0e873-118">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="0e873-118">Programming tips</span></span>

- <span data-ttu-id="0e873-119">**Расширение.**</span><span class="sxs-lookup"><span data-stu-id="0e873-119">**Widening.**</span></span> <span data-ttu-id="0e873-120">Тип `Short` данных расширяется `Long` `Decimal`до `Single` `Integer`, `Double`, , или .</span><span class="sxs-lookup"><span data-stu-id="0e873-120">The `Short` data type widens to `Integer`, `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="0e873-121">Это означает, что тип `Short` можно преобразовать в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0e873-121">This means you can convert `Short` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="0e873-122">**Тип символов.**</span><span class="sxs-lookup"><span data-stu-id="0e873-122">**Type Characters.**</span></span> <span data-ttu-id="0e873-123">При добавлении к литералу символа типа литерала `S` производится принудительное приведение литерала к типу данных `Short`.</span><span class="sxs-lookup"><span data-stu-id="0e873-123">Appending the literal type character `S` to a literal forces it to the `Short` data type.</span></span> <span data-ttu-id="0e873-124">`Short`не имеет символа типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="0e873-124">`Short` has no identifier type character.</span></span>  
  
- <span data-ttu-id="0e873-125">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="0e873-125">**Framework Type.**</span></span> <span data-ttu-id="0e873-126">В .NET Framework данный тип соответствует структуре <xref:System.Int16?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0e873-126">The corresponding type in the .NET Framework is the <xref:System.Int16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e873-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0e873-127">See also</span></span>

- <xref:System.Int16?displayProperty=nameWithType>
- [<span data-ttu-id="0e873-128">Типы данных</span><span class="sxs-lookup"><span data-stu-id="0e873-128">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="0e873-129">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="0e873-129">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="0e873-130">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="0e873-130">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="0e873-131">Тип данных негров</span><span class="sxs-lookup"><span data-stu-id="0e873-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="0e873-132">Тип данных Long</span><span class="sxs-lookup"><span data-stu-id="0e873-132">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [<span data-ttu-id="0e873-133">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="0e873-133">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
