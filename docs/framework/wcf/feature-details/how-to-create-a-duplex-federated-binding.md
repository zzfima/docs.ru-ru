---
title: Практическое руководство. Создание дуплексной федеративной привязки
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 71c970fa45d7d4ccd55fceddb2360d0aa0a768f8
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972061"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="3cb01-102">Практическое руководство. Создание дуплексной федеративной привязки</span><span class="sxs-lookup"><span data-stu-id="3cb01-102">How to: Create a Duplex Federated Binding</span></span>

<span data-ttu-id="3cb01-103">Привязка <xref:System.ServiceModel.WSFederationHttpBinding> поддерживает только датаграмму и контракты обмена сообщениями «запрос-ответ».</span><span class="sxs-lookup"><span data-stu-id="3cb01-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="3cb01-104">Чтобы использовать контакт дуплексного обмена сообщениями, необходимо создать пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="3cb01-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="3cb01-105">В процедурах ниже показана методика выполнения этой операции в конфигурации с использованием режима безопасности сообщений для транспортов HTTP и TCP и с использованием смешанного режима безопасности для транспорта TCP.</span><span class="sxs-lookup"><span data-stu-id="3cb01-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="3cb01-106">Образец кода, в котором показаны все 3 привязки, представлен в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="3cb01-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>

<span data-ttu-id="3cb01-107">Также можно создать привязку в коде.</span><span class="sxs-lookup"><span data-stu-id="3cb01-107">You can also create the binding in code.</span></span> <span data-ttu-id="3cb01-108">Описание создаваемого стека элементов привязки см. в разделе [как Создайте пользовательскую привязку с помощью](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)SecurityBindingElement.</span><span class="sxs-lookup"><span data-stu-id="3cb01-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="3cb01-109">Создание дуплексной федеративной пользовательской привязки с использованием HTTP</span><span class="sxs-lookup"><span data-stu-id="3cb01-109">To create a duplex federated custom binding with HTTP</span></span>

1. <span data-ttu-id="3cb01-110">В узле привязки > [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) файла конфигурации создайте элемент CustomBinding >. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)</span><span class="sxs-lookup"><span data-stu-id="3cb01-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="3cb01-111">`name` `FederationDuplexHttpMessageSecurityBinding` [ В\<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элементе CustomBinding > Создайте элемент [> привязкисатрибутом,длякоторогозаданозначение.\<](../../../../docs/framework/misc/binding.md)</span><span class="sxs-lookup"><span data-stu-id="3cb01-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="3cb01-112">`authenticationMode` `SecureConversation` [ В\<](../../../../docs/framework/misc/binding.md) элементе Binding > Создайте элемент [> безопасностисатрибутом,длякоторогозаданозначение.\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="3cb01-112">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="3cb01-113">`IssuedTokenForSslNegotiated`В элементе >`authenticationMode` безопасностисоздайте`IssuedTokenForCertificate` элемент [> секуреконверсатионбутстрап,атрибуткоторогоимеетзначениеили.\<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="3cb01-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="3cb01-114">После элемента [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) Security > Создайте пустой элемент > compositeDuplex. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="3cb01-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>

6. <span data-ttu-id="3cb01-115">После элемента [> compositeDuplexсоздайтепустойэлемент>OneWay.\<](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)</span><span class="sxs-lookup"><span data-stu-id="3cb01-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>

7. <span data-ttu-id="3cb01-116">После элемента [> OneWayсоздайтепустойэлемент>хттптранспорт.\<](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)</span><span class="sxs-lookup"><span data-stu-id="3cb01-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="3cb01-117">Создание дуплексной федеративной пользовательской привязки с использованием режима безопасности сообщения TCP</span><span class="sxs-lookup"><span data-stu-id="3cb01-117">To create a duplex federated custom binding with TCP message security mode</span></span>

1. <span data-ttu-id="3cb01-118">В узле привязки > [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) файла конфигурации создайте элемент CustomBinding >. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)</span><span class="sxs-lookup"><span data-stu-id="3cb01-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="3cb01-119">`name` `FederationDuplexTcpMessageSecurityBinding` [ В\<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элементе CustomBinding > Создайте элемент [> привязкисатрибутом,длякоторогозаданозначение.\<](../../../../docs/framework/misc/binding.md)</span><span class="sxs-lookup"><span data-stu-id="3cb01-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="3cb01-120">`authenticationMode` `SecureConversation` [ В\<](../../../../docs/framework/misc/binding.md) элементе Binding > Создайте элемент [> безопасностисатрибутом,длякоторогозаданозначение.\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="3cb01-120">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="3cb01-121">`IssuedTokenForSslNegotiated`В элементе >`authenticationMode` безопасностисоздайте`IssuedTokenForCertificate` элемент [> секуреконверсатионбутстрап,атрибуткоторогоимеетзначениеили.\<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="3cb01-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="3cb01-122">После элемента [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) Security > Создайте пустой элемент > tcpTransport платформы. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="3cb01-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="3cb01-123">Создание дуплексной федеративной пользовательской привязки с использованием смешанного режима безопасности TCP</span><span class="sxs-lookup"><span data-stu-id="3cb01-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>

1. <span data-ttu-id="3cb01-124">В узле привязки > [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) файла конфигурации создайте элемент CustomBinding >. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)</span><span class="sxs-lookup"><span data-stu-id="3cb01-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="3cb01-125">`name` `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding` [ В\<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) элементе CustomBinding > Создайте элемент [> привязкисатрибутом,длякоторогозаданозначение.\<](../../../../docs/framework/misc/binding.md)</span><span class="sxs-lookup"><span data-stu-id="3cb01-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>

3. <span data-ttu-id="3cb01-126">`authenticationMode` `SecureConversation` [ В\<](../../../../docs/framework/misc/binding.md) элементе Binding > Создайте элемент [> безопасностисатрибутом,длякоторогозаданозначение.\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="3cb01-126">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="3cb01-127">`IssuedTokenForSslNegotiated`В элементе >`authenticationMode` безопасностисоздайте`IssuedTokenForCertificate` элемент [> секуреконверсатионбутстрап,атрибуткоторогоимеетзначениеили.\<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="3cb01-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="3cb01-128">После элемента [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) Security > Создайте пустой элемент > раздел sslstreamsecurity. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="3cb01-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>

6. <span data-ttu-id="3cb01-129">После элемента [> разделsslstreamsecurityсоздайтепустойэлемент>tcpTransportплатформы.\<](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md)</span><span class="sxs-lookup"><span data-stu-id="3cb01-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="code-sample"></a><span data-ttu-id="3cb01-130">Образец кода</span><span class="sxs-lookup"><span data-stu-id="3cb01-130">Code Sample</span></span>

### <a name="sample-with-3-bindings"></a><span data-ttu-id="3cb01-131">Образец с 3 привязками</span><span class="sxs-lookup"><span data-stu-id="3cb01-131">Sample with 3 Bindings</span></span>

1. <span data-ttu-id="3cb01-132">Вставьте следующий код в свой файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3cb01-132">Insert the following code into your configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="3cb01-133">Пример</span><span class="sxs-lookup"><span data-stu-id="3cb01-133">Example</span></span>

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
