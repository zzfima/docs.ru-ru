---
title: "Побитовые операторы (F#)"
description: "Дополнительные сведения о битовые операторы, доступные в языке F #."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8a2c87f5-b4c7-47fe-8580-82c956f605e5
ms.openlocfilehash: 61a8e6bafe97a229480c967a4afb5d2a256474c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="bitwise-operators"></a><span data-ttu-id="b9bd8-104">Побитовые операторы</span><span class="sxs-lookup"><span data-stu-id="b9bd8-104">Bitwise Operators</span></span>

<span data-ttu-id="b9bd8-105">В этом разделе описываются побитовые операторы, доступные в языке F #.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-105">This topic describes bitwise operators that are available in the F# language.</span></span>

## <a name="summary-of-bitwise-operators"></a><span data-ttu-id="b9bd8-106">Побитовые операторы</span><span class="sxs-lookup"><span data-stu-id="b9bd8-106">Summary of Bitwise Operators</span></span>
<span data-ttu-id="b9bd8-107">В следующей таблице описаны побитовые операторы, которые поддерживаются для распакованный целочисленных типов в языке F #.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-107">The following table describes the bitwise operators that are supported for unboxed integral types in the F# language.</span></span>

|<span data-ttu-id="b9bd8-108">Оператор</span><span class="sxs-lookup"><span data-stu-id="b9bd8-108">Operator</span></span>|<span data-ttu-id="b9bd8-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="b9bd8-109">Notes</span></span>|
|--------|-----|
|`&&&`|<span data-ttu-id="b9bd8-110">Битовый оператор и.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-110">Bitwise AND operator.</span></span> <span data-ttu-id="b9bd8-111">Биты в результате имеют значение 1, только в том случае, если соответствующие биты в обоих операндах равны 1.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-111">Bits in the result have the value 1 if and only if the corresponding bits in both source operands are 1.</span></span>|
|<code>&#124;&#124;&#124;</code>|<span data-ttu-id="b9bd8-112">Битовый оператор или.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-112">Bitwise OR operator.</span></span> <span data-ttu-id="b9bd8-113">Биты в результате имеют значение 1, если любой из соответствующих бита в источнике операндов равны 1.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-113">Bits in the result have the value 1 if either of the corresponding bits in the source operands are 1.</span></span>|
|`^^^`|<span data-ttu-id="b9bd8-114">Побитовый оператор исключающего или.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-114">Bitwise exclusive OR operator.</span></span> <span data-ttu-id="b9bd8-115">Биты в результате имеют значение 1, только в том случае, если биты в операндах имеют разные значения.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-115">Bits in the result have the value 1 if and only if bits in the source operands have unequal values.</span></span>|
|`~~~`|<span data-ttu-id="b9bd8-116">Побитовый оператор отрицания.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-116">Bitwise negation operator.</span></span> <span data-ttu-id="b9bd8-117">Унарный оператор и выдает результат, в котором все биты 0 исходного операнда преобразуются в единичных битов, а все биты 1 преобразуются в 0.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-117">This is a unary operator and produces a result in which all 0 bits in the source operand are converted to 1 bits and all 1 bits are converted to 0 bits.</span></span>|
|`<<<`|<span data-ttu-id="b9bd8-118">Побитовый оператор сдвига влево.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-118">Bitwise left-shift operator.</span></span> <span data-ttu-id="b9bd8-119">Результатом является первый операнд с битами сдвинуты влево на число битов второго операнда.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-119">The result is the first operand with bits shifted left by the number of bits in the second operand.</span></span> <span data-ttu-id="b9bd8-120">Биты, сдвигаемые наиболее важное положение не перемещаются в позиции самого младшего.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-120">Bits shifted off the most significant position are not rotated into the least significant position.</span></span> <span data-ttu-id="b9bd8-121">Менее важные биты заполняются нулями.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-121">The least significant bits are padded with zeros.</span></span> <span data-ttu-id="b9bd8-122">Тип второго аргумента — `int32`.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-122">The type of the second argument is `int32`.</span></span>|
|`>>>`|<span data-ttu-id="b9bd8-123">Побитовый оператор сдвига вправо.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-123">Bitwise right-shift operator.</span></span> <span data-ttu-id="b9bd8-124">Результатом является первый операнд с битами, сдвигаются вправо на число битов второго операнда.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-124">The result is the first operand with bits shifted right by the number of bits in the second operand.</span></span> <span data-ttu-id="b9bd8-125">Биты, сдвигаемые наименее важного положения не перемещаются в наиболее важное положение.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-125">Bits shifted off the least significant position are not rotated into the most significant position.</span></span> <span data-ttu-id="b9bd8-126">Для типов без знака старшие биты заполняются нулями.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-126">For unsigned types, the most significant bits are padded with zeros.</span></span> <span data-ttu-id="b9bd8-127">Для типов со знаком старшие биты заполняются на другие.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-127">For signed types, the most significant bits are padded with ones.</span></span> <span data-ttu-id="b9bd8-128">Тип второго аргумента — `int32`.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-128">The type of the second argument is `int32`.</span></span>|

<span data-ttu-id="b9bd8-129">Можно использовать следующие типы с битовые операторы: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, и `unativeint`.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-129">The following types can be used with bitwise operators: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, and `unativeint`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9bd8-130">См. также</span><span class="sxs-lookup"><span data-stu-id="b9bd8-130">See Also</span></span>
[<span data-ttu-id="b9bd8-131">Справочник символов и операторов</span><span class="sxs-lookup"><span data-stu-id="b9bd8-131">Symbol and Operator Reference</span></span>](index.md)

[<span data-ttu-id="b9bd8-132">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="b9bd8-132">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="b9bd8-133">Логические операторы</span><span class="sxs-lookup"><span data-stu-id="b9bd8-133">Boolean Operators</span></span>](boolean-operators.md)

