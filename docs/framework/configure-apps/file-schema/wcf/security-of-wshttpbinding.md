---
title: "&lt;security&gt; для &lt;wsHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
caps.latest.revision: 18
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 18
---
# &lt;security&gt; для &lt;wsHttpBinding&gt;
Представляет возможности обеспечения безопасности [\<wsHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).  
  
## Синтаксис  
  
```  
  
<security mode="Message/None/Transport/TransportWithMessageCredential">  
   <transport  
         clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      realm="string"   
      defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      defaultRealm="string" />  
   <message  
            clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
       establishSecurityContext="Boolean"   
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|режим|-   Необязательно.  Задает тип применяемого механизма обеспечения безопасности.  Значение по умолчанию — `Message`.<br />-   Это атрибут типа <xref:System.ServiceModel.SecurityMode>.|  
  
## Атрибут mode  
  
|Значение|Описание|  
|--------------|--------------|  
|Нет|Режим безопасности отключен.|  
|Transport|Безопасность обеспечивается с помощью протокола HTTPS.  Необходимо настроить службу с использованием сертификата SSL.  Сообщение полностью защищено с помощью HTTPS, а проверка подлинности выполняется клиентом с помощью SSL\-сертификата службы.  Проверка подлинности клиента контролируется посредством атрибута `ClientCredentials`.  элемента [\<транспорт\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).|  
|Сообщение|Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.  По умолчанию текст сообщений SOAP шифруется и подписывается.  Этот режим предоставляет множество функций, например сведения о доступности учетных данных службы для клиентов на внештатных каналах, об используемом наборе алгоритмов и об уровне защиты, применяемом к тексту сообщения через свойство Security.Message.  Проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.|  
|TransportWithMessageCredential|В данном режиме HTTPS обеспечивает целостность, конфиденциальность и проверку подлинности сервера, а механизм безопасности сообщений SOAP обеспечивает проверку подлинности клиента.  По умолчанию проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<транспорт\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)|Определяет параметры безопасности транспорта.  Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.|  
|[\<сообщение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)|Определяет параметры безопасности сообщения.  Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<wsHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|Привязка безопасности для приложений транспорта HTTP.|  
  
## Заметки  
 Класс WSHttpBinding предназначен для взаимодействия со службами, реализующими спецификации WS\-\*.  Безопасность транспорта для этой привязки обеспечивается посредством протокола SSL по протоколам HTTP или HTTPS.  
  
## См. также  
 <xref:System.ServiceModel.WSHttpSecurity>   
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>   
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)