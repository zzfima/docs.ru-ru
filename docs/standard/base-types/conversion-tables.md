---
title: "Таблицы преобразования типов в .NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- widening conversions
- narrowing conversions
- type conversion, table
- converting types, narrowing conversions
- converting types, widening conversions
- base types, converting
- tables [.NET Framework], type conversions
- data types [.NET Framework], converting
ms.assetid: 0ea65c59-85eb-4a52-94ca-c36d3bd13058
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 327469f9a151b6ef7e1c42f6669c0a9dae7016fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="type-conversion-tables-in-net"></a><span data-ttu-id="1fe8c-102">Таблицы преобразования типов в .NET</span><span class="sxs-lookup"><span data-stu-id="1fe8c-102">Type Conversion Tables in .NET</span></span>
<span data-ttu-id="1fe8c-103">Расширяющее преобразование — это преобразование, при котором значение одного типа преобразуется в другой тип равного или большего размера.</span><span class="sxs-lookup"><span data-stu-id="1fe8c-103">Widening conversion occurs when a value of one type is converted to another type that is of equal or greater size.</span></span> <span data-ttu-id="1fe8c-104">Сужающее преобразование — это преобразование, при котором значение одного типа преобразуется в другой тип меньшего размера.</span><span class="sxs-lookup"><span data-stu-id="1fe8c-104">A narrowing conversion occurs when a value of one type is converted to a value of another type that is of a smaller size.</span></span> <span data-ttu-id="1fe8c-105">Таблицы в этом разделе описывают характеристики обоих типов преобразований.</span><span class="sxs-lookup"><span data-stu-id="1fe8c-105">The tables in this topic illustrate the behaviors exhibited by both types of conversions.</span></span>  
  
## <a name="widening-conversions"></a><span data-ttu-id="1fe8c-106">расширяющие преобразования</span><span class="sxs-lookup"><span data-stu-id="1fe8c-106">Widening Conversions</span></span>  
 <span data-ttu-id="1fe8c-107">В следующей таблице описаны расширяющие преобразования, которые могут выполняться без потери информации.</span><span class="sxs-lookup"><span data-stu-id="1fe8c-107">The following table describes the widening conversions that can be performed without the loss of information.</span></span>  
  
|<span data-ttu-id="1fe8c-108">Тип</span><span class="sxs-lookup"><span data-stu-id="1fe8c-108">Type</span></span>|<span data-ttu-id="1fe8c-109">Можно без потери данных преобразовать в</span><span class="sxs-lookup"><span data-stu-id="1fe8c-109">Can be converted without data loss to</span></span>|  
|----------|-------------------------------------------|  
|<xref:System.Byte>|<span data-ttu-id="1fe8c-110"><xref:System.UInt16>, <xref:System.Int16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="1fe8c-110"><xref:System.UInt16>, <xref:System.Int16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.SByte>|<span data-ttu-id="1fe8c-111"><xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="1fe8c-111"><xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Int16>|<span data-ttu-id="1fe8c-112"><xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="1fe8c-112"><xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.UInt16>|<span data-ttu-id="1fe8c-113"><xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="1fe8c-113"><xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Char>|<span data-ttu-id="1fe8c-114"><xref:System.UInt16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="1fe8c-114"><xref:System.UInt16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Int32>|<span data-ttu-id="1fe8c-115"><xref:System.Int64>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="1fe8c-115"><xref:System.Int64>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.UInt32>|<span data-ttu-id="1fe8c-116"><xref:System.Int64>, <xref:System.UInt64>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="1fe8c-116"><xref:System.Int64>, <xref:System.UInt64>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Int64>|<xref:System.Decimal>|  
|<xref:System.UInt64>|<xref:System.Decimal>|  
|<xref:System.Single>|<xref:System.Double>|  
  
 <span data-ttu-id="1fe8c-117">Некоторые расширяющие преобразования к <xref:System.Single> или <xref:System.Double> может привести к потере точности.</span><span class="sxs-lookup"><span data-stu-id="1fe8c-117">Some widening conversions to <xref:System.Single> or <xref:System.Double> can cause a loss of precision.</span></span> <span data-ttu-id="1fe8c-118">В следующей таблице описаны расширяющие преобразования, которые могут привести к частичной потере данных.</span><span class="sxs-lookup"><span data-stu-id="1fe8c-118">The following table describes the widening conversions that sometimes result in a loss of information.</span></span>  
  
|<span data-ttu-id="1fe8c-119">Тип</span><span class="sxs-lookup"><span data-stu-id="1fe8c-119">Type</span></span>|<span data-ttu-id="1fe8c-120">Можно преобразовать в</span><span class="sxs-lookup"><span data-stu-id="1fe8c-120">Can be converted to</span></span>|  
|----------|-------------------------|  
|<xref:System.Int32>|<xref:System.Single>|  
|<xref:System.UInt32>|<xref:System.Single>|  
|<xref:System.Int64>|<span data-ttu-id="1fe8c-121"><xref:System.Single>, <xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="1fe8c-121"><xref:System.Single>, <xref:System.Double></span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="1fe8c-122"><xref:System.Single>, <xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="1fe8c-122"><xref:System.Single>, <xref:System.Double></span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="1fe8c-123"><xref:System.Single>, <xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="1fe8c-123"><xref:System.Single>, <xref:System.Double></span></span>|  
  
## <a name="narrowing-conversions"></a><span data-ttu-id="1fe8c-124">сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="1fe8c-124">Narrowing Conversions</span></span>  
 <span data-ttu-id="1fe8c-125">Сужающее преобразование <xref:System.Single> или <xref:System.Double> может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="1fe8c-125">A narrowing conversion to <xref:System.Single> or <xref:System.Double> can cause a loss of information.</span></span> <span data-ttu-id="1fe8c-126">Если целевой тип не позволяет должным образом выразить порядок величины исходного типа, то результирующий тип будет приравнен к константе `PositiveInfinity` или `NegativeInfinity`.</span><span class="sxs-lookup"><span data-stu-id="1fe8c-126">If the target type cannot properly express the magnitude of the source, the resulting type is set to the constant `PositiveInfinity` or `NegativeInfinity`.</span></span> <span data-ttu-id="1fe8c-127">`PositiveInfinity`полученный в результате деления положительного числа на ноль и также возвращается в случае, если значение <xref:System.Single> или <xref:System.Double> превышает значение `MaxValue` поле.</span><span class="sxs-lookup"><span data-stu-id="1fe8c-127">`PositiveInfinity` results from dividing a positive number by zero and is also returned when the value of a <xref:System.Single> or <xref:System.Double> exceeds the value of the `MaxValue` field.</span></span> <span data-ttu-id="1fe8c-128">`NegativeInfinity`полученный в результате деления отрицательного числа на ноль и также возвращается в случае, если значение <xref:System.Single> или <xref:System.Double> минимального значения из `MinValue` поля.</span><span class="sxs-lookup"><span data-stu-id="1fe8c-128">`NegativeInfinity` results from dividing a negative number by zero and is also returned when the value of a <xref:System.Single> or <xref:System.Double> falls below the value of the `MinValue` field.</span></span> <span data-ttu-id="1fe8c-129">Преобразование из <xref:System.Double> для <xref:System.Single> может привести к `PositiveInfinity` или `NegativeInfinity`.</span><span class="sxs-lookup"><span data-stu-id="1fe8c-129">A conversion from a <xref:System.Double> to a <xref:System.Single> might result in `PositiveInfinity` or `NegativeInfinity`.</span></span>  
  
 <span data-ttu-id="1fe8c-130">Сужающее преобразование может также приводить к потере данных и для других типов данных.</span><span class="sxs-lookup"><span data-stu-id="1fe8c-130">A narrowing conversion can also result in a loss of information for other data types.</span></span> <span data-ttu-id="1fe8c-131">Тем не менее <xref:System.OverflowException> создается, если тип, который преобразуется выходит за пределы диапазона, указанного в целевом типе `MaxValue` и `MinValue` поля, а также преобразование проверяется средой выполнения, чтобы гарантировать, что значение целевого объекта тип не превышает его `MaxValue` или `MinValue`.</span><span class="sxs-lookup"><span data-stu-id="1fe8c-131">However, an <xref:System.OverflowException> is thrown if the value of a type that is being converted falls outside of the range specified by the target type's `MaxValue` and `MinValue` fields, and the conversion is checked by the runtime to ensure that the value of the target type does not exceed its `MaxValue` or `MinValue`.</span></span> <span data-ttu-id="1fe8c-132">Преобразования, выполняемые с <xref:System.Convert?displayProperty=nameWithType> класса, всегда проверяются таким образом.</span><span class="sxs-lookup"><span data-stu-id="1fe8c-132">Conversions that are performed with the <xref:System.Convert?displayProperty=nameWithType> class are always checked in this manner.</span></span>  
  
 <span data-ttu-id="1fe8c-133">В следующей таблице перечислены преобразования, которые вызывают <xref:System.OverflowException> с помощью <xref:System.Convert?displayProperty=nameWithType> или любого преобразования с проверкой, если значение преобразуемого типа находится вне диапазона, определенного для результирующего типа.</span><span class="sxs-lookup"><span data-stu-id="1fe8c-133">The following table lists conversions that throw an <xref:System.OverflowException> using <xref:System.Convert?displayProperty=nameWithType> or any checked conversion if the value of the type being converted is outside the defined range of the resulting type.</span></span>  
  
|<span data-ttu-id="1fe8c-134">Тип</span><span class="sxs-lookup"><span data-stu-id="1fe8c-134">Type</span></span>|<span data-ttu-id="1fe8c-135">Можно преобразовать в</span><span class="sxs-lookup"><span data-stu-id="1fe8c-135">Can be converted to</span></span>|  
|----------|-------------------------|  
|<xref:System.Byte>|<xref:System.SByte>|  
|<xref:System.SByte>|<span data-ttu-id="1fe8c-136"><xref:System.Byte>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="1fe8c-136"><xref:System.Byte>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64></span></span>|  
|<xref:System.Int16>|<span data-ttu-id="1fe8c-137"><xref:System.Byte>, <xref:System.SByte>, <xref:System.UInt16></span><span class="sxs-lookup"><span data-stu-id="1fe8c-137"><xref:System.Byte>, <xref:System.SByte>, <xref:System.UInt16></span></span>|  
|<xref:System.UInt16>|<span data-ttu-id="1fe8c-138"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16></span><span class="sxs-lookup"><span data-stu-id="1fe8c-138"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16></span></span>|  
|<xref:System.Int32>|<span data-ttu-id="1fe8c-139"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>,<xref:System.UInt32></span><span class="sxs-lookup"><span data-stu-id="1fe8c-139"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>,<xref:System.UInt32></span></span>|  
|<xref:System.UInt32>|<span data-ttu-id="1fe8c-140"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="1fe8c-140"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32></span></span>|  
|<xref:System.Int64>|<span data-ttu-id="1fe8c-141"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>,<xref:System.UInt32>,<xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="1fe8c-141"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>,<xref:System.UInt32>,<xref:System.UInt64></span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="1fe8c-142"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64></span><span class="sxs-lookup"><span data-stu-id="1fe8c-142"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64></span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="1fe8c-143"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="1fe8c-143"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span></span>|  
|<xref:System.Single>|<span data-ttu-id="1fe8c-144"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="1fe8c-144"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span></span>|  
|<xref:System.Double>|<span data-ttu-id="1fe8c-145"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="1fe8c-145"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1fe8c-146">См. также</span><span class="sxs-lookup"><span data-stu-id="1fe8c-146">See Also</span></span>  
 <xref:System.Convert?displayProperty=nameWithType>  
 [<span data-ttu-id="1fe8c-147">Преобразование типов в .NET</span><span class="sxs-lookup"><span data-stu-id="1fe8c-147">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)
