---
title: "&lt;транспорт&gt; для &lt;netHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;транспорт&gt; для &lt;netHttpBinding&gt;
Определяет свойства, которые управляют параметрами проверки подлинности для транспорта HTTP.  
  
## Синтаксис  
  
```  
<netHttpBinding>  
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
</basicHttpBinding>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|clientCredentialType|-   Задает тип учетных данных, которые должны использоваться при проверке подлинности клиента с использованием проверки подлинности HTTP.  Значение по умолчанию — `None`.  Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.|  
|proxyCredentialType|-   Задает тип учетных данных, используемых при проверке подлинности клиента из домена с использованием прокси через HTTP.  Этот атрибут применим, только если атрибут `mode` родительского элемента `security` имеет значение `Transport` или `TransportCredentialsOnly`.  Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.|  
|realm|Строка, указывающая область, используемую схемой проверки подлинности HTTP для обычной проверки подлинности или дайджест\-проверки подлинности.  Значение по умолчанию \- пустая строка.|  
|policyEnforcement|Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtectionPolicy>.<br /><br /> 1.  Never \- политика никогда не применяется \(расширенная защита отключена\).<br />2.  WhenSupported \- политика применяется только тогда, когда клиент поддерживает расширенную защиту.<br />3.  Always \- политика применяется всегда.  Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.|  
|protectionScenario|Это перечисление указывает сценарий защиты, регламентированный политикой.|  
  
## Атрибут clientCredentialType  
  
|Значение|Описание|  
|--------------|--------------|  
|Нет|Во время передачи сообщения не защищены.|  
|Basic|Задает обычную проверку подлинности.|  
|Digest|Задает дайджест\-проверку подлинности.|  
|Ntlm|Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.|  
|Windows|Задает встроенную проверку подлинности Windows.|  
  
## Атрибут proxyCredentialType  
  
|Значение|Описание|  
|--------------|--------------|  
|Нет|-   Во время передачи сообщения не защищены.|  
|Basic|Задает обычную проверку подлинности, как определено документом RFC 2617, который посвящен проверке подлинности HTTP, обычной проверке и дайджест\-проверке подлинности.|  
|Digest|Задает дайджест\-проверку подлинности, как определено документом RFC 2617, который посвящен проверке подлинности HTTP, обычной проверке и дайджест\-проверке подлинности.|  
|Ntlm|Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.|  
|Windows|Задает встроенную проверку подлинности Windows.|  
|Сертификат|Выполняет проверку подлинности клиента с использованием сертификата.  Такая возможность действует, только если атрибут `Mode` родительского элемента `security` имеет значение Transport, и не действует, если этот атрибут имеет значение TransportCredentialOnly.|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<безопасность\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|Определяет возможности безопасности для элемента [\<netHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md).|  
  
## Пример  
 В следующем примере демонстрируется использование безопасности транспорта SSL с использованием основной привязки.  По умолчанию основная привязка поддерживает взаимодействие по протоколу HTTP.  
  
```  
<system.serviceModel>  
   <services>  
      <service   
          type="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
         <endpoint address=""  
               binding="netHttpBinding"  
               bindingConfiguration="Binding1"   
               contract="Microsoft.ServiceModel.Samples.ICalculator" />  
      </service>  
   </services>  
    <bindings>  
        <netHttpBinding>  
        <!-- Configure basicHttpBinding with Transport security -- >  
        <!-- mode and clientCredentialType set to None.-->  
           <binding name="Binding1">  
               <security mode="Transport">  
                   <transport clientCredentialType="None"  
                              proxyCredentialType="None">  
                       <extendedProtectionPolicy  
                          policyEnforcement="WhenSupported"  
                          protectionScenario="TransportSelected">  
                    <customServiceNames></customServiceNames>  
                       </extendedProtectionPolicy>  
               </security>  
           </binding>  
        </netHttpBinding>  
    </bindings>  
</system.serviceModel>  
```  
  
## См. также  
 <xref:System.ServiceModel.Configuration.NetHttpSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.NetHttpSecurity.Transport%2A>   
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>   
 <xref:System.ServiceModel.HttpTransportSecurity>   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)