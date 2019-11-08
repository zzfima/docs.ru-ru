---
title: <transport> из <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 1afeed62fcbf3b083d69a7cedb7eb80b81f5c17b
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732735"
---
# <a name="transport-of-wshttpbinding"></a>\<транспортную > \<wsHttpBinding >

Определяет параметры проверки подлинности для HTTP-транспорта.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)\
привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) >
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsHttpBinding >** ](wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<security >** ](security-of-wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**транспорта >**  

## <a name="syntax"></a>Синтаксис

```xml
<wsHttpBinding>
  <binding>
    <security mode="None|Transport|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"
                 proxyCredentialType="Basic|Digest|None|Ntlm|Windows"
                 realm="string" />
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</wsHttpBinding>
```

## <a name="type"></a>Type

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`clientCredentialType`|Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе. Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.|
|`proxyCredentialType`|Задает учетные данные, используемые для проверки подлинности клиента при подключении к прокси-серверу домена. Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.|
|`realm`|Строка, указывающая область проверки подлинности для обычной проверки подлинности или дайджест-проверки подлинности. Значение по умолчанию - пустая строка.<br /><br /> Область проверки подлинности задает по крайней мере имя основного узла, выполняющего проверку подлинности. Она также может указывать коллекцию пользователей, которым разрешен доступ. Пользователь может запросить область проверки подлинности, чтобы выяснить, какое из нескольких возможных сочетаний имен пользователей и паролей можно использовать.|
|`policyEnforcement`|Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.<br /><br /> 1. Never — политика никогда не применяется (Расширенная защита отключена).<br />2. WhenSupported — политика применяется, только если клиент поддерживает расширенную защиту.<br />3. всегда — политика всегда применяется принудительно. Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.|

## <a name="clientcredentialtype-attribute"></a>Атрибут clientCredentialType

|значения|Описание|
|-----------|-----------------|
|`None`|Режим безопасности отключен.|
|`Basic`|Используется обычная проверка подлинности.|
|`Digest`|Используется дайджест-проверка подлинности.|
|`Ntlm`|Используется проверка подлинности NTLM в качестве резервной в домене Windows.|
|`Windows`|Используется встроенная проверка подлинности Windows.|
|`Certificate`|Для проверки подлинности клиента используются сертификаты X.509.|

## <a name="proxycredentialtype-attribute"></a>Атрибут proxyCredentialType

|значения|Описание|
|-----------|-----------------|
|`None`|Режим безопасности отключен.|
|`Basic`|Используется обычная проверка подлинности.|
|`Digest`|Используется дайджест-проверка подлинности.|
|`Ntlm`|Используется проверка подлинности NTLM в качестве резервной в домене Windows.|
|`Windows`|Используется встроенная проверка подлинности Windows.|
|`Certificate`|Для проверки подлинности клиента используются сертификаты X.509.|

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<> безопасности](security-of-wshttpbinding.md)|Представляет возможности безопасности [\<wsHttpBinding >](wshttpbinding.md).|

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
- [Привязки](../../../wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [> привязки \<](bindings.md)
