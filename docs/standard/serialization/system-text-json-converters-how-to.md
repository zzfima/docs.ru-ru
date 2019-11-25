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
ms.openlocfilehash: 33d1cd7764e71d9e2fa382c9f3c5feb77e8defb4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283351"
---
# <a name="how-to-write-custom-converters-for-json-serialization-in-net"></a><span data-ttu-id="975f0-102">Написание пользовательских преобразователей для сериализации JSON в .NET</span><span class="sxs-lookup"><span data-stu-id="975f0-102">How to write custom converters for JSON serialization in .NET</span></span>

<span data-ttu-id="975f0-103">В этой статье показано, как создать пользовательские преобразователи для классов сериализации JSON, предоставляемых в пространстве имен <xref:System.Text.Json>.</span><span class="sxs-lookup"><span data-stu-id="975f0-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span></span> <span data-ttu-id="975f0-104">Общие сведения о `System.Text.Json`см. [в статье сериализация и десериализация JSON в .NET](system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="975f0-104">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="975f0-105">*Преобразователь* — это класс, который преобразует объект или значение в JSON и обратно.</span><span class="sxs-lookup"><span data-stu-id="975f0-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="975f0-106">Пространство имен `System.Text.Json` содержит встроенные преобразователи для большинства типов-примитивов, которые сопоставляются с примитивами JavaScript.</span><span class="sxs-lookup"><span data-stu-id="975f0-106">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="975f0-107">Вы можете создавать пользовательские преобразователи:</span><span class="sxs-lookup"><span data-stu-id="975f0-107">You can write custom converters:</span></span>

* <span data-ttu-id="975f0-108">Переопределение поведения по умолчанию встроенного преобразователя.</span><span class="sxs-lookup"><span data-stu-id="975f0-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="975f0-109">Например, может потребоваться, чтобы `DateTime` значения были представлены в формате мм/дд/гггг вместо формата ISO 8601-1:2019 по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="975f0-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="975f0-110">Для поддержки пользовательского типа значения.</span><span class="sxs-lookup"><span data-stu-id="975f0-110">To support a custom value type.</span></span> <span data-ttu-id="975f0-111">Например, структура `PhoneNumber`.</span><span class="sxs-lookup"><span data-stu-id="975f0-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="975f0-112">Можно также написать пользовательские преобразователи для расширения `System.Text.Json` с функциональностью, не входящей в текущий выпуск.</span><span class="sxs-lookup"><span data-stu-id="975f0-112">You can also write custom converters to extend `System.Text.Json` with functionality not included in the current release.</span></span> <span data-ttu-id="975f0-113">Далее в этой статье рассматриваются следующие сценарии.</span><span class="sxs-lookup"><span data-stu-id="975f0-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="975f0-114">[Десериализация выводимых типов в свойства объекта](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="975f0-114">[Deserialize inferred types to Object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="975f0-115">[Словарь поддержки с ключом, не являющимся строкой](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="975f0-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="975f0-116">[Поддержка полиморфизма](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="975f0-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="975f0-117">Пользовательские шаблоны преобразователя</span><span class="sxs-lookup"><span data-stu-id="975f0-117">Custom converter patterns</span></span>

<span data-ttu-id="975f0-118">Существует два шаблона создания пользовательского преобразователя: базовый шаблон и шаблон фабрики.</span><span class="sxs-lookup"><span data-stu-id="975f0-118">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="975f0-119">Шаблон фабрики предназначен для преобразователей, обрабатывающих `Enum` типов или открытых универсальных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="975f0-119">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="975f0-120">Базовый шаблон предназначен для неуниверсальных и закрытых универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="975f0-120">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="975f0-121">Например, для преобразователей следующих типов требуется шаблон фабрики:</span><span class="sxs-lookup"><span data-stu-id="975f0-121">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="975f0-122">Ниже приведены некоторые примеры типов, которые могут быть обработаны базовым шаблоном.</span><span class="sxs-lookup"><span data-stu-id="975f0-122">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="975f0-123">Базовый шаблон создает класс, который может работать с одним типом.</span><span class="sxs-lookup"><span data-stu-id="975f0-123">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="975f0-124">Шаблон фабрики создает класс, который определяет в среде выполнения, какой необходим конкретный тип, и динамически создает соответствующий преобразователь.</span><span class="sxs-lookup"><span data-stu-id="975f0-124">The factory pattern creates a class that determines at runtime which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="975f0-125">Образец базового преобразователя</span><span class="sxs-lookup"><span data-stu-id="975f0-125">Sample basic converter</span></span>

<span data-ttu-id="975f0-126">Следующий пример представляет собой преобразователь, который переопределяет сериализацию по умолчанию для существующего типа данных.</span><span class="sxs-lookup"><span data-stu-id="975f0-126">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="975f0-127">Для `DateTimeOffset` свойств преобразователь использует формат мм/дд/гггг.</span><span class="sxs-lookup"><span data-stu-id="975f0-127">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="975f0-128">Образец преобразователя шаблона фабрики</span><span class="sxs-lookup"><span data-stu-id="975f0-128">Sample factory pattern converter</span></span>

<span data-ttu-id="975f0-129">В следующем коде показан пользовательский преобразователь, работающий с `Dictionary<Enum,TValue>`.</span><span class="sxs-lookup"><span data-stu-id="975f0-129">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="975f0-130">Код соответствует шаблону фабрики, так как первый параметр универсального типа является `Enum`, а второй — открытым.</span><span class="sxs-lookup"><span data-stu-id="975f0-130">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="975f0-131">Метод `CanConvert` возвращает `true` только для `Dictionary` с двумя универсальными параметрами, первый из которых является типом `Enum`.</span><span class="sxs-lookup"><span data-stu-id="975f0-131">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="975f0-132">Внутренний преобразователь получает существующий преобразователь для работы с любым типом, предоставленным во время выполнения для `TValue`.</span><span class="sxs-lookup"><span data-stu-id="975f0-132">The inner converter gets an existing converter to handle whichever type is provided at runtime for `TValue`.</span></span> 

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="975f0-133">Приведенный выше код аналогичен приведенному в [словаре поддержки с ключом, не являющимся строкой](#support-dictionary-with-non-string-key) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="975f0-133">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="975f0-134">Шаги по базовому шаблону</span><span class="sxs-lookup"><span data-stu-id="975f0-134">Steps to follow the basic pattern</span></span>

<span data-ttu-id="975f0-135">Ниже описано, как создать преобразователь, следуя базовому шаблону.</span><span class="sxs-lookup"><span data-stu-id="975f0-135">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="975f0-136">Создайте класс, производный от <xref:System.Text.Json.Serialization.JsonConverter%601>, где `T` — это тип для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="975f0-136">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="975f0-137">Переопределите метод `Read`, чтобы десериализовать входящий JSON и преобразовать его в тип `T`.</span><span class="sxs-lookup"><span data-stu-id="975f0-137">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="975f0-138">Используйте <xref:System.Text.Json.Utf8JsonReader>, передаваемый в метод для чтения JSON.</span><span class="sxs-lookup"><span data-stu-id="975f0-138">Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="975f0-139">Переопределите метод `Write`, чтобы сериализовать входящий объект типа `T`.</span><span class="sxs-lookup"><span data-stu-id="975f0-139">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="975f0-140">Используйте <xref:System.Text.Json.Utf8JsonWriter>, передаваемый в метод для записи JSON.</span><span class="sxs-lookup"><span data-stu-id="975f0-140">Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="975f0-141">Переопределяйте метод `CanConvert` только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="975f0-141">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="975f0-142">Реализация по умолчанию возвращает `true`, если тип для преобразования имеет тип `T`.</span><span class="sxs-lookup"><span data-stu-id="975f0-142">The default implementation returns `true` when the type to convert is type `T`.</span></span> <span data-ttu-id="975f0-143">Поэтому для преобразователей, поддерживающих только тип `T` не требуется переопределять этот метод.</span><span class="sxs-lookup"><span data-stu-id="975f0-143">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="975f0-144">Пример преобразователя, в котором требуется переопределить этот метод, см. в подразделе « [полиморфизм десериализации](#support-polymorphic-deserialization) » далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="975f0-144">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="975f0-145">В качестве эталонных реализаций для написания пользовательских преобразователей можно обратиться к [исходному коду встроенных преобразователей](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/) .</span><span class="sxs-lookup"><span data-stu-id="975f0-145">You can refer to the [built-in converters source code](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="975f0-146">Действия по шаблону фабрики</span><span class="sxs-lookup"><span data-stu-id="975f0-146">Steps to follow the factory pattern</span></span>

<span data-ttu-id="975f0-147">Ниже описано, как создать преобразователь, следуя шаблону фабрики.</span><span class="sxs-lookup"><span data-stu-id="975f0-147">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="975f0-148">Создайте класс, наследующий от класса <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span><span class="sxs-lookup"><span data-stu-id="975f0-148">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="975f0-149">Переопределите метод `CanConvert`, чтобы он возвращал значение true, если преобразуемый тип является одним, который может быть преобразован преобразователем.</span><span class="sxs-lookup"><span data-stu-id="975f0-149">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="975f0-150">Например, если преобразователь предназначен для `List<T>` он может работать только с `List<int>`, `List<string>`и `List<DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="975f0-150">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span> 
* <span data-ttu-id="975f0-151">Переопределите метод `CreateConverter`, чтобы он возвращал экземпляр класса преобразователя, обрабатывающего тип для преобразования, который будет предоставлен во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="975f0-151">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at runtime.</span></span>
* <span data-ttu-id="975f0-152">Создайте класс преобразователя, который создает экземпляр метода `CreateConverter`.</span><span class="sxs-lookup"><span data-stu-id="975f0-152">Create the converter class that the `CreateConverter` method instantiates.</span></span> 

<span data-ttu-id="975f0-153">Шаблон фабрики необходим для открытых универсальных шаблонов, поскольку код для преобразования объекта в строку и из строки не совпадает для всех типов.</span><span class="sxs-lookup"><span data-stu-id="975f0-153">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="975f0-154">Преобразователь для открытого универсального типа (например,`List<T>`) должен создать преобразователь для закрытого универсального типа (например,`List<DateTime>`) в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="975f0-154">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="975f0-155">Необходимо написать код для работы с каждым закрытым универсальным типом, который может обрабатываться преобразователем.</span><span class="sxs-lookup"><span data-stu-id="975f0-155">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="975f0-156">Тип `Enum` похож на открытый универсальный тип: преобразователь для `Enum` должен создать преобразователь для определенного `Enum` (например,`WeekdaysEnum`) в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="975f0-156">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span> 

## <a name="error-handling"></a><span data-ttu-id="975f0-157">Обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="975f0-157">Error handling</span></span>

<span data-ttu-id="975f0-158">Если необходимо создать исключение в коде обработки ошибок, рассмотрите возможность создания <xref:System.Text.Json.JsonException> без сообщения.</span><span class="sxs-lookup"><span data-stu-id="975f0-158">If you need to throw an exception in error-handling code, consider throwing a <xref:System.Text.Json.JsonException> without a message.</span></span> <span data-ttu-id="975f0-159">Этот тип исключения автоматически создает сообщение, содержащее путь к части JSON, вызвавшей ошибку.</span><span class="sxs-lookup"><span data-stu-id="975f0-159">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="975f0-160">Например, инструкция `throw new JsonException();` выдает сообщение об ошибке, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="975f0-160">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="975f0-161">Если вы выдаете сообщение (например, `throw new JsonException("Error occurred")`, исключение по-прежнему предоставляет путь в свойстве <xref:System.Text.Json.JsonException.Path>.</span><span class="sxs-lookup"><span data-stu-id="975f0-161">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the exception still provides the path in the <xref:System.Text.Json.JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="975f0-162">Регистрация пользовательского преобразователя</span><span class="sxs-lookup"><span data-stu-id="975f0-162">Register a custom converter</span></span>

<span data-ttu-id="975f0-163">*Зарегистрируйте* пользовательский преобразователь, чтобы методы `Serialize` и `Deserialize` использовали его.</span><span class="sxs-lookup"><span data-stu-id="975f0-163">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="975f0-164">Выберите один из следующих подходов:</span><span class="sxs-lookup"><span data-stu-id="975f0-164">Choose one of the following approaches:</span></span>

* <span data-ttu-id="975f0-165">Добавьте экземпляр класса преобразователя в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="975f0-165">Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="975f0-166">Примените атрибут [[жсонконвертер]](xref:System.Text.Json.Serialization.JsonConverterAttribute) к свойствам, для которых требуется пользовательский преобразователь.</span><span class="sxs-lookup"><span data-stu-id="975f0-166">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="975f0-167">Примените атрибут [[жсонконвертер]](xref:System.Text.Json.Serialization.JsonConverterAttribute) к классу или структуре, представляющей пользовательский тип значения.</span><span class="sxs-lookup"><span data-stu-id="975f0-167">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="975f0-168">Пример регистрации — Коллекция преобразователей</span><span class="sxs-lookup"><span data-stu-id="975f0-168">Registration sample - Converters collection</span></span> 

<span data-ttu-id="975f0-169">Ниже приведен пример, который делает <xref:System.ComponentModel.DateTimeOffsetConverter> по умолчанию для свойств типа <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="975f0-169">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

<span data-ttu-id="975f0-170">Предположим, что Вы сериализуете экземпляр следующего типа:</span><span class="sxs-lookup"><span data-stu-id="975f0-170">Suppose you serialize an instance of the following type:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="975f0-171">Ниже приведен пример выходных данных JSON, демонстрирующий использование пользовательского преобразователя.</span><span class="sxs-lookup"><span data-stu-id="975f0-171">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="975f0-172">Следующий код использует тот же подход для десериализации с помощью пользовательского преобразователя `DateTimeOffset`:</span><span class="sxs-lookup"><span data-stu-id="975f0-172">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="975f0-173">Пример регистрации-[Жсонконвертер] для свойства</span><span class="sxs-lookup"><span data-stu-id="975f0-173">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="975f0-174">Следующий код выбирает пользовательский преобразователь для свойства `Date`:</span><span class="sxs-lookup"><span data-stu-id="975f0-174">The following code selects a custom converter for the `Date` property:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

<span data-ttu-id="975f0-175">Код для сериализации `WeatherForecastWithConverterAttribute` не требует использования `JsonSerializeOptions.Converters`:</span><span class="sxs-lookup"><span data-stu-id="975f0-175">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

<span data-ttu-id="975f0-176">Код для десериализации также не требует использования `Converters`:</span><span class="sxs-lookup"><span data-stu-id="975f0-176">The code to deserialize also doesn't require the use of `Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="975f0-177">Пример регистрации-[Жсонконвертер] для типа</span><span class="sxs-lookup"><span data-stu-id="975f0-177">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="975f0-178">Вот код, создающий структуру и применяющий к нему атрибут `[JsonConverter]`:</span><span class="sxs-lookup"><span data-stu-id="975f0-178">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Temperature.cs)]

<span data-ttu-id="975f0-179">Вот пользовательский преобразователь для предыдущей структуры:</span><span class="sxs-lookup"><span data-stu-id="975f0-179">Here's the custom converter for the preceding struct:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/TemperatureConverter.cs)]

<span data-ttu-id="975f0-180">Атрибут `[JsonConvert]` в структуре регистрирует пользовательский преобразователь в качестве значения по умолчанию для свойств типа `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="975f0-180">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="975f0-181">Этот преобразователь автоматически используется в свойстве `TemperatureCelsius` следующего типа при сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="975f0-181">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a><span data-ttu-id="975f0-182">Приоритет регистрации преобразователя</span><span class="sxs-lookup"><span data-stu-id="975f0-182">Converter registration precedence</span></span>

<span data-ttu-id="975f0-183">Во время сериализации или десериализации выбирается преобразователь для каждого элемента JSON в следующем порядке, в котором в списке от наивысшего приоритета к наименьшему:</span><span class="sxs-lookup"><span data-stu-id="975f0-183">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="975f0-184">`[JsonConverter]` применено к свойству.</span><span class="sxs-lookup"><span data-stu-id="975f0-184">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="975f0-185">Преобразователь, добавленный в коллекцию `Converters`.</span><span class="sxs-lookup"><span data-stu-id="975f0-185">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="975f0-186">`[JsonConverter]` применяется к пользовательскому типу значения или POCO.</span><span class="sxs-lookup"><span data-stu-id="975f0-186">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="975f0-187">Если в коллекции `Converters` зарегистрировано несколько пользовательских преобразователей, то используется первый преобразователь, возвращающий значение true для `CanConvert`.</span><span class="sxs-lookup"><span data-stu-id="975f0-187">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="975f0-188">Встроенный преобразователь выбирается только в том случае, если соответствующий пользовательский преобразователь не зарегистрирован.</span><span class="sxs-lookup"><span data-stu-id="975f0-188">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="975f0-189">Примеры преобразователей для распространенных сценариев</span><span class="sxs-lookup"><span data-stu-id="975f0-189">Converter samples for common scenarios</span></span>

<span data-ttu-id="975f0-190">В следующих разделах приведены примеры преобразователей, в которых рассматриваются некоторые распространенные сценарии, которые не обрабатывались встроенными функциями.</span><span class="sxs-lookup"><span data-stu-id="975f0-190">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

* [<span data-ttu-id="975f0-191">Десериализация выводимых типов в свойства объекта</span><span class="sxs-lookup"><span data-stu-id="975f0-191">Deserialize inferred types to Object properties</span></span>](#deserialize-inferred-types-to-object-properties)
* [<span data-ttu-id="975f0-192">Словарь поддержки с ключом, не являющимся строкой</span><span class="sxs-lookup"><span data-stu-id="975f0-192">Support Dictionary with non-string key</span></span>](#support-dictionary-with-non-string-key)
* [<span data-ttu-id="975f0-193">Поддержка полиморфизма</span><span class="sxs-lookup"><span data-stu-id="975f0-193">Support polymorphic deserialization</span></span>](#support-polymorphic-deserialization)

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="975f0-194">Десериализация выводимых типов в свойства объекта</span><span class="sxs-lookup"><span data-stu-id="975f0-194">Deserialize inferred types to Object properties</span></span>

<span data-ttu-id="975f0-195">При десериализации свойства типа `Object`создается объект `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="975f0-195">When deserializing to a property of type `Object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="975f0-196">Причина заключается в том, что десериализатор не знает, какой тип CLR создать, и не пытается угадать.</span><span class="sxs-lookup"><span data-stu-id="975f0-196">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="975f0-197">Например, если свойство JSON имеет значение "true", десериализатор не определит, что значение является `Boolean`, а если у элемента есть "01/01/2019", десериализатор не определит, что это `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="975f0-197">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="975f0-198">Вывод типа может быть неточным.</span><span class="sxs-lookup"><span data-stu-id="975f0-198">Type inference can be inaccurate.</span></span> <span data-ttu-id="975f0-199">Если десериализатор анализирует номер JSON, не имеющий десятичного разделителя, в качестве `long`, это может привести к проблемам вне диапазона, если значение первоначально было сериализовано как `ulong` или `BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="975f0-199">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="975f0-200">Анализ числа с десятичной запятой в качестве `double` может привести к потере точности, если это число было первоначально сериализовано как `decimal`.</span><span class="sxs-lookup"><span data-stu-id="975f0-200">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="975f0-201">В сценариях, требующих вывода типа, в следующем коде показан пользовательский преобразователь для `Object` свойств.</span><span class="sxs-lookup"><span data-stu-id="975f0-201">For scenarios that require type inference, the following code shows a custom converter for `Object` properties.</span></span> <span data-ttu-id="975f0-202">Код преобразует:</span><span class="sxs-lookup"><span data-stu-id="975f0-202">The code converts:</span></span>

* <span data-ttu-id="975f0-203">`true` и `false` `Boolean`</span><span class="sxs-lookup"><span data-stu-id="975f0-203">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="975f0-204">Числа для `long` или `double`</span><span class="sxs-lookup"><span data-stu-id="975f0-204">Numbers to `long` or `double`</span></span>
* <span data-ttu-id="975f0-205">Даты для `DateTime`</span><span class="sxs-lookup"><span data-stu-id="975f0-205">Dates to `DateTime`</span></span>
* <span data-ttu-id="975f0-206">Строки для `string`</span><span class="sxs-lookup"><span data-stu-id="975f0-206">Strings to `string`</span></span>
* <span data-ttu-id="975f0-207">Все остальное для `JsonElement`</span><span class="sxs-lookup"><span data-stu-id="975f0-207">Everything else to `JsonElement`</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

<span data-ttu-id="975f0-208">Следующий код регистрирует преобразователь:</span><span class="sxs-lookup"><span data-stu-id="975f0-208">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertInferredTypesToObject.cs?name=SnippetRegister)]

<span data-ttu-id="975f0-209">Ниже приведен пример типа с `Object` свойствами.</span><span class="sxs-lookup"><span data-stu-id="975f0-209">Here's an example type with `Object` properties:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

<span data-ttu-id="975f0-210">Следующий пример JSON для десериализации содержит значения, которые будут десериализованы как `DateTime`, `long`и `string`:</span><span class="sxs-lookup"><span data-stu-id="975f0-210">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="975f0-211">Без пользовательского преобразователя десериализация помещает `JsonElement` в каждое свойство.</span><span class="sxs-lookup"><span data-stu-id="975f0-211">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="975f0-212">В [папке Unit Tests](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) в пространстве имен `System.Text.Json.Serialization` есть дополнительные примеры пользовательских преобразователей, которые обрабатывали свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="975f0-212">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to Object properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="975f0-213">Словарь поддержки с ключом, не являющимся строкой</span><span class="sxs-lookup"><span data-stu-id="975f0-213">Support Dictionary with non-string key</span></span>

<span data-ttu-id="975f0-214">Встроенная поддержка коллекций словаря предназначена для `Dictionary<string, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="975f0-214">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="975f0-215">То есть ключ должен быть строкой.</span><span class="sxs-lookup"><span data-stu-id="975f0-215">That is, the key must be a string.</span></span> <span data-ttu-id="975f0-216">Для поддержки словаря с целым числом или другим типом в качестве ключа требуется пользовательский преобразователь.</span><span class="sxs-lookup"><span data-stu-id="975f0-216">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="975f0-217">В следующем коде показан пользовательский преобразователь, работающий с `Dictionary<Enum,TValue>`:</span><span class="sxs-lookup"><span data-stu-id="975f0-217">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="975f0-218">Следующий код регистрирует преобразователь:</span><span class="sxs-lookup"><span data-stu-id="975f0-218">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

<span data-ttu-id="975f0-219">Преобразователь может сериализовать и десериализовать свойство `TemperatureRanges` следующего класса, который использует следующие `Enum`:</span><span class="sxs-lookup"><span data-stu-id="975f0-219">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

<span data-ttu-id="975f0-220">Выходные данные JSON из сериализации выглядят, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="975f0-220">The JSON output from serialization looks like the following example:</span></span>

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

<span data-ttu-id="975f0-221">В [папке Unit Tests](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) в пространстве имен `System.Text.Json.Serialization` есть дополнительные примеры пользовательских преобразователей, обрабатывающих словари, не являющиеся строковыми.</span><span class="sxs-lookup"><span data-stu-id="975f0-221">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="975f0-222">Поддержка полиморфизма</span><span class="sxs-lookup"><span data-stu-id="975f0-222">Support polymorphic deserialization</span></span>

<span data-ttu-id="975f0-223">Для сериализации с помощью [полиморфизма](system-text-json-how-to.md#serialize-properties-of-derived-classes) не требуется пользовательский преобразователь, но для десериализации требуется пользовательский преобразователь.</span><span class="sxs-lookup"><span data-stu-id="975f0-223">[Polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) doesn't require a custom converter, but deserialization does require a custom converter.</span></span>

<span data-ttu-id="975f0-224">Предположим, например, что имеется `Person` абстрактный базовый класс с `Employee` и `Customer` производными классами.</span><span class="sxs-lookup"><span data-stu-id="975f0-224">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="975f0-225">Полиморфизм десериализации означает, что во время разработки можно указать `Person` в качестве цели десериализации, а `Customer` и `Employee` объекты в JSON правильно десериализовать во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="975f0-225">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at runtime.</span></span> <span data-ttu-id="975f0-226">Во время десериализации необходимо найти подсказки, которые указывают требуемый тип в JSON.</span><span class="sxs-lookup"><span data-stu-id="975f0-226">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="975f0-227">В каждом сценарии доступны различные виды подкатегории.</span><span class="sxs-lookup"><span data-stu-id="975f0-227">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="975f0-228">Например, может быть доступно свойство дискриминатора, или может потребоваться полагаться на присутствие или отсутствие конкретного свойства.</span><span class="sxs-lookup"><span data-stu-id="975f0-228">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="975f0-229">В текущем выпуске `System.Text.Json` не предоставлены атрибуты для указания способов управления сценариями десериализации, поэтому требуются пользовательские преобразователи.</span><span class="sxs-lookup"><span data-stu-id="975f0-229">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="975f0-230">В следующем коде показан базовый класс, два производных класса и пользовательский преобразователь для них.</span><span class="sxs-lookup"><span data-stu-id="975f0-230">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="975f0-231">Преобразователь использует свойство дискриминатора для преобразования в полиморфизм.</span><span class="sxs-lookup"><span data-stu-id="975f0-231">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="975f0-232">Дискриминатор типа не находится в определениях классов, но создается во время сериализации и считывается во время десериализации.</span><span class="sxs-lookup"><span data-stu-id="975f0-232">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

<span data-ttu-id="975f0-233">Следующий код регистрирует преобразователь:</span><span class="sxs-lookup"><span data-stu-id="975f0-233">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertPolymorphic.cs?name=SnippetRegister)]

<span data-ttu-id="975f0-234">Преобразователь может десериализовать JSON, созданный с помощью того же преобразователя, для сериализации, например:</span><span class="sxs-lookup"><span data-stu-id="975f0-234">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

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

## <a name="other-custom-converter-samples"></a><span data-ttu-id="975f0-235">Другие примеры пользовательских преобразователей</span><span class="sxs-lookup"><span data-stu-id="975f0-235">Other custom converter samples</span></span>

<span data-ttu-id="975f0-236">[Папка Unit Tests](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) в исходном коде `System.Text.Json.Serialization` содержит другие примеры пользовательских преобразователей, например:</span><span class="sxs-lookup"><span data-stu-id="975f0-236">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="975f0-237">преобразователь `Int32`, который преобразует значение NULL в 0 при десериализации</span><span class="sxs-lookup"><span data-stu-id="975f0-237">`Int32` converter that converts null to 0 on deserialize</span></span>
* <span data-ttu-id="975f0-238">преобразователь `Int32`, допускающий строковые и числовые значения при десериализации</span><span class="sxs-lookup"><span data-stu-id="975f0-238">`Int32` converter that allows both string and number values on deserialize</span></span>
* <span data-ttu-id="975f0-239">преобразователь `Enum`</span><span class="sxs-lookup"><span data-stu-id="975f0-239">`Enum` converter</span></span>
* <span data-ttu-id="975f0-240">преобразователь `List<T>`, принимающий внешние данные</span><span class="sxs-lookup"><span data-stu-id="975f0-240">`List<T>` converter that accepts external data</span></span>
* <span data-ttu-id="975f0-241">преобразователь `Long[]`, который работает с разделенным запятыми списком чисел</span><span class="sxs-lookup"><span data-stu-id="975f0-241">`Long[]` converter that works with a comma-delimited list of numbers</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="975f0-242">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="975f0-242">Additional resources</span></span>

* [<span data-ttu-id="975f0-243">Общие сведения о System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="975f0-243">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="975f0-244">Справочник по API System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="975f0-244">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="975f0-245">Использование System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="975f0-245">How to use System.Text.Json</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="975f0-246">Исходный код для встроенных преобразователей</span><span class="sxs-lookup"><span data-stu-id="975f0-246">Source code for built-in converters</span></span>](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/)
* <span data-ttu-id="975f0-247">Проблемы GitHub, связанные с пользовательскими преобразователями для `System.Text.Json`</span><span class="sxs-lookup"><span data-stu-id="975f0-247">GitHub issues related to custom converters for `System.Text.Json`</span></span>
  * [<span data-ttu-id="975f0-248">36639. Введение в пользовательские конвертеры</span><span class="sxs-lookup"><span data-stu-id="975f0-248">36639 Introducing custom converters</span></span>](https://github.com/dotnet/corefx/issues/36639)
  * [<span data-ttu-id="975f0-249">38713 о десериализации в объект</span><span class="sxs-lookup"><span data-stu-id="975f0-249">38713 About deserializing to Object</span></span>](https://github.com/dotnet/corefx/issues/38713)
  * [<span data-ttu-id="975f0-250">40120 о словарях, не являющихся строковыми ключами</span><span class="sxs-lookup"><span data-stu-id="975f0-250">40120 About non-string-key dictionaries</span></span>](https://github.com/dotnet/corefx/issues/40120)
  * [<span data-ttu-id="975f0-251">37787 о полиморфизме</span><span class="sxs-lookup"><span data-stu-id="975f0-251">37787 About polymorphic deserialization</span></span>](https://github.com/dotnet/corefx/issues/37787)
