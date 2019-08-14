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
# <a name="how-to-configure-a-local-issuer"></a>Практическое руководство. Настройка локального издателя

В этом разделе описано, как настроить клиент на использование локального издателя для выданных маркеров.

Часто при взаимодействии клиента с федеративной службой служба указывает адрес службы маркеров безопасности, выдающей маркеры, которые клиент будет использовать, чтобы федеративная служба могла проверить его подлинность. В некоторых случаях клиент может быть настроен на использование *локального издателя*.

Windows Communication Foundation (WCF) использует локального издателя в случаях, когда адрес издателя Федеративной привязки — `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` или. `null` В этих случаях необходимо настроить объект <xref:System.ServiceModel.Description.ClientCredentials> с использованием адреса локального издателя и привязки, с помощью которой будет осуществляться взаимодействие с этим издателем.

> [!NOTE]
> `true`Если свойство класса`ClientCredentials` имеет значение, адрес локального издателя не указывается, а адрес издателя, указанный в [ \<> WSFederationHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) или другой федеративной привязкой, — <xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A> `http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self` ,`http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous`или имеет значение `null`, используется издатель Windows CardSpace.

## <a name="to-configure-the-local-issuer-in-code"></a>Настройка локального издателя в коде

1. Создайте переменную типа <xref:System.ServiceModel.Security.IssuedTokenClientCredential>.

2. Присвойте переменной экземпляр, возвращаемый свойством <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> класса `ClientCredentials`. Этот экземпляр возвращается свойством <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> клиента (унаследованным от <xref:System.ServiceModel.ClientBase%601>) или свойством <xref:System.ServiceModel.ChannelFactory.Credentials%2A> класса <xref:System.ServiceModel.ChannelFactory>:

     [!code-csharp[c_CreateSTS#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#9)]
     [!code-vb[c_CreateSTS#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#9)]

3. Присвойте свойству <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A> новый экземпляр класса <xref:System.ServiceModel.EndpointAddress>, указав в качестве аргумента конструктора адрес локального издателя.

     [!code-csharp[c_CreateSTS#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#10)]
     [!code-vb[c_CreateSTS#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#10)]

     Либо создайте новый экземпляр <xref:System.Uri> в качестве аргумента конструктора.

     [!code-csharp[c_CreateSTS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#11)]
     [!code-vb[c_CreateSTS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#11)]

     Параметр является массивом экземпляров, как показано ниже. <xref:System.ServiceModel.Channels.AddressHeader> `addressHeaders`

     [!code-csharp[c_CreateSTS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#12)]
     [!code-vb[c_CreateSTS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#12)]

4. Установите привязку для локального издателя, <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A> используя свойство.

     [!code-csharp[c_CreateSTS#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#13)]
     [!code-vb[c_CreateSTS#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#13)]

5. Необязательный параметр. Добавьте настроенные поведения конечных точек для локального издателя, добавив эти поведения в коллекцию, возвращаемую свойством <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A>.

     [!code-csharp[c_CreateSTS#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#14)]
     [!code-vb[c_CreateSTS#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#14)]

## <a name="to-configure-the-local-issuer-in-configuration"></a>Настройка локального издателя с помощью файла конфигурации

1. Создайте элемент [ >локалиссуервкачестведочернегоэлементаissuedToken>,которыйсамявляетсядочернимпоотношениюкэлементу>ClientCredentialsвповеденииконечнойточки.\<](../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)

2. Задайте в качестве атрибута `address` адрес локального издателя, которые будет принимать запросы маркеров.

3. Задайте в качестве атрибутов `binding` и `bindingConfiguration` значения, указывающие на соответствующую привязку, которую следует использовать при взаимодействии с конечной точкой локального издателя.

4. Необязательный параметр. Задайте элемент`localIssuer`Identity > как дочерний элемент < > и укажите сведения об удостоверении для локального издателя. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)

5. Необязательный параметр. Установите элемент`localIssuer`Headers > в качестве дочернего элемента < > и укажите дополнительные заголовки, необходимые для правильной адресации локального издателя. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)

## <a name="net-framework-security"></a>Безопасность платформы .NET Framework

Обратите внимание, что если для данной привязки указаны адрес издателя и привязка, локальный издатель не применяется в конечных точках, использующих эту привязку. Клиенты, которые предполагают всегда использовать локальный издатель, должны убедиться, что они не используют такую привязку или что привязка изменена таким образом, что адрес издателя имеет значение `null`.

## <a name="see-also"></a>См. также

- [Практическое руководство. Настройка учетных данных на служба федерации](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [Практическое руководство. Создание федеративного клиента](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [Практическое руководство. Создание WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
