---
title: Числовые значения в .NET
ms.date: 10/18/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- SIMD
- System.Numerics.Vectors
- vectors
- scientific computing
- Complex
- numerics
- BigInteger
ms.assetid: dfebc18e-acde-4510-9fa7-9a0f4aa3bd11
ms.openlocfilehash: e5815058898cac165e7a47d761ee86bb9c4cb940
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73091588"
---
# <a name="numerics-in-net"></a>Числовые значения в .NET

Платформа .NET предоставляет в пространстве имен <xref:System.Numerics.BigInteger?displayProperty=nameWithType> разные примитивы для целых чисел и чисел с плавающей запятой, а также <xref:System.Numerics.Complex?displayProperty=nameWithType> (целочисленный тип, не имеющий теоретической верхней и нижней границы), <xref:System.Numerics> (тип для представления комплексных чисел) и набор типов с поддержкой SIMD.
  
## <a name="integer-types"></a>Целочисленные типы

Платформа .NET поддерживает целочисленные типы со знаком и без знака с разрядностью 8, 16, 32 и 64 бита. Полный список приводится в следующей таблице.
  
|Type|Со знаком или без|Размер (в байтах)|Минимальное значение|Максимальное значение|  
|----------|----------------------|--------------------|-------------------|-------------------|  
|<xref:System.Byte?displayProperty=nameWithType>|Без знака|1|0|255|  
|<xref:System.Int16?displayProperty=nameWithType>|Со знаком|2|–32 768|32 767|  
|<xref:System.Int32?displayProperty=nameWithType>|Со знаком|4|–2 147 483 648|2,147,483,647|  
|<xref:System.Int64?displayProperty=nameWithType>|Со знаком|8|–9 223 372 036 854 775 808|9 223 372 036 854 775 807|  
|<xref:System.SByte?displayProperty=nameWithType>|Со знаком|1|–128|127|  
|<xref:System.UInt16?displayProperty=nameWithType>|Без знака|2|0|65 535|  
|<xref:System.UInt32?displayProperty=nameWithType>|Без знака|4|0|4 294 967 295|  
|<xref:System.UInt64?displayProperty=nameWithType>|Без знака|8|0|18 446 744 073 709 551 615|  
  
Каждый целочисленный тип поддерживает набор стандартных арифметических операторов. Класс <xref:System.Math?displayProperty=nameWithType> предоставляет методы для широкого набора математических функций.

Вы также можете работать с отдельными битами целочисленного значения с помощью класса <xref:System.BitConverter?displayProperty=nameWithType>.  

> [!NOTE]  
> Целочисленные типы без знака не совместимы с CLS. Дополнительные сведения см. в разделе [Независимость от языка и независимые от языка компоненты](language-independence-and-language-independent-components.md).

## <a name="biginteger"></a>BigInteger

Структура <xref:System.Numerics.BigInteger?displayProperty=nameWithType> является неизменяемым типом, который представляет произвольно большое целое число. Для него в теории не существует верхней или нижней границы. Методы типа <xref:System.Numerics.BigInteger> во многом повторяют методы других целочисленных типов.
  
## <a name="floating-point-types"></a>Типы с плавающей запятой

Платформа .NET поддерживает три примитива с плавающей запятой, которые перечислены в таблице ниже.
  
|Type|Размер (в байтах)|Приблизительный диапазон значений|Точность|  
|----------|--------|---------------------|--------------------|  
|<xref:System.Single?displayProperty=nameWithType>|4|От ±1,5 x 10<sup>−45</sup> до ±3,4 x 10<sup>38</sup>|6–9 цифр|  
|<xref:System.Double?displayProperty=nameWithType>|8|от ±5,0 × 10<sup>−324</sup> до ±1,7 × 10<sup>308</sup>|15–17 цифр|  
|<xref:System.Decimal?displayProperty=nameWithType>|16|от ±1,0 x 10<sup>-28</sup> до ±7,9228 x 10<sup>28</sup>|28-29 знаков|  
  
Оба типа <xref:System.Single> и <xref:System.Double> поддерживают специальные значения, обозначающие бесконечность и нечисловое значение. Например, тип <xref:System.Double> предоставляет следующие значения: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> и <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>. Для проверки на эти значения применяются методы <xref:System.Double.IsNaN%2A?displayProperty=nameWithType>, <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType>, <xref:System.Double.IsPositiveInfinity%2A?displayProperty=nameWithType> и <xref:System.Double.IsNegativeInfinity%2A?displayProperty=nameWithType>.

Каждый тип с плавающей запятой поддерживает набор стандартных арифметических операторов. Класс <xref:System.Math?displayProperty=nameWithType> предоставляет методы для широкого набора математических функций. .NET Core 2.0 и более поздних версий содержит класс <xref:System.MathF?displayProperty=nameWithType>, методы которого принимают аргументы с типом <xref:System.Single>.

Вы также можете работать с отдельными битами значений типа <xref:System.Double> и <xref:System.Single> с помощью класса <xref:System.BitConverter?displayProperty=nameWithType>. Структура <xref:System.Decimal?displayProperty=nameWithType> имеет собственные методы, <xref:System.Decimal.GetBits%2A?displayProperty=nameWithType> и <xref:System.Decimal.%23ctor%28System.Int32%5B%5D%29?displayProperty=nameWithType>, для работы с отдельными битами десятичного значения, а также собственный набор методов для выполнения некоторых дополнительных математических операций.
  
Типы <xref:System.Double> и <xref:System.Single> предназначены для значений, которые по своему характеру являются неточными (например, расстояние между двумя звездами), и для случаев, когда не требуются высокая степень точности и малая погрешность округления. Тип <xref:System.Decimal?displayProperty=nameWithType> следует использовать в случаях, когда требуется большая точность и минимальная погрешность округления.

> [!NOTE]
> Тип <xref:System.Decimal> не устраняет потребность в округлении. Но он сводит к минимуму ошибки, возникающие из-за округления.
  
## <a name="complex"></a>Complex

Структура <xref:System.Numerics.Complex?displayProperty=nameWithType> представляет комплексное число, то есть число, имеющее вещественную и мнимую части. Она поддерживает стандартный набор арифметических операторов, операторов сравнения, равенства, явного и неявного преобразования, а также математические, алгебраические и тригонометрические методы.  
  
## <a name="simd-enabled-types"></a>Типы с поддержкой SIMD

Пространство имен <xref:System.Numerics> содержит набор типов .NET с поддержкой SIMD. Операции SIMD (Single Instruction Multiple Data) допускают параллельное выполнение на аппаратном уровне. Эта возможность повышает производительность векторизированных вычислений, которые широко применяются в математических, научных и графических приложениях.
  
Ниже перечислены типы .NET с поддержкой SIMD:

- Типы <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3> и <xref:System.Numerics.Vector4>, которые представляют векторы с 2, 3 и 4 значениями <xref:System.Single>.

- Два матричных типа: <xref:System.Numerics.Matrix3x2> для представления матрицы 3×2 и <xref:System.Numerics.Matrix4x4> для представления матрицы 4×4.

- Тип <xref:System.Numerics.Plane>, который представляет плоскость в трехмерном пространстве.

- Тип <xref:System.Numerics.Quaternion>, который представляет вектор, используемый для кодирования трехмерных физических вращений.

- Тип <xref:System.Numerics.Vector%601>, который представляет вектор указанного числового типа и реализует широкий набор операторов, оптимизированных для поддержки SIMD. <xref:System.Numerics.Vector%601> имеет фиксированное число экземпляров, но его значение <xref:System.Numerics.Vector%601.Count%2A?displayProperty=nameWithType> зависит от характеристик ЦП на компьютере, на котором выполняется код.
  > [!NOTE]
  > Тип <xref:System.Numerics.Vector%601> не входит в .NET Framework. Чтобы получить доступ к этому типу, необходимо установить пакет NuGet [System.Numerics.Vectors](https://www.nuget.org/packages/System.Numerics.Vectors).
  
Типы с поддержкой SIMD реализованы так, что их можно использовать на оборудовании и (или) с JIT-компиляторами, которые не поддерживают SIMD. Чтобы получить преимущество от использования инструкций SIMD, необходимо запустить 64-разрядное приложение в среде выполнения с компилятором RyuJIT. Он входит в состав .NET Core и .NET Framework 4.6 и более поздних версий. Он добавляет поддержку SIMD при нацеливании на 64-разрядные процессоры.

## <a name="see-also"></a>См. также раздел

- [Основные сведения о приложениях .NET Framework](application-essentials.md)
- [Строки стандартных числовых форматов](base-types/standard-numeric-format-strings.md)
