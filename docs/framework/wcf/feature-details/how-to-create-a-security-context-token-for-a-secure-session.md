---
title: "Как создать маркер контекста безопасности с отслеживанием состояния для безопасного сеанса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 640676b6-c75a-4ff7-aea4-b1a1524d71b2
caps.latest.revision: "14"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 83e455c2377168c316bf34c25b687cde48b0fa3a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-security-context-token-for-a-secure-session"></a><span data-ttu-id="9ceff-102">Как создать маркер контекста безопасности с отслеживанием состояния для безопасного сеанса</span><span class="sxs-lookup"><span data-stu-id="9ceff-102">How to: Create a Security Context Token for a Secure Session</span></span>
<span data-ttu-id="9ceff-103">При использовании в безопасном сеансе маркера контекста безопасности (SCT) с отслеживанием состояния сеанс может сохраняться и при перезапуске службы.</span><span class="sxs-lookup"><span data-stu-id="9ceff-103">By using a stateful security context token (SCT) in a secure session, the session can withstand the service being recycled.</span></span> <span data-ttu-id="9ceff-104">Например, если в безопасном сеансе используется маркер SCT без отслеживания состояния, то при сбросе служб IIS данные сеанса, связанного со службой, будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="9ceff-104">For instance, when a stateless SCT is used in a secure session and Internet Information Services (IIS) is reset, then the session data that is associated with the service is lost.</span></span> <span data-ttu-id="9ceff-105">В состав данных сеанса входит кэш маркера SCT.</span><span class="sxs-lookup"><span data-stu-id="9ceff-105">This session data includes an SCT token cache.</span></span> <span data-ttu-id="9ceff-106">Поэтому в следующий раз, когда клиент отправляет в службу маркер SCT без отслеживания состояния, возвращается ошибка, так как невозможно извлечь ключ, связанный с этим маркером SCT.</span><span class="sxs-lookup"><span data-stu-id="9ceff-106">So, the next time a client sends the service a stateless SCT, an error is returned, because the key that is associated with the SCT cannot be retrieved.</span></span> <span data-ttu-id="9ceff-107">Однако если используется маркер SCT с отслеживанием состояния, то ключ, связанный с маркером SCT, содержится в этом маркере SCT.</span><span class="sxs-lookup"><span data-stu-id="9ceff-107">If, however, a stateful SCT is used, then the key that is associated with the SCT is contained within the SCT.</span></span> <span data-ttu-id="9ceff-108">Так как ключ содержится в маркере SCT и, следовательно, в сообщении, перезапуск службы не влияет на безопасный сеанс.</span><span class="sxs-lookup"><span data-stu-id="9ceff-108">Because the key is contained within the SCT and thus contained within the message, the secure session is not affected by the service being recycled.</span></span> <span data-ttu-id="9ceff-109">По умолчанию для безопасных сеансов в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] используются маркеры SCT без отслеживания состояния.</span><span class="sxs-lookup"><span data-stu-id="9ceff-109">By default, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] uses stateless SCTs in a secure session.</span></span> <span data-ttu-id="9ceff-110">В этом разделе описывается, как использовать в безопасном сеансе маркеры SCT с отслеживанием состояния.</span><span class="sxs-lookup"><span data-stu-id="9ceff-110">This topic details how to use stateful SCTs in a secure session.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ceff-111">Маркеры SCT с отслеживанием состояния не могут использоваться в безопасном сеансе, связанном с контрактом, унаследованным от <xref:System.ServiceModel.Channels.IDuplexChannel>.</span><span class="sxs-lookup"><span data-stu-id="9ceff-111">Stateful SCTs cannot be used in a secure session that involves a contract that derives from <xref:System.ServiceModel.Channels.IDuplexChannel>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ceff-112">Для приложений, использующих в безопасных сеансах маркеры SCT с отслеживанием состояния, идентификатором потока для службы должна быть учетная запись пользователя, имеющая связанный с ней профиль пользователя.</span><span class="sxs-lookup"><span data-stu-id="9ceff-112">For applications that use stateful SCTs in a secure session, the thread identity for the service must be a user account that has an associated user profile.</span></span> <span data-ttu-id="9ceff-113">Если служба запущена с учетной записью, не имеющей профиля пользователя (например, `Local Service`), возможно возникновение исключения.</span><span class="sxs-lookup"><span data-stu-id="9ceff-113">When the service is run under an account that does not have a user profile, such as `Local Service`, an exception may be thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ceff-114">Если в ОС Windows XP требуется олицетворение, следует использовать безопасный сеанс без маркера SCT с отслеживанием состояния.</span><span class="sxs-lookup"><span data-stu-id="9ceff-114">When impersonation is required on Windows XP, use a secure session without a stateful SCT.</span></span> <span data-ttu-id="9ceff-115">При использовании маркеров SCT с отслеживанием состояния вместе с олицетворением возникает исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="9ceff-115">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="9ceff-116">[Неподдерживаемые сценарии](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="9ceff-116"> [Unsupported Scenarios](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span></span>  
  
### <a name="to-use-stateful-scts-in-a-secure-session"></a><span data-ttu-id="9ceff-117">Использование маркеров SCT с отслеживанием состояния в безопасном сеансе</span><span class="sxs-lookup"><span data-stu-id="9ceff-117">To use stateful SCTs in a secure session</span></span>  
  
-   <span data-ttu-id="9ceff-118">Создайте пользовательскую привязку, которая задает, что сообщения SOAP защищаются безопасным сеансом, использующим маркер SCT с отслеживанием состояния.</span><span class="sxs-lookup"><span data-stu-id="9ceff-118">Create a custom binding that specifies that SOAP messages are protected by a secure session that uses a stateful SCT.</span></span>  
  
    1.  <span data-ttu-id="9ceff-119">Определите пользовательскую привязку, добавив [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) в файл конфигурации для службы.</span><span class="sxs-lookup"><span data-stu-id="9ceff-119">Define a custom binding, by adding a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) to the configuration file for the service.</span></span>  
  
        ```xml  
        <customBinding>  
        ```  
  
    2.  <span data-ttu-id="9ceff-120">Добавить [ \<привязки >](../../../../docs/framework/misc/binding.md) дочернего элемента [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="9ceff-120">Add a [\<binding>](../../../../docs/framework/misc/binding.md) child element to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
         <span data-ttu-id="9ceff-121">Укажите имя привязки, задав для атрибута `name` имя, уникальное в пределах этого файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9ceff-121">Specify a binding name by setting the `name` attribute to a unique name within the configuration file.</span></span>  
  
        ```xml  
        <binding name="StatefulSCTSecureSession">  
        ```  
  
    3.  <span data-ttu-id="9ceff-122">Укажите режим проверки подлинности для сообщений, отправляемых с этой службой, добавив [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) дочернего элемента [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="9ceff-122">Specify the authentication mode for messages sent to and from this service by adding a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) child element to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
         <span data-ttu-id="9ceff-123">Укажите, что используется безопасный сеанс, задав для атрибута `authenticationMode` значение `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="9ceff-123">Specify that a secure session is used by setting the `authenticationMode` attribute to `SecureConversation`.</span></span> <span data-ttu-id="9ceff-124">Укажите, что используются маркеры SCT с отслеживанием состояния, задав для атрибута `requireSecurityContextCancellation` значение `false`.</span><span class="sxs-lookup"><span data-stu-id="9ceff-124">Specify that stateful SCTs are used by setting the `requireSecurityContextCancellation` attribute to `false`.</span></span>  
  
        ```xml  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
        ```  
  
    4.  <span data-ttu-id="9ceff-125">Укажите способ проверки подлинности клиента при установлен безопасный сеанс, добавив [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) дочернего элемента [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="9ceff-125">Specify how the client is authenticated while the secure session is established by adding a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) child element to the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>  
  
         <span data-ttu-id="9ceff-126">Укажите, как производится проверка подлинности клиента, задав атрибут `authenticationMode`.</span><span class="sxs-lookup"><span data-stu-id="9ceff-126">Specify how the client is authenticated by setting the `authenticationMode` attribute.</span></span>  
  
        ```xml  
        <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        ```  
  
    5.  <span data-ttu-id="9ceff-127">Задания кодирования сообщений, добавив элемент кодирования, таких как [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span><span class="sxs-lookup"><span data-stu-id="9ceff-127">Specify the message encoding by adding an encoding element, such as [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span></span>  
  
        ```xml  
        <textMessageEncoding />  
        ```  
  
    6.  <span data-ttu-id="9ceff-128">Укажите транспорта, добавив элемент транспорта, таких как [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).</span><span class="sxs-lookup"><span data-stu-id="9ceff-128">Specify the transport by adding a transport element, such as the [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).</span></span>  
  
        ```xml  
        <httpTransport />  
        ```  
  
     <span data-ttu-id="9ceff-129">В следующем примере кода с помощью конфигурации задается пользовательская привязка, которая может использоваться сообщениями с маркерами SCT с отслеживанием состояния в безопасном сеансе.</span><span class="sxs-lookup"><span data-stu-id="9ceff-129">The following code example uses configuration to specify a custom binding that messages can use with stateful SCTs in a secure session.</span></span>  
  
    ```xml  
    <customBinding>  
      <binding name="StatefulSCTSecureSession">  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
          <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        </security>  
        <textMessageEncoding />  
        <httpTransport />  
      </binding>  
    </customBinding>  
    ```  
  
## <a name="example"></a><span data-ttu-id="9ceff-130">Пример</span><span class="sxs-lookup"><span data-stu-id="9ceff-130">Example</span></span>  
 <span data-ttu-id="9ceff-131">В следующем примере кода создается пользовательская привязка, которая использует режим проверки подлинности <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> для начальной загрузки безопасного сеанса.</span><span class="sxs-lookup"><span data-stu-id="9ceff-131">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
 [!code-csharp[c_CreateStatefulSCT#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createstatefulsct/cs/secureservice.cs#2)]
 [!code-vb[c_CreateStatefulSCT#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createstatefulsct/vb/secureservice.vb#2)]  
  
 <span data-ttu-id="9ceff-132">При использовании проверки подлинности Windows в сочетании с маркером SCT с отслеживанием состояния [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не заносит в свойство <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> фактический идентификатор вызывающей стороны, но вместо этого задает это свойство как анонимное.</span><span class="sxs-lookup"><span data-stu-id="9ceff-132">When Windows authentication is used in combination with a stateful SCT, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not populate the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property with the actual caller's identity but instead sets the property to anonymous.</span></span> <span data-ttu-id="9ceff-133">Поскольку безопасность [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] должна воссоздавать содержимое контекста безопасности службы для каждого запроса из входящего маркера SCT, сервер не ведет учета безопасных сеансов в памяти.</span><span class="sxs-lookup"><span data-stu-id="9ceff-133">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security must re-create the content of the service security context for every request from the incoming SCT, the server does not keep track of the security session in the memory.</span></span> <span data-ttu-id="9ceff-134">Поскольку выполнить сериализацию экземпляра <xref:System.Security.Principal.WindowsIdentity> в маркер SCT невозможно, свойство <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> возвращает анонимный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="9ceff-134">Because it is impossible to serialize the <xref:System.Security.Principal.WindowsIdentity> instance into the SCT, the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property returns an anonymous identity.</span></span>  
  
 <span data-ttu-id="9ceff-135">Следующая конфигурация демонстрирует это расширение функциональности.</span><span class="sxs-lookup"><span data-stu-id="9ceff-135">The following configuration exhibits this behavior.</span></span>  
  
```xml  
<customBinding>  
  <binding name="Cancellation">  
       <textMessageEncoding />  
        <security   
            requireSecurityContextCancellation="false">  
              <secureConversationBootstrap />  
      </security>  
    <httpTransport />  
  </binding>  
</customBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9ceff-136">См. также</span><span class="sxs-lookup"><span data-stu-id="9ceff-136">See Also</span></span>  
 [<span data-ttu-id="9ceff-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="9ceff-137">\<customBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
