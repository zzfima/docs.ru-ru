---
title: Буферы протоколов — gRPC для разработчиков WCF
description: Общие сведения о формате сети буферов, используемом для gRPC Networking.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 6b47c7f3576134d8ee44f79e329cc4879661e6c3
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841387"
---
# <a name="protocol-buffers"></a><span data-ttu-id="48545-103">Буферы протоколов</span><span class="sxs-lookup"><span data-stu-id="48545-103">Protocol buffers</span></span>

<span data-ttu-id="48545-104">gRPC Services отправляют и получают данные в виде сообщений в виде *буфера протокола (protobuf)* , как и контракты данных WCF.</span><span class="sxs-lookup"><span data-stu-id="48545-104">gRPC services send and receive data as *Protocol Buffer (Protobuf) messages*, similar to WCF's data contracts.</span></span> <span data-ttu-id="48545-105">Protobuf — это эффективный способ сериализации структурированных данных для компьютеров, предназначенных для чтения и записи, без издержек, которые могут возникнет в удобочитаемых форматах, таких как XML или JSON.</span><span class="sxs-lookup"><span data-stu-id="48545-105">Protobuf is an efficient way of serializing structured data for machines to read and write, without the overhead that human-readable formats like XML or JSON incur.</span></span>

<span data-ttu-id="48545-106">В этой главе описывается работа protobuf и определение собственных сообщений protobuf.</span><span class="sxs-lookup"><span data-stu-id="48545-106">This chapter covers how Protobuf works, and how to define your own Protobuf messages.</span></span>

## <a name="how-protobuf-works"></a><span data-ttu-id="48545-107">Как работает protobuf</span><span class="sxs-lookup"><span data-stu-id="48545-107">How Protobuf works</span></span>

<span data-ttu-id="48545-108">Большинство методов сериализации объектов .NET, включая контракты данных WCF, работают с помощью отражения для анализа структуры объектов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="48545-108">Most .NET object serialization techniques, including WCF's data contracts, work by using reflection to analyze the object structure at run time.</span></span> <span data-ttu-id="48545-109">Для большинства библиотек protobuf необходимо заранее определить структуру, используя выделенный язык (*язык буфера протокола*) в файле `.proto`.</span><span class="sxs-lookup"><span data-stu-id="48545-109">By contrast, most Protobuf libraries require you to define the structure up front using a dedicated language (*Protocol Buffer Language*) in a `.proto` file.</span></span> <span data-ttu-id="48545-110">Этот файл затем используется компилятором для создания кода для любой из поддерживаемых платформ, включая .NET, Java, C/C++, JavaScript и многие другие.</span><span class="sxs-lookup"><span data-stu-id="48545-110">This file is then used by a compiler to generate code for any of the supported platforms, including .NET, Java, C/C++, JavaScript, and many more.</span></span> <span data-ttu-id="48545-111">Компилятор protobuf, `protoc`, обслуживается Google, хотя доступны альтернативные реализации.</span><span class="sxs-lookup"><span data-stu-id="48545-111">The Protobuf compiler, `protoc`, is maintained by Google, although alternative implementations are available.</span></span> <span data-ttu-id="48545-112">Созданный код является эффективным и оптимизирован для быстрой сериализации и десериализации данных.</span><span class="sxs-lookup"><span data-stu-id="48545-112">The generated code is efficient and optimized for fast serialization and deserialization of data.</span></span>

<span data-ttu-id="48545-113">Сам формат подключения protobuf — это двоичная кодировка, которая использует некоторые полезные приемы для минимального числа байтов, используемых для представления сообщений.</span><span class="sxs-lookup"><span data-stu-id="48545-113">The Protobuf wire format itself is a binary encoding, which uses some clever tricks to minimize the number of bytes used to represent messages.</span></span> <span data-ttu-id="48545-114">Знание формата двоичного кодирования не обязательно для использования protobuf, но если вас интересует, вы можете узнать больше о нем на [веб-сайте буферов протоколов](https://developers.google.com/protocol-buffers/docs/encoding).</span><span class="sxs-lookup"><span data-stu-id="48545-114">Knowledge of the binary encoding format isn't necessary to use Protobuf, but if you're interested you can learn more about it on [the Protocol Buffers web site](https://developers.google.com/protocol-buffers/docs/encoding).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="48545-115">[Назад](why-grpc.md)
>[Вперед](protobuf-messages.md)</span><span class="sxs-lookup"><span data-stu-id="48545-115">[Previous](why-grpc.md)
[Next](protobuf-messages.md)</span></span>
