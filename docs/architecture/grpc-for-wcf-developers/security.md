---
title: Безопасность в gRPC приложениях — gRPC для разработчиков WCF
description: Общие сведения о проверке подлинности и авторизации вызовов в gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: d0b7ff5bef755c5eeb9b3c419dcda1cb75ac4031
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841375"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="1d32f-103">Безопасность в приложениях gRPC</span><span class="sxs-lookup"><span data-stu-id="1d32f-103">Security in gRPC applications</span></span>

<span data-ttu-id="1d32f-104">В любом реальном сценарии важно обеспечить безопасность приложений и служб.</span><span class="sxs-lookup"><span data-stu-id="1d32f-104">In any real-world scenario, securing applications and services is essential.</span></span> <span data-ttu-id="1d32f-105">Безопасность охватывает три ключевых области: шифрование сетевого трафика, чтобы предотвратить его перехват неправильными субъектами. Проверка подлинности клиентов и серверов для установления личности и доверия; и авторизация клиентов для управления доступом к системам и применения разрешений на основе удостоверения.</span><span class="sxs-lookup"><span data-stu-id="1d32f-105">Security covers three key areas: encrypting network traffic to prevent it from being intercepted by bad actors; authenticating clients and servers to establish identity and trust; and authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="1d32f-106">**Проверка подлинности** важна для установления удостоверения клиента или сервера.</span><span class="sxs-lookup"><span data-stu-id="1d32f-106">**Authentication** is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="1d32f-107">**Авторизация** связана с определением наличия у клиента разрешения на доступ к ресурсу или на выдачу команды.</span><span class="sxs-lookup"><span data-stu-id="1d32f-107">**Authorization** is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="1d32f-108">В этой главе будут рассмотрены средства проверки подлинности и авторизации в gRPC для ASP.NET Core, а также обсуждается Сетевая безопасность с использованием TLS зашифрованных соединений.</span><span class="sxs-lookup"><span data-stu-id="1d32f-108">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core, and discuss network security using TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="1d32f-109">Проверка подлинности и авторизация WCF</span><span class="sxs-lookup"><span data-stu-id="1d32f-109">WCF authentication and authorization</span></span>

<span data-ttu-id="1d32f-110">В WCF проверка подлинности и авторизация обрабатывались различными способами в зависимости от используемых транспортов и привязок.</span><span class="sxs-lookup"><span data-stu-id="1d32f-110">In WCF, authentication and authorization were handled in different ways depending on the transports and bindings being used.</span></span> <span data-ttu-id="1d32f-111">WCF поддерживала различные стандарты безопасности WS-\*, а также проверку подлинности Windows для служб HTTP, работающих в IIS или службах NetTCP, между системами Windows.</span><span class="sxs-lookup"><span data-stu-id="1d32f-111">WCF supported various WS-\* security standards, as well as Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="1d32f-112">Проверка подлинности и авторизация gRPC</span><span class="sxs-lookup"><span data-stu-id="1d32f-112">gRPC authentication and authorization</span></span>

<span data-ttu-id="1d32f-113">Проверка подлинности и авторизация gRPC работают на двух уровнях.</span><span class="sxs-lookup"><span data-stu-id="1d32f-113">gRPC authentication and authorization works on two levels.</span></span> <span data-ttu-id="1d32f-114">Проверка подлинности и авторизация на уровне вызовов обычно обрабатываются с помощью токенов, которые применяются в метаданных при вызове.</span><span class="sxs-lookup"><span data-stu-id="1d32f-114">Call-level authentication/authorization is usually handled using tokens that are applied in metadata when the call is made.</span></span> <span data-ttu-id="1d32f-115">Проверка подлинности на уровне канала использует сертификат клиента, применяемый на уровне соединения, и может также включать учетные данные проверки подлинности или авторизации на уровне вызовов, которые будут применяться к каждому вызову в канале автоматически.</span><span class="sxs-lookup"><span data-stu-id="1d32f-115">Channel-level authentication uses a client certificate that is applied at the connection level, and can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span> <span data-ttu-id="1d32f-116">Для защиты службы можно использовать любой из этих механизмов или оба этих механизма.</span><span class="sxs-lookup"><span data-stu-id="1d32f-116">You can use either or both of these mechanisms to secure your service.</span></span>

<span data-ttu-id="1d32f-117">ASP.NET Core реализация gRPC поддерживает проверку подлинности и авторизацию с помощью большинства стандартных механизмов ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="1d32f-117">The ASP.NET Core implementation of gRPC supports authentication and authorization using most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="1d32f-118">Проверка подлинности вызова</span><span class="sxs-lookup"><span data-stu-id="1d32f-118">Call authentication</span></span>
  - <span data-ttu-id="1d32f-119">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1d32f-119">Azure Active Directory</span></span>
  - <span data-ttu-id="1d32f-120">IdentityServer</span><span class="sxs-lookup"><span data-stu-id="1d32f-120">IdentityServer</span></span>
  - <span data-ttu-id="1d32f-121">Токен носителя JWT</span><span class="sxs-lookup"><span data-stu-id="1d32f-121">JWT Bearer Token</span></span>
  - <span data-ttu-id="1d32f-122">OAuth 2,0</span><span class="sxs-lookup"><span data-stu-id="1d32f-122">OAuth 2.0</span></span>
  - <span data-ttu-id="1d32f-123">OpenID Connect подключение</span><span class="sxs-lookup"><span data-stu-id="1d32f-123">OpenID Connect</span></span>
  - <span data-ttu-id="1d32f-124">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="1d32f-124">WS-Federation</span></span>
- <span data-ttu-id="1d32f-125">Проверка подлинности канала</span><span class="sxs-lookup"><span data-stu-id="1d32f-125">Channel authentication</span></span>
  - <span data-ttu-id="1d32f-126">Сертификат клиента</span><span class="sxs-lookup"><span data-stu-id="1d32f-126">Client Certificate</span></span>

<span data-ttu-id="1d32f-127">Методы проверки подлинности вызовов основаны на *маркерах*.</span><span class="sxs-lookup"><span data-stu-id="1d32f-127">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="1d32f-128">Единственное вещественное отличие заключается в том, как создается маркер и библиотеки, используемые для проверки маркеров в службе ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1d32f-128">The only real difference is how the token is generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="1d32f-129">Дополнительные сведения см. в [документации по проверке подлинности и авторизации на документация Майкрософт](https://docs.microsoft.com/aspnet/core/grpc/authn-and-authz?view=aspnetcore-3.0).</span><span class="sxs-lookup"><span data-stu-id="1d32f-129">For more information, see the [Authentication and authorization documentation on Microsoft Docs](https://docs.microsoft.com/aspnet/core/grpc/authn-and-authz?view=aspnetcore-3.0).</span></span>

> [!NOTE]
> <span data-ttu-id="1d32f-130">При использовании gRPC для подключения HTTP/2 с шифрованием TLS весь трафик между клиентами и серверами шифруется, даже если не используется проверка подлинности на уровне канала.</span><span class="sxs-lookup"><span data-stu-id="1d32f-130">When using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="1d32f-131">В этой главе показано, как применять учетные данные вызова и учетные данные канала к службе gRPC, а также как использовать учетные данные из клиента .NET Core gRPC для проверки подлинности в службе.</span><span class="sxs-lookup"><span data-stu-id="1d32f-131">This chapter will show how to apply call credentials and channel credentials to a gRPC service, and how to use credentials from a .NET Core gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1d32f-132">[Назад](client-libraries.md)
>[Вперед](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="1d32f-132">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
