---
title: Балансировка нагрузки gRPC-gRPC для разработчиков WCF
description: Выбор подсистемы балансировки нагрузки для работы со службами gRPC Services.
ms.date: 09/02/2019
ms.openlocfilehash: 070fc7fda73988302d15c8cec12b1ac359641317
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967444"
---
# <a name="load-balancing-grpc"></a><span data-ttu-id="1e1e3-103">GRPC балансировки нагрузки</span><span class="sxs-lookup"><span data-stu-id="1e1e3-103">Load balancing gRPC</span></span>

<span data-ttu-id="1e1e3-104">Типичное развертывание приложения gRPC включает ряд идентичных экземпляров службы, обеспечивая устойчивость и горизонтальную масштабируемость.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-104">A typical deployment of a gRPC application includes a number of identical instances of the service, providing resilience and horizontal scalability.</span></span> <span data-ttu-id="1e1e3-105">Балансировка нагрузки распределяет входящие запросы между этими экземплярами, чтобы обеспечить полное использование всех доступных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-105">Load balancing distributed incoming requests across these instances to provide full usage of all available resources.</span></span> <span data-ttu-id="1e1e3-106">Чтобы обеспечить невидимость этой балансировки нагрузки для клиента, обычно используется сервер балансировщика нагрузки прокси-сервера для обработки запросов от клиентов и их маршрутизации к экземплярам серверной части.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-106">To make this load balancing invisible to the client, it's common to use a proxy load balancer server to handle requests from clients and route them to back-end instances.</span></span>

<span data-ttu-id="1e1e3-107">Подсистемы балансировки нагрузки классифицируются в соответствии с *уровнем* , с которым они работают.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-107">Load balancers are classified according to the *layer* they operate on.</span></span> <span data-ttu-id="1e1e3-108">Подсистемы балансировки нагрузки уровня 4 работают на *транспортном* уровне, например с сокетами TCP, соединениями и пакетами.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-108">Layer 4 load balancers work on the *transport* level, for example, with TCP sockets, connections and packets.</span></span> <span data-ttu-id="1e1e3-109">Подсистемы балансировки нагрузки уровня 7 работают на уровне *приложения* , специально обрабатывая запросы HTTP/2 для приложений gRPC.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-109">Layer 7 load balancers work at the *application* level, specifically handling HTTP/2 requests for gRPC applications.</span></span>

## <a name="l4-load-balancers"></a><span data-ttu-id="1e1e3-110">Подсистемы балансировки нагрузки на уровне 4</span><span class="sxs-lookup"><span data-stu-id="1e1e3-110">L4 load balancers</span></span>

<span data-ttu-id="1e1e3-111">Балансировщик нагрузки уровня 4 принимает запрос TCP-соединения от клиента, открывает другое соединение с одним из внутренних экземпляров и копирует данные между двумя соединениями без реальной обработки.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-111">An L4 load balancer accepts a TCP connection request from a client, opens another connection to one of the back-end instances, and copies data between the two connections with no real processing.</span></span> <span data-ttu-id="1e1e3-112">Уровень 4 обеспечивает высокую производительность и низкую задержку, но очень мало средств управления и анализа.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-112">L4 offers excellent performance and low latency, but very little control or intelligence.</span></span> <span data-ttu-id="1e1e3-113">Пока клиент остается открытым, все запросы будут направлены на один и тот же экземпляр серверной части.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-113">As long as the client keeps the connection open, all requests will be directed to the same back-end instance.</span></span>

<span data-ttu-id="1e1e3-114">Примером использования балансировщика нагрузки уровня 4 является [Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/).</span><span class="sxs-lookup"><span data-stu-id="1e1e3-114">An example of an L4 load balancer is the [Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/).</span></span>

## <a name="l7-load-balancers"></a><span data-ttu-id="1e1e3-115">Подсистемы балансировки нагрузки уровня 7</span><span class="sxs-lookup"><span data-stu-id="1e1e3-115">L7 load balancers</span></span>

<span data-ttu-id="1e1e3-116">Балансировщик нагрузки уровня "на уровне 7" анализирует входящие запросы HTTP/2 и передает их на экземпляры серверной части по запросу, независимо от того, как долго соединение удерживает клиент.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-116">An L7 load balancer parses incoming HTTP/2 requests and passes them on to back-end instances on a request-by-request basis, no matter how long the connection is held by the client.</span></span>

<span data-ttu-id="1e1e3-117">Примерами подсистем балансировки нагрузки на уровне 7 являются:</span><span class="sxs-lookup"><span data-stu-id="1e1e3-117">Examples of L7 load balancers include:</span></span>

- [<span data-ttu-id="1e1e3-118">Nginx</span><span class="sxs-lookup"><span data-stu-id="1e1e3-118">Nginx</span></span>](https://www.nginx.com/)
- [<span data-ttu-id="1e1e3-119">HAproxy</span><span class="sxs-lookup"><span data-stu-id="1e1e3-119">HAproxy</span></span>](https://www.haproxy.com/)
- [<span data-ttu-id="1e1e3-120">траефик</span><span class="sxs-lookup"><span data-stu-id="1e1e3-120">Traefik</span></span>](https://traefik.io/)

<span data-ttu-id="1e1e3-121">Как правило, подсистемы балансировки нагрузки уровня "на уровне 7" являются лучшим выбором для gRPC и других приложений HTTP/2 (и для приложений HTTP, как правило, на самом деле).</span><span class="sxs-lookup"><span data-stu-id="1e1e3-121">As a rule of thumb, L7 load balancers are the best choice for gRPC and other HTTP/2 applications (and for HTTP applications generally, in fact).</span></span> <span data-ttu-id="1e1e3-122">Подсистемы балансировки нагрузки уровня 4 будут *работать* с gRPC приложениями, но они особенно полезны в тех случаях, когда низкая задержка и низкая нагрузка являются важнейшими по важности.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-122">L4 load balancers will *work* with gRPC applications, but are primarily useful when low latency and low overhead are of paramount importance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e1e3-123">На момент написания этой статьи не все подсистемы балансировки нагрузки уровня 7 поддерживают все части спецификации HTTP/2, необходимые для gRPC Services, например конечные заголовки.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-123">At the time of this writing, not all L7 load balancers support all parts of the HTTP/2 specification required by gRPC services, such as trailing headers.</span></span>

<span data-ttu-id="1e1e3-124">При использовании TLS-шифрования подсистемы балансировки нагрузки могут завершить TLS-подключение и передать незашифрованные запросы в серверное приложение или передать зашифрованный запрос вместе.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-124">When using TLS encryption, load balancers can terminate the TLS connection and pass unencrypted requests to the back-end application, or pass the encrypted request along.</span></span> <span data-ttu-id="1e1e3-125">В любом случае для подсистемы балансировки нагрузки необходимо настроить открытый и закрытый ключи сервера, чтобы он мог расшифровывать запросы на обработку.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-125">Either way, the load balancer will need to be configured with the server's public and private key, so that it can decrypt requests for processing.</span></span>

<span data-ttu-id="1e1e3-126">Сведения о том, как настроить обработку запросов HTTP/2 к серверным службам, см. в документации по предпочтительной подсистеме балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-126">Refer to the documentation for your preferred load balancer to find out how to configure it to handle HTTP/2 requests with your back-end services.</span></span>

## <a name="load-balancing-within-kubernetes"></a><span data-ttu-id="1e1e3-127">Балансировка нагрузки в Kubernetes</span><span class="sxs-lookup"><span data-stu-id="1e1e3-127">Load balancing within Kubernetes</span></span>

<span data-ttu-id="1e1e3-128">Описание балансировки нагрузки между внутренними службами в Kubernetes см. в [разделе о](service-mesh.md) связях между службами.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-128">See [the section on Service Meshes](service-mesh.md) for a discussion of load balancing across internal services on Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1e1e3-129">[Назад](service-mesh.md)
>[Вперед](application-performance-management.md)</span><span class="sxs-lookup"><span data-stu-id="1e1e3-129">[Previous](service-mesh.md)
[Next](application-performance-management.md)</span></span>
