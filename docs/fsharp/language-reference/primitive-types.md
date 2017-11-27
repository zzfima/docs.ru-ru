---
title: "Типы-примитивы (F#)"
description: "Обнаружение основных типов-примитивов, используемые в языке F #."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2f23d98b-551b-4fd2-9f4f-0fd7254288ed
ms.openlocfilehash: b493cdf7116d94f66940d03b86e584bcecbbb0f1
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2017
---
# <a name="primitive-types"></a><span data-ttu-id="07491-104">Типы-примитивы</span><span class="sxs-lookup"><span data-stu-id="07491-104">Primitive Types</span></span>

<span data-ttu-id="07491-105">В этом разделе перечислены основные типы-примитивы, используемые в языке F #.</span><span class="sxs-lookup"><span data-stu-id="07491-105">This topic lists the fundamental primitive types that are used in the F# language.</span></span> <span data-ttu-id="07491-106">Кроме того, указывает соответствующие типы .NET и минимальное и максимальное значения для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="07491-106">It also provides the corresponding .NET types and the minimum and maximum values for each type.</span></span>

## <a name="summary-of-primitive-types"></a><span data-ttu-id="07491-107">Сводка типов-примитивов</span><span class="sxs-lookup"><span data-stu-id="07491-107">Summary of Primitive Types</span></span>
<span data-ttu-id="07491-108">В следующей таблице перечислены свойства простых типов F #.</span><span class="sxs-lookup"><span data-stu-id="07491-108">The following table summarizes the properties of the primitive F# types.</span></span>

|<span data-ttu-id="07491-109">Тип</span><span class="sxs-lookup"><span data-stu-id="07491-109">Type</span></span>|<span data-ttu-id="07491-110">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="07491-110">.NET type</span></span>|<span data-ttu-id="07491-111">Описание</span><span class="sxs-lookup"><span data-stu-id="07491-111">Description</span></span>|
|----|---------|-----------|
|`bool`|`System.Boolean`|<span data-ttu-id="07491-112">Возможными значениями являются `true` и `false`.</span><span class="sxs-lookup"><span data-stu-id="07491-112">Possible values are `true` and `false`.</span></span>|
|`byte`|`System.Byte`|<span data-ttu-id="07491-113">Значения от 0 до 255.</span><span class="sxs-lookup"><span data-stu-id="07491-113">Values from 0 to 255.</span></span>|
|`sbyte`|`System.SByte`|<span data-ttu-id="07491-114">Значения от -128 до 127.</span><span class="sxs-lookup"><span data-stu-id="07491-114">Values from -128 to 127.</span></span>|
|`int16`|`System.Int16`|<span data-ttu-id="07491-115">Значения от -32768 до 32767.</span><span class="sxs-lookup"><span data-stu-id="07491-115">Values from -32768 to 32767.</span></span>|
|`uint16`|`System.UInt16`|<span data-ttu-id="07491-116">Значения от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="07491-116">Values from 0 to 65535.</span></span>|
|`int`|`System.Int32`|<span data-ttu-id="07491-117">Значения от -2147483648 до 2147483647.</span><span class="sxs-lookup"><span data-stu-id="07491-117">Values from -2,147,483,648 to 2,147,483,647.</span></span>|
|`uint32`|`System.UInt32`|<span data-ttu-id="07491-118">Значения от 0 до 4 294 967 295.</span><span class="sxs-lookup"><span data-stu-id="07491-118">Values from 0 to 4,294,967,295.</span></span>|
|`int64`|`System.Int64`|<span data-ttu-id="07491-119">Значения от -9223372036854775808 до 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="07491-119">Values from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.</span></span>|
|`uint64`|`System.UInt64`|<span data-ttu-id="07491-120">Значения от 0 до 18446744073709551615.</span><span class="sxs-lookup"><span data-stu-id="07491-120">Values from 0 to 18,446,744,073,709,551,615.</span></span>|
|`nativeint`|`System.IntPtr`|<span data-ttu-id="07491-121">Собственный указатель в виде целого числа со знаком.</span><span class="sxs-lookup"><span data-stu-id="07491-121">A native pointer as a signed integer.</span></span>|
|`unativeint`|`System.UIntPtr`|<span data-ttu-id="07491-122">Собственный указатель в виде целого числа без знака.</span><span class="sxs-lookup"><span data-stu-id="07491-122">A native pointer as an unsigned integer.</span></span>|
|`char`|`System.Char`|<span data-ttu-id="07491-123">Символы Юникода.</span><span class="sxs-lookup"><span data-stu-id="07491-123">Unicode character values.</span></span>|
|`string`|`System.String`|<span data-ttu-id="07491-124">Текст в кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="07491-124">Unicode text.</span></span>|
|`decimal`|`System.Decimal`|<span data-ttu-id="07491-125">С плавающей запятой, тип данных, по крайней мере 28 значащих цифр.</span><span class="sxs-lookup"><span data-stu-id="07491-125">A floating point data type that has at least 28 significant digits.</span></span>|
|`unit`|<span data-ttu-id="07491-126">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="07491-126">not applicable</span></span>|<span data-ttu-id="07491-127">Указывает на отсутствие фактическое значение.</span><span class="sxs-lookup"><span data-stu-id="07491-127">Indicates the absence of an actual value.</span></span> <span data-ttu-id="07491-128">Тип имеет только одно значение, который определяется `()`.</span><span class="sxs-lookup"><span data-stu-id="07491-128">The type has only one formal value, which is denoted `()`.</span></span> <span data-ttu-id="07491-129">Значение единицы измерения, `()`, часто используется в качестве заполнителя, в котором требуется значение, но не Вещественное значение имеет смысл, или не истечет.</span><span class="sxs-lookup"><span data-stu-id="07491-129">The unit value, `()`, is often used as a placeholder where a value is needed but no real value is available or makes sense.</span></span>|
|`void`|`System.Void`|<span data-ttu-id="07491-130">Указывает без типа или значения.</span><span class="sxs-lookup"><span data-stu-id="07491-130">Indicates no type or value.</span></span>|
|`float32, single`|`System.Single`|<span data-ttu-id="07491-131">32-разрядное число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="07491-131">A 32-bit floating point type.</span></span>|
|`float, double`|`System.Double`|<span data-ttu-id="07491-132">64-разрядное число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="07491-132">A 64-bit floating point type.</span></span>|

>[!NOTE]
<span data-ttu-id="07491-133">Позволяет выполнять вычисления с целыми числами слишком велик для 64-разрядного целочисленного типа с помощью [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) типа.</span><span class="sxs-lookup"><span data-stu-id="07491-133">You can perform computations with integers too big for the 64-bit integer type by using the [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) type.</span></span> <span data-ttu-id="07491-134">`bigint`не является типом-примитивом; он представляет собой сокращение от `System.Numerics.BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="07491-134">`bigint` is not considered a primitive type; it is an abbreviation for `System.Numerics.BigInteger`.</span></span>

## <a name="see-also"></a><span data-ttu-id="07491-135">См. также</span><span class="sxs-lookup"><span data-stu-id="07491-135">See Also</span></span>
[<span data-ttu-id="07491-136">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="07491-136">F# Language Reference</span></span>](index.md)
