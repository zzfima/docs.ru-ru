---
title: 'Базовые типы (F #)'
description: 'Узнайте основные базовые типы, которые используются в языке F #.'
ms.date: 07/09/2018
ms.openlocfilehash: 8f948d066323527b09b1d3f9f4167b95b1c875cf
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "48026949"
---
# <a name="basic-types"></a><span data-ttu-id="469c6-103">Базовые типы</span><span class="sxs-lookup"><span data-stu-id="469c6-103">Basic types</span></span>

<span data-ttu-id="469c6-104">В этом разделе перечислены базовые типы, которые определены в языке F #.</span><span class="sxs-lookup"><span data-stu-id="469c6-104">This topic lists the basic types that are defined in the F# language.</span></span> <span data-ttu-id="469c6-105">Эти типы представляют собой фундаментальные в F #, являющееся основой практически все программы на F #.</span><span class="sxs-lookup"><span data-stu-id="469c6-105">These types are the most fundamental in F#, forming the basis of nearly every F# program.</span></span> <span data-ttu-id="469c6-106">Они являются подмножеством типов-примитивов .NET.</span><span class="sxs-lookup"><span data-stu-id="469c6-106">They are a superset of .NET primitive types.</span></span>

|<span data-ttu-id="469c6-107">Тип</span><span class="sxs-lookup"><span data-stu-id="469c6-107">Type</span></span>|<span data-ttu-id="469c6-108">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="469c6-108">.NET type</span></span>|<span data-ttu-id="469c6-109">Описание</span><span class="sxs-lookup"><span data-stu-id="469c6-109">Description</span></span>|
|----|---------|-----------|
|`bool`|<xref:System.Boolean>|<span data-ttu-id="469c6-110">Возможными значениями являются `true` и `false`.</span><span class="sxs-lookup"><span data-stu-id="469c6-110">Possible values are `true` and `false`.</span></span>|
|`byte`|<xref:System.Byte>|<span data-ttu-id="469c6-111">Значения от 0 до 255.</span><span class="sxs-lookup"><span data-stu-id="469c6-111">Values from 0 to 255.</span></span>|
|`sbyte`|<xref:System.SByte>|<span data-ttu-id="469c6-112">Значения от -128 до 127.</span><span class="sxs-lookup"><span data-stu-id="469c6-112">Values from -128 to 127.</span></span>|
|`int16`|<xref:System.Int16>|<span data-ttu-id="469c6-113">Значения от -32768 до 32767.</span><span class="sxs-lookup"><span data-stu-id="469c6-113">Values from -32768 to 32767.</span></span>|
|`uint16`|<xref:System.UInt16>|<span data-ttu-id="469c6-114">Значения от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="469c6-114">Values from 0 to 65535.</span></span>|
|`int`|<xref:System.Int32>|<span data-ttu-id="469c6-115">Значения от -2147483648 до 2147483647.</span><span class="sxs-lookup"><span data-stu-id="469c6-115">Values from -2,147,483,648 to 2,147,483,647.</span></span>|
|`uint32`|<xref:System.UInt32>|<span data-ttu-id="469c6-116">Значения от 0 до 4 294 967 295.</span><span class="sxs-lookup"><span data-stu-id="469c6-116">Values from 0 to 4,294,967,295.</span></span>|
|`int64`|<xref:System.Int64>|<span data-ttu-id="469c6-117">Значения от -9223372036854775808 до 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="469c6-117">Values from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.</span></span>|
|`uint64`|<xref:System.UInt64>|<span data-ttu-id="469c6-118">Значения от 0 до 18446744073709551615.</span><span class="sxs-lookup"><span data-stu-id="469c6-118">Values from 0 to 18,446,744,073,709,551,615.</span></span>|
|`nativeint`|<xref:System.IntPtr>|<span data-ttu-id="469c6-119">Собственный указатель в виде целого числа со знаком.</span><span class="sxs-lookup"><span data-stu-id="469c6-119">A native pointer as a signed integer.</span></span>|
|`unativeint`|<xref:System.UIntPtr>|<span data-ttu-id="469c6-120">Собственный указатель в виде целого числа без знака.</span><span class="sxs-lookup"><span data-stu-id="469c6-120">A native pointer as an unsigned integer.</span></span>|
|`char`|<xref:System.Char>|<span data-ttu-id="469c6-121">Символы Юникода.</span><span class="sxs-lookup"><span data-stu-id="469c6-121">Unicode character values.</span></span>|
|`string`|<xref:System.String>|<span data-ttu-id="469c6-122">Текст в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="469c6-122">Unicode text.</span></span>|
|`decimal`|<xref:System.Decimal>|<span data-ttu-id="469c6-123">С плавающей запятой в тип данных, по крайней мере 28 значащих цифр.</span><span class="sxs-lookup"><span data-stu-id="469c6-123">A floating point data type that has at least 28 significant digits.</span></span>|
|`unit`|<span data-ttu-id="469c6-124">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="469c6-124">not applicable</span></span>|<span data-ttu-id="469c6-125">Указывает на отсутствие значения.</span><span class="sxs-lookup"><span data-stu-id="469c6-125">Indicates the absence of an actual value.</span></span> <span data-ttu-id="469c6-126">Тип имеет только одно значение, указав `()`.</span><span class="sxs-lookup"><span data-stu-id="469c6-126">The type has only one formal value, which is denoted `()`.</span></span> <span data-ttu-id="469c6-127">Значение единицы измерения, `()`, часто используется как заполнитель, в котором требуется значение, но нет реальные значения доступны или имеет смысл.</span><span class="sxs-lookup"><span data-stu-id="469c6-127">The unit value, `()`, is often used as a placeholder where a value is needed but no real value is available or makes sense.</span></span>|
|`void`|<xref:System.Void>|<span data-ttu-id="469c6-128">Указывает без типа или значения.</span><span class="sxs-lookup"><span data-stu-id="469c6-128">Indicates no type or value.</span></span>|
|<span data-ttu-id="469c6-129">`float32`, `single`</span><span class="sxs-lookup"><span data-stu-id="469c6-129">`float32`, `single`</span></span>|<xref:System.Single>|<span data-ttu-id="469c6-130">32-разрядное число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="469c6-130">A 32-bit floating point type.</span></span>|
|<span data-ttu-id="469c6-131">`float`, `double`</span><span class="sxs-lookup"><span data-stu-id="469c6-131">`float`, `double`</span></span>|<xref:System.Double>|<span data-ttu-id="469c6-132">64-разрядный тип с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="469c6-132">A 64-bit floating point type.</span></span>|

>[!NOTE]
<span data-ttu-id="469c6-133">Позволяет выполнять вычисления с целыми числами слишком велик для 64-разрядному целочисленному типу с помощью [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) типа.</span><span class="sxs-lookup"><span data-stu-id="469c6-133">You can perform computations with integers too big for the 64-bit integer type by using the [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) type.</span></span> <span data-ttu-id="469c6-134">`bigint` не является базовый тип; он представляет собой сокращение от `System.Numerics.BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="469c6-134">`bigint` is not considered a basic type; it is an abbreviation for `System.Numerics.BigInteger`.</span></span>

## <a name="see-also"></a><span data-ttu-id="469c6-135">См. также</span><span class="sxs-lookup"><span data-stu-id="469c6-135">See also</span></span>

- [<span data-ttu-id="469c6-136">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="469c6-136">F# Language Reference</span></span>](index.md)
