---
title: "Практическое руководство. Создание WSFederationHttpBinding | Microsoft Docs"
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
ms.assetid: e54897d7-aa6c-46ec-a278-b2430c8c2e10
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Практическое руководство. Создание WSFederationHttpBinding
В [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] класс <xref:System.ServiceModel.WSFederationHttpBinding> \([\<wsFederationHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) в конфигурации\) обеспечивает механизм для предоставления доступа к федеративной службе,  т. е. к службе, требующей проверки подлинности клиентов с использованием маркера безопасности, выданного службой маркеров безопасности.  В этом разделе показано, как настраивать привязку <xref:System.ServiceModel.WSFederationHttpBinding> в коде и в конфигурации.  После создания привязки можно настроить конечную точку на использование этой привязки.  
  
 Ниже перечислены основные шаги.  
  
1.  Выберите режим безопасности.  Привязка <xref:System.ServiceModel.WSFederationHttpBinding> поддерживает режим `Message`, обеспечивающий сквозную защиту на уровне сообщений даже при нескольких переходах, а также режим `TransportWithMessageCredential`, который повышает производительность в случаях, когда клиент и служба могут напрямую подключаться друг к другу с помощью протокола HTTPS.  
  
    > [!NOTE]
    >  Кроме того, привязка <xref:System.ServiceModel.WSFederationHttpBinding> поддерживает режим безопасности `None`.  Этот режим небезопасен и поддерживается только в целях отладки.  Если при развертывании конечной точки службы для привязки <xref:System.ServiceModel.WSFederationHttpBinding> задан режим безопасности `None`, для клиента будет создана \(с помощью средства [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)\) привязка <xref:System.ServiceModel.WsHttpBinding> с режимом безопасности `None`.  
  
     В отличие от других предоставляемых системой привязок, при использовании привязки `WSFederationHttpBinding` нет необходимости выбирать тип учетных данных клиента.  Это связано с тем, что типом учетных данных клиента всегда является выданный токен.  Среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] всегда получает токен от указанного издателя и передает его службе для проверки подлинности клиента.  
  
2.  В федеративных клиентах присвойте свойству <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerAddress%2A> URL\-адрес службы маркеров безопасности.  Задайте в качестве свойства <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerBinding%2A> привязку, которая должна использоваться для взаимодействия со службой маркеров безопасности.  
  
3.  Необязательно.  Задайте в качестве свойства <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedTokenType%2A> универсальный код ресурса \(URI\) типа маркера.  В федеративных службах укажите ожидаемый службой тип маркера.  В федеративных клиентах укажите тип маркера, запрашиваемый клиентом у службы маркеров безопасности.  
  
     Если тип маркера не задан, клиенты создают маркеры безопасности запросов \(RST\) WS\-Trust без универсального кода ресурса \(URI\) типа маркера, а служба по умолчанию ожидает проверки подлинности клиента с использованием маркера SAML 1.1.  
  
     Универсальный код ресурса \(URI\) маркера SAML 1.1: "http:\/\/docs.oasis\-open.org\/wss\/oasis\-wss\-saml\-token\-profile\-1.1\#SAMLV1.1".  
  
4.  Необязательно.  В федеративных службах присвойте свойству <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A> URL\-адрес метаданных службы маркеров безопасности.  Конечная точка метаданных позволяет клиентам службы выбрать соответствующую пару «привязка \- конечная точка», если служба настроена на публикацию метаданных.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] публикации метаданных см. в разделе [Публикация метаданных](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
 Можно также задать другие свойства, в том числе тип ключа, используемого в качестве ключа проверки в выданном маркере, набор алгоритмов для взаимодействия между клиентом и службой, необходимость согласования или явного задания учетных данных службы, конкретные утверждения, которые служба ожидает получить в выданном маркере, а также любые дополнительные элементы XML, которые необходимо добавить в запрос, отправляемый клиентом службе маркеров безопасности.  
  
> [!NOTE]
>  Свойство `NegotiateServiceCredential` используется только в том случае, если `SecurityMode` имеет значение `Message`.  Если `SecurityMode` имеет значение `TransportWithMessageCredential`, свойство `NegotiateServiceCredential` игнорируется.  
  
### Настройка привязки WSFederationHttpBinding в коде  
  
1.  Создайте экземпляр класса <xref:System.ServiceModel.WSFederationHttpBinding>.  
  
2.  Присвойте свойству <xref:System.ServiceModel.WSFederationHttpSecurity.Mode%2A> значение <xref:System.ServiceModel.WSFederationHttpSecurityMode> или <xref:System.ServiceModel.WSFederationHttpSecurityMode> в зависимости от необходимости.  Если требуется набор алгоритмов, отличный от <xref:System.ServiceModel.Security.SecurityAlgorithmSuite.Basic256%2A>, присвойте свойству <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.AlgorithmSuite%2A> значение из <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.  
  
3.  Задайте свойство <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.NegotiateServiceCredential%2A> в зависимости от необходимости.  
  
4.  Присвойте свойству <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedKeyType%2A> значение <xref:System.IdentityModel.Tokens.SecurityKeyType>. `SymmetricKey` или `AsymmetricKey` в зависимости от необходимости.  
  
5.  Присвойте свойству <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedTokenType%2A> соответствующее значение.  Если значение не задано, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует значение по умолчанию "http:\/\/docs.oasis\-open.org\/wss\/oasis\-wss\-saml\-token\-profile\-1.1\#SAMLV1.1", что соответствует маркерам SAML 1.1.  
  
6.  Является обязательным для клиента, если не задан локальный издатель; для службы является необязательным.  Создайте объект <xref:System.ServiceModel.EndpointAddress>, содержащий адрес и сведения об удостоверении службы маркеров безопасности и присвойте экземпляр <xref:System.ServiceModel.EndpointAddress> свойству <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerAddress%2A>.  
  
7.  Является обязательным для клиента, если не задан локальный издатель; для службы не используется.  Создайте привязку <xref:System.ServiceModel.Channels.Binding> для службы `SecurityTokenService` и присвойте экземпляр <xref:System.ServiceModel.Channels.Binding> свойству <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerBinding%2A>.  
  
8.  Не используется для клиента; является необязательным для службы.  Создайте экземпляр <xref:System.ServiceModel.EndpointAddress> для метаданных службы маркеров безопасности и присвойте его свойству `IssuerMetadataAddress`.  
  
9. Является необязательным как для клиента, так и для службы.  Создайте и добавьте один или более экземпляров <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement> в коллекцию, возвращаемую свойством <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>.  
  
10. Является необязательным как для клиента, так и для службы.  Создайте и добавьте один или более экземпляров <xref:System.Xml.XmlElement> в коллекцию, возвращаемую свойством <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>.  
  
### Создание федеративной конечной точки в конфигурации  
  
1.  В файле конфигурации создайте элемент [\<wsFederationHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md), являющийся дочерним для элемента [\<привязки\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md).  
  
2.  Создайте элемент [\<привязка\>](../../../../docs/framework/misc/binding.md), являющийся дочерним для элемента [\<wsFederationHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md), и задайте соответствующее значение атрибута `name`.  
  
3.  Создайте элемент `<security>`, являющийся дочерним для элемента [\<привязка\>](../../../../docs/framework/misc/binding.md).  
  
4.  Задайте для атрибута `mode` элемента `<security>` значение `Message` или `TransportWithMessageCredential` в зависимости от необходимости.  
  
5.  Создайте элемент `<message>`, являющийся дочерним для элемента `<security>`.  
  
6.  Необязательно.  Задайте соответствующее значение атрибута `algorithmSuite` элемента `<message>`.  Значение по умолчанию — `Basic256`.  
  
7.  Необязательно.  Если требуется асимметричный ключ проверки, задайте для атрибута `issuedKeyType` элемента `<message>` значение `AsymmetricKey`.  Значение по умолчанию — `SymmetricKey`.  
  
8.  Необязательно.  Задайте значение атрибута `issuedTokenType` элемента `<message>`.  
  
9. Является обязательным для клиента, если не задан локальный издатель; для службы является необязательным.  Создайте элемент `<issuer>`, являющийся дочерним для элемента `<message>`.  
  
10. Задайте атрибут `address` элемента `<issuer>` и укажите адрес, по которому служба маркеров безопасности принимает запросы маркеров.  
  
11. Необязательно.  Добавьте дочерний элемент `<identity>` и задайте удостоверение службы маркеров безопасности.  
  
12. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Идентификация и проверка подлинности службы](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
13. Является обязательным для клиента, если не задан локальный издатель; для службы не используется.  Создайте элемент [\<привязка\>](../../../../docs/framework/misc/binding.md) в разделе привязок, который может быть использован для взаимодействия со службой токенов безопасности.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] создании привязки см. в разделе [Как задать привязку службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
14. Укажите привязку, созданную на предыдущем этапе, задав атрибуты `binding` и `bindingConfiguration` элемента `<issuer>`.  
  
15. Не используется для клиента; является необязательным для службы.  Создайте элемент `<issuerMetadata>`, являющийся дочерним для элемента \<`message`\>.  Затем в атрибуте `address` элемента `<issuerMetadata>` укажите адрес, по которому служба маркеров безопасности должна опубликовать свои метаданные.  Добавьте дочерний элемент `<identity>` и задайте удостоверение службы маркеров безопасности \(необязательно\).  
  
16. Является необязательным как для клиента, так и для службы.  Добавьте элемент `<claimTypeRequirements>` в качестве дочернего элемента для элемента `<message>`.  Укажите обязательные и необязательные утверждения для службы, добавив элементы [\<добавление;\>](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-claimtyperequirements.md) в элемент `<claimTypeRequirements>` и задав тип утверждений с помощью атрибута `claimType`.  С помощью атрибута `isOptional` укажите, является ли то или иное утверждение обязательным.  
  
## Пример  
 Ниже приведен пример кода принудительной настройки привязки `WSFederationHttpBinding`.  
  
 [!code-csharp[c_FederationBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federationbinding/cs/source.cs#2)]
 <!-- TODO: review snippet reference [!code-vb[c_FederationBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federationbinding/vb/source.vb#2)]  -->  
  
## См. также  
 [Федерация](../../../../docs/framework/wcf/feature-details/federation.md)   
 [Образец федерации](../../../../docs/framework/wcf/samples/federation-sample.md)   
 [Как упорядочить отключения безопасных сеансов в WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)