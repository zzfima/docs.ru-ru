---
title: Практическое руководство. Настройка локального издателя
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 15263371-514e-4ea6-90fb-14b4939154cd
ms.openlocfilehash: 0028a0522447588ee0fb183b5b2f93d334a7b2b2
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972069"
---
# <a name="how-to-configure-a-local-issuer"></a><span data-ttu-id="be37b-102">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="be37b-102">How to: Configure a Local Issuer</span></span>

<span data-ttu-id="be37b-103">В этом разделе описано, как настроить клиент на использование локального издателя для выданных маркеров.</span><span class="sxs-lookup"><span data-stu-id="be37b-103">This topic describes how to configure a client to use a local issuer for issued tokens.</span></span>

<span data-ttu-id="be37b-104">Часто при взаимодействии клиента с федеративной службой служба указывает адрес службы маркеров безопасности, выдающей маркеры, которые клиент будет использовать, чтобы федеративная служба могла проверить его подлинность.</span><span class="sxs-lookup"><span data-stu-id="be37b-104">Often, when a client communicates with a federated service, the service specifies the address of the security token service that is expected to issue the token the client will use to authenticate itself to the federated service.</span></span> <span data-ttu-id="be37b-105">В некоторых случаях клиент может быть настроен на использование *локального издателя*.</span><span class="sxs-lookup"><span data-stu-id="be37b-105">In certain situations, the client may be configured to use a *local issuer*.</span></span>

<span data-ttu-id="be37b-106">Windows Communication Foundation (WCF) использует локального издателя в случаях, когда адрес издателя Федеративной привязки — `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` или. `null`</span><span class="sxs-lookup"><span data-stu-id="be37b-106">Windows Communication Foundation (WCF) uses a local issuer in cases where the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`.</span></span> <span data-ttu-id="be37b-107">В этих случаях необходимо настроить объект <xref:System.ServiceModel.Description.ClientCredentials> с использованием адреса локального издателя и привязки, с помощью которой будет осуществляться взаимодействие с этим издателем.</span><span class="sxs-lookup"><span data-stu-id="be37b-107">In such cases, you must configure the <xref:System.ServiceModel.Description.ClientCredentials> with the address of the local issuer and the binding to use to communicate with that issuer.</span></span>

> [!NOTE]
> <span data-ttu-id="be37b-108">`true`Если свойство класса`ClientCredentials` имеет значение, адрес локального издателя не указывается, а адрес издателя, указанный в [ \<> WSFederationHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) или другой федеративной привязкой, — <xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A> `http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self` ,`http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous`или имеет значение `null`, используется издатель Windows CardSpace.</span><span class="sxs-lookup"><span data-stu-id="be37b-108">If the <xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A> property of the `ClientCredentials` class is set to `true`, a local issuer address is not specified, and the issuer address specified by the [\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) or other federated binding is `http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self`, `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous`, or is `null`, then the Windows CardSpace issuer is used.</span></span>

## <a name="to-configure-the-local-issuer-in-code"></a><span data-ttu-id="be37b-109">Настройка локального издателя в коде</span><span class="sxs-lookup"><span data-stu-id="be37b-109">To configure the local issuer in code</span></span>

1. <span data-ttu-id="be37b-110">Создайте переменную типа <xref:System.ServiceModel.Security.IssuedTokenClientCredential>.</span><span class="sxs-lookup"><span data-stu-id="be37b-110">Create a variable of type <xref:System.ServiceModel.Security.IssuedTokenClientCredential></span></span>

2. <span data-ttu-id="be37b-111">Присвойте переменной экземпляр, возвращаемый свойством <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> класса `ClientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="be37b-111">Set the variable to the instance returned from the <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> property of the `ClientCredentials` class.</span></span> <span data-ttu-id="be37b-112">Этот экземпляр возвращается свойством <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> клиента (унаследованным от <xref:System.ServiceModel.ClientBase%601>) или свойством <xref:System.ServiceModel.ChannelFactory.Credentials%2A> класса <xref:System.ServiceModel.ChannelFactory>:</span><span class="sxs-lookup"><span data-stu-id="be37b-112">That instance is returned by the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the client (inherited from <xref:System.ServiceModel.ClientBase%601>) or the <xref:System.ServiceModel.ChannelFactory.Credentials%2A> property of the <xref:System.ServiceModel.ChannelFactory>:</span></span>

     [!code-csharp[c_CreateSTS#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#9)]
     [!code-vb[c_CreateSTS#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#9)]

3. <span data-ttu-id="be37b-113">Присвойте свойству <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A> новый экземпляр класса <xref:System.ServiceModel.EndpointAddress>, указав в качестве аргумента конструктора адрес локального издателя.</span><span class="sxs-lookup"><span data-stu-id="be37b-113">Set the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A> property to a new instance of the <xref:System.ServiceModel.EndpointAddress>, with the address of the local issuer as an argument to the constructor.</span></span>

     [!code-csharp[c_CreateSTS#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#10)]
     [!code-vb[c_CreateSTS#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#10)]

     <span data-ttu-id="be37b-114">Либо создайте новый экземпляр <xref:System.Uri> в качестве аргумента конструктора.</span><span class="sxs-lookup"><span data-stu-id="be37b-114">Alternatively, create a new <xref:System.Uri> instance as an argument to the constructor.</span></span>

     [!code-csharp[c_CreateSTS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#11)]
     [!code-vb[c_CreateSTS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#11)]

     <span data-ttu-id="be37b-115">Параметр является массивом экземпляров, как показано ниже. <xref:System.ServiceModel.Channels.AddressHeader> `addressHeaders`</span><span class="sxs-lookup"><span data-stu-id="be37b-115">The `addressHeaders` parameter is an array of <xref:System.ServiceModel.Channels.AddressHeader> instances, as shown.</span></span>

     [!code-csharp[c_CreateSTS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#12)]
     [!code-vb[c_CreateSTS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#12)]

4. <span data-ttu-id="be37b-116">Установите привязку для локального издателя, <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A> используя свойство.</span><span class="sxs-lookup"><span data-stu-id="be37b-116">Set the binding for the local issuer using the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A> property.</span></span>

     [!code-csharp[c_CreateSTS#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#13)]
     [!code-vb[c_CreateSTS#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#13)]

5. <span data-ttu-id="be37b-117">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="be37b-117">Optional.</span></span> <span data-ttu-id="be37b-118">Добавьте настроенные поведения конечных точек для локального издателя, добавив эти поведения в коллекцию, возвращаемую свойством <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A>.</span><span class="sxs-lookup"><span data-stu-id="be37b-118">Add configured endpoint behaviors for the local issuer by adding such behaviors to the collection returned by the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A> property.</span></span>

     [!code-csharp[c_CreateSTS#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#14)]
     [!code-vb[c_CreateSTS#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#14)]

## <a name="to-configure-the-local-issuer-in-configuration"></a><span data-ttu-id="be37b-119">Настройка локального издателя с помощью файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="be37b-119">To configure the local issuer in configuration</span></span>

1. <span data-ttu-id="be37b-120">Создайте элемент [ >локалиссуервкачестведочернегоэлементаissuedToken>,которыйсамявляетсядочернимпоотношениюкэлементу>ClientCredentialsвповеденииконечнойточки.\<](../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="be37b-120">Create a [\<localIssuer>](../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md) element as a child of the [\<issuedToken>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) element that is itself a child of the [\<clientCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element in an endpoint behavior.</span></span>

2. <span data-ttu-id="be37b-121">Задайте в качестве атрибута `address` адрес локального издателя, которые будет принимать запросы маркеров.</span><span class="sxs-lookup"><span data-stu-id="be37b-121">Set the `address` attribute to the address of the local issuer that will accept token requests.</span></span>

3. <span data-ttu-id="be37b-122">Задайте в качестве атрибутов `binding` и `bindingConfiguration` значения, указывающие на соответствующую привязку, которую следует использовать при взаимодействии с конечной точкой локального издателя.</span><span class="sxs-lookup"><span data-stu-id="be37b-122">Set the `binding` and `bindingConfiguration` attributes to values that reference the appropriate binding to use when communicating with the local issuer endpoint.</span></span>

4. <span data-ttu-id="be37b-123">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="be37b-123">Optional.</span></span> <span data-ttu-id="be37b-124">Задайте элемент`localIssuer`Identity > как дочерний элемент < > и укажите сведения об удостоверении для локального издателя. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)</span><span class="sxs-lookup"><span data-stu-id="be37b-124">Set the [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) element as a child of the <`localIssuer`> element and specify identity information for the local issuer.</span></span>

5. <span data-ttu-id="be37b-125">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="be37b-125">Optional.</span></span> <span data-ttu-id="be37b-126">Установите элемент`localIssuer`Headers > в качестве дочернего элемента < > и укажите дополнительные заголовки, необходимые для правильной адресации локального издателя. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)</span><span class="sxs-lookup"><span data-stu-id="be37b-126">Set the [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) element as a child of the <`localIssuer`> element and specify additional headers that are required in order to correctly address the local issuer.</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="be37b-127">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="be37b-127">.NET Framework Security</span></span>

<span data-ttu-id="be37b-128">Обратите внимание, что если для данной привязки указаны адрес издателя и привязка, локальный издатель не применяется в конечных точках, использующих эту привязку.</span><span class="sxs-lookup"><span data-stu-id="be37b-128">Note that if an issuer address and binding are specified for a given binding, the local issuer is not used for endpoints that use that binding.</span></span> <span data-ttu-id="be37b-129">Клиенты, которые предполагают всегда использовать локальный издатель, должны убедиться, что они не используют такую привязку или что привязка изменена таким образом, что адрес издателя имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="be37b-129">Clients who expect to always use the local issuer should ensure that they do not use such a binding or that they modify the binding so that the issuer address is `null`.</span></span>

## <a name="see-also"></a><span data-ttu-id="be37b-130">См. также</span><span class="sxs-lookup"><span data-stu-id="be37b-130">See also</span></span>

- [<span data-ttu-id="be37b-131">Практическое руководство. Настройка учетных данных на служба федерации</span><span class="sxs-lookup"><span data-stu-id="be37b-131">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="be37b-132">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="be37b-132">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="be37b-133">Практическое руководство. Создание WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="be37b-133">How to: Create a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
