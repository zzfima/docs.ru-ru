---
title: "Составное форматирование"
description: "Составное форматирование"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/25/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: a01efc8f-c242-4535-bd32-acd0032d9590
translationtype: Human Translation
ms.sourcegitcommit: 90ade65e167770bdbcbbf79707fe48e6fbc030c0
ms.openlocfilehash: 5b61b4736880d57f02070150d8613d860505b268

---

# <a name="composite-formatting"></a>Составное форматирование

В качестве входных данных для составного форматирования в .NET используется список объектов и строка составного формата. Строка составного формата состоит из фиксированного текста, в который включены индексированные местозаполнители, которые называются элементами форматирования и соответствуют объектам из списка. Операция форматирования создает результирующую строку, состоящую из исходного фиксированного текста, в который включено строковое представление объектов из списка. 

Возможность составного форматирования поддерживается следующими методами: 

* Метод [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)), который возвращает отформатированную результирующую строку. 

* [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)), который добавляет отформатированную строку результата в объект [StringBuilder](xref:System.Text.StringBuilder).

* Некоторые перегруженные версии метода [Console](xref:System.Console) `WriteLine`, которые отображают отформатированную результирующую строку в консоли.  

* Некоторые перегруженные версии метода [TextWriter](xref:System.IO.TextWriter) `WriteLine`, которые записывают отформатированную результирующую строку в поток или файл. Классы, производные от [TextWriter](xref:System.IO.TextWriter), например [StreamWriter](xref:System.IO.StreamWriter), также поддерживают эту функцию.

* Метод [Debug.WriteLine(String, Object[])](xref:System.Diagnostics.Debug.WriteLine(System.String,System.Object[])), который выводит отформатированное сообщение в прослушиватели трассировки. 

* Методы [Trace.TraceError(String, Object[])](xref:System.Diagnostics.Trace.TraceError(System.String,System.Object[])), [Trace.TraceInformation(String, Object[])](xref:System.Diagnostics.Trace.TraceInformation(System.String,System.Object[])) и [Trace.TraceWarning(String, Object[])](xref:System.Diagnostics.Trace.TraceWarning(System.String,System.Object[])), которые выводят отформатированные сообщения в прослушиватели трассировки. 

* Метод [TraceSource.TraceInformation(String, Object[])](xref:System.Diagnostics.TraceSource.TraceInformation(System.String,System.Object[])), который записывает информационный метод в прослушиватели трассировки. 

## <a name="composite-format-string"></a>Строка составного формата

Строка составного формата и список объектов используются в качестве аргументов методов, поддерживающих составное форматирование. Строка составного формата состоит из блоков фиксированного текста числом от нуля и больше, перемежаемых одним или несколькими элементами форматирования. Фиксированным текстом может являться произвольная строка, а каждый элемент форматирования должен соответствовать объекту или упакованной структуре из списка. В ходе составного форматирования создается новая результирующая строка, в которой все элементы форматирования заменены на строковое представление соответствующих объектов из списка.

Рассмотрим следующий фрагмент кода [форматирования](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)).

```csharp
string name = "Fred";
String.Format("Name = {0}, hours = {1:hh}", name, DateTime.Now);
```

```vb
Dim name As String = "Fred"
String.Format("Name = {0}, hours = {1:hh}", name, DateTime.Now)
```

Фиксированным текстом здесь является `"Name = "` и `", hours = "`. Элементы форматирования здесь — это `"{0}"` c индексом 0, который соответствует объекту `name`, и `"{1:hh}"` с индексом 1, который соответствует объекту `DateTime.Now`.

## <a name="format-item-syntax"></a>Синтаксис элементов форматирования

Каждый элемент форматирования имеет следующий вид и состоит из следующих компонентов:

__{__*index*[,*alignment*][:*formatString*]__}__

Парные фигурные скобки ("{" и "}") здесь обязательны. 
 
### <a name="index-component"></a>Индекс

Обязательный компонент *index*, также называемый описателем параметра, — это число, определяющее соответствующий объект из списка; индексация элементов ведется от нуля. Иными словами, элемент форматирования с индексом 0 отвечает за формат первого объекта в списке, элемент форматирования с индексом 1 служит для форматирования второго объекта в списке и т. д. В пример ниже входят четыре описателя параметров (от нуля до трех) для представления простых чисел меньше&10;. 

```csharp
string primes;
primes = String.Format("Prime numbers less than 10: {0}, {1}, {2}, {3}",
                       2, 3, 5, 7 );
Console.WriteLine(primes);
// The example displays the following output:
//      Prime numbers less than 10: 2, 3, 5, 7
```

```vb
Dim primes As String
primes = String.Format("Prime numbers less than 10: {0}, {1}, {2}, {3}",
                       2, 3, 5, 7 )
Console.WriteLine(primes)
' The example displays the following output:
'      Prime numbers less than 10: 2, 3, 5, 7
```

На один и тот же элемент в списке объектов может ссылаться сразу несколько элементов форматирования — достигается это путем задания одинакового описателя параметра. Например, одно и то же числовое значение можно перевести в формат шестнадцатеричного, экспоненциального и десятичного числа, задав строку составного формата, например "0x{0:X} {0:E} {0:N}", как показано в примере ниже. 

```csharp
string multiple = String.Format("0x{0:X} {0:E} {0:N}",
                                Int64.MaxValue);
Console.WriteLine(multiple);
// The example displays the following output:
//      0x7FFFFFFFFFFFFFFF 9.223372E+018 9,223,372,036,854,775,807.00
```

```vb
Dim multiple As String = String.Format("0x{0:X} {0:E} {0:N}",
                                       Int64.MaxValue)
Console.WriteLine(multiple)
' The example displays the following output:
'      0x7FFFFFFFFFFFFFFF 9.223372E+018 9,223,372,036,854,775,807.00
```

Любой элемент форматирования может ссылаться на произвольный объект списка. Например, если имеется три объекта, то можно отформатировать сначала второй, а затем первый и третий объекты, задав следующую строку составного форматирования: "{1} {0} {2}". Объекты, на которые не ссылаются элементы форматирования, пропускаются. Если описатель параметра ссылается на элемент за пределами списка объектов, то во время выполнения создается исключение [FormatException](xref:System.FormatException).

### <a name="alignment-component"></a>Выравнивание

Необязательный компонент *alignment* — это целое число со знаком, которое служит для указания желательной ширины поля форматирования. Если значение *alignment* меньше длины форматируемой строки, то *alignment* пропускается, и в качестве значения ширины поля используется длина форматируемой строки. Форматируемые данные выравниваются в поле по правому краю, если *alignment* имеет положительное значение, или по левому краю, если *alignment* имеет отрицательное значение. При необходимости отформатированная строка дополняется пробелами. При использовании компонента *alignment* необходимо поставить запятую.

В примере ниже определяются два массива: один содержит имена сотрудников, а второй — количество часов, которые они проработали в течение двух недель. Строка составного формата выравнивает имена по левому краю 20-символьного поля, а часы работы — по правому краю 5-символьного поля. Обратите внимание, что строка стандартного формата "N1" также используется для форматирования часов с одной цифрой дробной части. 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string[] names = { "Adam", "Bridgette", "Carla", "Daniel",
                         "Ebenezer", "Francine", "George" };
      decimal[] hours = { 40, 6.667m, 40.39m, 82, 40.333m, 80,
                                 16.75m };

      Console.WriteLine("{0,-20} {1,5}\n", "Name", "Hours");
      for (int ctr = 0; ctr < names.Length; ctr++)
         Console.WriteLine("{0,-20} {1,5:N1}", names[ctr], hours[ctr]);

   }
}
// The example displays the following output:
//       Name                 Hours
//
//       Adam                  40.0
//       Bridgette              6.7
//       Carla                 40.4
//       Daniel                82.0
//       Ebenezer              40.3
//       Francine              80.0
//       George                16.8
```

```vb
Module Example
   Public Sub Main()
      Dim names() As String = { "Adam", "Bridgette", "Carla", "Daniel",
                                "Ebenezer", "Francine", "George" }
      Dim hours() As Decimal = { 40, 6.667d, 40.39d, 82, 40.333d, 80,
                                 16.75d }

      Console.WriteLine("{0,-20} {1,5}", "Name", "Hours")
      Console.WriteLine()
      For ctr As Integer = 0 To names.Length - 1
         Console.WriteLine("{0,-20} {1,5:N1}", names(ctr), hours(ctr))
      Next
   End Sub
End Module
' The example displays the following output:
'       Name                 Hours
'
'       Adam                  40.0
'       Bridgette              6.7
'       Carla                 40.4
'       Daniel                82.0
'       Ebenezer              40.3
'       Francine              80.0
'       George                16.8
```

### <a name="format-string-component"></a>Компонент строки формата

Необязательный компонент *formatString* — это строка формата, соответствующая типу форматируемого объекта. Если соответствующий объект является объектом [DateTime](xref:System.DateTime), то используется строка стандартного или настраиваемого формата чисел, а если соответствующий объект является значением перечисления, то используется [строка формата перечисления](enumeration-format.md). Если компонент *formatString* не задан, то для числовых значений, значений даты и времени, а также перечислений используется общий формат ("G"). При использовании компонента *formatString* необходимо двоеточие.

В следующей таблице перечислены типы и категории типов в библиотеке классов .NET Framework, которые поддерживают предопределенный набор строк формата, а также ссылки на разделы, в которых перечисляются поддерживаемые строки формата. Обратите внимание, что форматирование строк — это расширяемый механизм, который позволяет определять новые строки формата для всех существующих типов, а также определять набор строк формата, поддерживаемых прикладным типом. Дополнительные сведения см. в разделах, посвященных интерфейсам [IFormattable](xref:System.IFormattable) и [ICustomFormatter](xref:System.ICustomFormatter). 

Тип или категория типов | См.
--------------------- | ---
Типы даты и времени ([DateTime](xref:System.DateTime), [DateTimeOffset](xref:System.DateTimeOffset)) | [Строки стандартных форматов даты и времени](standard-datetime.md), [Строки настраиваемых форматов даты и времени](custom-datetime.md)
Типы перечисления (все типы, производные от [System.Enum](xref:System.Enum)) | [Строки форматов перечисления](enumeration-format.md)
Числовые типы ([BigInteger](xref:System.Numerics.BigInteger), [Byte](xref:System.Byte), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64)) | [Строки стандартных числовых форматов](standard-numeric.md), [Строки настраиваемых числовых форматов](custom-numeric.md)
[Guid](xref:System.Guid) | [Guid.ToString(String)](xref:System.Guid.ToString(System.String))
[TimeSpan](xref:System.TimeSpan) | [Строки стандартного формата TimeSpan](standard-timespan.md), [Строки пользовательского формата TimeSpan](custom-timespan.md)

### <a name="escaping-braces"></a>Оформление фигурных скобок

Начало и конец элемента форматирования обозначаются соответственно открывающей и закрывающей фигурной скобкой. Это означает, что для вывода открывающих и закрывающих фигурных скобок необходимо использовать escape-последовательности. Для вывода открывающей или закрывающей фигурной скобки в фиксированном тексте следует поставить две открывающие или, соответственно, закрывающие фигурные скобки подряд ("{{" или "}}"). Фигурные скобки в элементе форматирования интерпретируются последовательно в порядке их обнаружения. Интерпретация вложенных скобок не поддерживается. 

Порядок интерпретации скобок может привести к непредвиденным результатам. Например, рассмотрим элемент форматирования "{{{0:D}}}", который должен вывести открывающую фигурную скобку, числовое значение, отформатированное в десятичном виде, и закрывающую фигурную скобку. В действительности элемент форматирования будет интерпретирован следующим образом: 

1. Первые две открывающие фигурные скобки ("{{") составляют escape-последовательность, которая дает в итоге одиночную открывающую фигурную скобку. 

2. Следующие три знака ("{0:") воспринимаются как начало элемента форматирования.

3. Следующий знак ("D") должен интерпретироваться как указатель на десятичный числовой формат, но стоящая за ним пара фигурных скобок ("}}") дает в результате одиночную фигурную скобку. Поскольку результирующая строка ("D}") не является стандартным описателем числового формата, то она будет интерпретирована как строка пользовательского формата, что приведет к выводу строки "D}". 

4. Последняя фигурная скобка ("}") интерпретируется как конец элемента форматирования. 

5. Итоговый результат, который будет выведен — строка "{D}". Числовое значение, которое требовалось отформатировать, выведено не будет.

Одним из способов избежать неправильной интерпретации фигурных скобок и элементов форматирования при написании кода является раздельное форматирование фигурных скобок и элементов форматирования. Это означает, что первая операция форматирования должна выводить строку с открывающей фигурной скобкой, следующая операция — результат обработки элемента форматирования, а последняя операция — строку с закрывающей фигурной скобкой. Этот подход показан в приведенном ниже примере.

```csharp
int value = 6324;
string output = string.Format("{0}{1:D}{2}", 
                             "{", value, "}");
Console.WriteLine(output);
// The example displays the following output:
//       {6324} 
```

```vb
Dim value As Integer = 6324
Dim output As String = String.Format("{0}{1:D}{2}", _
                                     "{", value, "}")
Console.WriteLine(output)   
' The example displays the following output:
'       {6324}
```

### <a name="processing-order"></a>Порядок обработки

Если вызов метода составного форматирования содержит аргумент [IFormatProvider](xref:System.IFormatProvider), значение которого не равно NULL, среда выполнения вызывает метод [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)), чтобы запросить реализацию [ICustomFormatter](xref:System.ICustomFormatter). Если метод может вернуть реализацию [ICustomFormatter](xref:System.ICustomFormatter), он кэшируется для последующего использования. 

Каждое значение в списке параметров, соответствующее элементу форматирования, преобразуется в строку путем выполнения нижеперечисленных действий. Если любое условие на первых трех шагах принимает логическое значение "true", строковое представление значения возвращается на этот шаг, и последующие шаги не выполняются.

1. Если форматируемое значение является значением `null`, возвращается пустая строка (""). 

2. Если реализация [ICustomFormatter](xref:System.ICustomFormatter) доступна, среда выполнения вызывает ее метод [Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)). Она передает в метод значение элемента форматирования *formatString* (при его наличии) или значение `null` (в случае его отсутствия) вместе с реализацией [IFormatProvider](xref:System.IFormatProvider). 

3. Если значение реализует интерфейс [IFormattable](xref:System.IFormattable), вызывается метод [ToString(String, IFormatProvider)](xref:System.IFormattable.ToString(System.String,System.IFormatProvider)) этого интерфейса. Методу передается значение *formatString* (при его наличии в элементе форматирования) или значение `null` (в случае его отсутствия). Аргумент [IFormatProvider](xref:System.IFormatProvider) определяется следующим образом:

    *   Для числового значения, если вызывается метод составного форматирования с аргументом [IFormatProvider](xref:System.IFormatProvider), не равным NULL, то среда выполнения запрашивает объект [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) из метода [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)). Если не удалось предоставить объект, если аргумент имеет значение `null` или если метод составного форматирования не имеет параметра [IFormatProvider](xref:System.IFormatProvider), то используется объект [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) для языка и региональных параметров текущего потока. 
    
    * Для значения даты и времени, если вызывается метод составного форматирования с аргументом [IFormatProvider](xref:System.IFormatProvider), не равным NULL, то среда выполнения запрашивает объект [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) из метода [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)). Если не удалось предоставить объект, если аргумент имеет значение `null` или метод составного форматирования не имеет параметра [IFormatProvider](xref:System.IFormatProvider), то используется объект [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) для языка и региональных параметров текущего потока. 
    
    * Для объектов других типов, если метод составного форматирования вызывается с аргументом [IFormatProvider](xref:System.IFormatProvider), его значение (в том числе и `null`, если объект [IFormatProvider](xref:System.IFormatProvider) не задан) передается непосредственно в реализацию [IFormattable.ToString](xref:System.IFormattable.ToString(System.String,System.IFormatProvider)). В противном случае объект [CultureInfo](xref:System.Globalization.CultureInfo), который представляет язык и региональные параметры текущего потока, передается в реализацию [IFormattable.ToString](xref:System.IFormattable.ToString(System.String,System.IFormatProvider)). 
    
4. Вызывается метод `ToString` без параметров, который переопределяет [Object.ToString()](xref:System.Object.ToString) или наследует поведение базового класса. В этом случае строка формата, указанная в компоненте *formatString* в элементе форматирования (при его наличии), игнорируется.

После выполнения предшествующих шагов производится выравнивание. 

## <a name="code-examples"></a>Примеры кода

В приведенном ниже примере одна строка создается с помощью составного форматирования, а другая – с помощью метода `ToString`. Оба способа форматирования дают идентичные результаты. 

```csharp
string FormatString1 = String.Format("{0:dddd MMMM}", DateTime.Now);
string FormatString2 = DateTime.Now.ToString("dddd MMMM");
```

```vb
Dim FormatString1 As String = String.Format("{0:dddd MMMM}", DateTime.Now)
Dim FormatString2 As String = DateTime.Now.ToString("dddd MMMM")
```

Предположим, что сейчас май, а текущий день недели — четверг. Тогда значение обеих строк в предыдущем примере будет `Thursday May` для языка и региональных параметров "Английский (США)".

Метод [Console.WriteLine](xref:System.Console.WriteLine) предоставляет те же функциональные возможности, что и метод [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)). Единственное различие между этими двумя методами состоит в том, что метод [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) возвращает результаты в виде строки, а метод [Console.WriteLine](xref:System.Console.WriteLine) записывает результаты в поток вывода, связанный с объектом [Console](xref:System.Console). В следующем примере для форматирования значения переменной `MyInt` в виде денежного значения используется метод [Console.WriteLine](xref:System.Console.WriteLine).

```csharp
int MyInt = 100;
Console.WriteLine("{0:C}", MyInt);
// The example displays the following output 
// if en-US is the current culture:
//        $100.00
```

```vb
Dim MyInt As Integer = 100
Console.WriteLine("{0:C}", MyInt)
' The example displays the following output
' if en-US is the current culture:
'        $100.00
```

В следующем примере демонстрируется форматирование нескольких объектов, в том числе форматирование одного и того же объекта двумя разными способами.

```csharp
string myName = "Fred";
Console.WriteLine(String.Format("Name = {0}, hours = {1:hh}, minutes = {1:mm}",
      myName, DateTime.Now));
// Depending on the current time, the example displays output like the following:
//    Name = Fred, hours = 11, minutes = 30                 
```

```vb
Dim myName As String = "Fred"
Console.WriteLine(String.Format("Name = {0}, hours = {1:hh}, minutes = {1:mm}", _
                  myName, DateTime.Now))
' Depending on the current time, the example displays output like the following:
'    Name = Fred, hours = 11, minutes = 30
```

В следующем примере показывается использование выравнивания при форматировании. Форматируемые аргументы разделены знаками вертикальной черты ("|"), подчеркивающими полученное выравнивание.

```csharp
string myFName = "Fred";
string myLName = "Opals";
int myInt = 100;
string FormatFName = String.Format("First Name = |{0,10}|", myFName);
string FormatLName = String.Format("Last Name = |{0,10}|", myLName);
string FormatPrice = String.Format("Price = |{0,10:C}|", myInt); 
Console.WriteLine(FormatFName);
Console.WriteLine(FormatLName);
Console.WriteLine(FormatPrice);
Console.WriteLine();

FormatFName = String.Format("First Name = |{0,-10}|", myFName);
FormatLName = String.Format("Last Name = |{0,-10}|", myLName);
FormatPrice = String.Format("Price = |{0,-10:C}|", myInt);
Console.WriteLine(FormatFName);
Console.WriteLine(FormatLName);
Console.WriteLine(FormatPrice);
// The example displays the following output on a system whose current
// culture is en-US:
//          First Name = |      Fred|
//          Last Name = |     Opals|
//          Price = |   $100.00|
//
//          First Name = |Fred      |
//          Last Name = |Opals     |
//          Price = |$100.00   |
```

```vb
Dim myFName As String = "Fred"
Dim myLName As String = "Opals"

Dim myInt As Integer = 100
Dim FormatFName As String = String.Format("First Name = |{0,10}|", myFName)
Dim FormatLName As String = String.Format("Last Name = |{0,10}|", myLName)
Dim FormatPrice As String = String.Format("Price = |{0,10:C}|", myInt)
Console.WriteLine(FormatFName)
Console.WriteLine(FormatLName)
Console.WriteLine(FormatPrice)
Console.WriteLine()

FormatFName = String.Format("First Name = |{0,-10}|", myFName)
FormatLName = String.Format("Last Name = |{0,-10}|", myLName)
FormatPrice = String.Format("Price = |{0,-10:C}|", myInt)
Console.WriteLine(FormatFName)
Console.WriteLine(FormatLName)
Console.WriteLine(FormatPrice)
' The example displays the following output on a system whose current
' culture is en-US:
'          First Name = |      Fred|
'          Last Name = |     Opals|
'          Price = |   $100.00|
'
'          First Name = |Fred      |
'          Last Name = |Opals     |
'          Price = |$100.00   |
```

## <a name="see-also"></a>См. также

[Console.WriteLine](xref:System.Console.WriteLine)

[String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))

[Типы форматирования](formatting-types.md)

[Строки стандартных форматов даты и времени](standard-datetime.md)

[Строки настраиваемых форматов даты и времени](custom-datetime.md)

[Строки форматов перечисления](enumeration-format.md)

[Строки стандартных числовых форматов](standard-numeric.md)

[Строки настраиваемых числовых форматов](custom-numeric.md)

[Строки стандартного формата TimeSpan](standard-timespan.md)

[Строки настраиваемого формата TimeSpan](custom-timespan.md)



<!--HONumber=Feb17_HO1-->


