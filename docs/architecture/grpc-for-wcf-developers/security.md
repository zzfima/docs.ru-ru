---
title: Безопасность в gRPC приложениях — gRPC для разработчиков WCF
description: Общие сведения о проверке подлинности и авторизации вызовов в gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: d5804ad5de4a834eb81b90fa1ea7a61969a0b42f
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503417"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="1d8ac-103">Безопасность в приложениях gRPC</span><span class="sxs-lookup"><span data-stu-id="1d8ac-103">Security in gRPC applications</span></span>

<span data-ttu-id="1d8ac-104">В любом реальном сценарии важно обеспечить безопасность приложений и служб.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-104">In any real-world scenario, securing applications and services is essential.</span></span> <span data-ttu-id="1d8ac-105">Безопасность охватывает три основные области:</span><span class="sxs-lookup"><span data-stu-id="1d8ac-105">Security covers three key areas:</span></span> 

* <span data-ttu-id="1d8ac-106">Шифрование сетевого трафика для предотвращения перехвата вредоносными злоумышленниками.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-106">Encrypting network traffic to prevent malicious hackers from intercepting it.</span></span>
* <span data-ttu-id="1d8ac-107">Проверка подлинности клиентов и серверов для установления удостоверения и доверия.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-107">Authenticating clients and servers to establish identity and trust.</span></span>
* <span data-ttu-id="1d8ac-108">Авторизация клиентов для управления доступом к системам и применения разрешений на основе удостоверения.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-108">Authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="1d8ac-109">*Проверка подлинности* важна для установления удостоверения клиента или сервера.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-109">*Authentication* is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="1d8ac-110">*Авторизация* связана с определением наличия у клиента разрешения на доступ к ресурсу или на выдачу команды.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-110">*Authorization* is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="1d8ac-111">В этой главе будут рассмотрены средства проверки подлинности и авторизации в gRPC для ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-111">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core.</span></span> <span data-ttu-id="1d8ac-112">Кроме того, в нем обсуждается Сетевая безопасность через TLS-шифрованные соединения.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-112">It will also discuss network security through TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="1d8ac-113">Проверка подлинности и авторизация WCF</span><span class="sxs-lookup"><span data-stu-id="1d8ac-113">WCF authentication and authorization</span></span>

<span data-ttu-id="1d8ac-114">В Windows Communication Foundation (WCF) проверка подлинности и авторизация была обработана различными способами в зависимости от используемых транспортов и привязок.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-114">In Windows Communication Foundation (WCF), authentication and authorization were handled in different ways, depending on the transports and bindings being used.</span></span> <span data-ttu-id="1d8ac-115">WCF поддерживала различные стандарты безопасности WS-\*.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-115">WCF supported various WS-\* security standards.</span></span> <span data-ttu-id="1d8ac-116">Она также поддерживала проверку подлинности Windows для служб HTTP, работающих в IIS или NetTCP Services между системами Windows.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-116">It also supported Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="1d8ac-117">Проверка подлинности и авторизация gRPC</span><span class="sxs-lookup"><span data-stu-id="1d8ac-117">gRPC authentication and authorization</span></span>

<span data-ttu-id="1d8ac-118">Проверка подлинности и авторизация gRPC работают на двух уровнях:</span><span class="sxs-lookup"><span data-stu-id="1d8ac-118">gRPC authentication and authorization works on two levels:</span></span>

* <span data-ttu-id="1d8ac-119">Проверка подлинности и авторизация на уровне вызовов обычно обрабатываются с помощью токенов, которые применяются в метаданных при вызове.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-119">Call-level authentication/authorization is usually handled through tokens that are applied in metadata when the call is made.</span></span> 
* <span data-ttu-id="1d8ac-120">При проверке подлинности на уровне канала используется сертификат клиента, который применяется на уровне подключения.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-120">Channel-level authentication uses a client certificate that's applied at the connection level.</span></span> <span data-ttu-id="1d8ac-121">Он также может включать учетные данные проверки подлинности или авторизации на уровне вызовов, которые будут применяться к каждому вызову в канале автоматически.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-121">It can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span> 

<span data-ttu-id="1d8ac-122">Для защиты службы можно использовать любой из этих механизмов или оба этих механизма.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-122">You can use either or both of these mechanisms to help secure your service.</span></span>

<span data-ttu-id="1d8ac-123">ASP.NET Core реализация gRPC поддерживает проверку подлинности и авторизацию с помощью большинства стандартных механизмов ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="1d8ac-123">The ASP.NET Core implementation of gRPC supports authentication and authorization through most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="1d8ac-124">Проверка подлинности вызова</span><span class="sxs-lookup"><span data-stu-id="1d8ac-124">Call authentication</span></span>
  - <span data-ttu-id="1d8ac-125">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1d8ac-125">Azure Active Directory</span></span>
  - <span data-ttu-id="1d8ac-126">IdentityServer</span><span class="sxs-lookup"><span data-stu-id="1d8ac-126">IdentityServer</span></span>
  - <span data-ttu-id="1d8ac-127">Токен носителя JWT</span><span class="sxs-lookup"><span data-stu-id="1d8ac-127">JWT Bearer Token</span></span>
  - <span data-ttu-id="1d8ac-128">OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="1d8ac-128">OAuth 2.0</span></span>
  - <span data-ttu-id="1d8ac-129">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="1d8ac-129">OpenID Connect</span></span>
  - <span data-ttu-id="1d8ac-130">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="1d8ac-130">WS-Federation</span></span>
- <span data-ttu-id="1d8ac-131">Проверка подлинности канала</span><span class="sxs-lookup"><span data-stu-id="1d8ac-131">Channel authentication</span></span>
  - <span data-ttu-id="1d8ac-132">Сертификат клиента</span><span class="sxs-lookup"><span data-stu-id="1d8ac-132">Client certificate</span></span>

<span data-ttu-id="1d8ac-133">Методы проверки подлинности вызовов основаны на *маркерах*.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-133">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="1d8ac-134">Единственное вещественное отличие состоит в том, как создаются маркеры и библиотеки, используемые для проверки маркеров в службе ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-134">The only real difference is how the tokens are generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="1d8ac-135">Дополнительные сведения см. в статье [Проверка подлинности и авторизация](/aspnet/core/grpc/authn-and-authz) .</span><span class="sxs-lookup"><span data-stu-id="1d8ac-135">For more information, see the [Authentication and authorization](/aspnet/core/grpc/authn-and-authz) article.</span></span>

> [!NOTE]
> <span data-ttu-id="1d8ac-136">Если вы используете gRPC через TLS-шифрованное подключение HTTP/2, весь трафик между клиентами и серверами шифруется, даже если не используется проверка подлинности на уровне канала.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-136">When you're using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="1d8ac-137">В этой главе показано, как применить учетные данные вызова и учетные данные канала к службе gRPC.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-137">This chapter will show how to apply call credentials and channel credentials to a gRPC service.</span></span> <span data-ttu-id="1d8ac-138">Также будет показано, как использовать учетные данные из клиента .NET Core gRPC для проверки подлинности в службе.</span><span class="sxs-lookup"><span data-stu-id="1d8ac-138">It will also show how to use credentials from a .NET Core gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1d8ac-139">[Назад](client-libraries.md)
>[Вперед](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="1d8ac-139">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
