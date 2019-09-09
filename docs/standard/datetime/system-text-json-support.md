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
ms.openlocfilehash: 5bff01b10b2bdea4fdcfee86e348c47f44d50103
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2019
ms.locfileid: "70374477"
---
# <a name="datetime-and-datetimeoffset-support-in-systemtextjson"></a>Поддержка DateTime и DateTimeOffset в System.Text.Json

Библиотека System. Text. JSON выполняет синтаксический анализ и <xref:System.DateTime> запись <xref:System.DateTimeOffset> и значения в соответствии с расширенным профилем ISO 8601:-2019.
[Преобразователи](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0) обеспечивают пользовательскую поддержку сериализации и десериализации с <xref:System.Text.Json.JsonSerializer>помощью.

## <a name="support-for-the-iso-8601-12019-format"></a>Поддержка формата ISO 8601-1:2019

<xref:System.Text.Json.JsonSerializer>Типы, <xref:System.Text.Json.Utf8JsonReader>, и<xref:System.Text.Json.Utf8JsonWriter> могутанализировать<xref:System.DateTime> и записывать и<xref:System.DateTimeOffset> текстовые представления в соответствии с расширенным профилем формата ISO 8601-1:2019, например 2019-07-26T16 <xref:System.Text.Json.JsonElement> : 59:57-05:00.

<xref:System.DateTime>данные <xref:System.DateTimeOffset> и могут быть сериализованы с <xref:System.Text.Json.JsonSerializer>помощью:

[!code-csharp[example-serializing-with-jsonserializer](~/samples/snippets/standard/datetime/json/serializing-with-jsonserializer.cs)]

Их также можно десериализовать с помощью <xref:System.Text.Json.JsonSerializer>:

[!code-csharp[example-deserializing-with-jsonserializer-valid](~/samples/snippets/standard/datetime/json/deserializing-with-jsonserializer-valid.cs)]

При использовании параметров по умолчанию <xref:System.DateTimeOffset> входные <xref:System.DateTime> и текстовые представления должны соответствовать расширенному профилю ISO 8601-1:2019.
Попытка десериализовать представления, которые не соответствуют профилю <xref:System.Text.Json.JsonSerializer> , приведет к <xref:System.Text.Json.JsonException>созданию исключения:

[!code-csharp[example-deserializing-with-jsonserializer-error](~/samples/snippets/standard/datetime/json/deserializing-with-jsonserializer-error.cs)]

Предоставляет структурированный доступ к содержимому полезных данных JSON, включая <xref:System.DateTime> представления и <xref:System.DateTimeOffset>. <xref:System.Text.Json.JsonDocument> В приведенном ниже примере показано, как при наличии коллекции температур можно вычислить среднюю температуру по понедельникам.

[!code-csharp[example-computing-with-jsondocument-valid](~/samples/snippets/standard/datetime/json/computing-with-jsondocument-valid.cs)]

Попытка вычисления средней температуры при наличии полезных данных с несоответствующими <xref:System.DateTime> представлениями <xref:System.Text.Json.JsonDocument> вызовет исключение <xref:System.FormatException>:

[!code-csharp[example-computing-with-jsondocument-error](~/samples/snippets/standard/datetime/json/computing-with-jsondocument-error.cs)]

Записи <xref:System.Text.Json.Utf8JsonWriter> <xref:System.DateTime> и данныенижнегоуровня:<xref:System.DateTimeOffset>

[!code-csharp[example-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/writing-with-utf8jsonwriter.cs)]

<xref:System.Text.Json.Utf8JsonReader>синтаксические анализы <xref:System.DateTimeOffset>иданные <xref:System.DateTime> :

[!code-csharp[example-reading-with-utf8jsonreader-valid](~/samples/snippets/standard/datetime/json/reading-with-utf8jsonreader-valid.cs)]

Попытка чтения несовместимых форматов с <xref:System.Text.Json.Utf8JsonReader> вызовет <xref:System.FormatException>исключение:

[!code-csharp[example-reading-with-utf8jsonreader-error](~/samples/snippets/standard/datetime/json/reading-with-utf8jsonreader-error.cs)]

## <a name="custom-support-for-xrefsystemdatetime-and-xrefsystemdatetimeoffset-in-xrefsystemtextjsonjsonserializer"></a>Пользовательская поддержка <xref:System.DateTime> для <xref:System.DateTimeOffset> и в<xref:System.Text.Json.JsonSerializer>

Если вы хотите, чтобы сериализатор выполнял пользовательское синтаксический анализ или форматирование, можно реализовать [пользовательские преобразователи](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0).
Вот несколько примеров.

### <a name="using-datetimeoffsetparse-and-datetimeoffsettostring"></a>Использование `DateTime(Offset).Parse` и`DateTime(Offset).ToString`

Если не удается определить форматы входных <xref:System.DateTime> или <xref:System.DateTimeOffset> текстовых представлений `DateTime(Offset).Parse` , можно использовать метод в логике чтения преобразователя. Это позволяет использовать. Обширная поддержка для анализа различных <xref:System.DateTime> форматов и <xref:System.DateTimeOffset> текста, в том числе строк, отличных от ISO 8601, и форматов ISO 8601, которые не соответствуют расширенному профилю ISO 8601-1:2019. Этот подход значительно меньше, чем использование собственной реализации сериализатора.

Для сериализации можно использовать `DateTime(Offset).ToString` метод в логике записи преобразователя. <xref:System.DateTime> Это позволяет писать значения <xref:System.DateTimeOffset> и использовать любые [стандартные форматы даты](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)и времени, а также [пользовательские форматы даты и времени](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).
Это также значительно менее производительно, чем использование собственной реализации сериализатора.

[!code-csharp[example-showing-datetime-parse](~/samples/snippets/standard/datetime/json/datetime-converter-examples/example1/Program.cs)]

> [!NOTE]
> При реализации <xref:System.Text.Json.Serialization.JsonConverter%601> `T` , `typeToConvert` и параметр всегда будет иметь`typeof(DateTime)`значение. <xref:System.DateTime>
Параметр полезен для обработки полиморфизмов и использования универсальных шаблонов для получения `typeof(T)` производительного способа.

### <a name="using-xrefsystembufferstextutf8parser-and-xrefsystembufferstextutf8formatter"></a>Использование <xref:System.Buffers.Text.Utf8Parser> и<xref:System.Buffers.Text.Utf8Formatter>

В логике преобразователя можно использовать быстрые методы синтаксического анализа и форматирования на основе UTF-8, если <xref:System.DateTime> входные <xref:System.DateTimeOffset> или текстовые представления совместимы с одной из строк "R", "l", "O" или "G" [стандартного формата даты и времени](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)или если вы хотите запись в соответствии с одним из этих форматов. Это гораздо быстрее, чем использование `DateTime(Offset).Parse` и `DateTime(Offset).ToString`.

В этом примере показан пользовательский преобразователь, который сериализует и десериализует <xref:System.DateTime> значения в соответствии со [стандартным форматом "R"](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-rfc1123-r-r-format-specifier):

[!code-csharp[example-showing-utf8-parser-and-formatter](~/samples/snippets/standard/datetime/json/datetime-converter-examples/example2/Program.cs)]

> [!NOTE]
> Стандартный формат "R" всегда будет иметь длину 29 символов.

### <a name="using-datetimeoffsetparse-as-a-fallback-to-the-serializers-native-parsing"></a>Использование `DateTime(Offset).Parse` в качестве резервного варианта для собственного анализа сериализатора

Если обычно вход <xref:System.DateTime> или <xref:System.DateTimeOffset> данные должны соответствовать расширенному профилю ISO 8601-1:2019, можно использовать собственную логику синтаксического анализа сериализатора. Также можно реализовать резервный механизм, как и в случае.
В этом примере показано, что после сбоя синтаксического анализа <xref:System.DateTime> текстового представления с <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>помощью преобразователь успешно проанализирует данные с помощью <xref:System.DateTime.Parse(System.String)>.

[!code-csharp[example-showing-datetime-parse-as-fallback](~/samples/snippets/standard/datetime/json/datetime-converter-examples/example3/Program.cs)]

## <a name="the-extended-iso-8601-12019-profile-in-systemtextjson"></a>Расширенный профиль ISO 8601-1:2019 в System. Text. JSON

### <a name="date-and-time-components"></a>Компоненты даты и времени

Расширенный профиль ISO 8601-1:2019, реализованный <xref:System.Text.Json> в, определяет следующие компоненты для представлений даты и времени. Эти компоненты используются для определения различных уровней детализации, поддерживаемых при анализе и форматировании <xref:System.DateTime> <xref:System.DateTimeOffset> и представлениях.

| Компонент       | Формат                      | Описание                                                                     |
|-----------------|-----------------------------|---------------------------------------------------------------------------------|
| Год            | "yyyy"                      | 0001-9999                                                                       |
| Месяц           | "MM"                        | 01-12                                                                           |
| День             | "dd"                        | 01-28, 01-29, 01-30, 01-31 в зависимости от месяца/года                                  |
| Час            | "HH"                        | 00-23                                                                           |
| Минута          | "mm"                        | 00-59                                                                           |
| Вторая          | "ss"                        | 00-59                                                                           |
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

Если в секундах есть десятичные дроби, должна быть хотя бы одна цифра; `2019-07-26T00:00:00.` не допускается.
Хотя допускается до 16 цифр дробной части, анализируются только первые семь. Все, что больше, считается нулем.
Например, будет `2019-07-26T00:00:00.1234567890` анализироваться так, как если бы он `2019-07-26T00:00:00.1234567`был.
Это позволяет обеспечить совместимость с <xref:System.DateTime> реализацией, которая ограничена этим разрешением.

Високосные секунды не поддерживаются.

### <a name="support-for-formatting"></a>Поддержка форматирования

Для форматирования определены следующие уровни гранулярности:

1. "' Полная дата ' 'T ' ' частичное время ' '
    1. "yyyy'-'MM'-'dd'T'HH": "mm": "SS" ([Описатель сортируемого формата ("s")](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))

        Используется для форматирования <xref:System.DateTime> без дробной части секунд и без сведений о смещении.

    2. "yyyy'-'MM'-'dd'T'HH ': ' mm ': ' SS '. ' FFFFFFF

        Используется для форматирования <xref:System.DateTime> с долей секунды, но без сведений о смещении.

2. "Дата и время"
    1. "yyyy'-'MM'-'dd'T'HH": "mm": "ссZ"

        Используется для форматирования <xref:System.DateTime> или <xref:System.DateTimeOffset> без доли секунды, но с смещением в формате UTC.

    2. "yyyy'-'MM'-'dd'T'HH ': ' mm ': ' SS '. ' ФФФФФФФЗ "

        Используется для форматирования <xref:System.DateTime> или <xref:System.DateTimeOffset> с долей секунды и со смещением в формате UTC.

    3. "yyyy'-'MM'-'dd'T'HH ': ' mm ': ' SS (' + '/'-') HH ': ' mm '

        Используется для форматирования <xref:System.DateTime> или <xref:System.DateTimeOffset> без доли секунды, но с локальным смещением.

    4. "yyyy'-'MM'-'dd'T'HH ': ' mm ': ' SS '. ' FFFFFFF (' + '/'-') HH ': ' mm '

        Используется для форматирования <xref:System.DateTime> или <xref:System.DateTimeOffset> с долей секунды и с локальным смещением.
