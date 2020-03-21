---
title: Миграция веб-служб WSE 3.0 на платформу WCF
ms.date: 03/30/2017
ms.assetid: 7bc5fff7-a2b2-4dbc-86cc-ecf73653dcdc
ms.openlocfilehash: 8f79674350109d111fe263704dee6c40c1a12451
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184572"
---
# <a name="migrating-wse-30-web-services-to-wcf"></a>Миграция веб-служб WSE 3.0 на платформу WCF
Преимущества миграции web-сервисов WSE 3.0 в Фонд связи Windows (WCF) включают повышение производительности и поддержку дополнительных транспортных средств, дополнительные сценарии безопасности и спецификации WS-. Веб-сервис, который переносится с WSE 3.0 на WCF, может испытывать до 200% до 400% повышения производительности. Для получения дополнительной информации о транспортных перевозках, поддерживаемых WCF, [см.](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md) Для списка сценариев, поддерживаемых WCF, [см.](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md) Список спецификаций, поддерживаемых WCF, можно узнать в [Руководстве по совместимости протоколов Web-сервисов.](../../../../docs/framework/wcf/feature-details/web-services-protocols-interoperability-guide.md)  
  
 В следующих разделах содержатся рекомендации о том, как перенести определенную функцию Web-сервиса WSE 3.0 в WCF.  
  
## <a name="general"></a>Общие сведения  
 WSE 3.0 и WCF включают в себя совместимость на уровне проводов и общий набор терминологии. WSE 3.0 и WCF являются совместимыми на уровне проводов на основе набора спецификаций WS-, которые они оба поддерживают. При разработке приложения WSE 3.0 или WCF существует общий набор терминологии, например, имена утверждений безопасности под ключ в WSE и режимы аутентификации.  
  
 Хотя существует много похожих аспектов между WCF и ASP.NET или WSE 3.0 модели программирования, они отличаются. Для получения подробной информации о модели программирования WCF [см.](../../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
> [!NOTE]
> Для переноса web-сервиса WSE в WCF для создания клиента можно использовать инструмент [ServiceModel Metadata Utility Tool (Svcutil.exe).](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Такой клиент содержит интерфейсы и классы, которые можно использовать в качестве отправной точки и для службы WCF. Созданные интерфейсы имеют атрибут <xref:System.ServiceModel.OperationContractAttribute>, применяемый ко всем членам контракта, у которых свойству <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> присвоено значение `*`. Когда клиент WSE вызывает веб-службу с этим параметром, выбрасывается следующее исключение: **Web.Services3.ResponseProcessingException: WSE910: Ошибка произошла при обработке сообщения ответа, и вы можете найти ошибку во внутреннем исключении.** Чтобы избежать такой ситуации, присвойте свойству <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> атрибута <xref:System.ServiceModel.OperationContractAttribute> значение, отличное от `null`, например `http://Microsoft.WCF.Documentation/ResponseToOCAMethod`.  
  
## <a name="security"></a>Безопасность  
  
### <a name="wse-30-web-services-that-are-secured-using-a-policy-file"></a>Защита веб-служб WSE 3.0 обеспечивается с помощью файла политики.  
 Службы WCF могут использовать файл конфигурации для обеспечения безопасности службы, и этот механизм аналогичен файлу политики WSE 3.0. В WSE 3.0 при защите веб-службы с помощью файла политики используется либо готовое к использованию утверждение безопасности, либо утверждение пользовательской политики. Утверждения безопасности под ключ точно отображаются в режиме проверки подлинности элемента связывания безопасности WCF. Режимы проверки подлинности WCF и утверждения безопасности под ключ WSE 3.0 под ключ называются одинаковыми или аналогичным образом, но и обеспечивают безопасность сообщений с использованием одних и тех же типов учетных данных. Например, `usernameForCertificate` утверждение безопасности под ключ на картах `UsernameForCertificate` WSE 3.0 в режиме проверки подлинности в WCF. Следующие примеры кода показывают, как `usernameForCertificate` минимальная политика, использующая утверждение безопасности под ключ на картах WSE 3.0 в режиме `UsernameForCertificate` проверки подлинности в WCF в пользовательском связке.  
  
 **WSE 3.0**  
  
```xml  
<policies>  
  <policy name="MyPolicy">  
    <usernameForCertificate messageProtectionOrder="SignBeforeEncrypt"  
                            requireDeriveKeys="true"/>  
  </policy>  
</policies>  
```  
  
 **WCF**  
  
```xml  
<customBinding>  
  <binding name="MyBinding">  
    <security authenticationMode="UserNameForCertificate"
              messageProtectionOrder="SignBeforeEncrypt"  
              requireDerivedKeys="true"/>  
  </binding>  
</customBinding>  
```  
  
 Для переноса параметров безопасности web-сервиса WSE 3.0, указанных в файле политики в WCF, в файле конфигурации должна быть создана пользовательская привязка, а утверждение безопасности под ключ должно быть настроено на эквивалентный режим проверки подлинности. Кроме того, необходимо настроить пользовательскую привязку для использования версии спецификации WS-Addressing от августа 2004 г. при взаимодействии клиентов WSE 3.0 с этой службой. Если миграционная служба WCF не требует связи с клиентами WSE 3.0 и должна поддерживать только паритет безопасности, рассмотрите возможность использования системных привязок WCF с соответствующими настройками безопасности вместо создания пользовательской привязки.  
  
 В следующей таблице перечислено отображение между файлом политики WSE 3.0 и эквивалентной пользовательской привязкой в WCF.  
  
|Готовое к использованию утверждение безопасности WSE 3.0|Конфигурация пользовательской привязки WCF|  
|----------------------------------------|--------------------------------------|  
|\<usernameOverTransportSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UserNameOverTransport" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate10Security />|`<customBinding>   <binding name="MyBinding">     <security messageSecurityVersion="WSSecurity10WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10" authenticationMode="MutualCertificate" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<usernameForCertificateSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UsernameForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<анонимныйForcertificateSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="AnonymousForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<kerberosSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="Kerberos"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate11Security />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="MutualCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
  
 Для получения дополнительной информации о создании пользовательских привязок в WCF [см.](../../../../docs/framework/wcf/extending/custom-bindings.md)  
  
### <a name="wse-30-web-services-that-are-secured-using-application-code"></a>Веб-службы WSE 3.0, защищаемые с использованием кода приложения  
 Независимо от того, используются ли WSE 3.0 или WCF, требования безопасности могут быть указаны в коде приложения, а не в конфигурации. В WSE 3.0 для этого создается класс, наследуемый от класса `Policy`, и добавляются требования путем вызова метода `Add`. Для получения более подробной информации об определении требований безопасности в коде [см.](https://docs.microsoft.com/previous-versions/dotnet/netframework-2.0/aa528763(v=msdn.10)) В WCF, чтобы указать требования безопасности <xref:System.ServiceModel.Channels.BindingElementCollection> в коде, <xref:System.ServiceModel.Channels.SecurityBindingElement> <xref:System.ServiceModel.Channels.BindingElementCollection>создайте экземпляр класса и добавьте экземпляр a к . Требования утверждений безопасности задаются с использованием статических методов поддержки режима проверки подлинности класса <xref:System.ServiceModel.Channels.SecurityBindingElement>. Для получения более подробной информации об определении требований безопасности в коде с помощью WCF [см. Как: Создать пользовательскую связующую систему с использованием SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md) и [как: Создать SecurityBindingElement для определенного режима аутентификации](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
### <a name="wse-30-custom-policy-assertion"></a>Утверждение пользовательской политики WSE 3.0  
 В WSE 3.0 предусмотрены два типа утверждений пользовательской политики: утверждения, обеспечивающие защиту сообщения SOAP, и утверждения, не обеспечивающие защиту сообщения SOAP. Утверждения политики, что безопасные сообщения SOAP `SecurityPolicyAssertion` происходят из класса WSE <xref:System.ServiceModel.Channels.SecurityBindingElement> 3.0, а концептуальный эквивалент в WCF является классом.  
  
 Важно отметить, что утверждения безопасности wsE 3.0 под ключ являются подмножеством режимов аутентификации WCF. Если вы создали утверждение пользовательской политики в WSE 3.0, может быть эквивалентный режим проверки подлинности WCF. Например, в WSE 3.0 отсутствует утверждение безопасности CertificateOverTransport, эквивалентное готовому к использованию утверждению безопасности `UsernameOverTransport`. Вместо этого для целей проверки подлинности клиента используется сертификат X.509. Если вы определили свое собственное утверждение пользовательской политики для этого сценария, WCF делает миграцию простой. WCF определяет режим проверки подлинности для этого сценария, так что вы можете воспользоваться методами<xref:System.ServiceModel.Channels.SecurityBindingElement>помощи режима статической аутентификации для настройки WCF.  
  
 Если нет режима проверки подлинности WCF, что эквивалентно утверждению пользовательской политики, которое защищает сообщения SOAP, получает класс из <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>классов <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> или <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>WCF и указывает эквивалентный элемент связывания. Для получения более подробной информации см. [Как: Создать пользовательский связывание с использованием SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
 Для преобразования утверждения пользовательской политики, которое не обеспечивает сообщение SOAP, [см. Фильтрация](../../../../docs/framework/wcf/feature-details/filtering.md) и образец [custom Message Interceptor.](../../../../docs/framework/wcf/samples/custom-message-interceptor.md)  
  
### <a name="wse-30-custom-security-token"></a>Пользовательский маркер безопасности WSE 3.0  
 Модель программирования WCF для создания пользовательского токена отличается от WSE 3.0. Подробную информацию о создании пользовательского токена в WSE можно узнать на примере [создания токенов пользовательской безопасности.](https://docs.microsoft.com/previous-versions/dotnet/netframework-2.0/aa529304(v=msdn.10)) Подробную информацию о создании пользовательского токена в WCF можно узнать по смотреть в [пример: Создать пользовательский токен.](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)  
  
### <a name="wse-30-custom-token-manager"></a>Пользовательский диспетчер маркеров WSE 3.0  
 Модель программирования для создания пользовательского менеджера токенов в WCF отличается от WSE 3.0. Подробную [информацию](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)о том, как создать пользовательский маркерный менеджер и другие компоненты, необходимые для пользовательского маркера безопасности, см.  
  
> [!NOTE]
> Если вы создали `UsernameToken` пользовательский маркербезопасности, WCF предоставляет более простой механизм для определения логики проверки подлинности, чем создание пользовательского менеджера маркеров безопасности. Для получения более подробной информации см. [Как: Используйте пользовательское имя пользователя и пароль валидатора](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md).  
  
### <a name="wse-30-web-services-that-use-mtom-encoded-soap-messages"></a>Веб-службы WSE 3.0, использующие сообщения SOAP с кодировкой MTOM  
 Как и приложение WSE 3, приложение WCF может указать кодирование сообщения MTOM в конфигурации. Чтобы перенести эту настройку, добавьте [ \<>mtomMessageEncoding](../../../../docs/framework/configure-apps/file-schema/wcf/mtommessageencoding.md) в привязку к службе. Следующий пример кода показывает, как кодирование MTOM указано в WSE 3.0 для службы, эквивалентной WCF.  
  
 **WSE 3.0**  
  
```xml  
<messaging>  
    <mtom clientMode="On"/>  
</messaging>  
```  
  
 **WCF**  
  
```xml  
<customBinding>  
  <binding name="MyBinding">  
    <mtomMessageEncoding/>  
  </binding>  
</customBinding>  
```  
  
## <a name="messaging"></a>Обмен сообщениями  
  
### <a name="wse-30-applications-that-use-the-wse-messaging-api"></a>Приложения WSE 3.0, использующие API обмена сообщениями WSE  

 Если для прямого доступа к данным XML, передаваемым между клиентами и веб-службами, используется API обмена сообщениями WSE, приложение можно преобразовать для использования POX (Plain Old XML). Для получения более подробной информации о POX, [см.](interoperability-with-pox-applications.md) Для получения более подробной информации о WSE Messaging API [см. Отправка и получение сообщений SOAP с помощью API сообщений WSE.](https://docs.microsoft.com/previous-versions/dotnet/netframework-2.0/aa529293(v=msdn.10))  
  
## <a name="transports"></a>Транспорты  
  
### <a name="tcp"></a>TCP  
 По умолчанию клиенты WSE 3.0 и веб-службы, отправляющие сообщения SOAP с помощью транспорта TCP, не сотрудничают с клиентами WCF и web-сервисами. Эта несовместимость обусловлена различиями в кадрировании в протоколе TCP и причинами, связанными с обеспечением производительности. Тем не менее, в примере WCF подробно описано, как реализовать пользовательскую сессию TCP, которая взаимодействует с WSE 3.0. Подробную информацию об этой выборке можно узнать на [примере: Transport: WSE 3.0 TCP Interoperability.](../../../../docs/framework/wcf/samples/transport-wse-3-0-tcp-interoperability.md)  
  
 Чтобы указать, что приложение WCF использует транспорт TCP, используйте [ \<>netTcpBinding. ](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)  
  
### <a name="custom-transport"></a>Пользовательский транспорт  
 Эквивалент пользовательского транспорта WSE 3.0 в WCF является расширением канала. Для получения подробной информации о создании расширения канала [см.](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)  
  
## <a name="see-also"></a>См. также раздел

- [Базовый жизненный цикл программирования](../../../../docs/framework/wcf/basic-programming-lifecycle.md)
- [Пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md)
- [Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Практическое руководства. Создание SecurityBindingElement для заданного режима проверки подлинности](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
