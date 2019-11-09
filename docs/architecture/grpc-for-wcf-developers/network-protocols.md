---
title: Сетевые протоколы — gRPC для разработчиков WCF
description: Общие сведения о сетевых протоколах gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: cf99b2608d576765856c992679b93b6f21e796cf
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841465"
---
# <a name="network-protocols"></a><span data-ttu-id="d355e-103">Сетевые протоколы</span><span class="sxs-lookup"><span data-stu-id="d355e-103">Network protocols</span></span>

<span data-ttu-id="d355e-104">В отличие от WCF, gRPC использует HTTP/2 в качестве основы для своей сети.</span><span class="sxs-lookup"><span data-stu-id="d355e-104">Unlike WCF, gRPC uses HTTP/2 as a base for its networking.</span></span> <span data-ttu-id="d355e-105">Это обеспечивает значительные преимущества по сравнению с WCF и SOAP, которые работают только с HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="d355e-105">This offers significant advantages over WCF and SOAP, which only operate on HTTP/1.1.</span></span> <span data-ttu-id="d355e-106">Для разработчиков, желающих использовать gRPC, учитывая, что нет альтернативы HTTP/2, кажется идеальным моментом исследовать HTTP/2 более подробно и определять дополнительные преимущества для использования gRPC.</span><span class="sxs-lookup"><span data-stu-id="d355e-106">For developers wanting to use gRPC, given that there's no alternative to HTTP/2, it would seem to be the ideal moment to explore HTTP/2 in more detail and identify additional benefits to using gRPC.</span></span>

<span data-ttu-id="d355e-107">HTTP/2, вызываемая веб-задачей инженерной разработки в 2015, была получена из экспериментального протокола SPDY, который уже использовался в Google.</span><span class="sxs-lookup"><span data-stu-id="d355e-107">HTTP/2, released by Internet Engineering Task Force in 2015, was derived from the experimental SPDY protocol, which was already being used by Google.</span></span> <span data-ttu-id="d355e-108">Он был специально разработан для более эффективного, быстрого и более безопасного, чем HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="d355e-108">It was specifically designed to be more efficient, faster, and more secure than HTTP/1.1.</span></span>

## <a name="key-features-of-http2"></a><span data-ttu-id="d355e-109">Основные функции HTTP/2</span><span class="sxs-lookup"><span data-stu-id="d355e-109">Key features of HTTP/2</span></span>

<span data-ttu-id="d355e-110">В следующем списке показаны некоторые основные функции и преимущества HTTP/2:</span><span class="sxs-lookup"><span data-stu-id="d355e-110">The following list shows some of the key features and advantages of HTTP/2:</span></span>

### <a name="binary-protocol"></a><span data-ttu-id="d355e-111">Двоичный протокол</span><span class="sxs-lookup"><span data-stu-id="d355e-111">Binary protocol</span></span>

<span data-ttu-id="d355e-112">Циклы запросов и ответов больше не требуют текстовых команд.</span><span class="sxs-lookup"><span data-stu-id="d355e-112">Request/response cycles no longer need text commands.</span></span> <span data-ttu-id="d355e-113">Это упрощает и ускоряет реализацию команд.</span><span class="sxs-lookup"><span data-stu-id="d355e-113">This simplifies and speeds up implementation of commands.</span></span> <span data-ttu-id="d355e-114">В частности, анализ данных выполняется быстрее и использует меньше памяти, задержка сети сокращается с помощью очевидных улучшений, а также обеспечивается общее лучшее использование сетевых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d355e-114">Specifically, parsing data is faster and uses less memory, network latency is reduced with obvious related improvements to speed, and there's an overall better use of network resources.</span></span>

### <a name="streams"></a><span data-ttu-id="d355e-115">Потоки</span><span class="sxs-lookup"><span data-stu-id="d355e-115">Streams</span></span>

<span data-ttu-id="d355e-116">Потоки позволяют создавать долгосрочные соединения между отправителем и получателем, при котором несколько сообщений или кадров могут быть отправлены асинхронно.</span><span class="sxs-lookup"><span data-stu-id="d355e-116">Streams allow for the creation of long-lived connections between sender and receiver, over which multiple messages or frames can be sent asynchronously.</span></span> <span data-ttu-id="d355e-117">Несколько потоков могут обрабатываться независимо друг от друга через одно соединение HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="d355e-117">Multiple streams can operate independently over a single HTTP/2 connection.</span></span>

### <a name="request-multiplexing-over-a-single-tcp-connection"></a><span data-ttu-id="d355e-118">Запрос мультиплексирования по одному TCP-соединению</span><span class="sxs-lookup"><span data-stu-id="d355e-118">Request multiplexing over a single TCP connection</span></span>

<span data-ttu-id="d355e-119">Эта функция является одним из наиболее важных нововведений HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="d355e-119">This feature is one of the most important innovations of HTTP/2.</span></span> <span data-ttu-id="d355e-120">Разрешая несколько параллельных запросов данных, теперь можно загружать веб-файлы параллельно с одного сервера.</span><span class="sxs-lookup"><span data-stu-id="d355e-120">By allowing multiple parallel requests for data, it's now possible to download web files concurrently from a single server.</span></span> <span data-ttu-id="d355e-121">Веб-сайты быстрее загружаются, и потребность в оптимизации уменьшается.</span><span class="sxs-lookup"><span data-stu-id="d355e-121">Websites load faster and the need for optimization is reduced.</span></span> <span data-ttu-id="d355e-122">Блокировка до конца строки (HOL), где готовые ответы должны ожидать отправки до тех пор, пока не завершится предыдущий запрос, также будет устранена (хотя блокировка на уровне ХОЛЬ может выполняться на транспортном протоколе TCP).</span><span class="sxs-lookup"><span data-stu-id="d355e-122">Head-of-line (HOL) blocking, where responses that are ready must wait to be sent until an earlier request is completed, is also mitigated (although HOL blocking can still occur at the TCP transport level).</span></span>

### <a name="nettcp-like-performance-cross-platform"></a><span data-ttu-id="d355e-123">Производительность NetTCP-Like, кросс-платформенные</span><span class="sxs-lookup"><span data-stu-id="d355e-123">NetTCP-like performance, cross-platform</span></span>

<span data-ttu-id="d355e-124">По сути, сочетание gRPC и HTTP/2 предоставляет разработчикам по крайней мере эквивалентную скорость и эффективность привязок NetTCP для WCF, а в некоторых случаях еще более высокую скорость и эффективность.</span><span class="sxs-lookup"><span data-stu-id="d355e-124">Fundamentally, the combination of gRPC and HTTP/2 offer developers at least the equivalent speed and efficiency of NetTCP bindings for WCF, and in some cases even greater speed and efficiency.</span></span> <span data-ttu-id="d355e-125">Однако, в отличие от NetTCP, gRPC через HTTP/2 не ограничены приложениями .NET.</span><span class="sxs-lookup"><span data-stu-id="d355e-125">However, unlike NetTCP, gRPC over HTTP/2 isn't constrained to .NET applications.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d355e-126">[Назад](interface-definition-language.md)
>[Вперед](why-grpc.md)</span><span class="sxs-lookup"><span data-stu-id="d355e-126">[Previous](interface-definition-language.md)
[Next](why-grpc.md)</span></span>
