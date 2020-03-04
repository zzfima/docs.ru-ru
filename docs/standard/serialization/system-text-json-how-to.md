---
title: Как сериализовать и десериализовать JSON с C# помощью-.NET
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 8025f84f2425f5b91e08b28ddb24d105d8c4d1a3
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159589"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a>Сериализация и десериализация (маршалирование и распаковки) JSON в .NET

В этой статье показано, как использовать пространство имен <xref:System.Text.Json> для сериализации и десериализации в нотация объектов JavaScript (JSON) и обратно.

В направлениях и образце кода библиотека используется напрямую, а не с помощью платформы, такой как [ASP.NET Core](/aspnet/core/).

Большинство примеров кода сериализации задают <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType>, чтобы `true`ся для «удобного» печати JSON (с отступами и пробелами для удобочитаемости). Для использования в рабочей среде для этого параметра обычно принимается значение по умолчанию `false`.

## <a name="namespaces"></a>Пространства имен

Пространство имен <xref:System.Text.Json> содержит все точки входа и основные типы. Пространство имен <xref:System.Text.Json.Serialization> содержит атрибуты и интерфейсы API для сложных сценариев и настройки, характерные для сериализации и десериализации. В примерах кода, приведенных в этой статье, требуются директивы `using` для одного или обоих пространств имен:

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

Атрибуты из пространства имен <xref:System.Runtime.Serialization> в настоящее время не поддерживаются в `System.Text.Json`.

## <a name="how-to-write-net-objects-to-json-serialize"></a>Как записывать объекты .NET в JSON (сериализовать)

Чтобы записать JSON в строку или в файл, вызовите метод <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.

В следующем примере показано создание JSON в виде строки:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerialize)]

В следующем примере синхронный код используется для создания JSON-файла:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

В следующем примере асинхронный код используется для создания JSON-файла:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

В предыдущих примерах для сериализуемого типа используется определение типа. Перегрузка `Serialize()` принимает параметр универсального типа:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a>Пример сериализации

Ниже приведен пример класса, который содержит коллекции и вложенный класс:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

Выходные данные JSON из сериализации экземпляра предыдущего типа выглядят так, как показано в следующем примере. Выходные данные JSON по умолчанию минифицированные:

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

В следующем примере показан один и тот же формат JSON, форматированный (т. е. который печатается с пробелами и отступами):

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": 20,
      "Low": -10
    },
    "Hot": {
      "High": 60,
      "Low": 20
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

### <a name="serialize-to-utf-8"></a>Сериализация в UTF-8

Чтобы выполнить сериализацию в UTF-8, вызовите метод <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

Также доступна перегрузка <xref:System.Text.Json.JsonSerializer.Serialize%2A>, которая принимает <xref:System.Text.Json.Utf8JsonWriter>.

Сериализация в UTF-8 происходит примерно на 5-10% быстрее, чем при использовании строковых методов. Разница заключается в том, что байты (как UTF-8) не нужно преобразовывать в строки (UTF-16).

## <a name="serialization-behavior"></a>Поведение сериализации

* По умолчанию все открытые свойства сериализуются. Можно [указать свойства для исключения](#exclude-properties-from-serialization).
* [Кодировщик по умолчанию](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) выводит символы, не входящие в набор ASCII, символы, УЧИТЫВАЮЩИЕ формат ASCII, и символы, которые должны быть экранированы в соответствии со [спецификацией RFC 8259 JSON](https://tools.ietf.org/html/rfc8259#section-7).
* По умолчанию JSON — минифицированные. JSON можно [довольно просто распечатать](#serialize-to-formatted-json).
* По умолчанию регистр имен JSON соответствует именам .NET. Можно [настроить регистр имен JSON](#customize-json-names-and-values).
* Обнаружены циклические ссылки и создаются исключения.
* В настоящее время поля исключаются.

Поддерживаемые типы:

* Примитивы .NET, которые сопоставляются с примитивами JavaScript, например числовыми типами, строками и логическими значениями.
* Определяемые пользователем [простые старые объекты CLR (POCO)](https://stackoverflow.com/questions/250001/poco-definition).
* Одномерное и зубчатые массивы (`ArrayName[][]`).
* `Dictionary<string,TValue>`, где `TValue` — `object`, `JsonElement`или POCO.
* Коллекции из следующих пространств имен.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

Можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md) для обработки дополнительных типов или для предоставления функциональных возможностей, которые не поддерживаются встроенными преобразователями.

## <a name="how-to-read-json-into-net-objects-deserialize"></a>Чтение JSON в объектах .NET (десериализация)

Чтобы выполнить десериализацию из строки или файла, вызовите метод <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.

В следующем примере показано чтение JSON из строки и создание экземпляра класса `WeatherForecast`, показанного ранее для [примера сериализации](#serialization-example):

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

Чтобы выполнить десериализацию из файла с помощью синхронного кода, считайте файл в строку, как показано в следующем примере:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

Чтобы выполнить десериализацию из файла с помощью асинхронного кода, вызовите метод <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a>Десериализация из UTF-8

Для десериализации из UTF-8 вызовите перегрузку <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>, которая принимает `Utf8JsonReader` или `ReadOnlySpan<byte>`, как показано в следующих примерах. В примерах предполагается, что JSON находится в массиве байтов с именем jsonUtf8Bytes.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a>Поведение десериализации

* По умолчанию при сопоставлении имен свойств учитывается регистр. Можно [указать нечувствительность к регистру](#case-insensitive-property-matching).
* Если JSON содержит значение для свойства, доступного только для чтения, значение игнорируется и исключение не создается.
* Десериализация в ссылочные типы без конструктора, не имеющего параметров, не поддерживается.
* Десериализация в неизменяемые объекты или свойства только для чтения не поддерживается.
* По умолчанию перечисления поддерживаются в виде чисел. [Имена перечислений можно сериализовать как строки](#enums-as-strings).
* Поля не поддерживаются.
* По умолчанию комментарии или замыкающие запятые в JSON вызывают исключения. Можно [Разрешить комментарии и завершающие запятые](#allow-comments-and-trailing-commas).
* [Максимальная глубина по умолчанию](xref:System.Text.Json.JsonReaderOptions.MaxDepth) — 64.

Вы можете [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md) для предоставления функциональных возможностей, которые не поддерживаются встроенными преобразователями.

## <a name="serialize-to-formatted-json"></a>Сериализовать в форматированный JSON

Чтобы довольно просто распечатать выходные данные JSON, задайте для <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> значение `true`.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

Ниже приведен пример типа для сериализации и печати выходных данных JSON:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a>Настройка имен и значений JSON

По умолчанию имена и ключи словарей не изменяются в выходных данных JSON, включая регистр. Значения перечисления представлены в виде чисел. В этом разделе объясняется, как выполнить такие задачи:

* [Настройка отдельных имен свойств](#customize-individual-property-names)
* [Преобразовать все имена свойств в неоднородный регистр](#use-camel-case-for-all-json-property-names)
* [Реализация политики именования пользовательских свойств](#use-a-custom-json-property-naming-policy)
* [Преобразовать ключи словаря в стиль Camel](#camel-case-dictionary-keys)
* [Преобразование перечислений в строки и Camel](#enums-as-strings)

Для других сценариев, требующих специальной обработки имен и значений свойств JSON, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).

### <a name="customize-individual-property-names"></a>Настройка отдельных имен свойств

Чтобы задать имя отдельных свойств, используйте атрибут [[жсонпропертинаме]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) .

Ниже приведен пример типа для сериализации и результирующего JSON:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

Имя свойства, заданное этим атрибутом:

* Применяется в обоих направлениях для сериализации и десериализации.
* Имеет приоритет над политиками именования свойств.

### <a name="use-camel-case-for-all-json-property-names"></a>Использовать прописные буквы для всех имен свойств JSON

Чтобы использовать прописные буквы для всех имен свойств JSON, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

Ниже приведен пример класса для сериализации и вывода JSON.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

Политика именования свойств case:

* Применяется к сериализации и десериализации.
* Переопределяется атрибутами `[JsonPropertyName]`. Именно поэтому имя свойства JSON, `Wind` в примере, не является ни прописным.

### <a name="use-a-custom-json-property-naming-policy"></a>Использование настраиваемой политики именования свойств JSON

Чтобы использовать пользовательскую политику именования свойств JSON, создайте класс, производный от <xref:System.Text.Json.JsonNamingPolicy>, и переопределите метод <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, как показано в следующем примере:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/UpperCaseNamingPolicy.cs)]

Затем задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> экземпляр класса политики именования:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

Ниже приведен пример класса для сериализации и вывода JSON.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

Политика именования свойств JSON:

* Применяется к сериализации и десериализации.
* Переопределяется атрибутами `[JsonPropertyName]`. Именно поэтому имя свойства JSON `Wind` в примере — не верхний регистр.

### <a name="camel-case-dictionary-keys"></a>Ключи словаря символов в стиле Camel

Если свойство сериализуемого объекта имеет тип `Dictionary<string,TValue>`, `string` ключи можно преобразовать в стиль Camel. Для этого задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

Сериализация объекта с помощью словаря с именем `TemperatureRanges`, имеющего пары "ключ-значение" `"ColdMinTemp", 20` и `"HotMinTemp", 40` привести к выходным данным JSON, как в следующем примере:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

Политика именования Camel для ключей словаря применяется только к сериализации. При десериализации словаря ключи будут соответствовать JSON-файлу, даже если для `DictionaryKeyPolicy`указан параметр `JsonNamingPolicy.CamelCase`.

### <a name="enums-as-strings"></a>Перечисление как строки

По умолчанию перечисления сериализуются как числа. Чтобы сериализовать имена перечислений как строки, используйте <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.

Например, предположим, что необходимо сериализовать следующий класс, имеющий перечисление:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

Если сводка имеет `Hot`, по умолчанию сериализованный JSON имеет числовое значение 3:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

Следующий пример кода сериализует имена перечислений вместо числовых значений и преобразует имена в Camel:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

Итоговый код JSON выглядит следующим образом:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

Имена строк перечисления можно также десериализовать, как показано в следующем примере:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a>Исключить свойства из сериализации

По умолчанию все открытые свойства сериализуются. Если вы не хотите, чтобы некоторые из них отображались в выходных данных JSON, у вас есть несколько вариантов. В этом разделе объясняется, как исключить:

* [Отдельные свойства](#exclude-individual-properties)
* [Все свойства только для чтения](#exclude-all-read-only-properties)
* [Все свойства значений NULL](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a>Исключить отдельные свойства

Чтобы игнорировать отдельные свойства, используйте атрибут [[жсонигноре]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) .

Ниже приведен пример типа для сериализации и вывода JSON.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a>Исключить все свойства только для чтения

Свойство доступно только для чтения, если оно содержит открытый метод получения, но не является открытым методом задания. Чтобы исключить все свойства только для чтения, задайте для <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> значение `true`, как показано в следующем примере:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

Ниже приведен пример типа для сериализации и вывода JSON.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

Этот параметр применяется только к сериализации. Во время десериализации свойства, доступные только для чтения, по умолчанию игнорируются.

### <a name="exclude-all-null-value-properties"></a>Исключить все свойства значений NULL

Чтобы исключить все свойства значений NULL, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> значение `true`, как показано в следующем примере:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

Ниже приведен пример объекта для сериализации и вывода JSON.

|Свойство |Значение  |
|---------|---------|
| Дата    | 8/1/2019 12:00:00 AM-07:00|
| температурецелсиус| 25 |
| Сводка| null|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

Этот параметр применяется к сериализации и десериализации. Сведения о том, как это влияет на десериализацию, см. в разделе [игнорирование значения NULL при десериализации](#ignore-null-when-deserializing).

## <a name="customize-character-encoding"></a>Настройка кодировки символов

По умолчанию сериализатор выполняет escape-последовательность символов, отличных от ASCII.  То есть он заменяет их `\uxxxx`, где `xxxx` является кодом Юникода символа.  Например, если для свойства `Summary` задано значение кириллицы жарко, `WeatherForecast` объект сериализуется, как показано в следующем примере:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a>Сериализация наборов символов языка

Чтобы сериализовать наборы символов одного или нескольких языков без экранирования, укажите [Диапазоны Юникода](xref:System.Text.Unicode.UnicodeRanges) при создании экземпляра <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, как показано в следующем примере:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

Этот код не поддерживает символы кириллицы или греческого языка. Если свойство `Summary` имеет значение кириллицы жарко, то `WeatherForecast` объект сериализуется, как показано в следующем примере:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

Чтобы сериализовать все языковые наборы без экранирования, используйте <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.

### <a name="serialize-specific-characters"></a>Сериализация конкретных символов

Альтернативой является указание отдельных символов, которые нужно разрешить, без экранирования. В следующем примере сериализуются только первые два символа жарко:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

Ниже приведен пример JSON, созданный с помощью приведенного выше кода.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a>Сериализовать все символы

Чтобы избежать экранирования, можно использовать <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, как показано в следующем примере:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> По сравнению с кодировщиком по умолчанию `UnsafeRelaxedJsonEscaping` кодировщик является более строгим, что позволяет передавать символы без экранирования:
>
> * Он не выполняет escape-символы с учетом HTML, например `<`, `>`, `&`и `'`.
> * Она не предоставляет никаких дополнительных средств защиты от атак с помощью XSS или раскрытия информации, например, которые могут возникать из-за того, что клиент и сервер не согласны с набором *символов*.
>
> Используйте ненадежный кодировщик, только если известно, что клиент будет интерпретировать полученные полезные данные как JSON в кодировке UTF-8. Например, его можно использовать, если сервер отправляет заголовок ответа `Content-Type: application/json; charset=utf-8`. Никогда не разрешайте вывод необработанных `UnsafeRelaxedJsonEscaping` в HTML-страницу или элемент `<script>`.

## <a name="serialize-properties-of-derived-classes"></a>Сериализация свойств производных классов

Сериализация иерархии полиморфизма типа не поддерживается. Например, если свойство определено как интерфейс или абстрактный класс, сериализуются только свойства, определенные в интерфейсе или абстрактном классе, даже если тип среды выполнения имеет дополнительные свойства. Исключения из этого поведения описаны в этом разделе.

Например, предположим, что у вас есть класс `WeatherForecast` и производный класс `WeatherForecastDerived`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

И предположим, что аргумент типа метода `Serialize` во время компиляции `WeatherForecast`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

В этом сценарии свойство `WindSpeed` не сериализуется, даже если объект `weatherForecast` фактически является `WeatherForecastDerived`ным объектом. Сериализуются только свойства базового класса:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

Это поведение предназначено для предотвращения случайного раскрытия данных в производном от среды CLR типе.

Чтобы сериализовать свойства производного типа в предыдущем примере, используйте один из следующих подходов:

* Вызовите перегрузку <xref:System.Text.Json.JsonSerializer.Serialize%2A>, которая позволяет указать тип во время выполнения:

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* Объявите объект, который должен быть сериализован как `object`.

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

В предыдущем примере сценария оба подхода приводят к тому, что `WindSpeed` свойство включается в выходные данные JSON:

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> Эти подходы обеспечивают одноэлементную сериализацию только для сериализации корневого объекта, а не для свойств этого корневого объекта.

Можно получить полиморфизм сериализации для объектов более низкого уровня, если они определены как тип `object`. Например, предположим, что у класса `WeatherForecast` есть свойство с именем `PreviousForecast`, которое может быть определено как тип `WeatherForecast` или `object`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

Если свойство `PreviousForecast` содержит экземпляр `WeatherForecastDerived`:

* Выходные данные JSON из сериализации `WeatherForecastWithPrevious` **не включают** `WindSpeed`.
* Выходные данные JSON из сериализации `WeatherForecastWithPreviousAsObject` **включают** `WindSpeed`.

Для сериализации `WeatherForecastWithPreviousAsObject`не нужно вызывать метод `Serialize<object>` или `GetType`, так как корневой объект не является производным от него. В следующем примере кода не вызывается `Serialize<object>` или `GetType`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

Приведенный выше код правильно сериализует `WeatherForecastWithPreviousAsObject`:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "PreviousForecast": {
    "WindSpeed": 35,
    "Date": "2019-08-01T00:00:00-07:00",
    "TemperatureCelsius": 25,
    "Summary": "Hot"
  }
}
```

Тот же подход к определению свойств `object` работает с интерфейсами. Предположим, что у вас есть следующий интерфейс и реализация, и вы хотите сериализовать класс со свойствами, которые содержат экземпляры реализации:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/IForecast.cs)]

При сериализации экземпляра `Forecasts`только `Tuesday` отображает свойство `WindSpeed`, так как `Tuesday` определяется как `object`.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

В следующем примере показан код JSON, полученный в результате предыдущего кода:

```json
{
  "Monday": {
    "Date": "2020-01-06T00:00:00-08:00",
    "TemperatureCelsius": 10,
    "Summary": "Cool"
  },
  "Tuesday": {
    "Date": "2020-01-07T00:00:00-08:00",
    "TemperatureCelsius": 11,
    "Summary": "Rainy",
    "WindSpeed": 10
  }
}
```

Дополнительные сведения о полиморфизме **сериализации**и сведения о **десериализации**см. в разделе [Миграция из Newtonsoft. JSON в System. Text. JSON](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).

## <a name="allow-comments-and-trailing-commas"></a>Разрешить комментарии и завершающие запятые

По умолчанию в JSON не допускаются комментарии и конечные запятые. Чтобы разрешить комментарии в JSON, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> значение `JsonCommentHandling.Skip`.
Чтобы разрешить замыкающие запятые, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> значение `true`. В следующем примере показано, как разрешить оба:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

Вот пример JSON с комментариями и завершающей запятой:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a>Сопоставление свойств без учета регистра

По умолчанию десериализация выполняет поиск совпадения имен свойств с учетом регистра между JSON и свойствами целевого объекта. Чтобы изменить это поведение, задайте для <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> значение `true`.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

Ниже приведен пример JSON с именами свойств «Case Camel». Его можно десериализовать в следующий тип, который содержит имена свойств case в стиле Pascal.

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a>Маркер переполнения токена JSON

При десериализации в JSON могут быть получены данные, которые не представлены свойствами целевого типа. Например, предположим, что целевой тип:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

И JSON для десериализации:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

При десериализации JSON, показанного в указанном типе, свойства `DatesAvailable` и `SummaryWords` не будут переходятся и теряются. Чтобы записать дополнительные данные, такие как эти свойства, примените атрибут [жсонекстенсиондата](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) к свойству типа `Dictionary<string,object>` или `Dictionary<string,JsonElement>`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

При десериализации JSON, показанного ранее, в этот тип данных дополнительные данные становятся парами "ключ-значение" свойства `ExtensionData`:

|Свойство |Значение  |Примечания  |
|---------|---------|---------|
| Дата    | 8/1/2019 12:00:00 AM-07:00||
| температурецелсиус| 0 | Несовпадение с учетом регистра (`temperatureCelsius` в JSON), поэтому свойство не задано. |
| Сводка | Горячий ||
| ExtensionData | Температурецелсиус: 25 |Так как регистр не соответствует, это свойство JSON является дополнительным и становится парой "ключ-значение" в словаре.|
|| Датесаваилабле:<br>  8/1/2019 12:00:00 AM-07:00<br>8/2/2019 12:00:00 AM-07:00 |Дополнительное свойство из JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.|
| |Суммаривордс:<br>Холодный<br>Ветрено<br>хумид |Дополнительное свойство из JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.|

При сериализации целевого объекта пары "ключ-значение" данных расширения становятся свойствами JSON так же, как и во входящем JSON:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 0,
  "Summary": "Hot",
  "temperatureCelsius": 25,
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

Обратите внимание, что имя свойства `ExtensionData` не отображается в JSON. Такое поведение позволяет JSON выполнить цикл обработки без потери дополнительных данных, которые в противном случае не будут десериализованы.

## <a name="ignore-null-when-deserializing"></a>Игнорировать null при десериализации

По умолчанию, если свойство в JSON имеет значение null, соответствующему свойству в целевом объекте присваивается значение null. В некоторых сценариях свойство Target может иметь значение по умолчанию, и вы не хотите, чтобы значение NULL переопределяло по умолчанию.

Например, предположим, что целевой объект представляет следующий код:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

Предположим, что десериализуется следующий JSON:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

После десериализации свойство `Summary` объекта `WeatherForecastWithDefault` имеет значение null.

Чтобы изменить это поведение, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> значение `true`, как показано в следующем примере:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

При использовании этого параметра свойство `Summary` объекта `WeatherForecastWithDefault` является значением по умолчанию "нет сводки" после десериализации.

Значения NULL в JSON пропускаются только в том случае, если они являются допустимыми. Значения NULL для типов значений, не допускающих значения NULL, вызывают исключения.

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a>Utf8JsonReader, Utf8JsonWriter и Жсондокумент

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> — это высокопроизводительное, медленное средство чтения, доступное только для прямого просмотра для текста JSON в кодировке UTF-8, чтение из `ReadOnlySpan<byte>` или `ReadOnlySequence<byte>`. `Utf8JsonReader` — это тип низкого уровня, который можно использовать для создания пользовательских средств синтаксического анализа и десериализаторов. Метод <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> использует `Utf8JsonReader`, как описано выше.

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> — это высокопроизводительный способ записи текста JSON в кодировке UTF-8 из распространенных типов .NET, таких как `String`, `Int32`и `DateTime`. Модуль записи — это тип низкого уровня, который можно использовать для создания пользовательских сериализаторов. Метод <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> использует `Utf8JsonWriter`, как описано выше.

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> предоставляет возможность создания модель DOM (DOM) только для чтения с помощью `Utf8JsonReader`. Модель DOM предоставляет произвольный доступ к данным в полезных данных JSON. Доступ к элементам JSON, составляющим полезные данные, можно получить с помощью типа <xref:System.Text.Json.JsonElement>. Тип `JsonElement` предоставляет перечислители массивов и объектов вместе с интерфейсами API для преобразования текста JSON в общие типы .NET. `JsonDocument` предоставляет свойство <xref:System.Text.Json.JsonDocument.RootElement>.

В следующих разделах показано, как использовать эти средства для чтения и записи данных JSON.

## <a name="use-jsondocument-for-access-to-data"></a>Использование Жсондокумент для доступа к данным

В следующем примере показано, как использовать класс <xref:System.Text.Json.JsonDocument> для произвольного доступа к данным в строке JSON:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

Предыдущий код:

* Предполагается, что анализируемый JSON находится в строке с именем `jsonString`.
* Вычисляет среднее значение для объектов в массиве `Students`, имеющих свойство `Grade`.
* Назначает значение по умолчанию 70 для учащихся, у которых нет категории.
* Подсчитывает число учащихся путем увеличения `count` переменной с каждой итерацией. Альтернативой является вызов <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, как показано в следующем примере:

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

Ниже приведен пример JSON, обрабатываемого этим кодом:

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a>Использование Жсондокумент для записи JSON

В следующем примере показано, как записать JSON из <xref:System.Text.Json.JsonDocument>.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

Предыдущий код:

* Считывает JSON-файл, загружает данные в `JsonDocument`и записывает форматированный (довольно печатный) JSON в файл.
* Использует <xref:System.Text.Json.JsonDocumentOptions>, чтобы указать, что комментарии во входном JSON разрешены, но игнорируются.
* По завершении вызывается <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> для модуля записи. В качестве альтернативы можно разрешить Автоочистку модуля записи при его удалении.

Ниже приведен пример входных данных JSON для обработки в примере кода:

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Grades.json)]

В результате получается следующий качественный вывод JSON:

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a>Использование Utf8JsonWriter

В следующем примере показано, как использовать класс <xref:System.Text.Json.Utf8JsonWriter>:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a>Использование Utf8JsonReader

В следующем примере показано, как использовать класс <xref:System.Text.Json.Utf8JsonReader>:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

В приведенном выше коде предполагается, что `jsonUtf8` переменной является массив байтов, который содержит допустимый формат JSON, закодированный как UTF-8.

### <a name="filter-data-using-utf8jsonreader"></a>Фильтрация данных с помощью Utf8JsonReader

В следующем примере показано, как синхронно прочитать файл и выполнить поиск значения:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromFile.cs)]

Предыдущий код:

* Предполагается, что JSON содержит массив объектов, и каждый объект может содержать свойство "Name" типа String.
* Подсчитывает объекты и значения свойств Name, заканчивающиеся на университет.
* Предполагается, что файл кодируется как UTF-16 и перекодируется в UTF-8. Файл, закодированный как UTF-8, можно прочитать непосредственно в `ReadOnlySpan<byte>`с помощью следующего кода:

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  Если файл содержит метку порядка байтов (BOM) UTF-8, удалите ее перед передачей байтов в `Utf8JsonReader`, так как средство чтения ждет текст. В противном случае спецификация считается недопустимым JSON, а средство чтения создает исключение.

Ниже приведен пример JSON, который можно считать с помощью приведенного выше кода. Полученное итоговое сообщение "2 из 4 имеют имена, заканчивающиеся на" Университет ":

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Universities.json)]

## <a name="additional-resources"></a>Дополнительные ресурсы

* [Обзор System.Text.Json](system-text-json-overview.md)
* [Написание пользовательских преобразователей](system-text-json-converters-how-to.md)
* [Переход с Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Поддержка DateTime и DateTimeOffset в System.Text.Json](../datetime/system-text-json-support.md)
* [Справочник по System.Text.Json API](xref:System.Text.Json)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
