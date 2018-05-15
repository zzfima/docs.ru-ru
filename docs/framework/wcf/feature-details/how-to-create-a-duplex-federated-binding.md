---
title: Практическое руководство. Создание дуплексной федеративной привязки
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: d736d0119f3e938d81a15d57bb6d97ca2a1990fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="56528-102">Практическое руководство. Создание дуплексной федеративной привязки</span><span class="sxs-lookup"><span data-stu-id="56528-102">How to: Create a Duplex Federated Binding</span></span>
<span data-ttu-id="56528-103">Привязка <xref:System.ServiceModel.WSFederationHttpBinding> поддерживает только датаграмму и контракты обмена сообщениями «запрос-ответ».</span><span class="sxs-lookup"><span data-stu-id="56528-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="56528-104">Чтобы использовать контакт дуплексного обмена сообщениями, необходимо создать пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="56528-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="56528-105">В процедурах ниже показана методика выполнения этой операции в конфигурации с использованием режима безопасности сообщений для транспортов HTTP и TCP и с использованием смешанного режима безопасности для транспорта TCP.</span><span class="sxs-lookup"><span data-stu-id="56528-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="56528-106">Образец кода, в котором показаны все 3 привязки, представлен в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="56528-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>  
  
 <span data-ttu-id="56528-107">Также можно создать привязку в коде.</span><span class="sxs-lookup"><span data-stu-id="56528-107">You can also create the binding in code.</span></span> <span data-ttu-id="56528-108">Описание стек элементов привязки, чтобы создать см. [как: Создание привязки настраиваемый с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="56528-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="56528-109">Создание дуплексной федеративной пользовательской привязки с использованием HTTP</span><span class="sxs-lookup"><span data-stu-id="56528-109">To create a duplex federated custom binding with HTTP</span></span>  
  
1.  <span data-ttu-id="56528-110">В [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) узел файла конфигурации, создавать [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="56528-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>  
  
2.  <span data-ttu-id="56528-111">Внутри [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элемент, создайте [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент с `name` атрибуту присвоено значение `FederationDuplexHttpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="56528-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>  
  
3.  <span data-ttu-id="56528-112">Внутри [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент, создайте [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент с `authenticationMode` атрибуту присвоено значение `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="56528-112">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4.  <span data-ttu-id="56528-113">Внутри [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент, создайте [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) элемент с `authenticationMode` атрибут `IssuedTokenForCertificate` или `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="56528-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5.  <span data-ttu-id="56528-114">Следующая [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент, создать пустой [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="56528-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>  
  
6.  <span data-ttu-id="56528-115">Следующая [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) элемент, создать пустой [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="56528-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>  
  
7.  <span data-ttu-id="56528-116">Следующая [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) элемент, создать пустой [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="56528-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="56528-117">Создание дуплексной федеративной пользовательской привязки с использованием режима безопасности сообщения TCP</span><span class="sxs-lookup"><span data-stu-id="56528-117">To create a duplex federated custom binding with TCP message security mode</span></span>  
  
1.  <span data-ttu-id="56528-118">В [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) узел файла конфигурации, создавать [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="56528-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2.  <span data-ttu-id="56528-119">Внутри [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элемент, создайте [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент с `name` атрибуту присвоено значение `FederationDuplexTcpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="56528-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>  
  
3.  <span data-ttu-id="56528-120">Внутри [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент, создайте [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент с `authenticationMode` атрибуту присвоено значение `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="56528-120">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4.  <span data-ttu-id="56528-121">Внутри [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент, создайте [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) элемент с `authenticationMode` атрибут `IssuedTokenForCertificate` или `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="56528-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5.  <span data-ttu-id="56528-122">Следующая [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент, создать пустой [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="56528-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="56528-123">Создание дуплексной федеративной пользовательской привязки с использованием смешанного режима безопасности TCP</span><span class="sxs-lookup"><span data-stu-id="56528-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>  
  
1.  <span data-ttu-id="56528-124">В [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) узел файла конфигурации, создавать [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="56528-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2.  <span data-ttu-id="56528-125">Внутри [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элемент, создайте [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент с `name` атрибуту присвоено значение `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span><span class="sxs-lookup"><span data-stu-id="56528-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>  
  
3.  <span data-ttu-id="56528-126">Внутри [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент, создайте [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент с `authenticationMode` атрибуту присвоено значение `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="56528-126">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4.  <span data-ttu-id="56528-127">Внутри [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент, создайте [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) элемент с `authenticationMode` атрибут `IssuedTokenForCertificate` или `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="56528-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5.  <span data-ttu-id="56528-128">После [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) элемент, создать пустой [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="56528-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>  
  
6.  <span data-ttu-id="56528-129">Следующая [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) элемент, создать пустой [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="56528-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="56528-130">Образец кода</span><span class="sxs-lookup"><span data-stu-id="56528-130">Code Sample</span></span>  
  
#### <a name="sample-with-3-bindings"></a><span data-ttu-id="56528-131">Образец с 3 привязками</span><span class="sxs-lookup"><span data-stu-id="56528-131">Sample with 3 Bindings</span></span>  
  
1.  <span data-ttu-id="56528-132">Вставьте следующий код в свой файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="56528-132">Insert the following code into your configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56528-133">Пример</span><span class="sxs-lookup"><span data-stu-id="56528-133">Example</span></span>  
  
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
