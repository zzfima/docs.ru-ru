---
title: '&lt;message&gt; для &lt;netMsmqBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 0e947667c414079f24398b401456efd56bf9922c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ltmessagegt-of-ltnetmsmqbindinggt"></a>&lt;message&gt; для &lt;netMsmqBinding&gt;
Определяет параметры безопасности сообщений SOAP для данной привязки `netMsmqBinding`.  
  
 \<система. ServiceModel >  
\<привязки >  
\<netMsmqBinding >  
\<Привязка >  
\<Безопасность >  
\<сообщение >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<netMsmqBinding>  
    <binding>  
      <security>  
         <message   
                      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
    </security>  
</netMsmqBinding>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|algorithmSuite|Задает алгоритмы шифрования сообщений и ключей, которые используются для обеспечения безопасности на уровне сообщений для сообщений, которые отправляются с помощью транспорта MSMQ.<br /><br /> Значение по умолчанию — `Aes256`. Это атрибут типа <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.|  
|clientCredentialType|Задает тип учетных данных, используемых при проверке подлинности клиента для сообщений, которые отправляются с помощью транспорта MSMQ. Допустимы следующие значения:<br /><br /> — None: Данное значение позволяет службе взаимодействовать с анонимными клиентами. Как для службы, так и для клиента учетные данные не требуются.<br />-Windows: Это позволяет проводить проверку подлинности учетных данных Windows обмен сообщениями SOAP. В этом случае всегда выполняется проверка подлинности на основе Kerberos.<br />-UserName: Данное значение позволяет службе требовать проверку подлинности клиента с помощью учетных данных UserName. В этом случае необходимо указать с помощью учетных данных `clientCredentials` поведение **осторожность:** Windows Communication Foundation (WCF) не поддерживает отправку хэш-кода или получение ключей с использованием пароля и использование таких ключей для пароля безопасность сообщений. Таким образом WCF принудительно обеспечивает безопасность обмена данными при использовании учетных данных UserName. В данном режиме требуется, чтобы сертификат службы был указан на стороне клиента при помощи поведения `clientCredential` и при помощи `serviceCertificate`. <br /><br /> -Certificate: Данное значение позволяет службе требовать проверки подлинности клиента с помощью сертификата. В этом случае учетные данные клиента должны быть определены с помощью поведения `clientCredentials`. Учетные данные службы в данном случае должны быть определены с помощью поведения `clientCredentials`, которому задается значение `serviceCertificate`.<br />-CardSpace: Данное значение позволяет службе требовать проверки подлинности клиента с помощью CardSpace. Необходимо определить `serviceCertiifcate` в поведении `clientCredential`.<br /><br /> Значение по умолчанию — `Windows`. Это атрибут типа <xref:System.ServiceModel.MessageCredentialType>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Безопасность >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|Определяет параметры безопасности для привязки.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>  
 <xref:System.ServiceModel.MessageSecurityOverMsmq>  
 [Очереди в WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Привязки](../../../../../docs/framework/wcf/bindings.md)  
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Использование привязок для настройки служб Windows Communication Foundation и клиентов](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<Привязка >](../../../../../docs/framework/misc/binding.md)
