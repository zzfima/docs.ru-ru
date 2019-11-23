---
title: Шифрование и безопасность сети — gRPC для разработчиков WCF
description: Некоторые замечания по сетевой безопасности и шифрованию в gRPC
ms.date: 09/02/2019
ms.openlocfilehash: fd993a2d75e97011c6c92cee02c24c5358a211ad
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967779"
---
# <a name="encryption-and-network-security"></a><span data-ttu-id="3e58f-103">Шифрование и безопасность сети</span><span class="sxs-lookup"><span data-stu-id="3e58f-103">Encryption and network security</span></span>

<span data-ttu-id="3e58f-104">Модель сетевой безопасности WCF обширна и сложная, включая безопасность на уровне транспорта с использованием HTTPS или TLS через TCP и безопасность на уровне сообщений с использованием спецификации WS-Security для шифрования отдельных сообщений.</span><span class="sxs-lookup"><span data-stu-id="3e58f-104">WCF's network security model is extensive and complex, including transport-level security using HTTPS or TLS-over-TCP, and message-level security using the WS-Security specification to encrypt individual messages.</span></span>

<span data-ttu-id="3e58f-105">gRPC оставляет защищенную сеть основным протоколом HTTP/2, который можно защитить с помощью обычных сертификатов TLS.</span><span class="sxs-lookup"><span data-stu-id="3e58f-105">gRPC leaves secure networking to the underlying HTTP/2 protocol, which can be secured using regular TLS certificates.</span></span>

<span data-ttu-id="3e58f-106">Веб-браузеры настаивает на использовании соединений TLS для HTTP/2, но большинство программных клиентов, включая. `HttpClient`сети, может использовать HTTP/2 через незашифрованные соединения.</span><span class="sxs-lookup"><span data-stu-id="3e58f-106">Web browsers insist on using TLS connections for HTTP/2, but most programmatic clients, including .NET's `HttpClient`, can use HTTP/2 over unencrypted connections.</span></span> <span data-ttu-id="3e58f-107">по умолчанию *для `HttpClient` требуется* шифрование, но его можно переопределить с помощью параметра <xref:System.AppContext>.</span><span class="sxs-lookup"><span data-stu-id="3e58f-107">`HttpClient` *does* require encryption by default, but you can override this using an <xref:System.AppContext> switch.</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="3e58f-108">Для общедоступных API следует всегда использовать TLS-подключения и предоставлять действительные сертификаты для служб из соответствующего центра SSL.</span><span class="sxs-lookup"><span data-stu-id="3e58f-108">For public APIs, you should always use TLS connections and provide valid certificates for your services from a proper SSL authority.</span></span> <span data-ttu-id="3e58f-109">[Летсенкрипт](https://letsencrypt.org) предоставляют бесплатные, АВТОМАТИЗИРОВАНные SSL-сертификаты и большинство современных инфраструктур размещения поддерживает стандарт летсенкрипт с общими подключаемыми модулями или расширениями.</span><span class="sxs-lookup"><span data-stu-id="3e58f-109">[LetsEncrypt](https://letsencrypt.org) provide free, automated SSL certificates, and most hosting infrastructure today supports the LetsEncrypt standard with common plug-ins or extensions.</span></span>

<span data-ttu-id="3e58f-110">Для внутренних служб в корпоративной сети по-прежнему следует использовать TLS для защиты сетевого трафика от gRPC Services.</span><span class="sxs-lookup"><span data-stu-id="3e58f-110">For internal services across a corporate network, you should still consider using TLS to secure network traffic to and from your gRPC services.</span></span>

<span data-ttu-id="3e58f-111">Обмен данными между микрослужбами в кластере, например Kubernetes или DOCKER Swarm, обычно автоматически шифруется на уровне сети контейнера, поэтому реализация TLS в службах, работающих исключительно в таком кластере, не является обязательной.</span><span class="sxs-lookup"><span data-stu-id="3e58f-111">Communication between microservices in a cluster like Kubernetes or Docker Swarm is in general automatically encrypted by the container networking layer, so implementing TLS in services running exclusively in such a cluster isn't necessary.</span></span> <span data-ttu-id="3e58f-112">Дополнительные сведения об этой теме см. в разделе "Сетка услуг" в следующей главе.</span><span class="sxs-lookup"><span data-stu-id="3e58f-112">There will be more on this subject in the "Service Mesh" section of the next chapter.</span></span>

<span data-ttu-id="3e58f-113">Если необходимо использовать явное TLS-соединение между службами, работающими в Kubernetes, рассмотрите возможность использования центра сертификации в кластере и контроллера диспетчера сертификатов, например [CERT-Manager](https://docs.cert-manager.io/en/latest/) , для назначения автоматических сертификатов службам во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="3e58f-113">If you need to use explicit TLS between services running in Kubernetes, consider using an in-cluster Certificate Authority and a Certificate Manager Controller like [cert-manager](https://docs.cert-manager.io/en/latest/) to assign automatically certificates to services at deployment time.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3e58f-114">[Назад](channel-credentials.md)
>[Вперед](grpc-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="3e58f-114">[Previous](channel-credentials.md)
[Next](grpc-in-production.md)</span></span>
