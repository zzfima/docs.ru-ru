---
title: How to write custom converters for JSON serialization - .NET
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: f72d2d83d701b20648140900d65c9098a8abb721
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76164064"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a><span data-ttu-id="777e9-102">How to write custom converters for JSON serialization (marshalling) in .NET</span><span class="sxs-lookup"><span data-stu-id="777e9-102">How to write custom converters for JSON serialization (marshalling) in .NET</span></span>

<span data-ttu-id="777e9-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span><span class="sxs-lookup"><span data-stu-id="777e9-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span></span> <span data-ttu-id="777e9-104">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="777e9-104">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="777e9-105">A *converter* is a class that converts an object or a value to and from JSON.</span><span class="sxs-lookup"><span data-stu-id="777e9-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="777e9-106">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span><span class="sxs-lookup"><span data-stu-id="777e9-106">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="777e9-107">You can write custom converters:</span><span class="sxs-lookup"><span data-stu-id="777e9-107">You can write custom converters:</span></span>

* <span data-ttu-id="777e9-108">To override the default behavior of a built-in converter.</span><span class="sxs-lookup"><span data-stu-id="777e9-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="777e9-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span><span class="sxs-lookup"><span data-stu-id="777e9-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="777e9-110">To support a custom value type.</span><span class="sxs-lookup"><span data-stu-id="777e9-110">To support a custom value type.</span></span> <span data-ttu-id="777e9-111">For example, a `PhoneNumber` struct.</span><span class="sxs-lookup"><span data-stu-id="777e9-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="777e9-112">You can also write custom converters to customize or extend `System.Text.Json` with functionality not included in the current release.</span><span class="sxs-lookup"><span data-stu-id="777e9-112">You can also write custom converters to customize or extend `System.Text.Json` with functionality not included in the current release.</span></span> <span data-ttu-id="777e9-113">The following scenarios are covered later in this article:</span><span class="sxs-lookup"><span data-stu-id="777e9-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="777e9-114">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="777e9-114">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="777e9-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="777e9-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="777e9-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="777e9-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="777e9-117">Custom converter patterns</span><span class="sxs-lookup"><span data-stu-id="777e9-117">Custom converter patterns</span></span>

<span data-ttu-id="777e9-118">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span><span class="sxs-lookup"><span data-stu-id="777e9-118">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="777e9-119">The factory pattern is for converters that handle type `Enum` or open generics.</span><span class="sxs-lookup"><span data-stu-id="777e9-119">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="777e9-120">The basic pattern is for non-generic and closed generic types.</span><span class="sxs-lookup"><span data-stu-id="777e9-120">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="777e9-121">For example, converters for the following types require the factory pattern:</span><span class="sxs-lookup"><span data-stu-id="777e9-121">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="777e9-122">Some examples of types that can be handled by the basic pattern include:</span><span class="sxs-lookup"><span data-stu-id="777e9-122">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="777e9-123">The basic pattern creates a class that can handle one type.</span><span class="sxs-lookup"><span data-stu-id="777e9-123">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="777e9-124">The factory pattern creates a class that determines at runtime which specific type is required and dynamically creates the appropriate converter.</span><span class="sxs-lookup"><span data-stu-id="777e9-124">The factory pattern creates a class that determines at runtime which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="777e9-125">Sample basic converter</span><span class="sxs-lookup"><span data-stu-id="777e9-125">Sample basic converter</span></span>

<span data-ttu-id="777e9-126">The following sample is a converter that overrides default serialization for an existing data type.</span><span class="sxs-lookup"><span data-stu-id="777e9-126">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="777e9-127">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span><span class="sxs-lookup"><span data-stu-id="777e9-127">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="777e9-128">Sample factory pattern converter</span><span class="sxs-lookup"><span data-stu-id="777e9-128">Sample factory pattern converter</span></span>

<span data-ttu-id="777e9-129">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span><span class="sxs-lookup"><span data-stu-id="777e9-129">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="777e9-130">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span><span class="sxs-lookup"><span data-stu-id="777e9-130">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="777e9-131">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span><span class="sxs-lookup"><span data-stu-id="777e9-131">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="777e9-132">Внутренний преобразователь получает существующий преобразователь для работы с любым типом, предоставленным во время выполнения для `TValue`.</span><span class="sxs-lookup"><span data-stu-id="777e9-132">The inner converter gets an existing converter to handle whichever type is provided at runtime for `TValue`.</span></span> 

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="777e9-133">Приведенный выше код аналогичен приведенному в [словаре поддержки с ключом, не являющимся строкой](#support-dictionary-with-non-string-key) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="777e9-133">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="777e9-134">Шаги по базовому шаблону</span><span class="sxs-lookup"><span data-stu-id="777e9-134">Steps to follow the basic pattern</span></span>

<span data-ttu-id="777e9-135">Ниже описано, как создать преобразователь, следуя базовому шаблону.</span><span class="sxs-lookup"><span data-stu-id="777e9-135">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="777e9-136">Создайте класс, производный от <xref:System.Text.Json.Serialization.JsonConverter%601>, где `T` — это тип для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="777e9-136">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="777e9-137">Переопределите метод `Read`, чтобы десериализовать входящий JSON и преобразовать его в тип `T`.</span><span class="sxs-lookup"><span data-stu-id="777e9-137">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="777e9-138">Используйте <xref:System.Text.Json.Utf8JsonReader>, передаваемый в метод для чтения JSON.</span><span class="sxs-lookup"><span data-stu-id="777e9-138">Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="777e9-139">Переопределите метод `Write`, чтобы сериализовать входящий объект типа `T`.</span><span class="sxs-lookup"><span data-stu-id="777e9-139">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="777e9-140">Используйте <xref:System.Text.Json.Utf8JsonWriter>, передаваемый в метод для записи JSON.</span><span class="sxs-lookup"><span data-stu-id="777e9-140">Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="777e9-141">Переопределяйте метод `CanConvert` только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="777e9-141">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="777e9-142">Реализация по умолчанию возвращает `true`, если тип для преобразования имеет тип `T`.</span><span class="sxs-lookup"><span data-stu-id="777e9-142">The default implementation returns `true` when the type to convert is of type `T`.</span></span> <span data-ttu-id="777e9-143">Поэтому для преобразователей, поддерживающих только тип `T` не требуется переопределять этот метод.</span><span class="sxs-lookup"><span data-stu-id="777e9-143">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="777e9-144">Пример преобразователя, в котором требуется переопределить этот метод, см. в подразделе « [полиморфизм десериализации](#support-polymorphic-deserialization) » далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="777e9-144">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="777e9-145">В качестве эталонных реализаций для написания пользовательских преобразователей можно обратиться к [исходному коду встроенных преобразователей](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) .</span><span class="sxs-lookup"><span data-stu-id="777e9-145">You can refer to the [built-in converters source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="777e9-146">Действия по шаблону фабрики</span><span class="sxs-lookup"><span data-stu-id="777e9-146">Steps to follow the factory pattern</span></span>

<span data-ttu-id="777e9-147">Ниже описано, как создать преобразователь, следуя шаблону фабрики.</span><span class="sxs-lookup"><span data-stu-id="777e9-147">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="777e9-148">Создайте класс, производный от <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span><span class="sxs-lookup"><span data-stu-id="777e9-148">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="777e9-149">Переопределите метод `CanConvert`, чтобы он возвращал значение true, если преобразуемый тип является одним, который может быть преобразован преобразователем.</span><span class="sxs-lookup"><span data-stu-id="777e9-149">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="777e9-150">Например, если преобразователь предназначен для `List<T>` он может работать только с `List<int>`, `List<string>`и `List<DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="777e9-150">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span> 
* <span data-ttu-id="777e9-151">Переопределите метод `CreateConverter`, чтобы он возвращал экземпляр класса преобразователя, обрабатывающего тип для преобразования, который будет предоставлен во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="777e9-151">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at runtime.</span></span>
* <span data-ttu-id="777e9-152">Создайте класс преобразователя, который создает экземпляр метода `CreateConverter`.</span><span class="sxs-lookup"><span data-stu-id="777e9-152">Create the converter class that the `CreateConverter` method instantiates.</span></span> 

<span data-ttu-id="777e9-153">Шаблон фабрики необходим для открытых универсальных шаблонов, поскольку код для преобразования объекта в строку и из строки не совпадает для всех типов.</span><span class="sxs-lookup"><span data-stu-id="777e9-153">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="777e9-154">Преобразователь для открытого универсального типа (например,`List<T>`) должен создать преобразователь для закрытого универсального типа (например,`List<DateTime>`) в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="777e9-154">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="777e9-155">Необходимо написать код для работы с каждым закрытым универсальным типом, который может обрабатываться преобразователем.</span><span class="sxs-lookup"><span data-stu-id="777e9-155">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="777e9-156">Тип `Enum` похож на открытый универсальный тип: преобразователь для `Enum` должен создать преобразователь для определенного `Enum` (например,`WeekdaysEnum`) в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="777e9-156">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span> 

## <a name="error-handling"></a><span data-ttu-id="777e9-157">Обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="777e9-157">Error handling</span></span>

<span data-ttu-id="777e9-158">Если необходимо создать исключение в коде обработки ошибок, рассмотрите возможность создания <xref:System.Text.Json.JsonException> без сообщения.</span><span class="sxs-lookup"><span data-stu-id="777e9-158">If you need to throw an exception in error-handling code, consider throwing a <xref:System.Text.Json.JsonException> without a message.</span></span> <span data-ttu-id="777e9-159">Этот тип исключения автоматически создает сообщение, содержащее путь к части JSON, вызвавшей ошибку.</span><span class="sxs-lookup"><span data-stu-id="777e9-159">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="777e9-160">Например, инструкция `throw new JsonException();` выдает сообщение об ошибке, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="777e9-160">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="777e9-161">Если вы выдаете сообщение (например, `throw new JsonException("Error occurred")`, исключение по-прежнему предоставляет путь в свойстве <xref:System.Text.Json.JsonException.Path>.</span><span class="sxs-lookup"><span data-stu-id="777e9-161">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the exception still provides the path in the <xref:System.Text.Json.JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="777e9-162">Регистрация пользовательского преобразователя</span><span class="sxs-lookup"><span data-stu-id="777e9-162">Register a custom converter</span></span>

<span data-ttu-id="777e9-163">*Зарегистрируйте* пользовательский преобразователь, чтобы методы `Serialize` и `Deserialize` использовали его.</span><span class="sxs-lookup"><span data-stu-id="777e9-163">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="777e9-164">Выберите один из следующих подходов:</span><span class="sxs-lookup"><span data-stu-id="777e9-164">Choose one of the following approaches:</span></span>

* <span data-ttu-id="777e9-165">Добавьте экземпляр класса преобразователя в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="777e9-165">Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="777e9-166">Примените атрибут [[жсонконвертер]](xref:System.Text.Json.Serialization.JsonConverterAttribute) к свойствам, для которых требуется пользовательский преобразователь.</span><span class="sxs-lookup"><span data-stu-id="777e9-166">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="777e9-167">Примените атрибут [[жсонконвертер]](xref:System.Text.Json.Serialization.JsonConverterAttribute) к классу или структуре, представляющей пользовательский тип значения.</span><span class="sxs-lookup"><span data-stu-id="777e9-167">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="777e9-168">Пример регистрации — Коллекция преобразователей</span><span class="sxs-lookup"><span data-stu-id="777e9-168">Registration sample - Converters collection</span></span> 

<span data-ttu-id="777e9-169">Ниже приведен пример, который делает <xref:System.ComponentModel.DateTimeOffsetConverter> по умолчанию для свойств типа <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="777e9-169">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

<span data-ttu-id="777e9-170">Предположим, что Вы сериализуете экземпляр следующего типа:</span><span class="sxs-lookup"><span data-stu-id="777e9-170">Suppose you serialize an instance of the following type:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="777e9-171">Ниже приведен пример выходных данных JSON, демонстрирующий использование пользовательского преобразователя.</span><span class="sxs-lookup"><span data-stu-id="777e9-171">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="777e9-172">Следующий код использует тот же подход для десериализации с помощью пользовательского преобразователя `DateTimeOffset`:</span><span class="sxs-lookup"><span data-stu-id="777e9-172">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="777e9-173">Пример регистрации-[Жсонконвертер] для свойства</span><span class="sxs-lookup"><span data-stu-id="777e9-173">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="777e9-174">Следующий код выбирает пользовательский преобразователь для свойства `Date`:</span><span class="sxs-lookup"><span data-stu-id="777e9-174">The following code selects a custom converter for the `Date` property:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

<span data-ttu-id="777e9-175">Код для сериализации `WeatherForecastWithConverterAttribute` не требует использования `JsonSerializeOptions.Converters`:</span><span class="sxs-lookup"><span data-stu-id="777e9-175">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

<span data-ttu-id="777e9-176">Код для десериализации также не требует использования `Converters`:</span><span class="sxs-lookup"><span data-stu-id="777e9-176">The code to deserialize also doesn't require the use of `Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="777e9-177">Пример регистрации-[Жсонконвертер] для типа</span><span class="sxs-lookup"><span data-stu-id="777e9-177">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="777e9-178">Вот код, создающий структуру и применяющий к нему атрибут `[JsonConverter]`:</span><span class="sxs-lookup"><span data-stu-id="777e9-178">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Temperature.cs)]

<span data-ttu-id="777e9-179">Вот пользовательский преобразователь для предыдущей структуры:</span><span class="sxs-lookup"><span data-stu-id="777e9-179">Here's the custom converter for the preceding struct:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/TemperatureConverter.cs)]

<span data-ttu-id="777e9-180">Атрибут `[JsonConvert]` в структуре регистрирует пользовательский преобразователь в качестве значения по умолчанию для свойств типа `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="777e9-180">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="777e9-181">Этот преобразователь автоматически используется в свойстве `TemperatureCelsius` следующего типа при сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="777e9-181">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a><span data-ttu-id="777e9-182">Приоритет регистрации преобразователя</span><span class="sxs-lookup"><span data-stu-id="777e9-182">Converter registration precedence</span></span>

<span data-ttu-id="777e9-183">Во время сериализации или десериализации выбирается преобразователь для каждого элемента JSON в следующем порядке, в котором в списке от наивысшего приоритета к наименьшему:</span><span class="sxs-lookup"><span data-stu-id="777e9-183">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="777e9-184">`[JsonConverter]` применено к свойству.</span><span class="sxs-lookup"><span data-stu-id="777e9-184">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="777e9-185">Преобразователь, добавленный в коллекцию `Converters`.</span><span class="sxs-lookup"><span data-stu-id="777e9-185">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="777e9-186">`[JsonConverter]` применяется к пользовательскому типу значения или POCO.</span><span class="sxs-lookup"><span data-stu-id="777e9-186">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="777e9-187">Если в коллекции `Converters` зарегистрировано несколько пользовательских преобразователей, то используется первый преобразователь, возвращающий значение true для `CanConvert`.</span><span class="sxs-lookup"><span data-stu-id="777e9-187">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="777e9-188">Встроенный преобразователь выбирается только в том случае, если соответствующий пользовательский преобразователь не зарегистрирован.</span><span class="sxs-lookup"><span data-stu-id="777e9-188">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="777e9-189">Примеры преобразователей для распространенных сценариев</span><span class="sxs-lookup"><span data-stu-id="777e9-189">Converter samples for common scenarios</span></span>

<span data-ttu-id="777e9-190">В следующих разделах приведены примеры преобразователей, в которых рассматриваются некоторые распространенные сценарии, которые не обрабатывались встроенными функциями.</span><span class="sxs-lookup"><span data-stu-id="777e9-190">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

* [<span data-ttu-id="777e9-191">Десериализация выводимых типов в свойства объекта</span><span class="sxs-lookup"><span data-stu-id="777e9-191">Deserialize inferred types to object properties</span></span>](#deserialize-inferred-types-to-object-properties)
* [<span data-ttu-id="777e9-192">Словарь поддержки с ключом, не являющимся строкой</span><span class="sxs-lookup"><span data-stu-id="777e9-192">Support Dictionary with non-string key</span></span>](#support-dictionary-with-non-string-key)
* [<span data-ttu-id="777e9-193">Поддержка полиморфизма</span><span class="sxs-lookup"><span data-stu-id="777e9-193">Support polymorphic deserialization</span></span>](#support-polymorphic-deserialization)

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="777e9-194">Десериализация выводимых типов в свойства объекта</span><span class="sxs-lookup"><span data-stu-id="777e9-194">Deserialize inferred types to object properties</span></span>

<span data-ttu-id="777e9-195">При десериализации свойства типа `object`создается объект `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="777e9-195">When deserializing to a property of type `object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="777e9-196">Причина заключается в том, что десериализатор не знает, какой тип CLR создать, и не пытается угадать.</span><span class="sxs-lookup"><span data-stu-id="777e9-196">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="777e9-197">Например, если свойство JSON имеет значение "true", десериализатор не определит, что значение является `Boolean`, а если у элемента есть "01/01/2019", десериализатор не определит, что это `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="777e9-197">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="777e9-198">Вывод типа может быть неточным.</span><span class="sxs-lookup"><span data-stu-id="777e9-198">Type inference can be inaccurate.</span></span> <span data-ttu-id="777e9-199">Если десериализатор анализирует номер JSON, не имеющий десятичного разделителя, в качестве `long`, это может привести к проблемам вне диапазона, если значение первоначально было сериализовано как `ulong` или `BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="777e9-199">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="777e9-200">Анализ числа с десятичной запятой в качестве `double` может привести к потере точности, если это число было первоначально сериализовано как `decimal`.</span><span class="sxs-lookup"><span data-stu-id="777e9-200">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="777e9-201">В сценариях, требующих вывода типа, в следующем коде показан пользовательский преобразователь для `object` свойств.</span><span class="sxs-lookup"><span data-stu-id="777e9-201">For scenarios that require type inference, the following code shows a custom converter for `object` properties.</span></span> <span data-ttu-id="777e9-202">Код преобразует:</span><span class="sxs-lookup"><span data-stu-id="777e9-202">The code converts:</span></span>

* <span data-ttu-id="777e9-203">`true` и `false` `Boolean`</span><span class="sxs-lookup"><span data-stu-id="777e9-203">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="777e9-204">Числа без десятичного разделителя для `long`</span><span class="sxs-lookup"><span data-stu-id="777e9-204">Numbers without a decimal to `long`</span></span>
* <span data-ttu-id="777e9-205">Числа с десятичным числом для `double`</span><span class="sxs-lookup"><span data-stu-id="777e9-205">Numbers with a decimal to `double`</span></span>
* <span data-ttu-id="777e9-206">Даты для `DateTime`</span><span class="sxs-lookup"><span data-stu-id="777e9-206">Dates to `DateTime`</span></span>
* <span data-ttu-id="777e9-207">Строки для `string`</span><span class="sxs-lookup"><span data-stu-id="777e9-207">Strings to `string`</span></span>
* <span data-ttu-id="777e9-208">Все остальное для `JsonElement`</span><span class="sxs-lookup"><span data-stu-id="777e9-208">Everything else to `JsonElement`</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

<span data-ttu-id="777e9-209">Следующий код регистрирует преобразователь:</span><span class="sxs-lookup"><span data-stu-id="777e9-209">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeInferredTypesToObject.cs?name=SnippetRegister)]

<span data-ttu-id="777e9-210">Ниже приведен пример типа с `object` свойствами.</span><span class="sxs-lookup"><span data-stu-id="777e9-210">Here's an example type with `object` properties:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

<span data-ttu-id="777e9-211">Следующий пример JSON для десериализации содержит значения, которые будут десериализованы как `DateTime`, `long`и `string`:</span><span class="sxs-lookup"><span data-stu-id="777e9-211">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="777e9-212">Без пользовательского преобразователя десериализация помещает `JsonElement` в каждое свойство.</span><span class="sxs-lookup"><span data-stu-id="777e9-212">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="777e9-213">[Папка Unit Tests](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) в пространстве имен `System.Text.Json.Serialization` содержит дополнительные примеры пользовательских преобразователей, которые обрабатывали десериализацию для `object` свойств.</span><span class="sxs-lookup"><span data-stu-id="777e9-213">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to `object` properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="777e9-214">Словарь поддержки с ключом, не являющимся строкой</span><span class="sxs-lookup"><span data-stu-id="777e9-214">Support Dictionary with non-string key</span></span>

<span data-ttu-id="777e9-215">Встроенная поддержка коллекций словаря предназначена для `Dictionary<string, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="777e9-215">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="777e9-216">То есть ключ должен быть строкой.</span><span class="sxs-lookup"><span data-stu-id="777e9-216">That is, the key must be a string.</span></span> <span data-ttu-id="777e9-217">Для поддержки словаря с целым числом или другим типом в качестве ключа требуется пользовательский преобразователь.</span><span class="sxs-lookup"><span data-stu-id="777e9-217">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="777e9-218">В следующем коде показан пользовательский преобразователь, работающий с `Dictionary<Enum,TValue>`:</span><span class="sxs-lookup"><span data-stu-id="777e9-218">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="777e9-219">Следующий код регистрирует преобразователь:</span><span class="sxs-lookup"><span data-stu-id="777e9-219">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

<span data-ttu-id="777e9-220">Преобразователь может сериализовать и десериализовать свойство `TemperatureRanges` следующего класса, который использует следующие `Enum`:</span><span class="sxs-lookup"><span data-stu-id="777e9-220">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

<span data-ttu-id="777e9-221">Выходные данные JSON из сериализации выглядят, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="777e9-221">The JSON output from serialization looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "Cold": 20,
    "Hot": 40
  }
}
```

<span data-ttu-id="777e9-222">В [папке Unit Tests](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) в пространстве имен `System.Text.Json.Serialization` есть дополнительные примеры пользовательских преобразователей, обрабатывающих словари, не являющиеся строковыми.</span><span class="sxs-lookup"><span data-stu-id="777e9-222">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="777e9-223">Поддержка полиморфизма</span><span class="sxs-lookup"><span data-stu-id="777e9-223">Support polymorphic deserialization</span></span>

<span data-ttu-id="777e9-224">Встроенные функции предоставляют ограниченный диапазон [полиморфизмной сериализации](system-text-json-how-to.md#serialize-properties-of-derived-classes) , но не поддерживают десериализацию.</span><span class="sxs-lookup"><span data-stu-id="777e9-224">Built-in features provide a limited range of [polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) but no support for deserialization at all.</span></span> <span data-ttu-id="777e9-225">Для десериализации требуется пользовательский преобразователь.</span><span class="sxs-lookup"><span data-stu-id="777e9-225">Deserialization requires a custom converter.</span></span>

<span data-ttu-id="777e9-226">Предположим, например, что имеется `Person` абстрактный базовый класс с `Employee` и `Customer` производными классами.</span><span class="sxs-lookup"><span data-stu-id="777e9-226">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="777e9-227">Полиморфизм десериализации означает, что во время разработки можно указать `Person` в качестве цели десериализации, а `Customer` и `Employee` объекты в JSON правильно десериализовать во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="777e9-227">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at runtime.</span></span> <span data-ttu-id="777e9-228">Во время десериализации необходимо найти подсказки, которые указывают требуемый тип в JSON.</span><span class="sxs-lookup"><span data-stu-id="777e9-228">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="777e9-229">В каждом сценарии доступны различные виды подкатегории.</span><span class="sxs-lookup"><span data-stu-id="777e9-229">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="777e9-230">Например, может быть доступно свойство дискриминатора, или может потребоваться полагаться на присутствие или отсутствие конкретного свойства.</span><span class="sxs-lookup"><span data-stu-id="777e9-230">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="777e9-231">В текущем выпуске `System.Text.Json` не предоставлены атрибуты для указания способов управления сценариями десериализации, поэтому требуются пользовательские преобразователи.</span><span class="sxs-lookup"><span data-stu-id="777e9-231">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="777e9-232">В следующем коде показан базовый класс, два производных класса и пользовательский преобразователь для них.</span><span class="sxs-lookup"><span data-stu-id="777e9-232">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="777e9-233">Преобразователь использует свойство дискриминатора для преобразования в полиморфизм.</span><span class="sxs-lookup"><span data-stu-id="777e9-233">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="777e9-234">Дискриминатор типа не находится в определениях классов, но создается во время сериализации и считывается во время десериализации.</span><span class="sxs-lookup"><span data-stu-id="777e9-234">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

<span data-ttu-id="777e9-235">Следующий код регистрирует преобразователь:</span><span class="sxs-lookup"><span data-stu-id="777e9-235">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPolymorphic.cs?name=SnippetRegister)]

<span data-ttu-id="777e9-236">Преобразователь может десериализовать JSON, созданный с помощью того же преобразователя, для сериализации, например:</span><span class="sxs-lookup"><span data-stu-id="777e9-236">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

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

<span data-ttu-id="777e9-237">Код преобразователя в предыдущем примере считывает и записывает каждое свойство вручную.</span><span class="sxs-lookup"><span data-stu-id="777e9-237">The converter code in the preceding example reads and writes each property manually.</span></span> <span data-ttu-id="777e9-238">Альтернативой является вызов `Deserialize` или `Serialize` для выполнения некоторой работы.</span><span class="sxs-lookup"><span data-stu-id="777e9-238">An alternative is to call `Deserialize` or `Serialize` to do some of the work.</span></span> <span data-ttu-id="777e9-239">Пример см. в [этой записи StackOverflow](https://stackoverflow.com/a/59744873/12509023).</span><span class="sxs-lookup"><span data-stu-id="777e9-239">For an example, see [this StackOverflow post](https://stackoverflow.com/a/59744873/12509023).</span></span>

## <a name="other-custom-converter-samples"></a><span data-ttu-id="777e9-240">Другие примеры пользовательских преобразователей</span><span class="sxs-lookup"><span data-stu-id="777e9-240">Other custom converter samples</span></span>

<span data-ttu-id="777e9-241">В статье [Миграция из Newtonsoft.Json в System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) содержатся дополнительные образцы пользовательских преобразователей.</span><span class="sxs-lookup"><span data-stu-id="777e9-241">The [Migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) article contains additional samples of custom converters.</span></span>

<span data-ttu-id="777e9-242">[Папка Unit Tests](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) в исходном коде `System.Text.Json.Serialization` содержит другие примеры пользовательских преобразователей, например:</span><span class="sxs-lookup"><span data-stu-id="777e9-242">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="777e9-243">[Преобразователь Int32, который преобразует значение NULL в 0 при десериализации](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span><span class="sxs-lookup"><span data-stu-id="777e9-243">[Int32 converter that converts null to 0 on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span></span>
* <span data-ttu-id="777e9-244">[Преобразователь Int32, который допускает как строковые, так и числовые значения при десериализации](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span><span class="sxs-lookup"><span data-stu-id="777e9-244">[Int32 converter that allows both string and number values on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span></span>
* <span data-ttu-id="777e9-245">[Преобразователь перечислений](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span><span class="sxs-lookup"><span data-stu-id="777e9-245">[Enum converter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span></span>
* <span data-ttu-id="777e9-246">[Перечисление\<преобразования >, принимающего внешние данные](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span><span class="sxs-lookup"><span data-stu-id="777e9-246">[List\<T> converter that accepts external data](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span></span>
* <span data-ttu-id="777e9-247">[Преобразователь long [], который работает с разделенным запятыми списком чисел](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span><span class="sxs-lookup"><span data-stu-id="777e9-247">[Long[] converter that works with a comma-delimited list of numbers](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span></span> 

<span data-ttu-id="777e9-248">Если необходимо сделать преобразователь, изменяющий поведение существующего встроенного преобразователя, можно получить [Исходный код существующего преобразователя](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) , который будет служить отправной точкой для настройки.</span><span class="sxs-lookup"><span data-stu-id="777e9-248">If you need to make a converter that modifies the behavior of an existing built-in converter, you can get [the source code of the existing converter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) to serve as a starting point for customization.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="777e9-249">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="777e9-249">Additional resources</span></span>

* <span data-ttu-id="777e9-250">[Исходный код для встроенных преобразователей](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span><span class="sxs-lookup"><span data-stu-id="777e9-250">[Source code for built-in converters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span></span>
* <span data-ttu-id="777e9-251">[Поддержка DateTime и DateTimeOffset в System.Text.Json](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="777e9-251">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="777e9-252">[Обзор System.Text.Json](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="777e9-252">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* <span data-ttu-id="777e9-253">[Использование System.Text.Json](system-text-json-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="777e9-253">[How to use System.Text.Json](system-text-json-how-to.md)</span></span>
* <span data-ttu-id="777e9-254">[Переход с Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="777e9-254">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* <span data-ttu-id="777e9-255">[Справочник по System.Text.Json API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="777e9-255">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="777e9-256">[System.Text.Json. Справочник по API сериализации](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="777e9-256">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
