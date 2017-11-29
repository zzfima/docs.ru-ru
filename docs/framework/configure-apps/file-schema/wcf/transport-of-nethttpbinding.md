---
title: "&lt;транспорт&gt; для &lt;netHttpBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 67bacedb9a2e46903b97ea0747880bbb1af24a68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportgt-of-ltnethttpbindinggt"></a>&lt;транспорт&gt; для &lt;netHttpBinding&gt;
Определяет свойства, которые управляют параметрами проверки подлинности для транспорта HTTP.  
  
\<system.serviceModel >  
\<привязки >  
\<Привязка netHttpBinding >  
\<Привязка >  
\<Безопасность >  
\<Транспорт >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml
<netHttpBinding>  
  <binding>  
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">  
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"  
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows" realm="string">  
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"  
                                  protectionScenario="TransportSelected|TrustedProxy">  
          <customServiceNames></customServiceNames>  
        </extendedProtectionPolicy>  
      </transport>  
    </security>  
  </binding>  
</netHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|clientCredentialType|— Указывает тип учетных данных для использования при проверке подлинности клиента с проверкой подлинности HTTP.  Значение по умолчанию — `None`. Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.|  
|proxyCredentialType|— Указывает тип учетных данных для использования при проверке подлинности клиента из домена с использованием прокси-сервер по протоколу HTTP. Этот атрибут применим, только если атрибут `mode` родительского элемента `security` имеет значение `Transport` или `TransportCredentialsOnly`. Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.|  
|realm|Строка, указывающая область, используемую схемой проверки подлинности HTTP для обычной проверки подлинности или дайджест-проверки подлинности. Значение по умолчанию - пустая строка.|  
|policyEnforcement|Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.<br /><br /> 1.  Never - политика никогда не применяется (расширенная защита отключена).<br />2.  WhenSupported - политика применяется только тогда, когда клиент поддерживает расширенную защиту.<br />3.  Always - политика применяется всегда. Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.|  
|protectionScenario|Это перечисление указывает сценарий защиты, регламентированный политикой.|  
  
## <a name="clientcredentialtype-attribute"></a>Атрибут clientCredentialType  
  
|Значение|Описание|  
|-----------|-----------------|  
|Нет|Во время передачи сообщения не защищены.|  
|Basic|Задает обычную проверку подлинности.|  
|Digest|Задает дайджест-проверку подлинности.|  
|Ntlm|Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.|  
|Windows|Задает встроенную проверку подлинности Windows.|  
  
## <a name="proxycredentialtype-attribute"></a>Атрибут proxyCredentialType  
  
|Значение|Описание|  
|-----------|-----------------|  
|Нет|-Во время передачи сообщения не защищены.|  
|Basic|Задает обычную проверку подлинности, как определено документом RFC 2617, который посвящен проверке подлинности HTTP, обычной проверке и дайджест-проверке подлинности.|  
|Digest|Задает дайджест-проверку подлинности, как определено документом RFC 2617, который посвящен проверке подлинности HTTP, обычной проверке и дайджест-проверке подлинности.|  
|Ntlm|Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.|  
|Windows|Задает встроенную проверку подлинности Windows.|  
|Сертификат|Выполняет проверку подлинности клиента с использованием сертификата. Такая возможность действует, только если атрибут `Mode` родительского элемента `security` имеет значение Transport, и не действует, если этот атрибут имеет значение TransportCredentialOnly.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Безопасность >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|Определяет возможности безопасности для [ \<netHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md).|  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется использование безопасности транспорта SSL с использованием основной привязки. По умолчанию основная привязка поддерживает взаимодействие по протоколу HTTP.  
  
```xml
<system.serviceModel>  
  <services>  
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"  
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
            <extendedProtectionPolicy policyEnforcement="WhenSupported"  
                                      protectionScenario="TransportSelected">  
              <customServiceNames></customServiceNames>  
            </extendedProtectionPolicy>
          </transport> 
        </security>  
      </binding>  
    </netHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Привязки](../../../../../docs/framework/wcf/bindings.md)  
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Использование привязок для настройки служб Windows Communication Foundation и клиентов](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<Привязка >](../../../../../docs/framework/misc/binding.md)
