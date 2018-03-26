---
title: Миграция веб-служб WSE 3.0 на платформу WCF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7bc5fff7-a2b2-4dbc-86cc-ecf73653dcdc
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a7e7187eb6ed444ba2c28aa301ce4b3b16129030
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2018
---
# <a name="migrating-wse-30-web-services-to-wcf"></a>Миграция веб-служб WSE 3.0 на платформу WCF
К преимуществам переноса веб-служб WSE 3.0 на [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] относятся повышение производительности и поддержка дополнительных транспортов, дополнительных сценариев безопасности и спецификаций WS-*. При переносе веб-службы с WSE 3.0 на [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно добиться повышения производительности от 200% до 400%. Дополнительные сведения о поддерживаемых транспортов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], в разделе [выбор транспорта](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md). Список поддерживаемых сценариев [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], в разделе [типовые сценарии безопасности](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md). Список спецификаций, которые поддерживаются [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], в разделе [руководство по взаимодействию по протоколам веб служб](../../../../docs/framework/wcf/feature-details/web-services-protocols-interoperability-guide.md).  
  
 В следующих разделах приведены указания по переносу определенных функций веб-службы WSE 3.0 на [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="general"></a>Общие  
 Приложения WSE 3.0 и [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] совместимы на уровне каналов связи и используют одинаковый набор терминов. Совместимость приложений WSE 3.0 и [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] на уровне канала связи обусловлена набором спецификаций WS-*, поддерживаемых обеими средами. При разработке приложения WSE 3.0 или [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используется общий набор терминов, таких как имена готовых к использованию утверждений безопасности в WSE и режимы проверки подлинности.  
  
 Несмотря на наличие многих общих аспектов в моделях программирования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и ASP.NET или WSE 3.0 эти модели различаются. Дополнительные сведения о [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] модель программирования, в разделе [базовый жизненный цикл программирования](../../../../docs/framework/wcf/basic-programming-lifecycle.md).  
  
> [!NOTE]
>  Для переноса WSE веб-службы для WCF [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) средство можно использовать для создания клиента. Такой клиент содержит интерфейсы и классы, которые можно использовать в качестве отправной точки и для службы WCF. Созданные интерфейсы имеют атрибут <xref:System.ServiceModel.OperationContractAttribute>, применяемый ко всем членам контракта, у которых свойству <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> присвоено значение `*`. Когда WSE клиент вызывает веб-службы с этим параметром, возникает следующее исключение: **Web.Services3.ResponseProcessingException: WSE910: произошла ошибка во время обработки ответного сообщения и ошибки можно найти во внутренний исключение**. Чтобы избежать такой ситуации, присвойте свойству <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> атрибута <xref:System.ServiceModel.OperationContractAttribute> значение, отличное от `null`, например `http://Microsoft.WCF.Documentation/ResponseToOCAMethod`.  
  
## <a name="security"></a>Безопасность  
  
### <a name="wse-30-web-services-that-are-secured-using-a-policy-file"></a>Защита веб-служб WSE 3.0 обеспечивается с помощью файла политики.  
 Службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] могут использовать файл конфигурации для защиты службы. Этот механизм аналогичен использованию файла политики WSE 3.0. В WSE 3.0 при защите веб-службы с помощью файла политики используется либо готовое к использованию утверждение безопасности, либо утверждение пользовательской политики. Готовые к использованию утверждения безопасности тесно связаны с режимом проверки подлинности элемента привязки безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Режимы проверки подлинности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и готовые к использованию утверждения безопасности в WSE 3.0 не только имеют одинаковые или похожие имена, но и используют одинаковые типы учетных данных для защиты сообщений. Например, готовое к использованию утверждение безопасности `usernameForCertificate` в WSE 3.0 соответствует режиму проверки подлинности `UsernameForCertificate` в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. В следующем примере кода показано, как минимальная политика с готовым к использованию утверждением безопасности `usernameForCertificate` в WSE 3.0 сопоставляется с режимом проверки подлинности `UsernameForCertificate` в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в пользовательской привязке.  
  
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
  
 Чтобы перенести параметры безопасности веб-службы WSE 3.0, указанные в файле политики, в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], необходимо создать в файле конфигурации пользовательскую привязку и задать готовому к использованию утверждению безопасности эквивалентный режим проверки подлинности. Кроме того, необходимо настроить пользовательскую привязку для использования версии спецификации WS-Addressing от августа 2004 г. при взаимодействии клиентов WSE 3.0 с этой службой. Если перенесенная служба [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не будет взаимодействовать с клиентами WSE 3.0 и должна только обеспечить одинаковый уровень безопасности, следует рассмотреть возможность использования системных привязок [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с соответствующими параметрами безопасности вместо создания пользовательской привязки.  
  
 В следующей таблице приведено сопоставление файла политики WSE 3.0 с эквивалентными пользовательскими привязками в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
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
 При использовании WSE 3.0 и [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] требования безопасности можно задавать не только в конфигурации, но и в коде приложения. В WSE 3.0 для этого создается класс, наследуемый от класса `Policy`, и добавляются требования путем вызова метода `Add`. Дополнительные сведения об указании требования безопасности в коде см. в разделе [как: защита веб-службы без с помощью файла политики](http://go.microsoft.com/fwlink/?LinkId=73747). В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для задания требований безопасности в коде создается экземпляр класса <xref:System.ServiceModel.Channels.BindingElementCollection>, а затем экземпляр класса <xref:System.ServiceModel.Channels.SecurityBindingElement> добавляется в коллекцию <xref:System.ServiceModel.Channels.BindingElementCollection>. Требования утверждений безопасности задаются с использованием статических методов поддержки режима проверки подлинности класса <xref:System.ServiceModel.Channels.SecurityBindingElement>. Дополнительные сведения об указании требования безопасности в коде с помощью [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], в разделе [как: создайте пользовательские привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md) и [как: создание SecurityBindingElement для Указанный режим проверки подлинности](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
### <a name="wse-30-custom-policy-assertion"></a>Утверждение пользовательской политики WSE 3.0  
 В WSE 3.0 предусмотрены два типа утверждений пользовательской политики: утверждения, обеспечивающие защиту сообщения SOAP, и утверждения, не обеспечивающие защиту сообщения SOAP. Утверждения политики, обеспечивающие защиту сообщений SOAP, наследуются от класса WSE 3.0 `SecurityPolicyAssertion`, концептуальным эквивалентом в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] является класс <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
 Обратите внимание на следующий важный момент. Готовые к использованию утверждения безопасности WSE 3.0 являются подмножеством режимов проверки подлинности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. В случае создания утверждения пользовательской политики в WSE 3.0 в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может существовать эквивалентный режим проверки подлинности. Например, в WSE 3.0 отсутствует утверждение безопасности CertificateOverTransport, эквивалентное готовому к использованию утверждению безопасности `UsernameOverTransport`. Вместо этого для целей проверки подлинности клиента используется сертификат X.509. В случае определения собственного проверочного утверждения пользовательской политики для этого сценария [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] значительно упрощает процесс миграции. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] определяет режим проверки подлинности для этого сценария, что дает возможность пользоваться режимом статической проверки подлинности для настройки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
 При отсутствии режима проверки подлинности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], эквивалентного утверждению пользовательской политики для защиты сообщения SOAP, следует создать класс, наследуемый от класса <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> или <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], и задать эквивалентный элемент привязки. Дополнительные сведения см. в разделе [как: создайте пользовательские привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
 Чтобы преобразовать утверждение пользовательской политики, который не обеспечивает безопасность сообщений SOAP, в разделе [фильтрация](../../../../docs/framework/wcf/feature-details/filtering.md) и образец [пользовательский перехватчик сообщений](../../../../docs/framework/wcf/samples/custom-message-interceptor.md).  
  
### <a name="wse-30-custom-security-token"></a>Пользовательский маркер безопасности WSE 3.0  
 Модель программирования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для создания пользовательского маркера отлична от модели WSE 3.0. Дополнительные сведения о создании пользовательского маркера в WSE см. в разделе [Создание пользовательских маркеров безопасности](http://go.microsoft.com/fwlink/?LinkID=73750). Дополнительные сведения о создании пользовательского маркера в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], в разделе [как: Создание пользовательского токена](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
### <a name="wse-30-custom-token-manager"></a>Пользовательский диспетчер маркеров WSE 3.0  
 Модель программирования для создания пользовательского диспетчера маркеров в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отлична от модели WSE 3.0. Дополнительные сведения о создании пользовательского диспетчера маркеров и другие компоненты, необходимые для создания пользовательского маркера безопасности см. в разделе [как: Создание пользовательского токена](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
> [!NOTE]
>  В случае создания пользовательского диспетчера маркеров безопасности `UsernameToken` в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предусмотрен более простой механизм задания логики проверки подлинности, чем создание пользовательского диспетчера маркеров безопасности. Дополнительные сведения см. в разделе [как: использовать пользовательское имя пользователя и пароль проверки](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md).  
  
### <a name="wse-30-web-services-that-use-mtom-encoded-soap-messages"></a>Веб-службы WSE 3.0, использующие сообщения SOAP с кодировкой MTOM  
 Приложение [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], также как и приложение WSE 3, может задавать кодирование сообщений MTOM в конфигурации. Чтобы перенести этот параметр, добавьте [ \<mtomMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/mtommessageencoding.md) привязку для службы. В следующем примере кода показано задание кодировки MTOM в WSE 3.0 для службы, имеющей эквивалент в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
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
 По умолчанию клиенты и веб-службы WSE 3.0, отправляющие сообщения SOAP с использованием транспорта TCP, не могут взаимодействовать с клиентами и веб-службами [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Эта несовместимость обусловлена различиями в кадрировании в протоколе TCP и причинами, связанными с обеспечением производительности. Однако в образце [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] показано, как реализовать пользовательский сеанс TCP, который может взаимодействовать с WSE 3.0. Дополнительные сведения об этом образце см. в разделе [транспорт: TCP-взаимодействие WSE 3.0](../../../../docs/framework/wcf/samples/transport-wse-3-0-tcp-interoperability.md).  
  
 Чтобы указать, что [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] приложение использует протокол TCP, используйте [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
### <a name="custom-transport"></a>Пользовательский транспорт  
 Эквивалентом пользовательского транспорта WSE 3.0 в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] является расширение канала. Сведения о создании расширение канала см. в разделе [расширение уровня каналов](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
## <a name="see-also"></a>См. также  
 [Базовый жизненный цикл программирования](../../../../docs/framework/wcf/basic-programming-lifecycle.md)  
 [Пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [Практическое руководство. Создание SecurityBindingElement для заданного режима проверки подлинности](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
