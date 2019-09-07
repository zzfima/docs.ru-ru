---
title: <message> из <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 09d9d4a5d1967afaf9a6ed5756c309e78fee0923
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400258"
---
# <a name="message-of-netmsmqbinding"></a>\<> сообщений > \<NetMsmqBinding

Определяет параметры безопасности сообщений SOAP для данной привязки `netMsmqBinding`.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netMsmqBinding >** ](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> безопасности**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> сообщения**  

## <a name="syntax"></a>Синтаксис

```xml
<netMsmqBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
    </security>
  </binding>
</netMsmqBinding>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|algorithmSuite|Задает алгоритмы шифрования сообщений и ключей, которые используются для обеспечения безопасности на уровне сообщений для сообщений, которые отправляются с помощью транспорта MSMQ.<br /><br /> Значение по умолчанию — `Aes256`. Это атрибут типа <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.|
|clientCredentialType|Задает тип учетных данных, используемых при проверке подлинности клиента для сообщений, которые отправляются с помощью транспорта MSMQ. Допустимы следующие значения:<br /><br /> None Данный атрибут позволяет службе взаимодействовать с анонимными клиентами. Как для службы, так и для клиента учетные данные не требуются.<br />Windows Это позволяет обмену SOAP в контексте учетных данных Windows, прошедших проверку подлинности. В этом случае всегда выполняется проверка подлинности на основе Kerberos.<br />Имен Это позволяет службе требовать проверку подлинности клиента с помощью учетных данных имени пользователя. Учетные данные в этом случае необходимо указать с помощью `clientCredentials` предупреждения о поведении **:**  Windows Communication Foundation (WCF) не поддерживает отправку дайджеста пароля или получение ключей с помощью пароля и использование таких ключей для обеспечения безопасности сообщений. Таким образом, WCF обеспечивает защиту Exchange при использовании учетных данных пользователя. В данном режиме требуется, чтобы сертификат службы был указан на стороне клиента при помощи поведения `clientCredential` и при помощи `serviceCertificate`. <br /><br /> Certificate Это позволяет службе требовать проверку подлинности клиента с помощью сертификата. В этом случае учетные данные клиента должны быть определены с помощью поведения `clientCredentials`. Учетные данные службы в данном случае должны быть определены с помощью поведения `clientCredentials`, которому задается значение `serviceCertificate`.<br />Предназначена Это позволяет службе требовать проверку подлинности клиента с помощью CardSpace. Необходимо определить `serviceCertificate` в поведении `clientCredential`.<br /><br /> Значение по умолчанию — `Windows`. Это атрибут типа <xref:System.ServiceModel.MessageCredentialType>.|

### <a name="child-elements"></a>Дочерние элементы

Отсутствуют

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<> безопасности](security-of-netmsmqbinding.md)|Определяет параметры безопасности для привязки.|

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [Очереди в WCF](../../../wcf/feature-details/queues-in-wcf.md)
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
- [Привязки](../../../wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<Привязка >](../../../misc/binding.md)
