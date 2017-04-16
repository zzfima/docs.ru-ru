---
title: "Таблицы преобразования типов в .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "расширяющие преобразования"
  - "сужающие преобразования"
  - "преобразование типов, таблица"
  - "преобразование типов, сужающие преобразования"
  - "преобразование типов, расширяющие преобразования"
  - "базовые типы, преобразование"
  - "таблицы [платформа .NET Framework] преобразования типов"
  - "типы данных [платформа .NET Framework], преобразование"
ms.assetid: 0ea65c59-85eb-4a52-94ca-c36d3bd13058
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Таблицы преобразования типов в .NET Framework
Расширяющее преобразование — это преобразование, при котором значение одного типа преобразуется в другой тип равного или большего размера.  Сужающее преобразование — это преобразование, при котором значение одного типа преобразуется в другой тип меньшего размера.  Таблицы в этом разделе описывают характеристики обоих типов преобразований.  
  
## Расширяющие преобразования  
 В следующей таблице описаны расширяющие преобразования, которые можно выполнять без потери данных.  
  
|Тип|Можно без потери данных преобразовать в|  
|---------|---------------------------------------------|  
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
  
 Некоторые расширяющие преобразования к типу <xref:System.Single> или <xref:System.Double> могут привести к потере точности.  В следующей таблице описаны расширяющие преобразования, которые могут привести к частичной потере данных.  
  
|Тип|Можно преобразовать в:|  
|---------|----------------------------|  
|<xref:System.Int32>|<xref:System.Single>|  
|<xref:System.UInt32>|<xref:System.Single>|  
|<xref:System.Int64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.UInt64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.Decimal>|<xref:System.Single>, <xref:System.Double>|  
  
## Сужающие преобразования  
 Сужающее преобразование к типу <xref:System.Single> или <xref:System.Double> может привести к потере данных.  Если целевой тип не позволяет должным образом выразить порядок величины исходного типа, то результирующий тип будет приравнен к константе `PositiveInfinity` или `NegativeInfinity`.  Константа `PositiveInfinity` возникает в результате деления положительного числа на ноль и также возвращается в случае, если значение типа <xref:System.Single> или <xref:System.Double> больше значения поля `MaxValue`.  Константа `NegativeInfinity` возникает в результате деления отрицательного числа на ноль и также возвращается в случае, если значение типа <xref:System.Single> или <xref:System.Double> меньше значения поля `MinValue`.  Результат преобразования из <xref:System.Double> в <xref:System.Single> может быть равен `PositiveInfinity` или `NegativeInfinity`.  
  
 Сужающее преобразование может также приводить к потере данных и для других типов данных.  Тем не менее в случае, если значение преобразуемого типа выходит за пределы диапазона, заданного значениями полей `MaxValue` и `MinValue` целевого типа, порождается исключение <xref:System.OverflowException>. При этом среда выполнения проверяет преобразование, чтобы гарантировать, что значение целевого типа не выйдет за пределы, заданные значениями полей `MaxValue` и `MinValue` этого типа.  Преобразования, выполняемые с помощью класса <xref:System.Convert?displayProperty=fullName>, всегда проверяются подобным образом.  
  
 В следующей таблице приведен список преобразований, порождающих исключение <xref:System.OverflowException> с помощью класса <xref:System.Convert?displayProperty=fullName> или любого преобразования с проверкой, если значение преобразуемого типа находится вне диапазона, определенного для результирующего типа.  
  
|Тип|Можно преобразовать в:|  
|---------|----------------------------|  
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
  
## См. также  
 <xref:System.Convert?displayProperty=fullName>   
 [Преобразование типов в .NET Framework](../../../docs/standard/base-types/type-conversion.md)