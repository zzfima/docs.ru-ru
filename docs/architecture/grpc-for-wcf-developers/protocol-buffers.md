---
title: Протокол буферов - gRPC для разработчиков WCF
description: Введение в формат провода Протокол афференисты, используемый для сетей gRPC.
ms.date: 09/09/2019
ms.openlocfilehash: 35319d299a8bc2866a87954b3e54bfda9314ffe8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147936"
---
# <a name="protocol-buffers"></a><span data-ttu-id="2f9d3-103">Буферы протокола</span><span class="sxs-lookup"><span data-stu-id="2f9d3-103">Protocol buffers</span></span>

<span data-ttu-id="2f9d3-104">службы gRPC отправляют и получают данные в виде *сообщений Протокола Буфера (Protobuf),* аналогичных контрактам на передачу данных в Фонд ес windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="2f9d3-104">gRPC services send and receive data as *Protocol Buffer (Protobuf) messages*, similar to data contracts in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="2f9d3-105">Protobuf является эффективным способом сериализации структурированных данных для машин для чтения и записи, без накладных расходов, которые понесут читаемые человеком форматы, такие как XML или JSON.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-105">Protobuf is an efficient way of serializing structured data for machines to read and write, without the overhead that human-readable formats like XML or JSON incur.</span></span>

<span data-ttu-id="2f9d3-106">В этой главе рассказывается о том, как работает Протобуф, и как определить свои собственные сообщения Protobuf.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-106">This chapter covers how Protobuf works, and how to define your own Protobuf messages.</span></span>

## <a name="how-protobuf-works"></a><span data-ttu-id="2f9d3-107">Как работает Протобуф</span><span class="sxs-lookup"><span data-stu-id="2f9d3-107">How Protobuf works</span></span>

<span data-ttu-id="2f9d3-108">Большинство методов сериализации объектов .NET, включая контракты WCF на данные, работают с помощью отражения для анализа структуры объекта во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-108">Most .NET object serialization techniques, including WCF's data contracts, work by using reflection to analyze the object structure at runtime.</span></span> <span data-ttu-id="2f9d3-109">В отличие от этого, большинство библиотек Protobuf требуют, чтобы вы определили структуру заранее, используя выделенный язык *(Протокол Buffer Language*) в файле. `.proto`</span><span class="sxs-lookup"><span data-stu-id="2f9d3-109">By contrast, most Protobuf libraries require you to define the structure up front by using a dedicated language (*Protocol Buffer Language*) in a `.proto` file.</span></span> <span data-ttu-id="2f9d3-110">Затем компилятор использует этот файл для генерации кода для любой из поддерживаемых платформ.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-110">A compiler then uses this file to generate code for any of the supported platforms.</span></span> <span data-ttu-id="2f9d3-111">Поддерживаемые платформы включают в себя .NET, Java, C/C , JavaScript и многое другое.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-111">Supported platforms include .NET, Java, C/C++, JavaScript, and many more.</span></span>

<span data-ttu-id="2f9d3-112">Компилятор Protobuf, `protoc`поддерживается Google, хотя альтернативные реализации доступны.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-112">The Protobuf compiler, `protoc`, is maintained by Google, although alternative implementations are available.</span></span> <span data-ttu-id="2f9d3-113">Сгенерированный код эффективен и оптимизирован для быстрой сериализации и десериализации данных.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-113">The generated code is efficient and optimized for fast serialization and deserialization of data.</span></span>

<span data-ttu-id="2f9d3-114">Формат провода Protobuf представляет собой двоичное кодирование.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-114">The Protobuf wire format is a binary encoding.</span></span> <span data-ttu-id="2f9d3-115">Он использует некоторые умные трюки, чтобы свести к минимуму количество байтов, используемых для представления сообщений.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-115">It uses some clever tricks to minimize the number of bytes used to represent messages.</span></span> <span data-ttu-id="2f9d3-116">Знание формата кодирования двоичного не обязательно использовать Protobuf.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-116">Knowledge of the binary encoding format isn't necessary to use Protobuf.</span></span> <span data-ttu-id="2f9d3-117">Но если вы заинтересованы, вы можете узнать больше об этом на [сайте Протокол буферов](https://developers.google.com/protocol-buffers/docs/encoding).</span><span class="sxs-lookup"><span data-stu-id="2f9d3-117">But if you're interested, you can learn more about it on [the Protocol Buffers website](https://developers.google.com/protocol-buffers/docs/encoding).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2f9d3-118">[Предыдущий](why-grpc.md)
>[Следующий](protobuf-messages.md)</span><span class="sxs-lookup"><span data-stu-id="2f9d3-118">[Previous](why-grpc.md)
[Next](protobuf-messages.md)</span></span>
