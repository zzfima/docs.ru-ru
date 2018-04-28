---
title: Побитовые операторы (F#)
description: 'Дополнительные сведения о битовые операторы, доступные в языке F #.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 4d5abff564a5d1dcbe52b99edf431ca10e442061
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="bitwise-operators"></a><span data-ttu-id="ac649-103">Побитовые операторы</span><span class="sxs-lookup"><span data-stu-id="ac649-103">Bitwise Operators</span></span>

<span data-ttu-id="ac649-104">В этом разделе описываются побитовые операторы, доступные в языке F #.</span><span class="sxs-lookup"><span data-stu-id="ac649-104">This topic describes bitwise operators that are available in the F# language.</span></span>

## <a name="summary-of-bitwise-operators"></a><span data-ttu-id="ac649-105">Побитовые операторы</span><span class="sxs-lookup"><span data-stu-id="ac649-105">Summary of Bitwise Operators</span></span>
<span data-ttu-id="ac649-106">В следующей таблице описаны побитовые операторы, которые поддерживаются для распакованный целочисленных типов в языке F #.</span><span class="sxs-lookup"><span data-stu-id="ac649-106">The following table describes the bitwise operators that are supported for unboxed integral types in the F# language.</span></span>

|<span data-ttu-id="ac649-107">Оператор</span><span class="sxs-lookup"><span data-stu-id="ac649-107">Operator</span></span>|<span data-ttu-id="ac649-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="ac649-108">Notes</span></span>|
|--------|-----|
|`&&&`|<span data-ttu-id="ac649-109">Битовый оператор и.</span><span class="sxs-lookup"><span data-stu-id="ac649-109">Bitwise AND operator.</span></span> <span data-ttu-id="ac649-110">Биты в результате имеют значение 1, только в том случае, если соответствующие биты в обоих операндах равны 1.</span><span class="sxs-lookup"><span data-stu-id="ac649-110">Bits in the result have the value 1 if and only if the corresponding bits in both source operands are 1.</span></span>|
|<code>&#124;&#124;&#124;</code>|<span data-ttu-id="ac649-111">Битовый оператор или.</span><span class="sxs-lookup"><span data-stu-id="ac649-111">Bitwise OR operator.</span></span> <span data-ttu-id="ac649-112">Биты в результате имеют значение 1, если любой из соответствующих бита в источнике операндов равны 1.</span><span class="sxs-lookup"><span data-stu-id="ac649-112">Bits in the result have the value 1 if either of the corresponding bits in the source operands are 1.</span></span>|
|`^^^`|<span data-ttu-id="ac649-113">Побитовый оператор исключающего или.</span><span class="sxs-lookup"><span data-stu-id="ac649-113">Bitwise exclusive OR operator.</span></span> <span data-ttu-id="ac649-114">Биты в результате имеют значение 1, только в том случае, если биты в операндах имеют разные значения.</span><span class="sxs-lookup"><span data-stu-id="ac649-114">Bits in the result have the value 1 if and only if bits in the source operands have unequal values.</span></span>|
|`~~~`|<span data-ttu-id="ac649-115">Побитовый оператор отрицания.</span><span class="sxs-lookup"><span data-stu-id="ac649-115">Bitwise negation operator.</span></span> <span data-ttu-id="ac649-116">Унарный оператор и выдает результат, в котором все биты 0 исходного операнда преобразуются в единичных битов, а все биты 1 преобразуются в 0.</span><span class="sxs-lookup"><span data-stu-id="ac649-116">This is a unary operator and produces a result in which all 0 bits in the source operand are converted to 1 bits and all 1 bits are converted to 0 bits.</span></span>|
|`<<<`|<span data-ttu-id="ac649-117">Побитовый оператор сдвига влево.</span><span class="sxs-lookup"><span data-stu-id="ac649-117">Bitwise left-shift operator.</span></span> <span data-ttu-id="ac649-118">Результатом является первый операнд с битами сдвинуты влево на число битов второго операнда.</span><span class="sxs-lookup"><span data-stu-id="ac649-118">The result is the first operand with bits shifted left by the number of bits in the second operand.</span></span> <span data-ttu-id="ac649-119">Биты, сдвигаемые наиболее важное положение не перемещаются в позиции самого младшего.</span><span class="sxs-lookup"><span data-stu-id="ac649-119">Bits shifted off the most significant position are not rotated into the least significant position.</span></span> <span data-ttu-id="ac649-120">Менее важные биты заполняются нулями.</span><span class="sxs-lookup"><span data-stu-id="ac649-120">The least significant bits are padded with zeros.</span></span> <span data-ttu-id="ac649-121">Тип второго аргумента — `int32`.</span><span class="sxs-lookup"><span data-stu-id="ac649-121">The type of the second argument is `int32`.</span></span>|
|`>>>`|<span data-ttu-id="ac649-122">Побитовый оператор сдвига вправо.</span><span class="sxs-lookup"><span data-stu-id="ac649-122">Bitwise right-shift operator.</span></span> <span data-ttu-id="ac649-123">Результатом является первый операнд с битами, сдвигаются вправо на число битов второго операнда.</span><span class="sxs-lookup"><span data-stu-id="ac649-123">The result is the first operand with bits shifted right by the number of bits in the second operand.</span></span> <span data-ttu-id="ac649-124">Биты, сдвигаемые наименее важного положения не перемещаются в наиболее важное положение.</span><span class="sxs-lookup"><span data-stu-id="ac649-124">Bits shifted off the least significant position are not rotated into the most significant position.</span></span> <span data-ttu-id="ac649-125">Для типов без знака старшие биты заполняются нулями.</span><span class="sxs-lookup"><span data-stu-id="ac649-125">For unsigned types, the most significant bits are padded with zeros.</span></span> <span data-ttu-id="ac649-126">Для типов со знаком старшие биты заполняются на другие.</span><span class="sxs-lookup"><span data-stu-id="ac649-126">For signed types, the most significant bits are padded with ones.</span></span> <span data-ttu-id="ac649-127">Тип второго аргумента — `int32`.</span><span class="sxs-lookup"><span data-stu-id="ac649-127">The type of the second argument is `int32`.</span></span>|

<span data-ttu-id="ac649-128">Можно использовать следующие типы с битовые операторы: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, и `unativeint`.</span><span class="sxs-lookup"><span data-stu-id="ac649-128">The following types can be used with bitwise operators: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, and `unativeint`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac649-129">См. также</span><span class="sxs-lookup"><span data-stu-id="ac649-129">See Also</span></span>
[<span data-ttu-id="ac649-130">Справочник символов и операторов</span><span class="sxs-lookup"><span data-stu-id="ac649-130">Symbol and Operator Reference</span></span>](index.md)

[<span data-ttu-id="ac649-131">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="ac649-131">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="ac649-132">Логические операторы</span><span class="sxs-lookup"><span data-stu-id="ac649-132">Boolean Operators</span></span>](boolean-operators.md)

