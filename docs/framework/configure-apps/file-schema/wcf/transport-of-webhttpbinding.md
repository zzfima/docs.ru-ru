---
title: "&lt;transport&gt; для &lt;webHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;transport&gt; для &lt;webHttpBinding&gt;
Определяет параметры безопасности уровня транспорта для конечной точки службы, настроенной для получения запросов HTTP.  
  
## Синтаксис  
  
```  
<webHttpBinding>  
    <binding>  
        <security  
        mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">  
            <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"  
             proxyCredentialType="None|Basic|Digest|Ntlm|Windows" realm="string" >  
                <extendedProtectionPolicy  
                     policyEnforcement="Never|WhenSupported|Always"  
                     protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                        </extendedProtectionPolicy>  
            </transport>  
        </security>  
    </binding>  
</WebHttpBinding>  
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
|`realm`|Строка, указывающая область проверки подлинности для обычной проверки подлинности или дайджест\-проверки подлинности.  Значение по умолчанию \- пустая строка.<br /><br /> Область проверки подлинности задает по крайней мере имя основного узла, выполняющего проверку подлинности.  Она также может указывать коллекцию пользователей, которым разрешен доступ.  Пользователь может запросить область проверки подлинности, чтобы выяснить, какое из нескольких возможных сочетаний имен пользователей и паролей можно использовать.|  
|`policyEnforcement`|Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtectionPolicy>.<br /><br /> 1.  Never \- политика никогда не применяется \(расширенная защита отключена\).<br />2.  WhenSupported \- политика применяется только тогда, когда клиент поддерживает расширенную защиту.<br />3.  Always \- политика применяется всегда.  Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.|  
  
## Атрибут clientCredentialType  
  
|Значение|Описание|  
|--------------|--------------|  
|`None`|Режим безопасности отключен.|  
|`Basic`|Используется обычная проверка подлинности.|  
|`Certificate`|Для проверки подлинности клиента используются сертификаты X.509.|  
|`Digest`|Используется дайджест\-проверка подлинности.|  
|`Ntlm`|Используется проверка подлинности NTLM в качестве резервной в домене Windows.|  
|`Windows`|Используется встроенная проверка подлинности Windows.|  
  
## Атрибут proxyCredentialType  
  
|Значение|Описание|  
|--------------|--------------|  
|`None`|Режим безопасности отключен.|  
|`Basic`|Используется обычная проверка подлинности.|  
|`Digest`|Используется дайджест\-проверка подлинности.|  
|`Ntlm`|Используется проверка подлинности NTLM в качестве резервной в домене Windows.|  
|`Windows`|Используется встроенная проверка подлинности Windows.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<безопасность\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-webhttpbinding.md)|Представляет возможности обеспечения безопасности элемента [\<wsHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).|  
  
## См. также  
 <xref:System.ServiceModel.HttpTransportSecurity>   
 <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>   
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)   
 [Модель веб\-программирования HTTP WCF](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)