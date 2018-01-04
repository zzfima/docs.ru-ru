---
title: "Протоколы безопасности версии 1.0"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee3402d2-1076-410b-a3cb-fae0372bd7af
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: ba5ce91f4cb3edd93698f7c0ba028186afdb8111
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="security-protocols-version-10"></a><span data-ttu-id="83dec-102">Протоколы безопасности версии 1.0</span><span class="sxs-lookup"><span data-stu-id="83dec-102">Security Protocols version 1.0</span></span>
<span data-ttu-id="83dec-103">Протоколы WS-Security предоставляют механизмы обеспечения безопасности веб-служб, охватывающие все существующие требования к безопасности обмена сообщениями на предприятии.</span><span class="sxs-lookup"><span data-stu-id="83dec-103">The Web Services Security Protocols provide Web services security mechanisms that cover all existing enterprise messaging security requirements.</span></span> <span data-ttu-id="83dec-104">В данном разделе рассматриваются подробные сведения [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] версии 1.0 (реализованные в <xref:System.ServiceModel.Channels.SecurityBindingElement>) для следующих протоколов WS-Security.</span><span class="sxs-lookup"><span data-stu-id="83dec-104">This section describes the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] version 1.0 details (implemented in the <xref:System.ServiceModel.Channels.SecurityBindingElement>) for the following Web services security protocols.</span></span>  
  
|<span data-ttu-id="83dec-105">Спецификация/документ</span><span class="sxs-lookup"><span data-stu-id="83dec-105">Specification/Document</span></span>|<span data-ttu-id="83dec-106">Ссылка</span><span class="sxs-lookup"><span data-stu-id="83dec-106">Link</span></span>|  
|-|-|  
|<span data-ttu-id="83dec-107">WSS: SOAP Message Security 1,0</span><span class="sxs-lookup"><span data-stu-id="83dec-107">WSS: SOAP Message Security 1.0</span></span>|<span data-ttu-id="83dec-108">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="83dec-108">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf</span></span>|  
|<span data-ttu-id="83dec-109">WSS: Username Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="83dec-109">WSS: Username Token Profile 1.0</span></span>|<span data-ttu-id="83dec-110">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="83dec-110">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="83dec-111">WSS: X509 Token Profile 1,0</span><span class="sxs-lookup"><span data-stu-id="83dec-111">WSS: X509 Token Profile 1.0</span></span>|<span data-ttu-id="83dec-112">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="83dec-112">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="83dec-113">WSS: SAML 1.1 Token Profile 1,0</span><span class="sxs-lookup"><span data-stu-id="83dec-113">WSS: SAML 1.1 Token Profile 1.0</span></span>|<span data-ttu-id="83dec-114">http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="83dec-114">http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="83dec-115">WSS: SOAP Message Security 1.1</span><span class="sxs-lookup"><span data-stu-id="83dec-115">WSS: SOAP Message Security 1.1</span></span>|<span data-ttu-id="83dec-116">http://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf</span><span class="sxs-lookup"><span data-stu-id="83dec-116">http://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf</span></span>|  
|<span data-ttu-id="83dec-117">WSS Username Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="83dec-117">WSS Username Token Profile 1.1</span></span>|<span data-ttu-id="83dec-118">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="83dec-118">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="83dec-119">WSS: X.509 Token Profile 1,1</span><span class="sxs-lookup"><span data-stu-id="83dec-119">WSS: X.509 Token Profile 1.1</span></span>|<span data-ttu-id="83dec-120">http://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf</span><span class="sxs-lookup"><span data-stu-id="83dec-120">http://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf</span></span>|  
|<span data-ttu-id="83dec-121">WSS: Kerberos Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="83dec-121">WSS: Kerberos Token Profile 1.1</span></span>|<span data-ttu-id="83dec-122">http://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf</span><span class="sxs-lookup"><span data-stu-id="83dec-122">http://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf</span></span>|  
|<span data-ttu-id="83dec-123">WSS: SAML 1.1 Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="83dec-123">WSS: SAML 1.1 Token Profile 1.1</span></span>|<span data-ttu-id="83dec-124">http://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf</span><span class="sxs-lookup"><span data-stu-id="83dec-124">http://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf</span></span>|  
|<span data-ttu-id="83dec-125">WS-Secure Conversation</span><span class="sxs-lookup"><span data-stu-id="83dec-125">WS-Secure Conversation</span></span>|<span data-ttu-id="83dec-126">http://msdn.microsoft.com/ws/2005/02/ws-secure-conversation/</span><span class="sxs-lookup"><span data-stu-id="83dec-126">http://msdn.microsoft.com/ws/2005/02/ws-secure-conversation/</span></span>|  
|<span data-ttu-id="83dec-127">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="83dec-127">WS-Trust</span></span>|<span data-ttu-id="83dec-128">http://msdn.microsoft.com/ws/2005/02/ws-trust/</span><span class="sxs-lookup"><span data-stu-id="83dec-128">http://msdn.microsoft.com/ws/2005/02/ws-trust/</span></span>|  
|<span data-ttu-id="83dec-129">Замечания по применению.</span><span class="sxs-lookup"><span data-stu-id="83dec-129">Application Note:</span></span><br /><br /> <span data-ttu-id="83dec-130">Использование WS-Trust для подтверждения TLS</span><span class="sxs-lookup"><span data-stu-id="83dec-130">Using WS-Trust for TLS Handshake</span></span>|<span data-ttu-id="83dec-131">Готовится к публикации</span><span class="sxs-lookup"><span data-stu-id="83dec-131">To be published</span></span>|  
|<span data-ttu-id="83dec-132">Замечания по применению.</span><span class="sxs-lookup"><span data-stu-id="83dec-132">Application Note:</span></span><br /><br /> <span data-ttu-id="83dec-133">Использование WS-Trust для подтверждения SPNEGO</span><span class="sxs-lookup"><span data-stu-id="83dec-133">Using WS-Trust for SPNEGO</span></span>|<span data-ttu-id="83dec-134">Готовится к публикации</span><span class="sxs-lookup"><span data-stu-id="83dec-134">To be published</span></span>|  
|<span data-ttu-id="83dec-135">Замечания по применению.</span><span class="sxs-lookup"><span data-stu-id="83dec-135">Application Note:</span></span><br /><br /> <span data-ttu-id="83dec-136">Ссылки и идентификация конечной точки адресации веб-служб</span><span class="sxs-lookup"><span data-stu-id="83dec-136">Web Services Addressing Endpoint References And Identity</span></span>|<span data-ttu-id="83dec-137">Готовится к публикации</span><span class="sxs-lookup"><span data-stu-id="83dec-137">To be published</span></span>|  
|<span data-ttu-id="83dec-138">WS-SecurityPolicy 1.1</span><span class="sxs-lookup"><span data-stu-id="83dec-138">WS-SecurityPolicy 1.1</span></span><br /><br /> <span data-ttu-id="83dec-139">(2005/07)</span><span class="sxs-lookup"><span data-stu-id="83dec-139">(2005/07)</span></span>|<span data-ttu-id="83dec-140">http://msdn.microsoft.com/ws/2005/07/ws-security-policy/</span><span class="sxs-lookup"><span data-stu-id="83dec-140">http://msdn.microsoft.com/ws/2005/07/ws-security-policy/</span></span><br /><br /> <span data-ttu-id="83dec-141">с учетом списка ошибок, переданных в технический комитет OASIS WS-SX http://www.oasis-open.org/archives/ws-sx/200512/msg00017.html</span><span class="sxs-lookup"><span data-stu-id="83dec-141">as amended by errata submitted to OASIS WS-SX Technical Committee http://www.oasis-open.org/archives/ws-sx/200512/msg00017.html</span></span>|  
  
 <span data-ttu-id="83dec-142">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] версии 1 предусмотрено 17 режимов проверки подлинности, которые можно использовать как основу для настройки безопасности веб-служб.</span><span class="sxs-lookup"><span data-stu-id="83dec-142">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], version 1, provides 17 authentication modes that can be used as the basis for Web services security configuration.</span></span> <span data-ttu-id="83dec-143">Каждый из режимов оптимизирован для того или иного типичного набора требований к развертыванию, например следующих:</span><span class="sxs-lookup"><span data-stu-id="83dec-143">Each mode is optimized for a common set of deployment requirements, such as:</span></span>  
  
-   <span data-ttu-id="83dec-144">учетные данные, используемые для проверки подлинности клиента и службы;</span><span class="sxs-lookup"><span data-stu-id="83dec-144">Credentials used to authenticate client and service.</span></span>  
  
-   <span data-ttu-id="83dec-145">механизмы обеспечения безопасности на уровне сообщений или транспорта;</span><span class="sxs-lookup"><span data-stu-id="83dec-145">Message or transport security protection mechanisms.</span></span>  
  
-   <span data-ttu-id="83dec-146">шаблоны обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="83dec-146">Message exchange patterns.</span></span>  
  
|<span data-ttu-id="83dec-147">Режим проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="83dec-147">Authentication Mode</span></span>|<span data-ttu-id="83dec-148">Аутентификация клиента</span><span class="sxs-lookup"><span data-stu-id="83dec-148">Client Authentication</span></span>|<span data-ttu-id="83dec-149">Проверка подлинности сервера</span><span class="sxs-lookup"><span data-stu-id="83dec-149">Server Authentication</span></span>|<span data-ttu-id="83dec-150">Mode</span><span class="sxs-lookup"><span data-stu-id="83dec-150">Mode</span></span>|  
|-------------------------|---------------------------|---------------------------|----------|  
|<span data-ttu-id="83dec-151">UserNameOverTransport</span><span class="sxs-lookup"><span data-stu-id="83dec-151">UserNameOverTransport</span></span>|<span data-ttu-id="83dec-152">Имя пользователя/пароль</span><span class="sxs-lookup"><span data-stu-id="83dec-152">User name/password</span></span>|<span data-ttu-id="83dec-153">X509</span><span class="sxs-lookup"><span data-stu-id="83dec-153">X509</span></span>|<span data-ttu-id="83dec-154">Transport</span><span class="sxs-lookup"><span data-stu-id="83dec-154">Transport</span></span>|  
|<span data-ttu-id="83dec-155">CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="83dec-155">CertificateOverTransport</span></span>|<span data-ttu-id="83dec-156">X509</span><span class="sxs-lookup"><span data-stu-id="83dec-156">X509</span></span>|<span data-ttu-id="83dec-157">X509</span><span class="sxs-lookup"><span data-stu-id="83dec-157">X509</span></span>|<span data-ttu-id="83dec-158">Transport</span><span class="sxs-lookup"><span data-stu-id="83dec-158">Transport</span></span>|  
|<span data-ttu-id="83dec-159">KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="83dec-159">KerberosOverTransport</span></span>|<span data-ttu-id="83dec-160">Windows</span><span class="sxs-lookup"><span data-stu-id="83dec-160">Windows</span></span>|<span data-ttu-id="83dec-161">X509</span><span class="sxs-lookup"><span data-stu-id="83dec-161">X509</span></span>|<span data-ttu-id="83dec-162">Transport</span><span class="sxs-lookup"><span data-stu-id="83dec-162">Transport</span></span>|  
|<span data-ttu-id="83dec-163">IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="83dec-163">IssuedTokenOverTransport</span></span>|<span data-ttu-id="83dec-164">Федеративная</span><span class="sxs-lookup"><span data-stu-id="83dec-164">Federated</span></span>|<span data-ttu-id="83dec-165">X509</span><span class="sxs-lookup"><span data-stu-id="83dec-165">X509</span></span>|<span data-ttu-id="83dec-166">Transport</span><span class="sxs-lookup"><span data-stu-id="83dec-166">Transport</span></span>|  
|<span data-ttu-id="83dec-167">SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="83dec-167">SspiNegotiatedOverTransport</span></span>|<span data-ttu-id="83dec-168">Согласование Windows Sspi</span><span class="sxs-lookup"><span data-stu-id="83dec-168">Windows Sspi Negotiated</span></span>|<span data-ttu-id="83dec-169">Согласование Windows Sspi</span><span class="sxs-lookup"><span data-stu-id="83dec-169">Windows Sspi Negotiated</span></span>|<span data-ttu-id="83dec-170">Transport</span><span class="sxs-lookup"><span data-stu-id="83dec-170">Transport</span></span>|  
|<span data-ttu-id="83dec-171">AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="83dec-171">AnonymousForCertificate</span></span>|<span data-ttu-id="83dec-172">Нет</span><span class="sxs-lookup"><span data-stu-id="83dec-172">None</span></span>|<span data-ttu-id="83dec-173">X509</span><span class="sxs-lookup"><span data-stu-id="83dec-173">X509</span></span>|<span data-ttu-id="83dec-174">Сообщение</span><span class="sxs-lookup"><span data-stu-id="83dec-174">Message</span></span>|  
|<span data-ttu-id="83dec-175">UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="83dec-175">UserNameForCertificate</span></span>|<span data-ttu-id="83dec-176">Имя пользователя/пароль</span><span class="sxs-lookup"><span data-stu-id="83dec-176">User name/password</span></span>|<span data-ttu-id="83dec-177">X509</span><span class="sxs-lookup"><span data-stu-id="83dec-177">X509</span></span>|<span data-ttu-id="83dec-178">Сообщение</span><span class="sxs-lookup"><span data-stu-id="83dec-178">Message</span></span>|  
|<span data-ttu-id="83dec-179">MutualCertificate</span><span class="sxs-lookup"><span data-stu-id="83dec-179">MutualCertificate</span></span>|<span data-ttu-id="83dec-180">X509</span><span class="sxs-lookup"><span data-stu-id="83dec-180">X509</span></span>|<span data-ttu-id="83dec-181">X509</span><span class="sxs-lookup"><span data-stu-id="83dec-181">X509</span></span>|<span data-ttu-id="83dec-182">Сообщение</span><span class="sxs-lookup"><span data-stu-id="83dec-182">Message</span></span>|  
|<span data-ttu-id="83dec-183">MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="83dec-183">MutualCertificateDuplex</span></span>|<span data-ttu-id="83dec-184">X509</span><span class="sxs-lookup"><span data-stu-id="83dec-184">X509</span></span>|<span data-ttu-id="83dec-185">X509</span><span class="sxs-lookup"><span data-stu-id="83dec-185">X509</span></span>|<span data-ttu-id="83dec-186">Сообщение</span><span class="sxs-lookup"><span data-stu-id="83dec-186">Message</span></span>|  
|<span data-ttu-id="83dec-187">IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="83dec-187">IssuedTokenForCertificate</span></span>|<span data-ttu-id="83dec-188">Федеративная</span><span class="sxs-lookup"><span data-stu-id="83dec-188">Federated</span></span>|<span data-ttu-id="83dec-189">X509</span><span class="sxs-lookup"><span data-stu-id="83dec-189">X509</span></span>|<span data-ttu-id="83dec-190">Сообщение</span><span class="sxs-lookup"><span data-stu-id="83dec-190">Message</span></span>|  
|<span data-ttu-id="83dec-191">Kerberos</span><span class="sxs-lookup"><span data-stu-id="83dec-191">Kerberos</span></span>|<span data-ttu-id="83dec-192">Windows</span><span class="sxs-lookup"><span data-stu-id="83dec-192">Windows</span></span>|<span data-ttu-id="83dec-193">Windows</span><span class="sxs-lookup"><span data-stu-id="83dec-193">Windows</span></span>|<span data-ttu-id="83dec-194">Сообщение</span><span class="sxs-lookup"><span data-stu-id="83dec-194">Message</span></span>|  
|<span data-ttu-id="83dec-195">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="83dec-195">IssuedToken</span></span>|<span data-ttu-id="83dec-196">Федеративная</span><span class="sxs-lookup"><span data-stu-id="83dec-196">Federated</span></span>|<span data-ttu-id="83dec-197">Федеративная</span><span class="sxs-lookup"><span data-stu-id="83dec-197">Federated</span></span>|<span data-ttu-id="83dec-198">Сообщение</span><span class="sxs-lookup"><span data-stu-id="83dec-198">Message</span></span>|  
|<span data-ttu-id="83dec-199">SspiNegotiation</span><span class="sxs-lookup"><span data-stu-id="83dec-199">SspiNegotiated</span></span>|<span data-ttu-id="83dec-200">Согласование Windows Sspi</span><span class="sxs-lookup"><span data-stu-id="83dec-200">Windows Sspi Negotiated</span></span>|<span data-ttu-id="83dec-201">Согласование Windows Sspi</span><span class="sxs-lookup"><span data-stu-id="83dec-201">Windows Sspi Negotiated</span></span>|<span data-ttu-id="83dec-202">Сообщение</span><span class="sxs-lookup"><span data-stu-id="83dec-202">Message</span></span>|  
|<span data-ttu-id="83dec-203">AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="83dec-203">AnonymousForSslNegotiated</span></span>|<span data-ttu-id="83dec-204">Нет</span><span class="sxs-lookup"><span data-stu-id="83dec-204">None</span></span>|<span data-ttu-id="83dec-205">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="83dec-205">X509, TLS-Nego</span></span>|<span data-ttu-id="83dec-206">Сообщение</span><span class="sxs-lookup"><span data-stu-id="83dec-206">Message</span></span>|  
|<span data-ttu-id="83dec-207">UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="83dec-207">UserNameForSslNegotiated</span></span>|<span data-ttu-id="83dec-208">Имя пользователя/пароль</span><span class="sxs-lookup"><span data-stu-id="83dec-208">User name/password</span></span>|<span data-ttu-id="83dec-209">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="83dec-209">X509, TLS-Nego</span></span>|<span data-ttu-id="83dec-210">Сообщение</span><span class="sxs-lookup"><span data-stu-id="83dec-210">Message</span></span>|  
|<span data-ttu-id="83dec-211">MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="83dec-211">MutualSslNegotiated</span></span>|<span data-ttu-id="83dec-212">X509</span><span class="sxs-lookup"><span data-stu-id="83dec-212">X509</span></span>|<span data-ttu-id="83dec-213">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="83dec-213">X509, TLS-Nego</span></span>|<span data-ttu-id="83dec-214">Сообщение</span><span class="sxs-lookup"><span data-stu-id="83dec-214">Message</span></span>|  
|<span data-ttu-id="83dec-215">IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="83dec-215">IssuedTokenForSslNegotiated</span></span>|<span data-ttu-id="83dec-216">Федеративная</span><span class="sxs-lookup"><span data-stu-id="83dec-216">Federated</span></span>|<span data-ttu-id="83dec-217">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="83dec-217">X509, TLS-Nego</span></span>|<span data-ttu-id="83dec-218">Сообщение</span><span class="sxs-lookup"><span data-stu-id="83dec-218">Message</span></span>|  
  
 <span data-ttu-id="83dec-219">Конечные точки, использующие такие режимы проверки подлинности, могут выражать свои требования безопасности с помощью WS-SecurityPolicy (WS-SP).</span><span class="sxs-lookup"><span data-stu-id="83dec-219">Endpoints using such authentication modes can express their security requirements using WS-SecurityPolicy (WS-SP).</span></span> <span data-ttu-id="83dec-220">В этом документе описывается структура заголовка безопасности и инфраструктурные сообщения для каждого режима проверки подлинности, а также приводятся примеры политик и сообщений.</span><span class="sxs-lookup"><span data-stu-id="83dec-220">This document describes the structure of security header and infrastructure messages for each authentication mode and provides examples of policies and messages.</span></span>  
  
 <span data-ttu-id="83dec-221">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для обеспечения поддержки безопасных сеансов с целью защиты обмена сообщениями между приложениями используется спецификация WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="83dec-221">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] leverages WS-SecureConversation to provide secure sessions support to protect multi-message exchanges between applications.</span></span>  <span data-ttu-id="83dec-222">Сведения о реализации см. ниже в подразделе "Безопасные сеансы".</span><span class="sxs-lookup"><span data-stu-id="83dec-222">See "Secure Sessions" below for implementation details.</span></span>  
  
 <span data-ttu-id="83dec-223">Помимо режимов проверки подлинности, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предоставляет параметры для управления распространенными механизмами защиты, которые применяются в большинстве режимов проверки подлинности, основанных на безопасности сообщений, например следующих: порядок подписывания относительно операций шифрования, наборы алгоритмов, формирование ключей и подтверждение сигнатур.</span><span class="sxs-lookup"><span data-stu-id="83dec-223">In addition to authentication modes, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides settings to control common protection mechanisms that apply to most message security-based authentication modes, for example: order of signature versus encryption operations, algorithm suites, key derivation, and signature confirmation.</span></span>  
  
 <span data-ttu-id="83dec-224">В данном документе используются перечисленные ниже префиксы и пространства имен.</span><span class="sxs-lookup"><span data-stu-id="83dec-224">The following prefixes and namespaces are used in this document.</span></span>  
  
|<span data-ttu-id="83dec-225">Префикс</span><span class="sxs-lookup"><span data-stu-id="83dec-225">Prefix</span></span>|<span data-ttu-id="83dec-226">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="83dec-226">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="83dec-227">s</span><span class="sxs-lookup"><span data-stu-id="83dec-227">s</span></span>|<span data-ttu-id="83dec-228">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="83dec-228">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="83dec-229">sp</span><span class="sxs-lookup"><span data-stu-id="83dec-229">sp</span></span>|<span data-ttu-id="83dec-230">http://schemas.xmlsoap.org/ws/2005/07/securitypolicy</span><span class="sxs-lookup"><span data-stu-id="83dec-230">http://schemas.xmlsoap.org/ws/2005/07/securitypolicy</span></span>|  
|<span data-ttu-id="83dec-231">a</span><span class="sxs-lookup"><span data-stu-id="83dec-231">a</span></span>|<span data-ttu-id="83dec-232">http://www.w3.org/2005/08/addressing</span><span class="sxs-lookup"><span data-stu-id="83dec-232">http://www.w3.org/2005/08/addressing</span></span>|  
|<span data-ttu-id="83dec-233">wsse</span><span class="sxs-lookup"><span data-stu-id="83dec-233">wsse</span></span>|<span data-ttu-id="83dec-234">Подлежит определению - универсальный код ресурса (URI) OASIS WSS 1,0</span><span class="sxs-lookup"><span data-stu-id="83dec-234">TBD – OASIS WSS 1.0 URI</span></span>|  
|<span data-ttu-id="83dec-235">wsse11</span><span class="sxs-lookup"><span data-stu-id="83dec-235">wsse11</span></span>|<span data-ttu-id="83dec-236">Подлежит определению - универсальный код ресурса (URI) OASIS WSS 1.1</span><span class="sxs-lookup"><span data-stu-id="83dec-236">TBD – OASIS WSS 1.1 URI</span></span>|  
|<span data-ttu-id="83dec-237">wsu</span><span class="sxs-lookup"><span data-stu-id="83dec-237">wsu</span></span>|<span data-ttu-id="83dec-238">Подлежит определению - универсальный код ресурса (URI) OASIS WSS 1.0 Utility</span><span class="sxs-lookup"><span data-stu-id="83dec-238">TBD – OASIS WSS 1.0 Utility URI</span></span>|  
|<span data-ttu-id="83dec-239">ds</span><span class="sxs-lookup"><span data-stu-id="83dec-239">ds</span></span>|<span data-ttu-id="83dec-240">Подлежит определению - универсальный код ресурса (URI) W3C XMLDSig</span><span class="sxs-lookup"><span data-stu-id="83dec-240">TBD – W3C XMLDSig URI</span></span>|  
|<span data-ttu-id="83dec-241">wst</span><span class="sxs-lookup"><span data-stu-id="83dec-241">wst</span></span>|<span data-ttu-id="83dec-242">Подлежит определению - универсальный код ресурса (URI) WS-Trust 2005/02</span><span class="sxs-lookup"><span data-stu-id="83dec-242">TBD – WS-Trust 2005/02 URI</span></span>|  
|<span data-ttu-id="83dec-243">wssc</span><span class="sxs-lookup"><span data-stu-id="83dec-243">wssc</span></span>|<span data-ttu-id="83dec-244">Подлежит определению - универсальный код ресурса (URI) WS-SecureConversation 2005/02</span><span class="sxs-lookup"><span data-stu-id="83dec-244">TBD – WS-SecureConversation 2005/02 URI</span></span>|  
|<span data-ttu-id="83dec-245">wsaw</span><span class="sxs-lookup"><span data-stu-id="83dec-245">wsaw</span></span>|<span data-ttu-id="83dec-246">Подлежит определению - пространство имен политики WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="83dec-246">TBD - WS-Addressing policy namespace</span></span>|  
|<span data-ttu-id="83dec-247">wsp</span><span class="sxs-lookup"><span data-stu-id="83dec-247">wsp</span></span>|<span data-ttu-id="83dec-248">http://schemas.xmlsoap.org/ws/2004/09/policy</span><span class="sxs-lookup"><span data-stu-id="83dec-248">http://schemas.xmlsoap.org/ws/2004/09/policy</span></span>|  
|<span data-ttu-id="83dec-249">mssp</span><span class="sxs-lookup"><span data-stu-id="83dec-249">mssp</span></span>|<span data-ttu-id="83dec-250">http://schemas.microsoft.com/ws/2005/07/securitypolicy</span><span class="sxs-lookup"><span data-stu-id="83dec-250">http://schemas.microsoft.com/ws/2005/07/securitypolicy</span></span>|  
  
## <a name="1-token-profiles"></a><span data-ttu-id="83dec-251">1. Профили маркеров</span><span class="sxs-lookup"><span data-stu-id="83dec-251">1. Token Profiles</span></span>  
 <span data-ttu-id="83dec-252">В спецификациях WS-Security учетные данные представляются в виде токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="83dec-252">Web Services Security specifications represent credential as security tokens.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="83dec-253"> поддерживает следующие типы токенов.</span><span class="sxs-lookup"><span data-stu-id="83dec-253"> supports the following token types:</span></span>  
  
### <a name="11-usernametoken"></a><span data-ttu-id="83dec-254">1.1 Маркер UsernameToken</span><span class="sxs-lookup"><span data-stu-id="83dec-254">1.1 UsernameToken</span></span>  
 <span data-ttu-id="83dec-255">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используются профили UsernameToken10 и UsernameToken11 со следующими ограничениями.</span><span class="sxs-lookup"><span data-stu-id="83dec-255">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] follows UsernameToken10 and UsernameToken11 profiles with the following constraints:</span></span>  
  
 <span data-ttu-id="83dec-256">R1101 Атрибут PasswordType элемента UsernameToken\Password ДОЛЖЕН быть либо опущен, либо иметь значение #PasswordText (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="83dec-256">R1101 PasswordType attribute on UsernameToken\Password element MUST be either omitted or have value #PasswordText (default).</span></span>  
  
 <span data-ttu-id="83dec-257">Можно реализовать #PasswordDigest с помощью расширяемости.</span><span class="sxs-lookup"><span data-stu-id="83dec-257">One can implement the #PasswordDigest using extensibility.</span></span> <span data-ttu-id="83dec-258">Замечено, что #PasswordDigest часто ошибочно считается достаточно безопасным механизмом защиты пароля.</span><span class="sxs-lookup"><span data-stu-id="83dec-258">It has been observed that #PasswordDigest was often mistaken to be a secure enough password protection mechanism.</span></span> <span data-ttu-id="83dec-259">Однако #PasswordDigest не может служить заменой шифрованию маркера UsernameToken.</span><span class="sxs-lookup"><span data-stu-id="83dec-259">But #PasswordDigest cannot serve as a substitute for encryption of the UsernameToken.</span></span> <span data-ttu-id="83dec-260">Основной целью #PasswordDigest является защита от атак с повторением.</span><span class="sxs-lookup"><span data-stu-id="83dec-260">The primary goal of #PasswordDigest is protection against replay attacks.</span></span> <span data-ttu-id="83dec-261">В режимах проверки подлинности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] угрозы атак с повторением устраняются с помощью сигнатур сообщений.</span><span class="sxs-lookup"><span data-stu-id="83dec-261">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] authentication modes, replay attack threats are mitigated by using message signatures.</span></span>  
  
 <span data-ttu-id="83dec-262">B1102 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] никогда не создает подэлементы Nonce и Created маркера UsernameToken.</span><span class="sxs-lookup"><span data-stu-id="83dec-262">B1102 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] never emits Nonce and Created sub-elements of the UsernameToken.</span></span>  
  
 <span data-ttu-id="83dec-263">Эти подэлементы предназначены для упрощения обнаружения атак с повторением.</span><span class="sxs-lookup"><span data-stu-id="83dec-263">These sub-elements are intended to help replay detection.</span></span> <span data-ttu-id="83dec-264">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] вместо них используются подписи сообщений.</span><span class="sxs-lookup"><span data-stu-id="83dec-264">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses message signatures instead.</span></span>  
  
 <span data-ttu-id="83dec-265">В профиле OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) введена функция создания производного ключа из пароля.</span><span class="sxs-lookup"><span data-stu-id="83dec-265">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) introduced key derivation from password feature.</span></span>  
  
 <span data-ttu-id="83dec-266">B1103 Пароль UsernameToken НЕ ДОЛЖЕН использоваться для создания производного ключа и, следовательно, для операций шифрования.</span><span class="sxs-lookup"><span data-stu-id="83dec-266">B1103 UsernameToken password MUST not be used for key derivation and therefore for cryptographic operations.</span></span>  
  
 <span data-ttu-id="83dec-267">Обоснование: пароли обычно считаются слишком слабой защитой, для того чтобы использовать их в операциях шифрования.</span><span class="sxs-lookup"><span data-stu-id="83dec-267">Rationale: passwords are generally considered too weak to be used for cryptographic operations.</span></span>  
  
### <a name="12-x509-token"></a><span data-ttu-id="83dec-268">1.2 Маркер X509</span><span class="sxs-lookup"><span data-stu-id="83dec-268">1.2 X509 Token</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="83dec-269"> поддерживает сертификаты X509v3 в качестве типа учетных данных в соответствии с профилями X509TokenProfile1.0 и X509TokenProfile1.1 со следующими ограничениями.</span><span class="sxs-lookup"><span data-stu-id="83dec-269"> supports X509v3 certificates as a credential type and follows X509TokenProfile1.0 and X509TokenProfile1.1 with the following constraints:</span></span>  
  
 <span data-ttu-id="83dec-270">R1201 Атрибут ValueType элемента BinarySecurityToken должен иметь значение #X509v3, если он содержит сертификат X509v3.</span><span class="sxs-lookup"><span data-stu-id="83dec-270">R1201 The ValueType attribute on the BinarySecurityToken element must have value #X509v3 when it contains an X509v3 certificate.</span></span>  
  
 <span data-ttu-id="83dec-271">Профили WSS X509 Token Profile 1.0 и 1.1 также определяют типы значений #X509PKIPathv1 и #PKCS7.</span><span class="sxs-lookup"><span data-stu-id="83dec-271">WSS X509 Token Profile 1.0 and 1.1 define also #X509PKIPathv1 and #PKCS7 as value types.</span></span> <span data-ttu-id="83dec-272">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] эти типы не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="83dec-272">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not support these types.</span></span>  
  
 <span data-ttu-id="83dec-273">R1202 Если в сертификате X509 имеется расширение SubjectKeyIdentifier (SKI), для внешних ссылок на маркер должен использоваться wsse:KeyIdentifier, со значением #X509SubjectKeyIdentifier атрибута ValueType и содержащий значение расширения SKI сертификата в кодировке base64.</span><span class="sxs-lookup"><span data-stu-id="83dec-273">R1202 If a SubjectKeyIdentifier (SKI) extension is present in an X509 certificate, wsse:KeyIdentifier should be used for external references to the token, with the ValueType attribute as #X509SubjectKeyIdentifier and its content the base64-encoded value of certificate's SKI extension.</span></span>  
  
 <span data-ttu-id="83dec-274">Ссылки SKI имеют множество реализаций и зарекомендовали себя как внешний ссылочный тип с широкими возможностями совместимости.</span><span class="sxs-lookup"><span data-stu-id="83dec-274">SKI references are widely implemented and proven to be a highly interoperable external reference type.</span></span>  
  
 <span data-ttu-id="83dec-275">R1203 Внешняя ссылка на маркер безопасности X509 НЕ ДОЛЖНА использовать ds:X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="83dec-275">R1203 An external Reference to X509 Security Token SHOULD NOT use ds:X509IssuerSerial.</span></span>  
  
 <span data-ttu-id="83dec-276">R1204 Если используется профиль X509TokenProfile1.1, внешняя ссылка на маркер безопасности X509 ДОЛЖНА использовать отпечаток, введенный в протоколе WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="83dec-276">R1204 If X509TokenProfile1.1 is in use, an external reference to X509 Security Token SHOULD use the thumbprint introduced by WS-Security 1.1.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="83dec-277"> поддерживает X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="83dec-277"> supports X509IssuerSerial.</span></span> <span data-ttu-id="83dec-278">Однако имеются проблемы взаимодействия, связанные с X509IssuerSerial: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для сравнения двух значений X509IssuerSerial используются строки.</span><span class="sxs-lookup"><span data-stu-id="83dec-278">However There are interoperability issues with X509IssuerSerial: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses a string to compare two values of X509IssuerSerial.</span></span> <span data-ttu-id="83dec-279">Поэтому если изменить порядок компонентов имени субъекта и отправить в службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ссылку на сертификат, он может быть не найден.</span><span class="sxs-lookup"><span data-stu-id="83dec-279">Therefore if one reorders components of the Subject Name and sends to an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service a reference to a certificate, it may not be found.</span></span>  
  
### <a name="13-kerberos-token"></a><span data-ttu-id="83dec-280">1.3 Маркер Kerberos</span><span class="sxs-lookup"><span data-stu-id="83dec-280">1.3 Kerberos Token</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="83dec-281"> поддерживает использование профиля KerberosTokenProfile1.1 для проверки подлинности Windows со следующими ограничениями.</span><span class="sxs-lookup"><span data-stu-id="83dec-281"> supports KerberosTokenProfile1.1 for the purpose of Windows authentication with the following constraints:</span></span>  
  
 <span data-ttu-id="83dec-282">R1301 Маркер Kerberos должен содержать значение GSS в оболочке Kerberos v4 AP_REQ, как определено в GSS_API и спецификации Kerberos, и должен иметь атрибут ValueType со значением #GSS_Kerberosv5_AP_REQ.</span><span class="sxs-lookup"><span data-stu-id="83dec-282">R1301 A Kerberos Token must carry the value of a GSS wrapped Kerberos v4 AP_REQ as defined in GSS_API and the Kerberos specification, and must have the ValueType attribute with the value #GSS_Kerberosv5_AP_REQ.</span></span>  
  
 <span data-ttu-id="83dec-283">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используется GSS в оболочке Kerberos AP-REQ, а не просто AP-REQ.</span><span class="sxs-lookup"><span data-stu-id="83dec-283">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses GSS wrapped Kerberos AP-REQ, not a bare AP-REQ.</span></span> <span data-ttu-id="83dec-284">Это рекомендуется в целях безопасности.</span><span class="sxs-lookup"><span data-stu-id="83dec-284">This is a security best practice.</span></span>  
  
### <a name="14-saml-v11-token"></a><span data-ttu-id="83dec-285">1.4 Маркер SAML 1.1</span><span class="sxs-lookup"><span data-stu-id="83dec-285">1.4 SAML v1.1 Token</span></span>  
 <span data-ttu-id="83dec-286">Для маркеров SAML 1.1 в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживаются профили маркеров WSS SAML 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="83dec-286">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports WSS SAML Token profiles 1.0 and 1.1 for SAML v1.1 tokens.</span></span> <span data-ttu-id="83dec-287">Возможна реализация других версий форматов маркеров SAML.</span><span class="sxs-lookup"><span data-stu-id="83dec-287">It is possible to implement other versions of SAML token formats.</span></span>  
  
### <a name="15-security-context-token"></a><span data-ttu-id="83dec-288">1.5 Маркер контекста безопасности</span><span class="sxs-lookup"><span data-stu-id="83dec-288">1.5 Security Context Token</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="83dec-289"> поддерживает маркер контекста безопасности, введенный в спецификации WS-SecureCoversation.</span><span class="sxs-lookup"><span data-stu-id="83dec-289"> supports the Security Context Token (SCT) introduced in WS-SecureCoversation.</span></span> <span data-ttu-id="83dec-290">Маркер контекста безопасности служит для представления контекста безопасности, установленного в спецификации SecureConversation, а также протоколов двоичного согласования TLS и SSPI, описываемых ниже.</span><span class="sxs-lookup"><span data-stu-id="83dec-290">SCT is used to represent a security context established in SecureConversation as well as the binary negotiation protocols TLS and SSPI, described below.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="83dec-291">2. Общие параметры безопасности сообщений</span><span class="sxs-lookup"><span data-stu-id="83dec-291">2. Common Message Security Parameters</span></span>  
  
### <a name="21-timestamp"></a><span data-ttu-id="83dec-292">2.1 TimeStamp</span><span class="sxs-lookup"><span data-stu-id="83dec-292">2.1 TimeStamp</span></span>  
 <span data-ttu-id="83dec-293">Наличие отметки времени определяется с помощью свойства <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> класса <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="83dec-293">Timestamp presence is controlled using the <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> property of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span> <span data-ttu-id="83dec-294">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поле wsse:TimeStamp всегда сериализуется с полями wsse:Created и wsse:Expires.</span><span class="sxs-lookup"><span data-stu-id="83dec-294">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] always serializes wsse:TimeStamp with wsse:Created and wsse:Expires fields.</span></span> <span data-ttu-id="83dec-295">Если используется подписывание, wsse:TimeStamp всегда подписывается.</span><span class="sxs-lookup"><span data-stu-id="83dec-295">The wsse:TimeStamp is always signed when signing is used.</span></span>  
  
### <a name="22-protection-order"></a><span data-ttu-id="83dec-296">2.2. Порядок защиты</span><span class="sxs-lookup"><span data-stu-id="83dec-296">2.2 Protection Order</span></span>  
 <span data-ttu-id="83dec-297">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживаются порядки защиты сообщений «подпись перед шифрованием» и «шифрование перед подписью» (Security Policy 1.1).</span><span class="sxs-lookup"><span data-stu-id="83dec-297">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports the message protection order "Sign Before Encrypt" and "Encrypt Before Sign" (Security Policy 1.1).</span></span> <span data-ttu-id="83dec-298">По ряду причин рекомендуется использовать порядок «подпись перед шифрованием», в том числе по следующим причинам: если не используется механизм WS-Security 1.1 SignatureConfirmation, сообщения, защищенные в порядке «шифрование перед подписью», подвержены атакам подмены подписи и при подписывании зашифрованного содержимого сложнее производить аудит.</span><span class="sxs-lookup"><span data-stu-id="83dec-298">"Sign Before Encrypt" is recommended for reasons including: messages protected with Encrypt Before Sign are open to signature substitution attacks unless the WS-Security 1.1 SignatureConfirmation mechanism is used, and a signature over encrypted content makes auditing harder.</span></span>  
  
### <a name="23-signature-protection"></a><span data-ttu-id="83dec-299">2.3 Защита сигнатуры</span><span class="sxs-lookup"><span data-stu-id="83dec-299">2.3 Signature Protection</span></span>  
 <span data-ttu-id="83dec-300">Если используется порядок "шифрование перед сигнатурой", рекомендуется защищать сигнатура, чтобы предотвратить атаки методом подбора для угадывания зашифрованного содержимого или ключа сигнатуры (особенно при использовании пользовательского маркера с ненадежным ключевым материалом).</span><span class="sxs-lookup"><span data-stu-id="83dec-300">When Encrypt Before Sign is used, it is recommended to protect the signature to prevent brute force attacks for guessing the encrypted content or the signing key (especially when a custom token is used with weak key material).</span></span>  
  
### <a name="24-algorithm-suite"></a><span data-ttu-id="83dec-301">2.4 Набор алгоритмов</span><span class="sxs-lookup"><span data-stu-id="83dec-301">2.4 Algorithm Suite</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="83dec-302"> поддерживает все наборы алгоритмов, перечисленные в спецификации Security Policy 1.1.</span><span class="sxs-lookup"><span data-stu-id="83dec-302"> supports all algorithm suites listed in Security Policy 1.1.</span></span>  
  
### <a name="25-key-derivation"></a><span data-ttu-id="83dec-303">2.5 Формирование ключей</span><span class="sxs-lookup"><span data-stu-id="83dec-303">2.5 Key Derivation</span></span>  
 <span data-ttu-id="83dec-304">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используется «формирование симметричных ключей», как описано в спецификации WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="83dec-304">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses "Key Derivation for symmetric keys" as described in WS-SecureConversation.</span></span>  
  
### <a name="26-signature-confirmation"></a><span data-ttu-id="83dec-305">2.6 Подтверждение сигнатуры</span><span class="sxs-lookup"><span data-stu-id="83dec-305">2.6 Signature Confirmation</span></span>  
 <span data-ttu-id="83dec-306">Подтверждение сигнатуры может использоваться в качестве защиты от атак типа «злоумышленник в середине», чтобы защитить набор подписей.</span><span class="sxs-lookup"><span data-stu-id="83dec-306">Signature confirmation can be as protection from middle man attacks to protect the set of signatures.</span></span>  
  
### <a name="27-security-header-layout"></a><span data-ttu-id="83dec-307">2.7 Структура заголовка безопасности</span><span class="sxs-lookup"><span data-stu-id="83dec-307">2.7 Security Header Layout</span></span>  
 <span data-ttu-id="83dec-308">Каждый режим проверки подлинности описывает определенную структуру заголовка безопасности.</span><span class="sxs-lookup"><span data-stu-id="83dec-308">Each authentication mode describes a certain layout for the security header.</span></span> <span data-ttu-id="83dec-309">Элементы в заголовке безопасности полуупорядочены.</span><span class="sxs-lookup"><span data-stu-id="83dec-309">Elements within the security header are semi-ordered.</span></span> <span data-ttu-id="83dec-310">Чтобы определить порядок дочерних элементов заголовка безопасности, в спецификации WS-Security Policy определены следующие режимы структуры заголовка безопасности:</span><span class="sxs-lookup"><span data-stu-id="83dec-310">To define the order of security header child elements, WS-Security Policy defines the following security header layout modes:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="83dec-311">Strict</span><span class="sxs-lookup"><span data-stu-id="83dec-311">Strict</span></span>|<span data-ttu-id="83dec-312">Элементы добавляются в заголовок безопасности в соответствии с правилами нумерованной структуры, описанными в разделе 7.7.1 спецификаций Security Policy, на основе общего принципа "объявить перед использованием".</span><span class="sxs-lookup"><span data-stu-id="83dec-312">Items are added to the security header following the numbered layout rules described in Security Policy section 7.7.1 according to a general principle of "declare before use".</span></span>|  
|<span data-ttu-id="83dec-313">Lax</span><span class="sxs-lookup"><span data-stu-id="83dec-313">Lax</span></span>|<span data-ttu-id="83dec-314">Элементы добавляются в заголовок безопасности в любом порядке, отвечающем требованиям безопасности сообщений WSS: SOAP Message Security.</span><span class="sxs-lookup"><span data-stu-id="83dec-314">Items are added to the security header in any order that conforms to WSS: SOAP Message Security.</span></span>|  
|<span data-ttu-id="83dec-315">LaxTimestampFirst</span><span class="sxs-lookup"><span data-stu-id="83dec-315">LaxTimestampFirst</span></span>|<span data-ttu-id="83dec-316">Аналогично Lax, но первым элементом в заголовке безопасности должен быть элемент wsse:Timestamp.</span><span class="sxs-lookup"><span data-stu-id="83dec-316">Same as Lax except that the first item in the security header must be a wsse:Timestamp</span></span>|  
|<span data-ttu-id="83dec-317">LaxTimestampLast</span><span class="sxs-lookup"><span data-stu-id="83dec-317">LaxTimestampLast</span></span>|<span data-ttu-id="83dec-318">Аналогично Lax, но последним элементом в заголовке безопасности должен быть элемент wsse:Timestamp.</span><span class="sxs-lookup"><span data-stu-id="83dec-318">Same as lax except that the last item in the security header must be a wsse:Timestamp</span></span>|  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="83dec-319"> поддерживает все четыре режима структуры заголовка безопасности.</span><span class="sxs-lookup"><span data-stu-id="83dec-319"> supports all four modes for security header layout.</span></span> <span data-ttu-id="83dec-320">В приведенных ниже структурах заголовков безопасности и примерах сообщений для режимов проверки подлинности используется режим "Strict".</span><span class="sxs-lookup"><span data-stu-id="83dec-320">Security header structure and message examples for authentication modes below follow the "Strict" mode.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="83dec-321">2. Общие параметры безопасности сообщений</span><span class="sxs-lookup"><span data-stu-id="83dec-321">2. Common Message Security Parameters</span></span>  
 <span data-ttu-id="83dec-322">В этом подразделе приведены примеры политик для каждого режима проверки подлинности, а также примеры, показывающие структуру заголовка безопасности в сообщениях, которыми обмениваются клиент и служба.</span><span class="sxs-lookup"><span data-stu-id="83dec-322">This section provides example policies for each authentication mode along with examples showing security header structure in messages exchanged by client and service.</span></span>  
  
### <a name="61-transport-protection"></a><span data-ttu-id="83dec-323">6.1 Защита транспорта</span><span class="sxs-lookup"><span data-stu-id="83dec-323">6.1 Transport Protection</span></span>  
 <span data-ttu-id="83dec-324">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предусмотрено пять режимов проверки подлинности, в которых для защиты сообщений используется безопасный транспорт: UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport и SspiNegotiatedOverTransport.</span><span class="sxs-lookup"><span data-stu-id="83dec-324">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides five authentication modes that use secure transport to protect messages; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport and SspiNegotiatedOverTransport.</span></span>  
  
 <span data-ttu-id="83dec-325">Эти режимы проверки подлинности построены с использованием привязок транспорта, описанных в спецификации SecurityPolicy.</span><span class="sxs-lookup"><span data-stu-id="83dec-325">These authentication modes are constructed using the transport binding described in SecurityPolicy.</span></span> <span data-ttu-id="83dec-326">Для режима проверки подлинности UserNameOverTransport маркер UsernameToken является подписанным поддерживающим маркером.</span><span class="sxs-lookup"><span data-stu-id="83dec-326">For the UserNameOverTransport authentication mode the UsernameToken is a signed supporting token.</span></span> <span data-ttu-id="83dec-327">Для других режимов проверки подлинности этот маркер является подписанным подтверждающим маркером.</span><span class="sxs-lookup"><span data-stu-id="83dec-327">For the other authentication modes the token appears as a signed endorsing token.</span></span> <span data-ttu-id="83dec-328">В приложениях C.1.2 и C.1.3 спецификации SecurityPolicy подробно описана структура заголовка безопасности.</span><span class="sxs-lookup"><span data-stu-id="83dec-328">Appendix C.1.2 and C.1.3 of SecurityPolicy describe the security header layout in detail.</span></span> <span data-ttu-id="83dec-329">В приведенных ниже примерах заголовки безопасности для определенного режима проверки подлинности показаны со структурой Strict.</span><span class="sxs-lookup"><span data-stu-id="83dec-329">The following example security headers show the Strict layout for a given authentication mode.</span></span>  
  
 <span data-ttu-id="83dec-330">Свойство Derived Keys для маркеров во всех случаях имеет значение "false".</span><span class="sxs-lookup"><span data-stu-id="83dec-330">The value of the "Derived Keys" property for the tokens in all cases is "false".</span></span>  
  
 <span data-ttu-id="83dec-331">Различные свойства привязок транспорта имеют следующие значения:</span><span class="sxs-lookup"><span data-stu-id="83dec-331">The values of the various properties of the transport binding are as follows:</span></span>  
  
 <span data-ttu-id="83dec-332">Отметка времени: true</span><span class="sxs-lookup"><span data-stu-id="83dec-332">Timestamp: true</span></span>  
  
 <span data-ttu-id="83dec-333">Структура заголовка безопасности: Strict</span><span class="sxs-lookup"><span data-stu-id="83dec-333">Security Header Layout: Strict</span></span>  
  
 <span data-ttu-id="83dec-334">Набор алгоритмов: Basic256</span><span class="sxs-lookup"><span data-stu-id="83dec-334">Algorithm Suite: Basic256</span></span>  
  
#### <a name="611-usernameovertransport"></a><span data-ttu-id="83dec-335">6.1.1 UsernameOverTransport</span><span class="sxs-lookup"><span data-stu-id="83dec-335">6.1.1 UsernameOverTransport</span></span>  
 <span data-ttu-id="83dec-336">В этом режиме проверка подлинности клиента осуществляется с использованием маркера Username, который доступен на уровне SOAP в качестве подписанного поддерживающего маркера, всегда отправляемого от инициатора получателю.</span><span class="sxs-lookup"><span data-stu-id="83dec-336">With this authentication mode, the client authenticates with a Username Token which appears at the SOAP layer as a signed supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="83dec-337">Служба проходит проверку подлинности с использованием сертификата X.509 на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="83dec-337">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="83dec-338">Используется привязка транспорта.</span><span class="sxs-lookup"><span data-stu-id="83dec-338">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="83dec-339">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-339">Policy</span></span>  
  
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
  
 <span data-ttu-id="83dec-340">Структура заголовка безопасности</span><span class="sxs-lookup"><span data-stu-id="83dec-340">Security Header Layout</span></span>  
  
 <span data-ttu-id="83dec-341">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-341">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-342">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-342">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="612-certificateovertransport"></a><span data-ttu-id="83dec-343">6.1.2 CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="83dec-343">6.1.2 CertificateOverTransport</span></span>  
 <span data-ttu-id="83dec-344">В этом режиме проверка подлинности клиента осуществляется с использованием сертификата X.509, который доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера, всегда отправляемого от инициатора получателю.</span><span class="sxs-lookup"><span data-stu-id="83dec-344">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="83dec-345">Служба проходит проверку подлинности с использованием сертификата X.509 на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="83dec-345">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="83dec-346">Используется привязка транспорта.</span><span class="sxs-lookup"><span data-stu-id="83dec-346">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="83dec-347">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-347">Policy</span></span>  
  
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
  
 <span data-ttu-id="83dec-348">Структура заголовка безопасности</span><span class="sxs-lookup"><span data-stu-id="83dec-348">Security Header Layout</span></span>  
  
 <span data-ttu-id="83dec-349">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-349">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-350">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-350">Response</span></span>  
  
```xml  
<o:Security>  
  <u:Timestamp u:Id="_0">  
  ...  
  </u:Timestamp>  
</o:Security>  
```  
  
#### <a name="613-issuedtokenovertransport"></a><span data-ttu-id="83dec-351">6.1.3 IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="83dec-351">6.1.3 IssuedTokenOverTransport</span></span>  
 <span data-ttu-id="83dec-352">В этом режиме проверки подлинности клиент не проходит как таковую проверку подлинности на стороне службы; вместо этого он предоставляет маркер, выданный службой маркеров безопасности (STS) и подтверждает знание общего ключа.</span><span class="sxs-lookup"><span data-stu-id="83dec-352">With this authentication mode the client does not authenticate to the service, as such, but rather presents a token issued by a Security Token Service (STS) and proves knowledge of a shared key.</span></span> <span data-ttu-id="83dec-353">Выданный маркер доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера, всегда отправляемого от инициатора получателю.</span><span class="sxs-lookup"><span data-stu-id="83dec-353">The issued token appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="83dec-354">Служба проходит проверку подлинности с использованием сертификата X.509 на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="83dec-354">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="83dec-355">Используется привязка транспорта.</span><span class="sxs-lookup"><span data-stu-id="83dec-355">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="83dec-356">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-356">Policy</span></span>  
  
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
  
 <span data-ttu-id="83dec-357">Структура заголовка безопасности</span><span class="sxs-lookup"><span data-stu-id="83dec-357">Security Header Layout</span></span>  
  
 <span data-ttu-id="83dec-358">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-358">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-359">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-359">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="614-kerberosovertransport"></a><span data-ttu-id="83dec-360">6.1.4 KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="83dec-360">6.1.4 KerberosOverTransport</span></span>  
 <span data-ttu-id="83dec-361">В этом режиме проверка подлинности клиента на стороне службы осуществляется с использованием билета Kerberos.</span><span class="sxs-lookup"><span data-stu-id="83dec-361">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="83dec-362">Маркер Kerberos доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера.</span><span class="sxs-lookup"><span data-stu-id="83dec-362">The Kerberos token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="83dec-363">Служба проходит проверку подлинности с использованием сертификата X.509 на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="83dec-363">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="83dec-364">Используется привязка транспорта.</span><span class="sxs-lookup"><span data-stu-id="83dec-364">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="83dec-365">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-365">Policy</span></span>  
  
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
  
 <span data-ttu-id="83dec-366">Структура заголовка безопасности</span><span class="sxs-lookup"><span data-stu-id="83dec-366">Security Header Layout</span></span>  
  
 <span data-ttu-id="83dec-367">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-367">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-368">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-368">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="615-sspinegotiatedovertransport"></a><span data-ttu-id="83dec-369">6.1.5 SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="83dec-369">6.1.5 SspiNegotiatedOverTransport</span></span>  
 <span data-ttu-id="83dec-370">В этом режиме для проверки подлинности клиента и сервера используется протокол согласования.</span><span class="sxs-lookup"><span data-stu-id="83dec-370">With this mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="83dec-371">Если это возможно, используется протокол Kerberos, в противном случае - протокол NTLM.</span><span class="sxs-lookup"><span data-stu-id="83dec-371">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="83dec-372">Итоговый маркер контекста безопасности доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера, всегда отправляемого от инициатора получателю.</span><span class="sxs-lookup"><span data-stu-id="83dec-372">The resulting SCT appears at the SOAP layer as an endorsing supporting token that is always sent from initiator to recipient.</span></span> <span data-ttu-id="83dec-373">Служба проходит дополнительную проверку подлинности на транспортном уровне с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="83dec-373">The service is additionally authenticated at the transport layer by an X.509 certificate.</span></span> <span data-ttu-id="83dec-374">Используется привязка транспорта.</span><span class="sxs-lookup"><span data-stu-id="83dec-374">The binding used is a transport binding.</span></span> <span data-ttu-id="83dec-375">Спецификация "SPNEGO" (согласование) описывает, как [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует протокол двоичного согласования SSPI со спецификацией WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="83dec-375">"SPNEGO" (negotiation) describes how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses SSPI binary negotiation protocol with WS-Trust.</span></span> <span data-ttu-id="83dec-376">В этом разделе приведены примеры заголовков безопасности после установления маркера контекста безопасности с помощью подтверждения SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="83dec-376">Security header examples in this section are after the SCT has been established through the SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="83dec-377">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-377">Policy</span></span>  
  
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
  
### <a name="security-header-examples"></a><span data-ttu-id="83dec-378">Примеры заголовков безопасности</span><span class="sxs-lookup"><span data-stu-id="83dec-378">Security Header Examples</span></span>  
 <span data-ttu-id="83dec-379">После установления маркера контекста безопасности с помощью подтверждения SPNEGO при использовании двоичного согласования WS-Trust заголовки безопасности в сообщениях приложения имеют следующую структуру.</span><span class="sxs-lookup"><span data-stu-id="83dec-379">Once the Security Context Token is established through SPNEGO handshake using WS-Trust Binary Negotiation, the application messages have security headers with the following structure.</span></span>  
  
 <span data-ttu-id="83dec-380">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-380">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-381">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-381">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
### <a name="62-using-x509-certificates-for-service-authentication"></a><span data-ttu-id="83dec-382">6.2 Использование сертификатов X.509 для проверки подлинности службы</span><span class="sxs-lookup"><span data-stu-id="83dec-382">6.2 Using X.509 Certificates for Service Authentication</span></span>  
 <span data-ttu-id="83dec-383">В этом разделе рассматриваются следующие режимы проверки подлинности: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate и IssuedTokenForCertificate.</span><span class="sxs-lookup"><span data-stu-id="83dec-383">This section describes the following authentication modes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate and IssuedTokenForCertificate.</span></span>  
  
#### <a name="621-mutualcertificate-wss10"></a><span data-ttu-id="83dec-384">6.2.1 MutualCertificate WSS1.0</span><span class="sxs-lookup"><span data-stu-id="83dec-384">6.2.1 MutualCertificate WSS1.0</span></span>  
 <span data-ttu-id="83dec-385">В этом режиме проверка подлинности клиента осуществляется с использованием сертификата X.509, который доступен на уровне SOAP в качестве маркера инициатора.</span><span class="sxs-lookup"><span data-stu-id="83dec-385">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="83dec-386">Служба также проходит проверку подлинности с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="83dec-386">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="83dec-387">Используется асимметричная привязка со следующими значениями свойств.</span><span class="sxs-lookup"><span data-stu-id="83dec-387">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="83dec-388">Маркер инициатора: сертификат X.509 клиента, задан режим включения …/IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="83dec-388">Initiator Token: the client’s X.509 certificate, with inclusion mode set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="83dec-389">Маркер получателя: сертификат X.509 сервера, задан режим включения …/IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="83dec-389">Recipient Token: Server’s X.509 Certificate, with inclusion mode is set …/IncludeToken/Never</span></span>  
  
 <span data-ttu-id="83dec-390">Защита маркера: False</span><span class="sxs-lookup"><span data-stu-id="83dec-390">Token Protection: False</span></span>  
  
 <span data-ttu-id="83dec-391">Сигнатуры всего заголовка и тела: True</span><span class="sxs-lookup"><span data-stu-id="83dec-391">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="83dec-392">Порядок защиты: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="83dec-392">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="83dec-393">Шифрование подписи: True</span><span class="sxs-lookup"><span data-stu-id="83dec-393">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="83dec-394">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-394">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="83dec-395">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="83dec-395">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="83dec-396">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-396">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-397">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-397">Response</span></span>  
  
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
  
 <span data-ttu-id="83dec-398">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="83dec-398">Security Header Examples: EncryptBeforeSign</span></span>  
  
 <span data-ttu-id="83dec-399">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-399">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-400">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-400">Response</span></span>  
  
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
  
#### <a name="622-mutualcertificateduplex"></a><span data-ttu-id="83dec-401">6.2.2 MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="83dec-401">6.2.2 MutualCertificateDuplex</span></span>  
 <span data-ttu-id="83dec-402">В этом режиме проверка подлинности клиента осуществляется с использованием сертификата X.509, который доступен на уровне SOAP в качестве маркера инициатора.</span><span class="sxs-lookup"><span data-stu-id="83dec-402">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="83dec-403">Служба также проходит проверку подлинности с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="83dec-403">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="83dec-404">Используется асимметричная привязка со следующими значениями свойств.</span><span class="sxs-lookup"><span data-stu-id="83dec-404">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="83dec-405">Маркер инициатора: сертификат X.509 клиента, задан режим включения …/IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="83dec-405">Initiator Token: Client’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="83dec-406">Маркер получателя: сертификат X.509 сервера, задан режим включения …/IncludeToken/AlwaysToInitiator</span><span class="sxs-lookup"><span data-stu-id="83dec-406">Recipient Token: Server’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToInitiator</span></span>  
  
 <span data-ttu-id="83dec-407">Защита маркера: False</span><span class="sxs-lookup"><span data-stu-id="83dec-407">Token Protection: False</span></span>  
  
 <span data-ttu-id="83dec-408">Сигнатуры всего заголовка и тела: True</span><span class="sxs-lookup"><span data-stu-id="83dec-408">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="83dec-409">Порядок защиты: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="83dec-409">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="83dec-410">Шифрование подписи: True</span><span class="sxs-lookup"><span data-stu-id="83dec-410">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="83dec-411">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-411">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="83dec-412">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="83dec-412">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="83dec-413">Запрос и ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-413">Request and Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="83dec-414">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="83dec-414">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="83dec-415">Запрос и ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-415">Request and Response</span></span>  
  
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
  
#### <a name="623-using-symmetricbinding-with-x509-service-authentication"></a><span data-ttu-id="83dec-416">6.2.3 Использование SymmetricBinding с проверкой подлинности службы X.509</span><span class="sxs-lookup"><span data-stu-id="83dec-416">6.2.3 Using SymmetricBinding with X.509 Service Authentication</span></span>  
 <span data-ttu-id="83dec-417">Спецификация "WSS10" обеспечивает ограниченную поддержку сценариев с маркерами X509.</span><span class="sxs-lookup"><span data-stu-id="83dec-417">"WSS10" provided limited support for scenarios with X509 tokens.</span></span> <span data-ttu-id="83dec-418">Например, в этой версии не было способа обеспечить защиту сообщений сигнатурой и шифрованием, используя только маркер X509 службы.</span><span class="sxs-lookup"><span data-stu-id="83dec-418">For example, there was no way to provide signature and encryption protection for messages using only service X509 token.</span></span> <span data-ttu-id="83dec-419">В спецификации "WSS11" вводится использование EncryptedKey в качестве симметричного маркера.</span><span class="sxs-lookup"><span data-stu-id="83dec-419">"WSS11" introduced the usage of EncryptedKey as a symmetric token.</span></span> <span data-ttu-id="83dec-420">Теперь временный ключ, зашифрованный для сертификата X.509 службы, может использоваться для защиты как сообщений запроса, так и сообщений ответа.</span><span class="sxs-lookup"><span data-stu-id="83dec-420">Now a temporary key encrypted for the service's X.509 certificate could be used for both request and response messages protection.</span></span> <span data-ttu-id="83dec-421">Эта схема используется в режимах проверки подлинности, описанных ниже в разделе 6.4.</span><span class="sxs-lookup"><span data-stu-id="83dec-421">The authentication modes described in the section 6.4 below use this pattern.</span></span>  
  
 <span data-ttu-id="83dec-422">В спецификации WS-SecurityPolicy эта схема описывается с помощью привязки SymmetricBinding с маркером X509 службы в качестве маркера защиты.</span><span class="sxs-lookup"><span data-stu-id="83dec-422">WS-SecurityPolicy describes this pattern using SymmetricBinding with Service X509 token as the protection token.</span></span>  
  
 <span data-ttu-id="83dec-423">В режимах проверки подлинности AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 и IssuedTokenForCertificate используется аналогичный экземпляр sp:SymmetricBinding со следующими значениями свойств.</span><span class="sxs-lookup"><span data-stu-id="83dec-423">Authentication modes AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 and IssuedTokenForCertificate all use a similar instance of sp:SymmetricBinding with the following property values:</span></span>  
  
 <span data-ttu-id="83dec-424">Токен защиты: сертификат X.509 сервера, задан режим включения …/IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="83dec-424">Protection Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="83dec-425">Защита маркера: False</span><span class="sxs-lookup"><span data-stu-id="83dec-425">Token Protection: False</span></span>  
  
 <span data-ttu-id="83dec-426">Сигнатуры всего заголовка и тела: True</span><span class="sxs-lookup"><span data-stu-id="83dec-426">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="83dec-427">Порядок защиты: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="83dec-427">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="83dec-428">Шифрование подписи: True</span><span class="sxs-lookup"><span data-stu-id="83dec-428">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="83dec-429">Перечисленные выше режимы проверки подлинности различаются только используемыми поддерживающими маркерами.</span><span class="sxs-lookup"><span data-stu-id="83dec-429">The above authentication modes only differ by the supporting tokens they use.</span></span> <span data-ttu-id="83dec-430">В режиме AnonymousForCertificate поддерживающие маркеры отсутствуют, в режиме MutualCertificate (WSS 1.1) сертификат X509 клиента используется как подтверждающие поддерживающие маркеры, в режиме UserNameForCertificate маркер UserName используется как подписанный поддерживающий маркер, а в режиме IssuedTokenForCertificate выданный маркер используется как подтверждающий поддерживающий маркер.</span><span class="sxs-lookup"><span data-stu-id="83dec-430">AnonymousForCertificate does not have any supporting tokens, MutualCertificate WSS 1.1 has the client’s X509 certificate as an endorsing supporting tokens, UserNameForCertificate has a UserName Token as a signed supporting token and IssuedTokenForCertificate has the issued token as an endorsing supporting token.</span></span>  
  
 <span data-ttu-id="83dec-431">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-431">Policy</span></span>  
  
 <span data-ttu-id="83dec-432">Симметричная привязка</span><span class="sxs-lookup"><span data-stu-id="83dec-432">Symmetric Binding</span></span>  
  
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
  
#### <a name="624-anonymousforcertificate"></a><span data-ttu-id="83dec-433">6.2.4 AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="83dec-433">6.2.4 AnonymousForCertificate</span></span>  
 <span data-ttu-id="83dec-434">В этом режиме проверки подлинности клиент является анонимным, а проверка подлинности службы осуществляется с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="83dec-434">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="83dec-435">Используется экземпляр симметричной привязки, как описано в разделе 6.4.2.</span><span class="sxs-lookup"><span data-stu-id="83dec-435">The binding used is an instance of symmetric binding as described in 6.4.2.</span></span>  
  
 <span data-ttu-id="83dec-436">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-436">Policy</span></span>  
  
 <span data-ttu-id="83dec-437">Сведения о привязке см. в пункте «Политика» раздела 6.2.3</span><span class="sxs-lookup"><span data-stu-id="83dec-437">See "Policy" in 6.2.3 above for binding details</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="83dec-438">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="83dec-438">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="83dec-439">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-439">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-440">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-440">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="83dec-441">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="83dec-441">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="83dec-442">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-442">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-443">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-443">Response</span></span>  
  
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
  
#### <a name="625-usernameforcertificate"></a><span data-ttu-id="83dec-444">6.2.5 UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="83dec-444">6.2.5 UserNameForCertificate</span></span>  
 <span data-ttu-id="83dec-445">В этом режиме проверка подлинности клиента в службе осуществляется с использованием маркера Username, который доступен на уровне SOAP в качестве подписанного поддерживающего маркера.</span><span class="sxs-lookup"><span data-stu-id="83dec-445">With this authentication mode the client authenticates to the service using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="83dec-446">Проверка подлинности службы на стороне клиента осуществляется с помощью сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="83dec-446">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="83dec-447">Используется симметричная привязка, в которой маркер защиты создан с помощью ключа клиента и зашифрован с помощью открытого ключа службы.</span><span class="sxs-lookup"><span data-stu-id="83dec-447">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="83dec-448">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-448">Policy</span></span>  
  
 <span data-ttu-id="83dec-449">Сведения о привязке см. в пункте «Политика» раздела 6.2.3</span><span class="sxs-lookup"><span data-stu-id="83dec-449">See "Policy" in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="83dec-450">Подписанный поддерживающий маркер</span><span class="sxs-lookup"><span data-stu-id="83dec-450">Signed Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="83dec-451">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="83dec-451">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="83dec-452">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-452">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-453">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-453">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="83dec-454">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="83dec-454">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="83dec-455">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-455">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-456">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-456">Response</span></span>  
  
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
  
#### <a name="626-mutualcertificate-wss-11"></a><span data-ttu-id="83dec-457">6.2.6 MutualCertificate (WSS 1.1)</span><span class="sxs-lookup"><span data-stu-id="83dec-457">6.2.6 MutualCertificate (WSS 1.1)</span></span>  
 <span data-ttu-id="83dec-458">В этом режиме проверка подлинности клиента осуществляется с использованием сертификата X.509, который доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера.</span><span class="sxs-lookup"><span data-stu-id="83dec-458">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="83dec-459">Служба также проходит проверку подлинности с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="83dec-459">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="83dec-460">Используется симметричная привязка, в которой маркер защиты создан с помощью ключа клиента и зашифрован с помощью открытого ключа службы.</span><span class="sxs-lookup"><span data-stu-id="83dec-460">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="83dec-461">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-461">Policy</span></span>  
  
 <span data-ttu-id="83dec-462">Сведения о привязке см. в пункте «Политика» раздела 6.2.3</span><span class="sxs-lookup"><span data-stu-id="83dec-462">See Policy in 6.2.3 for binding details</span></span>  
  
 <span data-ttu-id="83dec-463">Подтверждающий поддерживающий маркер</span><span class="sxs-lookup"><span data-stu-id="83dec-463">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="83dec-464">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="83dec-464">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="83dec-465">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-465">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-466">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-466">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="83dec-467">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="83dec-467">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="83dec-468">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-468">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-469">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-469">Response</span></span>  
  
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
  
#### <a name="627-issuedtokenforcertificate"></a><span data-ttu-id="83dec-470">6.2.7 IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="83dec-470">6.2.7 IssuedTokenForCertificate</span></span>  
 <span data-ttu-id="83dec-471">В этом режиме проверки подлинности клиент не проходит как таковую проверку подлинности на стороне службы; вместо этого он предоставляет маркер, выданный службой маркеров безопасности и подтверждает знание общего ключа.</span><span class="sxs-lookup"><span data-stu-id="83dec-471">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by a STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="83dec-472">Выданный маркер доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера.</span><span class="sxs-lookup"><span data-stu-id="83dec-472">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="83dec-473">Проверка подлинности службы на стороне клиента осуществляется с помощью сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="83dec-473">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="83dec-474">Используется симметричная привязка, в которой маркер защиты создан с помощью ключа клиента и зашифрован с помощью открытого ключа службы.</span><span class="sxs-lookup"><span data-stu-id="83dec-474">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="83dec-475">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-475">Policy</span></span>  
  
 <span data-ttu-id="83dec-476">Сведения о привязке см. в пункте «Политика» раздела 6.2.3</span><span class="sxs-lookup"><span data-stu-id="83dec-476">See Policy in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="83dec-477">Подтверждающий поддерживающий маркер</span><span class="sxs-lookup"><span data-stu-id="83dec-477">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="83dec-478">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="83dec-478">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="83dec-479">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-479">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-480">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-480">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="83dec-481">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="83dec-481">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="83dec-482">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-482">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-483">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-483">Response</span></span>  
  
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
  
## <a name="63-kerberos"></a><span data-ttu-id="83dec-484">6.3 Kerberos</span><span class="sxs-lookup"><span data-stu-id="83dec-484">6.3 Kerberos</span></span>  
 <span data-ttu-id="83dec-485">В этом режиме проверка подлинности клиента на стороне службы осуществляется с использованием билета Kerberos.</span><span class="sxs-lookup"><span data-stu-id="83dec-485">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="83dec-486">Этот же билет обеспечивает проверку подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="83dec-486">That same ticket also provides server authentication.</span></span> <span data-ttu-id="83dec-487">Используется симметричная привязка со следующими свойствами.</span><span class="sxs-lookup"><span data-stu-id="83dec-487">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="83dec-488">Токен защиты: билет kerberos, задан режим включения …/IncludeToken/Once</span><span class="sxs-lookup"><span data-stu-id="83dec-488">Protection Token: Kerberos Ticket, inclusion mode is set to .../IncludeToken/Once</span></span>  
<span data-ttu-id="83dec-489">Защита маркера: False</span><span class="sxs-lookup"><span data-stu-id="83dec-489">Token Protection: False</span></span>  
  
 <span data-ttu-id="83dec-490">Сигнатуры всего заголовка и тела: True</span><span class="sxs-lookup"><span data-stu-id="83dec-490">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="83dec-491">Порядок защиты: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="83dec-491">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="83dec-492">Шифрование подписи: True</span><span class="sxs-lookup"><span data-stu-id="83dec-492">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="83dec-493">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-493">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="83dec-494">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="83dec-494">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="83dec-495">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-495">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-496">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-496">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="83dec-497">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="83dec-497">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="83dec-498">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-498">Request</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
 <span data-ttu-id="83dec-499">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-499">Response</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
#### <a name="64-issuedtoken"></a><span data-ttu-id="83dec-500">6.4 IssuedToken</span><span class="sxs-lookup"><span data-stu-id="83dec-500">6.4 IssuedToken</span></span>  
 <span data-ttu-id="83dec-501">В этом режиме проверки подлинности клиент не проходит как таковую проверку подлинности на стороне службы; вместо этого клиент предоставляет маркер, выданный службой маркеров безопасности и подтверждает знание общего ключа.</span><span class="sxs-lookup"><span data-stu-id="83dec-501">With this authentication mode the client does not authenticate to the service, as such, rather the client presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="83dec-502">Служба не проходит как таковую проверку подлинности на стороне клиента, но служба маркеров безопасности шифрует общий ключ как часть выдаваемого маркера, чтобы только служба могла расшифровать этот ключ.</span><span class="sxs-lookup"><span data-stu-id="83dec-502">The service is not authenticated to the client, as such, instead the STS encrypts the shared key as part of the issued token such that only the service can decrypt the key.</span></span> <span data-ttu-id="83dec-503">Используется симметричная привязка со следующими свойствами.</span><span class="sxs-lookup"><span data-stu-id="83dec-503">The binding used is as symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="83dec-504">Токен защиты: выданный токен, задан режим включения .../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="83dec-504">Protection Token: Issued Token, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="83dec-505">Защита маркера: False</span><span class="sxs-lookup"><span data-stu-id="83dec-505">Token Protection: False</span></span>  
  
 <span data-ttu-id="83dec-506">Сигнатуры всего заголовка и тела: True</span><span class="sxs-lookup"><span data-stu-id="83dec-506">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="83dec-507">Порядок защиты: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="83dec-507">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="83dec-508">Шифрование подписи: True</span><span class="sxs-lookup"><span data-stu-id="83dec-508">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="83dec-509">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-509">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="83dec-510">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="83dec-510">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="83dec-511">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-511">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-512">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-512">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="83dec-513">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="83dec-513">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="83dec-514">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-514">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-515">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-515">Response</span></span>  
  
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
  
### <a name="65-using-sslnegotiated-for-service-authentication"></a><span data-ttu-id="83dec-516">6.5 Использование SslNegotiated для проверки подлинности службы</span><span class="sxs-lookup"><span data-stu-id="83dec-516">6.5 Using SslNegotiated for Service Authentication</span></span>  
 <span data-ttu-id="83dec-517">В этом разделе рассматривается группа режимов проверки подлинности, в которых используется симметричная привязка с маркером защиты, являющимся маркером контекста безопасности в соответствии со спецификацией WS-SecureConversation (WS-SC), значение ключа которого согласовывается путем выполнения протокола TLS с помощью сообщений RST/RSTR спецификации WS-Trust (WS-T).</span><span class="sxs-lookup"><span data-stu-id="83dec-517">This section describes a group of authentication modes that use a symmetric binding with the protection token being a Security Context Token per WS-SecureConversation (WS-SC) whose key value is negotiated by executing the TLS protocol over WS-Trust (WS-T) RST/RSTR messages.</span></span> <span data-ttu-id="83dec-518">Сведения о реализации подтверждения TLS с помощью спецификации WS-Trust приведены в спецификации TLSNEGO.</span><span class="sxs-lookup"><span data-stu-id="83dec-518">Details of the TLS handshake implementation using WS-Trust are described in TLSNEGO.</span></span> <span data-ttu-id="83dec-519">В приведенных ниже примерах сообщений предполагается, что маркер контекста безопасности со связанным контекстом безопасности уже установлен путем подтверждения.</span><span class="sxs-lookup"><span data-stu-id="83dec-519">Here in the message examples we will assume that SCT with an associated security context is already established through a handshake.</span></span>  
  
 <span data-ttu-id="83dec-520">Используется симметричная привязка со следующими свойствами.</span><span class="sxs-lookup"><span data-stu-id="83dec-520">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="83dec-521">Токен защиты: SslContextToken, задан режим включения .../IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="83dec-521">Protection Token: SslContextToken, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="83dec-522">Защита маркера: False</span><span class="sxs-lookup"><span data-stu-id="83dec-522">Token Protection: False</span></span>  
  
 <span data-ttu-id="83dec-523">Сигнатуры всего заголовка и тела: True</span><span class="sxs-lookup"><span data-stu-id="83dec-523">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="83dec-524">Порядок защиты: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="83dec-524">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="83dec-525">Шифрование подписи: True</span><span class="sxs-lookup"><span data-stu-id="83dec-525">Encrypt Signature: True</span></span>  
  
#### <a name="651-policy-for-sslnegotiated-service-authentication"></a><span data-ttu-id="83dec-526">6.5.1 Политика для проверки подлинности службы SslNegotiated</span><span class="sxs-lookup"><span data-stu-id="83dec-526">6.5.1 Policy for SslNegotiated service authentication</span></span>  
 <span data-ttu-id="83dec-527">Политики для всех режимов проверки подлинности в этом разделе аналогичны и различаются только определенными используемыми подписанными поддерживающими или подтверждающими маркерами.</span><span class="sxs-lookup"><span data-stu-id="83dec-527">Policy for all authentication modes in this section are similar and differ only by specific signed supporting or endorsing tokens used.</span></span>  
  
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
  
#### <a name="652-anonymousforsslnegotiated"></a><span data-ttu-id="83dec-528">6.5.2 AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="83dec-528">6.5.2 AnonymousForSslNegotiated</span></span>  
 <span data-ttu-id="83dec-529">В этом режиме проверки подлинности клиент является анонимным, а проверка подлинности службы осуществляется с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="83dec-529">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="83dec-530">Используется экземпляр симметричной привязки, как описано выше в разделе 6.5.1.</span><span class="sxs-lookup"><span data-stu-id="83dec-530">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="83dec-531">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-531">Policy</span></span>  
  
 <span data-ttu-id="83dec-532">Сведения о привязке см. в пункте «Политика» раздела 6.5.1.</span><span class="sxs-lookup"><span data-stu-id="83dec-532">See Policy in 6.5.1 above for binding details.</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="83dec-533">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="83dec-533">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="83dec-534">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-534">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-535">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-535">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="83dec-536">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="83dec-536">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="83dec-537">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-537">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-538">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-538">Response</span></span>  
  
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
  
#### <a name="653-usernameforsslnegotiated"></a><span data-ttu-id="83dec-539">6.5.3 UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="83dec-539">6.5.3 UserNameForSslNegotiated</span></span>  
 <span data-ttu-id="83dec-540">В этом режиме проверка подлинности клиента осуществляется с использованием маркера Username, который доступен на уровне SOAP в качестве подписанного поддерживающего маркера.</span><span class="sxs-lookup"><span data-stu-id="83dec-540">With this authentication mode the client is authenticates using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="83dec-541">Служба проходит проверку подлинности с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="83dec-541">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="83dec-542">Используется экземпляр симметричной привязки, как описано в разделе 6.5.1.</span><span class="sxs-lookup"><span data-stu-id="83dec-542">The binding used is an instance of symmetric binding as described in 6.5.1.</span></span>  
  
 <span data-ttu-id="83dec-543">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-543">Policy</span></span>  
  
 <span data-ttu-id="83dec-544">Сведения о привязке см. в разделе 6.5.1</span><span class="sxs-lookup"><span data-stu-id="83dec-544">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="83dec-545">Подписанный поддерживающий маркер</span><span class="sxs-lookup"><span data-stu-id="83dec-545">Signed Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="83dec-546">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="83dec-546">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="83dec-547">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-547">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-548">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-548">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="83dec-549">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="83dec-549">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="83dec-550">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-550">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-551">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-551">Response</span></span>  
  
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
  
#### <a name="654-issuedtokenforsslnegotiated"></a><span data-ttu-id="83dec-552">6.5.4 IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="83dec-552">6.5.4 IssuedTokenForSslNegotiated</span></span>  
 <span data-ttu-id="83dec-553">В этом режиме проверки подлинности клиент не проходит как таковую проверку подлинности на стороне службы; вместо этого он предоставляет маркер, выданный службой маркеров безопасности и подтверждает знание общего ключа.</span><span class="sxs-lookup"><span data-stu-id="83dec-553">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="83dec-554">Выданный маркер доступен на уровне SOAP в качестве подтверждающего поддерживающего маркера.</span><span class="sxs-lookup"><span data-stu-id="83dec-554">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="83dec-555">Служба проходит проверку подлинности с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="83dec-555">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="83dec-556">Используется экземпляр симметричной привязки, как описано выше в разделе 6.5.1.</span><span class="sxs-lookup"><span data-stu-id="83dec-556">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="83dec-557">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-557">Policy</span></span>  
  
 <span data-ttu-id="83dec-558">Сведения о привязке см. в разделе 6.5.1</span><span class="sxs-lookup"><span data-stu-id="83dec-558">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="83dec-559">Подтверждающий поддерживающий маркер</span><span class="sxs-lookup"><span data-stu-id="83dec-559">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="83dec-560">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="83dec-560">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="83dec-561">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-561">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-562">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-562">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="83dec-563">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="83dec-563">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="83dec-564">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-564">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-565">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-565">Response</span></span>  
  
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
  
#### <a name="655-mutualsslnegotiated"></a><span data-ttu-id="83dec-566">6.5.5 MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="83dec-566">6.5.5 MutualSslNegotiated</span></span>  
 <span data-ttu-id="83dec-567">В этом режиме проверка подлинности клиента и службы осуществляется с использованием сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="83dec-567">With this authentication mode the client and the service authenticate using X.509 certificates.</span></span> <span data-ttu-id="83dec-568">Используется экземпляр симметричной привязки, как описано выше в разделе 6.5.1.</span><span class="sxs-lookup"><span data-stu-id="83dec-568">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="83dec-569">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-569">Policy</span></span>  
  
 <span data-ttu-id="83dec-570">Сведения о привязке см. в разделе 6.5.1</span><span class="sxs-lookup"><span data-stu-id="83dec-570">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="83dec-571">Подтверждающий поддерживающий маркер</span><span class="sxs-lookup"><span data-stu-id="83dec-571">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="83dec-572">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="83dec-572">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="83dec-573">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-573">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-574">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-574">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="83dec-575">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="83dec-575">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="83dec-576">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-576">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-577">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-577">Response</span></span>  
  
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
  
### <a name="66-sspinegotiated"></a><span data-ttu-id="83dec-578">6.6 SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="83dec-578">6.6 SspiNegotiated</span></span>  
 <span data-ttu-id="83dec-579">В этом режиме для проверки подлинности клиента и сервера используется протокол согласования.</span><span class="sxs-lookup"><span data-stu-id="83dec-579">With this authentication mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="83dec-580">Если это возможно, используется протокол Kerberos, в противном случае - протокол NTLM.</span><span class="sxs-lookup"><span data-stu-id="83dec-580">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="83dec-581">Используется симметричная привязка со следующими свойствами.</span><span class="sxs-lookup"><span data-stu-id="83dec-581">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="83dec-582">Токен защиты: SpnegoContextToken, задан режим включения .../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="83dec-582">Protection Token: SpnegoContextToken, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="83dec-583">Защита маркера: False</span><span class="sxs-lookup"><span data-stu-id="83dec-583">Token Protection: False</span></span>  
  
 <span data-ttu-id="83dec-584">Сигнатуры всего заголовка и тела: True</span><span class="sxs-lookup"><span data-stu-id="83dec-584">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="83dec-585">Порядок защиты: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="83dec-585">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="83dec-586">Шифрование подписи: True</span><span class="sxs-lookup"><span data-stu-id="83dec-586">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="83dec-587">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-587">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="83dec-588">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="83dec-588">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="83dec-589">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-589">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-590">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-590">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="83dec-591">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="83dec-591">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="83dec-592">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-592">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-593">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-593">Response</span></span>  
  
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
  
### <a name="67-secureconversation"></a><span data-ttu-id="83dec-594">6.7 SecureConversation</span><span class="sxs-lookup"><span data-stu-id="83dec-594">6.7 SecureConversation</span></span>  
 <span data-ttu-id="83dec-595">Используется симметричная привязка, в которой маркером защиты является маркер контекста безопасности в соответствии со спецификацией WS-SecureConversation (WS-SC).</span><span class="sxs-lookup"><span data-stu-id="83dec-595">The binding used is a symmetric binding with the protection token being a SCT per WS-SecureConversation (WS-SC).</span></span> <span data-ttu-id="83dec-596">Согласование маркера контекста безопасности производится с использованием спецификации WS-Trust (WS-Trust) или WS-SecureConversation (WS-SC) в соответствии с вложенной привязкой, которая сама является симметричной привязкой, использующей протокол согласования.</span><span class="sxs-lookup"><span data-stu-id="83dec-596">The SCT is negotiated using WS-Trust (WS-Trust) or WS-SecureConversation (WS-SC) according to a nested binding, which is itself a symmetric binding that uses a negotiation protocol.</span></span> <span data-ttu-id="83dec-597">При возможности в протоколе согласования для проверки подлинности клиента и сервера используется протокол Kerberos.</span><span class="sxs-lookup"><span data-stu-id="83dec-597">The negotiation protocol will use Kerberos to perform client and server authentication if possible.</span></span> <span data-ttu-id="83dec-598">Если использование протокола Kerberos невозможно, используется резервный протокол NTLM.</span><span class="sxs-lookup"><span data-stu-id="83dec-598">If Kerberos cannot be used, it will fall back to NTLM.</span></span>  
  
 <span data-ttu-id="83dec-599">Политика</span><span class="sxs-lookup"><span data-stu-id="83dec-599">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="83dec-600">Примеры заголовков безопасности: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="83dec-600">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="83dec-601">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-601">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-602">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-602">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="83dec-603">Примеры заголовков безопасности: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="83dec-603">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="83dec-604">Запрос</span><span class="sxs-lookup"><span data-stu-id="83dec-604">Request</span></span>  
  
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
  
 <span data-ttu-id="83dec-605">Ответ</span><span class="sxs-lookup"><span data-stu-id="83dec-605">Response</span></span>  
  
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
