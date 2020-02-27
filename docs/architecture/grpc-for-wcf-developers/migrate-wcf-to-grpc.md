---
title: Перенос решения WCF в gRPC-gRPC для разработчиков WCF
description: Как перенести различные типы служб WCF в эквивалент в gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 12e724ab46a33547d352da7a604a5a994e617bc2
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628518"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a><span data-ttu-id="1a5d3-103">Перенос решения WCF в gRPC</span><span class="sxs-lookup"><span data-stu-id="1a5d3-103">Migrate a WCF solution to gRPC</span></span>

<span data-ttu-id="1a5d3-104">В этой главе описывается работа с проектами ASP.NET Core 3,0 gRPC и демонстрируется перенос различных типов служб Windows Communication Foundation (WCF) в эквивалент gRPC.</span><span class="sxs-lookup"><span data-stu-id="1a5d3-104">This chapter will describe how to work with ASP.NET Core 3.0 gRPC projects and demonstrate migrating different types of Windows Communication Foundation (WCF) services to the gRPC equivalent:</span></span>

- <span data-ttu-id="1a5d3-105">Создайте проект ASP.NET Core 3,0 gRPC.</span><span class="sxs-lookup"><span data-stu-id="1a5d3-105">Create an ASP.NET Core 3.0 gRPC project.</span></span>
- <span data-ttu-id="1a5d3-106">Простые операции запроса-ответа для gRPC унарного RPC.</span><span class="sxs-lookup"><span data-stu-id="1a5d3-106">Simple request-reply operations to gRPC unary RPC.</span></span>
- <span data-ttu-id="1a5d3-107">Односторонние операции для gRPC потоковой передачи RPC клиента.</span><span class="sxs-lookup"><span data-stu-id="1a5d3-107">One-way operations to gRPC client streaming RPC.</span></span>
- <span data-ttu-id="1a5d3-108">Службы с полным дуплексом для gRPC двунаправленной потоковой передачи RPC.</span><span class="sxs-lookup"><span data-stu-id="1a5d3-108">Full-duplex services to gRPC bidirectional streaming RPC.</span></span>

<span data-ttu-id="1a5d3-109">Также существует Сравнение использования служб потоковой передачи и повторяющихся полей для возврата наборов данных, и в конце главы рассматривается использование клиентских библиотек.</span><span class="sxs-lookup"><span data-stu-id="1a5d3-109">There's also a comparison of using streaming services versus repeated fields for returning datasets, and there's a discussion of the use of client libraries at the end of the chapter.</span></span>

<span data-ttu-id="1a5d3-110">Пример приложения WCF представляет собой минимальную заглушку набора служб торговли акции.</span><span class="sxs-lookup"><span data-stu-id="1a5d3-110">The sample WCF application is a minimal stub of a set of stock trading services.</span></span> <span data-ttu-id="1a5d3-111">В нем используется библиотека контейнеров инверсии управления (IoC) с открытым исходным кодом, именуемая Autofac для внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="1a5d3-111">It uses the open-source Inversion of Control (IoC) container library called Autofac for dependency injection.</span></span> <span data-ttu-id="1a5d3-112">Он включает три службы — по одному для каждого типа службы WCF.</span><span class="sxs-lookup"><span data-stu-id="1a5d3-112">It includes three services, one for each WCF service type.</span></span> <span data-ttu-id="1a5d3-113">Службы будут обсуждаться более подробно в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="1a5d3-113">The services will be discussed in more detail in the following sections.</span></span> <span data-ttu-id="1a5d3-114">Вы можете скачать решения из [DotNet-Architecture/GRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) на GitHub.</span><span class="sxs-lookup"><span data-stu-id="1a5d3-114">You can download the solutions from [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) on GitHub.</span></span> <span data-ttu-id="1a5d3-115">Службы используют фиктивные данные для сворачивания внешних зависимостей.</span><span class="sxs-lookup"><span data-stu-id="1a5d3-115">The services use fake data to minimize external dependencies.</span></span>

<span data-ttu-id="1a5d3-116">Примеры включают реализации WCF и gRPC для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="1a5d3-116">The samples include the WCF and gRPC implementations of each service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1a5d3-117">[Назад](ws-protocols.md)
>[Вперед](create-project.md)</span><span class="sxs-lookup"><span data-stu-id="1a5d3-117">[Previous](ws-protocols.md)
[Next](create-project.md)</span></span>
