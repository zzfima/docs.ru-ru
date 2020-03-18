---
title: Сообщения Protobuf - gRPC для разработчиков WCF
description: Узнайте, как сообщения Protobuf определяются в IDL и генерируются в C.
ms.date: 09/09/2019
ms.openlocfilehash: 5b3d4383de39a3785ef804fec21939a740f54669
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147988"
---
# <a name="protobuf-messages"></a><span data-ttu-id="9babd-103">Сообщения Protobuf</span><span class="sxs-lookup"><span data-stu-id="9babd-103">Protobuf messages</span></span>

<span data-ttu-id="9babd-104">В этом разделе рассказывается о том, как `.proto` декларировать сообщения Протокола буфера (Protobuf) в файлах.</span><span class="sxs-lookup"><span data-stu-id="9babd-104">This section covers how to declare Protocol Buffer (Protobuf) messages in `.proto` files.</span></span> <span data-ttu-id="9babd-105">В нем разъясняется основные понятия полевых чисел `protoc` и типов, а также рассматривается код C-кода, генерируемого компилятором.</span><span class="sxs-lookup"><span data-stu-id="9babd-105">It explains the fundamental concepts of field numbers and types, and it looks at the C# code that the `protoc` compiler generates.</span></span>

<span data-ttu-id="9babd-106">Остальная часть главы будет более подробно рассматривать, как различные типы данных представлены в Protobuf.</span><span class="sxs-lookup"><span data-stu-id="9babd-106">The rest of the chapter will look in more detail at how different types of data are represented in Protobuf.</span></span>

## <a name="declaring-a-message"></a><span data-ttu-id="9babd-107">Объявление сообщения</span><span class="sxs-lookup"><span data-stu-id="9babd-107">Declaring a message</span></span>

<span data-ttu-id="9babd-108">В Windows Communication Foundation (WCF) `Stock` класс для торгового приложения на фондовом рынке может быть определен следующим примером:</span><span class="sxs-lookup"><span data-stu-id="9babd-108">In Windows Communication Foundation (WCF), a `Stock` class for a stock market trading application might be defined like the following example:</span></span>

```csharp
namespace TraderSys
{
    [DataContract]
    public class Stock
    {
        [DataMember]
        public int Id { get; set;}
        [DataMember]
        public string Symbol { get; set;}
        [DataMember]
        public string DisplayName { get; set;}
        [DataMember]
        public int MarketId { get; set; }
    }
}
```

<span data-ttu-id="9babd-109">Чтобы реализовать эквивалентный класс в Protobuf, `.proto` необходимо объявить его в файле.</span><span class="sxs-lookup"><span data-stu-id="9babd-109">To implement the equivalent class in Protobuf, you must declare it in the `.proto` file.</span></span> <span data-ttu-id="9babd-110">Компилятор `protoc` будет генерировать класс .NET как часть процесса сборки.</span><span class="sxs-lookup"><span data-stu-id="9babd-110">The `protoc` compiler will then generate the .NET class as part of the build process.</span></span>

```protobuf
syntax "proto3";

option csharp_namespace = "TraderSys";

message Stock {

    int32 id = 1;
    string symbol = 2;
    string display_name = 3;
    int32 market_id = 4;

}  
```

<span data-ttu-id="9babd-111">Первая строка объявляет используемую версию синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="9babd-111">The first line declares the syntax version being used.</span></span> <span data-ttu-id="9babd-112">Версия 3 языка была выпущена в 2016 году.</span><span class="sxs-lookup"><span data-stu-id="9babd-112">Version 3 of the language was released in 2016.</span></span> <span data-ttu-id="9babd-113">Это версия, которую мы рекомендуем для услуг gRPC.</span><span class="sxs-lookup"><span data-stu-id="9babd-113">It's the version that we recommend for gRPC services.</span></span>

<span data-ttu-id="9babd-114">Линия `option csharp_namespace` определяет пространство имен, которое будет использоваться для генерируемых типов C.'.</span><span class="sxs-lookup"><span data-stu-id="9babd-114">The `option csharp_namespace` line specifies the namespace to be used for the generated C# types.</span></span> <span data-ttu-id="9babd-115">Этот параметр будет проигнорирован `.proto` при компиляции файла для других языков.</span><span class="sxs-lookup"><span data-stu-id="9babd-115">This option will be ignored when the `.proto` file is compiled for other languages.</span></span> <span data-ttu-id="9babd-116">Файлы Protobuf часто содержат языковые параметры для нескольких языков.</span><span class="sxs-lookup"><span data-stu-id="9babd-116">Protobuf files often contain language-specific options for several languages.</span></span>

<span data-ttu-id="9babd-117">Определение `Stock` сообщения определяет четыре поля.</span><span class="sxs-lookup"><span data-stu-id="9babd-117">The `Stock` message definition specifies four fields.</span></span> <span data-ttu-id="9babd-118">Каждый из них имеет тип, имя и номер поля.</span><span class="sxs-lookup"><span data-stu-id="9babd-118">Each has a type, a name, and a field number.</span></span>

## <a name="field-numbers"></a><span data-ttu-id="9babd-119">Номера полей</span><span class="sxs-lookup"><span data-stu-id="9babd-119">Field numbers</span></span>

<span data-ttu-id="9babd-120">Полевые номера являются важной частью Протобуфа.</span><span class="sxs-lookup"><span data-stu-id="9babd-120">Field numbers are an important part of Protobuf.</span></span> <span data-ttu-id="9babd-121">Они используются для идентификации полей в двоичных закодированных данных, что означает, что они не могут меняться от версии к версии службы.</span><span class="sxs-lookup"><span data-stu-id="9babd-121">They're used to identify fields in the binary encoded data, which means they can't change from version to version of your service.</span></span> <span data-ttu-id="9babd-122">Преимущество в том, что возможна обратная совместимость и передовая совместимость.</span><span class="sxs-lookup"><span data-stu-id="9babd-122">The advantage is that backward compatibility and forward compatibility are possible.</span></span> <span data-ttu-id="9babd-123">Клиенты и службы будут просто игнорировать номера полей, о которыми они не знают, до тех пор, пока будет обработана возможность отсутствующих значений.</span><span class="sxs-lookup"><span data-stu-id="9babd-123">Clients and services will simply ignore field numbers that they don't know about, as long as the possibility of missing values is handled.</span></span>

<span data-ttu-id="9babd-124">В двоичном формате номер поля сочетается с идентификатором типа.</span><span class="sxs-lookup"><span data-stu-id="9babd-124">In the binary format, the field number is combined with a type identifier.</span></span> <span data-ttu-id="9babd-125">Полевые номера от 1 до 15 могут быть закодированы с их типом в качестве одного байта.</span><span class="sxs-lookup"><span data-stu-id="9babd-125">Field numbers from 1 to 15 can be encoded with their type as a single byte.</span></span> <span data-ttu-id="9babd-126">Цифры от 16 до 2047 принимают 2 байта.</span><span class="sxs-lookup"><span data-stu-id="9babd-126">Numbers from 16 to 2,047 take 2 bytes.</span></span> <span data-ttu-id="9babd-127">Вы можете подняться выше, если вам нужно более 2047 полей на сообщение по любой причине.</span><span class="sxs-lookup"><span data-stu-id="9babd-127">You can go higher if you need more than 2,047 fields on a message for any reason.</span></span> <span data-ttu-id="9babd-128">Одноразовые идентификаторы байтов для полевых чисел от 1 до 15 обеспечивают более высокую производительность, поэтому их следует использовать для самых основных, часто используемых полей.</span><span class="sxs-lookup"><span data-stu-id="9babd-128">The single byte identifiers for field numbers 1 to 15 offer better performance, so you should use them for the most basic, frequently used fields.</span></span>

## <a name="types"></a><span data-ttu-id="9babd-129">Типы</span><span class="sxs-lookup"><span data-stu-id="9babd-129">Types</span></span>

<span data-ttu-id="9babd-130">В декларациях типа используются нативные типы данных Protobuf, которые более подробно обсуждаются в [следующем разделе.](protobuf-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="9babd-130">The type declarations are using Protobuf's native scalar data types, which are discussed in more detail in [the next section](protobuf-data-types.md).</span></span> <span data-ttu-id="9babd-131">Остальная часть этой главы будет охватывать встроенные типы Protobuf и показать, как они относятся к общим типам .NET.</span><span class="sxs-lookup"><span data-stu-id="9babd-131">The rest of this chapter will cover Protobuf's built-in types and show how they relate to common .NET types.</span></span>

> [!NOTE]
> <span data-ttu-id="9babd-132">Protobuf не родной поддержки `decimal` типа, поэтому `double` используется вместо.</span><span class="sxs-lookup"><span data-stu-id="9babd-132">Protobuf doesn't natively support a `decimal` type, so `double` is used instead.</span></span> <span data-ttu-id="9babd-133">Для приложений, которые требуют полной десятичной точности, обратитесь к [разделу о десятичных знаков](protobuf-data-types.md#decimals) в следующей части этой главы.</span><span class="sxs-lookup"><span data-stu-id="9babd-133">For applications that require full decimal precision, refer to the [section on decimals](protobuf-data-types.md#decimals) in the next part of this chapter.</span></span>

## <a name="the-generated-code"></a><span data-ttu-id="9babd-134">Сформированный код</span><span class="sxs-lookup"><span data-stu-id="9babd-134">The generated code</span></span>

<span data-ttu-id="9babd-135">При создании приложения Protobuf создает классы для каждого из ваших сообщений, отображая его родные типы до типов C.</span><span class="sxs-lookup"><span data-stu-id="9babd-135">When you build your application, Protobuf creates classes for each of your messages, mapping its native types to C# types.</span></span> <span data-ttu-id="9babd-136">Генерируемый `Stock` тип будет иметь следующую подпись:</span><span class="sxs-lookup"><span data-stu-id="9babd-136">The generated `Stock` type would have the following signature:</span></span>

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

<span data-ttu-id="9babd-137">Сгенерированный код гораздо сложнее, чем этот.</span><span class="sxs-lookup"><span data-stu-id="9babd-137">The actual code that's generated is far more complicated than this.</span></span> <span data-ttu-id="9babd-138">Причина в том, что каждый класс содержит весь код, необходимый для сериализации и десериализации в формате двоичного провода.</span><span class="sxs-lookup"><span data-stu-id="9babd-138">The reason is that each class contains all the code necessary to serialize and deserialize itself to the binary wire format.</span></span>

### <a name="property-names"></a><span data-ttu-id="9babd-139">Имена свойств</span><span class="sxs-lookup"><span data-stu-id="9babd-139">Property names</span></span>

<span data-ttu-id="9babd-140">Обратите внимание, что компилятор Protobuf применяется `PascalCase` к именам свойств, хотя они были `snake_case` в файле. `.proto`</span><span class="sxs-lookup"><span data-stu-id="9babd-140">Note that the Protobuf compiler applied `PascalCase` to the property names, although they were `snake_case` in the `.proto` file.</span></span> <span data-ttu-id="9babd-141">[Руководство по стилю Protobuf](https://developers.google.com/protocol-buffers/docs/style) рекомендует использовать `snake_case` в определениях сообщений, чтобы генерация кода для других платформ побуждала ожидаемый аргумент для их конвенций.</span><span class="sxs-lookup"><span data-stu-id="9babd-141">The [Protobuf style guide](https://developers.google.com/protocol-buffers/docs/style) recommends using `snake_case` in your message definitions so that the code generation for other platforms produces the expected case for their conventions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9babd-142">[Предыдущий](protocol-buffers.md)
>[Следующий](protobuf-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="9babd-142">[Previous](protocol-buffers.md)
[Next](protobuf-data-types.md)</span></span>
