---
title: "Таблицы преобразования типов"
description: "Таблицы преобразования типов"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/22/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: d602f260-e7cf-49c8-a37f-731f40e4a538
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: a27f78bc3c0753a7c5bc752bb6391839bfc21e75
ms.lasthandoff: 03/02/2017

---

# <a name="type-conversion-tables"></a>Таблицы преобразования типов

Расширяющее преобразование — это преобразование, при котором значение одного типа преобразуется в другой тип равного или большего размера. Сужающее преобразование — это преобразование, при котором значение одного типа преобразуется в другой тип меньшего размера. Таблицы в этом разделе описывают характеристики обоих типов преобразований.

## <a name="widening-conversions"></a>Расширяющие преобразования

Тип | Можно без потери данных преобразовать в
---- | -------------------------------------
[Byte](xref:System.Byte) | [UInt16](xref:System.UInt16), [Int16](xref:System.Int16), [UInt32](xref:System.UInt32), [Int32](xref:System.Int32), [UInt64](xref:System.UInt64), [Int64](xref:System.Int64), [Single](xref:System.Single), [Double](xref:System.Double), [Decimal](xref:System.Decimal)
[SByte](xref:System.SByte) | [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [Single](xref:System.Single), [Double](xref:System.Double), [Decimal](xref:System.Decimal)
[Int16](xref:System.Int16) | [Int32](xref:System.Int32), [Int64](xref:System.Int64), [Single](xref:System.Single), [Double](xref:System.Double), [Decimal](xref:System.Decimal)
[UInt16](xref:System.UInt16) | [UInt32](xref:System.UInt32), [Int32](xref:System.Int32), [UInt64](xref:System.UInt64), [Int64](xref:System.Int64), [Single](xref:System.Single), [Double](xref:System.Double), [Decimal](xref:System.Decimal)
[Char](xref:System.Char) | [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [Int32](xref:System.Int32), [UInt64](xref:System.UInt64), [Int64](xref:System.Int64), [Single](xref:System.Single), [Double](xref:System.Double), [Decimal](xref:System.Decimal)
[Int32](xref:System.Int32) | [Int64](xref:System.Int64), [Double](xref:System.Double), [Decimal](xref:System.Decimal)
[UInt32](xref:System.UInt32) | [Int64](xref:System.Int64), [UInt64](xref:System.UInt64), [Double](xref:System.Double), [Decimal](xref:System.Decimal)
[Int64](xref:System.Int64) | [Decimal](xref:System.Decimal)
[UInt64](xref:System.UInt64) | [Decimal](xref:System.Decimal)
[Single](xref:System.Single) | [Double](xref:System.Double)

Некоторые расширяющие преобразования к типу [Single](xref:System.Single) или [Double](xref:System.Double) могут привести к потере точности. В следующей таблице описаны расширяющие преобразования, которые могут привести к частичной потере данных.

Тип | Можно преобразовать в
---- | -------------------
[Int32](xref:System.Int32) | [Single](xref:System.Single)
[UInt32](xref:System.UInt32) | [Single](xref:System.Single)
[Int64](xref:System.Int64) | [Single](xref:System.Single), [Double](xref:System.Double)
[UInt64](xref:System.UInt64) | [Single](xref:System.Single), [Double](xref:System.Double)
[Decimal](xref:System.Decimal) | [Single](xref:System.Single), [Double](xref:System.Double)

## <a name="narrowing-conversions"></a>Сужающие преобразования

Сужающее преобразование к типу [Single](xref:System.Single) или [Double](xref:System.Double) может привести к потере данных. Если целевой тип не позволяет должным образом выразить порядок величины исходного типа, то результирующий тип будет приравнен к константе `PositiveInfinity` или `NegativeInfinity`. `PositiveInfinity` возникает в результате деления положительного числа на ноль и также возвращается в том случае, если значение типа [Single](xref:System.Single) или [Double](xref:System.Double) больше значения поля `MaxValue`. `NegativeInfinity` возникает в результате деления отрицательного числа на ноль и также возвращается в случае, если значение типа [Single](xref:System.Single) или [Double](xref:System.Double) меньше значения поля `MinValue`. Результат преобразования из [Double](xref:System.Double) в [Single](xref:System.Single) может быть равен `PositiveInfinity` или `NegativeInfinity`.

Сужающее преобразование может также приводить к потере данных и для других типов данных. Тем не менее в случае, если значение преобразуемого типа выходит за пределы диапазона, заданного значениями полей `MaxValue` и `MinValue` целевого типа, возникает исключение [OverflowException](xref:System.OverflowException). При этом среда выполнения проверяет преобразование, чтобы гарантировать, что значение целевого типа не выйдет за пределы, заданные значениями полей `MaxValue` или `MinValue` этого типа. Преобразования, выполняемые с помощью класса [System.Convert](xref:System.Convert), всегда проверяются подобным образом.

В следующей таблице приведен список преобразований, порождающих исключение [OverflowException](xref:System.OverflowException) с помощью класса [System.Convert](xref:System.Convert) или любого преобразования с проверкой, если значение преобразуемого типа находится вне диапазона, определенного для результирующего типа.

Тип | Можно преобразовать в
---- | -------------------
[Byte](xref:System.Byte) | [SByte](xref:System.SByte)
[SByte](xref:System.SByte) | [Byte](xref:System.Byte), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64)
[Int16](xref:System.Int16) | [Byte](xref:System.Byte), [SByte](xref:System.SByte), [UInt16](xref:System.UInt16)
[UInt16](xref:System.UInt16) | [Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16)
[Int32](xref:System.Int32) | [Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32)
[UInt32](xref:System.UInt32) | [Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [UInt16](xref:System.UInt16), [Int32](xref:System.Int32)
[Int64](xref:System.Int64) | [Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [UInt16](xref:System.UInt16), [Int32](xref:System.Int32), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64)
[UInt64](xref:System.UInt64) | [Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [UInt16](xref:System.UInt16), [Int32](xref:System.Int32), [UInt32](xref:System.UInt32), [Int64](xref:System.Int64)
[Decimal](xref:System.Decimal) | [Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [UInt16](xref:System.UInt16), [Int32](xref:System.Int32), [UInt32](xref:System.UInt32), [Int64](xref:System.Int64), [UInt64](xref:System.UInt64)
[Single](xref:System.Single) | [Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [UInt16](xref:System.UInt16), [Int32](xref:System.Int32), [UInt32](xref:System.UInt32), [Int64](xref:System.Int64), [UInt64](xref:System.UInt64)
[Double](xref:System.Double) | [Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [UInt16](xref:System.UInt16), [Int32](xref:System.Int32), [UInt32](xref:System.UInt32), [Int64](xref:System.Int64), [UInt64](xref:System.UInt64)

## <a name="see-also"></a>См. также

[System.Convert](xref:System.Convert)

[Преобразование типов](type-conversion.md)


