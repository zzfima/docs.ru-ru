---
title: Привязка HTTP для федерации WS 2007
ms.date: 03/30/2017
ms.assetid: 91c1b477-a96e-4bf5-9330-5e9312113371
ms.openlocfilehash: 0a01cd3790e17f532b2f6405f83c9507ecc2f6fd
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70038524"
---
# <a name="ws-2007-federation-http-binding"></a>Привязка HTTP для федерации WS 2007
В этом примере показано, как использовать <xref:System.ServiceModel.WS2007FederationHttpBinding> — стандартную привязку для создания федеративных сценариев, поддерживающих версию 1.3 спецификации WS-Trust.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Этот образец содержит консольную программу клиента (Client.exe), консольную служебную программу маркеров безопасности (Securitytokenservice.exe) и консольную программу службы (Service.exe). Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ". Контракт определяется интерфейсом `ICalculator`, который предоставляет математические операции (`Add`, `Subtract`, `Multiply` и `Divide`). Клиент получает маркер безопасности от службы маркеров безопасности (STS) и осуществляет синхронные вызовы службы для заданной математической операции. Служба отправляет в ответ результат. Действия клиента отображаются в окне консоли.  
  
 В этом образце контракт `ICalculator` делается доступным с помощью элемента `ws2007FederationHttpBinding`. В следующем коде показана конфигурация этой привязки на клиенте.  
  
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
  
 В [> безопасности значение указывает, какой режим безопасности следует использовать. \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md) `security` В этом примере `message` используется безопасность, [ \<поэтому](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)сообщение > задается в > безопасности. `ICalculator` [ Элемент\<](../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md) [ Issuer>всообщении>указываетадресипривязкудляSTS,котораявыдаетклиентумаркербезопасности,чтобы\<](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) клиент мог пройти проверку подлинности в службе.  
  
 В следующем коде показана конфигурация этой привязки на службе.  
  
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
  
 В [> безопасности значение указывает, какой режим безопасности следует использовать. \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md) `security` В этом примере `message` используется безопасность, [ \<поэтому](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)сообщение > задается в > безопасности. Элемент [> issuerMetadata внутри сообщения > указывает адрес и идентификатор для конечной точки, которые могут использоваться для получения метаданных для службы маркеров безопасности. \<](../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md) `ws2007FederationHttpBinding` [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md)  
  
 Поведение для службы показано в следующем коде.  
  
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
  
 > Иссуедтокенаусентикатион > позволяет службе указывать ограничения на токены, которые она разрешает клиентам во время проверки подлинности. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) Эта конфигурация указывает, что маркеры, подписанные сертификатом, у которых имя субъекта CN=STS, принимаются службой.  
  
 Служба маркеров безопасности делает единственную конечную точку доступной с помощью стандартной привязки <xref:System.ServiceModel.WS2007HttpBinding>. Служба отвечает на запросы маркеров от клиентов. Если клиент прошел проверку подлинности с использованием учетной записи Windows, служба выдает маркер, содержащий имя пользователя клиента в качестве утверждения. В одной из частей процедуры создания маркера служба маркеров безопасности подписывает маркер с использованием закрытого ключа, связанного с сертификатом CN=STS. Дополнительно она создает симметричный ключ и шифрует его с использованием открытого ключа, связанного с сертификатом CN=localhost. При возврате маркера клиенту служба маркеров безопасности также возвращает симметричный ключ. Клиент предъявляет выданный маркер службе `ICalculator` и подтверждает свое знание симметричного ключа, подписывая сообщение этим ключом.  
  
 При выполнении примера запрос маркера безопасности показан в окне консоли службы маркеров безопасности. Запросы и ответы операций появляются в окнах консоли клиента и службы. Чтобы закрыть приложение, нажмите клавишу ВВОД в любом из окон консоли.  

```
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714
Press <ENTER> to terminate client.
```

 Входящий в состав образца файл Setup.bat позволяет настроить сервер и службу маркеров безопасности с соответствующими сертификатами, необходимыми для выполнения резидентного приложения. Пакетный файл создает два сертификата в хранилище сертификатов LocalMachine/TrustedPeople. Имя субъекта первого сертификата CN=STS, он используется службой маркеров безопасности, чтобы подписывать маркеры безопасности, выдаваемые клиенту. Имя субъекта второго сертификата CN=localhost, он используется службой маркеров безопасности для шифрования ключа таким образом, чтобы служба могла его расшифровать.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Откройте Командная строка разработчика для Visual Studio с правами администратора и запустите файл Setup. bat, чтобы создать необходимые сертификаты.  
  
 Этот пакетный файл использует средства Certmgr.exe и Makecert.exe, поставляемые с пакетом Windows SDK. Однако файл Setup.bat необходимо запускать из командной строки Visual Studio, чтобы скрипт смог найти эти средства.  
  
1. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md). Если используется [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)], необходимо запустить Service. exe, Client. exe и SecurityTokenService. exe с повышенными привилегиями (щелкните файлы правой кнопкой мыши и выберите команду **Запуск от имени администратора**).  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] и примеры. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\WS2007FederationHttp`  
