---
title: Безопасность в приложениях gRPC - gRPC для разработчиков WCF
description: Обзор проверки подлинности и авторизации вызовов и каналов в gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 70cbf441bbc1b299b997f7d1f02bcd2bf7fde60c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147819"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="d42ba-103">Безопасность в приложениях gRPC</span><span class="sxs-lookup"><span data-stu-id="d42ba-103">Security in gRPC applications</span></span>

<span data-ttu-id="d42ba-104">В любом реальном сценарии защита приложений и служб имеет важное значение.</span><span class="sxs-lookup"><span data-stu-id="d42ba-104">In any real-world scenario, securing applications and services is essential.</span></span> <span data-ttu-id="d42ba-105">Безопасность охватывает три ключевые области:</span><span class="sxs-lookup"><span data-stu-id="d42ba-105">Security covers three key areas:</span></span>

* <span data-ttu-id="d42ba-106">Шифрование сетевого трафика, чтобы предотвратить перехват злоумышленниками.</span><span class="sxs-lookup"><span data-stu-id="d42ba-106">Encrypting network traffic to prevent malicious hackers from intercepting it.</span></span>
* <span data-ttu-id="d42ba-107">Проверка подлинности клиентов и серверов для установления идентичности и доверия.</span><span class="sxs-lookup"><span data-stu-id="d42ba-107">Authenticating clients and servers to establish identity and trust.</span></span>
* <span data-ttu-id="d42ba-108">Разрешение клиентам контролировать доступ к системам и применять разрешения на основе идентификации.</span><span class="sxs-lookup"><span data-stu-id="d42ba-108">Authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="d42ba-109">*Аутентификация* связана с установлением личности клиента или сервера.</span><span class="sxs-lookup"><span data-stu-id="d42ba-109">*Authentication* is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="d42ba-110">*Авторизация* связана с определением того, имеет ли клиент разрешение на доступ к ресурсу или выдать команду.</span><span class="sxs-lookup"><span data-stu-id="d42ba-110">*Authorization* is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="d42ba-111">Эта глава будет охватывать средства для проверки подлинности и авторизации в gRPC для ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="d42ba-111">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core.</span></span> <span data-ttu-id="d42ba-112">Он также будет обсуждать сетевую безопасность через TLS зашифрованных соединений.</span><span class="sxs-lookup"><span data-stu-id="d42ba-112">It will also discuss network security through TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="d42ba-113">Проверка подлинности и авторизации WCF</span><span class="sxs-lookup"><span data-stu-id="d42ba-113">WCF authentication and authorization</span></span>

<span data-ttu-id="d42ba-114">В Фонде связи Windows (WCF) аутентификация и авторизация обрабатываются по-разному, в зависимости от используемых транспортных средств и привязок.</span><span class="sxs-lookup"><span data-stu-id="d42ba-114">In Windows Communication Foundation (WCF), authentication and authorization were handled in different ways, depending on the transports and bindings being used.</span></span> <span data-ttu-id="d42ba-115">WCF поддерживает различные стандарты безопасности WS-.\*</span><span class="sxs-lookup"><span data-stu-id="d42ba-115">WCF supported various WS-\* security standards.</span></span> <span data-ttu-id="d42ba-116">Она также поддерживает аутентификацию Windows для служб HTTP, работающих в iIS или NetTCP между системами Windows.</span><span class="sxs-lookup"><span data-stu-id="d42ba-116">It also supported Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="d42ba-117">gRPC аутентификация и авторизация</span><span class="sxs-lookup"><span data-stu-id="d42ba-117">gRPC authentication and authorization</span></span>

<span data-ttu-id="d42ba-118">gRPC аутентификация и авторизация работает на двух уровнях:</span><span class="sxs-lookup"><span data-stu-id="d42ba-118">gRPC authentication and authorization works on two levels:</span></span>

* <span data-ttu-id="d42ba-119">Аутентификация/авторизация уровня вызова обычно обрабатывается через токены, которые применяются в метаданных при вызове.</span><span class="sxs-lookup"><span data-stu-id="d42ba-119">Call-level authentication/authorization is usually handled through tokens that are applied in metadata when the call is made.</span></span>
* <span data-ttu-id="d42ba-120">Аутентификация на уровне канала использует сертификат клиента, применяемый на уровне соединения.</span><span class="sxs-lookup"><span data-stu-id="d42ba-120">Channel-level authentication uses a client certificate that's applied at the connection level.</span></span> <span data-ttu-id="d42ba-121">Он также может включать в себя учетные данные аутентификации/авторизации уровня вызова, которые будут применяться к каждому вызову на канале автоматически.</span><span class="sxs-lookup"><span data-stu-id="d42ba-121">It can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span>

<span data-ttu-id="d42ba-122">Вы можете использовать один или оба этих механизма, чтобы помочь обезопасить свой сервис.</span><span class="sxs-lookup"><span data-stu-id="d42ba-122">You can use either or both of these mechanisms to help secure your service.</span></span>

<span data-ttu-id="d42ba-123">Внедрение ASP.NET Core gRPC поддерживает аутентификацию и авторизацию через большинство стандартных ASP.NET основных механизмов:</span><span class="sxs-lookup"><span data-stu-id="d42ba-123">The ASP.NET Core implementation of gRPC supports authentication and authorization through most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="d42ba-124">Вызов аутентификации</span><span class="sxs-lookup"><span data-stu-id="d42ba-124">Call authentication</span></span>
  - <span data-ttu-id="d42ba-125">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d42ba-125">Azure Active Directory</span></span>
  - <span data-ttu-id="d42ba-126">IdentityServer</span><span class="sxs-lookup"><span data-stu-id="d42ba-126">IdentityServer</span></span>
  - <span data-ttu-id="d42ba-127">JWT Bearer Токен</span><span class="sxs-lookup"><span data-stu-id="d42ba-127">JWT Bearer Token</span></span>
  - <span data-ttu-id="d42ba-128">OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="d42ba-128">OAuth 2.0</span></span>
  - <span data-ttu-id="d42ba-129">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="d42ba-129">OpenID Connect</span></span>
  - <span data-ttu-id="d42ba-130">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="d42ba-130">WS-Federation</span></span>
- <span data-ttu-id="d42ba-131">Проверка подлинности канала</span><span class="sxs-lookup"><span data-stu-id="d42ba-131">Channel authentication</span></span>
  - <span data-ttu-id="d42ba-132">Сертификат клиента</span><span class="sxs-lookup"><span data-stu-id="d42ba-132">Client certificate</span></span>

<span data-ttu-id="d42ba-133">Методы проверки подлинности вызовов основаны на *токенах.*</span><span class="sxs-lookup"><span data-stu-id="d42ba-133">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="d42ba-134">Единственное реальное различие заключается в том, как создаются токены и библиотеки, которые используются для проверки токенов в ASP.NET основной службе.</span><span class="sxs-lookup"><span data-stu-id="d42ba-134">The only real difference is how the tokens are generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="d42ba-135">Для получения дополнительной информации смотрите статью [«Аутентификация и авторизация».](/aspnet/core/grpc/authn-and-authz)</span><span class="sxs-lookup"><span data-stu-id="d42ba-135">For more information, see the [Authentication and authorization](/aspnet/core/grpc/authn-and-authz) article.</span></span>

> [!NOTE]
> <span data-ttu-id="d42ba-136">При использовании gRPC по подключению HTTP/2, зашифрованным, весь трафик между клиентами и серверами, даже если вы не используете аутентификацию на уровне канала.</span><span class="sxs-lookup"><span data-stu-id="d42ba-136">When you're using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="d42ba-137">В этой главе будет уотена, как применять учетные данные вызовов и учетные данные канала в службу gRPC.</span><span class="sxs-lookup"><span data-stu-id="d42ba-137">This chapter will show how to apply call credentials and channel credentials to a gRPC service.</span></span> <span data-ttu-id="d42ba-138">Он также покажет, как использовать учетные данные от клиента .NET Core gRPC для проверки подлинности с помощью службы.</span><span class="sxs-lookup"><span data-stu-id="d42ba-138">It will also show how to use credentials from a .NET Core gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d42ba-139">[Предыдущий](client-libraries.md)
>[Следующий](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="d42ba-139">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
