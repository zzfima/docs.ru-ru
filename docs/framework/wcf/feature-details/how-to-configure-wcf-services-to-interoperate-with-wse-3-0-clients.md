---
title: Практическое руководство. Настройка служб WCF для взаимодействия с клиентами WSE 3.0
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: 1c5a5e4e92eedb21e3405370e59344d3b861d1dc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619166"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="d4f70-102">Практическое руководство. Настройка служб WCF для взаимодействия с клиентами WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="d4f70-102">How to: Configure WCF Services to Interoperate with WSE 3.0 Clients</span></span>
<span data-ttu-id="d4f70-103">Службы Windows Communication Foundation (WCF) совместимы на уровне линий связи с Web Services Enhancements 3.0 для клиентов Microsoft .NET (WSE) при настройке службы WCF для использования версии спецификации WS-Addressing от августа 2004 г.</span><span class="sxs-lookup"><span data-stu-id="d4f70-103">Windows Communication Foundation (WCF) services are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) clients when WCF services are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="d4f70-104">Включение службы WCF для взаимодействия с клиентами WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="d4f70-104">To enable a WCF service to interoperate with WSE 3.0 clients</span></span>  
  
1. <span data-ttu-id="d4f70-105">Определите пользовательскую привязку для службы WCF.</span><span class="sxs-lookup"><span data-stu-id="d4f70-105">Define a custom binding for the WCF service.</span></span>  
  
     <span data-ttu-id="d4f70-106">Чтобы указать, что для кодирования сообщений используется версия спецификации WS-Addressing от августа 2004 г., необходимо создать пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="d4f70-106">To specify that the August 2004 version of the WS-Addressing specification is used for message encoding, a custom binding must be created.</span></span>  
  
    1. <span data-ttu-id="d4f70-107">Добавить учетную запись ребенка [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) для [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) файла конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="d4f70-107">Add a child [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) to the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) of the service's configuration file.</span></span>  
  
    2. <span data-ttu-id="d4f70-108">Укажите имя для привязки, добавив [ \<привязки >](../../../../docs/framework/misc/binding.md) для [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) и параметр `name` атрибута.</span><span class="sxs-lookup"><span data-stu-id="d4f70-108">Specify a name for the binding, by adding a [\<binding>](../../../../docs/framework/misc/binding.md) to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) and setting the `name` attribute.</span></span>  
  
    3. <span data-ttu-id="d4f70-109">Укажите режим проверки подлинности и версию спецификации WS-Security, которые используются для защиты сообщений, совместимых с WSE 3.0, добавив дочерний элемент [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) для [ \<привязки >](../../../../docs/framework/misc/binding.md).</span><span class="sxs-lookup"><span data-stu-id="d4f70-109">Specify an authentication mode and the version of the WS-Security specifications that are used to secure messages that are compatible with WSE 3.0, by adding a child [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) to the [\<binding>](../../../../docs/framework/misc/binding.md).</span></span>  
  
         <span data-ttu-id="d4f70-110">Чтобы задать режим проверки подлинности, задайте `authenicationMode` атрибут [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="d4f70-110">To set the authentication mode, set the `authenicationMode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="d4f70-111">Режим проверки подлинности примерно соответствует готовому к использованию утверждению безопасности в WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="d4f70-111">An authentication mode is roughly equivalent to a turnkey security assertion in WSE 3.0.</span></span> <span data-ttu-id="d4f70-112">В следующей таблице сопоставлены режимы проверки подлинности в WCF для утверждения готовое к использованию безопасности в WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="d4f70-112">The following table maps authentication modes in WCF to turnkey security assertions in WSE 3.0.</span></span>  
  
        |<span data-ttu-id="d4f70-113">Режим проверки подлинности WCF</span><span class="sxs-lookup"><span data-stu-id="d4f70-113">WCF Authentication Mode</span></span>|<span data-ttu-id="d4f70-114">Готовое к использованию утверждение безопасности WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="d4f70-114">WSE 3.0 turnkey security assertion</span></span>|  
        |-----------------------------|----------------------------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|  
  
         <span data-ttu-id="d4f70-115">\* Одно из основных различий между `mutualCertificate10Security` и `mutualCertificate11Security` утверждения готовое к использованию безопасности — это версия спецификации WS-Security, используемой в WSE для защиты сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="d4f70-115">\* One of the primary differences between the `mutualCertificate10Security` and `mutualCertificate11Security` turnkey security assertions is the version of the WS-Security specification that WSE uses to secure the SOAP messages.</span></span> <span data-ttu-id="d4f70-116">Для `mutualCertificate10Security` используется версия WS-Security 1.0, а для `mutualCertificate11Security` - версия WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="d4f70-116">For `mutualCertificate10Security`, WS-Security 1.0 is used, whereas WS-Security 1.1 is used for `mutualCertificate11Security`.</span></span> <span data-ttu-id="d4f70-117">Для WCF, версия спецификации WS-Security, указанная в `messageSecurityVersion` атрибут [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="d4f70-117">For WCF, the version of the WS-Security specification is specified in the `messageSecurityVersion` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>  
  
         <span data-ttu-id="d4f70-118">Чтобы определить версию спецификации WS-Security, который используется для защиты сообщений SOAP, задать `messageSecurityVersion` атрибут [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="d4f70-118">To set the version of the WS-Security specification that is used to secure SOAP messages, set the `messageSecurityVersion` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="d4f70-119">Для взаимодействия с WSE 3.0 установите для атрибута `messageSecurityVersion` значение <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4f70-119">To interoperate with WSE 3.0, set the value of the `messageSecurityVersion` attribute to <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span></span>  
  
    4. <span data-ttu-id="d4f70-120">Укажите, что спецификации WS-Addressing версии августа 2004 г., используется платформой WCF, добавив [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) и задайте `messageVersion` значение <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4f70-120">Specify that the August 2004 version of the WS-Addressing specification is used by WCF by adding a [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) and set the `messageVersion` to its value to <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="d4f70-121">При использовании протокола SOAP 1.2 задайте для атрибута `messageVersion` значение <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4f70-121">When you are using SOAP 1.2, set the `messageVersion` attribute to <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span></span>  
  
2. <span data-ttu-id="d4f70-122">Укажите, что служба использует пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="d4f70-122">Specify that the service uses the custom binding.</span></span>  
  
    1. <span data-ttu-id="d4f70-123">Задайте `binding` атрибут [ \<конечной точки >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) элемент `customBinding`.</span><span class="sxs-lookup"><span data-stu-id="d4f70-123">Set the `binding` attribute of the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element to `customBinding`.</span></span>  
  
    2. <span data-ttu-id="d4f70-124">Задайте `bindingConfiguration` атрибут [ \<конечной точки >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) элемента к значению, указанному в `name` атрибут [ \<привязки >](../../../../docs/framework/misc/binding.md) для настраиваемого привязка.</span><span class="sxs-lookup"><span data-stu-id="d4f70-124">Set the `bindingConfiguration` attribute of the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element to the value specified in the `name` attribute of the [\<binding>](../../../../docs/framework/misc/binding.md) for the custom binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4f70-125">Пример</span><span class="sxs-lookup"><span data-stu-id="d4f70-125">Example</span></span>  
 <span data-ttu-id="d4f70-126">Следующий пример кода задает, что служба `Service.HelloWorldService` использует для взаимодействия с клиентами WSE 3.0 пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="d4f70-126">The following code example specifies that the `Service.HelloWorldService` uses a custom binding to interoperate with WSE 3.0 clients.</span></span> <span data-ttu-id="d4f70-127">Пользовательская привязка задает, что для кодирования пересылаемых сообщений используется версия спецификация WS-Addressing от августа 2004 г. и набор спецификаций WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="d4f70-127">The custom binding specifies that the August 2004 version of the WS-Addressing and the WS-Security 1.1 set of specifications are used to encode the exchanged messages.</span></span> <span data-ttu-id="d4f70-128">Защита сообщений обеспечивается с помощью режима проверки подлинности <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>.</span><span class="sxs-lookup"><span data-stu-id="d4f70-128">The messages are secured using the <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> authentication mode.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d4f70-129">См. также</span><span class="sxs-lookup"><span data-stu-id="d4f70-129">See also</span></span>

- [<span data-ttu-id="d4f70-130">Практическое руководство. Настройка привязки, предоставляемой системой</span><span class="sxs-lookup"><span data-stu-id="d4f70-130">How to: Customize a System-Provided Binding</span></span>](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)
