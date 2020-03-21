---
title: Безопасность сообщений при использовании очереди сообщений
ms.date: 03/30/2017
ms.assetid: 329aea9c-fa80-45c0-b2b9-e37fd7b85b38
ms.openlocfilehash: 2048b27f15787c70abda65ae582849276469c763
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144439"
---
# <a name="message-security-over-message-queuing"></a>Безопасность сообщений при использовании очереди сообщений
В этом образце показано, как реализовать приложение, использующее протокол WS-Security и проверку подлинности с использованием сертификата X.509v3 для клиента и требующее проверки подлинности сервера с использованием сертификата X.509v3 сервера через MSMQ. В некоторых случаях безопасность сообщений применяется, чтобы гарантировать, что сообщения в хранилище MSMQ остаются зашифрованными, а приложение может осуществлять собственную проверку подлинности сообщений.

 Этот образец основан на [транс-образной пробы Связывания МСМЗ.](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) Сообщения шифруются и подписываются.

### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)

2. При первом запуске служба проверит наличие очереди. Если очередь отсутствует, служба ее создаст. Можно сначала запустить службу, чтобы создать очередь, либо создать ее с помощью диспетчера очередей MSMQ. Чтобы создать очередь в Windows 2008, выполните следующие шаги.

    1. Открытый менеджер сервера в Visual Studio 2012.

    2. Расширьте вкладку **«Функции».**

    3. Справа щелкните **Очереди частных сообщений**и выберите **Новый,** **Частный Конвей**.

    4. Проверьте **транзакционную** коробку.

    5. Введите `ServiceModelSamplesTransacted` как имя новой очереди.

3. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).

### <a name="to-run-the-sample-on-the-same-computer"></a>Запуск образца на одном компьютере

1. Убедитесь, что путь включает папку, в которой содержатся файлы Makecert.exe и FindPrivateKey.exe.

2. Запустите файл Setup.bat из папки установки примера. При этом устанавливаются все сертификаты, необходимые для выполнения образца.

    > [!NOTE]
    > После завершения работы образца выполните в папке образца файл Cleanup.bat, чтобы удалить сертификаты. В других образцах обеспечения безопасности используются те же сертификаты.  
  
3. Запустите программу Service.exe из каталога \service\bin.  
  
4. Запустите программу Client.exe из каталога \client\bin. Действия клиента отображаются в консольном приложении клиента.  
  
5. Если клиент и служба не в состоянии общаться, [см.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))  
  
### <a name="to-run-the-sample-across-computers"></a>Запуск образца на нескольких компьютерах  
  
1. Скопируйте файлы Setup.bat, Cleanup.bat и ImportClientCert.bat на компьютер службы.  
  
2. Создайте на клиентском компьютере каталог для двоичных файлов клиента.  
  
3. Скопируйте в клиентский каталог на клиентском компьютере файлы программы клиента. Кроме того, скопируйте на клиент файлы Setup.bat, Cleanup.bat и ImportServiceCert.bat.  
  
4. На сервере выполните команду `setup.bat service`. Запуск `setup.bat` с `service` аргументом создает сертификат обслуживания с полностью квалифицированным доменным именем компьютера и экспортирует сертификат службы в файл под названием Service.cer.  
  
5. Отодеть сервис service.exe.config, чтобы отразить новое `findValue` имя сертификата (в атрибуте в [ \<сервисеСертификат>), ](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)который является таким же, как полностью квалифицированное доменное имя компьютера.  
  
6. Скопируйте файл Service.cer из каталога службы в клиентский каталог на клиентском компьютере.  
  
7. На клиенте выполните команду `setup.bat client`. При выполнении команды `setup.bat`с аргументом `client` создается сертификат клиента с именем client.com, который экспортируется в файл с именем Client.cer.  
  
8. В файле Client.exe.config на клиентском компьютере измените значение адреса конечной точки, чтобы оно соответствовало новому адресу службы. Для этого замените имя localhost полным доменным именем сервера.  Кроме того, необходимо изменить имя сертификата службы, чтобы оно совпадало с полным именем домена компьютера службы (в атрибуте `findValue` элемента `defaultCertificate` элемента `serviceCertificate` элемента `clientCredentials`).  
  
9. Скопируйте файл Client.cer из клиентского каталога в каталог службы на сервере.  
  
10. На клиенте выполните команду `ImportServiceCert.bat`. Он импортирует сертификат службы из файла Service.cer в хранилище CurrentUser - TrustedPeople.  
  
11. На сервере запустите файл `ImportClientCert.bat`. Он импортирует сертификат клиента из файла Client.cer в хранилище LocalMachine - TrustedPeople.  
  
12. На компьютере службы запустите из командной строки программу Service.exe.  
  
13. На клиентском компьютере из командной строки запустите программу Client.exe. Если клиент и служба не в состоянии общаться, [см.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))  
  
### <a name="to-clean-up-after-the-sample"></a>Очистка после образца  
  
- После завершения работы примера запустите в папке примеров файл Cleanup.bat.  
  
    > [!NOTE]
    > Этот скрипт не удаляет сертификаты службы на клиенте при запуске образца на нескольких компьютерах. Если вы используете образцы Windows Communication Foundation (WCF), которые используют сертификаты на всех компьютерах, обязательно очистите сертификаты службы, установленные в магазине CurrentUser - TrustedPeople. Для этого воспользуйтесь следующей командой: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`. Например: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.

## <a name="requirements"></a>Требования
 Для этого образца необходимо установить и запустить MSMQ.

## <a name="demonstrates"></a>Что демонстрирует
 Клиент шифрует сообщение с использованием открытого ключа службы и подписывает сообщение с помощью своего сертификата. Служба, считывающая сообщение из очереди, проверяет подлинность сертификата клиента с использованием сертификата в своем хранилище доверенных лиц. Затем она расшифровывает сообщение и перенаправляет сообщение операции службы.

 Поскольку сообщение Фонда связи Windows (WCF) переносится в виде полезной нагрузки в теле сообщения МСМЗ, тело остается зашифрованным в магазине МСМЗ. Это защищает сообщение от нежелательного раскрытия информации. Обратите внимание, что сама служба MSMQ не содержит сведений о том, зашифрованы ли передаваемые через нее сообщения.

 В этом образце показано, как использовать проверку подлинности на уровне сообщений в MSMQ. Обмен сертификатами осуществляется по внешним каналам. Это всегда имеет место в случае использования приложением очередей, поскольку клиенту и службе не обязательно быть запущенными и работать одновременно.

## <a name="description"></a>Описание
 Пример клиента и сервисный код совпадают с [трансепробным образцом Связывания МСМ з](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) с одним отличием. Для контракта операции в виде заметки задается уровень защиты, который предполагает, что сообщение должно подписываться и шифроваться.

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, ProtectionLevel=ProtectionLevel.EncryptAndSign)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 Чтобы сообщение защищалось с помощью маркера, позволяющего идентифицировать службу и клиент, файл App.config содержит учетные данные.

 В конфигурации клиента задается сертификат службы, который служит для проверки подлинности службы. В качестве доверенного хранилища используется хранилище LocalMachine, чтобы можно было полагаться на допустимость службы. Кроме того, задается сертификат клиента, который прикрепляется к сообщению с целью проверки подлинности клиента службой.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>

  <system.serviceModel>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"
                binding="netMsmqBinding"
                bindingConfiguration="messageSecurityBinding"
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor"
                behaviorConfiguration="ClientCertificateBehavior" />
    </client>

    <bindings>
        <netMsmqBinding>
            <binding name="messageSecurityBinding">
                <security mode="Message">
                    <message clientCredentialType="Certificate"/>
                </security>
            </binding>
        </netMsmqBinding>
    </bindings>

    <behaviors>
      <endpointBehaviors>
        <behavior name="ClientCertificateBehavior">
          <!--
        The clientCredentials behavior allows one to define a certificate to present to a service.
        A certificate is used by a client to authenticate itself to the service and provide message integrity.
        This configuration references the "client.com" certificate installed during the setup instructions.
        -->
          <clientCredentials>
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName" />
            <serviceCertificate>
                <defaultCertificate findValue="localhost" storeLocation="CurrentUser" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>
              <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it is trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
              <authentication certificateValidationMode="PeerOrChainTrust" />
            </serviceCertificate>
          </clientCredentials>
        </behavior>
      </endpointBehaviors>
    </behaviors>

  </system.serviceModel>
</configuration>
```

 Обратите внимание, что задан режим безопасности Message, а атрибут ClientCredentialType имеет значение Certificate.

 Конфигурация службы включает поведение службы, которое задает учетные данные службы, которые используются при проверке подлинности службы на стороне клиента. Имя предмета сертификата сервера указано в атрибуте `findValue` [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)в>.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>

  <appSettings>
    <!-- Use appSetting to configure MSMQ queue name. -->
    <add key="queueName" value=".\private$\ServiceModelSamplesMessageSecurity" />
  </appSettings>

  <system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.OrderProcessorService"
          behaviorConfiguration="PurchaseOrderServiceBehavior">
        <host>
          <baseAddresses>
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
          </baseAddresses>
        </host>
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"
                  binding="netMsmqBinding"
                  bindingConfiguration="messageSecurityBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
        <!-- The mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex. -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>

    <bindings>
        <netMsmqBinding>
            <binding name="messageSecurityBinding">
                <security mode="Message">
                    <message clientCredentialType="Certificate" />
                </security>
            </binding>
        </netMsmqBinding>
    </bindings>

    <behaviors>
      <serviceBehaviors>
        <behavior name="PurchaseOrderServiceBehavior">
          <serviceMetadata httpGetEnabled="True"/>
          <!--
               The serviceCredentials behavior allows one to define a service certificate.
               A service certificate is used by the service to authenticate itself to its clients and to provide message protection.
               This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCredentials>
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
            <clientCertificate>
                <certificate findValue="client.com" storeLocation="LocalMachine" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>
              <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it is trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
              <authentication certificateValidationMode="PeerOrChainTrust" />
            </clientCertificate>
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>

  </system.serviceModel>

</configuration>
```

 В этом образце демонстрируется управление проверкой подлинности с помощью файла конфигурации, а также получение удостоверения вызывающей стороны из контекста безопасности, как показано в следующем образце кода.

```csharp
// Service class which implements the service contract.
// Added code to write output to the console window.
public class OrderProcessorService : IOrderProcessor
{
    private string GetCallerIdentity()
    {
        // The client certificate is not mapped to a Windows identity by default.
        // ServiceSecurityContext.PrimaryIdentity is populated based on the information
        // in the certificate that the client used to authenticate itself to the service.
        return ServiceSecurityContext.Current.PrimaryIdentity.Name;
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {
        Console.WriteLine("Client's Identity {0} ", GetCallerIdentity());
        Orders.Add(po);
        Console.WriteLine("Processing {0} ", po);
    }
  //…
}
```

 При выполнении код службы выводит удостоверение клиента. Ниже показан образец результатов выполнения кода службы.

```console
The service is ready.
Press <ENTER> to terminate service.

Client's Identity CN=client.com; ECA6629A3C695D01832D77EEE836E04891DE9D3C
Processing Purchase Order: 6536e097-da96-4773-9da3-77bab4345b5d
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

## <a name="comments"></a>Комментарии

- Создание сертификата клиента.

     Следующая строка пакетного файла создает сертификат клиента. В качестве имени субъекта создаваемого сертификата используется указанное имя клиента. Сертификат сохраняется в хранилище `My` в расположении `CurrentUser`.

    ```bat
    echo ************
    echo making client cert
    echo ************
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
    ```

- Установка сертификата клиента в хранилище доверенных сертификатов сервера.

     Следующая строка пакетного файла копирует сертификат клиента в хранилище TrustedPeople сервера, чтобы сервер мог принимать соответствующие решения о доверии или недоверии. Для того чтобы сертификат, установленный в магазине TrustedPeople, был доверен службе Windows Communication `PeerOrChainTrust` Foundation `PeerTrust` (WCF), режим проверки сертификата клиента должен быть установлен или определен. Чтобы узнать, как это сделать с помощью файла конфигурации, см. приведенный выше образец конфигурации службы.

    ```bat
    echo ************
    echo copying client cert to server's LocalMachine store
    echo ************
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```

- Создание сертификата сервера.

     Следующие строки из файла Setup.bat создают используемый в дальнейшем сертификат сервера.

    ```bat
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

     Переменная %SERVER_NAME% задает имя сервера. Сертификат хранится в хранилище LocalMachine. Если пакетный файл настройки работает с аргументом `setup.bat service`службы (например, % SERVER_NAME% содержит полностью квалифицированное доменное имя компьютера. В противном случае он по умолчанию локального хозяина

- Установка сертификата сервера в хранилище доверенных сертификатов клиента.

     Следующая строка копирует сертификат сервера в хранилище доверенных лиц клиента. Этот шаг является обязательным, поскольку сертификаты, созданные с помощью программы Makecert.exe, не получают неявного доверия со стороны клиентской системы. Если уже имеется сертификат, имеющий доверенный корневой сертификат клиента, например сертификат, выпущенный корпорацией Майкрософт, выполнять этот шаг по добавлению сертификата сервера в хранилище сертификатов клиента не требуется.

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

    > [!NOTE]
    > Если используется выпуск Microsoft Windows на языке, отличном от английского (США), необходимо изменить файл Setup.bat и заменить имя учетной записи "NT AUTHORITY\NETWORK SERVICE" эквивалентом соответствующего языка.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\MessageSecurity`  
