---
title: Типы-примитивы (F#)
description: 'Обнаружение основных типов-примитивов, используемые в языке F #.'
ms.date: 05/16/2016
ms.openlocfilehash: efe419e5ebf2e49be9433bbd3025ff290d648296
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564473"
---
# <a name="primitive-types"></a><span data-ttu-id="abd7c-103">Типы-примитивы</span><span class="sxs-lookup"><span data-stu-id="abd7c-103">Primitive Types</span></span>

<span data-ttu-id="abd7c-104">В этом разделе перечислены основные типы-примитивы, используемые в языке F #.</span><span class="sxs-lookup"><span data-stu-id="abd7c-104">This topic lists the fundamental primitive types that are used in the F# language.</span></span> <span data-ttu-id="abd7c-105">Кроме того, указывает соответствующие типы .NET и минимальное и максимальное значения для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="abd7c-105">It also provides the corresponding .NET types and the minimum and maximum values for each type.</span></span>

## <a name="summary-of-primitive-types"></a><span data-ttu-id="abd7c-106">Сводка типов-примитивов</span><span class="sxs-lookup"><span data-stu-id="abd7c-106">Summary of Primitive Types</span></span>
<span data-ttu-id="abd7c-107">В следующей таблице перечислены свойства простых типов F #.</span><span class="sxs-lookup"><span data-stu-id="abd7c-107">The following table summarizes the properties of the primitive F# types.</span></span>

|<span data-ttu-id="abd7c-108">Тип</span><span class="sxs-lookup"><span data-stu-id="abd7c-108">Type</span></span>|<span data-ttu-id="abd7c-109">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="abd7c-109">.NET type</span></span>|<span data-ttu-id="abd7c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="abd7c-110">Description</span></span>|
|----|---------|-----------|
|`bool`|`System.Boolean`|<span data-ttu-id="abd7c-111">Возможными значениями являются `true` и `false`.</span><span class="sxs-lookup"><span data-stu-id="abd7c-111">Possible values are `true` and `false`.</span></span>|
|`byte`|`System.Byte`|<span data-ttu-id="abd7c-112">Значения от 0 до 255.</span><span class="sxs-lookup"><span data-stu-id="abd7c-112">Values from 0 to 255.</span></span>|
|`sbyte`|`System.SByte`|<span data-ttu-id="abd7c-113">Значения от -128 до 127.</span><span class="sxs-lookup"><span data-stu-id="abd7c-113">Values from -128 to 127.</span></span>|
|`int16`|`System.Int16`|<span data-ttu-id="abd7c-114">Значения от -32768 до 32767.</span><span class="sxs-lookup"><span data-stu-id="abd7c-114">Values from -32768 to 32767.</span></span>|
|`uint16`|`System.UInt16`|<span data-ttu-id="abd7c-115">Значения от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="abd7c-115">Values from 0 to 65535.</span></span>|
|`int`|`System.Int32`|<span data-ttu-id="abd7c-116">Значения от -2147483648 до 2147483647.</span><span class="sxs-lookup"><span data-stu-id="abd7c-116">Values from -2,147,483,648 to 2,147,483,647.</span></span>|
|`uint32`|`System.UInt32`|<span data-ttu-id="abd7c-117">Значения от 0 до 4 294 967 295.</span><span class="sxs-lookup"><span data-stu-id="abd7c-117">Values from 0 to 4,294,967,295.</span></span>|
|`int64`|`System.Int64`|<span data-ttu-id="abd7c-118">Значения от -9223372036854775808 до 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="abd7c-118">Values from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.</span></span>|
|`uint64`|`System.UInt64`|<span data-ttu-id="abd7c-119">Значения от 0 до 18446744073709551615.</span><span class="sxs-lookup"><span data-stu-id="abd7c-119">Values from 0 to 18,446,744,073,709,551,615.</span></span>|
|`nativeint`|`System.IntPtr`|<span data-ttu-id="abd7c-120">Собственный указатель в виде целого числа со знаком.</span><span class="sxs-lookup"><span data-stu-id="abd7c-120">A native pointer as a signed integer.</span></span>|
|`unativeint`|`System.UIntPtr`|<span data-ttu-id="abd7c-121">Собственный указатель в виде целого числа без знака.</span><span class="sxs-lookup"><span data-stu-id="abd7c-121">A native pointer as an unsigned integer.</span></span>|
|`char`|`System.Char`|<span data-ttu-id="abd7c-122">Символы Юникода.</span><span class="sxs-lookup"><span data-stu-id="abd7c-122">Unicode character values.</span></span>|
|`string`|`System.String`|<span data-ttu-id="abd7c-123">Текст в кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="abd7c-123">Unicode text.</span></span>|
|`decimal`|`System.Decimal`|<span data-ttu-id="abd7c-124">С плавающей запятой, тип данных, по крайней мере 28 значащих цифр.</span><span class="sxs-lookup"><span data-stu-id="abd7c-124">A floating point data type that has at least 28 significant digits.</span></span>|
|`unit`|<span data-ttu-id="abd7c-125">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="abd7c-125">not applicable</span></span>|<span data-ttu-id="abd7c-126">Указывает на отсутствие фактическое значение.</span><span class="sxs-lookup"><span data-stu-id="abd7c-126">Indicates the absence of an actual value.</span></span> <span data-ttu-id="abd7c-127">Тип имеет только одно значение, который определяется `()`.</span><span class="sxs-lookup"><span data-stu-id="abd7c-127">The type has only one formal value, which is denoted `()`.</span></span> <span data-ttu-id="abd7c-128">Значение единицы измерения, `()`, часто используется в качестве заполнителя, в котором требуется значение, но не Вещественное значение имеет смысл, или не истечет.</span><span class="sxs-lookup"><span data-stu-id="abd7c-128">The unit value, `()`, is often used as a placeholder where a value is needed but no real value is available or makes sense.</span></span>|
|`void`|`System.Void`|<span data-ttu-id="abd7c-129">Указывает без типа или значения.</span><span class="sxs-lookup"><span data-stu-id="abd7c-129">Indicates no type or value.</span></span>|
|`float32, single`|`System.Single`|<span data-ttu-id="abd7c-130">32-разрядное число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="abd7c-130">A 32-bit floating point type.</span></span>|
|`float, double`|`System.Double`|<span data-ttu-id="abd7c-131">64-разрядное число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="abd7c-131">A 64-bit floating point type.</span></span>|

>[!NOTE]
<span data-ttu-id="abd7c-132">Позволяет выполнять вычисления с целыми числами слишком велик для 64-разрядного целочисленного типа с помощью [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) типа.</span><span class="sxs-lookup"><span data-stu-id="abd7c-132">You can perform computations with integers too big for the 64-bit integer type by using the [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) type.</span></span> <span data-ttu-id="abd7c-133">`bigint` не является типом-примитивом; он представляет собой сокращение от `System.Numerics.BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="abd7c-133">`bigint` is not considered a primitive type; it is an abbreviation for `System.Numerics.BigInteger`.</span></span>

## <a name="see-also"></a><span data-ttu-id="abd7c-134">См. также</span><span class="sxs-lookup"><span data-stu-id="abd7c-134">See Also</span></span>
[<span data-ttu-id="abd7c-135">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="abd7c-135">F# Language Reference</span></span>](index.md)
