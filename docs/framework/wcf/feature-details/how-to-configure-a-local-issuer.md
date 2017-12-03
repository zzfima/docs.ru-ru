---
title: "Практическое руководство. Настройка локального издателя"
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
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 15263371-514e-4ea6-90fb-14b4939154cd
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 90edf0735d890e0abc1560de5a7f523ee2faa7c8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-configure-a-local-issuer"></a>Практическое руководство. Настройка локального издателя
В этом разделе описано, как настроить клиент на использование локального издателя для выданных маркеров.  
  
 Часто при взаимодействии клиента с федеративной службой служба указывает адрес службы маркеров безопасности, выдающей маркеры, которые клиент будет использовать, чтобы федеративная служба могла проверить его подлинность. В некоторых случаях клиент можно настроить для использования *локального издателя*.  
  
 В [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] локальный издатель используется тогда, когда адрес издателя федеративной привязки имеет вид http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous или `null`. В этих случаях необходимо настроить объект <xref:System.ServiceModel.Description.ClientCredentials> с использованием адреса локального издателя и привязки, с помощью которой будет осуществляться взаимодействие с этим издателем.  
  
> [!NOTE]
>  Если <xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A> свойство `ClientCredentials` имеет значение `true`, не указан адрес локального издателя, а указывает адрес издателя [ \<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) или другие Федеративная привязка является http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self, http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous, или `null`, затем Windows [!INCLUDE[infocard](../../../../includes/infocard-md.md)] используется издателя.  
  
### <a name="to-configure-the-local-issuer-in-code"></a>Настройка локального издателя в коде  
  
1.  Создайте переменную типа <xref:System.ServiceModel.Security.IssuedTokenClientCredential>.  
  
2.  Присвойте переменной экземпляр, возвращаемый свойством <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> класса `ClientCredentials`. Этот экземпляр возвращается свойством <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> клиента (унаследованным от <xref:System.ServiceModel.ClientBase%601>) или свойством <xref:System.ServiceModel.ChannelFactory.Credentials%2A> класса <xref:System.ServiceModel.ChannelFactory>:  
  
     [!code-csharp[c_CreateSTS#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#9)]
     [!code-vb[c_CreateSTS#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#9)]  
  
3.  Присвойте свойству <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A> новый экземпляр класса <xref:System.ServiceModel.EndpointAddress>, указав в качестве аргумента конструктора адрес локального издателя.  
  
     [!code-csharp[c_CreateSTS#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#10)]
     [!code-vb[c_CreateSTS#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#10)]  
  
     Либо создайте новый экземпляр <xref:System.Uri> в качестве аргумента конструктора.  
  
     [!code-csharp[c_CreateSTS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#11)]
     [!code-vb[c_CreateSTS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#11)]  
  
     `addressHeaders` Параметр представляет собой массив <xref:System.ServiceModel.Channels.AddressHeader> экземпляров, как показано.  
  
     [!code-csharp[c_CreateSTS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#12)]
     [!code-vb[c_CreateSTS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#12)]  
  
4.  Установите привязку для локального издателя с помощью <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A> свойство.  
  
     [!code-csharp[c_CreateSTS#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#13)]
     [!code-vb[c_CreateSTS#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#13)]  
  
5.  Необязательно. Добавьте настроенные поведения конечных точек для локального издателя, добавив эти поведения в коллекцию, возвращаемую свойством <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A>.  
  
     [!code-csharp[c_CreateSTS#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#14)]
     [!code-vb[c_CreateSTS#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#14)]  
  
### <a name="to-configure-the-local-issuer-in-configuration"></a>Настройка локального издателя с помощью файла конфигурации  
  
1.  Создание [ \<localIssuer >](../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md) элемента в качестве дочернего элемента [ \<issuedToken >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) элемент, который сам является потомком [ \<clientCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) элемента поведения конечной точки.  
  
2.  Задайте в качестве атрибута `address` адрес локального издателя, которые будет принимать запросы маркеров.  
  
3.  Задайте в качестве атрибутов `binding` и `bindingConfiguration` значения, указывающие на соответствующую привязку, которую следует использовать при взаимодействии с конечной точкой локального издателя.  
  
4.  Необязательно. Задать [ \<удостоверение >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) элемента в качестве дочернего элемента <`localIssuer`> элемент и укажите сведения об удостоверении для локального издателя.  
  
5.  Необязательно. Задать [ \<заголовки >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) элемента в качестве дочернего элемента <`localIssuer`> элемент и указать дополнительные заголовки, которые необходимы для правильного обращения к локальному издателю.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Обратите внимание, что если для данной привязки указаны адрес издателя и привязка, локальный издатель не применяется в конечных точках, использующих эту привязку. Клиенты, которые предполагают всегда использовать локальный издатель, должны убедиться, что они не используют такую привязку или что привязка изменена таким образом, что адрес издателя имеет значение `null`.  
  
## <a name="see-also"></a>См. также  
 [Как: настройте учетные данные для службы федерации](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [Как: создание федеративного клиента](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [Как: создание WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
