---
title: <secureConversationBootstrap>
ms.date: 03/30/2017
ms.assetid: 66b46f95-fa2d-4b5b-b6ce-0572ab0cdd50
ms.openlocfilehash: b3187cb51b6fd32797c9ad401c704d5f16c6f7e8
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399913"
---
# <a name="secureconversationbootstrap"></a>\<Секуреконверсатионбутстрап >
Задает значения по умолчанию, используемые для инициализации службы безопасного обмена данными.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> безопасности**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Секуреконверсатионбутстрап >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<secureConversationBootstrap allowSerializedSigningTokenOnReply="Boolean"
                             authenticationMode="AuthenticationMode"
                             defaultAlgorithmSuite="SecurityAlgorithmSuite"
                             includeTimestamp="Boolean"
                             requireDerivedKeys="Boolean"
                             keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
                             messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
                             messageSecurityVersion="WSSecurityJan2004/WSSecurityXXX2005"
                             requireDerivedKeys="Boolean"
                             requireSecurityContextCancellation="Boolean"
                             requireSignatureConfirmation="Boolean"
                             securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"
                             includeTimestamp="Boolean" />
```  
  
## <a name="type"></a>Тип  
 `Type`  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`allowSerializedSigningTokenOnReply`|Необязательный параметр. Логическое значение, определяющее, может ли в ответе использоваться сериализованный маркер. Значение по умолчанию — `false`. При использовании двойной привязки для всех параметров, имеющих значение по умолчанию `true`, пропускаются любые установки.|  
|`authenticationMode`|Указывает режим проверки подлинности протокола SOAP, используемый между инициатором и респондентом.<br /><br /> Значение по умолчанию - sspiNegotiated.<br /><br /> Это атрибут типа <xref:System.ServiceModel.Configuration.AuthenticationMode>.|  
|`defaultAlgorithmSuite`|Набор алгоритмов безопасности содержит различные алгоритмы, такие как Canonicalization, Digest, KeyWrap, Signature, Encryption и KeyDerivation. Каждый из наборов алгоритмов безопасности определяет значения для этих различных параметров. Данные алгоритмы обеспечивают безопасность на уровне сообщений.<br /><br /> Этот атрибут используется при работе с другой платформой, которая использует набор алгоритмов, отличный от набора по умолчанию. При внесении изменений в параметры настройки необходимо знать о сильных и слабых сторонах соответствующих алгоритмов. Это атрибут типа <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>. Значение по умолчанию — `Basic256`.|  
|`includeTimestamp`|Логическое значение, определяющее, включается ли в каждое сообщение отметка времени. Значение по умолчанию — `true`.|  
|`keyEntropyMode`|Указывает способ вычисления ключей для защиты сообщений. Ключи могут быть основаны только на данных ключа клиента, только на данных ключа службы или на сочетании обоих типов данных. Допустимые значения:<br /><br /> -Клиентентропи: Ключ сеанса основан на предоставленном клиентом материале ключа.<br />-Серверентропи: Ключ сеанса основан на службе, которая предоставляет материал ключа.<br />-Комбинедентропи: Сеансовый ключ основан на клиенте и службе, который предоставил материал для ключа.<br /><br /> Значение по умолчанию - CombinedEntropy.<br /><br /> Это атрибут типа <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.|  
|`messageProtectionOrder`|Определяет порядок, в котором к сообщению применяются алгоритмы безопасности уровня сообщения. Допустимы следующие значения:<br /><br /> SignBeforeEncrypt Сначала подпишите, а затем зашифруйте.<br />-Сигнбефоринкриптанденкриптсигнатуре: Подписывание, шифрование и шифрование подписи.<br />-Енкриптбефоресигн: Сначала зашифруйте, а затем подпишите.<br /><br /> SignBeforeEncryptAndEncryptSignature - значение по умолчанию, если используются взаимные сертификаты и WS-Security 1.1.  SignBeforeEncrypt - значение по умолчанию, если используется WS-Security 1.0.<br /><br /> Это атрибут типа <xref:System.ServiceModel.Security.MessageProtectionOrder>.|  
|`messageSecurityVersion`|Задает используемую версию WS-Security. Допустимы следующие значения:<br /><br /> - WSSecurityJan2004<br />- WSSecurityXXX2005<br /><br /> Значение по умолчанию - WSSecurityXXX2005. Это атрибут типа <xref:System.ServiceModel.MessageSecurityVersion>.|  
|`requireDerivedKeys`|Логическое значение, которое указывает, могут ли ключи быть производными от исходных ключей проверки. Значение по умолчанию — `true`.|  
|`requireSecurityContextCancellation`|Логическое значение, определяющее, следует ли закрывать и завершать контекст безопасности, когда он больше не нужен. Значение по умолчанию — `true`.|  
|`requireSignatureConfirmation`|Логическое значение, определяющее, включено ли подтверждение сигнатуры WS-Security. Если установлено значение `true`, то сигнатуры сообщений подтверждаются респондентом. Значение по умолчанию — `false`.<br /><br /> Подтверждение сигнатуры используется для подтверждения того, что служба отвечает, получив запрос полностью.|  
|`securityHeaderLayout`|Определяет порядок расположения элементов в заголовке безопасности. Допустимые значения:<br /><br /> Ограничил. Элементы добавляются в заголовок безопасности в соответствии с общим принципом "объявить перед использованием".<br />Слаб. Элементы добавляются в заголовок безопасности в любом порядке, отвечающем требованиям безопасности сообщений WSS: SOAP Message Security.<br />-Лаксвистиместампфирст. Элементы добавляются в заголовок безопасности в любом порядке, отвечающем требованиям безопасности сообщений WSS: SOAP Message Security, но первым элементом в заголовке безопасности должен быть элемент wsse:Timestamp.<br />-Лаксвистиместампласт. Элементы добавляются в заголовок безопасности в любом порядке, отвечающем требованиям безопасности сообщений WSS: SOAP Message Security, но последним элементом в заголовке безопасности должен быть элемент wsse:Timestamp.<br /><br /> Значение по умолчанию - Strict.<br /><br /> Это элемент типа <xref:System.ServiceModel.Channels.SecurityHeaderLayout>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|Определяет текущий выданный маркер. Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>.|  
|[\<Локалклиентсеттингс >](localclientsettings-element.md)|Задает параметры безопасности локального клиента для этой привязки. Это элемент типа <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>.|  
|[\<Локалсервицесеттингс >](localservicesettings-element.md)|Задает параметры безопасности локальной службы для этой привязки. Это элемент типа <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> безопасности](security-of-custombinding.md)|Задает параметры безопасности для пользовательской привязки.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Привязки](../../../wcf/bindings.md)
- [Расширение привязок](../../../wcf/extending/extending-bindings.md)
- [Пользовательские привязки](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
- [Практическое руководство. Создание пользовательской привязки с помощью SecurityBindingElement](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Безопасность пользовательской привязки](../../../wcf/samples/custom-binding-security.md)
