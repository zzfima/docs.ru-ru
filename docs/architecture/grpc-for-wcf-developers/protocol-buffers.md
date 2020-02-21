---
title: Буферы протоколов — gRPC для разработчиков WCF
description: Общие сведения о формате сети буферов, используемом для gRPC Networking.
ms.date: 09/09/2019
ms.openlocfilehash: cc4ff272a9912d6f2dd8f8ddb1972c7369f980fe
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503454"
---
# <a name="protocol-buffers"></a><span data-ttu-id="3d1b7-103">Буферы протоколов</span><span class="sxs-lookup"><span data-stu-id="3d1b7-103">Protocol buffers</span></span>

<span data-ttu-id="3d1b7-104">службы gRPC Services отправляют и получают данные в виде сообщений в виде *буфера протокола (protobuf)* , как и контракты данных в Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3d1b7-104">gRPC services send and receive data as *Protocol Buffer (Protobuf) messages*, similar to data contracts in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="3d1b7-105">Protobuf — это эффективный способ сериализации структурированных данных для компьютеров, предназначенных для чтения и записи, без издержек, которые могут возникнет в удобочитаемых форматах, таких как XML или JSON.</span><span class="sxs-lookup"><span data-stu-id="3d1b7-105">Protobuf is an efficient way of serializing structured data for machines to read and write, without the overhead that human-readable formats like XML or JSON incur.</span></span>

<span data-ttu-id="3d1b7-106">В этой главе описывается работа protobuf и определение собственных сообщений protobuf.</span><span class="sxs-lookup"><span data-stu-id="3d1b7-106">This chapter covers how Protobuf works, and how to define your own Protobuf messages.</span></span>

## <a name="how-protobuf-works"></a><span data-ttu-id="3d1b7-107">Как работает protobuf</span><span class="sxs-lookup"><span data-stu-id="3d1b7-107">How Protobuf works</span></span>

<span data-ttu-id="3d1b7-108">Большинство методов сериализации объектов .NET, включая контракты данных WCF, работают с помощью отражения для анализа структуры объектов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="3d1b7-108">Most .NET object serialization techniques, including WCF's data contracts, work by using reflection to analyze the object structure at runtime.</span></span> <span data-ttu-id="3d1b7-109">В большинстве случаев для большинства библиотек protobuf требуется заранее определить структуру с помощью выделенного языка (*языкового буфера протокола*) в `.proto` файле.</span><span class="sxs-lookup"><span data-stu-id="3d1b7-109">By contrast, most Protobuf libraries require you to define the structure up front by using a dedicated language (*Protocol Buffer Language*) in a `.proto` file.</span></span> <span data-ttu-id="3d1b7-110">Затем компилятор использует этот файл для создания кода для любой из поддерживаемых платформ.</span><span class="sxs-lookup"><span data-stu-id="3d1b7-110">A compiler then uses this file to generate code for any of the supported platforms.</span></span> <span data-ttu-id="3d1b7-111">Поддерживаемыми платформами являются .NET, Java,C++C/, JavaScript и многие другие.</span><span class="sxs-lookup"><span data-stu-id="3d1b7-111">Supported platforms include .NET, Java, C/C++, JavaScript, and many more.</span></span> 

<span data-ttu-id="3d1b7-112">Компилятор protobuf, `protoc`, обслуживается Google, хотя доступны альтернативные реализации.</span><span class="sxs-lookup"><span data-stu-id="3d1b7-112">The Protobuf compiler, `protoc`, is maintained by Google, although alternative implementations are available.</span></span> <span data-ttu-id="3d1b7-113">Созданный код является эффективным и оптимизирован для быстрой сериализации и десериализации данных.</span><span class="sxs-lookup"><span data-stu-id="3d1b7-113">The generated code is efficient and optimized for fast serialization and deserialization of data.</span></span>

<span data-ttu-id="3d1b7-114">Формат сети protobuf — это двоичная кодировка.</span><span class="sxs-lookup"><span data-stu-id="3d1b7-114">The Protobuf wire format is a binary encoding.</span></span> <span data-ttu-id="3d1b7-115">Он использует некоторые полезные приемы, чтобы максимально сокращать число байтов, используемых для представления сообщений.</span><span class="sxs-lookup"><span data-stu-id="3d1b7-115">It uses some clever tricks to minimize the number of bytes used to represent messages.</span></span> <span data-ttu-id="3d1b7-116">Знание формата двоичного кодирования не обязательно для использования protobuf.</span><span class="sxs-lookup"><span data-stu-id="3d1b7-116">Knowledge of the binary encoding format isn't necessary to use Protobuf.</span></span> <span data-ttu-id="3d1b7-117">Но если вас интересует, вы можете узнать больше о нем на [веб-сайте буферов протоколов](https://developers.google.com/protocol-buffers/docs/encoding).</span><span class="sxs-lookup"><span data-stu-id="3d1b7-117">But if you're interested, you can learn more about it on [the Protocol Buffers website](https://developers.google.com/protocol-buffers/docs/encoding).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3d1b7-118">[Назад](why-grpc.md)
>[Вперед](protobuf-messages.md)</span><span class="sxs-lookup"><span data-stu-id="3d1b7-118">[Previous](why-grpc.md)
[Next](protobuf-messages.md)</span></span>
