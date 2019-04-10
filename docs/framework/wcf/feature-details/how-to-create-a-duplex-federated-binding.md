---
title: Практическое руководство. Создание дуплексной федеративной привязки
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 510faa0b1d791b1d164c55e9fa32daafa559d56c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59346240"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="c072a-102">Практическое руководство. Создание дуплексной федеративной привязки</span><span class="sxs-lookup"><span data-stu-id="c072a-102">How to: Create a Duplex Federated Binding</span></span>
<xref:System.ServiceModel.WSFederationHttpBinding> <span data-ttu-id="c072a-103">поддерживает только датаграмму и запрос/ответ контракты обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c072a-103">only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="c072a-104">Чтобы использовать контакт дуплексного обмена сообщениями, необходимо создать пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="c072a-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="c072a-105">В процедурах ниже показана методика выполнения этой операции в конфигурации с использованием режима безопасности сообщений для транспортов HTTP и TCP и с использованием смешанного режима безопасности для транспорта TCP.</span><span class="sxs-lookup"><span data-stu-id="c072a-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="c072a-106">Образец кода, в котором показаны все 3 привязки, представлен в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="c072a-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>  
  
 <span data-ttu-id="c072a-107">Также можно создать привязку в коде.</span><span class="sxs-lookup"><span data-stu-id="c072a-107">You can also create the binding in code.</span></span> <span data-ttu-id="c072a-108">Описание создания стека элементов привязки, см. в разделе [как: Создание пользовательской привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="c072a-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="c072a-109">Создание дуплексной федеративной пользовательской привязки с использованием HTTP</span><span class="sxs-lookup"><span data-stu-id="c072a-109">To create a duplex federated custom binding with HTTP</span></span>  
  
1. <span data-ttu-id="c072a-110">В [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) узел файла конфигурации, создавать [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="c072a-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>  
  
2. <span data-ttu-id="c072a-111">Внутри [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элемент, создание [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент с `name` атрибут `FederationDuplexHttpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="c072a-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>  
  
3. <span data-ttu-id="c072a-112">Внутри [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент, создание [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент с `authenticationMode` атрибут `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="c072a-112">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4. <span data-ttu-id="c072a-113">Внутри [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент, создание [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) элемент с `authenticationMode` атрибут `IssuedTokenForCertificate` или `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="c072a-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5. <span data-ttu-id="c072a-114">Следуя [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент, создать пустой [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="c072a-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>  
  
6. <span data-ttu-id="c072a-115">Следуя [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) элемент, создать пустой [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="c072a-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>  
  
7. <span data-ttu-id="c072a-116">Следуя [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) элемент, создать пустой [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="c072a-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="c072a-117">Создание дуплексной федеративной пользовательской привязки с использованием режима безопасности сообщения TCP</span><span class="sxs-lookup"><span data-stu-id="c072a-117">To create a duplex federated custom binding with TCP message security mode</span></span>  
  
1. <span data-ttu-id="c072a-118">В [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) узел файла конфигурации, создавать [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="c072a-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2. <span data-ttu-id="c072a-119">Внутри [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элемент, создание [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент с `name` атрибут `FederationDuplexTcpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="c072a-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>  
  
3. <span data-ttu-id="c072a-120">Внутри [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент, создание [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент с `authenticationMode` атрибут `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="c072a-120">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4. <span data-ttu-id="c072a-121">Внутри [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент, создание [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) элемент с `authenticationMode` атрибут `IssuedTokenForCertificate` или `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="c072a-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5. <span data-ttu-id="c072a-122">Следуя [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент, создать пустой [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="c072a-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="c072a-123">Создание дуплексной федеративной пользовательской привязки с использованием смешанного режима безопасности TCP</span><span class="sxs-lookup"><span data-stu-id="c072a-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>  
  
1. <span data-ttu-id="c072a-124">В [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) узел файла конфигурации, создавать [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="c072a-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2. <span data-ttu-id="c072a-125">Внутри [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элемент, создание [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент с `name` атрибут `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span><span class="sxs-lookup"><span data-stu-id="c072a-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>  
  
3. <span data-ttu-id="c072a-126">Внутри [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент, создание [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент с `authenticationMode` атрибут `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="c072a-126">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4. <span data-ttu-id="c072a-127">Внутри [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент, создание [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) элемент с `authenticationMode` атрибут `IssuedTokenForCertificate` или `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="c072a-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5. <span data-ttu-id="c072a-128">Следуя [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент, создать пустой [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="c072a-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>  
  
6. <span data-ttu-id="c072a-129">Следуя [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) элемент, создать пустой [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="c072a-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="c072a-130">Образец кода</span><span class="sxs-lookup"><span data-stu-id="c072a-130">Code Sample</span></span>  
  
#### <a name="sample-with-3-bindings"></a><span data-ttu-id="c072a-131">Образец с 3 привязками</span><span class="sxs-lookup"><span data-stu-id="c072a-131">Sample with 3 Bindings</span></span>  
  
1. <span data-ttu-id="c072a-132">Вставьте следующий код в свой файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c072a-132">Insert the following code into your configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c072a-133">Пример</span><span class="sxs-lookup"><span data-stu-id="c072a-133">Example</span></span>  
  
```xml  
<bindings>  
   <customBinding>  
      <binding name="FederationDuplexHttpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <compositeDuplex />  
          <oneWay />  
          <httpTransport />  
       </binding>  
<!-- duplex over https is not supported -->  
       <binding name="FederationDuplexTcpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <tcpTransport />  
       </binding>              
       <binding name="FederationDuplexTcpTransportSecurityWithMessageCredentialsBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenOverTransport" />  
          </security>  
<!-- requireClientCertificate = true or <windowsStreamSecurity /> can be used, but does not make sense for most scenarios -->  
          <sslStreamSecurity />  
          <tcpTransport />  
       </binding>              
    </customBinding>  
</bindings>  
```
