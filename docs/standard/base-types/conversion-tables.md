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
# <a name="type-conversion-tables-in-net"></a>Таблицы преобразования типов в .NET
Расширяющее преобразование — это преобразование, при котором значение одного типа преобразуется в другой тип равного или большего размера. Сужающее преобразование — это преобразование, при котором значение одного типа преобразуется в другой тип меньшего размера. Таблицы в этом разделе описывают характеристики обоих типов преобразований.  
  
## <a name="widening-conversions"></a>расширяющие преобразования  
 В следующей таблице описаны расширяющие преобразования, которые могут выполняться без потери информации.  
  
|Тип|Можно без потери данных преобразовать в|  
|----------|-------------------------------------------|  
|<xref:System.Byte>|<xref:System.UInt16>, <xref:System.Int16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.SByte>|<xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int16>|<xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.UInt16>|<xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Char>|<xref:System.UInt16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int32>|<xref:System.Int64>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.UInt32>|<xref:System.Int64>, <xref:System.UInt64>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int64>|<xref:System.Decimal>|  
|<xref:System.UInt64>|<xref:System.Decimal>|  
|<xref:System.Single>|<xref:System.Double>|  
  
 Некоторые расширяющие преобразования к <xref:System.Single> или <xref:System.Double> может привести к потере точности. В следующей таблице описаны расширяющие преобразования, которые могут привести к частичной потере данных.  
  
|Тип|Можно преобразовать в|  
|----------|-------------------------|  
|<xref:System.Int32>|<xref:System.Single>|  
|<xref:System.UInt32>|<xref:System.Single>|  
|<xref:System.Int64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.UInt64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.Decimal>|<xref:System.Single>, <xref:System.Double>|  
  
## <a name="narrowing-conversions"></a>сужающие преобразования  
 Сужающее преобразование <xref:System.Single> или <xref:System.Double> может привести к потере данных. Если целевой тип не позволяет должным образом выразить порядок величины исходного типа, то результирующий тип будет приравнен к константе `PositiveInfinity` или `NegativeInfinity`. `PositiveInfinity`полученный в результате деления положительного числа на ноль и также возвращается в случае, если значение <xref:System.Single> или <xref:System.Double> превышает значение `MaxValue` поле. `NegativeInfinity`полученный в результате деления отрицательного числа на ноль и также возвращается в случае, если значение <xref:System.Single> или <xref:System.Double> минимального значения из `MinValue` поля. Преобразование из <xref:System.Double> для <xref:System.Single> может привести к `PositiveInfinity` или `NegativeInfinity`.  
  
 Сужающее преобразование может также приводить к потере данных и для других типов данных. Тем не менее <xref:System.OverflowException> создается, если тип, который преобразуется выходит за пределы диапазона, указанного в целевом типе `MaxValue` и `MinValue` поля, а также преобразование проверяется средой выполнения, чтобы гарантировать, что значение целевого объекта тип не превышает его `MaxValue` или `MinValue`. Преобразования, выполняемые с <xref:System.Convert?displayProperty=nameWithType> класса, всегда проверяются таким образом.  
  
 В следующей таблице перечислены преобразования, которые вызывают <xref:System.OverflowException> с помощью <xref:System.Convert?displayProperty=nameWithType> или любого преобразования с проверкой, если значение преобразуемого типа находится вне диапазона, определенного для результирующего типа.  
  
|Тип|Можно преобразовать в|  
|----------|-------------------------|  
|<xref:System.Byte>|<xref:System.SByte>|  
|<xref:System.SByte>|<xref:System.Byte>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>|  
|<xref:System.Int16>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.UInt16>|  
|<xref:System.UInt16>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>|  
|<xref:System.Int32>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>,<xref:System.UInt32>|  
|<xref:System.UInt32>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>|  
|<xref:System.Int64>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>,<xref:System.UInt32>,<xref:System.UInt64>|  
|<xref:System.UInt64>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>|  
|<xref:System.Decimal>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
|<xref:System.Single>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
|<xref:System.Double>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Convert?displayProperty=nameWithType>  
 [Преобразование типов в .NET](../../../docs/standard/base-types/type-conversion.md)
