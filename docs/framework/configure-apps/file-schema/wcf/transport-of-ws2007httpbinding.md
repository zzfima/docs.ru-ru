---
title: "&lt;transport&gt; для &lt;ws2007HttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# &lt;transport&gt; для &lt;ws2007HttpBinding&gt;
Определяет параметры проверки подлинности для HTTP\-транспорта.  
  
## Синтаксис  
  
```  
  
transport clientCredentialType =   
       "Basic/Certificate/Digest/None/Ntlm/Windows"  
       proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
       realm="string"   
```  
  
## Тип  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`clientCredentialType`|Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.  Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.|  
|`proxyCredentialType`|Задает учетные данные, используемые для проверки подлинности клиента при подключении к прокси\-серверу домена.  Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.|  
|`realm`|Область проверки подлинности, используемая для дайджест\-проверки подлинности или базовой проверки подлинности.  Значение по умолчанию \- пустая строка.<br /><br /> Область проверки подлинности задает по крайней мере имя основного узла, выполняющего проверку подлинности.  Она также может указывать коллекцию пользователей, которым разрешен доступ.  Пользователь может направить запрос к области проверки подлинности, чтобы определить, какие конкретно имя и пароль из нескольких возможных можно использовать.|  
  
## Атрибут clientCredentialType  
  
|Значение|Описание|  
|--------------|--------------|  
|Нет|Режим безопасности отключен.|  
|Basic|Используется обычная проверка подлинности.|  
|Digest|Используется дайджест\-проверка подлинности.|  
|Ntlm|Используется проверка подлинности NTLM в качестве резервной в домене Windows.|  
|Windows|Используется встроенная проверка подлинности Windows.|  
|Сертификат|Для проверки подлинности клиента используются сертификаты X.509.|  
  
## Атрибут proxyCredentialType  
  
|Значение|Описание|  
|--------------|--------------|  
|Нет|Режим безопасности отключен.|  
|Basic|Используется обычная проверка подлинности.|  
|Digest|Используется дайджест\-проверка подлинности.|  
|Ntlm|Используется проверка подлинности NTLM в качестве резервной в домене Windows.|  
|Windows|Используется встроенная проверка подлинности Windows.|  
|Сертификат|Для проверки подлинности клиента используются сертификаты X.509.|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<безопасность\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|Представляет возможности обеспечения безопасности элемента [\<ws2007HttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md).|  
  
## См. также  
 <xref:System.ServiceModel.HttpTransportSecurity>   
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>   
 <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)