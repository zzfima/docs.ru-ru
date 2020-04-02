---
title: Независимость от языка и независимые от языка компоненты
description: Сведения о том, как можно вести разработку на одном из множества языков, поддерживаемых в .NET, например C#, C++/CLI, F#, IronPython, VB, Visual COBOL и PowerShell.
ms.date: 07/22/2016
dev_langs:
- csharp
- vb
ms.technology: dotnet-standard
ms.assetid: 2dbed1bc-86f5-43cd-9a57-adbb1c5efba4
ms.openlocfilehash: 03751fa3758c239cb9eea5fe826dff66c1c1605b
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249582"
---
# <a name="language-independence-and-language-independent-components"></a>Независимость от языка и независимые от языка компоненты

.NET является независимой от языка. Это означает, что вести разработку можно на одном из множества языков, предназначенных для реализаций .NET, например C#, F# и Visual Basic. Чтобы использовать типы и члены библиотек классов, разработанных для реализаций .NET, не требуется знать их исходный язык и следовать его правилам. Если вы разрабатываете компоненты, они будут доступны всем приложениям .NET вне зависимости от используемого вами языка.

> [!NOTE]
> В первой части этой статьи рассматривается, как создать компоненты, независимые от языка, чтобы использовать их в приложениях, написанных на любом языке. Кроме того, компонент и приложение могут состоять из фрагментов кода на разных языках. См. раздел [Взаимная совместимость кодов на разных языках](#cross-language-interoperability) во второй части этой статьи.

Чтобы обеспечить полное взаимодействие между объектами вне зависимости от их языка, объекты должны предоставлять вызывающим объектам возможности, общие для всех языков. Этот общий набор компонентов определяется общеязыковой спецификацией (спецификацией CLS) — рядом правил, который применяется к создаваемым сборкам. Спецификация CLS определяется в разделе I, пп. 7–11, [стандарт ECMA-335: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm).

Если компонент соответствует спецификации CLS, к нему можно обращаться из кода сборок, написанных на любом языке программирования, поддерживающем CLS. Чтобы проверить, является ли компонент CLS-совместимым, примените к исходному коду атрибут [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) во время компиляции. Дополнительные сведения см. в разделе [Атрибут CLSCompliantAttribute](#the-clscompliantattribute-attribute).

Содержание этой статьи

* [Правила CLS-совместимости](#cls-compliance-rules)

  * [Сигнатуры типов и членов типов](#types-and-type-member-signatures)

  * [Соглашения об именовании](#naming-conventions)

  * [Преобразование типов](#type-conversion)

  * [Массивы](#arrays)

  * [Интерфейсы](#interfaces)

  * [Перечисления](#enumerations)

  * [Обзор членов типов](#type-members-in-general)

  * [Доступность членов](#member-accessibility)

  * [Универсальные типы и члены](#generic-types-and-members)

  * [Конструкторы](#constructors)

  * [Свойства](#properties)

  * [События](#events)

  * [Перегрузки](#overloads)

  * [Исключения](#exceptions)

  * [Атрибуты](#attributes)

* [Атрибут CLSCompliantAttribute](#the-clscompliantattribute-attribute)

* [Взаимная совместимость кодов на разных языках](#cross-language-interoperability)

## <a name="cls-compliance-rules"></a>Правила CLS-совместимости

В этом разделе рассматриваются правила создания CLS-совместимого компонента. Полный список правил см. в разделе I, п. 11, [стандарта ECMA-335: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm).

> [!NOTE]
> Каждое правило CLS-совместимости спецификации CLS определяет требования к потребителям (разработчикам, которые программным образом обращаются к CLS-совместимому компоненту), платформам (разработчикам, которые используют компилятор языка для создания CLS-совместимых библиотек) и расширителям (разработчикам инструментов — например, компиляторов языка или синтаксических анализаторов кода, создающих CLS-совместимые компоненты). В этой статье описываются требования к платформам. Однако следует принимать во внимание, что некоторые правила в отношении расширителей могут также применяться к сборкам, создаваемым с помощью [Reflection.Emit](xref:System.Reflection.Emit).

Чтобы создать компонент, независимый от языка, достаточно применить правила CLS-совместимости к открытому интерфейсу компонента. Закрытая реализация может не соответствовать спецификации.

> [!IMPORTANT]
> Правила CLS-совместимости применяются только к открытому интерфейсу компонента и не применяются к закрытой реализации.

Например, за исключением чисел типа [Byte](xref:System.Byte) целые числа без знака не являются CLS-совместимыми. В следующем примере класс `Person` предоставляет свойство `Age`, имеющее тип [UInt16](xref:System.UInt16), поэтому в коде отображается предупреждение компилятора.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person
{
   private UInt16 personAge = 0;

   public UInt16 Age
   { get { return personAge; } }
}
// The attempt to compile the example displays the following compiler warning:
//    Public1.cs(10,18): warning CS3003: Type of 'Person.Age' is not CLS-compliant
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Person
   Private personAge As UInt16

   Public ReadOnly Property Age As UInt16
      Get
         Return personAge
      End Get
   End Property
End Class
' The attempt to compile the example displays the following compiler warning:
'    Public1.vb(9) : warning BC40027: Return type of function 'Age' is not CLS-compliant.
'
'       Public ReadOnly Property Age As UInt16
'                                ~~~
```

Чтобы класс Person удовлетворял требованиям CLS, можно изменить тип свойства `Age` с `UInt16` на [Int16](xref:System.Int16) — 16-битное целое число со знаком, которое является CLS-совместимым. Тип закрытого поля `personAge` изменять не требуется.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person
{
   private Int16 personAge = 0;

   public Int16 Age
   { get { return personAge; } }
}
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Person
   Private personAge As UInt16

   Public ReadOnly Property Age As Int16
      Get
         Return CType(personAge, Int16)
      End Get
   End Property
End Class
```

Публичный интерфейс библиотеки состоит из:

* определений открытых классов;

* определений открытых членов открытых классов и определений членов, доступных производным классам (т. е. защищенных членов);

* параметров и возвращаемых типов открытых методов открытых классов, а также параметров и возвращаемых типов методов, доступных производным классам.

В следующей таблице представлены правила CLS-совместимости. Текст правил взят дословно из [стандарт ECMA-335: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm), авторские права: Ecma International, 2012. Дополнительные сведения об этих правилах вы найдете в следующих разделах.

Категория | См. | Правило | Номер правила
-------- | --- | ---- | -----------
Специальные возможности | [Доступность членов](#member-accessibility) | При переопределении унаследованных методов не должна изменяться доступность. Исключение составляют методы, унаследованные из другой сборки с доступностью `family-or-assembly`. В таких случаях переопределенный метод должен иметь доступность `family`. | 10
Специальные возможности | [Доступность членов](#member-accessibility) | Видимость и доступность типов и членов должна быть такой, чтобы типы в сигнатуре любого члена были видимы и доступны всегда, когда видим или доступен сам член. Например, открытый метод, видимый за пределами его сборки, не должен иметь аргументов, типы которых видимы только в пределах сборки. Видимость и доступность типов, составляющих экземпляры универсального типа, используемого в сигнатуре любого члена, должна быть такой, чтобы типы в сигнатуре любого члена были видимы и доступны всегда, когда видим или доступен сам член. Например, экземпляр универсального типа в сигнатуре члена, видимого вне его сборки, не должен иметь универсальных аргументов, тип которых видимы только в пределах сборки. | 12
Массивы | [Массивы](#arrays) | Элементы массива должны быть CLS-совместимого типа, а измерения массива — иметь нижнюю границу, равную нулю. Для различения перегрузок достаточно, чтобы элемент был массивом и у него был задан тип элементов. Если перегрузка основана на нескольких типах массивов, типы элементов должны быть именованными. | 16
Атрибуты | [Атрибуты](#attributes) | Атрибуты должны иметь тип [System.Attribute](xref:System.Attribute) или унаследованный от него. | 41
Атрибуты | [Атрибуты](#attributes) | В спецификации CLS разрешено только подмножество кодировок настраиваемых атрибутов. Единственными типами, которые должны иметь эти кодировки (см. раздел IV), являются: [System.Type](xref:System.Type), [System.String](xref:System.String), [System.Char](xref:System.Char), [System.Boolean](xref:System.Boolean), [System.Byte](xref:System.Byte), [System.Int16](xref:System.Int16), [System.Int32](xref:System.Int32), [System.Int64](xref:System.Int64), [System.Single](xref:System.Single), [System.Double](xref:System.Double) и любой тип перечисления на основе CLS-совместимого базового целочисленного типа. | 34
Атрибуты | [Атрибуты](#attributes) | В спецификации CLS запрещены публично видимые обязательные модификаторы (`modreq`, см. раздел II), но разрешены необязательные модификаторы (`modopt`, см. раздел II), которые не распознаются. | 35
Конструкторы | [Конструкторы](#constructors) | Доступ к данным унаследованного экземпляра возможен после того, как конструктор объекта вызвал какой-либо конструктор экземпляра базового класса. (Правило не относится к типам значений, которым не требуются конструкторы).  | 21
Конструкторы | [Конструкторы](#constructors) | Конструктор объекта должен вызываться только в ходе создания объекта и объекты не должны инициализироваться дважды. | 22
Перечисления | [Перечисления](#enumerations) | Базовый тип перечисления должен быть встроенным целочисленным типом CLS, имя поля должно быть"value__" и это поле должно быть отмечено атрибутом `RTSpecialName`. |  7
Перечисления | [Перечисления](#enumerations) | Существует два вида перечислений, которые различаются наличием/отсутствием настраиваемого атрибута [System.FlagsAttribute](xref:System.FlagsAttribute) (см. раздел IV библиотеки). Одно представляет именованные целочисленные значения, другое — именованные битовые флаги, сочетая которые, можно создавать значения без имени. Перечисление `enum` может принимать и другие значения. |  8
Перечисления | [Перечисления](#enumerations) | Статические поля литералов перечисления должны иметь тип перечисления. |  9
События | [События](#events) | Реализующие событие методы должны быть отмечены в метаданных атрибутом `SpecialName`. |29
События | [События](#events) | Событие и его методы доступа должны иметь одинаковую доступность. |30
События | [События](#events) | У события должны либо присутствовать, либо отсутствовать оба метода `add` и `remove`. |31
События | [События](#events) | Методы `add` и `remove` для события должны иметь один параметр, тип которого определяет тип события. Тип параметра должен быть производным от [System.Delegate](xref:System.Delegate). |32
События | [События](#events) | События должны следовать определенному шаблону именования. Атрибут SpecialName, упоминаемый в правиле 29 спецификации CLS, должен игнорироваться в конкретных сравнениях имен и соответствовать правилам в отношении идентификаторов.  |33
Исключения | [Исключения](#exceptions) | Объекты исключений должны иметь тип [System.Exception](xref:System.Exception) или унаследованный от него тип. Однако не требуется, чтобы CLS-совместимые методы блокировали распространение других типов исключений. | 40
Общее | [Правила CLS-совместимости](#cls-compliance-rules) | Правила CLS-совместимости применяются только к тем составляющим типа, которые доступны или видны за пределами определяющей сборки. | 1
Общее | [Правила CLS-совместимости](#cls-compliance-rules) | Члены типов, не соответствующих правилам CLS-совместимости, не должны быть отмечены как CLS-совместимые. | 2
Универсальные шаблоны | [Универсальные типы и члены](#generic-types-and-members) | У вложенного типа должно не меньше универсальных параметров, чем у включающего его типа. Универсальные параметры вложенного типа соответствуют по позиции универсальным параметрам включающего типа.  | 42
Универсальные шаблоны | [Универсальные типы и члены](#generic-types-and-members) | В имени универсального типа должны кодироваться все параметры типа, объявленные в невложенном типе или введенные во вложенном типе, в соответствии с определенными выше правилами. | 43
Универсальные шаблоны | [Универсальные типы и члены](#generic-types-and-members) | В универсальном типе должны повторно объявляться ограничения, обеспечивающие соответствие всем ограничениям базового типа и интерфейсов. | 44
Универсальные шаблоны | [Универсальные типы и члены](#generic-types-and-members) | Типы, используемые в качестве ограничений универсальных параметров, должны быть CLS-совместимыми. | 45
Универсальные шаблоны | [Универсальные типы и члены](#generic-types-and-members) | Реализация видимости и доступности членов (включая вложенные типы) в экземплярах универсального типа должна ограничиваться областью конкретного экземпляра, а не объявлением универсального типа. С учетом этого также применяется правило 12 CLS-совместимости, касающееся видимости и доступности. | 46
Универсальные шаблоны | [Универсальные типы и члены](#generic-types-and-members) | Каждый абстрактный или виртуальный универсальный метод должен иметь конкретную (не абстрактную) реализацию по умолчанию. | 47
Интерфейсы | [Интерфейсы](#interfaces) | CLS-совместимые интерфейсы должны реализовываться без методов, не соответствующих правилам CLS-совместимости. | 18
Интерфейсы | [Интерфейсы](#interfaces) | CLS-совместимые интерфейсы не могут определять статические методы и поля. | 19
Участники | [Обзор членов типов](#type-members-in-general) | Глобальные статические (static) поля и методы не совместимы с CLS. | 36
Участники | -- | Значение статического поля литерала задается с помощью метаданных инициализации поля. У CLS-совместимого литерала тип значения должен совпадать с типом литерала (или базовым типом, если литерал — перечисление `enum`). | 13
Участники | [Обзор членов типов](#type-members-in-general) | Ограничение vararg не входит в спецификацию CLS. В спецификации поддерживается только стандартное соглашение об управляемых вызовах. | 15
Соглашения об именах | [Соглашения об именовании](#naming-conventions) | Допустимые в сборках открывающие и внутренние символы идентификаторов указаны в приложении 7 технического отчета 15 стандарта Юникода версии 3.0. См. [формы нормализации Юникода](https://www.unicode.org/unicode/reports/tr15/tr15-18.html). Идентификаторы должны иметь канонический формат, описанный в форме нормализации Юникода C. В рамках спецификации CLS два идентификатора считаются одинаковыми, если их записи в нижнем регистре совпадают (т. е. при взаимно-однозначном сопоставлении символов Юникода нижнего регистра без учета языкового стандарта). Таким образом, в рамках спецификации CLS отличия регистра недостаточно для различения идентификаторов. Однако чтобы переопределить наследуемое определение, требуется использовать точную кодировку исходного объявления. | 4
Перегрузка | [Соглашения об именовании](#naming-conventions) | Все имена, которые вводятся в CLS-совместимой области, должны быть различными независимо от типа, кроме случаев, когда имена одинаковы и разрешаются посредством перегрузки. Другими словами, в системе общих типов CTS разрешено давать одинаковое имя методу и полю, а в спецификации CLS — нет. | 5
Перегрузка | [Соглашения об именовании](#naming-conventions) | Поля и вложенные типы должны отличаться только идентификаторами, хотя в системе общих типов CTS могут отличаться сигнатуры. Методы, свойства и события с одинаковыми именами (при сравнении идентификаторов) должны отличаться не только типом возвращаемого значения, за исключением случаев из правила 39 спецификации CLS. | 6
Перегрузка | [Перегрузки](#overloads) | Перегружать можно только свойства и методы. | 37
Перегрузка | [Перегрузки](#overloads) |Свойства и методы могут перегружаться только на основе количества и типов их параметров, за исключением операторов преобразования `op_Implicit` и `op_Explicit`, которые также могут перегружаться на основе возвращаемого типа. | 38
Перегрузка | -- | Если в типе объявлены несколько CLS-совместимых методов с одним и тем же именем и они создают набор экземпляров типа с одинаковыми параметрами и возвращаемыми типами, эти методы должны быть семантически эквивалентны в экземплярах типа. | 48
Свойства | [Свойства](#properties) | Методы, которые реализуют получение и задание значения, должны быть отмечены в метаданных атрибутом `SpecialName`. | 24
Свойства | [Свойства](#properties) | Все методы доступа свойства должны быть либо одновременно статическими, виртуальными или экземплярами. | 26
Свойства | [Свойства](#properties) | Тип свойства, тип возвращаемого значения метода получения значения и тип последнего аргумента метода задания значения должны совпадать. Типы параметров свойства, типы параметров метода получения значения и типы параметров метода задания значения (за исключением его последнего параметра) должны совпадать. Все типы должны быть CLS-совместимыми и не могут быть управляемыми указателями (т. е. не могут передаваться по ссылке). | 27
Свойства | [Свойства](#properties) | Свойства должны следовать определенному шаблону именования. Атрибут `SpecialName`, упоминаемый в правиле 24 спецификации CLS, должен игнорироваться в соответствующих сравнениях имен и соответствовать правилам в отношении идентификаторов. Свойство должно иметь метод получения и/или задания значения. | 28
Преобразование типов | [Преобразование типов](#type-conversion) | При наличии оператора преобразования op_Implicit или op_Explicit необходимо предоставить альтернативный способ приведения. | 39
Типы | [Сигнатуры типов и членов типов](#types-and-type-member-signatures) | Упакованные типы значений не являются CLS-совместимыми. | 3
Типы | [Сигнатуры типов и членов типов](#types-and-type-member-signatures) | Все типы сигнатуры должны быть CLS-совместимыми. Все типы, составляющие экземпляры универсального типа, должны быть CLS-совместимыми. | 11
Типы | [Сигнатуры типов и членов типов](#types-and-type-member-signatures) | Типизированные ссылки несовместимы с CLS. | 14
Типы | [Сигнатуры типов и членов типов](#types-and-type-member-signatures) | Типы неуправляемых указателей не являются CLS-совместимыми. | 17
Типы | [Сигнатуры типов и членов типов](#types-and-type-member-signatures) | CLS-совместимые классы, типы значений и интерфейсы должны реализовываться без членов, не соответствующих правилам CLS-совместимости. | 20
Типы | [Сигнатуры типов и членов типов](#types-and-type-member-signatures) | [System.Object](xref:System.Object) является CLS-совместимым. Все другие CLS-совместимые классы должны наследоваться от CLS-совместимого класса. | 23

### <a name="types-and-type-member-signatures"></a>Сигнатуры типов и членов типов

Тип [System.Object](xref:System.Object) является CLS-совместимым. Это базовый тип всех типов объектов в системе типов .NET Framework. В платформе .NET Framework существует два вида наследования: неявное (например, класс [String](xref:System.String) неявно наследуется от класса `Object`) или явное (например, класс [CultureNotFoundException](xref:System.Globalization.CultureNotFoundException) явно наследуется от класса [ArgumentException](xref:System.ArgumentException), который явно наследуется от класса [Exception](xref:System.Exception)). Чтобы производный тип был CLS-совместимым, его базовый тип должен быть CLS-совместимыми.

В следующем примере рассматривается производный тип, базовый тип которого не является CLS-совместимым. Базовый класс `Counter` использует 32-битное целое число без знака в качестве счетчика. Поскольку этот класс реализует функцию счетчика с помощью переноса целого числа без знака, он помечается как не соответствующий правилам CLS-совместимости. Поэтому производный класс `NonZeroCounter` также не является CLS-совместимым.

```csharp
using System;

[assembly: CLSCompliant(true)]

[CLSCompliant(false)]
public class Counter
{
   UInt32 ctr;

   public Counter()
   {
      ctr = 0;
   }

   protected Counter(UInt32 ctr)
   {
      this.ctr = ctr;
   }

   public override string ToString()
   {
      return $"{ctr}). ";
   }

   public UInt32 Value
   {
      get { return ctr; }
   }

   public void Increment()
   {
      ctr += (uint) 1;
   }
}

public class NonZeroCounter : Counter
{
   public NonZeroCounter(int startIndex) : this((uint) startIndex)
   {
   }

   private NonZeroCounter(UInt32 startIndex) : base(startIndex)
   {
   }
}
// Compilation produces a compiler warning like the following:
//    Type3.cs(37,14): warning CS3009: 'NonZeroCounter': base type 'Counter' is not
//            CLS-compliant
//    Type3.cs(7,14): (Location of symbol related to previous warning)
```

```vb
<Assembly: CLSCompliant(True)>

<CLSCompliant(False)> _
Public Class Counter
   Dim ctr As UInt32

   Public Sub New
      ctr = 0
   End Sub

   Protected Sub New(ctr As UInt32)
      ctr = ctr
   End Sub

   Public Overrides Function ToString() As String
      Return $"{ctr}). "
   End Function

   Public ReadOnly Property Value As UInt32
      Get
         Return ctr
      End Get
   End Property

   Public Sub Increment()
      ctr += CType(1, UInt32)
   End Sub
End Class

Public Class NonZeroCounter : Inherits Counter
   Public Sub New(startIndex As Integer)
      MyClass.New(CType(startIndex, UInt32))
   End Sub

   Private Sub New(startIndex As UInt32)
      MyBase.New(CType(startIndex, UInt32))
   End Sub
End Class
' Compilation produces a compiler warning like the following:
'    Type3.vb(34) : warning BC40026: 'NonZeroCounter' is not CLS-compliant
'    because it derives from 'Counter', which is not CLS-compliant.
'
'    Public Class NonZeroCounter : Inherits Counter
'                 ~~~~~~~~~~~~~~
```

Все типы в сигнатурах членов, в том числе тип свойства и тип возвращаемого значения метода, должны быть CLS-совместимыми. Кроме того, в отношении универсальных типов применяются следующие правила:

* все типы, составляющие экземпляры универсального типа, должны быть CLS-совместимыми;

* все типы, используемые в качестве ограничений универсальных параметров, должны быть CLS-совместимыми.

[Система общих типов CTS](common-type-system.md) платформы .NET имеет ряд встроенных типов, которые поддерживаются непосредственно средой CLR и особым образом кодируются в метаданных сборки. В следующей таблице приводятся встроенные типы, которые являются CLS-совместимыми.

CLS-совместимый тип | Описание
------------------ | -----------
[Byte](xref:System.Byte) | 8-битное целое число без знака
[Int16](xref:System.Int16) | 16-битное целое число со знаком
[Int32](xref:System.Int32) | 32-битное целое число со знаком
[Int64](xref:System.Int64) | 64-битное целое число со знаком
[Single](xref:System.Single) | Число одинарной точности с плавающей запятой
[Double](xref:System.Double) | Число двойной точности с плавающей запятой
[Boolean](xref:System.Boolean) | Тип значения true или false
[Char](xref:System.Char) | Единица кода в кодировке UTF-16
[Decimal](xref:System.Decimal) | Десятичное число без плавающей запятой
[IntPtr](xref:System.IntPtr) | Указатель или дескриптор определяемого платформой размера
[String](xref:System.String) | Коллекция любого, в том числе нулевого, числа объектов Char

В следующей таблице приводятся встроенные типы, которые не являются CLS-совместимыми.

Тип, не являющийся CLS-совместимым | Описание | Альтернативный CLS-совместимый тип
------------------ | ----------- | -------------------------
[SByte](xref:System.SByte) | Тип данных — 8-битное целое число со знаком | [Int16](xref:System.Int16)
[UInt16](xref:System.UInt16) | 16-битное целое число без знака | [Int32](xref:System.Int32)
[UInt32](xref:System.UInt32) | 32-битное целое число без знака | [Int64](xref:System.Int64)
[UInt64](xref:System.UInt64) | 64-битное целое число без знака | [Int64](xref:System.Int64) (возможно переполнение), [BigInteger](xref:System.Numerics.BigInteger) или [Double](xref:System.Double)
[UIntPtr](xref:System.UIntPtr) | Дескриптор или указатель без знака | [IntPtr](xref:System.IntPtr)

В библиотеке классов .NET Framework и других библиотеках классов могут встречаться другие типы, не являющиеся CLS-совместимыми. Например:

* Упакованные типы значений. Следующий пример кода на C# создает класс с открытым свойством типа `int`* с именем `Value`. Так как `int`* — это упакованный тип значений, компилятор помечает, что он не соответствует правилам CLS-совместимости.

```csharp
using System;

[assembly:CLSCompliant(true)]

public unsafe class TestClass
{
   private int* val;

   public TestClass(int number)
   {
      val = (int*) number;
   }

   public int* Value {
      get { return val; }
   }
}
// The compiler generates the following output when compiling this example:
//        warning CS3003: Type of 'TestClass.Value' is not CLS-compliant
```

* Типизированные ссылки — особые конструкции, содержащие ссылку на объект и ссылку на тип.

Если тип не является CLS-совместимым, необходимо применить к нему атрибут [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) с параметром *isCompliant*, имеющим значение `false`. Дополнительные сведения см. в разделе [Атрибут CLSCompliantAttribute](#the-clscompliantattribute-attribute).

В следующем примере сигнатура метода и экземпляр универсального типа не являются CLS-совместимыми. Мы определяем класс `InvoiceItem`, имеющий свойство типа [UInt32](xref:System.UInt32), свойство типа [Nullable(Of UInt32)](xref:System.Nullable%601) и конструктор с параметрами типа `UInt32` и `Nullable(Of UInt32)`. При компиляции появляются четыре предупреждения.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class InvoiceItem
{
   private uint invId = 0;
   private uint itemId = 0;
   private Nullable<uint> qty;

   public InvoiceItem(uint sku, Nullable<uint> quantity)
   {
      itemId = sku;
      qty = quantity;
   }

   public Nullable<uint> Quantity
   {
      get { return qty; }
      set { qty = value; }
   }

   public uint InvoiceId
   {
      get { return invId; }
      set { invId = value; }
   }
}
// The attempt to compile the example displays the following output:
//    Type1.cs(13,23): warning CS3001: Argument type 'uint' is not CLS-compliant
//    Type1.cs(13,33): warning CS3001: Argument type 'uint?' is not CLS-compliant
//    Type1.cs(19,26): warning CS3003: Type of 'InvoiceItem.Quantity' is not CLS-compliant
//    Type1.cs(25,16): warning CS3003: Type of 'InvoiceItem.InvoiceId' is not CLS-compliant
```

```vb
<Assembly: CLSCompliant(True)>

Public Class InvoiceItem

   Private invId As UInteger = 0
   Private itemId As UInteger = 0
   Private qty AS Nullable(Of UInteger)

   Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
      itemId = sku
      qty = quantity
   End Sub

   Public Property Quantity As Nullable(Of UInteger)
      Get
         Return qty
      End Get
      Set
         qty = value
      End Set
   End Property

   Public Property InvoiceId As UInteger
      Get
         Return invId
      End Get
      Set
         invId = value
      End Set
   End Property
End Class
' The attempt to compile the example displays output similar to the following:
'    Type1.vb(13) : warning BC40028: Type of parameter 'sku' is not CLS-compliant.
'
'       Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
'                      ~~~
'    Type1.vb(13) : warning BC40041: Type 'UInteger' is not CLS-compliant.
'
'       Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
'                                                               ~~~~~~~~
'    Type1.vb(18) : warning BC40041: Type 'UInteger' is not CLS-compliant.
'
'       Public Property Quantity As Nullable(Of UInteger)
'                                               ~~~~~~~~
'    Type1.vb(27) : warning BC40027: Return type of function 'InvoiceId' is not CLS-compliant.
'
'       Public Property InvoiceId As UInteger
```

Они не будут отображаться, если заменить в открытом интерфейсе `InvoiceItem` типы, не соответствующие правилам CLS-совместимости, CLS-совместимыми типами:

```csharp
using System;

[assembly: CLSCompliant(true)]

public class InvoiceItem
{
   private uint invId = 0;
   private uint itemId = 0;
   private Nullable<int> qty;

   public InvoiceItem(int sku, Nullable<int> quantity)
   {
      if (sku <= 0)
         throw new ArgumentOutOfRangeException("The item number is zero or negative.");
      itemId = (uint) sku;

      qty = quantity;
   }

   public Nullable<int> Quantity
   {
      get { return qty; }
      set { qty = value; }
   }

   public int InvoiceId
   {
      get { return (int) invId; }
      set {
         if (value <= 0)
            throw new ArgumentOutOfRangeException("The invoice number is zero or negative.");
         invId = (uint) value; }
   }
}
```

```vb
Assembly: CLSCompliant(True)>

Public Class InvoiceItem

   Private invId As UInteger = 0
   Private itemId As UInteger = 0
   Private qty AS Nullable(Of Integer)

   Public Sub New(sku As Integer, quantity As Nullable(Of Integer))
      If sku <= 0 Then
         Throw New ArgumentOutOfRangeException("The item number is zero or negative.")
      End If
      itemId = CUInt(sku)
      qty = quantity
   End Sub

   Public Property Quantity As Nullable(Of Integer)
      Get
         Return qty
      End Get
      Set
         qty = value
      End Set
   End Property

   Public Property InvoiceId As Integer
      Get
         Return CInt(invId)
      End Get
      Set
         invId = CUInt(value)
      End Set
   End Property
End Class
```

Помимо перечисленных типов существуют и другие категории типов, не являющихся CLS-совместимыми. К ним относятся типы неуправляемых указателей и типы указателей функций. В следующем примере предупреждение компилятора отображается потому, что для создания массива целых чисел используется указатель на целое число.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ArrayHelper
{
   unsafe public static Array CreateInstance(Type type, int* ptr, int items)
   {
      Array arr = Array.CreateInstance(type, items);
      int* addr = ptr;
      for (int ctr = 0; ctr < items; ctr++) {
          int value = *addr;
          arr.SetValue(value, ctr);
          addr++;
      }
      return arr;
   }
}
// The attempt to compile this example displays the following output:
//    UnmanagedPtr1.cs(8,57): warning CS3001: Argument type 'int*' is not CLS-compliant
```

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ArrayHelper
{
   unsafe public static Array CreateInstance(Type type, int* ptr, int items)
   {
      Array arr = Array.CreateInstance(type, items);
      int* addr = ptr;
      for (int ctr = 0; ctr < items; ctr++) {
          int value = *addr;
          arr.SetValue(value, ctr);
          addr++;
      }
      return arr;
   }
}
// The attempt to compile this example displays the following output:
//    UnmanagedPtr1.cs(8,57): warning CS3001: Argument type 'int*' is not CLS-compliant
```

Все члены CLS-совместимых абстрактных классов (т. е. классов, отмеченных атрибутом `abstract` в C#) также должны быть CLS-совместимыми.

### <a name="naming-conventions"></a>Соглашения об именах

В некоторых языках программирования не учитывается регистр, поэтому идентификаторы (имена пространств имен, типов и членов) должны отличаться не только регистром. Два идентификатора считаются одинаковыми, если их записи в нижнем регистре совпадают. В следующем примере C# определяются два публичных класса: `Person` и `person`. Они отличаются только регистром, поэтому компилятор C# помечает, что они не соответствуют правилам CLS-совместимости.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person : person
{

}

public class person
{

}
// Compilation produces a compiler warning like the following:
//    Naming1.cs(11,14): warning CS3005: Identifier 'person' differing
//                       only in case is not CLS-compliant
//    Naming1.cs(6,14): (Location of symbol related to previous warning)
```

Идентификаторы языка программирования — имена пространств имен, типов и членов — должны соответствовать [стандарту Юникода версии 3.0 (технический отчет 15, приложение 7)](https://www.unicode.org/reports/tr15/tr15-18.html). Это означает следующее.

* В качестве первого символа идентификатора можно использовать любой символ верхнего или нижнего регистра, символ заголовка, модификатора, букву или цифру Юникода. Категории символов Юникода приводятся в описании перечисления [System.Globalization.UnicodeCategory](xref:System.Globalization.UnicodeCategory).

* Допустимые последующие символы — символы тех же категорий, что и первый, а также несамостоятельные знаки, комбинированные самостоятельные знаки, десятичные числа, соединительные знаки пунктуации и коды форматирования.

Перед сравнением идентификаторов необходимо отфильтровать коды форматирования и преобразовать идентификаторы в форму нормализации Юникода C, поскольку один символ может быть представлен несколькими единицами кода в кодировке UTF-16. Последовательности символов, соответствующие одним и тем же единицам кода в форме нормализации Юникода C, не являются CLS-совместимыми. В примере ниже определяется свойство с именем `Å`, представляющим собой символ ангстрема (U+212B), и свойство с именем `Å`, представляющим собой заглавную латинскую букву А с надстрочным кружком (U+00C5). Компилятор C# помечает, что исходный код не соответствует правилам CLS-совместимости.

```csharp
public class Size
{
   private double a1;
   private double a2;

   public double Å
   {
       get { return a1; }
       set { a1 = value; }
   }

   public double Å
   {
       get { return a2; }
       set { a2 = value; }
   }
}
// Compilation produces a compiler warning like the following:
//    Naming2a.cs(16,18): warning CS3005: Identifier 'Size.Å' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(10,18): (Location of symbol related to previous warning)
//    Naming2a.cs(18,8): warning CS3005: Identifier 'Size.Å.get' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(12,8): (Location of symbol related to previous warning)
//    Naming2a.cs(19,8): warning CS3005: Identifier 'Size.Å.set' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(13,8): (Location of symbol related to previous warning)
```

```vb
<Assembly: CLSCompliant(True)>
Public Class Size
   Private a1 As Double
   Private a2 As Double

   Public Property Å As Double
       Get
          Return a1
       End Get
       Set
          a1 = value
       End Set
   End Property

   Public Property Å As Double
       Get
          Return a2
       End Get
       Set
          a2 = value
       End Set
   End Property
End Class
' Compilation produces a compiler warning like the following:
'    Naming1.vb(9) : error BC30269: 'Public Property Å As Double' has multiple definitions
'     with identical signatures.
'
'       Public Property Å As Double
'                       ~
```

Имена членов в определенной области (например, имена пространств имен в сборке, типов в пространстве имен или членов типа) должны быть уникальными, за исключением имен, разрешаемых через перегрузку. Это правило более строгое, чем требования системы общих типов CTS, где члены разных типов (например, метод и поле) могут иметь одинаковые имена в области. В частности у членов типов:

* поля и вложенные типы различаются только по имени;

* методы, свойства и события с одинаковым именем должны отличаться не только возвращаемым типом.

Следующий пример иллюстрирует это правило. В нем определяется класс `Converter`, содержащий 4 члена с именем `Conversion`. Три из них — методы, один — свойство. Метод с параметром `Int64` имеет уникальное имя, а два метода с параметром `Int32` — нет, потому что возвращаемое значение не рассматривается как часть сигнатуры члена. Свойство `Conversion` также нарушает правило, поскольку имеет то же имя, что и перегруженные методы.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Converter
{
   public double Conversion(int number)
   {
      return (double) number;
   }

   public float Conversion(int number)
   {
      return (float) number;
   }

   public double Conversion(long number)
   {
      return (double) number;
   }

   public bool Conversion
   {
      get { return true; }
   }
}
// Compilation produces a compiler error like the following:
//    Naming3.cs(13,17): error CS0111: Type 'Converter' already defines a member called
//            'Conversion' with the same parameter types
//    Naming3.cs(8,18): (Location of symbol related to previous error)
//    Naming3.cs(23,16): error CS0102: The type 'Converter' already contains a definition for
//            'Conversion'
//    Naming3.cs(8,18): (Location of symbol related to previous error)
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Converter
   Public Function Conversion(number As Integer) As Double
      Return CDbl(number)
   End Function

   Public Function Conversion(number As Integer) As Single
      Return CSng(number)
   End Function

   Public Function Conversion(number As Long) As Double
      Return CDbl(number)
   End Function

   Public ReadOnly Property Conversion As Boolean
      Get
         Return True
      End Get
   End Property
End Class
' Compilation produces a compiler error like the following:
'    Naming3.vb(8) : error BC30301: 'Public Function Conversion(number As Integer) As Double'
'                    and 'Public Function Conversion(number As Integer) As Single' cannot
'                    overload each other because they differ only by return types.
'
'       Public Function Conversion(number As Integer) As Double
'                       ~~~~~~~~~~
'    Naming3.vb(20) : error BC30260: 'Conversion' is already declared as 'Public Function
'                     Conversion(number As Integer) As Single' in this class.
'
'       Public ReadOnly Property Conversion As Boolean
'                                ~~~~~~~~~~
```

В некоторых языках есть уникальные ключевые слова. В языках, поддерживаемых средой CLR, должен существовать механизм обозначения идентификаторов (например, имен типов), совпадающих с ключевыми словами. Например, `case` — ключевое слово как в C#, так и в Visual Basic. В примере кода на Visual Basic неоднозначность между классом с именем `case` и ключевым словом `case` устраняется с помощью парных фигурных скобок. Иначе бы код не скомпилировался и появилось бы сообщение об ошибке "Ключевое слово не может использоваться как идентификатор".

```vb
Public Class [case]
   Private _id As Guid
   Private name As String

   Public Sub New(name As String)
      _id = Guid.NewGuid()
      Me.name = name
   End Sub

   Public ReadOnly Property ClientName As String
      Get
         Return name
      End Get
   End Property
End Class
```

В примере кода на C#, где создается экземпляр класса `case`, неоднозначность между ключевым словом и идентификатором разрешается с помощью символа @. Без этого символа компилятор C# выдал бы два сообщения об ошибке: "Требуется тип" и "Недопустимый элемент case".

```csharp
using System;

public class Example
{
   public static void Main()
   {
      @case c = new @case("John");
      Console.WriteLine(c.ClientName);
   }
}
```

### <a name="type-conversion"></a>Преобразование типов

В спецификации CLS определены два оператора преобразования.

* Для расширяющих преобразований, которые не приводят к потере данных или потере точности, используется оператор `op_Implicit`. Например, структура [Decimal](xref:System.Decimal) включает перегруженный оператор `op_Implicit`, который преобразует значения целочисленных типов и значения [Char](xref:System.Char) в значения `Decimal`.

* Для сужающих преобразований, которые могут привести к потере порядка (преобразование в значение с меньшим диапазоном) или потере точности, используется оператор `op_Explicit`. Например, структура `Decimal` включает перегруженный оператор `op_Explicit`, который преобразует значения [Double](xref:System.Double) и [Single](xref:System.Single) в значения `Decimal`, а также значения `Decimal` в целочисленные значения и значения `Double`, `Single` и `Char`.

Однако перегружать операторы и определять пользовательские операторы можно не во всех языках. При реализации этих операторов преобразования необходимо предоставить альтернативный способ преобразования. Рекомендуется использовать методы `From`Xxx и `To`Xxx.

Следующий пример иллюстрирует неявное и явное преобразования, которые являются CLS-совместимыми. В нем создается класс `UDouble`, который представляет число двойной точности с плавающей запятой со знаком. В нем предусмотрены неявные преобразования `UDouble` в `Double` и явные преобразования `UDouble` в `Single`, `Double` в `UDouble` и `Single` в `UDouble`. В нем также определен метод `ToDouble` — альтернативный вариант неявного преобразования и методы `ToSingle`, `FromDouble` и `FromSingle` — альтернативные варианты явного преобразования.

```csharp
using System;

public struct UDouble
{
   private double number;

   public UDouble(double value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      number = value;
   }

   public UDouble(float value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      number = value;
   }

   public static readonly UDouble MinValue = (UDouble) 0.0;
   public static readonly UDouble MaxValue = (UDouble) Double.MaxValue;

   public static explicit operator Double(UDouble value)
   {
      return value.number;
   }

   public static implicit operator Single(UDouble value)
   {
      if (value.number > (double) Single.MaxValue)
         throw new InvalidCastException("A UDouble value is out of range of the Single type.");

      return (float) value.number;
   }

   public static explicit operator UDouble(double value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      return new UDouble(value);
   }

   public static implicit operator UDouble(float value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      return new UDouble(value);
   }

   public static Double ToDouble(UDouble value)
   {
      return (Double) value;
   }

   public static float ToSingle(UDouble value)
   {
      return (float) value;
   }

   public static UDouble FromDouble(double value)
   {
      return new UDouble(value);
   }

   public static UDouble FromSingle(float value)
   {
      return new UDouble(value);
   }
}
```

```vb
Public Structure UDouble
   Private number As Double

   Public Sub New(value As Double)
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      number = value
   End Sub

   Public Sub New(value As Single)
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      number = value
   End Sub

   Public Shared ReadOnly MinValue As UDouble = CType(0.0, UDouble)
   Public Shared ReadOnly MaxValue As UDouble = Double.MaxValue

   Public Shared Widening Operator CType(value As UDouble) As Double
      Return value.number
   End Operator

   Public Shared Narrowing Operator CType(value As UDouble) As Single
      If value.number > CDbl(Single.MaxValue) Then
         Throw New InvalidCastException("A UDouble value is out of range of the Single type.")
      End If
      Return CSng(value.number)
   End Operator

   Public Shared Narrowing Operator CType(value As Double) As UDouble
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      Return New UDouble(value)
   End Operator

   Public Shared Narrowing Operator CType(value As Single) As UDouble
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      Return New UDouble(value)
   End Operator

   Public Shared Function ToDouble(value As UDouble) As Double
      Return CType(value, Double)
   End Function

   Public Shared Function ToSingle(value As UDouble) As Single
      Return CType(value, Single)
   End Function

   Public Shared Function FromDouble(value As Double) As UDouble
      Return New UDouble(value)
   End Function

   Public Shared Function FromSingle(value As Single) As UDouble
      Return New UDouble(value)
   End Function
End Structure
```

### <a name="arrays"></a>Массивы

Правила CLS-совместимости для массивов:

* Нижняя граница всех измерений массива должна быть равна нулю. В следующем примере создается массив с нижней границей равной единице, т. е. он не соответствует правилам CLS-совместимости. Обратите внимание: несмотря на наличие атрибута [CLSCompliantAttribute](xref:System.CLSCompliantAttribute), компилятор не обнаруживает, что возвращаемый методом `Numbers.GetTenPrimes` массив не является CLS-совместимым.

  ```csharp
  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static Array GetTenPrimes()
    {
        Array arr = Array.CreateInstance(typeof(Int32), new int[] {10}, new int[] {1});
        arr.SetValue(1, 1);
        arr.SetValue(2, 2);
        arr.SetValue(3, 3);
        arr.SetValue(5, 4);
        arr.SetValue(7, 5);
        arr.SetValue(11, 6);
        arr.SetValue(13, 7);
        arr.SetValue(17, 8);
        arr.SetValue(19, 9);
        arr.SetValue(23, 10);

        return arr;
    }
  }
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Class Numbers
     Public Shared Function GetTenPrimes() As Array
        Dim arr As Array = Array.CreateInstance(GetType(Int32), {10}, {1})
        arr.SetValue(1, 1)
        arr.SetValue(2, 2)
        arr.SetValue(3, 3)
        arr.SetValue(5, 4)
        arr.SetValue(7, 5)
        arr.SetValue(11, 6)
        arr.SetValue(13, 7)
        arr.SetValue(17, 8)
        arr.SetValue(19, 9)
        arr.SetValue(23, 10)
        Return arr
     End Function
  End Class
  ```

* Все элементы массива должны состоять из CLS-совместимых типов. В следующем примере определяются два метода, которые возвращают массивы, не являющиеся CLS-совместимыми. Первый возвращает массив значений [UInt32](xref:System.UInt32). Второй возвращает массив [Object](xref:System.Object), содержащий значения [Int32](xref:System.Int32) и `UInt32`. Поскольку тип первого массива — `UInt32`, компилятор сообщает, что он не является CLS-совместимым. Однако он не распознает, что элементы второго массива не являются CLS-совместимыми.

  ```csharp
  using System;

  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static UInt32[] GetTenPrimes()
    {
        uint[] arr = { 1u, 2u, 3u, 5u, 7u, 11u, 13u, 17u, 19u };
        return arr;
    }

    public static Object[] GetFivePrimes()
    {
        Object[] arr = { 1, 2, 3, 5u, 7u };
        return arr;
    }
  }
  // Compilation produces a compiler warning like the following:
  //    Array2.cs(8,27): warning CS3002: Return type of 'Numbers.GetTenPrimes()' is not
  //            CLS-compliant
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Class Numbers
     Public Shared Function GetTenPrimes() As UInt32()
        Return { 1ui, 2ui, 3ui, 5ui, 7ui, 11ui, 13ui, 17ui, 19ui }
     End Function
     Public Shared Function GetFivePrimes() As Object()
        Dim arr() As Object = { 1, 2, 3, 5ui, 7ui }
        Return arr
     End Function
  End Class
  ' Compilation produces a compiler warning like the following:
  '    warning BC40027: Return type of function 'GetTenPrimes' is not CLS-compliant.
  ```

* Перегрузка методов, параметры которых являются массивами, разрешается исходя из предпосылки, что это массивы, и с учетом типа их элементов. Поэтому следующий перегруженный метод `GetSquares` является CLS-совместимым.

  ```csharp
  using System;
  using System.Numerics;

  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static byte[] GetSquares(byte[] numbers)
    {
        byte[] numbersOut = new byte[numbers.Length];
        for (int ctr = 0; ctr < numbers.Length; ctr++) {
            int square = ((int) numbers[ctr]) * ((int) numbers[ctr]);
            if (square <= Byte.MaxValue)
                numbersOut[ctr] = (byte) square;
            // If there's an overflow, assign MaxValue to the corresponding
            // element.
            else
                numbersOut[ctr] = Byte.MaxValue;

        }
        return numbersOut;
    }

    public static BigInteger[] GetSquares(BigInteger[] numbers)
  {
        BigInteger[] numbersOut = new BigInteger[numbers.Length];
        for (int ctr = 0; ctr < numbers.Length; ctr++)
            numbersOut[ctr] = numbers[ctr] * numbers[ctr];

       return numbersOut;
    }
  }
  ```

  ```vb
  Imports System.Numerics

  <Assembly: CLSCompliant(True)>

  Public Module Numbers
     Public Function GetSquares(numbers As Byte()) As Byte()
        Dim numbersOut(numbers.Length - 1) As Byte
        For ctr As Integer = 0 To numbers.Length - 1
           Dim square As Integer = (CInt(numbers(ctr)) * CInt(numbers(ctr)))
           If square <= Byte.MaxValue Then
              numbersOut(ctr) = CByte(square)
           ' If there's an overflow, assign MaxValue to the corresponding
           ' element.
           Else
              numbersOut(ctr) = Byte.MaxValue
           End If
        Next
        Return numbersOut
     End Function

     Public Function GetSquares(numbers As BigInteger()) As BigInteger()
         Dim numbersOut(numbers.Length - 1) As BigInteger
         For ctr As Integer = 0 To numbers.Length - 1
            numbersOut(ctr) = numbers(ctr) * numbers(ctr)
         Next
         Return numbersOut
     End Function
  End Module
  ```

### <a name="interfaces"></a>Интерфейсы

CLS-совместимый интерфейс может определять свойства, события и виртуальные методы (методы без реализации). Он не может содержать:

* Статические методы или статические поля. Компилятор C# выдает ошибки, если вы определили в интерфейсе статический член.

* Поля. Компилятор C# выдает ошибки, если вы определили в интерфейсе поле.

* Методы, которые не являются CLS-совместимыми. Например, в следующем определении интерфейса есть метод `INumber.GetUnsigned`. Компилятор выдает предупреждение о том, что он не является CLS-совместимым.

  ```csharp
  using System;

  [assembly:CLSCompliant(true)]

  public interface INumber
  {
      int Length();
      [CLSCompliant(false)] ulong GetUnsigned();
  }
  // Attempting to compile the example displays output like the following:
  //    Interface2.cs(8,32): warning CS3010: 'INumber.GetUnsigned()': CLS-compliant interfaces
  //            must have only CLS-compliant members
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Interface INumber
    Function Length As Integer
      <CLSCompliant(False)> Function GetUnsigned As ULong
    End Interface
    ' Attempting to compile the example displays output like the following:
    '    Interface2.vb(9) : warning BC40033: Non CLS-compliant 'function' is not allowed in a
    '    CLS-compliant interface.
    '
    '       <CLSCompliant(False)> Function GetUnsigned As ULong
    '                                      ~~~~~~~~~~~
  ```

  Вследствие этого правила не требуется, чтобы CLS-совместимые типы реализовывали члены, которые не являются CLS-совместимыми. Если CLS-совместимая платформа предоставляет класс, реализующий интерфейс, который не является CLS-совместимым, в ней должны быть определены конкретные реализации всех членов, которые не являются CLS-совместимыми.

Кроме того, CLS-совместимые языковые компиляторы должны разрешать классам иметь отдельные реализации членов с одинаковыми именами и сигнатурами в нескольких интерфейсах. Язык C# поддерживает явные реализации интерфейса, с помощью которых можно определить разные реализации методов с одинаковыми именами. Этот сценарий представлен в следующем примере, где определяется класс `Temperature`, который явно реализует интерфейсы `ICelsius` и `IFahrenheit`.

```csharp
using System;

[assembly: CLSCompliant(true)]

public interface IFahrenheit
{
   decimal GetTemperature();
}

public interface ICelsius
{
   decimal GetTemperature();
}

public class Temperature : ICelsius, IFahrenheit
{
   private decimal _value;

   public Temperature(decimal value)
   {
      // We assume that this is the Celsius value.
      _value = value;
   }

   decimal IFahrenheit.GetTemperature()
   {
      return _value * 9 / 5 + 32;
   }

   decimal ICelsius.GetTemperature()
   {
      return _value;
   }
}
public class Example
{
   public static void Main()
   {
      Temperature temp = new Temperature(100.0m);
      ICelsius cTemp = temp;
      IFahrenheit fTemp = temp;
      Console.WriteLine("Temperature in Celsius: {0} degrees",
                        cTemp.GetTemperature());
      Console.WriteLine("Temperature in Fahrenheit: {0} degrees",
                        fTemp.GetTemperature());
   }
}
// The example displays the following output:
//       Temperature in Celsius: 100.0 degrees
//       Temperature in Fahrenheit: 212.0 degrees
```

```vb
Assembly: CLSCompliant(True)>

Public Interface IFahrenheit
   Function GetTemperature() As Decimal
End Interface

Public Interface ICelsius
   Function GetTemperature() As Decimal
End Interface

Public Class Temperature : Implements ICelsius, IFahrenheit
   Private _value As Decimal

   Public Sub New(value As Decimal)
      ' We assume that this is the Celsius value.
      _value = value
   End Sub

   Public Function GetFahrenheit() As Decimal _
          Implements IFahrenheit.GetTemperature
      Return _value * 9 / 5 + 32
   End Function

   Public Function GetCelsius() As Decimal _
          Implements ICelsius.GetTemperature
      Return _value
   End Function
End Class

Module Example
   Public Sub Main()
      Dim temp As New Temperature(100.0d)
      Console.WriteLine("Temperature in Celsius: {0} degrees",
                        temp.GetCelsius())
      Console.WriteLine("Temperature in Fahrenheit: {0} degrees",
                        temp.GetFahrenheit())
   End Sub
End Module
' The example displays the following output:
'       Temperature in Celsius: 100.0 degrees
'       Temperature in Fahrenheit: 212.0 degrees
```

### <a name="enumerations"></a>Перечисления

Правила CLS-совместимости для перечислений:

* Базовый тип перечисления должен быть CLS-совместимым встроенным целочисленным типом ([Byte](xref:System.Byte), [Int16](xref:System.Int16), [Int32](xref:System.Int32) или [Int64](xref:System.Int64)). Например, при определении перечисления с базовым типом [UInt32](xref:System.UInt32) компилятор выдает предупреждение.

    ```csharp
    using System;

    [assembly: CLSCompliant(true)]

    public enum Size : uint {
        Unspecified = 0,
        XSmall = 1,
        Small = 2,
        Medium = 3,
        Large = 4,
        XLarge = 5
    };

    public class Clothing
    {
        public string Name;
        public string Type;
        public string Size;
    }
    // The attempt to compile the example displays a compiler warning like the following:
    //    Enum3.cs(6,13): warning CS3009: 'Size': base type 'uint' is not CLS-compliant
    ```

    ```vb
    <Assembly: CLSCompliant(True)>

    Public Enum Size As UInt32
       Unspecified = 0
       XSmall = 1
       Small = 2
       Medium = 3
       Large = 4
       XLarge = 5
    End Enum

    Public Class Clothing
       Public Name As String
       Public Type As String
       Public Size As Size
    End Class
    ' The attempt to compile the example displays a compiler warning like the following:
    '    Enum3.vb(6) : warning BC40032: Underlying type 'UInt32' of Enum is not CLS-compliant.
    '
    '    Public Enum Size As UInt32
    '                ~~~~
    ```

* Тип перечисления должен иметь поле `Value__` с одним экземпляром, отмеченное атрибутом `FieldAttributes.RTSpecialName`. Это позволяет неявно ссылаться на значение поля.

* Статические поля литералов перечисления должны иметь тот же тип, что и перечисление. Например, если определить перечисление `State` со значениями `State.On` и `State.Off`, `State.On` и `State.Off` будут статическими полями литералов типа `State`.

* Существует два вида перечислений:

  * Первый вид представляет набор взаимно исключающих именованных целочисленных значений и не имеет настраиваемого атрибута [System.FlagsAttribute](xref:System.FlagsAttribute).

  * Второй вид представляет набор битовых флагов, сочетая которые, можно создавать значения без имени. Такие перечисления имеют настраиваемый атрибут [System.FlagsAttribute](xref:System.FlagsAttribute).

Дополнительные сведения см. в документации по структуре [Enum](xref:System.Enum).

* Значение перечисления не ограничивается диапазоном указанных значений. Другими словами, диапазон значений в перечислении — это диапазон базового значения. Метод `Enum.IsDefined` позволяет определить, является ли указанное значение членом перечисления.

### <a name="type-members-in-general"></a>Обзор членов типов

В соответствии со спецификацией CLS доступ ко всем полям и методам должен осуществляться как к членам определенного класса. Поэтому глобальные статические поля и методы (статические поля и методы, определенные отдельно от типа) не являются CLS-совместимыми. Если такие поля или методы присутствуют в коде, компилятор C# выдает ошибку.

В спецификации CLS поддерживается только стандартное соглашение об управляемых вызовах. Соглашения о неуправляемых вызовах и методы со списками аргументов переменной длины, отмеченные ключевым словом `varargs`, не поддерживаются. Для переменных списков аргументов, совместимых со стандартным соглашением об управляемых вызовах, следует использовать атрибут [ParamArrayAttribute](xref:System.ParamArrayAttribute) или индивидуальную реализацию языка, например ключевое слово `params` в C# или ключевое слово `ParamArray` в Visual Basic.

### <a name="member-accessibility"></a>Доступность членов

Переопределение наследуемого члена не влияет на его доступность. Например, открытый метод базового класса невозможно переопределить с помощью закрытого метода производного класса. Существует одно исключение: член `protected internal` (в C#) или член `Protected Friend` (в Visual Basic) в одной сборке может переопределяться типом в другой сборке.  Тогда переопределенный член будет иметь доступность `Protected`.

Рассмотрим следующий пример. Атрибут [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) имеет значение `true`. Когда класс `Person`, производный от класса `Animal`, изменяет доступность свойства `Species` с открытой на закрытую, компилятор выдает ошибку. Однако если доступность меняется на открытую, ошибки не возникает.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Animal
{
   private string _species;

   public Animal(string species)
   {
      _species = species;
   }

   public virtual string Species
   {
      get { return _species; }
   }

   public override string ToString()
   {
      return _species;
   }
}

public class Human : Animal
{
   private string _name;

   public Human(string name) : base("Homo Sapiens")
   {
      _name = name;
   }

   public string Name
   {
      get { return _name; }
   }

   private override string Species
   {
      get { return base.Species; }
   }

   public override string ToString()
   {
      return _name;
   }
}

public class Example
{
   public static void Main()
   {
      Human p = new Human("John");
      Console.WriteLine(p.Species);
      Console.WriteLine(p.ToString());
   }
}
// The example displays the following output:
//    error CS0621: 'Human.Species': virtual or abstract members cannot be private
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Animal
   Private _species As String

   Public Sub New(species As String)
      _species = species
   End Sub

   Public Overridable ReadOnly Property Species As String
      Get
         Return _species
      End Get
   End Property

   Public Overrides Function ToString() As String
      Return _species
   End Function
End Class

Public Class Human : Inherits Animal
   Private _name As String

   Public Sub New(name As String)
      MyBase.New("Homo Sapiens")
      _name = name
   End Sub

   Public ReadOnly Property Name As String
      Get
         Return _name
      End Get
   End Property

   Private Overrides ReadOnly Property Species As String
      Get
         Return MyBase.Species
      End Get
   End Property

   Public Overrides Function ToString() As String
      Return _name
   End Function
End Class

Public Module Example
   Public Sub Main()
      Dim p As New Human("John")
      Console.WriteLine(p.Species)
      Console.WriteLine(p.ToString())
   End Sub
End Module
' The example displays the following output:
'     'Private Overrides ReadOnly Property Species As String' cannot override
'     'Public Overridable ReadOnly Property Species As String' because
'      they have different access levels.
'
'         Private Overrides ReadOnly Property Species As String
```

Типы в сигнатуре члена должны быть доступны всегда, когда доступен член. В частности, открытый член не может иметь параметр закрытого, защищенного или внутреннего типа. В следующем примере, когда конструктор класса `StringWrapper` предоставляет внутреннее значение перечисления `StringOperationType`, которое определяет, как переносится строка, компилятор выдает ошибку.

```csharp
using System;
using System.Text;

public class StringWrapper
{
   string internalString;
   StringBuilder internalSB = null;
   bool useSB = false;

   public StringWrapper(StringOperationType type)
   {
      if (type == StringOperationType.Normal) {
         useSB = false;
      }
      else {
         useSB = true;
         internalSB = new StringBuilder();
      }
   }

   // The remaining source code...
}

internal enum StringOperationType { Normal, Dynamic }
// The attempt to compile the example displays the following output:
//    error CS0051: Inconsistent accessibility: parameter type
//            'StringOperationType' is less accessible than method
//            'StringWrapper.StringWrapper(StringOperationType)'
```

```vb
Imports System.Text

<Assembly:CLSCompliant(True)>

Public Class StringWrapper

   Dim internalString As String
   Dim internalSB As StringBuilder = Nothing
   Dim useSB As Boolean = False

   Public Sub New(type As StringOperationType)
      If type = StringOperationType.Normal Then
         useSB = False
      Else
         internalSB = New StringBuilder()
         useSB = True
      End If
   End Sub

   ' The remaining source code...
End Class

Friend Enum StringOperationType As Integer
   Normal = 0
   Dynamic = 1
End Enum
' The attempt to compile the example displays the following output:
'    error BC30909: 'type' cannot expose type 'StringOperationType'
'     outside the project through class 'StringWrapper'.
'
'       Public Sub New(type As StringOperationType)
'                              ~~~~~~~~~~~~~~~~~~~
```

### <a name="generic-types-and-members"></a>Универсальные типы и члены

У вложенного типа должно быть не меньше универсальных параметров, чем у включающего типа. Они соответствуют по позиции универсальным параметрам включающего типа. Универсальный тип может также содержать новые универсальные параметры.

Связь между параметрами универсального типа содержащего типа и вложенных типов может скрываться синтаксисом отдельных языков. В следующем примере универсальный тип `Outer<T>` содержит два вложенных класса — `Inner1A` и `Inner1B<U>`. При вызове метода `ToString`, наследуемого от класса `Object.ToString`, видно, что каждый вложенный класс включает параметры типа содержащего его класса.

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Outer<T>
{
   T value;

   public Outer(T value)
   {
      this.value = value;
   }

   public class Inner1A : Outer<T>
   {
      public Inner1A(T value) : base(value)
      {  }
   }

   public class Inner1B<U> : Outer<T>
   {
      U value2;

      public Inner1B(T value1, U value2) : base(value1)
      {
         this.value2 = value2;
      }
   }
}

public class Example
{
   public static void Main()
   {
      var inst1 = new Outer<String>("This");
      Console.WriteLine(inst1);

      var inst2 = new Outer<String>.Inner1A("Another");
      Console.WriteLine(inst2);

      var inst3 = new Outer<String>.Inner1B<int>("That", 2);
      Console.WriteLine(inst3);
   }
}
// The example displays the following output:
//       Outer`1[System.String]
//       Outer`1+Inner1A[System.String]
//       Outer`1+Inner1B`1[System.String,System.Int32]
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Outer(Of T)
   Dim value As T

   Public Sub New(value As T)
      Me.value = value
   End Sub

   Public Class Inner1A : Inherits Outer(Of T)
      Public Sub New(value As T)
         MyBase.New(value)
      End Sub
   End Class

   Public Class Inner1B(Of U) : Inherits Outer(Of T)
      Dim value2 As U

      Public Sub New(value1 As T, value2 As U)
         MyBase.New(value1)
         Me.value2 = value2
      End Sub
   End Class
End Class

Public Module Example
   Public Sub Main()
      Dim inst1 As New Outer(Of String)("This")
      Console.WriteLine(inst1)

      Dim inst2 As New Outer(Of String).Inner1A("Another")
      Console.WriteLine(inst2)

      Dim inst3 As New Outer(Of String).Inner1B(Of Integer)("That", 2)
      Console.WriteLine(inst3)
   End Sub
End Module
' The example displays the following output:
'       Outer`1[System.String]
'       Outer`1+Inner1A[System.String]
'       Outer`1+Inner1B`1[System.String,System.Int32]
```

Имена универсальных типов кодируются в виде *имя*'*n*, где *имя* — имя типа, *`*  — символьный литерал, а *n* — количество параметров, объявленных в типе (у вложенных универсальных типов — количество новых параметров типа). Эта запись имен универсальных типов в первую очередь пригодится разработчикам, использующим отражение для доступа к универсальным CLS-совместимым типам в библиотеке.

Если к универсальному типу применяются ограничения, то типы, используемые в качестве ограничений, должны быть CLS-совместимыми. В следующем примере определяется класс `BaseClass`, который не является CLS-совместимым, и универсальный класс `BaseCollection`, у которого параметр типа должен быть производным от класса `BaseClass`. Поскольку `BaseClass` не является CLS-совместимым, компилятор выдает предупреждение.

```csharp
using System;

[assembly:CLSCompliant(true)]

[CLSCompliant(false)] public class BaseClass
{}

public class BaseCollection<T> where T : BaseClass
{}
// Attempting to compile the example displays the following output:
//    warning CS3024: Constraint type 'BaseClass' is not CLS-compliant
```

```vb
Assembly: CLSCompliant(True)>

<CLSCompliant(False)> Public Class BaseClass
End Class

Public Class BaseCollection(Of T As BaseClass)
End Class
' Attempting to compile the example displays the following output:
'    warning BC40040: Generic parameter constraint type 'BaseClass' is not
'    CLS-compliant.
'
'    Public Class BaseCollection(Of T As BaseClass)
'                                        ~~~~~~~~~
```

В универсальном типе, производном от универсального базового типа, должны повторно объявляться ограничения, обеспечивающие соответствие всем ограничениям базового типа. В следующем примере определяется `Number<T>`, который может представлять любой числовой тип. В нем также определяется класс `FloatingPoint<T>`, представляющий значение с плавающей запятой. Однако поскольку ограничения `Number<T>` (T должен быть типом значения) не применяются к `FloatingPoint<T>`, код не компилируется.

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Number<T> where T : struct
{
   // use Double as the underlying type, since its range is a superset of
   // the ranges of all numeric types except BigInteger.
   protected double number;

   public Number(T value)
   {
      try {
         this.number = Convert.ToDouble(value);
      }
      catch (OverflowException e) {
         throw new ArgumentException("value is too large.", e);
      }
      catch (InvalidCastException e) {
         throw new ArgumentException("The value parameter is not numeric.", e);
      }
   }

   public T Add(T value)
   {
      return (T) Convert.ChangeType(number + Convert.ToDouble(value), typeof(T));
   }

   public T Subtract(T value)
   {
      return (T) Convert.ChangeType(number - Convert.ToDouble(value), typeof(T));
   }
}

public class FloatingPoint<T> : Number<T>
{
   public FloatingPoint(T number) : base(number)
   {
      if (typeof(float) == number.GetType() ||
          typeof(double) == number.GetType() ||
          typeof(decimal) == number.GetType())
         this.number = Convert.ToDouble(number);
      else
         throw new ArgumentException("The number parameter is not a floating-point number.");
   }
}
// The attempt to compile the example displays the following output:
//       error CS0453: The type 'T' must be a non-nullable value type in
//               order to use it as parameter 'T' in the generic type or method 'Number<T>'
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Number(Of T As Structure)
   ' Use Double as the underlying type, since its range is a superset of
   ' the ranges of all numeric types except BigInteger.
   Protected number As Double

   Public Sub New(value As T)
      Try
         Me.number = Convert.ToDouble(value)
      Catch e As OverflowException
         Throw New ArgumentException("value is too large.", e)
      Catch e As InvalidCastException
         Throw New ArgumentException("The value parameter is not numeric.", e)
      End Try
   End Sub

   Public Function Add(value As T) As T
      Return CType(Convert.ChangeType(number + Convert.ToDouble(value), GetType(T)), T)
   End Function

   Public Function Subtract(value As T) As T
      Return CType(Convert.ChangeType(number - Convert.ToDouble(value), GetType(T)), T)
   End Function
End Class

Public Class FloatingPoint(Of T) : Inherits Number(Of T)
   Public Sub New(number As T)
      MyBase.New(number)
      If TypeOf number Is Single Or
               TypeOf number Is Double Or
               TypeOf number Is Decimal Then
         Me.number = Convert.ToDouble(number)
      Else
         throw new ArgumentException("The number parameter is not a floating-point number.")
      End If
   End Sub
End Class
' The attempt to compile the example displays the following output:
'    error BC32105: Type argument 'T' does not satisfy the 'Structure'
'    constraint for type parameter 'T'.
'
'    Public Class FloatingPoint(Of T) : Inherits Number(Of T)
'                                                          ~
```

Если в класс `FloatingPoint<T>` добавить ограничение, код компилируется.

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Number<T> where T : struct
{
   // use Double as the underlying type, since its range is a superset of
   // the ranges of all numeric types except BigInteger.
   protected double number;

   public Number(T value)
   {
      try {
         this.number = Convert.ToDouble(value);
      }
      catch (OverflowException e) {
         throw new ArgumentException("value is too large.", e);
      }
      catch (InvalidCastException e) {
         throw new ArgumentException("The value parameter is not numeric.", e);
      }
   }

   public T Add(T value)
   {
      return (T) Convert.ChangeType(number + Convert.ToDouble(value), typeof(T));
   }

   public T Subtract(T value)
   {
      return (T) Convert.ChangeType(number - Convert.ToDouble(value), typeof(T));
   }
}

public class FloatingPoint<T> : Number<T> where T : struct
{
   public FloatingPoint(T number) : base(number)
   {
      if (typeof(float) == number.GetType() ||
          typeof(double) == number.GetType() ||
          typeof(decimal) == number.GetType())
         this.number = Convert.ToDouble(number);
      else
         throw new ArgumentException("The number parameter is not a floating-point number.");
   }
}
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Number(Of T As Structure)
   ' Use Double as the underlying type, since its range is a superset of
   ' the ranges of all numeric types except BigInteger.
   Protected number As Double

   Public Sub New(value As T)
      Try
         Me.number = Convert.ToDouble(value)
      Catch e As OverflowException
         Throw New ArgumentException("value is too large.", e)
      Catch e As InvalidCastException
         Throw New ArgumentException("The value parameter is not numeric.", e)
      End Try
   End Sub

   Public Function Add(value As T) As T
      Return CType(Convert.ChangeType(number + Convert.ToDouble(value), GetType(T)), T)
   End Function

   Public Function Subtract(value As T) As T
      Return CType(Convert.ChangeType(number - Convert.ToDouble(value), GetType(T)), T)
   End Function
End Class

Public Class FloatingPoint(Of T As Structure) : Inherits Number(Of T)
   Public Sub New(number As T)
      MyBase.New(number)
      If TypeOf number Is Single Or
               TypeOf number Is Double Or
               TypeOf number Is Decimal Then
         Me.number = Convert.ToDouble(number)
      Else
         throw new ArgumentException("The number parameter is not a floating-point number.")
      End If
   End Sub
End Class
```

Спецификация CLS предполагает консервативную модель создания экземпляров вложенных типов и защищенных членов. Открытые универсальные типы не могут предоставлять поля и члены с сигнатурами, содержащими определенный экземпляр вложенного защищенного универсального типа. Неуниверсальные типы, расширяющие определенный экземпляр универсального базового класса или интерфейса, не могут предоставлять поля и члены с сигнатурами, содержащими другой экземпляр вложенного защищенного универсального типа.

В следующем примере определяется универсальный тип `C1<T>` и защищенный класс `C1<T>.N`. Объект `C1<T>` имеет два метода: `M1` и `M2`. Однако `M1` не является CLS-совместимым, поскольку он возвращает объект `C1<int>.N` из `C1<T>`. Второй класс `C2` является производным от `C1<long>`. Он имеет два метода: `M3` и `M4`. `M3` не является CLS-совместимым, поскольку он возвращает объект `C1<int>.N` из подкласса `C1<long>`. Обратите внимание, что языковые компиляторы могут накладывать даже более строгие ограничения. В этом примере на языке Visual Basic при компиляции `M4` возникает ошибка.

```csharp
using System;

[assembly:CLSCompliant(true)]

public class C1<T>
{
   protected class N { }

   protected void M1(C1<int>.N n) { } // Not CLS-compliant - C1<int>.N not
                                      // accessible from within C1<T> in all
                                      // languages
   protected void M2(C1<T>.N n) { }   // CLS-compliant – C1<T>.N accessible
                                      // inside C1<T>
}

public class C2 : C1<long>
{
   protected void M3(C1<int>.N n) { }  // Not CLS-compliant – C1<int>.N is not
                                       // accessible in C2 (extends C1<long>)

   protected void M4(C1<long>.N n) { } // CLS-compliant, C1<long>.N is
                                       // accessible in C2 (extends C1<long>)
}
// Attempting to compile the example displays output like the following:
//       Generics4.cs(9,22): warning CS3001: Argument type 'C1<int>.N' is not CLS-compliant
//       Generics4.cs(18,22): warning CS3001: Argument type 'C1<int>.N' is not CLS-compliant
```

```vb
<Assembly:CLSCompliant(True)>

Public Class C1(Of T)
   Protected Class N
   End Class

   Protected Sub M1(n As C1(Of Integer).N)   ' Not CLS-compliant - C1<int>.N not
                                             ' accessible from within C1(Of T) in all
   End Sub                                   ' languages

   Protected Sub M2(n As C1(Of T).N)     ' CLS-compliant – C1(Of T).N accessible
   End Sub                               ' inside C1(Of T)
End Class

Public Class C2 : Inherits C1(Of Long)
   Protected Sub M3(n As C1(Of Integer).N)   ' Not CLS-compliant – C1(Of Integer).N is not
   End Sub                                   ' accessible in C2 (extends C1(Of Long))

   Protected Sub M4(n As C1(Of Long).N)
   End Sub
End Class
' Attempting to compile the example displays output like the following:
'    error BC30508: 'n' cannot expose type 'C1(Of Integer).N' in namespace
'    '<Default>' through class 'C1'.
'
'       Protected Sub M1(n As C1(Of Integer).N)   ' Not CLS-compliant - C1<int>.N not
'                             ~~~~~~~~~~~~~~~~
'    error BC30389: 'C1(Of T).N' is not accessible in this context because
'    it is 'Protected'.
'
'       Protected Sub M3(n As C1(Of Integer).N)   ' Not CLS-compliant - C1(Of Integer).N is not
'
'                             ~~~~~~~~~~~~~~~~
'
'    error BC30389: 'C1(Of T).N' is not accessible in this context because it is 'Protected'.
'
'       Protected Sub M4(n As C1(Of Long).N)
'                             ~~~~~~~~~~~~~
```

### <a name="constructors"></a>Конструкторы

Правила для конструкторов CLS-совместимых классов и структур:

* Перед обращением к данным унаследованного экземпляра конструктор производного класса должен вызвать конструктор экземпляра базового класса, поскольку конструкторы базовых классов не наследуются производными классами. Это правило не применяется к структурам, не поддерживающим прямое наследование.

  Обычно компиляторы применяют это правило вне зависимости от требований CLS-совместимости. Это иллюстрирует следующий пример. Класс `Doctor` является производным от класса `Person`, однако класс `Doctor` не может вызывать конструктор класса `Person` для инициализации наследуемых полей экземпляра.

    ```csharp
    using System;

    [assembly: CLSCompliant(true)]

    public class Person
    {
    private string fName, lName, _id;

    public Person(string firstName, string lastName, string id)
    {
        if (String.IsNullOrEmpty(firstName + lastName))
            throw new ArgumentNullException("Either a first name or a last name must be provided.");

        fName = firstName;
        lName = lastName;
        _id = id;
    }

    public string FirstName
    {
        get { return fName; }
    }

    public string LastName
    {
        get { return lName; }
    }

    public string Id
    {
        get { return _id; }
    }

    public override string ToString()
    {
        return String.Format("{0}{1}{2}", fName,
                            String.IsNullOrEmpty(fName) ?  "" : " ",
                            lName);
    }
    }

    public class Doctor : Person
    {
    public Doctor(string firstName, string lastName, string id)
    {
    }

    public override string ToString()
    {
        return "Dr. " + base.ToString();
    }
    }
    // Attempting to compile the example displays output like the following:
    //    ctor1.cs(45,11): error CS1729: 'Person' does not contain a constructor that takes 0
    //            arguments
    //    ctor1.cs(10,11): (Location of symbol related to previous error)
    ```

    ```vb
    <Assembly: CLSCompliant(True)>

    Public Class Person
       Private fName, lName, _id As String

       Public Sub New(firstName As String, lastName As String, id As String)
          If String.IsNullOrEmpty(firstName + lastName) Then
             Throw New ArgumentNullException("Either a first name or a last name must be provided.")
          End If

          fName = firstName
          lName = lastName
          _id = id
       End Sub

       Public ReadOnly Property FirstName As String
          Get
             Return fName
          End Get
       End Property

       Public ReadOnly Property LastName As String
          Get
             Return lName
          End Get
       End Property

       Public ReadOnly Property Id As String
          Get
             Return _id
          End Get
       End Property

       Public Overrides Function ToString() As String
          Return String.Format("{0}{1}{2}", fName,
                               If(String.IsNullOrEmpty(fName), "", " "),
                               lName)
       End Function
    End Class

    Public Class Doctor : Inherits Person
       Public Sub New(firstName As String, lastName As String, id As String)
       End Sub

       Public Overrides Function ToString() As String
          Return "Dr. " + MyBase.ToString()
       End Function
    End Class
    ' Attempting to compile the example displays output like the following:
    '    Ctor1.vb(46) : error BC30148: First statement of this 'Sub New' must be a call
    '    to 'MyBase.New' or 'MyClass.New' because base class 'Person' of 'Doctor' does
    '    not have an accessible 'Sub New' that can be called with no arguments.
    '
    '       Public Sub New()
    '                  ~~~
    ````

* Конструктор объекта можно вызывать только для создания объекта. Объект невозможно инициализировать дважды. В частности, это означает, что метод `Object.MemberwiseClone` не должен вызывать конструкторы.

### <a name="properties"></a>Свойства

Правила для свойств CLS-совместимых типов:

* Свойство должно иметь метод задания значения, метод получения значения или оба эти метода. В сборке они реализованы в виде специальных методов, т. е. отображаются как отдельные методы (метод получения значения имеет имя `get`\_*propertyname*, метод задания значения — `set`\_*propertyname*) и помечаются атрибутом `SpecialName` в метаданных сборки. Компилятор C# обеспечивает соблюдение этого правила, поэтому применять атрибут <xref:System.CLSCompliantAttribute> не требуется.

* Тип свойства, тип возвращаемого значения метода получения значения свойства и тип последнего аргумента метода задания значения должны совпадать. Все эти типы должны быть CLS-совместимыми, и аргументы не могут присваиваться свойству по ссылке (т. е. не могут быть управляемыми указателями).

* Если свойство имеет и метод получения, и метод задания значения, оба эти метода должны быть либо виртуальными, либо статическими, либо экземплярами. Компилятор C# обеспечивает соблюдение этого правила с помощью синтаксиса определения свойств.

### <a name="events"></a>События

Событие определяется именем и типом. Тип события является делегатом, который используется для обозначения события. Например, событие `DbConnection.StateChange` имеет тип `StateChangeEventHandler`. Помимо события также определяются три метода с именами, производными от имени события, которые обеспечивают реализацию события и имеют в метаданных сборки атрибут `SpecialName`:

* Метод добавления обработчика событий с именем `add`_*EventName*. Например, метод подписки для события `DbConnection.StateChange` называется `add_StateChange`.

* Метод удаления обработчика событий с именем `remove`_*EventName*. Например, метод удаления для события `DbConnection.StateChange` называется `remove_StateChange`.

* Метод, который указывает, что возникло событие, с именем `raise`\_*EventName*.

> [!NOTE]
> Большинство правил спецификации CLS, связанных с событиями, реализуется языковыми компиляторами и являются прозрачными для разработчиков компонентов.

Методы добавления, удаления и вызова события должны иметь одинаковую доступность и быть либо одновременно статическими, либо виртуальными, либо экземплярами. Методы добавления и удаления события имеют один параметр, тип которого является типом делегата события. Методы добавления и удаления должны либо оба присутствовать, либо оба отсутствовать.

В следующем примере определяется CLS-совместимый класс `Temperature`, который создает событие `TemperatureChanged`, если перепад температуры между двумя показаниями равен пороговому значению или превышает его. Класс `Temperature` явно определяет метод `raise_TemperatureChanged`, чтобы он мог выборочно выполнять обработчики событий.

```csharp
using System;
using System.Collections;
using System.Collections.Generic;

[assembly: CLSCompliant(true)]

public class TemperatureChangedEventArgs : EventArgs
{
   private Decimal originalTemp;
   private Decimal newTemp;
   private DateTimeOffset when;

   public TemperatureChangedEventArgs(Decimal original, Decimal @new, DateTimeOffset time)
   {
      originalTemp = original;
      newTemp = @new;
      when = time;
   }

   public Decimal OldTemperature
   {
      get { return originalTemp; }
   }

   public Decimal CurrentTemperature
   {
      get { return newTemp; }
   }

   public DateTimeOffset Time
   {
      get { return when; }
   }
}

public delegate void TemperatureChanged(Object sender, TemperatureChangedEventArgs e);

public class Temperature
{
   private struct TemperatureInfo
   {
      public Decimal Temperature;
      public DateTimeOffset Recorded;
   }

   public event TemperatureChanged TemperatureChanged;

   private Decimal previous;
   private Decimal current;
   private Decimal tolerance;
   private List<TemperatureInfo> tis = new List<TemperatureInfo>();

   public Temperature(Decimal temperature, Decimal tolerance)
   {
      current = temperature;
      TemperatureInfo ti = new TemperatureInfo();
      ti.Temperature = temperature;
      tis.Add(ti);
      ti.Recorded = DateTimeOffset.UtcNow;
      this.tolerance = tolerance;
   }

   public Decimal CurrentTemperature
   {
      get { return current; }
      set {
         TemperatureInfo ti = new TemperatureInfo();
         ti.Temperature = value;
         ti.Recorded = DateTimeOffset.UtcNow;
         previous = current;
         current = value;
         if (Math.Abs(current - previous) >= tolerance)
            raise_TemperatureChanged(new TemperatureChangedEventArgs(previous, current, ti.Recorded));
      }
   }

   public void raise_TemperatureChanged(TemperatureChangedEventArgs eventArgs)
   {
      if (TemperatureChanged == null)
         return;

      foreach (TemperatureChanged d in TemperatureChanged.GetInvocationList()) {
         if (d.Method.Name.Contains("Duplicate"))
            Console.WriteLine("Duplicate event handler; event handler not executed.");
         else
            d.Invoke(this, eventArgs);
      }
   }
}

public class Example
{
   public Temperature temp;

   public static void Main()
   {
      Example ex = new Example();
   }

   public Example()
   {
      temp = new Temperature(65, 3);
      temp.TemperatureChanged += this.TemperatureNotification;
      RecordTemperatures();
      Example ex = new Example(temp);
      ex.RecordTemperatures();
   }

   public Example(Temperature t)
   {
      temp = t;
      RecordTemperatures();
   }

   public void RecordTemperatures()
   {
      temp.TemperatureChanged += this.DuplicateTemperatureNotification;
      temp.CurrentTemperature = 66;
      temp.CurrentTemperature = 63;
   }

   internal void TemperatureNotification(Object sender, TemperatureChangedEventArgs e)
   {
      Console.WriteLine("Notification 1: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature);
   }

   public void DuplicateTemperatureNotification(Object sender, TemperatureChangedEventArgs e)
   {
      Console.WriteLine("Notification 2: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature);
   }
}
```

```vb
Imports System.Collections
Imports System.Collections.Generic

<Assembly: CLSCompliant(True)>

Public Class TemperatureChangedEventArgs   : Inherits EventArgs
   Private originalTemp As Decimal
   Private newTemp As Decimal
   Private [when] As DateTimeOffset

   Public Sub New(original As Decimal, [new] As Decimal, [time] As DateTimeOffset)
      originalTemp = original
      newTemp = [new]
      [when] = [time]
   End Sub

   Public ReadOnly Property OldTemperature As Decimal
      Get
         Return originalTemp
      End Get
   End Property

   Public ReadOnly Property CurrentTemperature As Decimal
      Get
         Return newTemp
      End Get
   End Property

   Public ReadOnly Property [Time] As DateTimeOffset
      Get
         Return [when]
      End Get
   End Property
End Class

Public Delegate Sub TemperatureChanged(sender As Object, e As TemperatureChangedEventArgs)

Public Class Temperature
   Private Structure TemperatureInfo
      Dim Temperature As Decimal
      Dim Recorded As DateTimeOffset
   End Structure

   Public Event TemperatureChanged As TemperatureChanged

   Private previous As Decimal
   Private current As Decimal
   Private tolerance As Decimal
   Private tis As New List(Of TemperatureInfo)

   Public Sub New(temperature As Decimal, tolerance As Decimal)
      current = temperature
      Dim ti As New TemperatureInfo()
      ti.Temperature = temperature
      ti.Recorded = DateTimeOffset.UtcNow
      tis.Add(ti)
      Me.tolerance = tolerance
   End Sub

   Public Property CurrentTemperature As Decimal
      Get
         Return current
      End Get
      Set
         Dim ti As New TemperatureInfo
         ti.Temperature = value
         ti.Recorded = DateTimeOffset.UtcNow
         previous = current
         current = value
         If Math.Abs(current - previous) >= tolerance Then
            raise_TemperatureChanged(New TemperatureChangedEventArgs(previous, current, ti.Recorded))
         End If
      End Set
   End Property

   Public Sub raise_TemperatureChanged(eventArgs As TemperatureChangedEventArgs)
      If TemperatureChangedEvent Is Nothing Then Exit Sub

      Dim ListenerList() As System.Delegate = TemperatureChangedEvent.GetInvocationList()
      For Each d As TemperatureChanged In TemperatureChangedEvent.GetInvocationList()
         If d.Method.Name.Contains("Duplicate") Then
            Console.WriteLine("Duplicate event handler; event handler not executed.")
         Else
            d.Invoke(Me, eventArgs)
         End If
      Next
   End Sub
End Class

Public Class Example
   Public WithEvents temp As Temperature

   Public Shared Sub Main()
      Dim ex As New Example()
   End Sub

   Public Sub New()
      temp = New Temperature(65, 3)
      RecordTemperatures()
      Dim ex As New Example(temp)
      ex.RecordTemperatures()
   End Sub

   Public Sub New(t As Temperature)
      temp = t
      RecordTemperatures()
   End Sub

   Public Sub RecordTemperatures()
      temp.CurrentTemperature = 66
      temp.CurrentTemperature = 63

   End Sub

   Friend Shared Sub TemperatureNotification(sender As Object, e As TemperatureChangedEventArgs) _
          Handles temp.TemperatureChanged
      Console.WriteLine("Notification 1: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature)
   End Sub

   Friend Shared Sub DuplicateTemperatureNotification(sender As Object, e As TemperatureChangedEventArgs) _
          Handles temp.TemperatureChanged
      Console.WriteLine("Notification 2: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature)
   End Sub
End Class
```

### <a name="overloads"></a>Overloads

Спецификация CLS налагает следующие требования на перегруженные члены:

* Члены могут перегружаться на основе количества и типов параметров. Соглашение о вызовах, тип возвращаемого значения, пользовательские модификаторы, применяемые к методу или его параметру, и способ передачи параметров (по значению или по ссылке) не учитываются при различении перегрузок. См. пример, иллюстрирующий требование уникальности имен в пределах области в разделе [Соглашения об именовании](#naming-conventions).

* Перегружать можно только свойства и методы. Поля и события невозможно перегружать.

* Универсальные методы могут перегружаться на основе количества универсальных параметров.

> [!NOTE]
> Правило о том, что возвращаемое значение не считается частью сигнатуры метода для разрешения перегрузки не распространяется на операторы `op_Explicit` и `op_Implicit`. Их можно перегружать и на основе параметров, и на основе возвращаемого значения.

### <a name="exceptions"></a>Исключения

Объекты исключений должны наследоваться от [System.Exception](xref:System.Exception) или типа, производного от `System.Exception`. В следующем примере, когда пользовательский класс `ErrorClass` используется для обработки исключения, компилятор выдает ошибку.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ErrorClass
{
   string msg;

   public ErrorClass(string errorMessage)
   {
      msg = errorMessage;
   }

   public string Message
   {
      get { return msg; }
   }
}

public static class StringUtilities
{
   public static string[] SplitString(this string value, int index)
   {
      if (index < 0 | index > value.Length) {
         ErrorClass badIndex = new ErrorClass("The index is not within the string.");
         throw badIndex;
      }
      string[] retVal = { value.Substring(0, index - 1),
                          value.Substring(index) };
      return retVal;
   }
}
// Compilation produces a compiler error like the following:
//    Exceptions1.cs(26,16): error CS0155: The type caught or thrown must be derived from
//            System.Exception
```

```vb
Imports System.Runtime.CompilerServices

<Assembly: CLSCompliant(True)>

Public Class ErrorClass
   Dim msg As String

   Public Sub New(errorMessage As String)
      msg = errorMessage
   End Sub

   Public ReadOnly Property Message As String
      Get
         Return msg
      End Get
   End Property
End Class

Public Module StringUtilities
   <Extension()> Public Function SplitString(value As String, index As Integer) As String()
      If index < 0 Or index > value.Length Then
         Dim BadIndex As New ErrorClass("The index is not within the string.")
         Throw BadIndex
      End If
      Dim retVal() As String = { value.Substring(0, index - 1),
                                 value.Substring(index) }
      Return retVal
   End Function
End Module
' Compilation produces a compiler error like the following:
'    Exceptions1.vb(27) : error BC30665: 'Throw' operand must derive from 'System.Exception'.
'
'             Throw BadIndex
'             ~~~~~~~~~~~~~~
```

Чтобы она не возникала, класс `ErrorClass` должен наследоваться от `System.Exception`. Кроме того, необходимо переопределить свойство Message. Эти ошибки устранены в следующем примере, где определяется CLS-совместимый класс `ErrorClass`.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ErrorClass : Exception
{
   string msg;

   public ErrorClass(string errorMessage)
   {
      msg = errorMessage;
   }

   public override string Message
   {
      get { return msg; }
   }
}

public static class StringUtilities
{
   public static string[] SplitString(this string value, int index)
   {
      if (index < 0 | index > value.Length) {
         ErrorClass badIndex = new ErrorClass("The index is not within the string.");
         throw badIndex;
      }
      string[] retVal = { value.Substring(0, index - 1),
                          value.Substring(index) };
      return retVal;
   }
}
```

```vb
Imports System.Runtime.CompilerServices

<Assembly: CLSCompliant(True)>

Public Class ErrorClass : Inherits Exception
   Dim msg As String

   Public Sub New(errorMessage As String)
      msg = errorMessage
   End Sub

   Public Overrides ReadOnly Property Message As String
      Get
         Return msg
      End Get
   End Property
End Class

Public Module StringUtilities
   <Extension()> Public Function SplitString(value As String, index As Integer) As String()
      If index < 0 Or index > value.Length Then
         Dim BadIndex As New ErrorClass("The index is not within the string.")
         Throw BadIndex
      End If
      Dim retVal() As String = { value.Substring(0, index - 1),
                                 value.Substring(index) }
      Return retVal
   End Function
End Module
```

### <a name="attributes"></a>Атрибуты

В сборках .NET Framework настраиваемые атрибуты предоставляют расширяемый механизм хранения настраиваемых атрибутов и извлечения метаданных об объектах программирования (например, о сборках, типах, членах и параметрах методов). Настраиваемые атрибуты должны наследоваться от [System.Attribute](xref:System.Attribute) или типа, производного от `System.Attribute`.

Это правило не выполняется в следующем примере. В нем определяется класс `NumericAttribute`, который не является производным от `System.Attribute`. Обратите внимание, что компилятор выдает ошибку не при определении класса, а когда используется атрибут, который не является CLS-совместимым.

```csharp
using System;

[assembly: CLSCompliant(true)]

[AttributeUsageAttribute(AttributeTargets.Class | AttributeTargets.Struct)]
public class NumericAttribute
{
   private bool _isNumeric;

   public NumericAttribute(bool isNumeric)
   {
      _isNumeric = isNumeric;
   }

   public bool IsNumeric
   {
      get { return _isNumeric; }
   }
}

[Numeric(true)] public struct UDouble
{
   double Value;
}
// Compilation produces a compiler error like the following:
//    Attribute1.cs(22,2): error CS0616: 'NumericAttribute' is not an attribute class
//    Attribute1.cs(7,14): (Location of symbol related to previous error)
```

```vb
<Assembly: CLSCompliant(True)>

<AttributeUsageAttribute(AttributeTargets.Class Or AttributeTargets.Struct)> _
Public Class NumericAttribute
   Private _isNumeric As Boolean

   Public Sub New(isNumeric As Boolean)
      _isNumeric = isNumeric
   End Sub

   Public ReadOnly Property IsNumeric As Boolean
      Get
         Return _isNumeric
      End Get
   End Property
End Class

<Numeric(True)> Public Structure UDouble
   Dim Value As Double
End Structure
' Compilation produces a compiler error like the following:
'    error BC31504: 'NumericAttribute' cannot be used as an attribute because it
'    does not inherit from 'System.Attribute'.
'
'    <Numeric(True)> Public Structure UDouble
'     ~~~~~~~~~~~~~
```

Конструктор и свойства CLS-совместимого атрибута могут предоставлять только следующие типы:

* [Boolean](xref:System.Boolean)

* [Byte](xref:System.Byte)

* [Char](xref:System.Char)

* [Double](xref:System.Double)

* [Int16](xref:System.Int16)

* [Int32](xref:System.Int32)

* [Int64](xref:System.Int64)

* [Single](xref:System.Single)

* [String](xref:System.String)

* [Type](xref:System.Type)

* Любой тип перечисления с базовым типом `Byte`, `Int16`, `Int32` или `Int64`.

В следующем примере определяется класс `DescriptionAttribute`, производный от [Attribute](xref:System.Attribute). Конструктор класса имеет параметр типа `Descriptor`, поэтому класс не является CLS-совместимым. Обратите внимание, что компилятор C# выдает предупреждение, но при этом успешно завершает компиляцию.

```csharp
using System;

[assembly:CLSCompliantAttribute(true)]

public enum DescriptorType { type, member };

public class Descriptor
{
   public DescriptorType Type;
   public String Description;
}

[AttributeUsage(AttributeTargets.All)]
public class DescriptionAttribute : Attribute
{
   private Descriptor desc;

   public DescriptionAttribute(Descriptor d)
   {
      desc = d;
   }

   public Descriptor Descriptor
   { get { return desc; } }
}
// Attempting to compile the example displays output like the following:
//       warning CS3015: 'DescriptionAttribute' has no accessible
//               constructors which use only CLS-compliant types
```

```vb
<Assembly:CLSCompliantAttribute(True)>

Public Enum DescriptorType As Integer
   Type = 0
   Member = 1
End Enum

Public Class Descriptor
   Public Type As DescriptorType
   Public Description As String
End Class

<AttributeUsage(AttributeTargets.All)> _
Public Class DescriptionAttribute : Inherits Attribute
   Private desc As Descriptor

   Public Sub New(d As Descriptor)
      desc = d
   End Sub

   Public ReadOnly Property Descriptor As Descriptor
      Get
         Return desc
      End Get
   End Property
End Class
```

## <a name="the-clscompliantattribute-attribute"></a>Атрибут CLSCompliantAttribute

Атрибут [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) указывает, соответствует ли элемент правилам спецификации CLS. Конструктор `CLSCompliantAttribute.CLSCompliantAttribute(Boolean)` имеет один обязательный параметр *isCompliant*, определяющий, является ли элемент программы CLS-совместимым.

Компилятор определяет элементы, которые предположительно являются CLS-совместимыми, однако не соответствуют правилам спецификации CLS, и выдает предупреждение. Он пропускает типы и члены, которые явно объявлены как не соответствующие правилам спецификации CLS.

Разработчики компонентов могут использовать атрибут `CLSCompliantAttribute` двумя способами:

* Определять части открытого интерфейса, предоставляемые компонентом, которые являются или не являются CLS-совместимыми. Если с помощью этого атрибута пометить определенные элементы программы как CLS-совместимые, они будут доступны во всех языках и инструментах, ориентированных на .NET Framework.

* С его помощью обеспечить, чтобы открытый интерфейс библиотеки компонентов предоставлял только CLS-совместимые элементы программы. Если элементы не являются CLS-совместимыми, компиляторы обычно выдают предупреждение.

> [!WARNING]
> В некоторых случаях языковые компиляторы применяют правила CLS-совместимости вне зависимости от того, используется ли атрибут `CLSCompliantAttribute`. Например, когда в интерфейсе определяется член `*static`, нарушается правило CLS-совместимости. Однако если определить в интерфейсе член `*static`, компилятор C# выдает сообщение об ошибке и не компилирует приложение.

Атрибут `CLSCompliantAttribute` отмечен атрибутом [AttributeUsageAttribute](xref:System.AttributeUsageAttribute) со значением `AttributeTargets.All`. Это значение позволяет применять атрибут `CLSCompliantAttribute` к любым элементам программы: сборкам, модулям, типам (классам, структурам, перечислениям, интерфейсам и делегатам), членам типов (конструкторам, методам, свойствам, полям и событиям), параметрам, универсальным параметрам и возвращаемым значениям. Однако на практике атрибут рекомендуется применять только к сборкам, типам и членам типов. В противном случае компиляторы игнорируют атрибут и создают предупреждения для всех параметров, универсальных параметров и возвращаемых значений открытого интерфейса библиотеки, которые не являются CLS-совместимыми.

Значение атрибута `CLSCompliantAttribute` наследуется вложенными элементами программы. Например, если сборка отмечена как CLS-совместимая, ее типы также являются CLS-совместимыми. Если тип отмечен как CLS-совместимый, его вложенные типы и члены также являются CLS-совместимыми.

Можно явно переопределить наследуемую совместимость, применив к вложенному элементу программы атрибут `CLSCompliantAttribute`. Например, вы можете использовать атрибут `CLSCompliantAttribute`, указав для *isCompliant* значение `false`, чтобы определить в совместимой сборке несовместимый тип, а также использовать атрибут, указав для *isCompliant* значение `true`, чтобы определить в несовместимой сборке совместимый тип. Кроме того, можно определять несовместимые члены в совместимом типе. Однако несовместимый тип не может иметь совместимые члены, поэтому наследование от несовместимого типа невозможно переопределить с помощью параметра `true` со значением *isCompliant*.

При разработке компонентов следует всегда указывать, что сборка, ее типы и члены являются CLS-совместимыми с помощью атрибута `CLSCompliantAttribute`.

Создание CLS-совместимых компонентов

1. Пометьте сборку как CLS-совместимую с помощью атрибута `CLSCompliantAttribute`.

2. Пометьте все открытые типы в сборке, которые не являются CLS-совместимыми, как несовместимые.

3. Пометьте все открытые члены в CLS-совместимых типах как несовместимые.

4. Предоставьте CLS-совместимую альтернативу членам, которые не являются CLS-совместимыми.

Если все несовместимые типы и члены отмечены, компилятор не выдает предупреждений о несовместимости. Однако следует указать, какие члены не являются CLS-совместимым, и определить CLS-совместимые альтернативы в документации продукта.

В следующем примере с помощью атрибута `CLSCompliantAttribute` определяется CLS-совместимая сборка и тип `CharacterUtilities`, который имеет два члена, не являющихся CLS-совместимыми. Поскольку оба члена отмечены атрибутом `CLSCompliant(false)`, компилятор не выдает предупреждения. Класс также предоставляет CLS-совместимую альтернативу для обоих методов. В обычном случае мы бы добавили две перегрузки для метода `ToUTF16`, чтобы предоставить CLS-совместимые альтернативы. Однако методы не перегружаются на основе возвращаемого значения, поэтому CLS-совместимые и несовместимые методы имеют разные имена.

```csharp
using System;
using System.Text;

[assembly:CLSCompliant(true)]

public class CharacterUtilities
{
   [CLSCompliant(false)] public static ushort ToUTF16(String s)
   {
      s = s.Normalize(NormalizationForm.FormC);
      return Convert.ToUInt16(s[0]);
   }

   [CLSCompliant(false)] public static ushort ToUTF16(Char ch)
   {
      return Convert.ToUInt16(ch);
   }

   // CLS-compliant alternative for ToUTF16(String).
   public static int ToUTF16CodeUnit(String s)
   {
      s = s.Normalize(NormalizationForm.FormC);
      return (int) Convert.ToUInt16(s[0]);
   }

   // CLS-compliant alternative for ToUTF16(Char).
   public static int ToUTF16CodeUnit(Char ch)
   {
      return Convert.ToInt32(ch);
   }

   public bool HasMultipleRepresentations(String s)
   {
      String s1 = s.Normalize(NormalizationForm.FormC);
      return s.Equals(s1);
   }

   public int GetUnicodeCodePoint(Char ch)
   {
      if (Char.IsSurrogate(ch))
         throw new ArgumentException("ch cannot be a high or low surrogate.");

      return Char.ConvertToUtf32(ch.ToString(), 0);
   }

   public int GetUnicodeCodePoint(Char[] chars)
   {
      if (chars.Length > 2)
         throw new ArgumentException("The array has too many characters.");

      if (chars.Length == 2) {
         if (! Char.IsSurrogatePair(chars[0], chars[1]))
            throw new ArgumentException("The array must contain a low and a high surrogate.");
         else
            return Char.ConvertToUtf32(chars[0], chars[1]);
      }
      else {
         return Char.ConvertToUtf32(chars.ToString(), 0);
      }
   }
}
```

```vb
Imports System.Text

<Assembly:CLSCompliant(True)>

Public Class CharacterUtilities
   <CLSCompliant(False)> Public Shared Function ToUTF16(s As String) As UShort
      s = s.Normalize(NormalizationForm.FormC)
      Return Convert.ToUInt16(s(0))
   End Function

   <CLSCompliant(False)> Public Shared Function ToUTF16(ch As Char) As UShort
      Return Convert.ToUInt16(ch)
   End Function

   ' CLS-compliant alternative for ToUTF16(String).
   Public Shared Function ToUTF16CodeUnit(s As String) As Integer
      s = s.Normalize(NormalizationForm.FormC)
      Return CInt(Convert.ToInt16(s(0)))
   End Function

   ' CLS-compliant alternative for ToUTF16(Char).
   Public Shared Function ToUTF16CodeUnit(ch As Char) As Integer
      Return Convert.ToInt32(ch)
   End Function

   Public Function HasMultipleRepresentations(s As String) As Boolean
      Dim s1 As String = s.Normalize(NormalizationForm.FormC)
      Return s.Equals(s1)
   End Function

   Public Function GetUnicodeCodePoint(ch As Char) As Integer
      If Char.IsSurrogate(ch) Then
         Throw New ArgumentException("ch cannot be a high or low surrogate.")
      End If
      Return Char.ConvertToUtf32(ch.ToString(), 0)
   End Function

   Public Function GetUnicodeCodePoint(chars() As Char) As Integer
      If chars.Length > 2 Then
         Throw New ArgumentException("The array has too many characters.")
      End If
      If chars.Length = 2 Then
         If Not Char.IsSurrogatePair(chars(0), chars(1)) Then
            Throw New ArgumentException("The array must contain a low and a high surrogate.")
         Else
            Return Char.ConvertToUtf32(chars(0), chars(1))
         End If
      Else
         Return Char.ConvertToUtf32(chars.ToString(), 0)
      End If
   End Function
End Class
```

При разработке приложений (а не библиотек, где предоставляются типы и члены, которые могут использоваться другими разработчиками) вы столкнетесь с вопросами CLS-совместимости программных элементов, которые использует приложение, только если их не поддерживает язык, на котором вы работаете. И если вы попытаетесь использовать элементы, которые не являются CLS-совместимыми, языковой компилятор выдаст предупреждение.

## <a name="cross-language-interoperability"></a>Взаимная совместимость кодов на разных язык

Независимость от языка имеет несколько возможных значений. Первое значение подразумевает беспроблемное использование типов, созданных на одном языке, приложением, написанным на другом языке. Второе значение, которое рассматривается в этой статье, — это объединение кода, написанного на нескольких языках, в единую сборку .NET Framework.

В следующем примере показана организация межъязыкового взаимодействия путем создания библиотеки классов с именем "Utilities.dll", которая содержит два класса: `NumericLib` и `StringLib`. Класс `NumericLib` написан на C#, а класс `StringLib` — на Visual Basic. Ниже приведен исходный код для `StringUtil.vb`, который содержит один член — `ToTitleCase` — в своем классе `StringLib`.

```vb
Imports System.Collections.Generic
Imports System.Runtime.CompilerServices

Public Module StringLib
   Private exclusions As List(Of String)

   Sub New()
      Dim words() As String = { "a", "an", "and", "of", "the" }
      exclusions = New List(Of String)
      exclusions.AddRange(words)
   End Sub

   <Extension()> _
   Public Function ToTitleCase(title As String) As String
      Dim words() As String = title.Split()
      Dim result As String = String.Empty

      For ctr As Integer = 0 To words.Length - 1
         Dim word As String = words(ctr)
         If ctr = 0 OrElse Not exclusions.Contains(word.ToLower()) Then
            result += word.Substring(0, 1).ToUpper() + _
                      word.Substring(1).ToLower()
         Else
            result += word.ToLower()
         End If
         If ctr <= words.Length - 1 Then
            result += " "
         End If
      Next
      Return result
   End Function
End Module
```

Ниже приведен исходный код для "NumberUtil.cs", определяющий класс `NumericLib` с двумя членами: `IsEven` и `NearZero`.

```csharp
using System;

public static class NumericLib
{
   public static bool IsEven(this IConvertible number)
   {
      if (number is Byte ||
          number is SByte ||
          number is Int16 ||
          number is UInt16 ||
          number is Int32 ||
          number is UInt32 ||
          number is Int64)
         return ((long) number) % 2 == 0;
      else if (number is UInt64)
         return ((ulong) number) %2 == 0;
      else
         throw new NotSupportedException("IsEven called for a non-integer value.");
   }

   public static bool NearZero(double number)
   {
      return number < .00001;
   }
}
```

Чтобы упаковать оба класса в одну сборку, необходимо скомпилировать их в модули. Чтобы скомпилировать файл исходного кода на Visual Basic в модуль, используйте следующую команду.

```console
vbc /t:module StringUtil.vb
```

Чтобы скомпилировать файл исходного кода на C# в модуль, используйте следующую команду.

```console
csc /t:module NumberUtil.cs
```

Затем вызовите компоновщик (Link.exe), чтобы скомпилировать оба модуля в сборку.

```console
link numberutil.netmodule stringutil.netmodule /out:UtilityLib.dll /dll
```

В следующем примере показаны вызовы методов `NumericLib.NearZero` и `StringLib.ToTitleCase`. Обратите внимание, что и код Visual Basic, и код C#, могут обращаться к методам в обоих классах.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      Double dbl = 0.0 - Double.Epsilon;
      Console.WriteLine(NumericLib.NearZero(dbl));

      string s = "war and peace";
      Console.WriteLine(s.ToTitleCase());
   }
}
// The example displays the following output:
//       True
//       War and Peace
```

```vb
Module Example
   Public Sub Main()
      Dim dbl As Double = 0.0 - Double.Epsilon
      Console.WriteLine(NumericLib.NearZero(dbl))

      Dim s As String = "war and peace"
      Console.WriteLine(s.ToTitleCase())
   End Sub
End Module
' The example displays the following output:
'       True
'       War and Peace
```

Чтобы скомпилировать код Visual Basic, используйте следующую команду.

```console
vbc example.vb /r:UtilityLib.dll
```

Чтобы скомпилировать C#, измените имя компилятора с vbc на csc и расширение файла на с VB на CS.

```console
csc example.cs /r:UtilityLib.dll
```
