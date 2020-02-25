---
title: Шифрование и безопасность сети — gRPC для разработчиков WCF
description: Некоторые замечания по сетевой безопасности и шифрованию в gRPC
ms.date: 09/02/2019
ms.openlocfilehash: f8a7aeaf2a65e4ff56ac33d728e40f09a436f7a6
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542784"
---
# <a name="encryption-and-network-security"></a><span data-ttu-id="3b082-103">Шифрование и безопасность сети</span><span class="sxs-lookup"><span data-stu-id="3b082-103">Encryption and network security</span></span>

<span data-ttu-id="3b082-104">Модель сетевой безопасности для Windows Communication Foundation (WCF) является обширной и сложной.</span><span class="sxs-lookup"><span data-stu-id="3b082-104">The network security model for Windows Communication Foundation (WCF) is extensive and complex.</span></span> <span data-ttu-id="3b082-105">Она включает безопасность на уровне транспорта с помощью HTTPS или TLS-over-TCP и безопасность на уровне сообщений, используя спецификацию WS-Security для шифрования отдельных сообщений.</span><span class="sxs-lookup"><span data-stu-id="3b082-105">It includes transport-level security by using HTTPS or TLS-over-TCP, and message-level security by using the WS-Security specification to encrypt individual messages.</span></span>

<span data-ttu-id="3b082-106">gRPC оставляет защищенную сеть основным протоколом HTTP/2, который можно защитить с помощью TLS-сертификатов.</span><span class="sxs-lookup"><span data-stu-id="3b082-106">gRPC leaves secure networking to the underlying HTTP/2 protocol, which you can secure by using TLS certificates.</span></span>

<span data-ttu-id="3b082-107">Веб-браузеры настаивает на использовании соединений TLS для HTTP/2, но большинство программных клиентов, включая. `HttpClient`сети, может использовать HTTP/2 через незашифрованные соединения.</span><span class="sxs-lookup"><span data-stu-id="3b082-107">Web browsers insist on using TLS connections for HTTP/2, but most programmatic clients, including .NET's `HttpClient`, can use HTTP/2 over unencrypted connections.</span></span> <span data-ttu-id="3b082-108">по умолчанию для `HttpClient` требуется шифрование, но его можно переопределить с помощью параметра <xref:System.AppContext>.</span><span class="sxs-lookup"><span data-stu-id="3b082-108">`HttpClient` does require encryption by default, but you can override this by using an <xref:System.AppContext> switch.</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="3b082-109">Для общедоступных API следует всегда использовать TLS-подключения и предоставлять действительные сертификаты для служб из соответствующего центра SSL.</span><span class="sxs-lookup"><span data-stu-id="3b082-109">For public APIs, you should always use TLS connections, and provide valid certificates for your services from a proper SSL authority.</span></span> <span data-ttu-id="3b082-110">[Летсенкрипт](https://letsencrypt.org) предоставляет бесплатные, АВТОМАТИЗИРОВАНные SSL-сертификаты и большинство современных инфраструктур размещения поддерживает стандарт летсенкрипт с общими подключаемыми модулями или расширениями.</span><span class="sxs-lookup"><span data-stu-id="3b082-110">[LetsEncrypt](https://letsencrypt.org) provides free, automated SSL certificates, and most hosting infrastructure today supports the LetsEncrypt standard with common plug-ins or extensions.</span></span>

<span data-ttu-id="3b082-111">Для внутренних служб в корпоративной сети по-прежнему следует использовать TLS для защиты сетевого трафика от gRPC Services.</span><span class="sxs-lookup"><span data-stu-id="3b082-111">For internal services across a corporate network, you should still consider using TLS to secure network traffic to and from your gRPC services.</span></span>

<span data-ttu-id="3b082-112">Если необходимо использовать явный протокол TLS между службами, работающими в Kubernetes, рассмотрите возможность использования центра сертификации в кластере и контроллера диспетчера сертификатов, например [CERT-Manager](https://docs.cert-manager.io/en/latest/).</span><span class="sxs-lookup"><span data-stu-id="3b082-112">If you need to use explicit TLS between services running in Kubernetes, consider using an in-cluster certificate authority and a certificate manager controller like [cert-manager](https://docs.cert-manager.io/en/latest/).</span></span> <span data-ttu-id="3b082-113">Затем можно автоматически назначать сертификаты службам во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="3b082-113">You can then automatically assign certificates to services at deployment time.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3b082-114">[Назад](channel-credentials.md)
>[Вперед](grpc-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="3b082-114">[Previous](channel-credentials.md)
[Next](grpc-in-production.md)</span></span>
