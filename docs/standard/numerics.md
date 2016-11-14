---
title: "Числовые значения в .NET Core"
description: "Числовые значения в .NET Core"
keywords: .NET, .NET Core
author: rpetrusha
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 6b8696be-55f5-4b66-98f3-69ff827c2c49
translationtype: Human Translation
ms.sourcegitcommit: d5c7a18af16b4f3416e84b6cf86f0f78f28948da
ms.openlocfilehash: 6d14668e643c2451f4ace2119006f442ed4dee15

---

# <a name="numerics-in-net-core"></a>Числовые значения в .NET Core

Платформа .NET Core поддерживает стандартные числовые типы-примитивы (целочисленные и с плавающей запятой), а также [System.Numerics.BigInteger](https://docs.microsoft.com/dotnet/core/api/System.Numerics.BigInteger)0 — целочисленный тип, теоретически не имеющий верхней и нижней границ, [System.Numerics.Complex](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Complex) — тип, представляющий комплексные числа, и набор векторных типов с поддержкой [SIMD](https://en.wikipedia.org/wiki/SIMD) в пространстве имен [System.Numerics](https://docs.microsoft.com/dotnet/core/api/System.Numerics). 

## <a name="integral-types"></a>Целочисленные типы

.NET Core поддерживает целочисленные значения как со знаком, так и без него, и длиной от одного до восьми байтов. В таблице ниже перечислены целочисленные типы и их размеры, указано, имеют ли они знак, и приведены их диапазоны. Все целые числа являются типами значений. 

Тип | Со знаком или без | Размер (в байтах) | Минимальное значение | Максимальное значение
---- | --------------- | ------------ | ------------- | -------------
[System.Byte](https://docs.microsoft.com/dotnet/core/api/System.Byte) | Без знака | 1 | 0 | 255
[System.Int16](https://docs.microsoft.com/dotnet/core/api/System.Int16) | Подписанный | 2 | –32 768 | 32 767
[System.Int32](https://docs.microsoft.com/dotnet/core/api/System.Int32) | Подписанный | 4 | –2 147 483 648 | 2 147 483 647
[System.Int64](https://docs.microsoft.com/dotnet/core/api/System.Int64) | Подписанный | 8 | –9 223 372 036 854 775 808 | 9 223 372 036 854 775 807
[System.SByte](https://docs.microsoft.com/dotnet/core/api/System.SByte) | Подписанный | 1 | –128 | 127
[System.UInt16](https://docs.microsoft.com/dotnet/core/api/System.UInt16) | Без знака | 2 | 0 | 65 535
[System.UInt32](https://docs.microsoft.com/dotnet/core/api/System.UInt32) | Без знака | 4 | 0 | 4 294 967 295
[System.UInt64](https://docs.microsoft.com/dotnet/core/api/System.UInt64) | Без знака | 8 | 0 | 18 446 744 073 709 551 615

Каждый целочисленный тип поддерживает стандартный набор арифметических операторов, операторов сравнения, равенства, явного и неявного преобразования. Каждый целочисленный тип также имеет методы для выполнения сравнения на равенство и относительного сравнения, преобразования строкового представления числа в данный целочисленный тип и преобразования целого числа в строковое представление. Некоторые дополнительные математические операции, помимо обеспечиваемых стандартными операторами, такие как округление и определение меньшего или большего из двух целых чисел, доступны посредством класса [System.Math](https://docs.microsoft.com/dotnet/core/api/System.Math). Вы также можете работать с отдельными битами целочисленного значения с помощью класса [System.BitConverter](https://docs.microsoft.com/dotnet/core/api/System.BitConverter). 
     
Имейте в виду, что целочисленные типы без знака не совместимы с CLS. Дополнительные сведения см. в разделе [Система общих типов .NET и спецификация CLS](common-type-system.md).

## <a name="floatingpoint-types"></a>Типы с плавающей запятой

Платформа .NET Core включает в себя три типа-примитива с плавающей запятой, которые перечислены в таблице ниже. 

Тип | Размер (в байтах) | Минимальное значение | Максимальное значение
---- | ------------ | ------------- | -------------
[System.Double](https://docs.microsoft.com/dotnet/core/api/System.Double) | 8 | –1,79769313486232e308 | 1,79769313486232e308
[System.Single](https://docs.microsoft.com/dotnet/core/api/System.Single) | 4 | –3,402823e38 | 3,402823e38
[System.Decimal](https://docs.microsoft.com/dotnet/core/api/System.Decimal) | 16 | –79 228 162 514 264 337 593 543 950 335 | 79 228 162 514 264 337 593 543 950 335
   
Каждый тип с плавающей запятой поддерживает стандартный набор арифметических операторов, операторов сравнения, равенства, явного и неявного преобразования. Каждый тип также имеет методы для выполнения сравнения на равенство и относительного сравнения, преобразования строкового представления числа с плавающей запятой в данный тип и преобразования числа с плавающей запятой в строковое представление. Некоторые дополнительные математические, алгебраические и тригонометрические операции доступны посредством класса `Math`. Вы также можете работать с отдельными битами значений типа `Double` и `Single` с помощью класса `BitConverter`. Структура `Decimal` имеет собственные методы, `Decimal.GetBits` и `Decimal.Decimal(Int32())`, для работы с отдельными битами десятичного значения, а также собственный набор методов для выполнения некоторых дополнительных математических операций. 

Типы `Double` и `Single` предназначены для значений, которые по своему характеру являются неточными (например, расстояние между двумя звездами в солнечной системе), и для случаев, когда высокая степень точности и малая погрешность округления не требуются. Тип `Decimal` следует использовать в случаях, когда требуется большая точность и погрешность округления нежелательна.

## <a name="biginteger"></a>BigInteger

[System.Numerics.BigInteger](https://docs.microsoft.com/dotnet/core/api/System.Numerics.BigInteger) является неизменяемым типом, представляющим произвольно большое целое число, значение которого теоретически не имеет верхней или нижней границы. Методы типа `BigInteger` во многом повторяют методы других целочисленных типов.  

## <a name="complex"></a>Complex

Тип [System.Numerics.Complex](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Complex) представляет комплексное число, то есть число, имеющее вещественную и мнимую части. Он поддерживает стандартный набор арифметических операторов, операторов сравнения, равенства, явного и неявного преобразования, а также математические, алгебраические и тригонометрические методы. 

## <a name="simdenabled-vector-types"></a>Векторные типы с поддержкой SIMD

Пространство имен `System.Numerics` содержит набор векторных типов с поддержкой SIMD для платформы .NET Core. Технология SIMD обеспечивает параллельное выполнение некоторых операций на аппаратном уровне, значительно повышая производительность математических, научных и графических приложений, которые производят вычисления с векторами. 

На платформе .NET Core используются перечисленные ниже векторные типы с поддержкой SIMD. 

* Типы [System.Numerics.Vector2](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Vector2), [System.Numerics.Vector3](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Vector3) и [System.Numerics.Vector4](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Vector4), представляющие двух-, трех- и четырехмерные векторы типа `Single`.

* Структура [Vector&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Vector-1), которая позволяет создавать вектор любого числового типа-примитива. К числовым типам-примитивам относятся все числовые типы в пространстве имен System, за исключением Decimal.

* Два матричных типа: [System.Numerics.Matrix3x2](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Matrix3x2), представляющий собой матрицу 3x2, и [System.Numerics.Matrix4x4](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Matrix4x4), представляющий собой матрицу 4x4. 

* Тип [System.Numerics.Plane](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Plane), который представляет трехмерную плоскость, и тип [System.Numerics.Quaternion](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Quaternion), который представляет вектор, используемый для кодирования трехмерных физических поворотов.



<!--HONumber=Nov16_HO1-->


