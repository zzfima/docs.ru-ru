---
title: "&lt;transport&gt; для &lt;netTcpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# &lt;transport&gt; для &lt;netTcpBinding&gt;
Определяет тип требований безопасности на уровне сообщений для конечной точки, настроенной с [\<netTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
## Синтаксис  
  
```  
<netTcpBinding>  
    <binding>  
        <security  
         mode="None|Transport|Message|TransportWithMessageCredential">  
            <transport clientCredentialType="None|Windows|Certificate"  
             protectionLevel="None|Sign|EncryptAndSign"  
             sslProtocols="Ssl3|Tls|Tls11|Tls12">  
                <extendedProtectionPolicy  
                     policyEnforcement="Never|WhenSupported|Always"  
                     protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                        </extendedProtectionPolicy>  
            </transport>  
        </security>  
    </binding>  
</netTcpBinding>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|clientCredentialType|Необязательно.  Задает тип учетных данных, используемых при проверке подлинности клиента с помощью безопасности транспорта.<br /><br /> -   Значение по умолчанию — `Windows`.<br />-   Это атрибут типа <xref:System.ServiceModel.TcpClientCredentialType>.|  
|protectionLevel|Необязательно.  Определяет безопасность на уровне транспорта TCP.  Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.  Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.<br /><br /> Значение по умолчанию — `EncryptAndSign`.|  
|sslProtocols|Значение флага перечисления SslProtocols, указывающее, какие протоколы SslProtocols поддерживаются.  Значение по умолчанию — Ssl3&#124;Tls&#124;Tls11&#124;Tls12.|  
|policyEnforcement|Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtectionPolicy>.<br /><br /> 1.  Never \- политика никогда не применяется \(расширенная защита отключена\).<br />2.  WhenSupported \- политика применяется только тогда, когда клиент поддерживает расширенную защиту.<br />3.  Always \- политика применяется всегда.  Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.|  
  
## Атрибут clientCredentialType  
  
|Значение|Описание|  
|--------------|--------------|  
|Нет|Анонимный клиент.  Это требует сертификата для службы.|  
|Windows|Задает проверку подлинности Windows для клиента с использованием согласования SP \(согласование Kerberos\).|  
|Сертификат|Проверка подлинности клиента выполняется с использованием сертификата.  Это требует согласования SSL и сертификата для службы.|  
  
## Атрибут protectionLevel  
  
|Значение|Описание|  
|--------------|--------------|  
|Нет|Нет защиты.|  
|Sign|Сообщения подписываются.|  
|EncryptAndSign|-   Сообщения шифруются и подписываются.|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<безопасность\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|Задает возможности безопасности [\<netTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).|  
  
## Заметки  
 Безопасность транспорта используется для обеспечения целостности и конфиденциальности сообщений SOAP и для взаимной проверки подлинности.  Если этот режим безопасности выбран для какой\-либо привязки, стек каналов настраивается с использованием безопасного транспорта, а сообщения SOAP защищаются с использованием безопасности транспорта, например Windows \(Negotiate\) или SSL по TCP.  
  
## См. также  
 <xref:System.ServiceModel.TcpTransportSecurity>   
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>   
 <xref:System.ServiceModel.Configuration.NetTcpTransportSecurityElement>   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)