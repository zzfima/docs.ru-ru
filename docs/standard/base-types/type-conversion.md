---
title: Преобразование типов в .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- widening conversions
- explicit conversions
- narrowing conversions
- type conversion, about type conversion
- type conversion
- converting types
- narrowing coercion
- Explicit operator
- IConvertible interface
- base types, converting
- op_Implicit method
- widening coercion
- op_Explicit method
- Convert class
- implicit conversions
- Implicit operator
- data types [.NET Framework], converting
ms.assetid: ba36154f-064c-47d3-9f05-72f93a7ca96d
ms.openlocfilehash: 0e88303f2bac2dae90a97f9d2de92af1d2a0f80d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73976492"
---
# <a name="type-conversion-in-the-net-framework"></a>Преобразование типов в .NET Framework
Каждое значение имеет соответствующий тип, который определяет атрибуты, такие как объем памяти, выделяемой значению, диапазон возможных значений и доступные элементы. Многие значения можно выразить несколькими типами. Например, число 4 можно выразить как целое число или как число с плавающей запятой. Преобразование типа создает значение нового типа, эквивалентное значению старого типа, но при этом не обязательно сохраняется идентичность (или точные значения) первоначального объекта.  
  
 Платформа .NET Framework автоматически поддерживает указанные далее преобразования.  
  
- Преобразование из производного класса в базовый класс. Это означает, например, что экземпляр любого класса или структуры может быть преобразован в экземпляр <xref:System.Object>.  Для этого преобразования не требуется оператор приведения или преобразования.  
  
- Преобразование из базового класса обратно в исходный производный класс. В C# для этого преобразования требуется оператор приведения. В Visual Basic требуется оператор `CType`, если `Option Strict` включен.  
  
- Преобразование из типа, реализующего интерфейс, в объект интерфейса, представляющий этот интерфейс. Для этого преобразования не требуется оператор приведения или преобразования.  
  
- Преобразование из объекта интерфейса обратно в исходный тип, который реализует этот интерфейс.  В C# для этого преобразования требуется оператор приведения. В Visual Basic требуется оператор `CType`, если `Option Strict` включен.  
  
 Помимо этих автоматических преобразований .NET Framework предоставляет несколько возможностей для поддержки преобразования пользовательского типа. В число этих требований входят следующие:  
  
- Оператор `Implicit`, определяющий доступные расширяющие преобразования между типами. Дополнительные сведения см. в разделе [Неявные преобразования с помощью оператора Implicit](#implicit-conversion-with-the-implicit-operator).  
  
- Оператор `Explicit`, определяющий доступные сужающие преобразования между типами. Дополнительные сведения см. в разделе [Явные преобразования с помощью оператора Explicit](#explicit-conversion-with-the-explicit-operator).  
  
- Интерфейс <xref:System.IConvertible>, определяющий преобразования в каждый из базовых типов данных платформы .NET Framework. Дополнительные сведения см. в разделе [Интерфейс IConvertible](#the-iconvertible-interface).  
  
- Класс <xref:System.Convert>, предоставляющий набор методов, реализующих методы интерфейса <xref:System.IConvertible>. Дополнительные сведения см. в разделе [Класс Convert](#the-convert-class).  
  
- Класс <xref:System.ComponentModel.TypeConverter>, являющийся базовым классом, который может быть расширен для поддержки преобразования указанного типа в любой другой тип. Дополнительные сведения см. в разделе [Класс TypeConverter](#the-typeconverter-class).  

## <a name="implicit-conversion-with-the-implicit-operator"></a>Неявное преобразование с помощью оператора Implicit  
 Расширяющие преобразования предполагают создание нового значения из значения существующего типа, имеющего более ограничивающий диапазон или более ограниченный список членов, чем целевой тип. Расширяющие преобразования не могут привести к потере данных (хотя способны дать в результате меньшую точность). Поскольку потеря данных исключена, компиляторы могут обрабатывать преобразование неявно или прозрачно без необходимости использования метода явного преобразования или оператора приведения.  
  
> [!NOTE]
> Хотя код, используемый для неявного преобразования, может вызывать метод преобразования или использовать оператор приведения, применение таких методов компиляторами, поддерживающими неявные преобразования, не требуется.  
  
 Например, тип <xref:System.Decimal> поддерживает неявные преобразования значений из типов <xref:System.Byte>, <xref:System.Char>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.SByte>, <xref:System.UInt16>, <xref:System.UInt32> и <xref:System.UInt64>. В следующем примере демонстрируются некоторые неявные преобразования при присвоении значений переменной <xref:System.Decimal>.  
  
 [!code-csharp[Conceptual.Conversion#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/implicit1.cs#1)]
 [!code-vb[Conceptual.Conversion#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/implicit1.vb#1)]  
  
 Если компилятор конкретного языка поддерживает настраиваемые операторы, можно также определить неявные преобразования в собственных настраиваемых типах. В следующем примере показана частичная реализация знакового типа данных byte с именем `ByteWithSign`, использующего представление знака и величины. Он поддерживает неявное преобразование значений <xref:System.Byte> и <xref:System.SByte> в значения `ByteWithSign`.  
  
 [!code-csharp[Conceptual.Conversion#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/implicit1.cs#2)]
 [!code-vb[Conceptual.Conversion#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/implicit1.vb#2)]  
  
 В клиентском коде затем можно объявить переменную `ByteWithSign` и присвоить ей значения <xref:System.Byte> и <xref:System.SByte>, не выполняя явные преобразования и не используя операторы приведения, как показано в следующем примере.  
  
 [!code-csharp[Conceptual.Conversion#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/implicit1.cs#3)]
 [!code-vb[Conceptual.Conversion#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/implicit1.vb#3)]  

## <a name="explicit-conversion-with-the-explicit-operator"></a>Явное преобразование с помощью оператора Explicit  
 Сужающие преобразования предполагают создание нового значения из значения существующего типа, имеющего более широкий диапазон или список членов, чем у целевого типа. Поскольку сужающее преобразование может привести к потере данных, компиляторы, как правило, требуют выполнять преобразование явно посредством вызова метода преобразования или оператора приведения. Это означает, что преобразование должно обрабатываться явно в коде разработчика.  
  
> [!NOTE]
> Основная цель требования явного использования метода преобразования или оператора приведения заключается в информировании разработчика о возможной потере данных или исключении <xref:System.OverflowException>, чтобы это можно было учесть в коде. При этом некоторые компиляторы могут опускать это требование. Например, в Visual Basic, если параметр `Option Strict` выключен (по умолчанию), компилятор Visual Basic предпринимает попытку выполнения сужающего преобразования неявно.  
  
 Например, типы данных <xref:System.UInt32>, <xref:System.Int64> и <xref:System.UInt64> имеют диапазоны, покрывающие диапазон типа данных <xref:System.Int32>, как показано в таблице ниже.  
  
|Type|Сравнение с диапазоном Int32|  
|----------|------------------------------------|  
|<xref:System.Int64>|<xref:System.Int64.MaxValue?displayProperty=nameWithType> больше, чем <xref:System.Int32.MaxValue?displayProperty=nameWithType>, а <xref:System.Int64.MinValue?displayProperty=nameWithType> меньше (имеет больший отрицательный диапазон), чем <xref:System.Int32.MinValue?displayProperty=nameWithType>.|  
|<xref:System.UInt32>|Значение <xref:System.UInt32.MaxValue?displayProperty=nameWithType> больше значения <xref:System.Int32.MaxValue?displayProperty=nameWithType>.|  
|<xref:System.UInt64>|Значение <xref:System.UInt64.MaxValue?displayProperty=nameWithType> больше значения <xref:System.Int32.MaxValue?displayProperty=nameWithType>.|  
  
 Для обработки таких сужающих преобразований .NET Framework позволяет типам определять оператор `Explicit`. Компиляторы отдельных языков могут реализовывать этот оператор, используя свой собственный синтаксис или вызывая член класса <xref:System.Convert> для преобразования. (Дополнительные сведения о <xref:System.Convert> см. в разделе [Класс Convert](#the-convert-class) далее в этом разделе.) Следующий пример иллюстрирует использование функций языка для обработки явного преобразования этих потенциально выходящих из диапазона целочисленных значений в значения <xref:System.Int32>.  
  
 [!code-csharp[Conceptual.Conversion#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/explicit1.cs#4)]
 [!code-vb[Conceptual.Conversion#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/explicit1.vb#4)]  
  
 Результаты явного преобразования в разных языках могут быть различными. Кроме того, эти результаты могут отличаться от значений, возвращаемых соответствующим методом <xref:System.Convert>. Например, если значение типа <xref:System.Double>, равное 12,63251, преобразуется в <xref:System.Int32>, метод Visual Basic `CInt` и метод платформы .NET Framework <xref:System.Convert.ToInt32%28System.Double%29?displayProperty=nameWithType> округляют <xref:System.Double>, возвращая значение 13, а оператор C# `(int)` усекает значение <xref:System.Double>, возвращая значение 12. Аналогично оператор C# `(int)` не поддерживает преобразование логических значений в целочисленные, а метод Visual Basic `CInt` преобразует значение `true` в –1. С другой стороны, метод <xref:System.Convert.ToInt32%28System.Boolean%29?displayProperty=nameWithType> преобразует значение `true` в 1.  
  
 Большинство компиляторов допускают явное преобразование как с проверкой, так и без проверки. Если при выполнении преобразования с проверкой преобразуемое значение находится вне диапазона допустимых значений конечного типа, создается исключение <xref:System.OverflowException>. Если в такой же ситуации выполнять преобразование без проверки, то исключение может не быть создано, но результат преобразования в данном случае неизвестен, и на выходе может быть получено неверное значение.  
  
> [!NOTE]
> В C# для преобразования с проверкой используется ключевое слово `checked`, добавляемое к оператору приведения, или параметр компилятора `/checked+`. Для преобразования без проверки используется ключевое слово `unchecked`, добавляемое к оператору приведения, или параметр компилятора `/checked-`. По умолчанию явное преобразование выполняется без проверки. В Visual Basic для преобразования с проверкой необходимо снять флажок **Отключить проверку переполнения для целочисленных значений** в диалоговом окне **Дополнительные параметры компилятора** проекта или воспользоваться параметром компилятора `/removeintchecks-`. Для преобразования без проверки необходимо установить флажок **Отключить проверку переполнения для целочисленных значений** в диалоговом окне **Дополнительные параметры компилятора** проекта или воспользоваться параметром компилятора `/removeintchecks+`. По умолчанию явное преобразование выполняется с проверкой.  
  
 В следующем примере на C# используются ключевые слова `checked` и `unchecked` для демонстрации разницы поведения при преобразовании выходящего за пределы диапазона значения <xref:System.Byte> в <xref:System.Byte>. При выполнении преобразования с проверкой создается исключение, а при выполнении преобразования без проверки значение <xref:System.Byte.MaxValue?displayProperty=nameWithType> присваивается переменой <xref:System.Byte>.  
  
 [!code-csharp[Conceptual.Conversion#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/explicit1.cs#12)]  
  
 Если компилятор конкретного языка поддерживает настраиваемые перегруженные операторы, можно также определить явные преобразования в собственных настраиваемых типах. В следующем примере показана частичная реализация знакового типа данных byte с именем `ByteWithSign`, использующего представление знака и величины. Он поддерживает явное преобразование значений <xref:System.Int32> и <xref:System.UInt32> в значения `ByteWithSign`.  
  
 [!code-csharp[Conceptual.Conversion#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/explicit1.cs#5)]
 [!code-vb[Conceptual.Conversion#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/explicit1.vb#5)]  
  
 Если присваивание включает оператор приведения или метод преобразования, как показано в следующем примере, в клиентском коде можно объявить переменную `ByteWithSign` и присвоить ей значения <xref:System.Int32> и <xref:System.UInt32>.  
  
 [!code-csharp[Conceptual.Conversion#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/explicit1.cs#6)]
 [!code-vb[Conceptual.Conversion#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/explicit1.vb#6)]  

## <a name="the-iconvertible-interface"></a>Интерфейс IConvertible  
 Для поддержки преобразования любого типа в базовый тип среды CLR .NET Framework предоставляет интерфейс <xref:System.IConvertible>. Реализующий тип должен предоставить следующее:  
  
- Метод, возвращающий объект <xref:System.TypeCode> реализующего типа.  
  
- Метод для преобразования реализующего типа в каждый из базовых типов среды CLR (<xref:System.Boolean>, <xref:System.Byte>, <xref:System.DateTime>, <xref:System.Decimal>, <xref:System.Double> и т. д.).  
  
- Универсальный метод преобразования экземпляра реализующего типа в другой заданный тип. Неподдерживаемые преобразования должны порождать исключение <xref:System.InvalidCastException>.  
  
 Все базовые типы среды CLR (т. е. <xref:System.Boolean>, <xref:System.Byte>, <xref:System.Char>, <xref:System.DateTime>, <xref:System.Decimal>, <xref:System.Double>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.SByte>, <xref:System.Single>, <xref:System.String>, <xref:System.UInt16>, <xref:System.UInt32> и <xref:System.UInt64>), а также типы <xref:System.DBNull> и <xref:System.Enum> реализуют интерфейс <xref:System.IConvertible>. Тем не менее это явные реализации интерфейса; метод преобразования можно вызвать только посредством переменной интерфейса <xref:System.IConvertible>, как показано в следующем примере. В этом примере показано преобразование значения <xref:System.Int32> в эквивалентное значение <xref:System.Char>.  
  
 [!code-csharp[Conceptual.Conversion#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/iconvertible1.cs#7)]
 [!code-vb[Conceptual.Conversion#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/iconvertible1.vb#7)]  
  
 Требование вызова метода преобразования для интерфейса, а не для реализующего типа, делает явные реализации интерфейса относительно требовательными к ресурсам. Вместо этого для выполнения преобразования между базовыми типами среды CLR рекомендуется вызывать соответствующий член класса <xref:System.Convert>. Дополнительные сведения см. в следующем разделе, [Класс Convert](#the-convert-class).  
  
> [!NOTE]
> В дополнение к интерфейсу <xref:System.IConvertible> и классу <xref:System.Convert>, предоставленным в .NET Framework, отдельные языки могут также предоставлять различные способы выполнения преобразования. Например, в C# используются операторы приведения типов. В Visual Basic используются функции преобразования, реализованные в компиляторе, такие как `CType``CInt` и `DirectCast`.  
  
 Интерфейс <xref:System.IConvertible> по большей части предназначен для поддержки преобразований между базовыми типами в .NET Framework. При этом данный интерфейс также можно реализовать и в пользовательском типе, чтобы обеспечить поддержку преобразования этого типа в другой пользовательский тип. Дополнительные сведения см. в разделе [Настраиваемые преобразования с использованием метода ChangeType](#custom-conversions-with-the-changetype-method) ниже.

## <a name="the-convert-class"></a>Класс Convert
 Хотя каждая реализация интерфейса <xref:System.IConvertible> базового типа может быть вызвана для выполнения преобразования типа, вызов методов класса <xref:System.Convert?displayProperty=nameWithType> является рекомендуемым и не зависящим от языка способом преобразования одного базового типа в другой. Кроме этого, метод <xref:System.Convert.ChangeType%28System.Object%2CSystem.Type%2CSystem.IFormatProvider%29?displayProperty=nameWithType> может использоваться для преобразования указанного настраиваемого типа в другой тип.  
  
### <a name="conversions-between-base-types"></a>Преобразования между базовыми типами  
 Класс <xref:System.Convert> обеспечивает не зависящий от языка способ выполнения преобразований между базовыми типами и доступен во всех языках, предназначенных для среды CLR. Он предоставляет набор методов для расширяющих и сужающих преобразований и создает исключение <xref:System.InvalidCastException> для преобразований, которые не поддерживаются (например, для преобразования значения <xref:System.DateTime> в целочисленное значение). Сужающие преобразования выполняются в проверяемом контексте, а если преобразование завершается неудачей, порождается исключение <xref:System.OverflowException>.  
  
> [!IMPORTANT]
> Поскольку класс <xref:System.Convert> включает методы преобразования для каждого базового типа, он исключает необходимость вызова явной реализации интерфейса <xref:System.IConvertible> каждого из базовых классов.  
  
 В следующем примере показано применение класса <xref:System.Convert?displayProperty=nameWithType> для выполнения нескольких расширяющих и сужающих преобразований между базовыми типами платформы .NET Framework.  
  
 [!code-csharp[Conceptual.Conversion#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/convert1.cs#8)]
 [!code-vb[Conceptual.Conversion#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/convert1.vb#8)]  
  
 В некоторых случаях, особенно при преобразовании значений с плавающей запятой, преобразование может предполагать потерю точности, даже если исключение <xref:System.OverflowException> не создается. В следующем примере показана потеря точности. В этом случае значение <xref:System.Decimal> после преобразования в <xref:System.Double> имеет меньшую точность (меньше значимых цифр). Во втором случае при преобразовании значения <xref:System.Double> оно округляется с 42,72 до 43, чтобы было выполнено преобразование.  
  
 [!code-csharp[Conceptual.Conversion#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/convert1.cs#9)]
 [!code-vb[Conceptual.Conversion#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/convert1.vb#9)]  
  
 См. дополнительные сведения о [таблице, в которой перечислены расширяющие и сужающие преобразования](../../../docs/standard/base-types/conversion-tables.md), поддерживаемые классом <xref:System.Convert>.  

### <a name="custom-conversions-with-the-changetype-method"></a>Настраиваемые преобразования с использованием метода ChangeType  
 В дополнение к поддержке преобразований в каждый из базовых типов класс <xref:System.Convert> может использоваться для преобразования настраиваемых типов в один или несколько предопределенных типов. Это преобразование выполняется с помощью метода <xref:System.Convert.ChangeType%28System.Object%2CSystem.Type%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, который, в свою очередь, служит оболочкой вызова метода <xref:System.IConvertible.ToType%2A?displayProperty=nameWithType> параметра `value`. Это означает, что объект, представленный параметром `value`, должен предоставить реализацию интерфейса <xref:System.IConvertible>.  
  
> [!NOTE]
> Поскольку методы <xref:System.Convert.ChangeType%28System.Object%2CSystem.Type%29?displayProperty=nameWithType> и <xref:System.Convert.ChangeType%28System.Object%2CSystem.Type%2CSystem.IFormatProvider%29?displayProperty=nameWithType> используют объект <xref:System.Type> для указания типа целевого объекта, в который преобразуется `value`, их можно использовать для выполнения динамического преобразования в объект, тип которого неизвестен во время компиляции. Однако обратите внимание, что реализация <xref:System.IConvertible> значения `value` все равно должна поддерживать данное преобразование.  
  
 В следующем примере показана возможная реализация интерфейса <xref:System.IConvertible>, позволяющая преобразовать объект `TemperatureCelsius` в `TemperatureFahrenheit` или наоборот. В примере определяется базовый класс, `Temperature`, который реализует интерфейс <xref:System.IConvertible> и переопределяет метод <xref:System.Object.ToString%2A?displayProperty=nameWithType>. Производные классы `TemperatureCelsius` и `TemperatureFahrenheit` переопределяют методы `ToType` и `ToString` базового класса.  
  
 [!code-csharp[Conceptual.Conversion#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/iconvertible2.cs#10)]
 [!code-vb[Conceptual.Conversion#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/iconvertible2.vb#10)]  
  
 В следующем примере показано несколько вызовов реализаций интерфейса <xref:System.IConvertible> для преобразования объектов `TemperatureCelsius` в объекты `TemperatureFahrenheit` и наоборот.  
  
 [!code-csharp[Conceptual.Conversion#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/iconvertible2.cs#11)]
 [!code-vb[Conceptual.Conversion#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/iconvertible2.vb#11)]  

## <a name="the-typeconverter-class"></a>Класс TypeConverter  
 Платформа .NET Framework также позволяет определить преобразователь типов для пользовательского типа путем расширения класса <xref:System.ComponentModel.TypeConverter?displayProperty=nameWithType> и сопоставления преобразователя с типом через атрибут <xref:System.ComponentModel.TypeConverterAttribute?displayProperty=nameWithType>. В следующей таблице выделены различия между этим подходом и реализацией интерфейса <xref:System.IConvertible> для настраиваемого типа.  
  
> [!NOTE]
> Поддержка во время разработки может быть предоставлена для настраиваемого типа лишь при условии, что для него определен преобразователь типа.  
  
|Преобразование с использованием TypeConverter|Преобразование с использованием IConvertible|  
|------------------------------------|-----------------------------------|  
|Реализуется для настраиваемого типа посредством создания отдельного класса-наследника <xref:System.ComponentModel.TypeConverter>. Производный класс связывается с настраиваемым типом посредством атрибута <xref:System.ComponentModel.TypeConverterAttribute>.|Реализуется настраиваемым типом для выполнения преобразования. Пользователь типа вызывает метод преобразования <xref:System.IConvertible> для типа.|  
|Может использоваться как во время разработки, так и во время выполнения.|Может использоваться только во время выполнения.|  
|Использует отражение, поэтому выполняется медленнее, чем преобразование, использующее <xref:System.IConvertible>.|Не использует отражения.|  
|Обеспечивает двустороннее преобразование настраиваемого типа в другие типы данных и наоборот. Например, тип <xref:System.ComponentModel.TypeConverter>, определенный для `MyType`, позволяет выполнять преобразования из `MyType` в <xref:System.String> и из <xref:System.String> в `MyType`.|Обеспечивает преобразование из настраиваемого типа в другие типы данных, но не наоборот.|  
  
 Дополнительные сведения о выполнении преобразований с помощью преобразователей типов см. в разделе <xref:System.ComponentModel.TypeConverter?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Convert?displayProperty=nameWithType>
- <xref:System.IConvertible>
- [Таблицы преобразования типов](../../../docs/standard/base-types/conversion-tables.md)
