---
title: Миграция веб-служб WSE 3.0 на платформу WCF
ms.date: 03/30/2017
ms.assetid: 7bc5fff7-a2b2-4dbc-86cc-ecf73653dcdc
ms.openlocfilehash: 50939253027ff82a256b9627305c26fb69e13be9
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212150"
---
# <a name="migrating-wse-30-web-services-to-wcf"></a>Миграция веб-служб WSE 3.0 на платформу WCF
Преимущества миграции веб-служб WSE 3,0 на Windows Communication Foundation (WCF) включают улучшенную производительность и поддержку дополнительных транспортов, дополнительных сценариев безопасности и спецификаций WS-*. Веб-служба, перенесенная из WSE 3,0 в WCF, может работать с повышением производительности до 200% до 400%. Дополнительные сведения о транспортах, поддерживаемых WCF, см. [в разделе Выбор транспорта](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md). Список сценариев, поддерживаемых WCF, см. в разделе [Общие сценарии безопасности](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md). Список спецификаций, поддерживаемых WCF, см. в разделе [Guide взаимодействие протоколов веб-служб](../../../../docs/framework/wcf/feature-details/web-services-protocols-interoperability-guide.md).  
  
 В следующих разделах приведены рекомендации по переносу определенной функции веб-службы WSE 3,0 в WCF.  
  
## <a name="general"></a>Общие  
 Приложения WSE 3,0 и WCF включают взаимодействие на уровне сети и общий набор терминологии. Приложения WSE 3,0 и WCF поддерживают взаимодействие на уровне сети на основе набора спецификаций WS-*, которые они поддерживают. При разработке приложения WSE 3,0 или WCF существует общий набор терминов, таких как имена готовых утверждений безопасности в WSE и режимы проверки подлинности.  
  
 Несмотря на множество схожих аспектов между моделями программирования WCF и ASP.NET или WSE 3,0, они отличаются. Дополнительные сведения о модели программирования WCF см. в разделе [Базовый жизненный цикл программирования](../../../../docs/framework/wcf/basic-programming-lifecycle.md).  
  
> [!NOTE]
> Чтобы перенести веб-службу WSE в WCF, можно использовать средство [служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания клиента. Такой клиент содержит интерфейсы и классы, которые можно использовать в качестве отправной точки и для службы WCF. Созданные интерфейсы имеют атрибут <xref:System.ServiceModel.OperationContractAttribute>, применяемый ко всем членам контракта, у которых свойству <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> присвоено значение `*`. Когда клиент WSE вызывает веб-службу с этим параметром, возникает следующее исключение: **Web. Services3. респонсепроцессинжексцептион: WSE910: во время обработки ответного сообщения произошла ошибка, и ошибку можно найти во внутреннем исключении**. Чтобы избежать такой ситуации, присвойте свойству <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> атрибута <xref:System.ServiceModel.OperationContractAttribute> значение, отличное от `null`, например `http://Microsoft.WCF.Documentation/ResponseToOCAMethod`.  
  
## <a name="security"></a>по безопасности  
  
### <a name="wse-30-web-services-that-are-secured-using-a-policy-file"></a>Защита веб-служб WSE 3.0 обеспечивается с помощью файла политики.  
 Службы WCF могут использовать файл конфигурации для защиты службы, и этот механизм аналогичен файлу политики WSE 3,0. В WSE 3.0 при защите веб-службы с помощью файла политики используется либо готовое к использованию утверждение безопасности, либо утверждение пользовательской политики. Готовые утверждения безопасности соответствуют режиму проверки подлинности элемента привязки безопасности WCF. Не только режимы проверки подлинности WCF и готовые утверждения безопасности WSE 3,0 с одинаковыми или аналогичными, они защищают сообщения с использованием одних и тех же типов учетных данных. Например, `usernameForCertificate` готового утверждения безопасности в WSE 3,0 сопоставляется с режимом проверки подлинности `UsernameForCertificate` в WCF. В следующих примерах кода показано, как минимальная политика, использующая `usernameForCertificate` готового утверждения безопасности в WSE 3,0, сопоставляется с `UsernameForCertificate`ным режимом проверки подлинности в WCF в пользовательской привязке.  
  
 **WSE 3,0**  
  
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
  
 Чтобы перенести параметры безопасности веб-службы WSE 3,0, указанные в файле политики в WCF, необходимо создать пользовательскую привязку в файле конфигурации, а в качестве утвержденного утверждения безопасности должен быть указан соответствующий режим проверки подлинности. Кроме того, необходимо настроить пользовательскую привязку для использования версии спецификации WS-Addressing от августа 2004 г. при взаимодействии клиентов WSE 3.0 с этой службой. Если перенесенная служба WCF не требует взаимодействия с клиентами WSE 3,0 и должна поддерживать только четность безопасности, рекомендуется использовать системные привязки WCF с соответствующими параметрами безопасности вместо создания пользовательской привязки.  
  
 В следующей таблице перечислены сопоставления между файлом политики WSE 3,0 и эквивалентной пользовательской привязкой в WCF.  
  
|Готовое к использованию утверждение безопасности WSE 3.0|Конфигурация пользовательской привязки WCF|  
|----------------------------------------|--------------------------------------|  
|\<Усернамеовертранспортсекурити/>|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UserNameOverTransport" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate10Security/>|`<customBinding>   <binding name="MyBinding">     <security messageSecurityVersion="WSSecurity10WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10" authenticationMode="MutualCertificate" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<Усернамефорцертификатесекурити/>|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UsernameForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<Анонимаусфорцертификатесекурити/>|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="AnonymousForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<Кербероссекурити/>|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="Kerberos"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate11Security/>|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="MutualCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
  
 Дополнительные сведения о создании пользовательских привязок в WCF см. в разделе [пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
### <a name="wse-30-web-services-that-are-secured-using-application-code"></a>Веб-службы WSE 3.0, защищаемые с использованием кода приложения  
 Независимо от того, используется ли WSE 3,0 или WCF, требования безопасности могут быть указаны в коде приложения, а не в конфигурации. В WSE 3.0 для этого создается класс, наследуемый от класса `Policy`, и добавляются требования путем вызова метода `Add`. Дополнительные сведения об указании требований безопасности в коде см. в разделе [как защитить веб-службу без использования файла политики](https://docs.microsoft.com/previous-versions/dotnet/netframework-2.0/aa528763(v=msdn.10)). В WCF, чтобы указать требования к безопасности в коде, создайте экземпляр класса <xref:System.ServiceModel.Channels.BindingElementCollection> и добавьте в <xref:System.ServiceModel.Channels.BindingElementCollection>экземпляр <xref:System.ServiceModel.Channels.SecurityBindingElement>. Требования утверждений безопасности задаются с использованием статических методов поддержки режима проверки подлинности класса <xref:System.ServiceModel.Channels.SecurityBindingElement>. Дополнительные сведения об указании требований безопасности в коде с помощью WCF см. в разделе [Создание пользовательской привязки с помощью SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md) и [инструкции. Создание SecurityBindingElement для указанного режима проверки подлинности](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
### <a name="wse-30-custom-policy-assertion"></a>Утверждение пользовательской политики WSE 3.0  
 В WSE 3.0 предусмотрены два типа утверждений пользовательской политики: утверждения, обеспечивающие защиту сообщения SOAP, и утверждения, не обеспечивающие защиту сообщения SOAP. Утверждения политики, которые защищают сообщения SOAP от класса WSE 3,0 `SecurityPolicyAssertion`, а концептуальный эквивалент в WCF — это класс <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
 Важно отметить, что утвержденные утверждения для безопасного использования WSE 3,0 являются подмножеством режимов проверки подлинности WCF. Если вы создали утверждение пользовательской политики в WSE 3,0, возможно, существует эквивалентный режим проверки подлинности WCF. Например, в WSE 3.0 отсутствует утверждение безопасности CertificateOverTransport, эквивалентное готовому к использованию утверждению безопасности `UsernameOverTransport`. Вместо этого для целей проверки подлинности клиента используется сертификат X.509. Если для этого сценария определено собственное утверждение пользовательской политики, то WCF упрощает миграцию. WCF определяет режим проверки подлинности для этого сценария, поэтому для настройки<xref:System.ServiceModel.Channels.SecurityBindingElement>WCF можно воспользоваться преимуществами вспомогательных методов режима статической проверки подлинности.  
  
 Если отсутствует режим проверки подлинности WCF, эквивалентный утверждению настраиваемой политики, который защищает сообщения SOAP, следует наследовать класс от <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> или <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>классов WCF и указать эквивалентный элемент привязки. Дополнительные сведения см. в разделе [инструкции. Создание пользовательской привязки с помощью SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
 Чтобы преобразовать утверждение пользовательской политики, которое не защищает сообщение SOAP, см. раздел [Фильтрация](../../../../docs/framework/wcf/feature-details/filtering.md) и пример [пользовательского перехватчика сообщений](../../../../docs/framework/wcf/samples/custom-message-interceptor.md).  
  
### <a name="wse-30-custom-security-token"></a>Пользовательский маркер безопасности WSE 3.0  
 Модель программирования WCF для создания пользовательского маркера отличается от WSE 3,0. Дополнительные сведения о создании пользовательского токена в WSE см. в разделе [Создание настраиваемых маркеров безопасности](https://docs.microsoft.com/previous-versions/dotnet/netframework-2.0/aa529304(v=msdn.10)). Дополнительные сведения о создании пользовательского токена в WCF см. в разделе [как создать настраиваемый токен](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
### <a name="wse-30-custom-token-manager"></a>Пользовательский диспетчер маркеров WSE 3.0  
 Модель программирования для создания пользовательского диспетчера маркеров отличается от модели WCF, отличной от WSE 3,0. Дополнительные сведения о создании настраиваемого диспетчера маркеров и других компонентов, необходимых для настраиваемого маркера безопасности, см. в разделе [как создать настраиваемый токен](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
> [!NOTE]
> Если вы создали пользовательский `UsernameToken` диспетчера маркеров безопасности, WCF предоставляет более простой механизм для указания логики проверки подлинности, чем создание пользовательского диспетчера маркеров безопасности. Дополнительные сведения см. в разделе [как использовать настраиваемое средство проверки имени пользователя и пароля](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md).  
  
### <a name="wse-30-web-services-that-use-mtom-encoded-soap-messages"></a>Веб-службы WSE 3.0, использующие сообщения SOAP с кодировкой MTOM  
 Как и приложение WSE 3, приложение WCF может задавать кодировку сообщений MTOM в конфигурации. Чтобы перенести этот параметр, добавьте [\<мтоммессажеенкодинг >](../../../../docs/framework/configure-apps/file-schema/wcf/mtommessageencoding.md) в привязку для службы. В следующем примере кода показано, как задается кодировка MTOM в WSE 3,0 для службы, которая эквивалентна в WCF.  
  
 **WSE 3,0**  
  
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

 Если для прямого доступа к данным XML, передаваемым между клиентами и веб-службами, используется API обмена сообщениями WSE, приложение можно преобразовать для использования POX (Plain Old XML). Дополнительные сведения о POX см. [в статье взаимодействие с приложениями POX](interoperability-with-pox-applications.md). Дополнительные сведения об API обмена сообщениями WSE см. в разделе [Отправка и получение сообщений SOAP с помощью API обмена сообщениями WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-2.0/aa529293(v=msdn.10)).  
  
## <a name="transports"></a>Транспорты  
  
### <a name="tcp"></a>TCP  
 По умолчанию клиенты WSE 3,0 и веб-службы, отправляющие сообщения SOAP с помощью транспорта TCP, не взаимодействуют с клиентами и веб-службами WCF. Эта несовместимость обусловлена различиями в кадрировании в протоколе TCP и причинами, связанными с обеспечением производительности. Однако пример WCF подробно описывает, как реализовать пользовательский сеанс TCP, взаимодействующий с WSE 3,0. Дополнительные сведения об этом примере см. в разделе [Transport: взаимодействие с TCP WSE 3,0](../../../../docs/framework/wcf/samples/transport-wse-3-0-tcp-interoperability.md).  
  
 Чтобы указать, что приложение WCF использует транспорт TCP, используйте [\<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
### <a name="custom-transport"></a>Пользовательский транспорт  
 Эквивалентом пользовательского транспорта WSE 3,0 в WCF является расширение канала. Дополнительные сведения о создании расширения канала см. [в разделе Расширение канального уровня](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
## <a name="see-also"></a>См. также:

- [Базовый жизненный цикл программирования](../../../../docs/framework/wcf/basic-programming-lifecycle.md)
- [Пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md)
- [Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Практическое руководство. Создание SecurityBindingElement для заданного режима проверки подлинности](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
