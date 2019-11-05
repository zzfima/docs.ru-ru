---
title: Практическое руководство. Сохранение и восстановление значения даты и времени
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- round-trip date and time values
- dates [.NET Framework], round-trip values
- time zones [.NET Framework], round-trip date and time values
- time [.NET Framework], round-trip values
- formatting strings [.NET Framework], round-trip values
ms.assetid: b609b277-edc6-4c74-b03e-ea73324ecbdb
ms.openlocfilehash: 2e3a58ffe8332e0afec62461f6897d673e1da09f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132008"
---
# <a name="how-to-round-trip-date-and-time-values"></a>Практическое руководство. Сохранение и восстановление значения даты и времени

Во многих приложениях значение даты и времени предназначено для однозначного определения одного момента времени. В этой статье показано, как правильно сохранять и восстанавливать значения <xref:System.DateTime> и <xref:System.DateTimeOffset>, а также значения времени с информацией о часовом поясе, чтобы восстановленное значение определяло то же время, что и сохраненное значение.

### <a name="to-round-trip-a-datetime-value"></a>Выполнение цикла обработки значения DateTime

1. Преобразуйте значение <xref:System.DateTime> в строковое представление с помощью метода <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> с описателем формата "o".

2. Сохраните строковое представление значения <xref:System.DateTime> в файл или передайте его между процессами, доменами приложений или компьютерами.

3. Получите строку, представляющую значение <xref:System.DateTime>.

4. Вызовите метод <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> и передайте ему значение <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> в параметре `styles`.

В следующем примере показано, как выполнить цикл обработки значения <xref:System.DateTime>.

[!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
[!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]

Этот метод позволяет сохранить любое значение локального или универсального времени в процессе обработки значения <xref:System.DateTime>. Например, если локальное значение <xref:System.DateTime> сохранено в системе в тихоокеанском стандартном часовом поясе США и восстановлено в системе в центральном стандартном часовом поясе США, восстановленные дата и время будут на два часа больше исходного времени, что отражает разницу во времени между двумя часовыми поясами. Однако этот способ не всегда точен для неуказанного времени. Все значения <xref:System.DateTime>, для которых свойство <xref:System.DateTime.Kind%2A> имеет значение <xref:System.DateTimeKind.Unspecified>, обрабатываются как значения местного времени. Если это не так, <xref:System.DateTime> не сможет правильно установить нужный момент времени. Чтобы устранить это ограничение, нужно тесно связать значение даты и времени с его часовым поясом для операций сохранения и восстановления.

### <a name="to-round-trip-a-datetimeoffset-value"></a>Выполнение цикла обработки значения DateTimeOffset

1. Преобразуйте значение <xref:System.DateTimeOffset> в строковое представление с помощью метода <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> с описателем формата "o".

2. Сохраните строковое представление значения <xref:System.DateTimeOffset> в файл или передайте его между процессами, доменами приложений или компьютерами.

3. Получите строку, представляющую значение <xref:System.DateTimeOffset>.

4. Вызовите метод <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> и передайте ему значение <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> в параметре `styles`.

В следующем примере показано, как выполнить цикл обработки значения <xref:System.DateTimeOffset>.

[!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
[!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]

Этот метод всегда однозначно идентифицирует единственный момент времени по значению <xref:System.DateTimeOffset>. Полученное значение можно преобразовать в формат UTC с помощью метода <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> или в значение времени в определенным часовом поясе с помощью метода <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> или <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>. Основное ограничение этого способа — арифметические действия с датами и временем, которые могут дать неточные результаты для значения <xref:System.DateTimeOffset>, представляющего время в определенном часовом поясе. Это происходит потому, что значение <xref:System.DateTimeOffset> при создании "открепляется" от сведений о часовом поясе. Таким образом, правила коррекции часового пояса не могут быть больше применены при выполнении вычислений с датами и временем. Можно обойти эту проблему, определив пользовательский тип, который содержит значение даты и времени с его соответствующим часовым поясом.

### <a name="to-round-trip-a-date-and-time-value-with-its-time-zone"></a>Цикл обработки значения даты и времени с часовым поясом

1. Определите класс или структуру с двумя полями. Первое поле содержит объект <xref:System.DateTime> или <xref:System.DateTimeOffset>, а второе — объект <xref:System.TimeZoneInfo>. Следующий пример демонстрирует простой вариант такого типа.

    [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
    [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]

2. Отметьте этот класс атрибутом <xref:System.SerializableAttribute>.

3. Сериализуйте объект с помощью метода <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>.

4. Восстановите объект с помощью метода <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A>.

5. Приведите или преобразуйте десериализованный объект (в C#) в объект нужного типа (в Visual Basic).

В следующем примере описан цикл обработки объекта, позволяющий сохранить сведения о дате, времени и часовом поясе.

[!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
[!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]

Этот метод всегда будет однозначно определять правильный момент времени как до, так и после сохранения и восстановления, если реализация комбинированного объекта для даты, времени и часового пояса не допускает рассинхронизацию значений даты и часового пояса.

## <a name="compiling-the-code"></a>Компиляция кода

Для этих примеров требуются:

- Импорт следующих пространств имен с помощью операторов C# `using` или операторов Visual Basic `Imports`:

  - <xref:System> (только для C#);

  - <xref:System.Globalization?displayProperty=nameWithType>.

  - <xref:System.IO?displayProperty=nameWithType>.

  - <xref:System.Runtime.Serialization?displayProperty=nameWithType>.

  - <xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.

- Все примеры кода, кроме класса `DateInTimeZone`, нужно включить в класс или модуль Visual Basic, упаковать в методы и вызывать из метода `Main`.

## <a name="see-also"></a>См. также

- [Выполнение операций форматирования](../../../docs/standard/base-types/performing-formatting-operations.md)
- [Выбор между типами DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).
- [Строки стандартных форматов даты и времени](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)
