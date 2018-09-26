---
title: Практическое руководство. Создание сеанса безопасности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
author: BrucePerlerMS
ms.openlocfilehash: 01ad849090bd66ba7e0b4e062f78ad7a04ad059d
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47200234"
---
# <a name="how-to-create-a-secure-session"></a><span data-ttu-id="ae90f-102">Практическое руководство. Создание сеанса безопасности</span><span class="sxs-lookup"><span data-stu-id="ae90f-102">How to: Create a Secure Session</span></span>
<span data-ttu-id="ae90f-103">За исключением элемента [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) привязки, предоставляемые системой привязки в Windows Communication Foundation (WCF) автоматически используют безопасные сеансы при включенной безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="ae90f-103">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, the system-provided bindings in Windows Communication Foundation (WCF) automatically use secure sessions when message security is enabled.</span></span>  
  
 <span data-ttu-id="ae90f-104">По умолчанию безопасные сеансы не сохраняются на перезапускаемом веб-сервере.</span><span class="sxs-lookup"><span data-stu-id="ae90f-104">By default, secure sessions do not survive a Web server that is recycled.</span></span> <span data-ttu-id="ae90f-105">После установления безопасного сеанса клиент и служба кэшируют ключ, связанный с безопасным сеансом.</span><span class="sxs-lookup"><span data-stu-id="ae90f-105">When a secure session is established, the client and the service cache the key that is associated with the secure session.</span></span> <span data-ttu-id="ae90f-106">При обмене сообщениями происходит только обмен идентификатором кэшированного ключа.</span><span class="sxs-lookup"><span data-stu-id="ae90f-106">As the messages are exchanged, only an identifier to the cached key is exchanged.</span></span> <span data-ttu-id="ae90f-107">При перезапуске веб-сервера кэш также перезапускается, следовательно, веб-сервер не может извлечь кэшированный ключ для идентификатора.</span><span class="sxs-lookup"><span data-stu-id="ae90f-107">If the Web server is recycled, the cache is also recycled, such that the Web server cannot retrieve the cached key for the identifier.</span></span> <span data-ttu-id="ae90f-108">В этом случае исключение передается назад клиенту.</span><span class="sxs-lookup"><span data-stu-id="ae90f-108">If this happens, an exception is thrown back to the client.</span></span> <span data-ttu-id="ae90f-109">Безопасные сеансы, использующие токен контекста безопасности с отслеживанием состояния (SCT), сохраняются при перезапуске веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="ae90f-109">Secure sessions that use a stateful security context token (SCT) can survive a Web server being recycled.</span></span> <span data-ttu-id="ae90f-110">Дополнительные сведения об использовании SCT с отслеживанием состояния в безопасном сеансе см. в разделе [как: создание токена контекста безопасности для безопасного сеанса](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span><span class="sxs-lookup"><span data-stu-id="ae90f-110">For more information about using a stateful SCT in a secure session, see [How to: Create a Security Context Token for a Secure Session](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a><span data-ttu-id="ae90f-111">Задание использования службой безопасных сеансов с помощью одной из предоставляемых системой привязок</span><span class="sxs-lookup"><span data-stu-id="ae90f-111">To specify that a service uses secure sessions by using one of the system-provided bindings</span></span>  
  
-   <span data-ttu-id="ae90f-112">Настройте службу на использование предоставляемой системой привязки, поддерживающей безопасность сообщений.</span><span class="sxs-lookup"><span data-stu-id="ae90f-112">Configure a service to use a system-provided binding that supports message security.</span></span>  
  
     <span data-ttu-id="ae90f-113">За исключением элемента [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) привязки, если предоставляемые системой привязки настроены на использование безопасности сообщений, WCF автоматически использует безопасные сеансы.</span><span class="sxs-lookup"><span data-stu-id="ae90f-113">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, when the system-provided bindings are configured to use message security, WCF automatically uses secure sessions.</span></span> <span data-ttu-id="ae90f-114">В следующей таблице перечислены предоставляемые системой привязки, поддерживающие безопасность сообщений, и указано, является ли безопасность сообщений механизмом безопасности по умолчанию для данной привязки.</span><span class="sxs-lookup"><span data-stu-id="ae90f-114">The following table lists the system-provided bindings that support message security and whether message security is the default security mechanism.</span></span>  
  
    |<span data-ttu-id="ae90f-115">Предоставляемая системой привязка</span><span class="sxs-lookup"><span data-stu-id="ae90f-115">System-provided binding</span></span>|<span data-ttu-id="ae90f-116">Элемент конфигурации</span><span class="sxs-lookup"><span data-stu-id="ae90f-116">Configuration element</span></span>|<span data-ttu-id="ae90f-117">Безопасность сообщений включена по умолчанию</span><span class="sxs-lookup"><span data-stu-id="ae90f-117">Message security on by default</span></span>|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[<span data-ttu-id="ae90f-118">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="ae90f-118">\<basicHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|<span data-ttu-id="ae90f-119">Нет</span><span class="sxs-lookup"><span data-stu-id="ae90f-119">No</span></span>|  
    |<xref:System.ServiceModel.WSHttpBinding>|[<span data-ttu-id="ae90f-120">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="ae90f-120">\<wsHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="ae90f-121">Да</span><span class="sxs-lookup"><span data-stu-id="ae90f-121">Yes</span></span>|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[<span data-ttu-id="ae90f-122">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="ae90f-122">\<wsDualHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|<span data-ttu-id="ae90f-123">Да</span><span class="sxs-lookup"><span data-stu-id="ae90f-123">Yes</span></span>|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[<span data-ttu-id="ae90f-124">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="ae90f-124">\<wsFederationHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|<span data-ttu-id="ae90f-125">Да</span><span class="sxs-lookup"><span data-stu-id="ae90f-125">Yes</span></span>|  
    |<xref:System.ServiceModel.NetTcpBinding>|[<span data-ttu-id="ae90f-126">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="ae90f-126">\<netTcpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|<span data-ttu-id="ae90f-127">Нет</span><span class="sxs-lookup"><span data-stu-id="ae90f-127">No</span></span>|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[<span data-ttu-id="ae90f-128">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="ae90f-128">\<netMsmqBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|<span data-ttu-id="ae90f-129">Нет</span><span class="sxs-lookup"><span data-stu-id="ae90f-129">No</span></span>|  
  
     <span data-ttu-id="ae90f-130">В следующем примере кода с помощью конфигурации задается привязка с именем `wsHttpBinding_Calculator` , использующий [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), безопасность сообщений и безопасные сеансы.</span><span class="sxs-lookup"><span data-stu-id="ae90f-130">The following code example uses configuration to specify a binding named `wsHttpBinding_Calculator` that uses the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions.</span></span>  
  
    ```xml  
    <bindings>  
      <WSHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </WSHttpBinding>  
    </bindings>  
    ```  
  
     <span data-ttu-id="ae90f-131">В следующем примере кода указывает, что [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), безопасность сообщений и безопасные сеансы используются для защиты `secureCalculator` службы.</span><span class="sxs-lookup"><span data-stu-id="ae90f-131">The following code example specifies that the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions are used to secure the `secureCalculator` service.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="ae90f-132">Можно отключить безопасные сеансы для [ <wsHttpBinding> ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) , задав `establishSecurityContext` атрибут `false`.</span><span class="sxs-lookup"><span data-stu-id="ae90f-132">Secure sessions can be turned off for the [<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) by setting the `establishSecurityContext` attribute to `false`.</span></span> <span data-ttu-id="ae90f-133">Безопасные сеансы для других предоставляемых системой привязок можно отключить, только создав пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="ae90f-133">For the other system-provided bindings, secure sessions can only be turned off by creating a custom binding.</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a><span data-ttu-id="ae90f-134">Задание использования службой безопасных сеансов с помощью пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="ae90f-134">To specify that a service uses secure sessions by using a custom binding</span></span>  
  
-   <span data-ttu-id="ae90f-135">Создайте пользовательскую привязку, которая задает, что сообщения SOAP защищаются безопасным сеансом.</span><span class="sxs-lookup"><span data-stu-id="ae90f-135">Create a custom binding that specifies that SOAP messages are protected by a secure session.</span></span>  
  
     <span data-ttu-id="ae90f-136">Дополнительные сведения о создании пользовательской привязки, см. в разделе [как: изменение привязки, предоставляемые системой](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span><span class="sxs-lookup"><span data-stu-id="ae90f-136">For more information about creating a custom binding, see [How to: Customize a System-Provided Binding](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>  
  
     <span data-ttu-id="ae90f-137">В следующем примере кода с помощью конфигурации задается пользовательская привязка для обмена сообщениями с использованием безопасного сеанса.</span><span class="sxs-lookup"><span data-stu-id="ae90f-137">The following code example uses configuration to specify a custom binding that messages using a secure session.</span></span>  
  
    ```xml  
    <bindings>  
      <!-- configure a custom binding -->  
      <customBinding>  
        <binding name="customBinding_Calculator">  
          <security authenticationMode="SecureConversation" />  
          <secureConversationBootstrap authenticationMode="SspiNegotiated" />  
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
     <span data-ttu-id="ae90f-138">В следующем примере кода создается пользовательская привязка, которая использует режим проверки подлинности <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> для начальной загрузки безопасного сеанса.</span><span class="sxs-lookup"><span data-stu-id="ae90f-138">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="ae90f-139">См. также</span><span class="sxs-lookup"><span data-stu-id="ae90f-139">See Also</span></span>  
 [<span data-ttu-id="ae90f-140">Общие сведения о привязках WCF</span><span class="sxs-lookup"><span data-stu-id="ae90f-140">WCF Bindings Overview</span></span>](../../../../docs/framework/wcf/bindings-overview.md)
