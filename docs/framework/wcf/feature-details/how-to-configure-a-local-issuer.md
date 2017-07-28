---
title: "Как настраивать локальный издатель | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "федерация"
  - "WCF, федерация"
ms.assetid: 15263371-514e-4ea6-90fb-14b4939154cd
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Как настраивать локальный издатель
В этом разделе описано, как настроить клиент на использование локального издателя для выданных маркеров.  
  
 Часто при взаимодействии клиента с федеративной службой служба указывает адрес службы маркеров безопасности, выдающей маркеры, которые клиент будет использовать, чтобы федеративная служба могла проверить его подлинность.В некоторых случаях клиент можно настроить на использование *локального издателя*.  
  
 В [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] локальный издатель используется тогда, когда адрес издателя федеративной привязки имеет вид http:\/\/schemas.microsoft.com\/2005\/12\/ServiceModel\/Addressing\/Anonymous или `null`.В этих случаях необходимо настроить объект <xref:System.ServiceModel.Description.ClientCredentials> с использованием адреса локального издателя и привязки, с помощью которой будет осуществляться взаимодействие с этим издателем.  
  
> [!NOTE]
>  Если свойство <xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A> класса `ClientCredentials` имеет значение `true`, адрес локального издателя не задан, а адрес издателя, задаваемый элементом [\<wsFederationHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) или другой федеративной привязкой, имеет вид http:\/\/schemas.xmlsoap.org\/ws\/2005\/05\/identity\/issuer\/self, http:\/\/schemas.microsoft.com\/2005\/12\/ServiceModel\/Addressing\/Anonymous или `null`, используется издатель [!INCLUDE[infocard](../../../../includes/infocard-md.md)] Windows.  
  
### Настройка локального издателя в коде  
  
1.  Создайте переменную типа <xref:System.ServiceModel.Security.IssuedTokenClientCredential>.  
  
2.  Присвойте переменной экземпляр, возвращаемый свойством <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> класса `ClientCredentials`.Этот экземпляр возвращается свойством <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> клиента \(унаследованным от <xref:System.ServiceModel.ClientBase%601>\) или свойством <xref:System.ServiceModel.ChannelFactory.Credentials%2A> класса <xref:System.ServiceModel.ChannelFactory>:  
  
     [!code-csharp[c_CreateSTS#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#9)]
     [!code-vb[c_CreateSTS#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#9)]  
  
3.  Присвойте свойству <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A> новый экземпляр класса <xref:System.ServiceModel.EndpointAddress>, указав в качестве аргумента конструктора адрес локального издателя.  
  
     [!code-csharp[c_CreateSTS#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#10)]
     [!code-vb[c_CreateSTS#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#10)]  
  
     Либо создайте новый экземпляр <xref:System.Uri> в качестве аргумента конструктора.  
  
     [!code-csharp[c_CreateSTS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#11)]
     [!code-vb[c_CreateSTS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#11)]  
  
     Параметр`addressHeaders` представляет собой массив экземпляров <xref:System.ServiceModel.Channels.AddressHeader>, как показано в следующем примере.  
  
     [!code-csharp[c_CreateSTS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#12)]
     [!code-vb[c_CreateSTS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#12)]  
  
4.  С помощью свойства <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A> установите привязку для локального издателя.  
  
     [!code-csharp[c_CreateSTS#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#13)]
     [!code-vb[c_CreateSTS#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#13)]  
  
5.  Необязательно.Добавьте настроенные поведения конечных точек для локального издателя, добавив эти поведения в коллекцию, возвращаемую свойством <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A>.  
  
     [!code-csharp[c_CreateSTS#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#14)]
     [!code-vb[c_CreateSTS#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#14)]  
  
### Настройка локального издателя с помощью файла конфигурации  
  
1.  Создайте элемент [\<localIssuer\>](../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md), являющийся дочерним для элемента [\<issuedToken\>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md), который в свою очередь является дочерним для элемента [\<clientCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) в поведении конечной точки.  
  
2.  Задайте в качестве атрибута `address` адрес локального издателя, которые будет принимать запросы маркеров.  
  
3.  Задайте в качестве атрибутов `binding` и `bindingConfiguration` значения, указывающие на соответствующую привязку, которую следует использовать при взаимодействии с конечной точкой локального издателя.  
  
4.  Необязательно.Задайте элемент [\<удостоверение\>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md), являющийся дочерним для элемента \<`localIssuer`\>, и укажите сведения об удостоверении локального издателя.  
  
5.  Необязательно.Задайте элемент [\<верхние колонтитулы\>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md), являющийся дочерним для элемента \<`localIssuer`\>, и укажите дополнительные заголовки, необходимые для правильного обнаружения локального издателя.  
  
## Безопасность платформы .NET Framework  
 Обратите внимание, что если для данной привязки указаны адрес издателя и привязка, локальный издатель не применяется в конечных точках, использующих эту привязку.Клиенты, которые предполагают всегда использовать локальный издатель, должны убедиться, что они не используют такую привязку или что привязка изменена таким образом, что адрес издателя имеет значение `null`.  
  
## См. также  
 [Как настраивать учетные данные службы федерации](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)   
 [Как создавать федеративный клиент](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)   
 [Практическое руководство. Создание WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)