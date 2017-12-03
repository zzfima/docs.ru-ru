---
title: "Практическое руководство. Настройка служб WCF для взаимодействия с клиентами WSE 3.0"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5589ad8e4193416738da98676551bbf82c128a79
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="865ac-102">Практическое руководство. Настройка служб WCF для взаимодействия с клиентами WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="865ac-102">How to: Configure WCF Services to Interoperate with WSE 3.0 Clients</span></span>
<span data-ttu-id="865ac-103">Службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] на уровне каналов связи совместимы с клиентами расширений веб-служб версии 3.0 для Microsoft .NET (WSE), если службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] настроены на использование спецификации WS-Addressing (версия от августа 2004 г.).</span><span class="sxs-lookup"><span data-stu-id="865ac-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) clients when [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="865ac-104">Включение службы WCF для взаимодействия с клиентами WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="865ac-104">To enable a WCF service to interoperate with WSE 3.0 clients</span></span>  
  
1.  <span data-ttu-id="865ac-105">Определите пользовательскую привязку для службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="865ac-105">Define a custom binding for the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
     <span data-ttu-id="865ac-106">Чтобы указать, что для кодирования сообщений используется версия спецификации WS-Addressing от августа 2004 г., необходимо создать пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="865ac-106">To specify that the August 2004 version of the WS-Addressing specification is used for message encoding, a custom binding must be created.</span></span>  
  
    1.  <span data-ttu-id="865ac-107">Добавить дочерний элемент [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) для [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) файла конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="865ac-107">Add a child [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) to the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) of the service's configuration file.</span></span>  
  
    2.  <span data-ttu-id="865ac-108">Укажите имя для привязки, добавляя [ \<привязки >](../../../../docs/framework/misc/binding.md) для [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) и параметр `name` атрибута.</span><span class="sxs-lookup"><span data-stu-id="865ac-108">Specify a name for the binding, by adding a [\<binding>](../../../../docs/framework/misc/binding.md) to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) and setting the `name` attribute.</span></span>  
  
    3.  <span data-ttu-id="865ac-109">Укажите режим проверки подлинности и версии спецификации WS-Security, которые используются для защиты сообщений, которые совместимы с WSE 3.0, путем добавления дочернего [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) для [ \<привязки >](../../../../docs/framework/misc/binding.md).</span><span class="sxs-lookup"><span data-stu-id="865ac-109">Specify an authentication mode and the version of the WS-Security specifications that are used to secure messages that are compatible with WSE 3.0, by adding a child [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) to the [\<binding>](../../../../docs/framework/misc/binding.md).</span></span>  
  
         <span data-ttu-id="865ac-110">Чтобы задать режим проверки подлинности, установите `authenicationMode` атрибут [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="865ac-110">To set the authentication mode, set the `authenicationMode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="865ac-111">Режим проверки подлинности примерно соответствует готовому к использованию утверждению безопасности в WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="865ac-111">An authentication mode is roughly equivalent to a turnkey security assertion in WSE 3.0.</span></span> <span data-ttu-id="865ac-112">В следующей таблице показано соответствие между режимами проверки подлинности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и готовыми к использованию утверждениями безопасности в WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="865ac-112">The following table maps authentication modes in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to turnkey security assertions in WSE 3.0.</span></span>  
  
        |<span data-ttu-id="865ac-113">Режим проверки подлинности WCF</span><span class="sxs-lookup"><span data-stu-id="865ac-113">WCF Authentication Mode</span></span>|<span data-ttu-id="865ac-114">Готовое к использованию утверждение безопасности WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="865ac-114">WSE 3.0 turnkey security assertion</span></span>|  
        |-----------------------------|----------------------------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|  
  
         <span data-ttu-id="865ac-115">\*Одно из основных различий между `mutualCertificate10Security` и `mutualCertificate11Security` готовые утверждения безопасности — это версия спецификации WS-Security, используемой в WSE для защиты сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="865ac-115">\* One of the primary differences between the `mutualCertificate10Security` and `mutualCertificate11Security` turnkey security assertions is the version of the WS-Security specification that WSE uses to secure the SOAP messages.</span></span> <span data-ttu-id="865ac-116">Для `mutualCertificate10Security` используется версия WS-Security 1.0, а для `mutualCertificate11Security` - версия WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="865ac-116">For `mutualCertificate10Security`, WS-Security 1.0 is used, whereas WS-Security 1.1 is used for `mutualCertificate11Security`.</span></span> <span data-ttu-id="865ac-117">Для [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], версия спецификации WS-Security, указанная в `messageSecurityVersion` атрибут [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="865ac-117">For [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], the version of the WS-Security specification is specified in the `messageSecurityVersion` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>  
  
         <span data-ttu-id="865ac-118">Чтобы установить версию спецификации WS-Security, который используется для защиты сообщений SOAP, задайте `messageSecurityVersion` атрибут [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="865ac-118">To set the version of the WS-Security specification that is used to secure SOAP messages, set the `messageSecurityVersion` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="865ac-119">Для взаимодействия с WSE 3.0 установите для атрибута `messageSecurityVersion` значение <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span><span class="sxs-lookup"><span data-stu-id="865ac-119">To interoperate with WSE 3.0, set the value of the `messageSecurityVersion` attribute to <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span></span>  
  
    4.  <span data-ttu-id="865ac-120">Укажите используемые версии спецификации WS-Addressing августа 2004 г. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] путем добавления [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) и задайте `messageVersion` для него значение <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span><span class="sxs-lookup"><span data-stu-id="865ac-120">Specify that the August 2004 version of the WS-Addressing specification is used by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] by adding a [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) and set the `messageVersion` to its value to <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="865ac-121">При использовании протокола SOAP 1.2 задайте для атрибута `messageVersion` значение <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span><span class="sxs-lookup"><span data-stu-id="865ac-121">When you are using SOAP 1.2, set the `messageVersion` attribute to <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span></span>  
  
2.  <span data-ttu-id="865ac-122">Укажите, что служба использует пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="865ac-122">Specify that the service uses the custom binding.</span></span>  
  
    1.  <span data-ttu-id="865ac-123">Задать `binding` атрибут [ \<endpoint >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) элемент `customBinding`.</span><span class="sxs-lookup"><span data-stu-id="865ac-123">Set the `binding` attribute of the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element to `customBinding`.</span></span>  
  
    2.  <span data-ttu-id="865ac-124">Задать `bindingConfiguration` атрибут [ \<endpoint >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) элемента значение, указанное в `name` атрибут [ \<привязки >](../../../../docs/framework/misc/binding.md) настраиваемый привязка.</span><span class="sxs-lookup"><span data-stu-id="865ac-124">Set the `bindingConfiguration` attribute of the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element to the value specified in the `name` attribute of the [\<binding>](../../../../docs/framework/misc/binding.md) for the custom binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="865ac-125">Пример</span><span class="sxs-lookup"><span data-stu-id="865ac-125">Example</span></span>  
 <span data-ttu-id="865ac-126">Следующий пример кода задает, что служба `Service.HelloWorldService` использует для взаимодействия с клиентами WSE 3.0 пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="865ac-126">The following code example specifies that the `Service.HelloWorldService` uses a custom binding to interoperate with WSE 3.0 clients.</span></span> <span data-ttu-id="865ac-127">Пользовательская привязка задает, что для кодирования пересылаемых сообщений используется версия спецификация WS-Addressing от августа 2004 г. и набор спецификаций WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="865ac-127">The custom binding specifies that the August 2004 version of the WS-Addressing and the WS-Security 1.1 set of specifications are used to encode the exchanged messages.</span></span> <span data-ttu-id="865ac-128">Защита сообщений обеспечивается с помощью режима проверки подлинности <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>.</span><span class="sxs-lookup"><span data-stu-id="865ac-128">The messages are secured using the <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> authentication mode.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service   
        behaviorConfiguration="ServiceBehavior"   
        name="Service.HelloWorldService">  
        <endpoint binding="customBinding" address=""  
          bindingConfiguration="ServiceBinding"  
          contract="Service.IHelloWorld"></endpoint>  
      </service>  
    </services>  
  
    <bindings>  
      <customBinding>  
        <binding name="ServiceBinding">  
          <security authenticationMode="AnonymousForCertificate"  
                  messageProtectionOrder="SignBeforeEncrypt"  
                  messageSecurityVersion="WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10"  
                  requireDerivedKeys="false">  
          </security>  
          <textMessageEncoding messageVersion ="Soap11WSAddressingAugust2004"></textMessageEncoding>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <behavior name="ServiceBehavior" returnUnknownExceptionsAsFaults="true">  
        <serviceCredentials>  
          <serviceCertificate findValue="CN=WCFQuickstartServer" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName"/>  
        </serviceCredentials>  
      </behavior>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="865ac-129">См. также</span><span class="sxs-lookup"><span data-stu-id="865ac-129">See Also</span></span>  
 [<span data-ttu-id="865ac-130">Как: изменение привязки, предоставляемые системой</span><span class="sxs-lookup"><span data-stu-id="865ac-130">How to: Customize a System-Provided Binding</span></span>](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)
