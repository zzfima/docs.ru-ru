---
title: Написание пользовательских преобразователей для сериализации JSON — .NET
author: tdykstra
ms.author: tdykstra
ms.date: 10/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: 361818a0bda8863f8878b86e5fb377dc0faf5246
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73741906"
---
# <a name="how-to-write-custom-converters-for-json-serialization-in-net"></a>Написание пользовательских преобразователей для сериализации JSON в .NET

В этой статье показано, как создать пользовательские преобразователи для классов сериализации JSON, предоставляемых в пространстве имен <xref:System.Text.Json>. Общие сведения о `System.Text.Json`см. [в статье сериализация и десериализация JSON в .NET](system-text-json-how-to.md).

*Преобразователь* — это класс, который преобразует объект или значение в JSON и обратно. Пространство имен `System.Text.Json` содержит встроенные преобразователи для большинства типов-примитивов, которые сопоставляются с примитивами JavaScript. Вы можете создавать пользовательские преобразователи:

* Переопределение поведения по умолчанию встроенного преобразователя. Например, может потребоваться, чтобы `DateTime` значения были представлены в формате мм/дд/гггг вместо формата ISO 8601-1:2019 по умолчанию.
* Для поддержки пользовательского типа значения. Например, структура `PhoneNumber`.

Можно также написать пользовательские преобразователи для расширения `System.Text.Json` с функциональностью, не входящей в текущий выпуск. Далее в этой статье рассматриваются следующие сценарии.

* [Десериализация выводимых типов в свойства объекта](#deserialize-inferred-types-to-object-properties).
* [Словарь поддержки с ключом, не являющимся строкой](#support-dictionary-with-non-string-key).
* [Поддержка полиморфизма](#support-polymorphic-deserialization).

## <a name="custom-converter-patterns"></a>Пользовательские шаблоны преобразователя

Существует два шаблона создания пользовательского преобразователя: базовый шаблон и шаблон фабрики. Шаблон фабрики предназначен для преобразователей, обрабатывающих `Enum` типов или открытых универсальных шаблонов. Базовый шаблон предназначен для неуниверсальных и закрытых универсальных типов.  Например, для преобразователей следующих типов требуется шаблон фабрики:

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

Ниже приведены некоторые примеры типов, которые могут быть обработаны базовым шаблоном.

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

Базовый шаблон создает класс, который может работать с одним типом. Шаблон фабрики создает класс, который определяет в среде выполнения, какой необходим конкретный тип, и динамически создает соответствующий преобразователь.

## <a name="sample-basic-converter"></a>Образец базового преобразователя

Следующий пример представляет собой преобразователь, который переопределяет сериализацию по умолчанию для существующего типа данных. Для `DateTimeOffset` свойств преобразователь использует формат мм/дд/гггг.

```csharp
private class ExampleDateTimeOffsetConverter : JsonConverter<DateTimeOffset>
{
    public override DateTimeOffset Read(
        ref Utf8JsonReader reader, 
        Type typeToConvert, 
        JsonSerializerOptions options)
    {
        return DateTimeOffset.ParseExact(reader.GetString(), 
            "MM/dd/yyyy", CultureInfo.InvariantCulture);
    }

    public override void Write(
        Utf8JsonWriter writer, 
        DateTimeOffset value, 
        JsonSerializerOptions options)
    {
        writer.WriteStringValue(value.ToString(
            "MM/dd/yyyy", CultureInfo.InvariantCulture));
    }
}
```

## <a name="sample-factory-pattern-converter"></a>Образец преобразователя шаблона фабрики

В следующем коде показан пользовательский преобразователь, работающий с `Dictionary<Enum,TValue>`. Код соответствует шаблону фабрики, так как первый параметр универсального типа является `Enum`, а второй — открытым. Метод `CanConvert` возвращает `true` только для `Dictionary` с двумя универсальными параметрами, первый из которых является типом `Enum`. Внутренний преобразователь получает существующий преобразователь для работы с любым типом, предоставленным во время выполнения для `TValue`. 

```csharp
using System;
using System.Collections.Generic;
using System.Reflection;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class ConverterDictionaryTKeyEnumTValue : JsonConverterFactory
    {
        public override bool CanConvert(Type typeToConvert)
        {
            if (!typeToConvert.IsGenericType)
            {
                return false;
            }

            if (typeToConvert.GetGenericTypeDefinition() != typeof(Dictionary<,>))
            {
                return false;
            }

            return typeToConvert.GetGenericArguments()[0].IsEnum;
        }

        public override JsonConverter CreateConverter(
            Type type, 
            JsonSerializerOptions options)
        {
            Type keyType = type.GetGenericArguments()[0];
            Type valueType = type.GetGenericArguments()[1];

            JsonConverter converter = (JsonConverter)Activator.CreateInstance(
                typeof(DictionaryEnumConverterInner<,>).MakeGenericType(
                    new Type[] { keyType, valueType }),
                BindingFlags.Instance | BindingFlags.Public,
                binder: null,
                args: new object[] { options },
                culture: null);

            return converter;
        }

        private class DictionaryEnumConverterInner<TKey, TValue> : 
            JsonConverter<Dictionary<TKey, TValue>> where TKey : struct, Enum
        {
            private readonly JsonConverter<TValue> _valueConverter;
            private Type _keyType;
            private Type _valueType;

            public DictionaryEnumConverterInner(JsonSerializerOptions options)
            {
                // For performance, use the existing converter if available.
                _valueConverter = (JsonConverter<TValue>)options
                    .GetConverter(typeof(TValue));

                // Cache the key and value types.
                _keyType = typeof(TKey);
                _valueType = typeof(TValue);
            }

            public override Dictionary<TKey, TValue> Read(
                ref Utf8JsonReader reader, 
                Type typeToConvert, 
                JsonSerializerOptions options)
            {
                if (reader.TokenType != JsonTokenType.StartObject)
                {
                    throw new JsonException();
                }

                Dictionary<TKey, TValue> value = new Dictionary<TKey, TValue>();

                while (reader.Read())
                {
                    if (reader.TokenType == JsonTokenType.EndObject)
                    {
                        return value;
                    }

                    // Get the key.
                    if (reader.TokenType != JsonTokenType.PropertyName)
                    {
                        throw new JsonException();
                    }

                    string propertyName = reader.GetString();

                    // For performance, parse with ignoreCase:false first.
                    if (!Enum.TryParse(propertyName, ignoreCase: false, out TKey key) &&
                        !Enum.TryParse(propertyName, ignoreCase: true, out key))
                    {
                        throw new JsonException(
                            $"Unable to convert \"{propertyName}\" to Enum \"{_keyType}\".");
                    }

                    // Get the value.
                    TValue v;
                    if (_valueConverter != null)
                    {
                        reader.Read();
                        v = _valueConverter.Read(ref reader, _valueType, options);
                    }
                    else
                    {
                        v = JsonSerializer.Deserialize<TValue>(ref reader, options);
                    }

                    // Add to dictionary.
                    value.Add(key, v);
                }

                throw new JsonException();
            }

            public override void Write(
                Utf8JsonWriter writer, 
                Dictionary<TKey, TValue> value, 
                JsonSerializerOptions options)
            {
                writer.WriteStartObject();

                foreach (KeyValuePair<TKey, TValue> kvp in value)
                {
                    writer.WritePropertyName(kvp.Key.ToString());

                    if (_valueConverter != null)
                    {
                        _valueConverter.Write(writer, kvp.Value, options);
                    }
                    else
                    {
                        JsonSerializer.Serialize(writer, kvp.Value, options);
                    }
                }

                writer.WriteEndObject();
            }
        }
    }
}
```

Приведенный выше код аналогичен приведенному в [словаре поддержки с ключом, не являющимся строкой](#support-dictionary-with-non-string-key) далее в этой статье.

## <a name="steps-to-follow-the-basic-pattern"></a>Шаги по базовому шаблону

Ниже описано, как создать преобразователь, следуя базовому шаблону.

* Создайте класс, производный от <xref:System.Text.Json.Serialization.JsonConverter%601>, где `T` — это тип для сериализации и десериализации.
* Переопределите метод `Read`, чтобы десериализовать входящий JSON и преобразовать его в тип `T`. Используйте <xref:System.Text.Json.Utf8JsonReader>, передаваемый в метод для чтения JSON.
* Переопределите метод `Write`, чтобы сериализовать входящий объект типа `T`. Используйте <xref:System.Text.Json.Utf8JsonWriter>, передаваемый в метод для записи JSON.
* Переопределяйте метод `CanConvert` только при необходимости. Реализация по умолчанию возвращает `true`, если тип для преобразования имеет тип `T`. Поэтому для преобразователей, поддерживающих только тип `T` не требуется переопределять этот метод. Пример преобразователя, в котором требуется переопределить этот метод, см. в подразделе « [полиморфизм десериализации](#support-polymorphic-deserialization) » далее в этой статье.

В качестве эталонных реализаций для написания пользовательских преобразователей можно обратиться к [исходному коду встроенных преобразователей](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/) .

## <a name="steps-to-follow-the-factory-pattern"></a>Действия по шаблону фабрики

Ниже описано, как создать преобразователь, следуя шаблону фабрики.

* Создайте класс, наследующий от класса <xref:System.Text.Json.Serialization.JsonConverterFactory>.
* Переопределите метод `CanConvert`, чтобы он возвращал значение true, если преобразуемый тип является одним, который может быть преобразован преобразователем. Например, если преобразователь предназначен для `List<T>` он может работать только с `List<int>`, `List<string>`и `List<DateTime>`. 
* Переопределите метод `CreateConverter`, чтобы он возвращал экземпляр класса преобразователя, обрабатывающего тип для преобразования, который будет предоставлен во время выполнения.
* Создайте класс преобразователя, который создает экземпляр метода `CreateConverter`. 

Шаблон фабрики необходим для открытых универсальных шаблонов, поскольку код для преобразования объекта в строку и из строки не совпадает для всех типов. Преобразователь для открытого универсального типа (например,`List<T>`) должен создать преобразователь для закрытого универсального типа (например,`List<DateTime>`) в фоновом режиме. Необходимо написать код для работы с каждым закрытым универсальным типом, который может обрабатываться преобразователем.

Тип `Enum` похож на открытый универсальный тип: преобразователь для `Enum` должен создать преобразователь для определенного `Enum` (например,`WeekdaysEnum`) в фоновом режиме. 

## <a name="error-handling"></a>Обработка ошибок

Если необходимо создать исключение в коде обработки ошибок, рассмотрите возможность создания <xref:System.Text.Json.JsonException> без сообщения. Этот тип исключения автоматически создает сообщение, содержащее путь к части JSON, вызвавшей ошибку. Например, инструкция `throw new JsonException();` выдает сообщение об ошибке, как в следующем примере:

```text
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

Если вы выдаете сообщение (например, `throw new JsonException("Error occurred)`, исключение по-прежнему предоставляет путь в свойстве <xref:System.Text.Json.JsonException.Path>.

## <a name="register-a-custom-converter"></a>Регистрация пользовательского преобразователя

*Зарегистрируйте* пользовательский преобразователь, чтобы методы `Serialize` и `Deserialize` использовали его. Выберите один из следующих подходов:

* Добавьте экземпляр класса преобразователя в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType>.
* Примените атрибут [[жсонконвертер]](xref:System.Text.Json.Serialization.JsonConverterAttribute) к свойствам, для которых требуется пользовательский преобразователь.
* Примените атрибут [[жсонконвертер]](xref:System.Text.Json.Serialization.JsonConverterAttribute) к классу или структуре, представляющей пользовательский тип значения.

## <a name="registration-sample---converters-collection"></a>Пример регистрации — Коллекция преобразователей 

Ниже приведен пример, который делает `ExampleDateTimeOffsetConverter` по умолчанию для свойств типа `DateTimeOffset`.

```csharp
//...
JsonSerializerOptions options = new JsonSerializerOptions();
options.Converters.Add(new ExampleDateTimeOffsetConverter());
string json = JsonSerializer.Serialize(weatherForecast, options);
```

Предположим, что Вы сериализуете следующий тип:

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

Ниже приведен пример выходных данных JSON, демонстрирующий использование пользовательского преобразователя.

```json
{
  "Date": "08/01/2019",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

Следующий код использует тот же подход для десериализации с помощью пользовательского преобразователя `DateTimeOffset`:

```csharp
//...
JsonSerializerOptions options = new JsonSerializerOptions();
options.Converters.Add(new ExampleDateTimeOffsetConverter());
weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json, options);
```

## <a name="registration-sample---jsonconverter-on-a-property"></a>Пример регистрации-[Жсонконвертер] для свойства

Следующий код выбирает пользовательский преобразователь для свойства `Date`:

```csharp
class WeatherForecastWithConverter
{
    [JsonConverter(typeof(ExampleDateTimeOffsetConverter))]
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

Для сериализации и десериализации кода `WeatherForecastWithConverter` не требуется использование `JsonSerializeOptions.Converters`:

```csharp
string json = JsonSerializer.Serialize(weatherForecastWithConverter);
```

```csharp
weatherForecast = JsonSerializer.Deserialize<WeatherForecastWithConverter>(json);
```

## <a name="registration-sample---jsonconverter-on-a-type"></a>Пример регистрации-[Жсонконвертер] для типа

Вот код, создающий структуру и применяющий к нему атрибут `[JsonConverter]`:

```csharp
[JsonConverter(typeof(TemperatureConverter))]
public struct Temperature
{
    public Temperature(int degrees, bool celsius)
    {
        _degrees = degrees;
        _isCelsius = celsius;
    }
    private bool _isCelsius;
    private int _degrees;
    public int Degrees => _degrees;
    public bool IsCelsius => _isCelsius; 
    public bool IsFahrenheit => !_isCelsius;
    public override string ToString() =>
        $"{_degrees.ToString()}{(_isCelsius ? "C" : "F")}";
    public static Temperature Parse(string input)
    {
        int degrees = int.Parse(input.Substring(0, input.Length - 1));
        bool celsius = (input.Substring(input.Length - 1) == "C");
        return new Temperature(degrees, celsius);
    }
}
```

Вот пользовательский преобразователь для предыдущей структуры:

```csharp
public class TemperatureConverter : JsonConverter<Temperature>
{
    public override Temperature Read(
        ref Utf8JsonReader reader,
        Type typeToConvert,
        JsonSerializerOptions options)
    {
        Debug.Assert(typeToConvert == typeof(Temperature));
        return Temperature.Parse(reader.GetString());
    }

    public override void Write(
        Utf8JsonWriter writer,
        Temperature value,
        JsonSerializerOptions options)
    {
        writer.WriteStringValue(value.ToString());
    }
}
```

Атрибут `[JsonConvert]` в структуре регистрирует пользовательский преобразователь в качестве значения по умолчанию для свойств типа `Temperature`. Этот преобразователь автоматически используется в свойстве `TemperatureC` следующего типа при сериализации или десериализации.

```csharp
class WeatherForecastWithTemperatureStruct
{
    public DateTimeOffset Date { get; set; }
    public Temperature TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

## <a name="converter-registration-precedence"></a>Приоритет регистрации преобразователя

Во время сериализации или десериализации выбирается преобразователь для каждого элемента JSON в следующем порядке, в котором в списке от наивысшего приоритета к наименьшему:

* `[JsonConverter]` применено к свойству.
* Преобразователь, добавленный в коллекцию `Converters`.
* `[JsonConverter]` применяется к пользовательскому типу значения или POCO.

Если в коллекции `Converters` зарегистрировано несколько пользовательских преобразователей, то используется первый преобразователь, возвращающий значение true для `CanConvert`.

Встроенный преобразователь выбирается только в том случае, если соответствующий пользовательский преобразователь не зарегистрирован.

## <a name="converter-samples-for-common-scenarios"></a>Примеры преобразователей для распространенных сценариев

В следующих разделах приведены примеры преобразователей, в которых рассматриваются некоторые распространенные сценарии, которые не обрабатывались встроенными функциями.

### <a name="deserialize-inferred-types-to-object-properties"></a>Десериализация выводимых типов в свойства объекта

При десериализации свойства типа `Object`создается объект `JsonElement`. Причина заключается в том, что десериализатор не знает, какой тип CLR создать, и не пытается угадать. Например, если свойство JSON имеет значение "true", десериализатор не определит, что значение является `Boolean`, а если у элемента есть "01/01/2019", десериализатор не определит, что это `DateTime`.

Вывод типа может быть неточным. Если десериализатор анализирует номер JSON, не имеющий десятичного разделителя, в качестве `long`, это может привести к проблемам вне диапазона, если значение первоначально было сериализовано как `ulong` или `BigInteger`. Анализ числа с десятичной запятой в качестве `double` может привести к потере точности, если это число было первоначально сериализовано как `decimal`.

В сценариях, требующих вывода типа, в следующем коде показан пользовательский преобразователь для `Object` свойств. Код преобразует:

* `true` и `false` `Boolean`
* Числа для `long` или `double`
* Даты для `DateTime`
* Строки для `string`
* Все остальное для `JsonElement`

```csharp
using System;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class ObjectToInferredTypesConverter
        : JsonConverter<object>
    {
        public override object Read(
            ref Utf8JsonReader reader,
            Type typeToConvert,
            JsonSerializerOptions options)
        {
            if (reader.TokenType == JsonTokenType.True)
            {
                return true;
            }

            if (reader.TokenType == JsonTokenType.False)
            {
                return false;
            }

            if (reader.TokenType == JsonTokenType.Number)
            {
                if (reader.TryGetInt64(out long l))
                {
                    return l;
                }

                return reader.GetDouble();
            }

            if (reader.TokenType == JsonTokenType.String)
            {
                if (reader.TryGetDateTime(out DateTime datetime))
                {
                    return datetime;
                }

                return reader.GetString();
            }

            // Use JsonElement as fallback.
            // Newtonsoft uses JArray or JObject.
            using (JsonDocument document = JsonDocument.ParseValue(ref reader))
            {
                return document.RootElement.Clone();
            }
        }

        public override void Write(
            Utf8JsonWriter writer,
            object value,
            JsonSerializerOptions options)
        {
            throw new InvalidOperationException("Should not get here.");
        }
    }
}
```

Следующий код регистрирует преобразователь:

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new ObjectToInferredTypesConverter());
```

Ниже приведен пример типа со свойством объекта:

```csharp
public class WeatherForecastWithObjectProperties
{
    public object Date { get; set; }
    public object TemperatureC { get; set; }
    public object Summary { get; set; }
}
```

Следующий пример JSON для десериализации содержит значения, которые будут десериализованы как `DateTime`, `long`и `string`:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
}
```

Без пользовательского преобразователя десериализация помещает `JsonElement` в каждое свойство.

В [папке Unit Tests](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) в пространстве имен `System.Text.Json.Serialization` есть дополнительные примеры пользовательских преобразователей, которые обрабатывали свойства объекта.

### <a name="support-dictionary-with-non-string-key"></a>Словарь поддержки с ключом, не являющимся строкой

Встроенная поддержка коллекций словаря предназначена для `Dictionary<string, TValue>`. То есть ключ должен быть строкой. Для поддержки словаря с целым числом или другим типом в качестве ключа требуется пользовательский преобразователь.

В следующем коде показан пользовательский преобразователь, работающий с `Dictionary<Enum,TValue>`:

```csharp
using System;
using System.Collections.Generic;
using System.Reflection;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class ConverterDictionaryTKeyEnumTValue : JsonConverterFactory
    {
        public override bool CanConvert(Type typeToConvert)
        {
            if (!typeToConvert.IsGenericType)
            {
                return false;
            }

            if (typeToConvert.GetGenericTypeDefinition() != typeof(Dictionary<,>))
            {
                return false;
            }

            return typeToConvert.GetGenericArguments()[0].IsEnum;
        }

        public override JsonConverter CreateConverter(
            Type type, 
            JsonSerializerOptions options)
        {
            Type keyType = type.GetGenericArguments()[0];
            Type valueType = type.GetGenericArguments()[1];

            JsonConverter converter = (JsonConverter)Activator.CreateInstance(
                typeof(DictionaryEnumConverterInner<,>).MakeGenericType(
                    new Type[] { keyType, valueType }),
                BindingFlags.Instance | BindingFlags.Public,
                binder: null,
                args: new object[] { options },
                culture: null);

            return converter;
        }

        private class DictionaryEnumConverterInner<TKey, TValue> : 
            JsonConverter<Dictionary<TKey, TValue>> where TKey : struct, Enum
        {
            private readonly JsonConverter<TValue> _valueConverter;
            private Type _keyType;
            private Type _valueType;

            public DictionaryEnumConverterInner(JsonSerializerOptions options)
            {
                // For performance, use the existing converter if available.
                _valueConverter = (JsonConverter<TValue>)options
                    .GetConverter(typeof(TValue));

                // Cache the key and value types.
                _keyType = typeof(TKey);
                _valueType = typeof(TValue);
            }

            public override Dictionary<TKey, TValue> Read(
                ref Utf8JsonReader reader, 
                Type typeToConvert, 
                JsonSerializerOptions options)
            {
                if (reader.TokenType != JsonTokenType.StartObject)
                {
                    throw new JsonException();
                }

                Dictionary<TKey, TValue> value = new Dictionary<TKey, TValue>();

                while (reader.Read())
                {
                    if (reader.TokenType == JsonTokenType.EndObject)
                    {
                        return value;
                    }

                    // Get the key.
                    if (reader.TokenType != JsonTokenType.PropertyName)
                    {
                        throw new JsonException();
                    }

                    string propertyName = reader.GetString();

                    // For performance, parse with ignoreCase:false first.
                    if (!Enum.TryParse(propertyName, ignoreCase: false, out TKey key) &&
                        !Enum.TryParse(propertyName, ignoreCase: true, out key))
                    {
                        throw new JsonException(
                            $"Unable to convert \"{propertyName}\" to Enum \"{_keyType}\".");
                    }

                    // Get the value.
                    TValue v;
                    if (_valueConverter != null)
                    {
                        reader.Read();
                        v = _valueConverter.Read(ref reader, _valueType, options);
                    }
                    else
                    {
                        v = JsonSerializer.Deserialize<TValue>(ref reader, options);
                    }

                    // Add to dictionary.
                    value.Add(key, v);
                }

                throw new JsonException();
            }

            public override void Write(
                Utf8JsonWriter writer, 
                Dictionary<TKey, TValue> value, 
                JsonSerializerOptions options)
            {
                writer.WriteStartObject();

                foreach (KeyValuePair<TKey, TValue> kvp in value)
                {
                    writer.WritePropertyName(kvp.Key.ToString());

                    if (_valueConverter != null)
                    {
                        _valueConverter.Write(writer, kvp.Value, options);
                    }
                    else
                    {
                        JsonSerializer.Serialize(writer, kvp.Value, options);
                    }
                }

                writer.WriteEndObject();
            }
        }
    }
}
```

Следующий код регистрирует преобразователь:

```csharp
var serializeOptions = new JsonSerializerOptions();
serializeOptions.Converters.Add(new ConverterDictionaryTKeyEnumTValue());
```

Преобразователь может сериализовать и десериализовать свойство `TemperatureRanges` следующего класса, который использует следующие `Enum`:

```csharp
public class WeatherForecastWithEnumDictionary
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public Dictionary<SummaryWordsEnum, int> TemperatureRanges { get; set; }
}

public enum SummaryWordsEnum
{
    Cold, Hot
}
```

Выходные данные JSON из сериализации выглядят, как в следующем примере:

```json
{

  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "Cold": 20,
    "Hot": 40
  }
}
```

В [папке Unit Tests](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) в пространстве имен `System.Text.Json.Serialization` есть дополнительные примеры пользовательских преобразователей, обрабатывающих словари, не являющиеся строковыми.

### <a name="support-polymorphic-deserialization"></a>Поддержка полиморфизма

Для сериализации с помощью [полиморфизма](system-text-json-how-to.md#serialize-properties-of-derived-classes) не требуется пользовательский преобразователь, но для десериализации требуется пользовательский преобразователь.

Предположим, например, что имеется `Person` абстрактный базовый класс с `Employee` и `Customer` производными классами. Полиморфизм десериализации означает, что во время разработки можно указать `Person` в качестве цели десериализации, а `Customer` и `Employee` объекты в JSON правильно десериализовать во время выполнения. Во время десериализации необходимо найти подсказки, которые указывают требуемый тип в JSON. В каждом сценарии доступны различные виды подкатегории. Например, может быть доступно свойство дискриминатора, или может потребоваться полагаться на присутствие или отсутствие конкретного свойства. В текущем выпуске `System.Text.Json` не предоставлены атрибуты для указания способов управления сценариями десериализации, поэтому требуются пользовательские преобразователи.

В следующем коде показан базовый класс, два производных класса и пользовательский преобразователь для них. Преобразователь использует свойство дискриминатора для преобразования в полиморфизм. Дискриминатор типа не находится в определениях классов, но создается во время сериализации и считывается во время десериализации.

```csharp
public class Person
{
    public string Name { get; set; }
}

public class Customer : Person
{
    public decimal CreditLimit { get; set; }
}

public class Employee : Person
{
    public string OfficeNumber { get; set; }
}
```

```csharp
using System;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class PersonConverterWithTypeDiscriminator : JsonConverter<Person>
    {
        enum TypeDiscriminator
        {
            Customer = 1,
            Employee = 2
        }

        public override bool CanConvert(Type typeToConvert)
        {
            return typeof(Person).IsAssignableFrom(typeToConvert);
        }

        public override Person Read(ref Utf8JsonReader reader, Type typeToConvert, JsonSerializerOptions options)
        {
            if (reader.TokenType != JsonTokenType.StartObject)
            {
                throw new JsonException();
            }

            reader.Read();
            if (reader.TokenType != JsonTokenType.PropertyName)
            {
                throw new JsonException();
            }

            string propertyName = reader.GetString();
            if (propertyName != "TypeDiscriminator")
            {
                throw new JsonException();
            }

            reader.Read();
            if (reader.TokenType != JsonTokenType.Number)
            {
                throw new JsonException();
            }

            Person value;
            TypeDiscriminator typeDiscriminator = (TypeDiscriminator)reader.GetInt32();
            switch (typeDiscriminator)
            {
                case TypeDiscriminator.Customer:
                    value = new Customer();
                    break;

                case TypeDiscriminator.Employee:
                    value = new Employee();
                    break;

                default:
                    throw new JsonException();
            }

            while (reader.Read())
            {
                if (reader.TokenType == JsonTokenType.EndObject)
                {
                    return value;
                }

                if (reader.TokenType == JsonTokenType.PropertyName)
                {
                    propertyName = reader.GetString();
                    reader.Read();
                    switch (propertyName)
                    {
                        case "CreditLimit":
                            decimal creditLimit = reader.GetDecimal();
                            ((Customer)value).CreditLimit = creditLimit;
                            break;
                        case "OfficeNumber":
                            string officeNumber = reader.GetString();
                            ((Employee)value).OfficeNumber = officeNumber;
                            break;
                        case "Name":
                            string name = reader.GetString();
                            value.Name = name;
                            break;
                    }
                }
            }

            throw new JsonException();
        }

        public override void Write(Utf8JsonWriter writer, Person value, JsonSerializerOptions options)
        {
            writer.WriteStartObject();

            if (value is Customer customer)
            {
                writer.WriteNumber("TypeDiscriminator", (int)TypeDiscriminator.Customer);
                writer.WriteNumber("CreditLimit", customer.CreditLimit);
            }
            else if (value is Employee employee)
            {
                writer.WriteNumber("TypeDiscriminator", (int)TypeDiscriminator.Employee);
                writer.WriteString("OfficeNumber", employee.OfficeNumber);
            }

            writer.WriteString("Name", value.Name);

            writer.WriteEndObject();
        }
    }
}
```

Следующий код регистрирует преобразователь:

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new PersonConverterWithTypeDiscriminator());
```

Преобразователь может десериализовать JSON, созданный с помощью того же преобразователя, для сериализации, например:

```json
[
  {
    "TypeDiscriminator": 1,
    "CreditLimit": 10000,
    "Name": "John"
  },
  {
    "TypeDiscriminator": 2,
    "OfficeNumber": "555-1234",
    "Name": "Nancy"
  }
]
```

## <a name="other-custom-converter-samples"></a>Другие примеры пользовательских преобразователей

[Папка Unit Tests](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) в исходном коде `System.Text.Json.Serialization` содержит другие примеры пользовательских преобразователей, например:

* преобразователь `Int32`, который преобразует значение NULL в 0 при десериализации
* преобразователь `Int32`, допускающий строковые и числовые значения при десериализации
* преобразователь `Enum`
* преобразователь `List<T>`, принимающий внешние данные
* преобразователь `Long[]`, который работает с разделенным запятыми списком чисел 

## <a name="additional-resources"></a>Дополнительные ресурсы

* [Общие сведения о System. Text. JSON](system-text-json-overview.md)
* [Справочник по API System. Text. JSON](xref:System.Text.Json)
* [Использование System. Text. JSON](system-text-json-how-to.md)
* [Исходный код для встроенных преобразователей](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/)
* Проблемы GitHub, связанные с пользовательскими преобразователями для `System.Text.Json`
  * [36639. Введение в пользовательские конвертеры](https://github.com/dotnet/corefx/issues/36639)
  * [38713 о десериализации в объект](https://github.com/dotnet/corefx/issues/38713)
  * [40120 о словарях, не являющихся строковыми ключами](https://github.com/dotnet/corefx/issues/40120)
  * [37787 о полиморфизме](https://github.com/dotnet/corefx/issues/37787)
