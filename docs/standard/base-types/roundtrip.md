---
title: "Практическое руководство. Обеспечение однозначности при сохранении и восстановлении значений даты и времени"
description: "Практическое руководство. Обеспечение однозначности при сохранении и восстановлении значений даты и времени"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 15690f18-1bb9-4bb8-bc11-0b737e2f0859
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: b4bf747faff171e4a90a897e5f7ef442012e7699

---

# <a name="how-to-round-trip-date-and-time-values"></a>Практическое руководство. Обеспечение однозначности при сохранении и восстановлении значений даты и времени

Во многих приложениях значение даты и времени предназначено для однозначного определения одного момента времени. В этом разделе показано, как сохранять и восстанавливать значения [DateTime](xref:System.DateTime) и [DateTimeOffset](xref:System.DateTimeOffset), чтобы восстановленное значение определяло то же самое время, что и сохраненное значение.

## <a name="to-round-trip-a-datetime-value"></a>Выполнение цикла обработки значения DateTime

1. Преобразуйте значение [DateTime](xref:System.DateTime) в строковое представление посредством вызова метода [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)) с описателем формата "o".

2. Сохраните строковое представление значения [DateTime](xref:System.DateTime) в файл или передайте его между процессами, доменами приложений или между компьютерами.

3. Получите строку, представляющую значение [DateTime](xref:System.DateTime).

4. Вызовите метод [DateTime.Parse(String, IFormatProvider, DateTimeStyles)](xref:System.DateTime.Parse(System.String,System.IFormatProvider,System.Globalization.DateTimeStyles)) и передайте [DateTimeStyles.RoundtripKind](xref:System.Globalization.DateTimeStyles.RoundtripKind) в качестве значения параметра *DateTimeStyles*.

В следующем примере показано, как выполнить цикл обработки значения [DateTime](xref:System.DateTime).

```csharp
const string fileName = @".\DateFile.txt";

StreamWriter outFile = new StreamWriter(fileName);

// Save DateTime value.
DateTime dateToSave = DateTime.SpecifyKind(new DateTime(2008, 6, 12, 18, 45, 15), 
                                           DateTimeKind.Local);
string dateString = dateToSave.ToString("o");      
Console.WriteLine("Converted {0} ({1}) to {2}.", 
                  dateToSave.ToString(), 
                  dateToSave.Kind.ToString(), 
                  dateString);      
outFile.WriteLine(dateString);
Console.WriteLine("Wrote {0} to {1}.", dateString, fileName);
outFile.Close();

// Restore DateTime value.
DateTime restoredDate;

StreamReader inFile = new StreamReader(fileName);
dateString = inFile.ReadLine();
inFile.Close();
restoredDate = DateTime.Parse(dateString, null, DateTimeStyles.RoundtripKind);
Console.WriteLine("Read {0} ({2}) from {1}.", restoredDate.ToString(), 
                                              fileName, 
                                              restoredDate.Kind.ToString());
// The example displays the following output:
//    Converted 6/12/2008 6:45:15 PM (Local) to 2008-06-12T18:45:15.0000000-05:00.
//    Wrote 2008-06-12T18:45:15.0000000-05:00 to .\DateFile.txt.
//    Read 6/12/2008 6:45:15 PM (Local) from .\DateFile.txt.
```

```vb
Const fileName As String = ".\DateFile.txt"

Dim outFile As New StreamWriter(fileName)

' Save DateTime value.
Dim dateToSave As Date = DateTime.SpecifyKind(#06/12/2008 6:45:15 PM#, _
                                              DateTimeKind.Local)
Dim dateString As String = dateToSave.ToString("o")      
Console.WriteLine("Converted {0} ({1}) to {2}.", dateToSave.ToString(), _
                  dateToSave.Kind.ToString(), dateString)      
outFile.WriteLine(dateString)
Console.WriteLine("Wrote {0} to {1}.", dateString, fileName)
outFile.Close()   

' Restore DateTime value.
Dim restoredDate As Date

Dim inFile As New StreamReader(fileName)
dateString = inFile.ReadLine()
inFile.Close()
restoredDate = DateTime.Parse(dateString, Nothing, DateTimeStyles.RoundTripKind)
Console.WriteLine("Read {0} ({2}) from {1}.", restoredDate.ToString(), _
                  fileName, restoredDAte.Kind.ToString())
' The example displays the following output:
'    Converted 6/12/2008 6:45:15 PM (Local) to 2008-06-12T18:45:15.0000000-05:00.
'    Wrote 2008-06-12T18:45:15.0000000-05:00 to .\DateFile.txt.
'    Read 6/12/2008 6:45:15 PM (Local) from .\DateFile.txt.
```

Во время цикла обработки значения [DateTime](xref:System.DateTime) этот метод успешно сохраняет время для всех значений локального и универсального времени. Например, если локальное значение [DateTime](xref:System.DateTime) сохранено в системе в тихоокеанском стандартном часовом поясе США и восстановлено в системе в центральном стандартном часовом поясе США, восстановленные дата и время будут на два часа больше исходного времени, что отражает разницу во времени между двумя часовыми поясами. Однако этот способ не всегда точен для неуказанного времени. Любое значение [DateTime](xref:System.DateTime), свойством [Kind](xref:System.DateTime.Kind) которого является [Unspecified](xref:System.DateTimeKind.Unspecified), рассматривается как локальное время. Если это не так, [DateTime](xref:System.DateTime) не будет успешно определять корректный момент времени. Чтобы устранить это ограничение, нужно тесно связать значение даты и времени с его часовым поясом для операций сохранения и восстановления.

## <a name="to-round-trip-a-datetimeoffset-value"></a>Выполнение цикла обработки значения DateTimeOffset

Преобразуйте значение [DateTimeOffset](xref:System.DateTimeOffset) в строковое представление посредством вызова метода [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) с описателем формата "o".

2. Сохраните строковое представление значения [DateTimeOffset](xref:System.DateTimeOffset) в файл или передайте его между процессами, доменами приложений или между компьютерами.

3. Получите строку, представляющую значение [DateTimeOffset](xref:System.DateTimeOffset).

4. Вызовите метод [DateTimeOffset.Parse(String, IFormatProvider, DateTimeStyles)](xref:System.DateTimeOffset.Parse(System.String,System.IFormatProvider,System.Globalization.DateTimeStyles)) и передайте [DateTimeStyles.RoundtripKind](xref:System.Globalization.DateTimeStyles.RoundtripKind) в качестве значения параметра *styles*.

В следующем примере показано, как выполнить цикл обработки значения [DateTimeOffset](xref:System.DateTimeOffset).

```csharp
const string fileName = @".\DateOff.txt";

StreamWriter outFile = new StreamWriter(fileName);

// Save DateTime value.
DateTimeOffset dateToSave = new DateTimeOffset(2008, 6, 12, 18, 45, 15, 
                                               new TimeSpan(7, 0, 0));
string dateString = dateToSave.ToString("o");      
Console.WriteLine("Converted {0} to {1}.", dateToSave.ToString(), 
                  dateString);      
outFile.WriteLine(dateString);
Console.WriteLine("Wrote {0} to {1}.", dateString, fileName);
outFile.Close();

// Restore DateTime value.
DateTimeOffset restoredDateOff;

StreamReader inFile = new StreamReader(fileName);
dateString = inFile.ReadLine();
inFile.Close();
restoredDateOff = DateTimeOffset.Parse(dateString, null, 
                                       DateTimeStyles.RoundtripKind);
Console.WriteLine("Read {0} from {1}.", restoredDateOff.ToString(), 
                  fileName);
// The example displays the following output:
//    Converted 6/12/2008 6:45:15 PM +07:00 to 2008-06-12T18:45:15.0000000+07:00.
//    Wrote 2008-06-12T18:45:15.0000000+07:00 to .\DateOff.txt.
//    Read 6/12/2008 6:45:15 PM +07:00 from .\DateOff.txt.
```

```vb
Const fileName As String = ".\DateOff.txt"

Dim outFile As New StreamWriter(fileName)

' Save DateTime value.
Dim dateToSave As New DateTimeOffset(2008, 6, 12, 18, 45, 15, _
                                     New TimeSpan(7, 0, 0))
Dim dateString As String = dateToSave.ToString("o")      
Console.WriteLine("Converted {0} to {1}.", dateToSave.ToString(), dateString)      
outFile.WriteLine(dateString)
Console.WriteLine("Wrote {0} to {1}.", dateString, fileName)
outFile.Close()   

' Restore DateTime value.
Dim restoredDateOff As DateTimeOffset

Dim inFile As New StreamReader(fileName)
dateString = inFile.ReadLine()
inFile.Close()
restoredDateOff = DateTimeOffset.Parse(dateString, Nothing, DateTimeStyles.RoundTripKind)
Console.WriteLine("Read {0} from {1}.", restoredDateOff.ToString(), fileName)
' The example displays the following output:
'    Converted 6/12/2008 6:45:15 PM +07:00 to 2008-06-12T18:45:15.0000000+07:00.
'    Wrote 2008-06-12T18:45:15.0000000+07:00 to .\DateOff.txt.
'    Read 6/12/2008 6:45:15 PM +07:00 from .\DateOff.txt.
```

Этот метод всегда однозначно идентифицирует значение [DateTimeOffset](xref:System.DateTimeOffset) как единственный момент времени. Значение затем может быть преобразовано в универсальное синхронизированное время (UTC) посредством вызова метода [DateTimeOffset.ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) или оно может быть преобразовано во время в конкретном часовом поясе посредством вызова метода [DateTimeOffset.ToOffset](xref:System.DateTimeOffset.ToOffset(System.TimeSpan)) или метода [TimeZoneInfo.ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo). Основным ограничением этого способа являются арифметические действия с датами и временем, которые при выполнении их над значением [DateTimeOffset](xref:System.DateTimeOffset), представляющим время в определенном часовом поясе, могут возвратить неточные результаты для этого часового пояса. Это происходит потому, что при создании значения [DateTimeOffset](xref:System.DateTimeOffset) оно не связано со своим часовым поясом. Таким образом, правила коррекции часового пояса не могут быть больше применены при выполнении вычислений с датами и временем. Можно обойти эту проблему, определив пользовательский тип, который содержит значение даты и времени с его соответствующим часовым поясом.

## <a name="see-also"></a>См. также

[Выполнение операций форматирования](performing-formatting-operations.md)

[Строки стандартных форматов даты и времени](standard-datetime.md)




<!--HONumber=Nov16_HO3-->


