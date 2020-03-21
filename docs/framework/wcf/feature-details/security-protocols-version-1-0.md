---
title: Протоколы безопасности версии 1.0
ms.date: 03/30/2017
ms.assetid: ee3402d2-1076-410b-a3cb-fae0372bd7af
ms.openlocfilehash: 2014e1f6f8fefa89ed44bd820c3712617ff51470
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184522"
---
# <a name="security-protocols-version-10"></a><span data-ttu-id="795ec-102">Протоколы безопасности версии 1.0</span><span class="sxs-lookup"><span data-stu-id="795ec-102">Security Protocols version 1.0</span></span>
<span data-ttu-id="795ec-103">Протоколы WS-Security предоставляют механизмы обеспечения безопасности веб-служб, охватывающие все существующие требования к безопасности обмена сообщениями на предприятии.</span><span class="sxs-lookup"><span data-stu-id="795ec-103">The Web Services Security Protocols provide Web services security mechanisms that cover all existing enterprise messaging security requirements.</span></span> <span data-ttu-id="795ec-104">В этом разделе описывается версия 1.0 Windows Communication Foundation <xref:System.ServiceModel.Channels.SecurityBindingElement>(WCF) (реализована в ) для следующих протоколов безопасности Web-сервисов.</span><span class="sxs-lookup"><span data-stu-id="795ec-104">This section describes the Windows Communication Foundation (WCF) version 1.0 details (implemented in the <xref:System.ServiceModel.Channels.SecurityBindingElement>) for the following Web services security protocols.</span></span>  
  
|<span data-ttu-id="795ec-105">Спецификация/документ</span><span class="sxs-lookup"><span data-stu-id="795ec-105">Specification/Document</span></span>|<span data-ttu-id="795ec-106">Ссылка</span><span class="sxs-lookup"><span data-stu-id="795ec-106">Link</span></span>|  
|-|-|  
|<span data-ttu-id="795ec-107">WSS: SOAP Message Security 1,0</span><span class="sxs-lookup"><span data-stu-id="795ec-107">WSS: SOAP Message Security 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf>|
|<span data-ttu-id="795ec-108">WSS: Username Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="795ec-108">WSS: Username Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="795ec-109">WSS: X509 Token Profile 1,0</span><span class="sxs-lookup"><span data-stu-id="795ec-109">WSS: X509 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf>|
|<span data-ttu-id="795ec-110">WSS: SAML 1.1 Token Profile 1,0</span><span class="sxs-lookup"><span data-stu-id="795ec-110">WSS: SAML 1.1 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf>|
|<span data-ttu-id="795ec-111">WSS: SOAP Message Security 1.1</span><span class="sxs-lookup"><span data-stu-id="795ec-111">WSS: SOAP Message Security 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf>|
|<span data-ttu-id="795ec-112">WSS Username Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="795ec-112">WSS Username Token Profile 1.1</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="795ec-113">WSS: X.509 Token Profile 1,1</span><span class="sxs-lookup"><span data-stu-id="795ec-113">WSS: X.509 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf>|
|<span data-ttu-id="795ec-114">WSS: Kerberos Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="795ec-114">WSS: Kerberos Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf>|
|<span data-ttu-id="795ec-115">WSS: SAML 1.1 Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="795ec-115">WSS: SAML 1.1 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf>|
|<span data-ttu-id="795ec-116">WS-Secure Conversation</span><span class="sxs-lookup"><span data-stu-id="795ec-116">WS-Secure Conversation</span></span>|<https://specs.xmlsoap.org/ws/2005/02/sc/WS-SecureConversation.pdf>|
|<span data-ttu-id="795ec-117">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="795ec-117">WS-Trust</span></span>|<https://specs.xmlsoap.org/ws/2005/02/trust/ws-trust.pdf>|
|<span data-ttu-id="795ec-118">Замечания по применению.</span><span class="sxs-lookup"><span data-stu-id="795ec-118">Application Note:</span></span><br /><br /> <span data-ttu-id="795ec-119">Использование WS-Trust для подтверждения TLS</span><span class="sxs-lookup"><span data-stu-id="795ec-119">Using WS-Trust for TLS Handshake</span></span>|<span data-ttu-id="795ec-120">Готовится к публикации</span><span class="sxs-lookup"><span data-stu-id="795ec-120">To be published</span></span>|  
|<span data-ttu-id="795ec-121">Замечания по применению.</span><span class="sxs-lookup"><span data-stu-id="795ec-121">Application Note:</span></span><br /><br /> <span data-ttu-id="795ec-122">Использование WS-Trust для подтверждения SPNEGO</span><span class="sxs-lookup"><span data-stu-id="795ec-122">Using WS-Trust for SPNEGO</span></span>|<span data-ttu-id="795ec-123">Готовится к публикации</span><span class="sxs-lookup"><span data-stu-id="795ec-123">To be published</span></span>|  
|<span data-ttu-id="795ec-124">Замечания по применению.</span><span class="sxs-lookup"><span data-stu-id="795ec-124">Application Note:</span></span><br /><br /> <span data-ttu-id="795ec-125">Ссылки и идентификация конечной точки адресации веб-служб</span><span class="sxs-lookup"><span data-stu-id="795ec-125">Web Services Addressing Endpoint References And Identity</span></span>|<span data-ttu-id="795ec-126">Готовится к публикации</span><span class="sxs-lookup"><span data-stu-id="795ec-126">To be published</span></span>|  
|<span data-ttu-id="795ec-127">WS-SecurityPolicy 1.1</span><span class="sxs-lookup"><span data-stu-id="795ec-127">WS-SecurityPolicy 1.1</span></span><br /><br /> <span data-ttu-id="795ec-128">(2005/07)</span><span class="sxs-lookup"><span data-stu-id="795ec-128">(2005/07)</span></span>|<https://specs.xmlsoap.org/ws/2005/07/securitypolicy/ws-securitypolicy.pdf><br /><br /> <span data-ttu-id="795ec-129">с поправками, внесенными [errata,](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) представленными техническому комитету OASIS WS-SX</span><span class="sxs-lookup"><span data-stu-id="795ec-129">as amended by [errata](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) submitted to OASIS WS-SX Technical Committee</span></span> |  
  
 <span data-ttu-id="795ec-130">WCF, версия 1, предоставляет 17 режимов аутентификации, которые могут быть использованы в качестве основы для конфигурации безопасности Web-сервисов.</span><span class="sxs-lookup"><span data-stu-id="795ec-130">WCF, version 1, provides 17 authentication modes that can be used as the basis for Web services security configuration.</span></span> <span data-ttu-id="795ec-131">Каждый из режимов оптимизирован для того или иного типичного набора требований к развертыванию, например следующих:</span><span class="sxs-lookup"><span data-stu-id="795ec-131">Each mode is optimized for a common set of deployment requirements, such as:</span></span>  
  
- <span data-ttu-id="795ec-132">учетные данные, используемые для проверки подлинности клиента и службы;</span><span class="sxs-lookup"><span data-stu-id="795ec-132">Credentials used to authenticate client and service.</span></span>  
  
- <span data-ttu-id="795ec-133">механизмы обеспечения безопасности на уровне сообщений или транспорта;</span><span class="sxs-lookup"><span data-stu-id="795ec-133">Message or transport security protection mechanisms.</span></span>  
  
- <span data-ttu-id="795ec-134">шаблоны обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="795ec-134">Message exchange patterns.</span></span>  
  
|<span data-ttu-id="795ec-135">Режим проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="795ec-135">Authentication Mode</span></span>|<span data-ttu-id="795ec-136">Аутентификация клиента</span><span class="sxs-lookup"><span data-stu-id="795ec-136">Client Authentication</span></span>|<span data-ttu-id="795ec-137">Проверка подлинности сервера</span><span class="sxs-lookup"><span data-stu-id="795ec-137">Server Authentication</span></span>|<span data-ttu-id="795ec-138">Режим</span><span class="sxs-lookup"><span data-stu-id="795ec-138">Mode</span></span>|  
|-------------------------|---------------------------|---------------------------|----------|  
|<span data-ttu-id="795ec-139">UserNameOverTransport</span><span class="sxs-lookup"><span data-stu-id="795ec-139">UserNameOverTransport</span></span>|<span data-ttu-id="795ec-140">Имя пользователя/пароль</span><span class="sxs-lookup"><span data-stu-id="795ec-140">User name/password</span></span>|<span data-ttu-id="795ec-141">X509</span><span class="sxs-lookup"><span data-stu-id="795ec-141">X509</span></span>|<span data-ttu-id="795ec-142">Транспортировка</span><span class="sxs-lookup"><span data-stu-id="795ec-142">Transport</span></span>|  
|<span data-ttu-id="795ec-143">CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="795ec-143">CertificateOverTransport</span></span>|<span data-ttu-id="795ec-144">X509</span><span class="sxs-lookup"><span data-stu-id="795ec-144">X509</span></span>|<span data-ttu-id="795ec-145">X509</span><span class="sxs-lookup"><span data-stu-id="795ec-145">X509</span></span>|<span data-ttu-id="795ec-146">Транспортировка</span><span class="sxs-lookup"><span data-stu-id="795ec-146">Transport</span></span>|  
|<span data-ttu-id="795ec-147">KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="795ec-147">KerberosOverTransport</span></span>|<span data-ttu-id="795ec-148">Windows</span><span class="sxs-lookup"><span data-stu-id="795ec-148">Windows</span></span>|<span data-ttu-id="795ec-149">X509</span><span class="sxs-lookup"><span data-stu-id="795ec-149">X509</span></span>|<span data-ttu-id="795ec-150">Транспортировка</span><span class="sxs-lookup"><span data-stu-id="795ec-150">Transport</span></span>|  
|<span data-ttu-id="795ec-151">IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="795ec-151">IssuedTokenOverTransport</span></span>|<span data-ttu-id="795ec-152">Федеративные</span><span class="sxs-lookup"><span data-stu-id="795ec-152">Federated</span></span>|<span data-ttu-id="795ec-153">X509</span><span class="sxs-lookup"><span data-stu-id="795ec-153">X509</span></span>|<span data-ttu-id="795ec-154">Транспортировка</span><span class="sxs-lookup"><span data-stu-id="795ec-154">Transport</span></span>|  
|<span data-ttu-id="795ec-155">SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="795ec-155">SspiNegotiatedOverTransport</span></span>|<span data-ttu-id="795ec-156">Согласование Windows Sspi</span><span class="sxs-lookup"><span data-stu-id="795ec-156">Windows Sspi Negotiated</span></span>|<span data-ttu-id="795ec-157">Согласование Windows Sspi</span><span class="sxs-lookup"><span data-stu-id="795ec-157">Windows Sspi Negotiated</span></span>|<span data-ttu-id="795ec-158">Транспортировка</span><span class="sxs-lookup"><span data-stu-id="795ec-158">Transport</span></span>|  
|<span data-ttu-id="795ec-159">AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="795ec-159">AnonymousForCertificate</span></span>|<span data-ttu-id="795ec-160">None</span><span class="sxs-lookup"><span data-stu-id="795ec-160">None</span></span>|<span data-ttu-id="795ec-161">X509</span><span class="sxs-lookup"><span data-stu-id="795ec-161">X509</span></span>|<span data-ttu-id="795ec-162">Сообщение</span><span class="sxs-lookup"><span data-stu-id="795ec-162">Message</span></span>|  
|<span data-ttu-id="795ec-163">UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="795ec-163">UserNameForCertificate</span></span>|<span data-ttu-id="795ec-164">Имя пользователя/пароль</span><span class="sxs-lookup"><span data-stu-id="795ec-164">User name/password</span></span>|<span data-ttu-id="795ec-165">X509</span><span class="sxs-lookup"><span data-stu-id="795ec-165">X509</span></span>|<span data-ttu-id="795ec-166">Сообщение</span><span class="sxs-lookup"><span data-stu-id="795ec-166">Message</span></span>|  
|<span data-ttu-id="795ec-167">MutualCertificate</span><span class="sxs-lookup"><span data-stu-id="795ec-167">MutualCertificate</span></span>|<span data-ttu-id="795ec-168">X509</span><span class="sxs-lookup"><span data-stu-id="795ec-168">X509</span></span>|<span data-ttu-id="795ec-169">X509</span><span class="sxs-lookup"><span data-stu-id="795ec-169">X509</span></span>|<span data-ttu-id="795ec-170">Сообщение</span><span class="sxs-lookup"><span data-stu-id="795ec-170">Message</span></span>|  
|<span data-ttu-id="795ec-171">MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="795ec-171">MutualCertificateDuplex</span></span>|<span data-ttu-id="795ec-172">X509</span><span class="sxs-lookup"><span data-stu-id="795ec-172">X509</span></span>|<span data-ttu-id="795ec-173">X509</span><span class="sxs-lookup"><span data-stu-id="795ec-173">X509</span></span>|<span data-ttu-id="795ec-174">Сообщение</span><span class="sxs-lookup"><span data-stu-id="795ec-174">Message</span></span>|  
|<span data-ttu-id="795ec-175">IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="795ec-175">IssuedTokenForCertificate</span></span>|<span data-ttu-id="795ec-176">Федеративные</span><span class="sxs-lookup"><span data-stu-id="795ec-176">Federated</span></span>|<span data-ttu-id="795ec-177">X509</span><span class="sxs-lookup"><span data-stu-id="795ec-177">X509</span></span>|<span data-ttu-id="795ec-178">Сообщение</span><span class="sxs-lookup"><span data-stu-id="795ec-178">Message</span></span>|  
|<span data-ttu-id="795ec-179">Kerberos</span><span class="sxs-lookup"><span data-stu-id="795ec-179">Kerberos</span></span>|<span data-ttu-id="795ec-180">Windows</span><span class="sxs-lookup"><span data-stu-id="795ec-180">Windows</span></span>|<span data-ttu-id="795ec-181">Windows</span><span class="sxs-lookup"><span data-stu-id="795ec-181">Windows</span></span>|<span data-ttu-id="795ec-182">Сообщение</span><span class="sxs-lookup"><span data-stu-id="795ec-182">Message</span></span>|  
|<span data-ttu-id="795ec-183">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="795ec-183">IssuedToken</span></span>|<span data-ttu-id="795ec-184">Федеративные</span><span class="sxs-lookup"><span data-stu-id="795ec-184">Federated</span></span>|<span data-ttu-id="795ec-185">Федеративные</span><span class="sxs-lookup"><span data-stu-id="795ec-185">Federated</span></span>|<span data-ttu-id="795ec-186">Сообщение</span><span class="sxs-lookup"><span data-stu-id="795ec-186">Message</span></span>|  
|<span data-ttu-id="795ec-187">SspiNegotiation</span><span class="sxs-lookup"><span data-stu-id="795ec-187">SspiNegotiated</span></span>|<span data-ttu-id="795ec-188">Согласование Windows Sspi</span><span class="sxs-lookup"><span data-stu-id="795ec-188">Windows Sspi Negotiated</span></span>|<span data-ttu-id="795ec-189">Согласование Windows Sspi</span><span class="sxs-lookup"><span data-stu-id="795ec-189">Windows Sspi Negotiated</span></span>|<span data-ttu-id="795ec-190">Сообщение</span><span class="sxs-lookup"><span data-stu-id="795ec-190">Message</span></span>|  
|<span data-ttu-id="795ec-191">AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="795ec-191">AnonymousForSslNegotiated</span></span>|<span data-ttu-id="795ec-192">None</span><span class="sxs-lookup"><span data-stu-id="795ec-192">None</span></span>|<span data-ttu-id="795ec-193">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="795ec-193">X509, TLS-Nego</span></span>|<span data-ttu-id="795ec-194">Сообщение</span><span class="sxs-lookup"><span data-stu-id="795ec-194">Message</span></span>|  
|<span data-ttu-id="795ec-195">UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="795ec-195">UserNameForSslNegotiated</span></span>|<span data-ttu-id="795ec-196">Имя пользователя/пароль</span><span class="sxs-lookup"><span data-stu-id="795ec-196">User name/password</span></span>|<span data-ttu-id="795ec-197">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="795ec-197">X509, TLS-Nego</span></span>|<span data-ttu-id="795ec-198">Сообщение</span><span class="sxs-lookup"><span data-stu-id="795ec-198">Message</span></span>|  
|<span data-ttu-id="795ec-199">MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="795ec-199">MutualSslNegotiated</span></span>|<span data-ttu-id="795ec-200">X509</span><span class="sxs-lookup"><span data-stu-id="795ec-200">X509</span></span>|<span data-ttu-id="795ec-201">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="795ec-201">X509, TLS-Nego</span></span>|<span data-ttu-id="795ec-202">Сообщение</span><span class="sxs-lookup"><span data-stu-id="795ec-202">Message</span></span>|  
|<span data-ttu-id="795ec-203">IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="795ec-203">IssuedTokenForSslNegotiated</span></span>|<span data-ttu-id="795ec-204">Федеративные</span><span class="sxs-lookup"><span data-stu-id="795ec-204">Federated</span></span>|<span data-ttu-id="795ec-205">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="795ec-205">X509, TLS-Nego</span></span>|<span data-ttu-id="795ec-206">Сообщение</span><span class="sxs-lookup"><span data-stu-id="795ec-206">Message</span></span>|  
  
 <span data-ttu-id="795ec-207">Конечные точки, использующие такие режимы проверки подлинности, могут выражать свои требования безопасности с помощью WS-SecurityPolicy (WS-SP).</span><span class="sxs-lookup"><span data-stu-id="795ec-207">Endpoints using such authentication modes can express their security requirements using WS-SecurityPolicy (WS-SP).</span></span> <span data-ttu-id="795ec-208">В этом документе описывается структура заголовка безопасности и инфраструктурные сообщения для каждого режима проверки подлинности, а также приводятся примеры политик и сообщений.</span><span class="sxs-lookup"><span data-stu-id="795ec-208">This document describes the structure of security header and infrastructure messages for each authentication mode and provides examples of policies and messages.</span></span>  
  
 <span data-ttu-id="795ec-209">WCF использует WS-SecureConversation для обеспечения надежной поддержки сеансов для защиты обмена мультисообщениями между приложениями.</span><span class="sxs-lookup"><span data-stu-id="795ec-209">WCF leverages WS-SecureConversation to provide secure sessions support to protect multi-message exchanges between applications.</span></span>  <span data-ttu-id="795ec-210">Сведения о реализации см. ниже в подразделе "Безопасные сеансы".</span><span class="sxs-lookup"><span data-stu-id="795ec-210">See "Secure Sessions" below for implementation details.</span></span>  
  
 <span data-ttu-id="795ec-211">В дополнение к режимам аутентификации, WCF предоставляет настройки для управления общими механизмами защиты, которые применяются к большинству режимов проверки подлинности на основе сообщений, например: порядок операций шифрования по сравнению с шифрованием, наборы алгоритмов, производные ключевые элементы , и подтверждение подписи.</span><span class="sxs-lookup"><span data-stu-id="795ec-211">In addition to authentication modes, WCF provides settings to control common protection mechanisms that apply to most message security-based authentication modes, for example: order of signature versus encryption operations, algorithm suites, key derivation, and signature confirmation.</span></span>  
  
 <span data-ttu-id="795ec-212">В данном документе используются перечисленные ниже префиксы и пространства имен.</span><span class="sxs-lookup"><span data-stu-id="795ec-212">The following prefixes and namespaces are used in this document.</span></span>  
  
|<span data-ttu-id="795ec-213">Prefix</span><span class="sxs-lookup"><span data-stu-id="795ec-213">Prefix</span></span>|<span data-ttu-id="795ec-214">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="795ec-214">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="795ec-215">s</span><span class="sxs-lookup"><span data-stu-id="795ec-215">s</span></span>|<http://www.w3.org/2003/05/soap-envelope/>|
|<span data-ttu-id="795ec-216">sp</span><span class="sxs-lookup"><span data-stu-id="795ec-216">sp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/>|
|<span data-ttu-id="795ec-217">a</span><span class="sxs-lookup"><span data-stu-id="795ec-217">a</span></span>|<http://www.w3.org/2005/08/addressing>|  
|<span data-ttu-id="795ec-218">wsse</span><span class="sxs-lookup"><span data-stu-id="795ec-218">wsse</span></span>|<span data-ttu-id="795ec-219">Подлежит определению - универсальный код ресурса (URI) OASIS WSS 1,0</span><span class="sxs-lookup"><span data-stu-id="795ec-219">TBD – OASIS WSS 1.0 URI</span></span>|  
|<span data-ttu-id="795ec-220">wsse11</span><span class="sxs-lookup"><span data-stu-id="795ec-220">wsse11</span></span>|<span data-ttu-id="795ec-221">Подлежит определению - универсальный код ресурса (URI) OASIS WSS 1.1</span><span class="sxs-lookup"><span data-stu-id="795ec-221">TBD – OASIS WSS 1.1 URI</span></span>|  
|<span data-ttu-id="795ec-222">wsu</span><span class="sxs-lookup"><span data-stu-id="795ec-222">wsu</span></span>|<span data-ttu-id="795ec-223">Подлежит определению - универсальный код ресурса (URI) OASIS WSS 1.0 Utility</span><span class="sxs-lookup"><span data-stu-id="795ec-223">TBD – OASIS WSS 1.0 Utility URI</span></span>|  
|<span data-ttu-id="795ec-224">ds</span><span class="sxs-lookup"><span data-stu-id="795ec-224">ds</span></span>|<span data-ttu-id="795ec-225">Подлежит определению - универсальный код ресурса (URI) W3C XMLDSig</span><span class="sxs-lookup"><span data-stu-id="795ec-225">TBD – W3C XMLDSig URI</span></span>|  
|<span data-ttu-id="795ec-226">wst</span><span class="sxs-lookup"><span data-stu-id="795ec-226">wst</span></span>|<span data-ttu-id="795ec-227">Подлежит определению - универсальный код ресурса (URI) WS-Trust 2005/02</span><span class="sxs-lookup"><span data-stu-id="795ec-227">TBD – WS-Trust 2005/02 URI</span></span>|  
|<span data-ttu-id="795ec-228">wssc</span><span class="sxs-lookup"><span data-stu-id="795ec-228">wssc</span></span>|<span data-ttu-id="795ec-229">Подлежит определению - универсальный код ресурса (URI) WS-SecureConversation 2005/02</span><span class="sxs-lookup"><span data-stu-id="795ec-229">TBD – WS-SecureConversation 2005/02 URI</span></span>|  
|<span data-ttu-id="795ec-230">wsaw</span><span class="sxs-lookup"><span data-stu-id="795ec-230">wsaw</span></span>|<span data-ttu-id="795ec-231">Подлежит определению - пространство имен политики WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="795ec-231">TBD - WS-Addressing policy namespace</span></span>|  
|<span data-ttu-id="795ec-232">wsp</span><span class="sxs-lookup"><span data-stu-id="795ec-232">wsp</span></span>|<http://schemas.xmlsoap.org/ws/2004/09/policy>|  
|<span data-ttu-id="795ec-233">mssp</span><span class="sxs-lookup"><span data-stu-id="795ec-233">mssp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy>|
  
## <a name="1-token-profiles"></a><span data-ttu-id="795ec-234">1. Профили токенов</span><span class="sxs-lookup"><span data-stu-id="795ec-234">1. Token Profiles</span></span>  
 <span data-ttu-id="795ec-235">В спецификациях WS-Security учетные данные представляются в виде токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="795ec-235">Web Services Security specifications represent credential as security tokens.</span></span> <span data-ttu-id="795ec-236">WCF поддерживает следующие типы токенов:</span><span class="sxs-lookup"><span data-stu-id="795ec-236">WCF supports the following token types:</span></span>  
  
### <a name="11-usernametoken"></a><span data-ttu-id="795ec-237">1.1 Маркер UsernameToken</span><span class="sxs-lookup"><span data-stu-id="795ec-237">1.1 UsernameToken</span></span>  
 <span data-ttu-id="795ec-238">WCF следует профилям UsernameToken10 и UsernameToken11с со следующими ограничениями:</span><span class="sxs-lookup"><span data-stu-id="795ec-238">WCF follows UsernameToken10 and UsernameToken11 profiles with the following constraints:</span></span>  
  
 <span data-ttu-id="795ec-239">R1101 Атрибут PasswordType элемента UsernameToken\Password ДОЛЖЕН быть либо опущен, либо иметь значение #PasswordText (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="795ec-239">R1101 PasswordType attribute on UsernameToken\Password element MUST be either omitted or have value #PasswordText (default).</span></span>  
  
 <span data-ttu-id="795ec-240">Можно реализовать #PasswordDigest с помощью расширяемости.</span><span class="sxs-lookup"><span data-stu-id="795ec-240">One can implement the #PasswordDigest using extensibility.</span></span> <span data-ttu-id="795ec-241">Замечено, что #PasswordDigest часто ошибочно считается достаточно безопасным механизмом защиты пароля.</span><span class="sxs-lookup"><span data-stu-id="795ec-241">It has been observed that #PasswordDigest was often mistaken to be a secure enough password protection mechanism.</span></span> <span data-ttu-id="795ec-242">Однако #PasswordDigest не может служить заменой шифрованию маркера UsernameToken.</span><span class="sxs-lookup"><span data-stu-id="795ec-242">But #PasswordDigest cannot serve as a substitute for encryption of the UsernameToken.</span></span> <span data-ttu-id="795ec-243">Основной целью #PasswordDigest является защита от атак с повторением.</span><span class="sxs-lookup"><span data-stu-id="795ec-243">The primary goal of #PasswordDigest is protection against replay attacks.</span></span> <span data-ttu-id="795ec-244">В режимах проверки подлинности WCF угрозы повторного воспроизведения смягчаются с помощью подписей сообщений.</span><span class="sxs-lookup"><span data-stu-id="795ec-244">In WCF authentication modes, replay attack threats are mitigated by using message signatures.</span></span>  
  
 <span data-ttu-id="795ec-245">B1102 WCF никогда не излучает Nonce и не создает подэлементы UsernameToken.</span><span class="sxs-lookup"><span data-stu-id="795ec-245">B1102 WCF never emits Nonce and Created sub-elements of the UsernameToken.</span></span>  
  
 <span data-ttu-id="795ec-246">Эти подэлементы предназначены для упрощения обнаружения атак с повторением.</span><span class="sxs-lookup"><span data-stu-id="795ec-246">These sub-elements are intended to help replay detection.</span></span> <span data-ttu-id="795ec-247">Вместо этого WCF использует подписи сообщений.</span><span class="sxs-lookup"><span data-stu-id="795ec-247">WCF uses message signatures instead.</span></span>  
  
 <span data-ttu-id="795ec-248">В профиле OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) введена возможность создания производного ключа из пароля.</span><span class="sxs-lookup"><span data-stu-id="795ec-248">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) introduced key derivation from password feature.</span></span>  
  
 <span data-ttu-id="795ec-249">B1103 Пароль UsernameToken НЕ ДОЛЖЕН использоваться для создания производного ключа и, следовательно, для операций шифрования.</span><span class="sxs-lookup"><span data-stu-id="795ec-249">B1103 UsernameToken password MUST not be used for key derivation and therefore for cryptographic operations.</span></span>  
  
 <span data-ttu-id="795ec-250">Обоснование: пароли обычно считаются слишком слабой защитой, для того чтобы использовать их в операциях шифрования.</span><span class="sxs-lookup"><span data-stu-id="795ec-250">Rationale: passwords are generally considered too weak to be used for cryptographic operations.</span></span>  
  
### <a name="12-x509-token"></a><span data-ttu-id="795ec-251">1.2 Маркер X509</span><span class="sxs-lookup"><span data-stu-id="795ec-251">1.2 X509 Token</span></span>  
 <span data-ttu-id="795ec-252">WCF поддерживает сертификаты X509v3 в качестве типока и следует X509TokenProfile1.0 и X509TokenProfile1.1 со следующими ограничениями:</span><span class="sxs-lookup"><span data-stu-id="795ec-252">WCF supports X509v3 certificates as a credential type and follows X509TokenProfile1.0 and X509TokenProfile1.1 with the following constraints:</span></span>  
  
 <span data-ttu-id="795ec-253">R1201 Атрибут ValueType элемента BinarySecurityToken должен иметь значение #X509v3, если он содержит сертификат X509v3.</span><span class="sxs-lookup"><span data-stu-id="795ec-253">R1201 The ValueType attribute on the BinarySecurityToken element must have value #X509v3 when it contains an X509v3 certificate.</span></span>  
  
 <span data-ttu-id="795ec-254">Профили WSS X509 Token Profile 1.0 и 1.1 также определяют типы значений #X509PKIPathv1 и #PKCS7.</span><span class="sxs-lookup"><span data-stu-id="795ec-254">WSS X509 Token Profile 1.0 and 1.1 define also #X509PKIPathv1 and #PKCS7 as value types.</span></span> <span data-ttu-id="795ec-255">WCF не поддерживает эти типы.</span><span class="sxs-lookup"><span data-stu-id="795ec-255">WCF does not support these types.</span></span>  
  
 <span data-ttu-id="795ec-256">R1202 Если в сертификате X509 имеется расширение SubjectKeyIdentifier (SKI), для внешних ссылок на маркер должен использоваться wsse:KeyIdentifier, со значением #X509SubjectKeyIdentifier атрибута ValueType и содержащий значение расширения SKI сертификата в кодировке base64.</span><span class="sxs-lookup"><span data-stu-id="795ec-256">R1202 If a SubjectKeyIdentifier (SKI) extension is present in an X509 certificate, wsse:KeyIdentifier should be used for external references to the token, with the ValueType attribute as #X509SubjectKeyIdentifier and its content the base64-encoded value of certificate's SKI extension.</span></span>  
  
 <span data-ttu-id="795ec-257">Ссылки SKI имеют множество реализаций и зарекомендовали себя как внешний ссылочный тип с широкими возможностями совместимости.</span><span class="sxs-lookup"><span data-stu-id="795ec-257">SKI references are widely implemented and proven to be a highly interoperable external reference type.</span></span>  
  
 <span data-ttu-id="795ec-258">R1203 Внешняя ссылка на маркер безопасности X509 НЕ ДОЛЖНА использовать ds:X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="795ec-258">R1203 An external Reference to X509 Security Token SHOULD NOT use ds:X509IssuerSerial.</span></span>  
  
 <span data-ttu-id="795ec-259">R1204 Если используется профиль X509TokenProfile1.1, внешняя ссылка на маркер безопасности X509 ДОЛЖНА использовать отпечаток, введенный в протоколе WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="795ec-259">R1204 If X509TokenProfile1.1 is in use, an external reference to X509 Security Token SHOULD use the thumbprint introduced by WS-Security 1.1.</span></span>  
  
 <span data-ttu-id="795ec-260">WCF поддерживает X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="795ec-260">WCF supports X509IssuerSerial.</span></span> <span data-ttu-id="795ec-261">Однако Есть проблемы совместимостью с X509IssuerSerial: WCF использует строку для сравнения двух значений X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="795ec-261">However There are interoperability issues with X509IssuerSerial: WCF uses a string to compare two values of X509IssuerSerial.</span></span> <span data-ttu-id="795ec-262">Поэтому, если один перезаказ компонентов имя субъекта и отправляет в службу WCF ссылку на сертификат, он не может быть найден.</span><span class="sxs-lookup"><span data-stu-id="795ec-262">Therefore if one reorders components of the Subject Name and sends to an WCF service a reference to a certificate, it may not be found.</span></span>  
  
### <a name="13-kerberos-token"></a><span data-ttu-id="795ec-263">1.3 Маркер Kerberos</span><span class="sxs-lookup"><span data-stu-id="795ec-263">1.3 Kerberos Token</span></span>  
 <span data-ttu-id="795ec-264">WCF поддерживает KerberosTokenProfile1.1 для проверки подлинности Windows со следующими ограничениями:</span><span class="sxs-lookup"><span data-stu-id="795ec-264">WCF supports KerberosTokenProfile1.1 for the purpose of Windows authentication with the following constraints:</span></span>  
  
 <span data-ttu-id="795ec-265">R1301 Маркер Kerberos должен содержать значение GSS в оболочке Kerberos v4 AP_REQ, как определено в GSS_API и спецификации Kerberos, и должен иметь атрибут ValueType со значением #GSS_Kerberosv5_AP_REQ.</span><span class="sxs-lookup"><span data-stu-id="795ec-265">R1301 A Kerberos Token must carry the value of a GSS wrapped Kerberos v4 AP_REQ as defined in GSS_API and the Kerberos specification, and must have the ValueType attribute with the value #GSS_Kerberosv5_AP_REQ.</span></span>  
  
 <span data-ttu-id="795ec-266">WCF использует GSS обернутые Kerberos AP-RE, а не голые AP-RE.</span><span class="sxs-lookup"><span data-stu-id="795ec-266">WCF uses GSS wrapped Kerberos AP-REQ, not a bare AP-REQ.</span></span> <span data-ttu-id="795ec-267">Это рекомендуется в целях безопасности.</span><span class="sxs-lookup"><span data-stu-id="795ec-267">This is a security best practice.</span></span>  
  
### <a name="14-saml-v11-token"></a><span data-ttu-id="795ec-268">1.4 Маркер SAML 1.1</span><span class="sxs-lookup"><span data-stu-id="795ec-268">1.4 SAML v1.1 Token</span></span>  
 <span data-ttu-id="795ec-269">WCF поддерживает профили ТОкенов WSS SAML 1.0 и 1.1 для токенов SAML v1.1.</span><span class="sxs-lookup"><span data-stu-id="795ec-269">WCF supports WSS SAML Token profiles 1.0 and 1.1 for SAML v1.1 tokens.</span></span> <span data-ttu-id="795ec-270">Возможна реализация других версий форматов маркеров SAML.</span><span class="sxs-lookup"><span data-stu-id="795ec-270">It is possible to implement other versions of SAML token formats.</span></span>  
  
### <a name="15-security-context-token"></a><span data-ttu-id="795ec-271">1.5 Маркер контекста безопасности</span><span class="sxs-lookup"><span data-stu-id="795ec-271">1.5 Security Context Token</span></span>  
 <span data-ttu-id="795ec-272">WCF поддерживает токен контекста безопасности (SCT), представленный в WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="795ec-272">WCF supports the Security Context Token (SCT) introduced in WS-SecureConversation.</span></span> <span data-ttu-id="795ec-273">Маркер контекста безопасности служит для представления контекста безопасности, установленного в спецификации SecureConversation, а также протоколов двоичного согласования TLS и SSPI, описываемых ниже.</span><span class="sxs-lookup"><span data-stu-id="795ec-273">SCT is used to represent a security context established in SecureConversation as well as the binary negotiation protocols TLS and SSPI, described below.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="795ec-274">2. Общие параметры безопасности сообщений</span><span class="sxs-lookup"><span data-stu-id="795ec-274">2. Common Message Security Parameters</span></span>  
  
### <a name="21-timestamp"></a><span data-ttu-id="795ec-275">2.1 TimeStamp</span><span class="sxs-lookup"><span data-stu-id="795ec-275">2.1 TimeStamp</span></span>  
 <span data-ttu-id="795ec-276">Наличие отметки времени определяется с помощью свойства <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> класса <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="795ec-276">Timestamp presence is controlled using the <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> property of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span> <span data-ttu-id="795ec-277">WCF всегда serializes wsse:TimeStamp с wsse:Created и wsse:Expires поля.</span><span class="sxs-lookup"><span data-stu-id="795ec-277">WCF always serializes wsse:TimeStamp with wsse:Created and wsse:Expires fields.</span></span> <span data-ttu-id="795ec-278">Если используется подписывание, wsse:TimeStamp всегда подписывается.</span><span class="sxs-lookup"><span data-stu-id="795ec-278">The wsse:TimeStamp is always signed when signing is used.</span></span>  
  
### <a name="22-protection-order"></a><span data-ttu-id="795ec-279">2.2. Порядок защиты</span><span class="sxs-lookup"><span data-stu-id="795ec-279">2.2 Protection Order</span></span>  
 <span data-ttu-id="795ec-280">WCF поддерживает приказ о защите сообщений "Подписать перед шифрованием" и "Шифсование перед знаком" (Политика безопасности 1.1).</span><span class="sxs-lookup"><span data-stu-id="795ec-280">WCF supports the message protection order "Sign Before Encrypt" and "Encrypt Before Sign" (Security Policy 1.1).</span></span> <span data-ttu-id="795ec-281">По ряду причин рекомендуется использовать порядок «подпись перед шифрованием», в том числе по следующим причинам: если не используется механизм WS-Security 1.1 SignatureConfirmation, сообщения, защищенные в порядке «шифрование перед подписью», подвержены атакам подмены подписи и при подписывании зашифрованного содержимого сложнее производить аудит.</span><span class="sxs-lookup"><span data-stu-id="795ec-281">"Sign Before Encrypt" is recommended for reasons including: messages protected with Encrypt Before Sign are open to signature substitution attacks unless the WS-Security 1.1 SignatureConfirmation mechanism is used, and a signature over encrypted content makes auditing harder.</span></span>  
  
### <a name="23-signature-protection"></a><span data-ttu-id="795ec-282">2.3 Защита сигнатуры</span><span class="sxs-lookup"><span data-stu-id="795ec-282">2.3 Signature Protection</span></span>  
 <span data-ttu-id="795ec-283">Если используется порядок "шифрование перед сигнатурой", рекомендуется защищать сигнатура, чтобы предотвратить атаки методом подбора для угадывания зашифрованного содержимого или ключа сигнатуры (особенно при использовании пользовательского маркера с ненадежным ключевым материалом).</span><span class="sxs-lookup"><span data-stu-id="795ec-283">When Encrypt Before Sign is used, it is recommended to protect the signature to prevent brute force attacks for guessing the encrypted content or the signing key (especially when a custom token is used with weak key material).</span></span>  
  
### <a name="24-algorithm-suite"></a><span data-ttu-id="795ec-284">2.4 Набор алгоритмов</span><span class="sxs-lookup"><span data-stu-id="795ec-284">2.4 Algorithm Suite</span></span>  
 <span data-ttu-id="795ec-285">WCF поддерживает все наборы алгоритмов, перечисленные в политике безопасности 1.1.</span><span class="sxs-lookup"><span data-stu-id="795ec-285">WCF supports all algorithm suites listed in Security Policy 1.1.</span></span>  
  
### <a name="25-key-derivation"></a><span data-ttu-id="795ec-286">2.5 Формирование ключей</span><span class="sxs-lookup"><span data-stu-id="795ec-286">2.5 Key Derivation</span></span>  
 <span data-ttu-id="795ec-287">WCF использует "Ключевая производние для симметричных ключей", как описано в WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="795ec-287">WCF uses "Key Derivation for symmetric keys" as described in WS-SecureConversation.</span></span>  
  
### <a name="26-signature-confirmation"></a><span data-ttu-id="795ec-288">2.6 Подтверждение сигнатуры</span><span class="sxs-lookup"><span data-stu-id="795ec-288">2.6 Signature Confirmation</span></span>  
 <span data-ttu-id="795ec-289">Подтверждение сигнатуры может использоваться в качестве защиты от атак типа «злоумышленник в середине», чтобы защитить набор подписей.</span><span class="sxs-lookup"><span data-stu-id="795ec-289">Signature confirmation can be as protection from middle man attacks to protect the set of signatures.</span></span>  
  
### <a name="27-security-header-layout"></a><span data-ttu-id="795ec-290">2.7 Структура заголовка безопасности</span><span class="sxs-lookup"><span data-stu-id="795ec-290">2.7 Security Header Layout</span></span>  
 <span data-ttu-id="795ec-291">Каждый режим проверки подлинности описывает определенную структуру заголовка безопасности.</span><span class="sxs-lookup"><span data-stu-id="795ec-291">Each authentication mode describes a certain layout for the security header.</span></span> <span data-ttu-id="795ec-292">Элементы в заголовке безопасности полуупорядочены.</span><span class="sxs-lookup"><span data-stu-id="795ec-292">Elements within the security header are semi-ordered.</span></span> <span data-ttu-id="795ec-293">Чтобы определить порядок дочерних элементов заголовка безопасности, в спецификации WS-Security Policy определены следующие режимы структуры заголовка безопасности:</span><span class="sxs-lookup"><span data-stu-id="795ec-293">To define the order of security header child elements, WS-Security Policy defines the following security header layout modes:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="795ec-294">Strict</span><span class="sxs-lookup"><span data-stu-id="795ec-294">Strict</span></span>|<span data-ttu-id="795ec-295">Элементы добавляются в заголовок безопасности в соответствии с правилами нумерованной структуры, описанными в разделе 7.7.1 спецификаций Security Policy, на основе общего принципа "объявить перед использованием".</span><span class="sxs-lookup"><span data-stu-id="795ec-295">Items are added to the security header following the numbered layout rules described in Security Policy section 7.7.1 according to a general principle of "declare before use".</span></span>|  
|<span data-ttu-id="795ec-296">Lax</span><span class="sxs-lookup"><span data-stu-id="795ec-296">Lax</span></span>|<span data-ttu-id="795ec-297">Элементы добавляются в заголовок безопасности в любом порядке, отвечающем требованиям безопасности сообщений WSS: SOAP Message Security.</span><span class="sxs-lookup"><span data-stu-id="795ec-297">Items are added to the security header in any order that conforms to WSS: SOAP Message Security.</span></span>|  
|<span data-ttu-id="795ec-298">LaxTimestampFirst</span><span class="sxs-lookup"><span data-stu-id="795ec-298">LaxTimestampFirst</span></span>|<span data-ttu-id="795ec-299">Аналогично Lax, но первым элементом в заголовке безопасности должен быть элемент wsse:Timestamp.</span><span class="sxs-lookup"><span data-stu-id="795ec-299">Same as Lax except that the first item in the security header must be a wsse:Timestamp</span></span>|  
|<span data-ttu-id="795ec-300">LaxTimestampLast</span><span class="sxs-lookup"><span data-stu-id="795ec-300">LaxTimestampLast</span></span>|<span data-ttu-id="795ec-301">Аналогично Lax, но последним элементом в заголовке безопасности должен быть элемент wsse:Timestamp.</span><span class="sxs-lookup"><span data-stu-id="795ec-301">Same as lax except that the last item in the security header must be a wsse:Timestamp</span></span>|  
  
 <span data-ttu-id="795ec-302">WCF поддерживает все четыре режима для компоновки заголовка безопасности.</span><span class="sxs-lookup"><span data-stu-id="795ec-302">WCF supports all four modes for security header layout.</span></span> <span data-ttu-id="795ec-303">В приведенных ниже структурах заголовков безопасности и примерах сообщений для режимов проверки подлинности используется режим "Strict".</span><span class="sxs-lookup"><span data-stu-id="795ec-303">Security header structure and message examples for authentication modes below follow the "Strict" mode.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="795ec-304">2. Общие параметры безопасности сообщений</span><span class="sxs-lookup"><span data-stu-id="795ec-304">2. Common Message Security Parameters</span></span>  
 <span data-ttu-id="795ec-305">В этом подразделе приведены примеры политик для каждого режима проверки подлинности, а также примеры, показывающие структуру заголовка безопасности в сообщениях, которыми обмениваются клиент и служба.</span><span class="sxs-lookup"><span data-stu-id="795ec-305">This section provides example policies for each authentication mode along with examples showing security header structure in messages exchanged by client and service.</span></span>  
  
### <a name="61-transport-protection"></a><span data-ttu-id="795ec-306">6.1 Защита транспорта</span><span class="sxs-lookup"><span data-stu-id="795ec-306">6.1 Transport Protection</span></span>  
 <span data-ttu-id="795ec-307">WCF предоставляет пять режимов аутентификации, которые используют безопасный транспорт для защиты сообщений; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport и SspiNegotiatedOverTransport.</span><span class="sxs-lookup"><span data-stu-id="795ec-307">WCF provides five authentication modes that use secure transport to protect messages; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport and SspiNegotiatedOverTransport.</span></span>  
  
 <span data-ttu-id="795ec-308">Эти режимы проверки подлинности построены с использованием привязок транспорта, описанных в спецификации SecurityPolicy.</span><span class="sxs-lookup"><span data-stu-id="795ec-308">These authentication modes are constructed using the transport binding described in SecurityPolicy.</span></span> <span data-ttu-id="795ec-309">Для режима проверки подлинности UserNameOverTransport маркер UsernameToken является подписанным поддерживающим маркером.</span><span class="sxs-lookup"><span data-stu-id="795ec-309">For the UserNameOverTransport authentication mode the UsernameToken is a signed supporting token.</span></span> <span data-ttu-id="795ec-310">Для других режимов проверки подлинности этот маркер является подписанным подтверждающим маркером.</span><span class="sxs-lookup"><span data-stu-id="795ec-310">For the other authentication modes the token appears as a signed endorsing token.</span></span> <span data-ttu-id="795ec-311">В приложениях C.1.2 и C.1.3 спецификации SecurityPolicy подробно описана структура заголовка безопасности.</span><span class="sxs-lookup"><span data-stu-id="795ec-311">Appendix C.1.2 and C.1.3 of SecurityPolicy describe the security header layout in detail.</span></span> <span data-ttu-id="795ec-312">В приведенных ниже примерах заголовки безопасности для определенного режима проверки подлинности показаны со структурой Strict.</span><span class="sxs-lookup"><span data-stu-id="795ec-312">The following example security headers show the Strict layout for a given authentication mode.</span></span>  
  
 <span data-ttu-id="795ec-313">Свойство Derived Keys для маркеров во всех случаях имеет значение "false".</span><span class="sxs-lookup"><span data-stu-id="795ec-313">The value of the "Derived Keys" property for the tokens in all cases is "false".</span></span>  
  
 <span data-ttu-id="795ec-314">Различные свойства привязок транспорта имеют следующие значения:</span><span class="sxs-lookup"><span data-stu-id="795ec-314">The values of the various properties of the transport binding are as follows:</span></span>  
  
 <span data-ttu-id="795ec-315">Отметка времени: true</span><span class="sxs-lookup"><span data-stu-id="795ec-315">Timestamp: true</span></span>  
  
 <span data-ttu-id="795ec-316">Структура заголовка безопасности: Strict</span><span class="sxs-lookup"><span data-stu-id="795ec-316">Security Header Layout: Strict</span></span>  
  
 <span data-ttu-id="795ec-317">Набор алгоритмов: Basic256</span><span class="sxs-lookup"><span data-stu-id="795ec-317">Algorithm Suite: Basic256</span></span>  
  
#### <a name="611-usernameovertransport"></a><span data-ttu-id="795ec-318">6.1.1 UsernameOverTransport</span><span class="sxs-lookup"><span data-stu-id="795ec-318">6.1.1 UsernameOverTransport</span></span>  
 <span data-ttu-id="795ec-319">В этом режиме проверка подлинности клиента осуществляется с использованием маркера Username, который доступен на уровне SOAP в качестве подписанного поддерживающего маркера, всегда отправляемого от инициатора получателю.</span><span class="sxs-lookup"><span data-stu-id="795ec-319">With this authentication mode, the client authenticates with a Username Token which appears at the SOAP layer as a signed supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="795ec-320">Служба проходит проверку подлинности с использованием сертификата X.509 на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="795ec-320">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="795ec-321">Используется привязка транспорта.</span><span class="sxs-lookup"><span data-stu-id="795ec-321">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="795ec-322">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-322">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='UsernameOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:SignedSupportingTokens >  
        <wsp:Policy>  
          <sp:UsernameToken
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:WssUsernameToken10 />
            </wsp:Policy>  
          </sp:UsernameToken>  
        </wsp:Policy>  
      </sp:SignedSupportingTokens>  
      <sp:Wss11 >  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10 >  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="795ec-323">Структура заголовка безопасности</span><span class="sxs-lookup"><span data-stu-id="795ec-323">Security Header Layout</span></span>  
  
 <span data-ttu-id="795ec-324">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-324">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:UsernameToken ... >  
  ...  
  </wsse:UsernameToken>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-325">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-325">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="612-certificateovertransport"></a><span data-ttu-id="795ec-326">6.1.2 CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="795ec-326">6.1.2 CertificateOverTransport</span></span>  
 <span data-ttu-id="795ec-327">В этом режиме проверка подлинности клиента осуществляется с использованием сертификата X.509, который доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера, всегда отправляемого от инициатора получателю.</span><span class="sxs-lookup"><span data-stu-id="795ec-327">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="795ec-328">Служба проходит проверку подлинности с использованием сертификата X.509 на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="795ec-328">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="795ec-329">Используется привязка транспорта.</span><span class="sxs-lookup"><span data-stu-id="795ec-329">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="795ec-330">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-330">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CertificateOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding xmlns:sp='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy' >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
             <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:RequireThumbprintReference />
              <sp:WssX509V3Token10 />
            </wsp:Policy>  
          </sp:X509Token>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="795ec-331">Структура заголовка безопасности</span><span class="sxs-lookup"><span data-stu-id="795ec-331">Security Header Layout</span></span>  
  
 <span data-ttu-id="795ec-332">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-332">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wse:Timestamp u:Id="_0">  
  ...  
  </wse:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-333">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-333">Response</span></span>  
  
```xml  
<o:Security>  
  <u:Timestamp u:Id="_0">  
  ...  
  </u:Timestamp>  
</o:Security>  
```  
  
#### <a name="613-issuedtokenovertransport"></a><span data-ttu-id="795ec-334">6.1.3 IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="795ec-334">6.1.3 IssuedTokenOverTransport</span></span>  
 <span data-ttu-id="795ec-335">В этом режиме проверки подлинности клиент не проходит как таковую проверку подлинности на стороне службы; вместо этого он предоставляет маркер, выданный службой маркеров безопасности (STS) и подтверждает знание общего ключа.</span><span class="sxs-lookup"><span data-stu-id="795ec-335">With this authentication mode the client does not authenticate to the service, as such, but rather presents a token issued by a Security Token Service (STS) and proves knowledge of a shared key.</span></span> <span data-ttu-id="795ec-336">Выданный маркер доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера, всегда отправляемого от инициатора получателю.</span><span class="sxs-lookup"><span data-stu-id="795ec-336">The issued token appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="795ec-337">Служба проходит проверку подлинности с использованием сертификата X.509 на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="795ec-337">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="795ec-338">Используется привязка транспорта.</span><span class="sxs-lookup"><span data-stu-id="795ec-338">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="795ec-339">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-339">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='IssuedTokenOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:IssuedToken
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <sp:RequestSecurityTokenTemplate>  
              <wst:KeyType>  
              http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
              </wst:KeyType>
            </sp:RequestSecurityTokenTemplate>  
            <wsp:Policy>  
              <sp:RequireInternalReference />
            </wsp:Policy>  
          </sp:IssuedToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="795ec-340">Структура заголовка безопасности</span><span class="sxs-lookup"><span data-stu-id="795ec-340">Security Header Layout</span></span>  
  
 <span data-ttu-id="795ec-341">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-341">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion ...>  
  ...  
  </saml:Assertion>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-342">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-342">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="614-kerberosovertransport"></a><span data-ttu-id="795ec-343">6.1.4 KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="795ec-343">6.1.4 KerberosOverTransport</span></span>  
 <span data-ttu-id="795ec-344">В этом режиме проверка подлинности клиента на стороне службы осуществляется с использованием билета Kerberos.</span><span class="sxs-lookup"><span data-stu-id="795ec-344">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="795ec-345">Маркер Kerberos доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера.</span><span class="sxs-lookup"><span data-stu-id="795ec-345">The Kerberos token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="795ec-346">Служба проходит проверку подлинности с использованием сертификата X.509 на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="795ec-346">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="795ec-347">Используется привязка транспорта.</span><span class="sxs-lookup"><span data-stu-id="795ec-347">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="795ec-348">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-348">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='KerberosOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:KerberosToken  
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
            <wsp:Policy>  
              <sp:WssGssKerberosV5ApReqToken11 />
            </wsp:Policy>  
          </sp:KerberosToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="795ec-349">Структура заголовка безопасности</span><span class="sxs-lookup"><span data-stu-id="795ec-349">Security Header Layout</span></span>  
  
 <span data-ttu-id="795ec-350">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-350">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken ValueType="...#GSS_Kerberosv5_AP_REQ">  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-351">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-351">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="615-sspinegotiatedovertransport"></a><span data-ttu-id="795ec-352">6.1.5 SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="795ec-352">6.1.5 SspiNegotiatedOverTransport</span></span>  
 <span data-ttu-id="795ec-353">В этом режиме для проверки подлинности клиента и сервера используется протокол согласования.</span><span class="sxs-lookup"><span data-stu-id="795ec-353">With this mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="795ec-354">Если это возможно, используется протокол Kerberos, в противном случае - протокол NTLM.</span><span class="sxs-lookup"><span data-stu-id="795ec-354">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="795ec-355">Итоговый маркер контекста безопасности доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера, всегда отправляемого от инициатора получателю.</span><span class="sxs-lookup"><span data-stu-id="795ec-355">The resulting SCT appears at the SOAP layer as an endorsing supporting token that is always sent from initiator to recipient.</span></span> <span data-ttu-id="795ec-356">Служба проходит дополнительную проверку подлинности на транспортном уровне с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="795ec-356">The service is additionally authenticated at the transport layer by an X.509 certificate.</span></span> <span data-ttu-id="795ec-357">Используется привязка транспорта.</span><span class="sxs-lookup"><span data-stu-id="795ec-357">The binding used is a transport binding.</span></span> <span data-ttu-id="795ec-358">"SPNEGO" (переговоры) описывает, как WCF использует двоичный протокол переговоров SSPI с WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="795ec-358">"SPNEGO" (negotiation) describes how WCF uses SSPI binary negotiation protocol with WS-Trust.</span></span> <span data-ttu-id="795ec-359">В этом разделе приведены примеры заголовков безопасности после установления маркера контекста безопасности с помощью подтверждения SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="795ec-359">Security header examples in this section are after the SCT has been established through the SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="795ec-360">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-360">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SspiNegotiatedOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:SpnegoContextToken
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy />
          </sp:SpnegoContextToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples"></a><span data-ttu-id="795ec-361">Примеры заголовков безопасности</span><span class="sxs-lookup"><span data-stu-id="795ec-361">Security Header Examples</span></span>  
 <span data-ttu-id="795ec-362">После установления маркера контекста безопасности с помощью подтверждения SPNEGO при использовании двоичного согласования WS-Trust заголовки безопасности в сообщениях приложения имеют следующую структуру.</span><span class="sxs-lookup"><span data-stu-id="795ec-362">Once the Security Context Token is established through SPNEGO handshake using WS-Trust Binary Negotiation, the application messages have security headers with the following structure.</span></span>  
  
 <span data-ttu-id="795ec-363">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-363">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:SecurityContextToken u:Id="uuid-2202746a-7725-453d-8747-809cb718dab0-29" >  
  ...  
  </wssc:SecurityContextToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-364">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-364">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
### <a name="62-using-x509-certificates-for-service-authentication"></a><span data-ttu-id="795ec-365">6.2 Использование сертификатов X.509 для проверки подлинности службы</span><span class="sxs-lookup"><span data-stu-id="795ec-365">6.2 Using X.509 Certificates for Service Authentication</span></span>  
 <span data-ttu-id="795ec-366">В этом разделе рассматриваются следующие режимы проверки подлинности: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate и IssuedTokenForCertificate.</span><span class="sxs-lookup"><span data-stu-id="795ec-366">This section describes the following authentication modes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate and IssuedTokenForCertificate.</span></span>  
  
#### <a name="621-mutualcertificate-wss10"></a><span data-ttu-id="795ec-367">6.2.1 MutualCertificate WSS1.0</span><span class="sxs-lookup"><span data-stu-id="795ec-367">6.2.1 MutualCertificate WSS1.0</span></span>  
 <span data-ttu-id="795ec-368">В этом режиме проверка подлинности клиента осуществляется с использованием сертификата X.509, который доступен на уровне SOAP в качестве маркера инициатора.</span><span class="sxs-lookup"><span data-stu-id="795ec-368">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="795ec-369">Служба также проходит проверку подлинности с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="795ec-369">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="795ec-370">Используется асимметричная привязка со следующими значениями свойств.</span><span class="sxs-lookup"><span data-stu-id="795ec-370">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="795ec-371">Маркер инициатора: сертификат X.509 клиента, задан режим включения …/IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="795ec-371">Initiator Token: the client’s X.509 certificate, with inclusion mode set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="795ec-372">Маркер получателя: сертификат X.509 сервера, задан режим включения …/IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="795ec-372">Recipient Token: Server’s X.509 Certificate, with inclusion mode is set …/IncludeToken/Never</span></span>  
  
 <span data-ttu-id="795ec-373">Защита маркера: False</span><span class="sxs-lookup"><span data-stu-id="795ec-373">Token Protection: False</span></span>  
  
 <span data-ttu-id="795ec-374">Сигнатуры всего заголовка и тела: True</span><span class="sxs-lookup"><span data-stu-id="795ec-374">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="795ec-375">Порядок защиты: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="795ec-375">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="795ec-376">Шифрование подписи: True</span><span class="sxs-lookup"><span data-stu-id="795ec-376">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="795ec-377">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-377">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificate_WSS10_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="795ec-378">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="795ec-378">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="795ec-379">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-379">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-380">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-380">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-381">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="795ec-381">Security Header Examples: EncryptBeforeSign</span></span>  
  
 <span data-ttu-id="795ec-382">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-382">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-383">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-383">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="622-mutualcertificateduplex"></a><span data-ttu-id="795ec-384">6.2.2 MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="795ec-384">6.2.2 MutualCertificateDuplex</span></span>  
 <span data-ttu-id="795ec-385">В этом режиме проверка подлинности клиента осуществляется с использованием сертификата X.509, который доступен на уровне SOAP в качестве маркера инициатора.</span><span class="sxs-lookup"><span data-stu-id="795ec-385">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="795ec-386">Служба также проходит проверку подлинности с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="795ec-386">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="795ec-387">Используется асимметричная привязка со следующими значениями свойств.</span><span class="sxs-lookup"><span data-stu-id="795ec-387">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="795ec-388">Маркер инициатора: сертификат X.509 клиента, задан режим включения …/IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="795ec-388">Initiator Token: Client’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="795ec-389">Маркер получателя: сертификат X.509 сервера, задан режим включения …/IncludeToken/AlwaysToInitiator</span><span class="sxs-lookup"><span data-stu-id="795ec-389">Recipient Token: Server’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToInitiator</span></span>  
  
 <span data-ttu-id="795ec-390">Защита маркера: False</span><span class="sxs-lookup"><span data-stu-id="795ec-390">Token Protection: False</span></span>  
  
 <span data-ttu-id="795ec-391">Сигнатуры всего заголовка и тела: True</span><span class="sxs-lookup"><span data-stu-id="795ec-391">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="795ec-392">Порядок защиты: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="795ec-392">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="795ec-393">Шифрование подписи: True</span><span class="sxs-lookup"><span data-stu-id="795ec-393">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="795ec-394">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-394">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificateDuplex_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToInitiator' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="795ec-395">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="795ec-395">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="795ec-396">Запрос и ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-396">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="795ec-397">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="795ec-397">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="795ec-398">Запрос и ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-398">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="623-using-symmetricbinding-with-x509-service-authentication"></a><span data-ttu-id="795ec-399">6.2.3 Использование SymmetricBinding с проверкой подлинности службы X.509</span><span class="sxs-lookup"><span data-stu-id="795ec-399">6.2.3 Using SymmetricBinding with X.509 Service Authentication</span></span>  
 <span data-ttu-id="795ec-400">Спецификация "WSS10" обеспечивает ограниченную поддержку сценариев с маркерами X509.</span><span class="sxs-lookup"><span data-stu-id="795ec-400">"WSS10" provided limited support for scenarios with X509 tokens.</span></span> <span data-ttu-id="795ec-401">Например, в этой версии не было способа обеспечить защиту сообщений сигнатурой и шифрованием, используя только маркер X509 службы.</span><span class="sxs-lookup"><span data-stu-id="795ec-401">For example, there was no way to provide signature and encryption protection for messages using only service X509 token.</span></span> <span data-ttu-id="795ec-402">В спецификации "WSS11" вводится использование EncryptedKey в качестве симметричного маркера.</span><span class="sxs-lookup"><span data-stu-id="795ec-402">"WSS11" introduced the usage of EncryptedKey as a symmetric token.</span></span> <span data-ttu-id="795ec-403">Теперь временный ключ, зашифрованный для сертификата X.509 службы, может использоваться для защиты как сообщений запроса, так и сообщений ответа.</span><span class="sxs-lookup"><span data-stu-id="795ec-403">Now a temporary key encrypted for the service's X.509 certificate could be used for both request and response messages protection.</span></span> <span data-ttu-id="795ec-404">Эта схема используется в режимах проверки подлинности, описанных ниже в разделе 6.4.</span><span class="sxs-lookup"><span data-stu-id="795ec-404">The authentication modes described in the section 6.4 below use this pattern.</span></span>  
  
 <span data-ttu-id="795ec-405">В спецификации WS-SecurityPolicy эта схема описывается с помощью привязки SymmetricBinding с маркером X509 службы в качестве маркера защиты.</span><span class="sxs-lookup"><span data-stu-id="795ec-405">WS-SecurityPolicy describes this pattern using SymmetricBinding with Service X509 token as the protection token.</span></span>  
  
 <span data-ttu-id="795ec-406">В режимах проверки подлинности AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 и IssuedTokenForCertificate используется аналогичный экземпляр sp:SymmetricBinding со следующими значениями свойств.</span><span class="sxs-lookup"><span data-stu-id="795ec-406">Authentication modes AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 and IssuedTokenForCertificate all use a similar instance of sp:SymmetricBinding with the following property values:</span></span>  
  
 <span data-ttu-id="795ec-407">Токен защиты: сертификат X.509 сервера, задан режим включения …/IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="795ec-407">Protection Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="795ec-408">Защита маркера: False</span><span class="sxs-lookup"><span data-stu-id="795ec-408">Token Protection: False</span></span>  
  
 <span data-ttu-id="795ec-409">Сигнатуры всего заголовка и тела: True</span><span class="sxs-lookup"><span data-stu-id="795ec-409">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="795ec-410">Порядок защиты: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="795ec-410">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="795ec-411">Шифрование подписи: True</span><span class="sxs-lookup"><span data-stu-id="795ec-411">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="795ec-412">Перечисленные выше режимы проверки подлинности различаются только используемыми поддерживающими маркерами.</span><span class="sxs-lookup"><span data-stu-id="795ec-412">The above authentication modes only differ by the supporting tokens they use.</span></span> <span data-ttu-id="795ec-413">В режиме AnonymousForCertificate поддерживающие маркеры отсутствуют, в режиме MutualCertificate (WSS 1.1) сертификат X509 клиента используется как подтверждающие поддерживающие маркеры, в режиме UserNameForCertificate маркер UserName используется как подписанный поддерживающий маркер, а в режиме IssuedTokenForCertificate выданный маркер используется как подтверждающий поддерживающий маркер.</span><span class="sxs-lookup"><span data-stu-id="795ec-413">AnonymousForCertificate does not have any supporting tokens, MutualCertificate WSS 1.1 has the client’s X509 certificate as an endorsing supporting tokens, UserNameForCertificate has a UserName Token as a signed supporting token and IssuedTokenForCertificate has the issued token as an endorsing supporting token.</span></span>  
  
 <span data-ttu-id="795ec-414">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-414">Policy</span></span>  
  
 <span data-ttu-id="795ec-415">Симметричная привязка</span><span class="sxs-lookup"><span data-stu-id="795ec-415">Symmetric Binding</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SymmetricCert_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:RequireThumbprintReference />
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />  
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting Token Assertions appear here -->  
      ...  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
          <sp:RequireSignatureConfirmation />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="624-anonymousforcertificate"></a><span data-ttu-id="795ec-416">6.2.4 AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="795ec-416">6.2.4 AnonymousForCertificate</span></span>  
 <span data-ttu-id="795ec-417">В этом режиме проверки подлинности клиент является анонимным, а проверка подлинности службы осуществляется с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="795ec-417">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="795ec-418">Используется экземпляр симметричной привязки, как описано в разделе 6.4.2.</span><span class="sxs-lookup"><span data-stu-id="795ec-418">The binding used is an instance of symmetric binding as described in 6.4.2.</span></span>  
  
 <span data-ttu-id="795ec-419">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-419">Policy</span></span>  
  
 <span data-ttu-id="795ec-420">Сведения о привязке см. в пункте «Политика» раздела 6.2.3</span><span class="sxs-lookup"><span data-stu-id="795ec-420">See "Policy" in 6.2.3 above for binding details</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="795ec-421">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="795ec-421">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="795ec-422">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-422">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-423">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-423">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="795ec-424">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="795ec-424">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="795ec-425">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-425">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-426">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-426">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="625-usernameforcertificate"></a><span data-ttu-id="795ec-427">6.2.5 UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="795ec-427">6.2.5 UserNameForCertificate</span></span>  
 <span data-ttu-id="795ec-428">В этом режиме проверка подлинности клиента в службе осуществляется с использованием маркера Username, который доступен на уровне SOAP в качестве подписанного поддерживающего маркера.</span><span class="sxs-lookup"><span data-stu-id="795ec-428">With this authentication mode the client authenticates to the service using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="795ec-429">Проверка подлинности службы на стороне клиента осуществляется с помощью сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="795ec-429">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="795ec-430">Используется симметричная привязка, в которой маркер защиты создан с помощью ключа клиента и зашифрован с помощью открытого ключа службы.</span><span class="sxs-lookup"><span data-stu-id="795ec-430">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="795ec-431">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-431">Policy</span></span>  
  
 <span data-ttu-id="795ec-432">Сведения о привязке см. в пункте «Политика» раздела 6.2.3</span><span class="sxs-lookup"><span data-stu-id="795ec-432">See "Policy" in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="795ec-433">Подписанный поддерживающий маркер</span><span class="sxs-lookup"><span data-stu-id="795ec-433">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="795ec-434">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="795ec-434">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="795ec-435">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-435">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-436">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-436">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="795ec-437">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="795ec-437">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="795ec-438">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-438">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-439">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-439">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="626-mutualcertificate-wss-11"></a><span data-ttu-id="795ec-440">6.2.6 MutualCertificate (WSS 1.1)</span><span class="sxs-lookup"><span data-stu-id="795ec-440">6.2.6 MutualCertificate (WSS 1.1)</span></span>  
 <span data-ttu-id="795ec-441">В этом режиме проверка подлинности клиента осуществляется с использованием сертификата X.509, который доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера.</span><span class="sxs-lookup"><span data-stu-id="795ec-441">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="795ec-442">Служба также проходит проверку подлинности с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="795ec-442">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="795ec-443">Используется симметричная привязка, в которой маркер защиты создан с помощью ключа клиента и зашифрован с помощью открытого ключа службы.</span><span class="sxs-lookup"><span data-stu-id="795ec-443">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="795ec-444">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-444">Policy</span></span>  
  
 <span data-ttu-id="795ec-445">Сведения о привязке см. в пункте «Политика» раздела 6.2.3</span><span class="sxs-lookup"><span data-stu-id="795ec-445">See Policy in 6.2.3 for binding details</span></span>  
  
 <span data-ttu-id="795ec-446">Подтверждающий поддерживающий маркер</span><span class="sxs-lookup"><span data-stu-id="795ec-446">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />
        <sp:WssX509V3Token10 />
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="795ec-447">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="795ec-447">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="795ec-448">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-448">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-449">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-449">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="795ec-450">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="795ec-450">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="795ec-451">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-451">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-452">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-452">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="627-issuedtokenforcertificate"></a><span data-ttu-id="795ec-453">6.2.7 IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="795ec-453">6.2.7 IssuedTokenForCertificate</span></span>  
 <span data-ttu-id="795ec-454">В этом режиме проверки подлинности клиент не проходит как таковую проверку подлинности на стороне службы; вместо этого он предоставляет маркер, выданный службой маркеров безопасности и подтверждает знание общего ключа.</span><span class="sxs-lookup"><span data-stu-id="795ec-454">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by a STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="795ec-455">Выданный маркер доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера.</span><span class="sxs-lookup"><span data-stu-id="795ec-455">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="795ec-456">Проверка подлинности службы на стороне клиента осуществляется с помощью сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="795ec-456">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="795ec-457">Используется симметричная привязка, в которой маркер защиты создан с помощью ключа клиента и зашифрован с помощью открытого ключа службы.</span><span class="sxs-lookup"><span data-stu-id="795ec-457">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="795ec-458">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-458">Policy</span></span>  
  
 <span data-ttu-id="795ec-459">Сведения о привязке см. в пункте «Политика» раздела 6.2.3</span><span class="sxs-lookup"><span data-stu-id="795ec-459">See Policy in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="795ec-460">Подтверждающий поддерживающий маркер</span><span class="sxs-lookup"><span data-stu-id="795ec-460">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
       </wst:KeyType>  
     </sp:RequestSecurityTokenTemplate>  
     <wsp:Policy>  
       <sp:RequireDerivedKeys />
       <sp:RequireInternalReference />
     </wsp:Policy>  
   </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="795ec-461">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="795ec-461">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="795ec-462">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-462">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-463">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-463">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="795ec-464">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="795ec-464">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="795ec-465">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-465">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-466">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-466">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
## <a name="63-kerberos"></a><span data-ttu-id="795ec-467">6.3 Kerberos</span><span class="sxs-lookup"><span data-stu-id="795ec-467">6.3 Kerberos</span></span>  
 <span data-ttu-id="795ec-468">В этом режиме проверка подлинности клиента на стороне службы осуществляется с использованием билета Kerberos.</span><span class="sxs-lookup"><span data-stu-id="795ec-468">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="795ec-469">Этот же билет обеспечивает проверку подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="795ec-469">That same ticket also provides server authentication.</span></span> <span data-ttu-id="795ec-470">Используется симметричная привязка со следующими свойствами.</span><span class="sxs-lookup"><span data-stu-id="795ec-470">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="795ec-471">Токен защиты: билет kerberos, задан режим включения …/IncludeToken/Once</span><span class="sxs-lookup"><span data-stu-id="795ec-471">Protection Token: Kerberos Ticket, inclusion mode is set to .../IncludeToken/Once</span></span>  
<span data-ttu-id="795ec-472">Защита маркера: False</span><span class="sxs-lookup"><span data-stu-id="795ec-472">Token Protection: False</span></span>  
  
 <span data-ttu-id="795ec-473">Сигнатуры всего заголовка и тела: True</span><span class="sxs-lookup"><span data-stu-id="795ec-473">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="795ec-474">Порядок защиты: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="795ec-474">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="795ec-475">Шифрование подписи: True</span><span class="sxs-lookup"><span data-stu-id="795ec-475">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="795ec-476">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-476">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='Kerberos_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:KerberosToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:WssGssKerberosV5ApReqToken11 />
                </wsp:Policy>  
              </sp:KerberosToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="795ec-477">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="795ec-477">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="795ec-478">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-478">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-479">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-479">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="795ec-480">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="795ec-480">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="795ec-481">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-481">Request</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-482">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-482">Response</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
#### <a name="64-issuedtoken"></a><span data-ttu-id="795ec-483">6.4 IssuedToken</span><span class="sxs-lookup"><span data-stu-id="795ec-483">6.4 IssuedToken</span></span>  
 <span data-ttu-id="795ec-484">В этом режиме проверки подлинности клиент не проходит как таковую проверку подлинности на стороне службы; вместо этого клиент предоставляет маркер, выданный службой маркеров безопасности и подтверждает знание общего ключа.</span><span class="sxs-lookup"><span data-stu-id="795ec-484">With this authentication mode the client does not authenticate to the service, as such, rather the client presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="795ec-485">Служба не проходит как таковую проверку подлинности на стороне клиента, но служба маркеров безопасности шифрует общий ключ как часть выдаваемого маркера, чтобы только служба могла расшифровать этот ключ.</span><span class="sxs-lookup"><span data-stu-id="795ec-485">The service is not authenticated to the client, as such, instead the STS encrypts the shared key as part of the issued token such that only the service can decrypt the key.</span></span> <span data-ttu-id="795ec-486">Используется симметричная привязка со следующими свойствами.</span><span class="sxs-lookup"><span data-stu-id="795ec-486">The binding used is as symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="795ec-487">Токен защиты: выданный токен, задан режим включения .../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="795ec-487">Protection Token: Issued Token, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="795ec-488">Защита маркера: False</span><span class="sxs-lookup"><span data-stu-id="795ec-488">Token Protection: False</span></span>  
  
 <span data-ttu-id="795ec-489">Сигнатуры всего заголовка и тела: True</span><span class="sxs-lookup"><span data-stu-id="795ec-489">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="795ec-490">Порядок защиты: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="795ec-490">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="795ec-491">Шифрование подписи: True</span><span class="sxs-lookup"><span data-stu-id="795ec-491">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="795ec-492">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-492">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple3_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <sp:RequestSecurityTokenTemplate>  
                  <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
                  </wst:KeyType>
                </sp:RequestSecurityTokenTemplate>  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:RequireInternalReference />
                </wsp:Policy>  
              </sp:IssuedToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="795ec-493">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="795ec-493">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="795ec-494">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-494">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-495">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-495">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="795ec-496">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="795ec-496">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="795ec-497">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-497">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-498">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-498">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="65-using-sslnegotiated-for-service-authentication"></a><span data-ttu-id="795ec-499">6.5 Использование SslNegotiated для проверки подлинности службы</span><span class="sxs-lookup"><span data-stu-id="795ec-499">6.5 Using SslNegotiated for Service Authentication</span></span>  
 <span data-ttu-id="795ec-500">В этом разделе рассматривается группа режимов проверки подлинности, в которых используется симметричная привязка с маркером защиты, являющимся маркером контекста безопасности в соответствии со спецификацией WS-SecureConversation (WS-SC), значение ключа которого согласовывается путем выполнения протокола TLS с помощью сообщений RST/RSTR спецификации WS-Trust (WS-T).</span><span class="sxs-lookup"><span data-stu-id="795ec-500">This section describes a group of authentication modes that use a symmetric binding with the protection token being a Security Context Token per WS-SecureConversation (WS-SC) whose key value is negotiated by executing the TLS protocol over WS-Trust (WS-T) RST/RSTR messages.</span></span> <span data-ttu-id="795ec-501">Сведения о реализации подтверждения TLS с помощью спецификации WS-Trust приведены в спецификации TLSNEGO.</span><span class="sxs-lookup"><span data-stu-id="795ec-501">Details of the TLS handshake implementation using WS-Trust are described in TLSNEGO.</span></span> <span data-ttu-id="795ec-502">В приведенных ниже примерах сообщений предполагается, что маркер контекста безопасности со связанным контекстом безопасности уже установлен путем подтверждения.</span><span class="sxs-lookup"><span data-stu-id="795ec-502">Here in the message examples we will assume that SCT with an associated security context is already established through a handshake.</span></span>  
  
 <span data-ttu-id="795ec-503">Используется симметричная привязка со следующими свойствами.</span><span class="sxs-lookup"><span data-stu-id="795ec-503">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="795ec-504">Токен защиты: SslContextToken, задан режим включения .../IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="795ec-504">Protection Token: SslContextToken, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="795ec-505">Защита маркера: False</span><span class="sxs-lookup"><span data-stu-id="795ec-505">Token Protection: False</span></span>  
  
 <span data-ttu-id="795ec-506">Сигнатуры всего заголовка и тела: True</span><span class="sxs-lookup"><span data-stu-id="795ec-506">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="795ec-507">Порядок защиты: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="795ec-507">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="795ec-508">Шифрование подписи: True</span><span class="sxs-lookup"><span data-stu-id="795ec-508">Encrypt Signature: True</span></span>  
  
#### <a name="651-policy-for-sslnegotiated-service-authentication"></a><span data-ttu-id="795ec-509">6.5.1 Политика для проверки подлинности службы SslNegotiated</span><span class="sxs-lookup"><span data-stu-id="795ec-509">6.5.1 Policy for SslNegotiated service authentication</span></span>  
 <span data-ttu-id="795ec-510">Политики для всех режимов проверки подлинности в этом разделе аналогичны и различаются только определенными используемыми подписанными поддерживающими или подтверждающими маркерами.</span><span class="sxs-lookup"><span data-stu-id="795ec-510">Policy for all authentication modes in this section are similar and differ only by specific signed supporting or endorsing tokens used.</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SslNegotiated_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <mssp:SslContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' />  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                </wsp:Policy>  
              </mssp:SslContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting token assertions go here -->  
      ..  
      <sp:Wss11>
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="652-anonymousforsslnegotiated"></a><span data-ttu-id="795ec-511">6.5.2 AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="795ec-511">6.5.2 AnonymousForSslNegotiated</span></span>  
 <span data-ttu-id="795ec-512">В этом режиме проверки подлинности клиент является анонимным, а проверка подлинности службы осуществляется с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="795ec-512">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="795ec-513">Используется экземпляр симметричной привязки, как описано выше в разделе 6.5.1.</span><span class="sxs-lookup"><span data-stu-id="795ec-513">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="795ec-514">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-514">Policy</span></span>  
  
 <span data-ttu-id="795ec-515">Сведения о привязке см. в пункте «Политика» раздела 6.5.1.</span><span class="sxs-lookup"><span data-stu-id="795ec-515">See Policy in 6.5.1 above for binding details.</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="795ec-516">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="795ec-516">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="795ec-517">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-517">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-518">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-518">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="795ec-519">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="795ec-519">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="795ec-520">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-520">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-521">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-521">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="653-usernameforsslnegotiated"></a><span data-ttu-id="795ec-522">6.5.3 UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="795ec-522">6.5.3 UserNameForSslNegotiated</span></span>  
 <span data-ttu-id="795ec-523">В этом режиме проверка подлинности клиента осуществляется с использованием маркера Username, который доступен на уровне SOAP в качестве подписанного поддерживающего маркера.</span><span class="sxs-lookup"><span data-stu-id="795ec-523">With this authentication mode the client is authenticates using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="795ec-524">Служба проходит проверку подлинности с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="795ec-524">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="795ec-525">Используется экземпляр симметричной привязки, как описано в разделе 6.5.1.</span><span class="sxs-lookup"><span data-stu-id="795ec-525">The binding used is an instance of symmetric binding as described in 6.5.1.</span></span>  
  
 <span data-ttu-id="795ec-526">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-526">Policy</span></span>  
  
 <span data-ttu-id="795ec-527">Сведения о привязке см. в разделе 6.5.1</span><span class="sxs-lookup"><span data-stu-id="795ec-527">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="795ec-528">Подписанный поддерживающий маркер</span><span class="sxs-lookup"><span data-stu-id="795ec-528">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="795ec-529">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="795ec-529">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="795ec-530">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-530">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-531">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-531">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="795ec-532">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="795ec-532">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="795ec-533">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-533">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-534">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-534">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="654-issuedtokenforsslnegotiated"></a><span data-ttu-id="795ec-535">6.5.4 IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="795ec-535">6.5.4 IssuedTokenForSslNegotiated</span></span>  
 <span data-ttu-id="795ec-536">В этом режиме проверки подлинности клиент не проходит как таковую проверку подлинности на стороне службы; вместо этого он предоставляет маркер, выданный службой маркеров безопасности и подтверждает знание общего ключа.</span><span class="sxs-lookup"><span data-stu-id="795ec-536">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="795ec-537">Выданный маркер доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера.</span><span class="sxs-lookup"><span data-stu-id="795ec-537">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="795ec-538">Служба проходит проверку подлинности с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="795ec-538">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="795ec-539">Используется экземпляр симметричной привязки, как описано выше в разделе 6.5.1.</span><span class="sxs-lookup"><span data-stu-id="795ec-539">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="795ec-540">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-540">Policy</span></span>  
  
 <span data-ttu-id="795ec-541">Сведения о привязке см. в разделе 6.5.1</span><span class="sxs-lookup"><span data-stu-id="795ec-541">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="795ec-542">Подтверждающий поддерживающий маркер</span><span class="sxs-lookup"><span data-stu-id="795ec-542">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
        </wst:KeyType>
      </sp:RequestSecurityTokenTemplate>  
      <wsp:Policy>  
        <sp:RequireDerivedKeys />
        <sp:RequireInternalReference />
      </wsp:Policy>  
    </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="795ec-543">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="795ec-543">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="795ec-544">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-544">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-545">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-545">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="795ec-546">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="795ec-546">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="795ec-547">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-547">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-548">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-548">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="655-mutualsslnegotiated"></a><span data-ttu-id="795ec-549">6.5.5 MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="795ec-549">6.5.5 MutualSslNegotiated</span></span>  
 <span data-ttu-id="795ec-550">В этом режиме проверка подлинности клиента и службы осуществляется с использованием сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="795ec-550">With this authentication mode the client and the service authenticate using X.509 certificates.</span></span> <span data-ttu-id="795ec-551">Используется экземпляр симметричной привязки, как описано выше в разделе 6.5.1.</span><span class="sxs-lookup"><span data-stu-id="795ec-551">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="795ec-552">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-552">Policy</span></span>  
  
 <span data-ttu-id="795ec-553">Сведения о привязке см. в разделе 6.5.1</span><span class="sxs-lookup"><span data-stu-id="795ec-553">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="795ec-554">Подтверждающий поддерживающий маркер</span><span class="sxs-lookup"><span data-stu-id="795ec-554">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />
        <sp:WssX509V3Token10 />
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="795ec-555">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="795ec-555">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="795ec-556">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-556">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-557">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-557">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="795ec-558">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="795ec-558">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="795ec-559">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-559">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-560">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-560">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="66-sspinegotiated"></a><span data-ttu-id="795ec-561">6.6 SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="795ec-561">6.6 SspiNegotiated</span></span>  
 <span data-ttu-id="795ec-562">В этом режиме для проверки подлинности клиента и сервера используется протокол согласования.</span><span class="sxs-lookup"><span data-stu-id="795ec-562">With this authentication mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="795ec-563">Если это возможно, используется протокол Kerberos, в противном случае - протокол NTLM.</span><span class="sxs-lookup"><span data-stu-id="795ec-563">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="795ec-564">Используется симметричная привязка со следующими свойствами.</span><span class="sxs-lookup"><span data-stu-id="795ec-564">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="795ec-565">Токен защиты: SpnegoContextToken, задан режим включения .../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="795ec-565">Protection Token: SpnegoContextToken, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="795ec-566">Защита маркера: False</span><span class="sxs-lookup"><span data-stu-id="795ec-566">Token Protection: False</span></span>  
  
 <span data-ttu-id="795ec-567">Сигнатуры всего заголовка и тела: True</span><span class="sxs-lookup"><span data-stu-id="795ec-567">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="795ec-568">Порядок защиты: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="795ec-568">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="795ec-569">Шифрование подписи: True</span><span class="sxs-lookup"><span data-stu-id="795ec-569">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="795ec-570">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-570">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple13_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                </wsp:Policy>  
              </sp:SpnegoContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="795ec-571">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="795ec-571">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="795ec-572">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-572">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-573">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-573">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="795ec-574">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="795ec-574">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="795ec-575">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-575">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-576">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-576">Response</span></span>  
  
```xml  
<wsse:Security>  
<wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="67-secureconversation"></a><span data-ttu-id="795ec-577">6.7 SecureConversation</span><span class="sxs-lookup"><span data-stu-id="795ec-577">6.7 SecureConversation</span></span>  
 <span data-ttu-id="795ec-578">Используется симметричная привязка, в которой маркером защиты является маркер контекста безопасности в соответствии со спецификацией WS-SecureConversation (WS-SC).</span><span class="sxs-lookup"><span data-stu-id="795ec-578">The binding used is a symmetric binding with the protection token being a SCT per WS-SecureConversation (WS-SC).</span></span> <span data-ttu-id="795ec-579">Согласование маркера контекста безопасности производится с использованием спецификации WS-Trust (WS-Trust) или WS-SecureConversation (WS-SC) в соответствии с вложенной привязкой, которая сама является симметричной привязкой, использующей протокол согласования.</span><span class="sxs-lookup"><span data-stu-id="795ec-579">The SCT is negotiated using WS-Trust (WS-Trust) or WS-SecureConversation (WS-SC) according to a nested binding, which is itself a symmetric binding that uses a negotiation protocol.</span></span> <span data-ttu-id="795ec-580">При возможности в протоколе согласования для проверки подлинности клиента и сервера используется протокол Kerberos.</span><span class="sxs-lookup"><span data-stu-id="795ec-580">The negotiation protocol will use Kerberos to perform client and server authentication if possible.</span></span> <span data-ttu-id="795ec-581">Если использование протокола Kerberos невозможно, используется резервный протокол NTLM.</span><span class="sxs-lookup"><span data-stu-id="795ec-581">If Kerberos cannot be used, it will fall back to NTLM.</span></span>  
  
 <span data-ttu-id="795ec-582">Политика</span><span class="sxs-lookup"><span data-stu-id="795ec-582">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SecureConversation_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SecureConversationToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:BootstrapPolicy>  
                    <wsp:Policy>  
                      <sp:SignedParts>  
                        <sp:Body />
                        <sp:Header Name='To' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='From' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='FaultTo' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='ReplyTo' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='MessageID' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='RelatesTo' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='Action' Namespace='http://www.w3.org/2005/08/addressing' />
                      </sp:SignedParts>  
                      <sp:EncryptedParts>  
                        <sp:Body />
                      </sp:EncryptedParts>  
                      <sp:SymmetricBinding>  
                        <wsp:Policy>  
                          <sp:ProtectionToken>  
                            <wsp:Policy>  
                              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                                <wsp:Policy>  
                                  <sp:RequireDerivedKeys />
                                </wsp:Policy>  
                              </sp:SpnegoContextToken>  
                            </wsp:Policy>  
                          </sp:ProtectionToken>  
                          <sp:AlgorithmSuite>  
                            <wsp:Policy>  
                              <sp:Basic256 />
                            </wsp:Policy>  
                          </sp:AlgorithmSuite>  
                          <sp:Layout>  
                            <wsp:Policy>  
                              <sp:Strict />
                            </wsp:Policy>  
                          </sp:Layout>  
                          <sp:IncludeTimestamp />
                          <sp:EncryptSignature />
                          <sp:OnlySignEntireHeadersAndBody />
                        </wsp:Policy>  
                      </sp:SymmetricBinding>  
                      <sp:Wss11>  
                        <wsp:Policy>  
                          <sp:MustSupportRefKeyIdentifier />
                          <sp:MustSupportRefIssuerSerial />
                          <sp:MustSupportRefThumbprint />
                          <sp:MustSupportRefEncryptedKey />
                        </wsp:Policy>  
                      </sp:Wss11>  
                      <sp:Trust10>  
                        <wsp:Policy>  
                          <sp:MustSupportIssuedTokens />
                          <sp:RequireClientEntropy />
                          <sp:RequireServerEntropy />
                        </wsp:Policy>  
                      </sp:Trust10>  
                    </wsp:Policy>  
                  </sp:BootstrapPolicy>  
                </wsp:Policy>  
              </sp:SecureConversationToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="795ec-583">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="795ec-583">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="795ec-584">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-584">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-585">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-585">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="795ec-586">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="795ec-586">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="795ec-587">Запрос</span><span class="sxs-lookup"><span data-stu-id="795ec-587">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="795ec-588">Ответ</span><span class="sxs-lookup"><span data-stu-id="795ec-588">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```
