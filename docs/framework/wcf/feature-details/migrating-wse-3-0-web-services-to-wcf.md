---
title: "Миграция веб-служб WSE 3.0 на платформу WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7bc5fff7-a2b2-4dbc-86cc-ecf73653dcdc
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Миграция веб-служб WSE 3.0 на платформу WCF
К преимуществам переноса веб-служб WSE 3.0 на [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] относятся повышение производительности и поддержка дополнительных транспортов, дополнительных сценариев безопасности и спецификаций WS-*. При переносе веб-службы с WSE 3.0 на [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно добиться повышения производительности от 200% до 400%. Дополнительные сведения о поддерживаемых транспортов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], в разделе [выбор транспорта](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md). Список сценариев, поддерживаемых [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], в разделе [типовые сценарии безопасности](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md). Список спецификаций, поддерживаемых [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], в разделе [руководство по взаимодействию по протоколам веб службы](../../../../docs/framework/wcf/feature-details/web-services-protocols-interoperability-guide.md).  
  
 В следующих разделах приведены указания по переносу определенных функций веб-службы WSE 3.0 на [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="general"></a>Общие  
 Приложения WSE 3.0 и [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] совместимы на уровне каналов связи и используют одинаковый набор терминов. Совместимость приложений WSE 3.0 и [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] на уровне канала связи обусловлена набором спецификаций WS-*, поддерживаемых обеими средами. При разработке приложения WSE 3.0 или [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используется общий набор терминов, таких как имена готовых к использованию утверждений безопасности в WSE и режимы проверки подлинности.  
  
 Несмотря на наличие многих общих аспектов в моделях программирования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и ASP.NET или WSE 3.0 эти модели различаются. Дополнительные сведения о [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] модель программирования, в разделе [базовый жизненный цикл программирования](../../../../docs/framework/wcf/basic-programming-lifecycle.md).  
  
> [!NOTE]
>  Для переноса WSE веб-службы для WCF [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) средство можно использовать для создания клиента. Такой клиент содержит интерфейсы и классы, которые можно использовать в качестве отправной точки и для службы WCF. Созданные интерфейсы имеют <xref:System.ServiceModel.OperationContractAttribute> атрибут, применяемый ко всем членам контракта с <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> свойству `*`. Когда клиент WSE вызывает веб-службы с помощью этого параметра, следующее исключение: **Web.Services3.ResponseProcessingException: WSE910: произошла ошибка во время обработки ответного сообщения и ошибки можно найти в внутреннее исключение**. Чтобы обойти эту проблему, установите <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> свойство <xref:System.ServiceModel.OperationContractAttribute> атрибута не-`null` значения, такие как `http://Microsoft.WCF.Documentation/ResponseToOCAMethod`.  
  
## <a name="security"></a>Безопасность  
  
### <a name="wse-30-web-services-that-are-secured-using-a-policy-file"></a>Защита веб-служб WSE 3.0 обеспечивается с помощью файла политики.  
 Службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] могут использовать файл конфигурации для защиты службы. Этот механизм аналогичен использованию файла политики WSE 3.0. В WSE 3.0 при защите веб-службы с помощью файла политики используется либо готовое к использованию утверждение безопасности, либо утверждение пользовательской политики. Готовые к использованию утверждения безопасности тесно связаны с режимом проверки подлинности элемента привязки безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Режимы проверки подлинности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и готовые к использованию утверждения безопасности в WSE 3.0 не только имеют одинаковые или похожие имена, но и используют одинаковые типы учетных данных для защиты сообщений. Например, готовое к использованию утверждение безопасности `usernameForCertificate` в WSE 3.0 соответствует режиму проверки подлинности `UsernameForCertificate` в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. В следующем примере кода показано, как минимальная политика с готовым к использованию утверждением безопасности `usernameForCertificate` в WSE 3.0 сопоставляется с режимом проверки подлинности `UsernameForCertificate` в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в пользовательской привязке.  
  
 **WSE 3.0**  
  
```  
<policies>  
  <policy name="MyPolicy">  
    <usernameForCertificate messageProtectionOrder="SignBeforeEncrypt"  
                            requireDeriveKeys="true"/>  
  </policy>  
</policies>  
```  
  
 **WCF**  
  
```  
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
|<usernameOverTransportSecurity></usernameOverTransportSecurity>\>|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UserNameOverTransport" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|<mutualCertificate10Security></mutualCertificate10Security>\>|`<customBinding>   <binding name="MyBinding">     <security messageSecurityVersion="WSSecurity10WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10" authenticationMode="MutualCertificate" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|<usernameForCertificateSecurity></usernameForCertificateSecurity>\>|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UsernameForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|<anonymousForCertificateSecurity></anonymousForCertificateSecurity>\>|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="AnonymousForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|<kerberosSecurity></kerberosSecurity>\>|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="Kerberos"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|<mutualCertificate11Security></mutualCertificate11Security>\>|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="MutualCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
  
 Дополнительные сведения о создании пользовательских привязок в WCF см. в разделе [пользовательских привязок](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
### <a name="wse-30-web-services-that-are-secured-using-application-code"></a>Веб-службы WSE 3.0, защищаемые с использованием кода приложения  
 При использовании WSE 3.0 и [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] требования безопасности можно задавать не только в конфигурации, но и в коде приложения. В WSE 3.0 для этого создается класс, наследуемый от класса `Policy`, и добавляются требования путем вызова метода `Add`. Дополнительные сведения о задании требований безопасности в коде см. в разделе [как: безопасность веб-службы без, используя файл политики](http://go.microsoft.com/fwlink/?LinkId=73747). В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]для задания требований безопасности в коде создается экземпляр <xref:System.ServiceModel.Channels.BindingElementCollection> и добавьте экземпляр <xref:System.ServiceModel.Channels.SecurityBindingElement> для <xref:System.ServiceModel.Channels.BindingElementCollection>. Требования утверждений безопасности задаются с помощью статической проверки подлинности методов поддержки режима <xref:System.ServiceModel.Channels.SecurityBindingElement> класса. Дополнительные сведения о задании требований безопасности в коде с помощью [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], в разделе [как: создайте пользовательские привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md) и [Практическое руководство: создание SecurityBindingElement для указанного режима проверки подлинности](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
### <a name="wse-30-custom-policy-assertion"></a>Утверждение пользовательской политики WSE 3.0  
 В WSE 3.0 предусмотрены два типа утверждений пользовательской политики: утверждения, обеспечивающие защиту сообщения SOAP, и утверждения, не обеспечивающие защиту сообщения SOAP. Утверждения политики, обеспечивающие защиту сообщений SOAP, наследуются от WSE 3.0 `SecurityPolicyAssertion` класс и концептуальным эквивалентом в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] — <xref:System.ServiceModel.Channels.SecurityBindingElement> класса.  
  
 Обратите внимание на следующий важный момент. Готовые к использованию утверждения безопасности WSE 3.0 являются подмножеством режимов проверки подлинности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. В случае создания утверждения пользовательской политики в WSE 3.0 в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может существовать эквивалентный режим проверки подлинности. Например, в WSE 3.0 отсутствует утверждение безопасности CertificateOverTransport, эквивалентное готовому к использованию утверждению безопасности `UsernameOverTransport`. Вместо этого для целей проверки подлинности клиента используется сертификат X.509. В случае определения собственного проверочного утверждения пользовательской политики для этого сценария [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] значительно упрощает процесс миграции. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]Определяет режим проверки подлинности для этого сценария, можно воспользоваться преимуществами режим проверки подлинности статические вспомогательные методы для настройки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
 Если не [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] режим проверки подлинности, эквивалентное утверждение пользовательской политики защиты сообщения SOAP, наследуйте класс от <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> или <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и задать эквивалентный элемент привязки. Дополнительные сведения см. в разделе [как: создайте пользовательские привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
 Чтобы преобразовать утверждение пользовательской политики, который не обеспечивает безопасность сообщений SOAP, в разделе [фильтрация](../../../../docs/framework/wcf/feature-details/filtering.md) и образец [пользовательский перехватчик сообщений](../../../../docs/framework/wcf/samples/custom-message-interceptor.md).  
  
### <a name="wse-30-custom-security-token"></a>Пользовательский маркер безопасности WSE 3.0  
 Модель программирования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для создания пользовательского маркера отлична от модели WSE 3.0. Дополнительные сведения о создании пользовательского маркера в WSE см. в разделе [Создание пользовательских маркеров безопасности](http://go.microsoft.com/fwlink/?LinkID=73750). Подробные сведения о создании пользовательского маркера в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], в разделе [Практическое руководство: Создание пользовательского токена](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
### <a name="wse-30-custom-token-manager"></a>Пользовательский диспетчер маркеров WSE 3.0  
 Модель программирования для создания пользовательского диспетчера маркеров в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отлична от модели WSE 3.0. Дополнительные сведения о создании пользовательского диспетчера маркеров и другие компоненты, необходимые для пользовательского маркера безопасности см. в разделе [Практическое руководство: Создание пользовательского токена](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
> [!NOTE]
>  В случае создания пользовательского диспетчера маркеров безопасности `UsernameToken` в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предусмотрен более простой механизм задания логики проверки подлинности, чем создание пользовательского диспетчера маркеров безопасности. Дополнительные сведения см. в разделе [Практическое руководство: использование пользовательского имени пользователя и пароля проверяющий элемент управления](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md).  
  
### <a name="wse-30-web-services-that-use-mtom-encoded-soap-messages"></a>Веб-службы WSE 3.0, использующие сообщения SOAP с кодировкой MTOM  
 Приложение [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], также как и приложение WSE 3, может задавать кодирование сообщений MTOM в конфигурации. Чтобы перенести этот параметр, добавьте [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/mtommessageencoding.md) привязку для службы. В следующем примере кода показано задание кодировки MTOM в WSE 3.0 для службы, имеющей эквивалент в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 **WSE 3.0**  
  
```  
<messaging>  
    <mtom clientMode="On"/>  
</messaging>  
```  
  
 **WCF**  
  
```  
<customBinding>  
  <binding name="MyBinding">  
    <mtomMessageEncoding/>  
  </binding>  
</customBinding>  
```  
  
## <a name="messaging"></a>Обмен сообщениями  
  
### <a name="wse-30-applications-that-use-the-wse-messaging-api"></a>Приложения WSE 3.0, использующие API обмена сообщениями WSE  
 Если для прямого доступа к данным XML, передаваемым между клиентами и веб-службами, используется API обмена сообщениями WSE, приложение можно преобразовать для использования POX (Plain Old XML). Дополнительные сведения о POX см. в разделе [взаимодействие с приложениями POX](../../../../docs/framework/wcf/feature-details/interoperability-with-pox-applications.md). Дополнительные сведения о API обмена сообщениями WSE см. в разделе [отправка и получение сообщений с помощью WSE Messaging API-Интерфейс SOAP](http://go.microsoft.com/fwlink/?LinkID=73755).  
  
## <a name="transports"></a>Транспорты  
  
### <a name="tcp"></a>TCP  
 По умолчанию клиенты и веб-службы WSE 3.0, отправляющие сообщения SOAP с использованием транспорта TCP, не могут взаимодействовать с клиентами и веб-службами [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Эта несовместимость обусловлена различиями в кадрировании в протоколе TCP и причинами, связанными с обеспечением производительности. Однако в образце [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] показано, как реализовать пользовательский сеанс TCP, который может взаимодействовать с WSE 3.0. Дополнительные сведения об этом образце см. в разделе [транспорт: TCP-взаимодействие WSE 3.0](../../../../docs/framework/wcf/samples/transport-wse-3-0-tcp-interoperability.md).  
  
 Чтобы указать, что [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] приложение использует протокол TCP, используйте [ <> \</> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
### <a name="custom-transport"></a>Пользовательский транспорт  
 Эквивалентом пользовательского транспорта WSE 3.0 в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] является расширение канала. Дополнительные сведения о создании расширения канала см [расширение уровня каналов](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
## <a name="see-also"></a>См. также  
 [Базовый жизненный цикл программирования](../../../../docs/framework/wcf/basic-programming-lifecycle.md)   
 [Пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [Практическое руководство: Создание пользовательской привязки, с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)   
 [Практическое руководство: создание SecurityBindingElement для заданного режима проверки подлинности](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)