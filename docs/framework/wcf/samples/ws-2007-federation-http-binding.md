---
title: Привязка HTTP для федерации WS 2007
ms.date: 03/30/2017
ms.assetid: 91c1b477-a96e-4bf5-9330-5e9312113371
ms.openlocfilehash: bf61e64733859d96adf42fbacf08266eca1f5b45
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183184"
---
# <a name="ws-2007-federation-http-binding"></a>Привязка HTTP для федерации WS 2007

В этом примере показано, как использовать <xref:System.ServiceModel.WS2007FederationHttpBinding> — стандартную привязку для создания федеративных сценариев, поддерживающих версию 1.3 спецификации WS-Trust.

> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

Образец состоит из клиентской программы на базе консолей *(Client.exe),* программы обслуживания токенов безопасности на основе консоли *(Securitytokenservice.exe)* и программы обслуживания на основе консолей *(Service.exe*). Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ". Контракт определяется интерфейсом `ICalculator`, который предоставляет математические операции (`Add`, `Subtract`, `Multiply` и `Divide`). Клиент получает маркер безопасности от службы маркеров безопасности (STS) и осуществляет синхронные вызовы службы для заданной математической операции. Служба отправляет в ответ результат. Действия клиента отображаются в окне консоли.

В этом образце контракт `ICalculator` делается доступным с помощью элемента `ws2007FederationHttpBinding`. Конфигурация этой привязки к клиенту отображается в следующем коде:

```xml
<bindings>
  <ws2007FederationHttpBinding>
    <binding name="ServiceFed" >
      <security mode ="Message">
        <message issuedKeyType ="SymmetricKey"
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >
          <!-- Endpoint address and binding for Security Token Service -->
          <issuer address ="http://localhost:8000/sts/windows"
                  binding ="ws2007HttpBinding" />
        </message>
      </security>
    </binding>
  </ws2007FederationHttpBinding>
</bindings>
```

На [ \<>безопасности ](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md) `security` значение определяет, какой режим безопасности следует использовать. В этом `message` примере используется безопасность, поэтому [ \<>сообщения](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) указана внутри [ \<>безопасности. ](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md) Эмитент [ \<>](../../configure-apps/file-schema/wcf/issuer.md) элемент внутри [ \<сообщения>](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) определяет адрес и привязку для STS, который выдает маркер безопасности клиенту, чтобы клиент мог проверить подлинность службы. `ICalculator`
  
Конфигурация этой привязки к службе отображается в следующем коде:

```xml
<bindings>
  <ws2007FederationHttpBinding>
    <binding name="ServiceFed" >
      <security mode ="Message">
        <message issuedKeyType ="SymmetricKey"
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >
          <!-- Metadata address for Security Token Service -->
          <issuerMetadata address ="http://localhost:8000/sts/mex" >
            <identity>
              <certificateReference storeLocation ="CurrentUser"
                                    storeName="TrustedPeople"
                                    x509FindType ="FindBySubjectDistinguishedName"
                                    findValue ="CN=STS" />
            </identity>
          </issuerMetadata>
        </message>
      </security>
    </binding>
  </ws2007FederationHttpBinding>
</bindings>
```

На [ \<>безопасности ](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md) `security` значение определяет, какой режим безопасности следует использовать. В этом `message` примере используется безопасность, поэтому [ \<>сообщения](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) указана внутри [ \<>безопасности. ](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md) [ \<элемент>в](../../configure-apps/file-schema/wcf/issuermetadata.md) [ \<сообщении,](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md)>`ws2007FederationHttpBinding` определяет адрес и идентификацию для конечной точки, которая может быть использована для получения метаданных для STS.

Поведение службы отображается в следующем коде:

```xml
<behaviors>
  <serviceBehaviors>
    <behavior name ="ServiceBehaviour" >
      <serviceDebug includeExceptionDetailInFaults ="true"/>
      <serviceMetadata httpGetEnabled ="true"/>
      <serviceCredentials>
        <issuedTokenAuthentication>
          <knownCertificates>
            <add storeLocation ="LocalMachine"
                 storeName="TrustedPeople"
                 x509FindType="FindBySubjectDistinguishedName"
                 findValue="CN=STS" />
          </knownCertificates>
        </issuedTokenAuthentication>
        <serviceCertificate storeLocation ="LocalMachine"
                            storeName ="My"
                            x509FindType ="FindBySubjectDistinguishedName"
                            findValue ="CN=localhost"/>
      </serviceCredentials>
    </behavior>
  </serviceBehaviors>
</behaviors>
```
  
ВыданноеToTokenAuthentication>> позволяет службе указывать ограничения на токены, которые она позволяет клиентам представить во время проверки подлинности. [ \<](../../configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) Эта конфигурация указывает, что маркеры, подписанные сертификатом, у которых имя субъекта CN=STS, принимаются службой.

Служба маркеров безопасности делает единственную конечную точку доступной с помощью стандартной привязки <xref:System.ServiceModel.WS2007HttpBinding>. Служба отвечает на запросы маркеров от клиентов. Если клиент прошел проверку подлинности с использованием учетной записи Windows, служба выдает маркер, содержащий имя пользователя клиента в качестве утверждения. В одной из частей процедуры создания маркера служба маркеров безопасности подписывает маркер с использованием закрытого ключа, связанного с сертификатом CN=STS. Дополнительно она создает симметричный ключ и шифрует его с использованием открытого ключа, связанного с сертификатом CN=localhost. При возврате маркера клиенту служба маркеров безопасности также возвращает симметричный ключ. Клиент предъявляет выданный маркер службе `ICalculator` и подтверждает свое знание симметричного ключа, подписывая сообщение этим ключом.

При выполнении примера запрос маркера безопасности показан в окне консоли службы маркеров безопасности. Запросы и ответы операций появляются в окнах консоли клиента и службы. Чтобы закрыть приложение, нажмите клавишу ВВОД в любом из окон консоли.

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714
Press <ENTER> to terminate client.
```

Файл *Setup.bat,* включенный в этот пример, позволяет настроить сервер и STS с соответствующими сертификатами для запуска самоходного приложения. Пакетный файл создает два сертификата в хранилище сертификатов LocalMachine/TrustedPeople. Имя субъекта первого сертификата CN=STS, он используется службой маркеров безопасности, чтобы подписывать маркеры безопасности, выдаваемые клиенту. Имя субъекта второго сертификата CN=localhost, он используется службой маркеров безопасности для шифрования ключа таким образом, чтобы служба могла его расшифровать.

## <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](one-time-setup-procedure-for-the-wcf-samples.md)

2. Откройте командный запрос разработчика для Visual Studio с привилегиями администратора и запустите файл Setup.bat для создания необходимых сертификатов.

 Этот пакетный файл использует *Certmgr.exe* и Makecert.exe, которые распространяются с Windows SDK. Тем не менее, необходимо запустить *Setup.bat* из команды Visual Studio, чтобы позволить скрипту найти эти инструменты.

1. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](building-the-samples.md).

2. Чтобы запустить образец в одно- или кросс-компьютерной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](running-the-samples.md) Если вы используете Windows Vista, вы должны запустить *Service.exe*, *Client.exe*, и *SecurityTokenService.exe* с повышенными привилегиями (право нажмите на файлы, а затем нажмите **Run в качестве администратора).**

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец находится в следующем каталоге:
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\WS2007FederationHttp`
