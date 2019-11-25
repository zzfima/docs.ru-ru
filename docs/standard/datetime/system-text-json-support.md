---
title: Поддержка DateTime и DateTimeOffset в System.Text.Json
description: Общие сведения о поддержке типов DateTime и DateTimeOffset в библиотеке System. Text. JSON.
ms.technology: dotnet-standard
author: layomia
ms.author: laakinri
ms.date: 07/22/2019
helpviewer_keywords:
- JSON, Serializer, Utf8
- JSON DateTime, JSON DateTimeOffset
- DateTime, DateTimeOffset
- JsonSerializer, Utf8JsonReader, Utf8JsonWriter, JsonElement, JsonDocument
- JSON Serializer, JSON Reader, JSON Writer
- Converter, JSON Converter, DateTime Converter
- ISO, ISO 8601, ISO 8601-1:2019
ms.openlocfilehash: 04e0e3c613b194ac85241d50d3bc5fd5dc0b6e54
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977329"
---
# <a name="datetime-and-datetimeoffset-support-in-systemtextjson"></a>Поддержка DateTime и DateTimeOffset в System.Text.Json

Библиотека System. Text. JSON анализирует и записывает значения <xref:System.DateTime> и <xref:System.DateTimeOffset> в соответствии с расширенным профилем ISO 8601:-2019.
[Преобразователи](xref:System.Text.Json.Serialization.JsonConverter%601) обеспечивают пользовательскую поддержку сериализации и десериализации с помощью <xref:System.Text.Json.JsonSerializer>.
Пользовательская поддержка также может быть реализована при использовании <xref:System.Text.Json.Utf8JsonReader> и <xref:System.Text.Json.Utf8JsonWriter>.

## <a name="support-for-the-iso-8601-12019-format"></a>Поддержка формата ISO 8601-1:2019

Типы <xref:System.Text.Json.JsonSerializer>, <xref:System.Text.Json.Utf8JsonReader>, <xref:System.Text.Json.Utf8JsonWriter>и <xref:System.Text.Json.JsonElement> позволяют анализировать и записывать <xref:System.DateTime> и <xref:System.DateTimeOffset> текстовые представления в соответствии с расширенным профилем формата ISO 8601-1:2019. Например, 2019-07-26T16:59:57-05:00.

<xref:System.DateTime> и <xref:System.DateTimeOffset> данные можно сериализовать с помощью <xref:System.Text.Json.JsonSerializer>:

[!code-csharp[example-serializing-with-jsonserializer](~/samples/snippets/standard/datetime/json/csharp/serializing-with-jsonserializer/Program.cs)]

Их также можно десериализовать с помощью <xref:System.Text.Json.JsonSerializer>:

[!code-csharp[example-deserializing-with-jsonserializer-valid](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-valid/Program.cs)]

При использовании параметров по умолчанию входные <xref:System.DateTime> и <xref:System.DateTimeOffset> текстовые представления должны соответствовать расширенному профилю ISO 8601-1:2019.
Попытка десериализовать представления, которые не соответствуют профилю, приведет к тому, что <xref:System.Text.Json.JsonSerializer> выдаст <xref:System.Text.Json.JsonException>:

[!code-csharp[example-deserializing-with-jsonserializer-error](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-error/Program.cs)]

<xref:System.Text.Json.JsonDocument> предоставляет структурированный доступ к содержимому полезных данных JSON, включая представления <xref:System.DateTime> и <xref:System.DateTimeOffset>. В приведенном ниже примере показано, как при наличии коллекции температур можно вычислить среднюю температуру по понедельникам.

[!code-csharp[example-computing-with-jsondocument-valid](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-valid/Program.cs)]

Попытка вычисления средней температуры при наличии полезных данных с несоответствующими <xref:System.DateTime> представлениями приведет к тому, что <xref:System.Text.Json.JsonDocument> выдаст <xref:System.FormatException>:

[!code-csharp[example-computing-with-jsondocument-error](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-error/Program.cs)]

Нижний уровень <xref:System.Text.Json.Utf8JsonWriter> записывает <xref:System.DateTime> и данные <xref:System.DateTimeOffset>:

[!code-csharp[example-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/writing-with-utf8jsonwriter/Program.cs)]

<xref:System.Text.Json.Utf8JsonReader> анализирует <xref:System.DateTime> и данные <xref:System.DateTimeOffset>:

[!code-csharp[example-reading-with-utf8jsonreader-valid](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-valid/Program.cs)]

Попытка чтения несовместимых форматов с <xref:System.Text.Json.Utf8JsonReader> приведет к выдаче <xref:System.FormatException>:

[!code-csharp[example-reading-with-utf8jsonreader-error](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-error/Program.cs)]

## <a name="custom-support-for-xrefsystemdatetime-and-xrefsystemdatetimeoffset"></a>Настраиваемая поддержка для <xref:System.DateTime> и <xref:System.DateTimeOffset>

### <a name="when-using-xrefsystemtextjsonjsonserializer"></a>При использовании <xref:System.Text.Json.JsonSerializer>

Если вы хотите, чтобы сериализатор выполнял пользовательское синтаксический анализ или форматирование, можно реализовать [пользовательские преобразователи](xref:System.Text.Json.Serialization.JsonConverter%601).
Вот несколько примеров:

#### <a name="using-datetimeoffsetparse-and-datetimeoffsettostring"></a>Использование `DateTime(Offset).Parse` и `DateTime(Offset).ToString`

Если не удается определить форматы входных <xref:System.DateTime> или <xref:System.DateTimeOffset> текстовых представлений, можно использовать метод `DateTime(Offset).Parse` в логике чтения преобразователя. Это позволяет использовать. Обширная поддержка анализа различных <xref:System.DateTime> и <xref:System.DateTimeOffset> текстовых форматов, включая строки, отличные от ISO 8601, и форматы ISO 8601, которые не соответствуют расширенному профилю ISO 8601-1:2019. Этот подход значительно меньше, чем использование собственной реализации сериализатора.

Для сериализации можно использовать метод `DateTime(Offset).ToString` в логике записи преобразователя. Это позволяет записывать <xref:System.DateTime> и <xref:System.DateTimeOffset> значения, используя любой из [стандартных форматов даты и времени](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings), а также [пользовательские форматы даты и времени](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).
Это также значительно менее производительно, чем использование собственной реализации сериализатора.

[!code-csharp[example-showing-datetime-parse](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example1/Program.cs)]

> [!NOTE]
> При реализации <xref:System.Text.Json.Serialization.JsonConverter%601>и `T` <xref:System.DateTime>параметр `typeToConvert` всегда будет `typeof(DateTime)`.
Параметр полезен для обработки полиморфизмов и при использовании универсальных шаблонов для получения `typeof(T)` в удобном виде.

#### <a name="using-xrefsystembufferstextutf8parser-and-xrefsystembufferstextutf8formatter"></a>Использование <xref:System.Buffers.Text.Utf8Parser> и <xref:System.Buffers.Text.Utf8Formatter>

В логике преобразователя можно использовать быстрые методы синтаксического анализа и форматирования на основе UTF-8, если входные <xref:System.DateTime> или <xref:System.DateTimeOffset> текстовые представления совместимы с одним из [строк стандартных форматов даты и времени](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)"R", "l", "O" или "G", или вы хотите писать в соответствии с одним из этих форматов. Это гораздо быстрее, чем использование `DateTime(Offset).Parse` и `DateTime(Offset).ToString`.

В этом примере показан пользовательский преобразователь, который сериализует и десериализует значения <xref:System.DateTime> в соответствии со [стандартным форматом "R"](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-rfc1123-r-r-format-specifier):

[!code-csharp[example-showing-utf8-parser-and-formatter](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example2/Program.cs)]

> [!NOTE]
> Стандартный формат "R" всегда будет иметь длину 29 символов.

#### <a name="using-datetimeoffsetparse-as-a-fallback-to-the-serializers-native-parsing"></a>Использование `DateTime(Offset).Parse` в качестве резервной стратегии для анализа машинного кода сериализатора

Если вы обычно предполагаете, что входные <xref:System.DateTime> или <xref:System.DateTimeOffset> данные соответствуют расширенному профилю ISO 8601-1:2019, можно использовать собственную логику синтаксического анализа сериализатора. Также можно реализовать резервный механизм, как и в случае.
В этом примере показано, что после сбоя синтаксического анализа <xref:System.DateTime> текстового представления с помощью <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>преобразователь успешно проанализирует данные с помощью <xref:System.DateTime.Parse(System.String)>.

[!code-csharp[example-showing-datetime-parse-as-fallback](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example3/Program.cs)]

### <a name="when-writing-with-xrefsystemtextjsonutf8jsonwriter"></a>При записи с помощью <xref:System.Text.Json.Utf8JsonWriter>

Если вы хотите написать пользовательское <xref:System.DateTime> или <xref:System.DateTimeOffset> текстовое представление с <xref:System.Text.Json.Utf8JsonWriter>, можно отформатировать пользовательское представление до <xref:System.String>, `ReadOnlySpan<Byte>`, `ReadOnlySpan<Char>`или <xref:System.Text.Json.JsonEncodedText>, а затем передать его в соответствующий метод [Utf8JsonWriter. вритестрингвалуе](https://docs.microsoft.com/dotnet/api/system.text.json.utf8jsonwriter.writestringvalue?view=netcore-3.0) или [Utf8JsonWriter. WriteString](https://docs.microsoft.com/dotnet/api/system.text.json.utf8jsonwriter.writestring?view=netcore-3.0) .

В следующем примере показано, как можно создать пользовательский формат <xref:System.DateTime> с помощью <xref:System.DateTime.ToString(System.String,System.IFormatProvider)>, а затем написать с помощью метода <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)>:

[!code-csharp[example-custom-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/custom-writing-with-utf8jsonwriter/Program.cs)]

### <a name="when-reading-with-xrefsystemtextjsonutf8jsonreader"></a>При чтении с помощью <xref:System.Text.Json.Utf8JsonReader>

Если вы хотите прочитать Пользовательское <xref:System.DateTime> или <xref:System.DateTimeOffset> текстовое представление с <xref:System.Text.Json.Utf8JsonReader>, можно получить значение текущего маркера JSON как <xref:System.String> с помощью <xref:System.Text.Json.Utf8JsonReader.GetString>, а затем проанализировать значение с помощью пользовательской логики.

В следующем примере показано, как можно получить пользовательское <xref:System.DateTimeOffset> текстовое представление с помощью <xref:System.Text.Json.Utf8JsonReader.GetString>, а затем выполнить синтаксический анализ с помощью <xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)>:

[!code-csharp[example-custom-reading-with-utf8jsonreader](~/samples/snippets/standard/datetime/json/csharp/custom-reading-with-utf8jsonreader/Program.cs)]

## <a name="the-extended-iso-8601-12019-profile-in-systemtextjson"></a>Расширенный профиль ISO 8601-1:2019 в System. Text. JSON

### <a name="date-and-time-components"></a>Компоненты даты и времени

Расширенный профиль ISO 8601-1:2019, реализованный в <xref:System.Text.Json>, определяет следующие компоненты для представлений даты и времени. Эти компоненты используются для определения различных уровней детализации, поддерживаемых при анализе и форматировании <xref:System.DateTime> и <xref:System.DateTimeOffset> представлений.

| Компонент       | Формат                      | Описание                                                                     |
|-----------------|-----------------------------|---------------------------------------------------------------------------------|
| Year            | "yyyy"                      | 0001-9999                                                                       |
| Месяц.           | "MM"                        | 01-12                                                                           |
| Day             | "dd"                        | 01-28, 01-29, 01-30, 01-31 в зависимости от месяца/года                                  |
| Hour            | "HH"                        | 00-23                                                                           |
| Minute          | "mm"                        | 00-59                                                                           |
| Second          | "ss"                        | 00-59                                                                           |
| Вторая дробь | "FFFFFFF"                   | Минимум одна цифра, максимум 16 цифр                                      |
| Смещение времени     | "K"                         | "Z" или "(' + '/'-') HH ': ' mm '                                                |
| Частичное время    | "HH": "mm": "SS [FFFFFFF]"     | Время без сведений о смещении UTC                                             |
| Полная дата       | "yyyy'-'MM'-'дд"            | Дата календаря                                                                   |
| Полное время       | "Partial Тиме'к"           | Время суток в формате UTC или местного времени дня с смещением времени между местным временем и временем в формате UTC |
| Дата и время       | "' Полная дата ' \ ' ' полное время ' ' | Календарная дата и время суток, например 2019-07-26T16:59:57-05:00                   |

### <a name="support-for-parsing"></a>Поддержка синтаксического анализа

Для синтаксического анализа определены следующие уровни детализации:

1. "Полная дата"
    1. "yyyy'-'MM'-'дд"

2. "' Полная дата ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' '
    1. "yyyy'-'MM'-'dd'T'HH": "mm"

3. "' Полная дата ' 'T ' ' частичное время ' '
    1. "yyyy'-'MM'-'dd'T'HH": "mm": "SS" ([Описатель сортируемого формата ("s")](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))
    2. "yyyy'-'MM'-'dd'T'HH ': ' mm ': ' SS '. ' FFFFFFF

4. "' Полная дата ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' '
    1. "yyyy'-'MM'-'dd'T'HH": "ММЗ"
    2. "yyyy'-'MM'-'dd'T'HH": "mm (' + '/'-') HH ': ' mm"

5. "Дата и время"
    1. "yyyy'-'MM'-'dd'T'HH": "mm": "ссZ"
    2. "yyyy'-'MM'-'dd'T'HH ': ' mm ': ' SS '. ' ФФФФФФФЗ "
    3. "yyyy'-'MM'-'dd'T'HH ': ' mm ': ' SS (' + '/'-') HH ': ' mm '
    4. "yyyy'-'MM'-'dd'T'HH ': ' mm ': ' SS '. ' FFFFFFF (' + '/'-') HH ': ' mm '

Если в секундах есть десятичные дроби, должна быть хотя бы одна цифра; `2019-07-26T00:00:00.` не разрешено.
Хотя допускается до 16 цифр дробной части, анализируются только первые семь. Все, что больше, считается нулем.
Например, `2019-07-26T00:00:00.1234567890` будет анализироваться так, как если бы он `2019-07-26T00:00:00.1234567`.
Это необходимо для совместимости с реализацией <xref:System.DateTime>, которая ограничена этим разрешением.

Високосные секунды не поддерживаются.

### <a name="support-for-formatting"></a>Поддержка форматирования

Для форматирования определены следующие уровни гранулярности:

1. "' Полная дата ' 'T ' ' частичное время ' '
    1. "yyyy'-'MM'-'dd'T'HH": "mm": "SS" ([Описатель сортируемого формата ("s")](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))

        Используется для форматирования <xref:System.DateTime> без дробных секунд и без сведений о смещении.

    2. "yyyy'-'MM'-'dd'T'HH ': ' mm ': ' SS '. ' FFFFFFF

        Используется для форматирования <xref:System.DateTime> с долей секунд, но без сведений о смещении.

2. "Дата и время"
    1. "yyyy'-'MM'-'dd'T'HH": "mm": "ссZ"

        Используется для форматирования <xref:System.DateTime> без доли секунды, но с смещением в формате UTC.

    2. "yyyy'-'MM'-'dd'T'HH ': ' mm ': ' SS '. ' ФФФФФФФЗ "

        Используется для форматирования <xref:System.DateTime> с долей секунды и со смещением в формате UTC.

    3. "yyyy'-'MM'-'dd'T'HH ': ' mm ': ' SS (' + '/'-') HH ': ' mm '

        Используется для форматирования <xref:System.DateTime> или <xref:System.DateTimeOffset> без доли секунды, но с локальным смещением.

    4. "yyyy'-'MM'-'dd'T'HH ': ' mm ': ' SS '. ' FFFFFFF (' + '/'-') HH ': ' mm '

        Используется для форматирования <xref:System.DateTime> или <xref:System.DateTimeOffset> с долей секунд и с локальным смещением.

Если оно имеется, записывается не более 7 цифр дробной части. Это соответствует реализации <xref:System.DateTime>, которая ограничена этим разрешением.
