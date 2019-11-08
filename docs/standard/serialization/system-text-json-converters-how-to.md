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
# <a name="how-to-write-custom-converters-for-json-serialization-in-net"></a><span data-ttu-id="88ef7-102">Написание пользовательских преобразователей для сериализации JSON в .NET</span><span class="sxs-lookup"><span data-stu-id="88ef7-102">How to write custom converters for JSON serialization in .NET</span></span>

<span data-ttu-id="88ef7-103">В этой статье показано, как создать пользовательские преобразователи для классов сериализации JSON, предоставляемых в пространстве имен <xref:System.Text.Json>.</span><span class="sxs-lookup"><span data-stu-id="88ef7-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span></span> <span data-ttu-id="88ef7-104">Общие сведения о `System.Text.Json`см. [в статье сериализация и десериализация JSON в .NET](system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="88ef7-104">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="88ef7-105">*Преобразователь* — это класс, который преобразует объект или значение в JSON и обратно.</span><span class="sxs-lookup"><span data-stu-id="88ef7-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="88ef7-106">Пространство имен `System.Text.Json` содержит встроенные преобразователи для большинства типов-примитивов, которые сопоставляются с примитивами JavaScript.</span><span class="sxs-lookup"><span data-stu-id="88ef7-106">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="88ef7-107">Вы можете создавать пользовательские преобразователи:</span><span class="sxs-lookup"><span data-stu-id="88ef7-107">You can write custom converters:</span></span>

* <span data-ttu-id="88ef7-108">Переопределение поведения по умолчанию встроенного преобразователя.</span><span class="sxs-lookup"><span data-stu-id="88ef7-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="88ef7-109">Например, может потребоваться, чтобы `DateTime` значения были представлены в формате мм/дд/гггг вместо формата ISO 8601-1:2019 по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="88ef7-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="88ef7-110">Для поддержки пользовательского типа значения.</span><span class="sxs-lookup"><span data-stu-id="88ef7-110">To support a custom value type.</span></span> <span data-ttu-id="88ef7-111">Например, структура `PhoneNumber`.</span><span class="sxs-lookup"><span data-stu-id="88ef7-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="88ef7-112">Можно также написать пользовательские преобразователи для расширения `System.Text.Json` с функциональностью, не входящей в текущий выпуск.</span><span class="sxs-lookup"><span data-stu-id="88ef7-112">You can also write custom converters to extend `System.Text.Json` with functionality not included in the current release.</span></span> <span data-ttu-id="88ef7-113">Далее в этой статье рассматриваются следующие сценарии.</span><span class="sxs-lookup"><span data-stu-id="88ef7-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="88ef7-114">[Десериализация выводимых типов в свойства объекта](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="88ef7-114">[Deserialize inferred types to Object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="88ef7-115">[Словарь поддержки с ключом, не являющимся строкой](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="88ef7-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="88ef7-116">[Поддержка полиморфизма](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="88ef7-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="88ef7-117">Пользовательские шаблоны преобразователя</span><span class="sxs-lookup"><span data-stu-id="88ef7-117">Custom converter patterns</span></span>

<span data-ttu-id="88ef7-118">Существует два шаблона создания пользовательского преобразователя: базовый шаблон и шаблон фабрики.</span><span class="sxs-lookup"><span data-stu-id="88ef7-118">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="88ef7-119">Шаблон фабрики предназначен для преобразователей, обрабатывающих `Enum` типов или открытых универсальных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="88ef7-119">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="88ef7-120">Базовый шаблон предназначен для неуниверсальных и закрытых универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="88ef7-120">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="88ef7-121">Например, для преобразователей следующих типов требуется шаблон фабрики:</span><span class="sxs-lookup"><span data-stu-id="88ef7-121">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="88ef7-122">Ниже приведены некоторые примеры типов, которые могут быть обработаны базовым шаблоном.</span><span class="sxs-lookup"><span data-stu-id="88ef7-122">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="88ef7-123">Базовый шаблон создает класс, который может работать с одним типом.</span><span class="sxs-lookup"><span data-stu-id="88ef7-123">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="88ef7-124">Шаблон фабрики создает класс, который определяет в среде выполнения, какой необходим конкретный тип, и динамически создает соответствующий преобразователь.</span><span class="sxs-lookup"><span data-stu-id="88ef7-124">The factory pattern creates a class that determines at runtime which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="88ef7-125">Образец базового преобразователя</span><span class="sxs-lookup"><span data-stu-id="88ef7-125">Sample basic converter</span></span>

<span data-ttu-id="88ef7-126">Следующий пример представляет собой преобразователь, который переопределяет сериализацию по умолчанию для существующего типа данных.</span><span class="sxs-lookup"><span data-stu-id="88ef7-126">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="88ef7-127">Для `DateTimeOffset` свойств преобразователь использует формат мм/дд/гггг.</span><span class="sxs-lookup"><span data-stu-id="88ef7-127">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

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

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="88ef7-128">Образец преобразователя шаблона фабрики</span><span class="sxs-lookup"><span data-stu-id="88ef7-128">Sample factory pattern converter</span></span>

<span data-ttu-id="88ef7-129">В следующем коде показан пользовательский преобразователь, работающий с `Dictionary<Enum,TValue>`.</span><span class="sxs-lookup"><span data-stu-id="88ef7-129">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="88ef7-130">Код соответствует шаблону фабрики, так как первый параметр универсального типа является `Enum`, а второй — открытым.</span><span class="sxs-lookup"><span data-stu-id="88ef7-130">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="88ef7-131">Метод `CanConvert` возвращает `true` только для `Dictionary` с двумя универсальными параметрами, первый из которых является типом `Enum`.</span><span class="sxs-lookup"><span data-stu-id="88ef7-131">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="88ef7-132">Внутренний преобразователь получает существующий преобразователь для работы с любым типом, предоставленным во время выполнения для `TValue`.</span><span class="sxs-lookup"><span data-stu-id="88ef7-132">The inner converter gets an existing converter to handle whichever type is provided at runtime for `TValue`.</span></span> 

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

<span data-ttu-id="88ef7-133">Приведенный выше код аналогичен приведенному в [словаре поддержки с ключом, не являющимся строкой](#support-dictionary-with-non-string-key) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="88ef7-133">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="88ef7-134">Шаги по базовому шаблону</span><span class="sxs-lookup"><span data-stu-id="88ef7-134">Steps to follow the basic pattern</span></span>

<span data-ttu-id="88ef7-135">Ниже описано, как создать преобразователь, следуя базовому шаблону.</span><span class="sxs-lookup"><span data-stu-id="88ef7-135">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="88ef7-136">Создайте класс, производный от <xref:System.Text.Json.Serialization.JsonConverter%601>, где `T` — это тип для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="88ef7-136">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="88ef7-137">Переопределите метод `Read`, чтобы десериализовать входящий JSON и преобразовать его в тип `T`.</span><span class="sxs-lookup"><span data-stu-id="88ef7-137">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="88ef7-138">Используйте <xref:System.Text.Json.Utf8JsonReader>, передаваемый в метод для чтения JSON.</span><span class="sxs-lookup"><span data-stu-id="88ef7-138">Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="88ef7-139">Переопределите метод `Write`, чтобы сериализовать входящий объект типа `T`.</span><span class="sxs-lookup"><span data-stu-id="88ef7-139">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="88ef7-140">Используйте <xref:System.Text.Json.Utf8JsonWriter>, передаваемый в метод для записи JSON.</span><span class="sxs-lookup"><span data-stu-id="88ef7-140">Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="88ef7-141">Переопределяйте метод `CanConvert` только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="88ef7-141">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="88ef7-142">Реализация по умолчанию возвращает `true`, если тип для преобразования имеет тип `T`.</span><span class="sxs-lookup"><span data-stu-id="88ef7-142">The default implementation returns `true` when the type to convert is type `T`.</span></span> <span data-ttu-id="88ef7-143">Поэтому для преобразователей, поддерживающих только тип `T` не требуется переопределять этот метод.</span><span class="sxs-lookup"><span data-stu-id="88ef7-143">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="88ef7-144">Пример преобразователя, в котором требуется переопределить этот метод, см. в подразделе « [полиморфизм десериализации](#support-polymorphic-deserialization) » далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="88ef7-144">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="88ef7-145">В качестве эталонных реализаций для написания пользовательских преобразователей можно обратиться к [исходному коду встроенных преобразователей](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/) .</span><span class="sxs-lookup"><span data-stu-id="88ef7-145">You can refer to the [built-in converters source code](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="88ef7-146">Действия по шаблону фабрики</span><span class="sxs-lookup"><span data-stu-id="88ef7-146">Steps to follow the factory pattern</span></span>

<span data-ttu-id="88ef7-147">Ниже описано, как создать преобразователь, следуя шаблону фабрики.</span><span class="sxs-lookup"><span data-stu-id="88ef7-147">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="88ef7-148">Создайте класс, наследующий от класса <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span><span class="sxs-lookup"><span data-stu-id="88ef7-148">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="88ef7-149">Переопределите метод `CanConvert`, чтобы он возвращал значение true, если преобразуемый тип является одним, который может быть преобразован преобразователем.</span><span class="sxs-lookup"><span data-stu-id="88ef7-149">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="88ef7-150">Например, если преобразователь предназначен для `List<T>` он может работать только с `List<int>`, `List<string>`и `List<DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="88ef7-150">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span> 
* <span data-ttu-id="88ef7-151">Переопределите метод `CreateConverter`, чтобы он возвращал экземпляр класса преобразователя, обрабатывающего тип для преобразования, который будет предоставлен во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="88ef7-151">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at runtime.</span></span>
* <span data-ttu-id="88ef7-152">Создайте класс преобразователя, который создает экземпляр метода `CreateConverter`.</span><span class="sxs-lookup"><span data-stu-id="88ef7-152">Create the converter class that the `CreateConverter` method instantiates.</span></span> 

<span data-ttu-id="88ef7-153">Шаблон фабрики необходим для открытых универсальных шаблонов, поскольку код для преобразования объекта в строку и из строки не совпадает для всех типов.</span><span class="sxs-lookup"><span data-stu-id="88ef7-153">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="88ef7-154">Преобразователь для открытого универсального типа (например,`List<T>`) должен создать преобразователь для закрытого универсального типа (например,`List<DateTime>`) в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="88ef7-154">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="88ef7-155">Необходимо написать код для работы с каждым закрытым универсальным типом, который может обрабатываться преобразователем.</span><span class="sxs-lookup"><span data-stu-id="88ef7-155">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="88ef7-156">Тип `Enum` похож на открытый универсальный тип: преобразователь для `Enum` должен создать преобразователь для определенного `Enum` (например,`WeekdaysEnum`) в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="88ef7-156">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span> 

## <a name="error-handling"></a><span data-ttu-id="88ef7-157">Обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="88ef7-157">Error handling</span></span>

<span data-ttu-id="88ef7-158">Если необходимо создать исключение в коде обработки ошибок, рассмотрите возможность создания <xref:System.Text.Json.JsonException> без сообщения.</span><span class="sxs-lookup"><span data-stu-id="88ef7-158">If you need to throw an exception in error-handling code, consider throwing a <xref:System.Text.Json.JsonException> without a message.</span></span> <span data-ttu-id="88ef7-159">Этот тип исключения автоматически создает сообщение, содержащее путь к части JSON, вызвавшей ошибку.</span><span class="sxs-lookup"><span data-stu-id="88ef7-159">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="88ef7-160">Например, инструкция `throw new JsonException();` выдает сообщение об ошибке, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="88ef7-160">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```text
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="88ef7-161">Если вы выдаете сообщение (например, `throw new JsonException("Error occurred)`, исключение по-прежнему предоставляет путь в свойстве <xref:System.Text.Json.JsonException.Path>.</span><span class="sxs-lookup"><span data-stu-id="88ef7-161">If you do provide a message (for example, `throw new JsonException("Error occurred)`, the exception still provides the path in the <xref:System.Text.Json.JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="88ef7-162">Регистрация пользовательского преобразователя</span><span class="sxs-lookup"><span data-stu-id="88ef7-162">Register a custom converter</span></span>

<span data-ttu-id="88ef7-163">*Зарегистрируйте* пользовательский преобразователь, чтобы методы `Serialize` и `Deserialize` использовали его.</span><span class="sxs-lookup"><span data-stu-id="88ef7-163">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="88ef7-164">Выберите один из следующих подходов:</span><span class="sxs-lookup"><span data-stu-id="88ef7-164">Choose one of the following approaches:</span></span>

* <span data-ttu-id="88ef7-165">Добавьте экземпляр класса преобразователя в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="88ef7-165">Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="88ef7-166">Примените атрибут [[жсонконвертер]](xref:System.Text.Json.Serialization.JsonConverterAttribute) к свойствам, для которых требуется пользовательский преобразователь.</span><span class="sxs-lookup"><span data-stu-id="88ef7-166">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="88ef7-167">Примените атрибут [[жсонконвертер]](xref:System.Text.Json.Serialization.JsonConverterAttribute) к классу или структуре, представляющей пользовательский тип значения.</span><span class="sxs-lookup"><span data-stu-id="88ef7-167">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="88ef7-168">Пример регистрации — Коллекция преобразователей</span><span class="sxs-lookup"><span data-stu-id="88ef7-168">Registration sample - Converters collection</span></span> 

<span data-ttu-id="88ef7-169">Ниже приведен пример, который делает `ExampleDateTimeOffsetConverter` по умолчанию для свойств типа `DateTimeOffset`.</span><span class="sxs-lookup"><span data-stu-id="88ef7-169">Here's an example that makes the `ExampleDateTimeOffsetConverter` the default for properties of type `DateTimeOffset`:</span></span>

```csharp
//...
JsonSerializerOptions options = new JsonSerializerOptions();
options.Converters.Add(new ExampleDateTimeOffsetConverter());
string json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="88ef7-170">Предположим, что Вы сериализуете следующий тип:</span><span class="sxs-lookup"><span data-stu-id="88ef7-170">Suppose you serialize the following type:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="88ef7-171">Ниже приведен пример выходных данных JSON, демонстрирующий использование пользовательского преобразователя.</span><span class="sxs-lookup"><span data-stu-id="88ef7-171">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="88ef7-172">Следующий код использует тот же подход для десериализации с помощью пользовательского преобразователя `DateTimeOffset`:</span><span class="sxs-lookup"><span data-stu-id="88ef7-172">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

```csharp
//...
JsonSerializerOptions options = new JsonSerializerOptions();
options.Converters.Add(new ExampleDateTimeOffsetConverter());
weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json, options);
```

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="88ef7-173">Пример регистрации-[Жсонконвертер] для свойства</span><span class="sxs-lookup"><span data-stu-id="88ef7-173">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="88ef7-174">Следующий код выбирает пользовательский преобразователь для свойства `Date`:</span><span class="sxs-lookup"><span data-stu-id="88ef7-174">The following code selects a custom converter for the `Date` property:</span></span>

```csharp
class WeatherForecastWithConverter
{
    [JsonConverter(typeof(ExampleDateTimeOffsetConverter))]
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="88ef7-175">Для сериализации и десериализации кода `WeatherForecastWithConverter` не требуется использование `JsonSerializeOptions.Converters`:</span><span class="sxs-lookup"><span data-stu-id="88ef7-175">The code to serialize and deserialize `WeatherForecastWithConverter` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

```csharp
string json = JsonSerializer.Serialize(weatherForecastWithConverter);
```

```csharp
weatherForecast = JsonSerializer.Deserialize<WeatherForecastWithConverter>(json);
```

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="88ef7-176">Пример регистрации-[Жсонконвертер] для типа</span><span class="sxs-lookup"><span data-stu-id="88ef7-176">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="88ef7-177">Вот код, создающий структуру и применяющий к нему атрибут `[JsonConverter]`:</span><span class="sxs-lookup"><span data-stu-id="88ef7-177">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

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

<span data-ttu-id="88ef7-178">Вот пользовательский преобразователь для предыдущей структуры:</span><span class="sxs-lookup"><span data-stu-id="88ef7-178">Here's the custom converter for the preceding struct:</span></span>

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

<span data-ttu-id="88ef7-179">Атрибут `[JsonConvert]` в структуре регистрирует пользовательский преобразователь в качестве значения по умолчанию для свойств типа `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="88ef7-179">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="88ef7-180">Этот преобразователь автоматически используется в свойстве `TemperatureC` следующего типа при сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="88ef7-180">The converter is automatically used on the `TemperatureC` property of the following type when you serialize or deserialize it:</span></span>

```csharp
class WeatherForecastWithTemperatureStruct
{
    public DateTimeOffset Date { get; set; }
    public Temperature TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

## <a name="converter-registration-precedence"></a><span data-ttu-id="88ef7-181">Приоритет регистрации преобразователя</span><span class="sxs-lookup"><span data-stu-id="88ef7-181">Converter registration precedence</span></span>

<span data-ttu-id="88ef7-182">Во время сериализации или десериализации выбирается преобразователь для каждого элемента JSON в следующем порядке, в котором в списке от наивысшего приоритета к наименьшему:</span><span class="sxs-lookup"><span data-stu-id="88ef7-182">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="88ef7-183">`[JsonConverter]` применено к свойству.</span><span class="sxs-lookup"><span data-stu-id="88ef7-183">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="88ef7-184">Преобразователь, добавленный в коллекцию `Converters`.</span><span class="sxs-lookup"><span data-stu-id="88ef7-184">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="88ef7-185">`[JsonConverter]` применяется к пользовательскому типу значения или POCO.</span><span class="sxs-lookup"><span data-stu-id="88ef7-185">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="88ef7-186">Если в коллекции `Converters` зарегистрировано несколько пользовательских преобразователей, то используется первый преобразователь, возвращающий значение true для `CanConvert`.</span><span class="sxs-lookup"><span data-stu-id="88ef7-186">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="88ef7-187">Встроенный преобразователь выбирается только в том случае, если соответствующий пользовательский преобразователь не зарегистрирован.</span><span class="sxs-lookup"><span data-stu-id="88ef7-187">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="88ef7-188">Примеры преобразователей для распространенных сценариев</span><span class="sxs-lookup"><span data-stu-id="88ef7-188">Converter samples for common scenarios</span></span>

<span data-ttu-id="88ef7-189">В следующих разделах приведены примеры преобразователей, в которых рассматриваются некоторые распространенные сценарии, которые не обрабатывались встроенными функциями.</span><span class="sxs-lookup"><span data-stu-id="88ef7-189">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="88ef7-190">Десериализация выводимых типов в свойства объекта</span><span class="sxs-lookup"><span data-stu-id="88ef7-190">Deserialize inferred types to Object properties</span></span>

<span data-ttu-id="88ef7-191">При десериализации свойства типа `Object`создается объект `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="88ef7-191">When deserializing to a property of type `Object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="88ef7-192">Причина заключается в том, что десериализатор не знает, какой тип CLR создать, и не пытается угадать.</span><span class="sxs-lookup"><span data-stu-id="88ef7-192">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="88ef7-193">Например, если свойство JSON имеет значение "true", десериализатор не определит, что значение является `Boolean`, а если у элемента есть "01/01/2019", десериализатор не определит, что это `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="88ef7-193">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="88ef7-194">Вывод типа может быть неточным.</span><span class="sxs-lookup"><span data-stu-id="88ef7-194">Type inference can be inaccurate.</span></span> <span data-ttu-id="88ef7-195">Если десериализатор анализирует номер JSON, не имеющий десятичного разделителя, в качестве `long`, это может привести к проблемам вне диапазона, если значение первоначально было сериализовано как `ulong` или `BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="88ef7-195">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="88ef7-196">Анализ числа с десятичной запятой в качестве `double` может привести к потере точности, если это число было первоначально сериализовано как `decimal`.</span><span class="sxs-lookup"><span data-stu-id="88ef7-196">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="88ef7-197">В сценариях, требующих вывода типа, в следующем коде показан пользовательский преобразователь для `Object` свойств.</span><span class="sxs-lookup"><span data-stu-id="88ef7-197">For scenarios that require type inference, the following code shows a custom converter for `Object` properties.</span></span> <span data-ttu-id="88ef7-198">Код преобразует:</span><span class="sxs-lookup"><span data-stu-id="88ef7-198">The code converts:</span></span>

* <span data-ttu-id="88ef7-199">`true` и `false` `Boolean`</span><span class="sxs-lookup"><span data-stu-id="88ef7-199">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="88ef7-200">Числа для `long` или `double`</span><span class="sxs-lookup"><span data-stu-id="88ef7-200">Numbers to `long` or `double`</span></span>
* <span data-ttu-id="88ef7-201">Даты для `DateTime`</span><span class="sxs-lookup"><span data-stu-id="88ef7-201">Dates to `DateTime`</span></span>
* <span data-ttu-id="88ef7-202">Строки для `string`</span><span class="sxs-lookup"><span data-stu-id="88ef7-202">Strings to `string`</span></span>
* <span data-ttu-id="88ef7-203">Все остальное для `JsonElement`</span><span class="sxs-lookup"><span data-stu-id="88ef7-203">Everything else to `JsonElement`</span></span>

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

<span data-ttu-id="88ef7-204">Следующий код регистрирует преобразователь:</span><span class="sxs-lookup"><span data-stu-id="88ef7-204">The following code registers the converter:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new ObjectToInferredTypesConverter());
```

<span data-ttu-id="88ef7-205">Ниже приведен пример типа со свойством объекта:</span><span class="sxs-lookup"><span data-stu-id="88ef7-205">Here's an example type with an Object property:</span></span>

```csharp
public class WeatherForecastWithObjectProperties
{
    public object Date { get; set; }
    public object TemperatureC { get; set; }
    public object Summary { get; set; }
}
```

<span data-ttu-id="88ef7-206">Следующий пример JSON для десериализации содержит значения, которые будут десериализованы как `DateTime`, `long`и `string`:</span><span class="sxs-lookup"><span data-stu-id="88ef7-206">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="88ef7-207">Без пользовательского преобразователя десериализация помещает `JsonElement` в каждое свойство.</span><span class="sxs-lookup"><span data-stu-id="88ef7-207">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="88ef7-208">В [папке Unit Tests](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) в пространстве имен `System.Text.Json.Serialization` есть дополнительные примеры пользовательских преобразователей, которые обрабатывали свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="88ef7-208">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to Object properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="88ef7-209">Словарь поддержки с ключом, не являющимся строкой</span><span class="sxs-lookup"><span data-stu-id="88ef7-209">Support Dictionary with non-string key</span></span>

<span data-ttu-id="88ef7-210">Встроенная поддержка коллекций словаря предназначена для `Dictionary<string, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="88ef7-210">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="88ef7-211">То есть ключ должен быть строкой.</span><span class="sxs-lookup"><span data-stu-id="88ef7-211">That is, the key must be a string.</span></span> <span data-ttu-id="88ef7-212">Для поддержки словаря с целым числом или другим типом в качестве ключа требуется пользовательский преобразователь.</span><span class="sxs-lookup"><span data-stu-id="88ef7-212">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="88ef7-213">В следующем коде показан пользовательский преобразователь, работающий с `Dictionary<Enum,TValue>`:</span><span class="sxs-lookup"><span data-stu-id="88ef7-213">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

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

<span data-ttu-id="88ef7-214">Следующий код регистрирует преобразователь:</span><span class="sxs-lookup"><span data-stu-id="88ef7-214">The following code registers the converter:</span></span>

```csharp
var serializeOptions = new JsonSerializerOptions();
serializeOptions.Converters.Add(new ConverterDictionaryTKeyEnumTValue());
```

<span data-ttu-id="88ef7-215">Преобразователь может сериализовать и десериализовать свойство `TemperatureRanges` следующего класса, который использует следующие `Enum`:</span><span class="sxs-lookup"><span data-stu-id="88ef7-215">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

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

<span data-ttu-id="88ef7-216">Выходные данные JSON из сериализации выглядят, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="88ef7-216">The JSON output from serialization looks like the following example:</span></span>

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

<span data-ttu-id="88ef7-217">В [папке Unit Tests](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) в пространстве имен `System.Text.Json.Serialization` есть дополнительные примеры пользовательских преобразователей, обрабатывающих словари, не являющиеся строковыми.</span><span class="sxs-lookup"><span data-stu-id="88ef7-217">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="88ef7-218">Поддержка полиморфизма</span><span class="sxs-lookup"><span data-stu-id="88ef7-218">Support polymorphic deserialization</span></span>

<span data-ttu-id="88ef7-219">Для сериализации с помощью [полиморфизма](system-text-json-how-to.md#serialize-properties-of-derived-classes) не требуется пользовательский преобразователь, но для десериализации требуется пользовательский преобразователь.</span><span class="sxs-lookup"><span data-stu-id="88ef7-219">[Polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) doesn't require a custom converter, but deserialization does require a custom converter.</span></span>

<span data-ttu-id="88ef7-220">Предположим, например, что имеется `Person` абстрактный базовый класс с `Employee` и `Customer` производными классами.</span><span class="sxs-lookup"><span data-stu-id="88ef7-220">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="88ef7-221">Полиморфизм десериализации означает, что во время разработки можно указать `Person` в качестве цели десериализации, а `Customer` и `Employee` объекты в JSON правильно десериализовать во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="88ef7-221">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at runtime.</span></span> <span data-ttu-id="88ef7-222">Во время десериализации необходимо найти подсказки, которые указывают требуемый тип в JSON.</span><span class="sxs-lookup"><span data-stu-id="88ef7-222">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="88ef7-223">В каждом сценарии доступны различные виды подкатегории.</span><span class="sxs-lookup"><span data-stu-id="88ef7-223">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="88ef7-224">Например, может быть доступно свойство дискриминатора, или может потребоваться полагаться на присутствие или отсутствие конкретного свойства.</span><span class="sxs-lookup"><span data-stu-id="88ef7-224">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="88ef7-225">В текущем выпуске `System.Text.Json` не предоставлены атрибуты для указания способов управления сценариями десериализации, поэтому требуются пользовательские преобразователи.</span><span class="sxs-lookup"><span data-stu-id="88ef7-225">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="88ef7-226">В следующем коде показан базовый класс, два производных класса и пользовательский преобразователь для них.</span><span class="sxs-lookup"><span data-stu-id="88ef7-226">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="88ef7-227">Преобразователь использует свойство дискриминатора для преобразования в полиморфизм.</span><span class="sxs-lookup"><span data-stu-id="88ef7-227">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="88ef7-228">Дискриминатор типа не находится в определениях классов, но создается во время сериализации и считывается во время десериализации.</span><span class="sxs-lookup"><span data-stu-id="88ef7-228">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

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

<span data-ttu-id="88ef7-229">Следующий код регистрирует преобразователь:</span><span class="sxs-lookup"><span data-stu-id="88ef7-229">The following code registers the converter:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new PersonConverterWithTypeDiscriminator());
```

<span data-ttu-id="88ef7-230">Преобразователь может десериализовать JSON, созданный с помощью того же преобразователя, для сериализации, например:</span><span class="sxs-lookup"><span data-stu-id="88ef7-230">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

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

## <a name="other-custom-converter-samples"></a><span data-ttu-id="88ef7-231">Другие примеры пользовательских преобразователей</span><span class="sxs-lookup"><span data-stu-id="88ef7-231">Other custom converter samples</span></span>

<span data-ttu-id="88ef7-232">[Папка Unit Tests](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) в исходном коде `System.Text.Json.Serialization` содержит другие примеры пользовательских преобразователей, например:</span><span class="sxs-lookup"><span data-stu-id="88ef7-232">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="88ef7-233">преобразователь `Int32`, который преобразует значение NULL в 0 при десериализации</span><span class="sxs-lookup"><span data-stu-id="88ef7-233">`Int32` converter that converts null to 0 on deserialize</span></span>
* <span data-ttu-id="88ef7-234">преобразователь `Int32`, допускающий строковые и числовые значения при десериализации</span><span class="sxs-lookup"><span data-stu-id="88ef7-234">`Int32` converter that allows both string and number values on deserialize</span></span>
* <span data-ttu-id="88ef7-235">преобразователь `Enum`</span><span class="sxs-lookup"><span data-stu-id="88ef7-235">`Enum` converter</span></span>
* <span data-ttu-id="88ef7-236">преобразователь `List<T>`, принимающий внешние данные</span><span class="sxs-lookup"><span data-stu-id="88ef7-236">`List<T>` converter that accepts external data</span></span>
* <span data-ttu-id="88ef7-237">преобразователь `Long[]`, который работает с разделенным запятыми списком чисел</span><span class="sxs-lookup"><span data-stu-id="88ef7-237">`Long[]` converter that works with a comma-delimited list of numbers</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="88ef7-238">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="88ef7-238">Additional resources</span></span>

* [<span data-ttu-id="88ef7-239">Общие сведения о System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="88ef7-239">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="88ef7-240">Справочник по API System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="88ef7-240">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="88ef7-241">Использование System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="88ef7-241">How to use System.Text.Json</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="88ef7-242">Исходный код для встроенных преобразователей</span><span class="sxs-lookup"><span data-stu-id="88ef7-242">Source code for built-in converters</span></span>](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/)
* <span data-ttu-id="88ef7-243">Проблемы GitHub, связанные с пользовательскими преобразователями для `System.Text.Json`</span><span class="sxs-lookup"><span data-stu-id="88ef7-243">GitHub issues related to custom converters for `System.Text.Json`</span></span>
  * [<span data-ttu-id="88ef7-244">36639. Введение в пользовательские конвертеры</span><span class="sxs-lookup"><span data-stu-id="88ef7-244">36639 Introducing custom converters</span></span>](https://github.com/dotnet/corefx/issues/36639)
  * [<span data-ttu-id="88ef7-245">38713 о десериализации в объект</span><span class="sxs-lookup"><span data-stu-id="88ef7-245">38713 About deserializing to Object</span></span>](https://github.com/dotnet/corefx/issues/38713)
  * [<span data-ttu-id="88ef7-246">40120 о словарях, не являющихся строковыми ключами</span><span class="sxs-lookup"><span data-stu-id="88ef7-246">40120 About non-string-key dictionaries</span></span>](https://github.com/dotnet/corefx/issues/40120)
  * [<span data-ttu-id="88ef7-247">37787 о полиморфизме</span><span class="sxs-lookup"><span data-stu-id="88ef7-247">37787 About polymorphic deserialization</span></span>](https://github.com/dotnet/corefx/issues/37787)
