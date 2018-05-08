---
title: Миграция веб-служб WSE 3.0 на платформу WCF
ms.date: 03/30/2017
ms.assetid: 7bc5fff7-a2b2-4dbc-86cc-ecf73653dcdc
ms.openlocfilehash: fea56d5737b47dabd5632477b7daed23fcfaf249
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="migrating-wse-30-web-services-to-wcf"></a>Миграция веб-служб WSE 3.0 на платформу WCF
Преимущества миграции WSE 3.0 веб-служб для Windows Communication Foundation (WCF) относятся повышение производительности и поддержка дополнительных транспортов, дополнительных сценариев безопасности и WS-* спецификации. Веб-служба, которая переносится с WSE 3.0 на платформу WCF можно добиться более высокую производительность 200% до 400%. Дополнительные сведения о службах, поддерживаемого службами WCF см. в разделе [выбор транспорта](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md). Список сценариев, поддерживаемого службами WCF см. в разделе [типовые сценарии безопасности](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md). Список спецификаций, поддерживаемых в WCF см. в разделе [руководство по взаимодействию по протоколам веб служб](../../../../docs/framework/wcf/feature-details/web-services-protocols-interoperability-guide.md).  
  
 Ниже приведены рекомендации по переносу определенных функций веб-WSE 3.0 службы для WCF.  
  
## <a name="general"></a>Общие  
 Приложения WSE 3.0 и WCF включают взаимодействие транспортного уровня и общий набор терминов. Приложения WSE 3.0 и WCF, транспортного уровня с возможностью взаимодействия на основе набора WS-* спецификации, которые они поддерживают. При разработке приложения WSE 3.0 или WCF имеется общий набор терминов, таких как имена готовые утверждения безопасности в WSE и режимы проверки подлинности.  
  
 Несмотря на то, что существует множество общих аспектов WCF и ASP.NET или WSE 3.0, модели программирования, они отличаются. Дополнительные сведения о модели программирования WCF см. в разделе [базовый жизненный цикл программирования](../../../../docs/framework/wcf/basic-programming-lifecycle.md).  
  
> [!NOTE]
>  Для переноса WSE веб-службы для WCF [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) средство можно использовать для создания клиента. Такой клиент содержит интерфейсы и классы, которые можно использовать в качестве отправной точки и для службы WCF. Созданные интерфейсы имеют атрибут <xref:System.ServiceModel.OperationContractAttribute>, применяемый ко всем членам контракта, у которых свойству <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> присвоено значение `*`. Когда WSE клиент вызывает веб-службы с этим параметром, возникает следующее исключение: **Web.Services3.ResponseProcessingException: WSE910: произошла ошибка во время обработки ответного сообщения и ошибки можно найти во внутренний исключение**. Чтобы избежать такой ситуации, присвойте свойству <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> атрибута <xref:System.ServiceModel.OperationContractAttribute> значение, отличное от `null`, например `http://Microsoft.WCF.Documentation/ResponseToOCAMethod`.  
  
## <a name="security"></a>Безопасность  
  
### <a name="wse-30-web-services-that-are-secured-using-a-policy-file"></a>Защита веб-служб WSE 3.0 обеспечивается с помощью файла политики.  
 Службы WCF можно использовать файл конфигурации для защиты службы, и этот механизм аналогичен файла политики WSE 3.0. В WSE 3.0 при защите веб-службы с помощью файла политики используется либо готовое к использованию утверждение безопасности, либо утверждение пользовательской политики. Готовые утверждения безопасности тесно связаны с режимом проверки подлинности элемента привязки безопасности WCF. Не только являются режимов проверки подлинности WCF и утверждения WSE 3.0 готовое к использованию безопасности с именем или аналогичным образом, они защиты сообщений, используя те же типы учетных данных. Например `usernameForCertificate` использованию утверждением безопасности в WSE 3.0 сопоставляется `UsernameForCertificate` режим проверки подлинности в WCF. В следующем примере кода показано, как минимальная политика с использует `usernameForCertificate` использованию утверждением безопасности в WSE 3.0 сопоставляется `UsernameForCertificate` режим проверки подлинности в WCF в пользовательскую привязку.  
  
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
  
 Чтобы перенести параметры безопасности WSE 3.0 веб-службы, указанные в файле политики, в WCF, необходимо создать пользовательскую привязку в файле конфигурации и использованию утверждением безопасности должно быть присвоено его эквивалентный режим проверки подлинности. Кроме того, необходимо настроить пользовательскую привязку для использования версии спецификации WS-Addressing от августа 2004 г. при взаимодействии клиентов WSE 3.0 с этой службой. При миграции службы WCF не требует взаимодействия с клиентами WSE 3.0 и должна только обеспечить одинаковый уровень безопасности, рассмотрите возможность использования системных привязок WCF с соответствующими параметрами безопасности вместо создания пользовательской привязки.  
  
 В следующей таблице перечислены сопоставление файла политики WSE 3.0 и эквивалентные пользовательскую привязку в WCF.  
  
|Готовое к использованию утверждение безопасности WSE 3.0|Конфигурация пользовательской привязки WCF|  
|----------------------------------------|--------------------------------------|  
|\<usernameOverTransportSecurity / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UserNameOverTransport" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate10Security / >|`<customBinding>   <binding name="MyBinding">     <security messageSecurityVersion="WSSecurity10WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10" authenticationMode="MutualCertificate" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<usernameForCertificateSecurity / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UsernameForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<anonymousForCertificateSecurity / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="AnonymousForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<kerberosSecurity / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="Kerberos"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate11Security / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="MutualCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
  
 Дополнительные сведения о создании настраиваемых привязок в WCF см. в разделе [пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
### <a name="wse-30-web-services-that-are-secured-using-application-code"></a>Веб-службы WSE 3.0, защищаемые с использованием кода приложения  
 Используемый WSE 3.0 или WCF, требования безопасности можно указать в коде приложения, а не в конфигурации. В WSE 3.0 для этого создается класс, наследуемый от класса `Policy`, и добавляются требования путем вызова метода `Add`. Дополнительные сведения об указании требования безопасности в коде см. в разделе [как: защита веб-службы без с помощью файла политики](http://go.microsoft.com/fwlink/?LinkId=73747). В WCF, чтобы указать требования к безопасности в коде, создать экземпляр <xref:System.ServiceModel.Channels.BindingElementCollection> класса и добавить экземпляр <xref:System.ServiceModel.Channels.SecurityBindingElement> для <xref:System.ServiceModel.Channels.BindingElementCollection>. Требования утверждений безопасности задаются с использованием статических методов поддержки режима проверки подлинности класса <xref:System.ServiceModel.Channels.SecurityBindingElement>. Дополнительные сведения об указании требования безопасности в коде с помощью WCF см. в разделе [как: создайте пользовательские привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md) и [как: создание SecurityBindingElement для указанного Режим проверки подлинности](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
### <a name="wse-30-custom-policy-assertion"></a>Утверждение пользовательской политики WSE 3.0  
 В WSE 3.0 предусмотрены два типа утверждений пользовательской политики: утверждения, обеспечивающие защиту сообщения SOAP, и утверждения, не обеспечивающие защиту сообщения SOAP. Утверждения политики, обеспечивающие защиту сообщений SOAP, являются производными от WSE 3.0 `SecurityPolicyAssertion` класса, концептуальным эквивалентом в WCF является <xref:System.ServiceModel.Channels.SecurityBindingElement> класса.  
  
 Важно отметить является то, что утверждения готовое к использованию безопасности WSE 3.0 являются подмножеством режимов проверки подлинности WCF. Если вы создали утверждение пользовательской политики в WSE 3.0, могут существовать эквивалентный режим проверки подлинности WCF. Например, в WSE 3.0 отсутствует утверждение безопасности CertificateOverTransport, эквивалентное готовому к использованию утверждению безопасности `UsernameOverTransport`. Вместо этого для целей проверки подлинности клиента используется сертификат X.509. Если вы определили утверждения пользовательской политики для этого сценария, WCF упрощает процедуру миграции. WCF определяет режим проверки подлинности для этого сценария, поэтому вы сможете использовать проверки подлинности статических методов поддержки режима для настройки WCF<xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
 Если не режим проверки подлинности WCF, которое эквивалентно значению утверждение пользовательской политики, обеспечивающий безопасность сообщений SOAP, создайте класс, производный от <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> или <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>WCF классов и укажите элемент эквивалентные привязки. Дополнительные сведения см. в разделе [как: создайте пользовательские привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
 Чтобы преобразовать утверждение пользовательской политики, который не обеспечивает безопасность сообщений SOAP, в разделе [фильтрация](../../../../docs/framework/wcf/feature-details/filtering.md) и образец [пользовательский перехватчик сообщений](../../../../docs/framework/wcf/samples/custom-message-interceptor.md).  
  
### <a name="wse-30-custom-security-token"></a>Пользовательский маркер безопасности WSE 3.0  
 Модель программирования WCF для создания пользовательского маркера отлична от WSE 3.0. Дополнительные сведения о создании пользовательского маркера в WSE см. в разделе [Создание пользовательских маркеров безопасности](http://go.microsoft.com/fwlink/?LinkID=73750). Дополнительные сведения о создании пользовательского маркера в WCF см. в разделе [как: Создание пользовательского токена](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
### <a name="wse-30-custom-token-manager"></a>Пользовательский диспетчер маркеров WSE 3.0  
 Модель программирования для создания пользовательского диспетчера маркеров отличается в WCF WSE 3.0. Дополнительные сведения о создании пользовательского диспетчера маркеров и другие компоненты, необходимые для создания пользовательского маркера безопасности см. в разделе [как: Создание пользовательского токена](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
> [!NOTE]
>  Если вы создали пользовательский `UsernameToken` диспетчера маркеров безопасности WCF предоставляет простой механизм задания логики проверки подлинности, чем создание диспетчер маркеров безопасности. Дополнительные сведения см. в разделе [как: использовать пользовательское имя пользователя и пароль проверки](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md).  
  
### <a name="wse-30-web-services-that-use-mtom-encoded-soap-messages"></a>Веб-службы WSE 3.0, использующие сообщения SOAP с кодировкой MTOM  
 Как приложение WSE 3 приложения WCF можно указать в конфигурации кодирование сообщений MTOM. Чтобы перенести этот параметр, добавьте [ \<mtomMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/mtommessageencoding.md) привязку для службы. В следующем примере кода показано, как кодирование MTOM указывается в WSE 3.0 для службы, имеющей эквивалент в WCF.  
  
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
 Если для прямого доступа к данным XML, передаваемым между клиентами и веб-службами, используется API обмена сообщениями WSE, приложение можно преобразовать для использования POX (Plain Old XML). Дополнительные сведения о POX см. в разделе [взаимодействие с приложениями POX](../../../../docs/framework/wcf/feature-details/interoperability-with-pox-applications.md). Дополнительные сведения об API обмена сообщениями WSE см. в разделе [отправка и получение SOAP сообщения с помощью API обмена сообщениями WSE](http://go.microsoft.com/fwlink/?LinkID=73755).  
  
## <a name="transports"></a>Транспорты  
  
### <a name="tcp"></a>TCP  
 По умолчанию клиентами WSE 3.0 и веб-служб, отправляющие сообщения SOAP с помощью транспорта TCP не могут взаимодействовать с клиентами WCF и веб-служб. Эта несовместимость обусловлена различиями в кадрировании в протоколе TCP и причинами, связанными с обеспечением производительности. Тем не менее образец WCF подробно описано, как реализовать пользовательский сеанс TCP, который может взаимодействовать с WSE 3.0. Дополнительные сведения об этом образце см. в разделе [транспорт: TCP-взаимодействие WSE 3.0](../../../../docs/framework/wcf/samples/transport-wse-3-0-tcp-interoperability.md).  
  
 Чтобы указать, что приложения WCF использует протокол TCP, используйте [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
### <a name="custom-transport"></a>Пользовательский транспорт  
 Эквивалентом пользовательского транспорта WSE 3.0 в WCF является расширение канала. Сведения о создании расширение канала см. в разделе [расширение уровня каналов](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
## <a name="see-also"></a>См. также  
 [Базовый жизненный цикл программирования](../../../../docs/framework/wcf/basic-programming-lifecycle.md)  
 [Пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [Практическое руководство. Создание SecurityBindingElement для заданного режима проверки подлинности](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
